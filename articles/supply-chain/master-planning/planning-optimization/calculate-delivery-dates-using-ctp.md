---
title: Calculer les dates de livraison des commandes clients à l’aide de CTP
description: La fonctionnalité Capable-to-Promise (CTP) vous permet de donner aux clients des dates réalistes auxquelles vous pouvez promettre des marchandises spécifiques. Cet article décrit comment configurer et utiliser CTP pour chaque moteur de planification (Optimisation de la planification et moteur de planification générale déprécié).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 4a3b8ba89d9fb224026cf32cad89d7f28321ee79
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741201"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Calculer les dates de livraison des commandes clients à l’aide de CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->
<!-- KFN: Split into two topics, one for PO and one for classic. -->

La fonctionnalité Capable-to-Promise (CTP) vous permet de donner aux clients des dates réalistes auxquelles vous pouvez promettre des marchandises spécifiques. Pour chaque ligne de vente, vous pouvez fournir une date qui tient compte du stock disponible existant, de la capacité de production et des temps de transport.

Le CTP étend [disponible à la promesse](../../sales-marketing/delivery-dates-available-promise-calculations.md) la fonctionnalité (ATP) en tenant compte des informations relatives aux capacités. Alors que l’ATP ne prend en compte que la disponibilité des matériaux et suppose des ressources de capacité infinies, le CTP tient compte à la fois la disponibilité des matériaux et de la capacité. Par conséquent, il permet de mieux déterminer si la demande peut être satisfaite dans un délai d’exécution donné.

Le CTP fonctionne de manière légèrement différente, selon le moteur de planification générale que vous utilisez (Optimisation de la planification ou le moteur de planification générale déprécié). Cet article explique comment configurer chaque moteur. CTP pour Optimisation de la planification ne prend actuellement en charge qu’un sous-ensemble des scénarios CTP pris en charge par le moteur de planification générale déprécié.

## <a name="turn-on-ctp-for-planning-optimization"></a>Activer CTP pour Optimisation de la planification

CTP pour le moteur de planification générale générale reste disponible. Cependant, si vous souhaitez utiliser CTP pour Optimisation de la planification, il doit être activé pour votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Planification*
- **Nom de la fonctionnalité :** *(Version préliminaire) CTP pour Optimisation de la planification*

## <a name="how-ctp-compares-to-atp"></a>Comparaison entre CTP et DAV

CTP et DAV sont similaires, mais CTP peut souvent fournir un résultat plus précis, comme le montre l’exemple suivant.

L’article A est un article composé des articles B et C, et la quantité en stock de l’article A est 0 (zéro). Si vous effectuez un contrôle DAV qui ne prend en compte que les matériaux, la quantité DAV sera également de 0 (zéro). Cependant, si vous effectuez un contrôle CTP, le système vérifiera la disponibilité des articles B et C, vérifiera les ressources nécessaires pour les transformer en article A et calculera combien d’articles A peuvent être fabriqués. En outre, le calcul du CTP peut vérifier les ressources et les matériaux nécessaires pour fabriquer davantage d’articles B et C, et les utiliser pour fabriquer davantage d’articles A.

Un calcul CTP qui prend en compte à la fois les matériaux et les ressources peut afficher une quantité plus importante qu’un calcul qui ne vérifie que les matériaux, en particulier lorsque l’article contrôlé est un article assemblé à la commande. En d’autres termes, la fonctionnalité CTP est basée sur la fonction d’éclatement et peut être exécutée pour une ligne de commande client sélectionnée afin de calculer la date de livraison prévue.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>Comment CTP diffère selon le moteur de planification que vous utilisez

Le tableau suivant résume les différences entre CTP pour l’Optimisation de la planification et CTP pour le moteur de planification générale déprécié.

| Elément | Optimisation de la planification | Moteur de planification générale déprécié |
|---|---|---|
| Paramètre **Contrôle de la date de livraison** des commandes, des lignes de commande et des produits | *CTP pour Optimisation de la planification* | *CTP* |
| Heure de calcul | Le calcul est déclenché par l’exécution d’un plan dynamique en tant que tâche planifiée. | Le calcul est immédiatement déclenché chaque fois que vous saisissez ou mettez à jour une ligne de commande client. |
| Valeur du champ **Statut CTP pour Optimisation de la planification** | <p>Une valeur *Pas prêt* s’affiche pour les commandes et les lignes de commande pour lesquelles le plan dynamique n’a pas été exécuté depuis la création ou la dernière mise à jour des commandes et des lignes.</p><p>Une valeur *Prêt* s’affiche pour les commandes et les lignes où le CTP a été utilisé pour calculer les dates de livraison confirmées en exécutant le plan dynamique.</p> | Une valeur *Prêt* est toujours affichée. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Définir les méthodes de contrôle de la date de livraison par défaut

Le système peut utiliser plusieurs méthodes pour calculer les estimations de date de livraison pour chaque commande et ligne de commande. Vous devez définir la méthode de contrôle de la date de livraison que vous souhaitez utiliser le plus souvent comme méthode globale par défaut. Vous pouvez également définir des dérogations individuelles pour chaque produit. Plus tard, vous pourrez remplacer les méthodes par défaut pour chaque commande et/ou ligne de commande selon vos besoins.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Définir le contrôle global de la date de livraison par défaut

La méthode de contrôle de la date de livraison par défaut sera appliquée à toutes les nouvelles lignes de commande où une substitution ne s’applique pas. Pour en sélectionner une, procédez comme suit :

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Dans l’onglet **Expéditions** sur le raccourci **Contrôle de livraison** dans le champ **Contrôle de la date de livraison**, sélectionnez la méthode que vous souhaitez utiliser comme méthode par défaut pour votre entreprise :

    - *Aucun* : ne pas calculer les dates de livraison.
    - *Délai de vente* – Le délai de vente est le temps entre la création de la commande client et l’expédition des articles. Le calcul de la date de livraison est basé sur un nombre de jours par défaut, et ne prend pas en compte pas la disponibilité du stock, la demande connue ni l’approvisionnement prévu.
    - *DAV* – Le DAV correspond à la quantité d’un article qui est disponible et peut être promise à un client à une date spécifique. Le calcul de DAV inclut le stock non engagé, les délais, les réceptions et les sorties prévues.
    - *DAV + Marge de sortie* – La date d’expédition correspond à la date DAV plus la marge de sortie de l’article. La marge de sortie est le temps nécessaire pour préparer les articles pour l’expédition.
    - *CTP* – Utilisez le calcul CTP fourni par le moteur de planification générale déprécié. Si vous utilisez l’Optimisation de la planification, la méthode de contrôle de la date de livraison *CTP* n’est pas autorisée et, si elle est sélectionnée, elle entraînera une erreur lors de l’exécution du calcul.
    - *CTP pour l’optimisation de la planification* – Utilisez le calcul CTP fourni par Optimisation de la planification. Cette option n’a aucun effet si vous utilisez le moteur de planification générale déprécié.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Définissez des substitutions de contrôle de la date de livraison pour des produits individuels

Vous pouvez attribuer des substitutions pour des produits spécifiques pour lesquels vous souhaitez utiliser une méthode de contrôle de la date de livraison autre que celle définie comme méthode globale par défaut.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez le produit que vous souhaitez configurer.
1. Dans le volet Actions, sur l’onglet **Gérer le stock**, dans le groupe **Paramètres de commande**, sélectionnez **Paramètres de commande par défaut**.
1. Sur la page **Paramètres de commande par défaut**, sur le raccourci **Commande client**, définissez l’option **Substituer le contrôle des livraisons** sur *Oui*.
1. Dans le champ **Contrôle de la date de livraison**, sélectionnez la méthode à utiliser pour le produit sélectionné. Les mêmes options décrites dans la section [Définir le contrôle global de la date de livraison par défaut](#global-default) sont disponibles.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Planifier le CTP pour les calculs d’optimisation de la planification

Lorsque vous utilisez CTP pour Optimisation de la planification, vous devez exécuter un plan dynamique pour déclencher le système afin qu’il effectue les calculs CTP, puis définir les dates d’expédition et de réception confirmées pour toutes les commandes pertinentes. Le plan doit inclure tous les articles pour lesquels des dates d’expédition et de réception confirmées sont requises. (Lorsque vous utilisez CTP pour le moteur de planification générale déprécié, les calculs CTP sont immédiatement effectués localement. Par conséquent, vous n’avez pas besoin d’exécuter un plan dynamique pour voir les résultats CTP.)

Pour vous assurer que les dates sont disponibles à temps pour tous les utilisateurs, nous vous recommandons de configurer des traitements par lots pour exécuter les plans pertinents de manière récurrente. Par exemple, un traitement par lots configuré pour exécuter un plan dynamique toutes les 30 minutes définira les dates d’expédition et de réception confirmées toutes les 30 minutes. Par conséquent, les utilisateurs qui saisissent et importent des commandes devront attendre un maximum de 30 minutes pour obtenir les dates d’expédition et de réception confirmées.

Pour configurer une tâche par lots afin d’exécuter un plan dynamique selon une planification régulière, procédez comme suit.

1. Accédez à **Planification principale \> Planification principale \> Exécuter \> Planification principale**.
1. Dans la boîte de dialogue **Planification générale** sur le raccourci **Paramètres**, définissez le champ **Plan principal** sur le plan dynamique que vous souhaitez exécuter.
1. Dans le raccourci **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur *Oui*.
1. Sélectionnez **Périodicité**, et configurez le programme selon vos besoins.
1. Cliquez sur **OK** pour enregistrer le programme.
1. Cliquez sur **OK** pour créer la tâche par lots et fermer la boîte de dialogue.

## <a name="use-ctp-for-the-deprecated-master-planning-engine"></a>Utiliser CTP pour le moteur de planification générale déprécié

### <a name="create-a-new-order-by-using-ctp-for-the-deprecated-master-planning-engine"></a>Créer une nouvelle commande en utilisant CTP pour le moteur de planification générale déprécié

Chaque fois que vous ajoutez une nouvelle commande client ou ligne de commande, le système lui affecte une méthode de contrôle de la date de livraison par défaut. L’en-tête de la commande commence toujours par la méthode globale par défaut. Si une substitution est attribuée à un article commandé, la nouvelle ligne de commande utilisera cette substitution. Sinon, la nouvelle ligne de commande utilisera également la méthode globale par défaut. Par conséquent, vous devez définir vos méthodes par défaut de manière à ce qu’elles correspondent à la méthode de contrôle des dates de livraison que vous utilisez le plus souvent. Après avoir créé une commande, vous pouvez remplacer la méthode par défaut au niveau de l’en-tête de commande et/ou de la ligne de commande selon vos besoins. Pour plus d’informations, voir [Définir les méthodes de contrôle de la date de livraison par défaut](#default-methods) et [Modifier les commandes clients existantes pour utiliser CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-the-deprecated-master-planning-engine"></a>Afficher les dates de livraison confirmées lorsque vous utilisez CTP pour le moteur de planification générale déprécié

Si vous utilisez le moteur de planification générale déprécié, les calculs CTP sont appliqués aux commandes et/ou aux lignes de commande où le champ **Contrôle de la date de livraison** est défini sur *CTP*.

Pour les lignes de vente qui utilisent CTP pour le moteur de planification générale déprécié, le système définit automatiquement les champs **Date d’expédition confirmée** et **Date de réception confirmée** chaque fois que vous enregistrez une ligne de vente. Si vous apportez ultérieurement une modification pertinente à une ligne de vente (par exemple, en modifiant sa quantité ou son site), les dates seront immédiatement recalculées.

- Pour afficher les dates de livraison confirmées pour une ligne de commande client, ouvrez la commande client et sélectionnez la ligne vente. Ensuite, sur le raccourci **Détails de ligne**, sur l’onglet **Livraison**, passez en revue les valeurs **Date d’expédition confirmée** et **Date de réception confirmée**.
- Pour afficher les dates de livraison confirmées pour une commande entière, ouvrez la commande client et sélectionnez la vue **En-tête**. Ensuite, sur le raccourci **Livraison**, passez en revue les valeurs **Date d’expédition confirmée** et **Date de réception confirmée**.

## <a name="use-ctp-for-planning-optimization"></a>Utiliser CTP pour Optimisation de la planification

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Créer une nouvelle commande en utilisant CTP pour Optimisation de la planification

Chaque fois que vous ajoutez une nouvelle commande client ou ligne de commande, le système lui affecte une méthode de contrôle de la date de livraison par défaut. L’en-tête de la commande commence toujours par la méthode globale par défaut. Si une substitution est attribuée à un article commandé, la nouvelle ligne de commande utilisera cette substitution. Sinon, la nouvelle ligne de commande utilisera également la méthode globale par défaut. Par conséquent, vous devez définir vos méthodes par défaut de manière à ce qu’elles correspondent à la méthode de contrôle des dates de livraison que vous utilisez le plus souvent. Après avoir créé une commande, vous pouvez remplacer la méthode par défaut au niveau de l’en-tête de commande et/ou de la ligne de commande selon vos besoins. Pour plus d’informations, voir [Définir les méthodes de contrôle de la date de livraison par défaut](#default-methods) et [Modifier les commandes clients existantes pour utiliser CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Afficher les dates de livraison confirmées lors de l’utilisation de CTP pour Optimisation de la planification

Si vous utilisez Optimisation de la planification, les calculs CTP sont appliqués aux commandes et/ou aux lignes de commande où le champ **Contrôle de la date de livraison** est défini sur *CTP pour Optimisation de la planification*.

Pour les lignes de vente qui utilisent CTP pour Optimisation de la planification, les champs **Date d’expédition confirmée** et **Date de réception confirmée** seront vides jusqu’à ce que vous exécutiez le plan dynamique approprié (généralement à l’aide d’une tâche par lots périodique). Ils sont alors automatiquement définis. Pour plus d’informations, voir [Programmer CTP pour les calculs d’optimisation de la planification](#batch-job).

Le champ **CTP pour l’état de l’optimisation de la planification** indique si les dates confirmées ont déjà été calculées pour chaque ligne qui utilise CTP pour Optimisation de la planification. Le champ affiche une valeur *Pas prêt* pour les lignes et les commandes dont les dates de livraison confirmées n’ont pas encore été calculées ou ne sont plus valides en raison d’autres modifications. Il affiche une valeur *Prêt* pour les lignes et les commandes qui ont été calculées. Vous pouvez afficher l’état de chaque ligne et de l’ensemble de la commande.

- Pour afficher l’état d’une ligne de commande client, ouvrez la commande client et sélectionnez la ligne vente. Ensuite, sur le raccourci **Détails de la ligne** dans l’onglet **Livraison**, passez en revue la valeur **CTP pour l’état de Optimisation de la planification**. Les champs **Date d’expédition confirmée** et **Date de réception confirmée** apparaissent également dans cet onglet après avoir été calculés.
- Pour afficher l’état d’une commande entière, ouvrez la commande client et sélectionnez la vue **En-tête**. Ensuite, sur le raccourci **Livraison**, passez en revue la valeur **CTP pour l’état de Optimisation de la planification**. Les champs **Date d’expédition confirmée** et **Date de réception confirmée** pour la commande apparaissent également dans cet onglet après avoir été calculés.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Si vous mettez à jour une ligne de commande client après que le CTP pour Optimisation de la planification a calculé les dates confirmées pour celle-ci, le système effacera ces dates jusqu’à la prochaine exécution du plan dynamique approprié.
> - Si vous modifiez un paramètre connexe susceptible d’affecter les dates confirmées existantes (par exemple, en modifiant les délais, les réservations ou les marquages), vous devez effacer les dates confirmées pour les commandes existantes pertinentes. Cette action entraînera le changement de l’état de chaque ligne concernée, qui sera défini sur *Pas prêt*. Cette modification, à son tour, obligera le système à recalculer les dates confirmées la prochaine fois qu’il exécutera le plan dynamique.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Modifier les commandes client existantes afin qu’elles utilisent CTP

Vous pouvez modifier la valeur **Contrôle de la date de livraison** pour toute commande ouverte à tout moment. Vous pouvez modifier la valeur au niveau de l’en-tête et/ou pour chaque ligne selon vos besoins.

### <a name="change-to-ctp-at-the-order-header-level"></a>Modifier vers CTP au niveau de l’en-tête de commande

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Pour modifier une commande afin qu’elle utilise CTP au niveau de l’en-tête de commande, procédez comme suit.

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.
1. Ouvrez la commande client que vous souhaitez configurer ou créez-en une nouvelle.
1. Sélectionnez **En-tête** pour ouvrir les informations sur l’en-tête sur la page **Détails de la commande client**.
1. Sur le raccourci **Livraison**, définissez le champ **Contrôle de la date de livraison** sur l’une des valeurs suivantes, selon le moteur de planification que vous utilisez :

    - *CTP* – Utilisez le calcul CTP fourni par le moteur de planification générale déprécié. Si vous utilisez Optimisation de la planification, la méthode de contrôle de la date de livraison *CTP* n’est pas autorisée. Par conséquent, si vous sélectionnez cette valeur, une erreur se produira lors de l’exécution du calcul.
    - *CTP pour l’optimisation de la planification* – Utilisez le calcul CTP fourni par Optimisation de la planification. Ce paramètre n’a aucun effet si vous utilisez le moteur de planification générale déprécié.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Sélectionner **OK** pour appliquer vos modifications.

### <a name="change-to-ctp-at-the-order-line-level"></a>Modifier vers CTP au niveau de la ligne de commande

Si vous avez créé une ligne de commande en utilisant une autre méthode de contrôle de la date de livraison, vous pouvez passer au CTP à tout moment. Les modifications que vous apportez au niveau de la ligne n’affectent aucune autre ligne. Cependant, elles peuvent entraîner l’avancement ou le recul des dates de livraison globales des commandes, en fonction de la modification du calcul de chaque ligne mise à jour. <!-- KFM: Confirm this intro at next revision -->

Pour modifier une commande afin qu’elle utilise CTP pour le moteur de planification générale déprécié au niveau de la ligne, procédez comme suit.

1. Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.
1. Ouvrez la commande client que vous souhaitez configurer ou créez-en une nouvelle.
1. Sur la page **Détails de la commande client**, sur le raccourci **Ligne de commande client**, sélectionnez la ligne de commande client que vous souhaitez configurer.
1. Sur le raccourci **Détails de la ligne**, définissez l’onglet **Livraison**, puis le champ **Contrôle de la date de livraison** sur l’une des valeurs suivantes, selon le moteur de planification que vous utilisez :

    - *CTP* – Utilisez le calcul CTP fourni par le moteur de planification générale déprécié. Si vous utilisez Optimisation de la planification, la méthode de contrôle de la date de livraison *CTP* n’est pas autorisée. Par conséquent, si vous sélectionnez cette valeur, une erreur se produira lors de l’exécution du calcul.
    - *CTP pour l’optimisation de la planification* – Utilisez le calcul CTP fourni par Optimisation de la planification. Ce paramètre n’a aucun effet si vous utilisez le moteur de planification générale déprécié.

    La boîte de dialogue **Dates d’expédition et de réception disponibles** s’affiche et indique les dates d’expédition et de réception disponibles. Cette boîte de dialogue fonctionne de la même manière pour les lignes de commande que pour l’en-tête de commande, comme décrit dans la section précédente.

1. Dans le volet Actions, sélectionnez **Enregistrer**.
