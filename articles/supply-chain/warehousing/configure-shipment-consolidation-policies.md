---
title: Configurer les stratégies de consolidation de l’expédition
description: Cet article explique comment configurer des stratégies de consolidation de l’expédition par défaut et personnalisées.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427980"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurer les stratégies de consolidation de l’expédition

[!include [banner](../includes/banner.md)]

Le processus de consolidation de l’expédition qui utilise des stratégies de consolidation permet une consolidation automatisée des expéditions lors du lancement automatique et manuel dans l’entrepôt. Après avoir activé cette fonctionnalité, vous devez configurer vos stratégies initiales. Si aucune stratégie n’est configurée, chaque ligne de vente générera une expédition distincte contenant une seule ligne de chargement.

Les scénarios présentés dans cet article montrent comment configurer des stratégies de consolidation d’expédition par défaut et personnalisées.

> [!WARNING]
> Si vous mettez à niveau un système Microsoft Dynamics 365 Supply Chain Management sur lequel vous utilisiez l’ancienne fonctionnalité de consolidation des expéditions, la consolidation risque de cesser de fonctionner comme prévu, sauf si vous suivez les conseils donnés ici.
>
> Sur les installations Supply Chain Management où la fonctionnalité *Stratégies de consolidation des expéditions* est désactivée, vous activez la consolidation des expéditions à l’aide du paramètre **Consolider l’expédition à la libération dans l’entrepôt** pour chaque entrepôt individuel. Cette fonctionnalité est obligatoire à partir de la version 10.0.29. Lorsqu’il est activé, le paramètre **Consolider l’expédition à la libération dans l’entrepôt** devient masqué et la fonctionnalité est remplacée par les *stratégies de consolidation des expéditions* qui sont décrites dans cet article. Chaque stratégie établit des règles de consolidation et inclut une requête pour contrôler où la stratégie s’applique. Lorsque vous activez la fonctionnalité pour la première fois, aucune politique de consolidation des expéditions ne sera définie sur la page **Stratégie de consolidation des expéditions**. Lorsqu’aucune stratégie n’est définie, le système utilise le comportement hérité. Ainsi, chaque entrepôt existant continue de respecter son paramètre **Consolider l’expédition à la libération dans l’entrepôt**, même si ce paramètre est maintenant masqué. Cependant, après avoir créé au moins une stratégie de consolidation des expéditions, le paramètre **Consolider l’expédition à la libération dans l’entrepôt** n’a plus d’effet et la fonctionnalité de consolidation est entièrement contrôlée par les stratégies.
>
> Après avoir défini au moins une stratégie de consolidation des expéditions, le système vérifie les stratégies de consolidation chaque fois qu’une commande est envoyée à l’entrepôt. Le système traite les stratégies en utilisant le classement défini par la valeur **Séquence de stratégies** de chaque stratégie. Il applique la première stratégie où la requête correspond à la nouvelle commande. Si aucune stratégie n’est configurée, chaque ligne de vente générera une expédition distincte contenant une seule ligne de chargement. Par conséquent, en guise de solution de rechange, nous vous recommandons de créer une stratégie par défaut qui s’applique à tous les entrepôts et groupes par numéro de commande. Donnez à cette stratégie de secours la valeur **Séquence de stratégies** la plus élevée, afin qu’elle soit traitée en dernier.
>
> Pour reproduire le comportement hérité, vous devez créer une stratégie qui ne regroupe pas par numéro de commande et qui a des critères de requête qui incluent tous les entrepôts pertinents.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Activer la fonctionnalité Stratégie de consolidation de l’expédition

Pour utiliser la fonctionnalité *Politiques de consolidation de l’expédition*, il doit être activer pour votre système. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Politiques de consolidation de l'expédition* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Configurer vos stratégies de regroupement initiales

Si vous utilisez un nouveau système ou un système sur lequel vous venez d’activer la fonctionnalité *Stratégies de consolidation des expéditions* pour la première fois, suivez ces étapes pour configurer vos stratégies initiales de consolidation des expéditions.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Dans le volet Actions, sélectionnez **Créer un paramétrage par défaut** pour créer les stratégies suivantes :

    - Une stratégie intitulée *Par défaut* pour le type de stratégie *Commandes client*.
    - Une stratégie intitulée *Par défaut* pour le type de stratégie *Problème de transfert*.
    - Une stratégie intitulée *CrossOrder* pour le type de stratégie *Problème de transfert*. (Cette stratégie est créée uniquement si vous aviez au moins un entrepôt où l’ancien paramètre **Consolider l’expédition à la libération dans l’entrepôt** a été activé.)
    - Une stratégie intitulée *CrossOrder* pour le type de stratégie *Commandes client*. (Cette stratégie est créée uniquement si vous aviez au moins un entrepôt où l’ancien paramètre **Consolider l’expédition à la libération dans l’entrepôt** a été activé.)

    > [!NOTE]
    > - Les deux stratégies *CrossOrder* prennent en compte le même ensemble de champs que la logique précédente. Cependant, elles tiennent également compte du champ du numéro de commande. (Ce champ est utilisé pour consolider les lignes en expéditions, en fonction de facteurs tels que l’entrepôt, le mode de transport et l’adresse.)
    > - Les deux stratégies *Par défaut* prennent en compte le même ensemble de champs que la logique précédente. Cependant, elles tiennent également compte du champ du numéro de commande. (Ce champ est utilisé pour consolider les lignes en expéditions, en fonction de facteurs tels que le numéro de commande, l’entrepôt, le mode de transport et l’adresse.)

1. Si le système a généré une stratégie *CrossOrder* pour le type de stratégie *Commandes*, sélectionnez-la, puis, dans le volet Actions, sélectionnez **Modifier la requête**. Dans l’éditeur de requêtes, vous pouvez voir pour lequel de vos entrepôts le paramètre **Consolider l’expédition à la libération dans l’entrepôt** a été précédemment activé. Par conséquent, cette stratégie reproduit vos paramètres précédents pour ces entrepôts.
1. Personnalisez les nouvelles stratégies par défaut selon vos besoins en ajoutant ou en supprimant des champs et/ou en modifiant les requêtes. Vous pouvez également ajouter autant de stratégies que nécessaire. Pour obtenir des exemples montrant comment personnaliser et configurer vos stratégies, consultez l’exemple de scénario plus loin dans cet article.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Scénario : Configurer les stratégies de consolidation des expéditions personnalisées

Ce scénario fournit un exemple qui montre comment configurer des stratégies de consolidation d’expédition personnalisées, puis les tester à l’aide de données de démonstration. Les stratégies personnalisées peuvent prendre en charge des exigences commerciales complexes où la consolidation des expéditions dépend de plusieurs conditions. Pour chaque exemple de stratégie plus loin dans ce scénario, une brève description de l’analyse de rentabilisation est incluse. Ces exemples de stratégies doivent être configurés dans une séquence qui garantit une évaluation pyramidale des requêtes. (En d’autres termes, les stratégies qui ont le plus de conditions doivent être évaluées comme ayant la plus haute priorité.)

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Ce scénario fait référence à des valeurs et des enregistrements inclus dans les [données de démonstration](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard fournies pour Supply Chain Management. Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur *USMF* avant de commencer.

### <a name="prepare-master-data-for-this-scenario"></a>Préparer les données principales pour ce scénario

Avant de pouvoir effectuer les exercices de ce scénario, vous devez préparer les données principales requises pour effectuer le filtrage, comme décrit dans les sous-sections suivantes. (Ces conditions préalables s’appliquent également aux scénarios répertoriés dans la [section Exemples de scénarios d’utilisation des stratégies de consolidation de l’expédition](#example-scenarios).)

#### <a name="create-two-new-product-filter-codes"></a>Créer deux codes de filtre de produit

1. Allez dans **Gestion des entrepôts \> Configuration \> Filtres de produit \> Filtres de produit** et ajoutez deux filtres de produit :

    - Filtre de produit 1 :

        - **Code du filtre :** *Inflammable*
        - **Titre du filtre :** *Code 4*

    - Filtre de produit 2 :

        - **Code du filtre :** *Explosif*
        - **Titre du filtre :** *Code 4*

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit ayant le numéro d’article *M9200*. (Le produit que vous sélectionnez doit être activé pour le processus \[WMS\] des entrepôts avancées, et ce produit est pré-activé pour les processus WMS dans les données de démonstration **USMF**.)
1. Dans le raccourci **Entrepôt**, définissez le champ **Code 4** sur *Inflammable*.
1. Fermez la page.
1. Ouvrez le produit ayant le numéro d’article *M9201*. (Ce produit est également pré-activé pour les processus WMS dans les données de démonstration **USMF**.)
1. Dans le raccourci **Entrepôt**, définissez le champ **Code 4** sur *Explosif*.
1. Fermez la page.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Créer un nouveau mode de livraison

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Mode**.
1. Créez un mode de transport qui sera utilisé dans les requêtes de consolidation et nommez-le *Avion*.
1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.
1. Créez un transporteur possédant les paramètres suivants :

    - **Transporteur :** *Avion*
    - **Nom :** *Avion*
    - **Mode :** *Avion*

1. Dans le raccourcis **Services** du nouveau transporteur, ajoutez une ligne ayant les paramètres suivants :

    - **Service de transporteur :** *Air*
    - **Mode de transport :** *Air*

1. Dans le volet Actions, sélectionnez **Enregistrer**.

    > [!NOTE]
    > Lorsque vous enregistrez le nouveau transporteur, le champ **Mode de livraison** de la nouvelle ligne de la grille **Services** est automatiquement défini sur *Airwa-Air*. Lorsque vous utilisez le mode de livraison *Airwa-Air* pour une commande client, le mode de transport *Avion* sera utilisé pour les expéditions associées.

#### <a name="create-an-order-pool"></a>Créer un regroupement de commandes

1. Allez dans **Ventes et marketing \> Configuration \> Commandes client \> Regroupements de commandes**.
1. Créez un regroupement de commandes qui sera utilisé pour la requête de consolidation. Ce regroupement de commandes doit avoir les paramètres suivants :

    - **Regroupement :** Entrez un entier qui n’est pas déjà utilisé par un autre regroupement.
    - **Nom :** *ShipCons*

1. Allez dans **Ventes et marketing \> Clients \> Tous les clients**.
1. Ouvrez le client qui a un numéro de compte *US-003*.
1. Dans le raccourci **Valeurs par défaut des commandes client**, définissez le champ **Regroupement de commandes client** sur le regroupement de commandes que vous venez de créer.
1. Fermez la page, puis répétez les étapes 4 et 5 pour le client ayant le numéro de compte *US-004*.

### <a name="create-example-policy-1"></a>Créer un exemple de stratégie 1

Dans cet exemple, vous allez créer une stratégie *Client + Mode* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un compte client spécifique (*US-001*) et un mode de livraison spécifique (*Airwa-Air*).
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée par ID de commande. (En d’autres termes, il y aura des expéditions distinctes par commande, entrepôt, etc.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *CustomerMode*
    - **Description de la stratégie :** *Compte client et mode de livraison*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, dans la grille, recherchez la ligne où le champ **Champ** est défini sur *Compte client* et définissez le champ **Critères** pour cette ligne sur *US-001*.
1. Sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Lignes de commande*
    - **Table dérivée :** *Lignes de commande*
    - **Champ :** *Mode de livraison*
    - **Critères :** *Airwa-Air*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, les lignes de commande pour le client *US-001* qui utilisent le mode de livraison *Airwa-Air* ne seront pas consolidées dans l’ensemble des commandes. Cette stratégie est destinée à être utilisée en premier dans une séquence, dans les cas où les expéditions pour tous les autres modes de livraison sont consolidées pour ce client.

### <a name="create-example-policy-2"></a>Créer un exemple de stratégie 2

Dans cet exemple, vous allez créer une stratégie *Marchandises dangereuses* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un code de filtre spécifique (*dangereux*) et un mode de livraison spécifique (*Airwa-Air*).
- La consolidation avec les expéditions en cours est activée.
- La consolidation est effectuée dans l’ensemble des commandes. (En d’autres termes, il y aura des expéditions distinctes par compte, entrepôt, etc., mais uniquement au sein du groupe d’articles spécifié dans la requête.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Type d’élément*
    - **Description de la stratégie :** *Consolider le même type d’article dans l’ensemble des commandes*

1. Définissez l’option **Consolider avec des expéditions en cours** définie sur *Oui*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Jointures**, développez et sélectionnez **Tables \> Détails du chargement** dans l’arborescence.
1. Sélectionnez **Ajouter une jointure de table**.
1. Dans la grille de relations qui apparaît, recherchez et sélectionnez la ligne où le champ **Relation** est défini sur *Numéro d’article de l’entrepôt (numéro d’article)*, puis sélectionnez **Sélectionner**. 
1. Dans l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Numéro d’article de l’entrepôt*
    - **Table dérivée :** *Numéro d’article de l’entrepôt*
    - **Champ :** *Code 4*
    - **Critères :** *Inflammable*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les articles ont un code de filtre spécifique (c’est-à-dire le code de filtre où le champ **Code 4** est défini sur *Inflammable*) seront consolidées avec d’autres articles du même type dans toutes les commandes. S’il y a une expédition en cours pour le même compte, entrepôt et groupe d’articles, les nouvelles lignes y seront attachées.

### <a name="create-example-policy-3"></a>Créer un exemple de stratégie 3

Dans cet exemple, vous allez créer une stratégie *Besoins du client* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un compte client spécifique.
- La consolidation avec les expéditions en cours est activée.
- La consolidation se fait entre les commandes mais est basée sur les demandes des clients. (En d’autres termes, plusieurs commandes seront regroupées en expéditions, en fonction du même numéro de demande client et du même entrepôt.)

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *CustomerOrderNo*
    - **Description de la stratégie :** *Consolider les lignes en fonction du bon de commande client*

1. Définissez l’option **Consolider avec des expéditions en cours** définie sur *Oui*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Demande client*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans la liste **Champs restants**, sélectionnez la ligne où le champ **Nom de champ** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, recherchez la ligne où le champ **Champ** est défini sur *Compte client* et définissez le champ **Critères** pour cette ligne sur *US-001*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les commandes client ont le même numéro de demande client seront regroupées en une seule expédition, quel que soit le numéro de commande client. (Le numéro de demande du client est utilisé comme bon de commande du client \[PO\].) S’il y a une expédition en cours pour le même compte, entrepôt et demande client, les nouvelles lignes y seront attachées. Cette stratégie peut être utilisée si le client envoie des lignes de commande supplémentaires qui ont le même numéro de bon de commande plusieurs fois au cours d’une journée et souhaite que toutes les lignes soient regroupées en une seule expédition. (En d’autres termes, il y aura une feuille de chargement et un bon de livraison.)

### <a name="create-example-policy-4"></a>Créer un exemple de stratégie 4

Dans cet exemple, vous allez créer une stratégie *Clients autorisant la consolidation* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un regroupement de commandes spécifique pour identifier les clients qui acceptent les expéditions consolidées.
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée entre les commandes à l’aide des champs sélectionnés par la stratégie CrossOrder par défaut (pour répliquer la case à cocher **Consolider l’expédition au lancement dans l’entrepôt** antérieure).

- Vous pouvez remplacer la règle sur une commande client en sélectionnant un regroupement de commandes différent.

Suivez ces étapes pour créer la stratégie de consolidation des expéditions pour cette analyse de rentabilisation.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Regroupement de commandes*
    - **Description de la stratégie :** *Consolider les commandes en fonction du regroupement de commandes*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans la liste **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :

    - **Table :** *Commandes client*
    - **Table dérivée :** *Commandes client*
    - **Champ :** *Regroupement*
    - **Critères :** *ShipCons*

1. Sélectionnez **OK** pour fermer la boîte de dialogue.

> [!NOTE]
> Pour cette analyse de rentabilisation, toutes les lignes de commande où les commandes client appartiennent au même regroupement de commandes seront consolidées en une seule expédition parmi les commandes client pour le même compte, entrepôt et mode de livraison de transport. Au lieu du regroupement de commandes, vous pouvez utiliser n’importe quel autre champ pour distinguer un groupe de clients et utiliser l’en-tête de commande client par défaut. Vous pouvez utiliser cette approche si le client, et non l’entrepôt, émet le besoin de consolidation. (Dans la logique de consolidation antérieure, l’entrepôt était à l’origine du besoin de consolidation.)

### <a name="create-example-policy-5"></a>Créer un exemple de stratégie 5

Dans cet exemple, vous allez créer une stratégie *Entrepôts autorisant la consolidation* qui peut être utilisée pour l’analyse de rentabilisation suivante :

- La stratégie recherchera un regroupement de commandes spécifique pour identifier les entrepôts qui peuvent consolider les expéditions.
- La consolidation avec les expéditions en cours est désactivée.
- La consolidation est effectuée entre les commandes à l’aide des champs sélectionnés par la stratégie CrossOrder par défaut (pour répliquer la case à cocher **Consolider l’expédition au lancement dans l’entrepôt** antérieure).

En règle générale, cette analyse de rentabilisation peut être traitée à l’aide des stratégies par défaut que vous avez créées dans le [Configurer vos stratégies de consolidation initiales](#initial-policies). Cependant, vous pouvez également créer manuellement des stratégies similaires en suivant ces étapes.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une stratégie qui possède les paramètres suivants :

    - **Nom de la stratégie :** *Commande croisée*
    - **Description de la stratégie :** *Consolidation des commandes croisées pour des entrepôts spécifiques*

1. Laissez l’option **Consolider avec des expéditions en cours** définie sur *Non*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le raccourci **Champs de consolidation**, dans le champ **Champs restants**, sélectionnez la ligne où **Nom de domaine** est défini sur *Mode de livraison*.
1. Sélectionnez le bouton **Ajouter** ![Flèche droite.](media/forward-button.png) pour déplacer le champ vers la liste **Champs sélectionnés**.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Dans la boîte de dialogue de l’éditeur de requête, sur l’onglet **Plage**, recherchez la ligne où le champ **Champ** est défini sur *Entrepôt* et définissez le champ **Critères** pour cette ligne sur *61, 63*.
1. Sélectionnez **OK** pour fermer la boîte de dialogue.

### <a name="set-the-order"></a>Définir la commande

Maintenant que vous avez créé toutes vos stratégies, vous devez établir l’ordre dans lequel elles seront appliquées. Pour utiliser une approche pyramidale, où les stratégies qui ont le plus de conditions sont évaluées comme ayant la priorité la plus élevée, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.
1. Définissez le champ **Type de stratégie** sur *Commandes client*.
1. Sélectionnez chaque stratégie répertoriée dans la colonne de gauche, puis utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** du volet Actions pour organiser les stratégies dans l’ordre suivant :

    1. CustomerMode
    1. Type d’article
    1. CustomerOrderNo
    1. Regroupement de commandes
    1. Ordre croisé
    1. Valeur par défaut

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Exemples de scénarios d’utilisation des stratégies de consolidation de l’expédition

Les scénarios suivants illustrent la façon dont vous pouvez utiliser les stratégies de consolidation de l’expédition créées lors de la lecture de cet article. Chaque scénario vous guide tout au long du processus de consolidation de l’expédition qui utilise des stratégies de consolidation lors du lancement automatique ou manuel dans l’entrepôt :

- Scénario 1 : [Consolider les expéditions lorsqu’elles sont transmises à l’entrepôt à l’aide de la procédure Lancement automatique des commandes client dans l’entrepôt](../warehousing/consolidate-shipments-automatic.md)
- Scénario 2 : [Consolider les expéditions lorsque la stratégie de consolidation de l’expédition est remplacée à partir de la page Lancement dans l’entrepôt](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scénario 3 : [Consolider les expéditions à l’aide de page Lancement dans l’entrepôt à partir de l’atelier de planification des chargements](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scénario 4 : [Consolider les expéditions à l’aide de l’atelier de consolidation d’expédition](../warehousing/consolidate-shipments-manual-workbench.md)
- Scénario 5 : [Consolider les expéditions manuellement à l’aide de la page Consolider les expéditions](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des stratégies de consolidation de l’expédition](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
