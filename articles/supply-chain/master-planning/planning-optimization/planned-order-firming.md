---
title: Commandes prévisionnelles confirmées
description: Cette rubrique explique comment confirmer des commandes prévisionnelles. Lorsque des commandes prévisionnelles sont confirmées, elles deviennent des commandes fournisseur, des ordres de transfert ou des ordres de fabrication réels.
author: t-benebo
ms.date: 04/22/2021
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30f3ee656b97e0337b6e3e78f0acb2300d7d85dc
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468466"
---
# <a name="firm-planned-orders"></a>Commandes prévisionnelles confirmées

[!include [banner](../../includes/banner.md)]

Les commandes prévisionnelles doivent être *confirmées* (c’est-à-dire lancées) dans le cadre du processus de planification principal. Lorsque des commandes prévisionnelles sont confirmées, elles deviennent des commandes fournisseur, des ordres de transfert ou des ordres de fabrication réels. Elles sont également connues sous le nom de *commandes lancées* ou *commandes en cours*.

Il existe trois méthodes pour confirmer les commandes prévisionnelles :

- **Confirmation manuelle** – Sélectionnez des commandes prévisionnelles spécifiques dans une liste, puis démarrez le processus manuellement.
- **Confirmation automatique** – Définissez une plage horaire de confirmation par défaut pour les groupes de couverture, les éléments individuels et les combinaisons d’éléments et de plans directeurs. Ensuite, pendant les cycles de planification générale, les commandes prévisionnelles seront automatiquement confirmées si la date de commande se situe dans la plage de temps spécifiée pour la confirmation.
- **Confirmation basée sur les requêtes** – Définissez une requête pour sélectionner les commandes prévisionnelles en fonction de leurs propriétés. Vous pouvez configurer un traitement par lots pour exécuter la requête et confirmer les commandes correspondantes selon un calendrier régulier.

Cette rubrique décrit chaque méthode en détail.

## <a name="enable-the-features-that-are-described-in-this-topic"></a><a name="enable-features"></a>Activer les fonctionnalités décrites dans cette rubrique

La plupart des fonctionnalités de commandes prévisionnelles sont disponibles dans toutes les installations standard de Microsoft Dynamics 365 Supply Chain Management qui utilisent l’optimisation de la planification. Cependant, certaines des fonctionnalités décrites dans cette rubrique doivent être activées dans la gestion des fonctionnalités avant de pouvoir être utilisées.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Activer ou désactiver la confirmation de la mise en parallèle des commandes prévisionnelles

La confirmation de la mise en parallèle permet d’accélérer le processus de confirmation en le mettant en parallèle sur plusieurs threads. Cette approche peut être utile lorsque de nombreuses commandes prévisionnelles sont confirmées. Pour utiliser cette fonctionnalité, la fonctionnalité *Consolidation parallèle des commandes planifiées* doit être activée pour votre système. À compter de la version 10.0.21 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, vous pouvez ensuite activer ou désactiver cette fonctionnalité en accédant à [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et en recherchant la fonction *Confirmation de la mise en parallèle des ordres prévisionnels*.

### <a name="enable-planned-order-firming-with-filtering"></a>Activer la confirmation des commandes prévisionnelles avec filtrage

La confirmation des commandes prévisionnelles avec filtrage vous permet de définir des critères logiques pour sélectionner les commandes prévisionnelles à confirmer. Vous pouvez également prévisualiser les commandes prévisionnelles sélectionnées, exécuter le processus en arrière-plan et/ou le planifier en tant que traitement par lots.

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Confirmation de l’ordre planifié avec filtrage* dans l’espace de travail [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-auto-firming-for-planning-optimization"></a>Activer la confirmation automatique pour l’Optimisation de la planification

La confirmation automatique vous permet de confirmer les commandes prévisionnelles dans le cadre du processus de planification durant la plage de gestion de confirmation. La confirmation automatique est toujours prise en charge pour le moteur de planification intégré à Supply Chain Management. Vous devez cependant activer la fonctionnalité pour l’utiliser également avec l’Optimisation de la planification.

Pour rendre cette fonctionnalité disponible dans votre système, accédez à [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), et activez la fonctionnalité *Confirmation automatique de l’Optimisation de la planification*. (Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut.)

## <a name="manually-firm-planned-orders"></a>Confirmer manuellement les commandes prévisionnelles

Pour confirmer manuellement les commandes prévisionnelles, recherchez et sélectionnez celles que vous souhaitez confirmer, puis démarrez manuellement le processus de confirmation.

1. [Ouvrir n’importe quelle page de liste de commandes prévisionnelles](approved-planned-order.md#view-planned-orders).
1. Utilisez le champ **Filtrer**, **Plan** et les en-têtes de champ et de colonne pour filtrer et trier la liste afin de trouver les commandes prévisionnelles que vous recherchez.
1. Activez la case à cocher en regard de chaque commande prévisionnelle à confirmer. Si vous souhaitez confirmer toutes les commandes prévisionnelles actuellement répertoriées sur la page (en fonction des filtres que vous avez appliqués), ignorez cette étape.
1. Sur le volet Actions, sélectionnez l’un des boutons suivants :

    - **Confirmer** – Confirmer uniquement les commandes prévisionnelles sélectionnées.
    - **Confirmer tout** – Confirmer toutes les commandes prévisionnelles actuellement répertoriées sur la page (en fonction des filtres que vous avez appliqués), quelles que soient les cases à cocher sélectionnées. Cette option peut être utile si vous confirmez plusieurs commandes prévisionnelles.

1. Dans la boîte de dialogue **Confirmation**, sur le raccourci **Paramètres**, définissez les champs suivants : (Beaucoup de ces champs tirent leurs valeurs par défaut de l’onglet **Mise à jour standard** sur la page **Paramètres de planification**.)

    - **Mettre à jour le marquage** – Sélectionnez la politique de marquage du stock à utiliser lors de la confirmation de commandes prévisionnelles.
    - **Arrêter la confirmation si une erreur se produit** – Définissez cette option sur *Oui* pour arrêter de confirmer toutes les commandes prévisionnelles sélectionnées si une erreur se produit dans l’une d’entre elles. Cette option doit être définie sur *Non* si l’option **Confirmation de la mise en parallèle** est définie sur *Oui*.
    - **Confirmation de la mise en parallèle** – Cette option n’est disponible que si la fonctionnalité [*Confirmation de la mise en parallèle des commandes prévisionnelles*](#enable-features) est activée dans votre système et si vous avez sélectionné au moins deux commandes prévisionnelles pour confirmation. Définissez l’option sur *Oui* pour exécuter les processus de conformation en parallèle. Une confirmation de la mise en parallèle peut aider à améliorer les performances.
    - **Nombre de threads** – Cette option n’est disponible que si la fonctionnalité [*Confirmation de la mise en parallèle des commandes prévisionnelles*](#enable-features) est activée dans votre système et si vous avez défini l’option **Confirmation de la mise en parallèle** sur *Oui*. Entrez le nombre de threads à utiliser pour mettre en parallèle le processus de confirmation. Pour obtenir des conseils sur l’utilisation de cette option dans la planification générale, voir [Améliorer les performances de planification](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Une valeur *0* (zéro) pour le champ **Nombre de threads** augmente le temps d’exécution de la planification générale. Par conséquent, nous vous recommandons de toujours définir ce champ sur une valeur supérieure à 0.

    - **Regrouper par fournisseur** – Définissez cette option sur *Oui* pour regrouper les commandes fournisseur prévisionnelles et créer une commande d’achat par fournisseur lors de la confirmation. Vous pouvez également créer une commande fournisseur ayant une ligne pour chaque commande prévisionnelle.
    - **Regrouper par groupe d’acheteurs** – Définissez cette option sur *Oui* pour regrouper les commandes fournisseur prévisionnelles et créer une commande fournisseur qui combine le groupe de fournisseurs et le groupe d’acheteurs. Pour utiliser cette option, vous devez également définir l’option **Regrouper par fournisseur** sur *Oui*.
    - **Regrouper par contrat d’achat** : définissez cette option sur *Oui* pour regrouper les commandes fournisseur planifiées avec le même fournisseur comme contrats d’achat existants et créer une commande fournisseur par contrat d’achat. Cette option est automatiquement activée lorsque **Regrouper par fournisseur** est activé. Pour utiliser l’option **Regrouper par contrat d’achat**, l’option **Rechercher des contrats d’achat** doit être définie sur *Oui* dans la page **Paramètres de planification générale**.
    - **Regrouper par période** (dans la section **Commandes fournisseur**) – Sélectionnez la période selon laquelle regrouper les commandes fournisseur prévisionnelles. Pour utiliser cette option, vous devez également sélectionner l’option **Regrouper par fournisseur**.
    - **Regrouper par période** (dans la section **Transferts**) – Sélectionnez la période selon laquelle regrouper les ordres de transfert prévisionnels. Les commandes seront regroupées en fonction des valeurs **Entrepôt d’origine** et **Entrepôt de destination**.

    > [!NOTE]
    > Chacune des options "Grouper par" amène le système à convertir chaque commande planifiée en une ligne dans la commande fournisseur unique qui résulte du regroupement.

    ![Raccourci Paramètres dans la boîte de dialogue Confirmation.](./media/manual-firming.png "Raccourci Paramètres dans la boîte de dialogue Confirmation")

1. Sur le raccourci **Exécuter à l’arrière-plan**, configurez le processus pour qu’il s’exécute par lots. Cependant, cela n’a pas de sens de mettre en place un calendrier récurrent lorsque vous effectuez une confirmation manuelle. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management. Cependant, pour la confirmation manuelle, le traitement par lots ne traitera que les commandes prévisionnelles actuellement sélectionnées. Il ne traitera aucune commande correspondant aux filtres actuellement appliqués sur la page.
1. Cliquez sur **OK** pour appliquer vos paramètres et générer des commandes confirmées.

## <a name="auto-firm-planned-orders"></a>Confirmation automatique des commandes prévisionnelles

La confirmation automatique vous permet de confirmer des commandes prévisionnelles dans le cadre du processus de planification. Vous pouvez définir une plage horaire de confirmation par défaut pour les groupes de couverture, les éléments individuels et les combinaisons d’éléments et de plans directeurs. Ensuite, pendant les cycles de planification générale, les commandes prévisionnelles seront automatiquement confirmées si la date de commande se situe dans la plage de temps spécifiée pour la confirmation. Les commandes prévisionnelles générées par l’optimisation de la planification et l’opération de planification principale intégrée gèrent différemment la date de la commande (c’est-à-dire la date de début).

> [!NOTE]
> La confirmation automatique de commandes fournisseur prévisionnelles n’est possible que si les articles sont associés à un fournisseur.
> 
> Les commandes dérivées (c’est-à-dire les commandes d’achat de sous-traitance) confirmées afficheront un statut *En cours de révision* si le suivi des modifications de dossier est activé.

> [!IMPORTANT]
> Avant que la fonctionnalité décrite dans cette section puisse être utilisée avec Optimisation de la planification, la fonctionnalité [*Confirmation automatique de l’Optimisation de la planification*](#enable-features) doit être activée dans votre système, comme décrit au début de cette rubrique. La confirmation automatique peut toujours être utilisée avec le moteur de planification principal intégré.

### <a name="auto-firming-with-planning-optimization-vs-the-built-in-planning-engine"></a>Confirmation automatique avec l’option Optimisation de la planification par rapport au moteur de planification intégré

L’option Optimisation de planification et le moteur de planification intégré peuvent être utilisés pour confirmer automatiquement les commandes prévisionnelles. Toutefois, il existe des différences importantes. Par exemple, l’option Optimisation de la planification utilise la date de commande (à savoir la date de début) pour déterminer quelles commandes prévisionnelles confirmer, tandis que le moteur de planification intégré utilise la date de demande (à savoir la date de fin). Le tableau suivant résume les différences.

| Fonctionnalité | Service Optimisation de la planification | Moteur de planification intégré |
|---|---|---|
| **Base de la date** | La confirmation automatique est basée sur la date de commande (date de début). | La confirmation automatique est basée sur la date de besoin (date de fin). |
| **Délai** | Puisque la date de commande (date de début) déclenche la confirmation, vous n’avez pas à tenir compte du délai d’exécution dans le cadre de la plage de confirmation. | Pour assurer que les commandes sont confirmées en temps voulu, la plage de confirmation doit être plus longue que le délai d’exécution. |
| **Commandes pour la semaine en cours** | Pour confirmer toutes les commandes qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être d’une semaine. | Pour confirmer toutes les commandes qui doivent commencer pendant la semaine en cours, la plage de confirmation doit être le délai d’exécution plus une semaine. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Mettre en place la confirmation automatique et la plage de gestion de la confirmation

Vous devez activer la confirmation automatique en attribuant une plage de gestion de la confirmation automatique à la configuration de couverture appropriée, comme décrit plus loin dans cette section. Si la confirmation automatique n’est activée pour aucun paramétrage de couverture, ou si la planification est lancée à partir d’une page spécifique, telle que la page **Besoins nets** pour un produit lancé, le processus de confirmation automatique est ignoré.

Les options de regroupement et de marquage pour la confirmation automatique tirent leurs valeurs de l’onglet **Mise à jour standard** sur la page **Paramètres de planification**.

La plage de gestion de la confirmation automatique est définie par le nombre de jours que vous entrez pour la configuration de couverture appropriée. Vous pouvez activer la confirmation automatique et contrôler la plage de gestion de confirmation comme suit :

- Pour définir la plage de gestion de confirmation par défaut pour un groupe de couvertures, accédez à **Planification \> Paramétrage \> Couverture \> Groupes de couvertures**, puis sélectionnez un groupe de couvertures. Puis, dans l’organisateur **Autre**, dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.
- Pour remplacer la plage de temps de confirmation définie pour le groupe de couvertures pour un article spécifique, accédez à **Gestion des informations sur les produits \> Produits lancés**. Dans le volet Actions, sélectionnez **Plan**, puis sélectionnez **Couverture de l’article**. Dans l’onglet **Général**, sélectionnez **Remplacer les plages de gestion**, puis dans le champ **Plage de gestion de confirmation automatique (jours)**, entrez le nombre de jours.
- Pour remplacer la plage de confirmation définie pour le groupe de couvertures et la couverture d’article pour un plan général spécifique, accédez à **Planification \> Paramétrage \> Plans généraux**, puis sélectionnez un plan général. Puis, dans l’organisateur **Plage de gestion en jours**, définissez l’option **Confirmation** sur *Oui*, et saisissez le nombre de jours.

Si vous définissez toutes les plages horaires mentionnées précédemment sur *0* (zéro), la confirmation automatique est effectivement désactivée pour les éléments couverts concernés.

## <a name="firm-planned-orders-by-using-a-query"></a>Commandes prévisionnelles confirmées à l’aide d’une requête

Une confirmation basée une requête vous permet de planifier une confirmation en fonction de critères définis à l’avance. Contrairement à la confirmation automatique, une confirmation basée sur une requête permet de confirmer automatiquement différents sous-ensembles de commandes à différents moments. De plus, vous pouvez utiliser des opérations manuelles ou automatisées pour confirmer différents types de commandes prévisionnelles. Vous pouvez également prévisualiser les commandes confirmées sélectionnées en fonction de vos paramètres. Par conséquent, vous pouvez confirmer que la sélection correspond à vos attentes.

Vous pouvez combiner la confirmation automatique avec celle basée sur une requête. Par exemple, une tâche de confirmation basée sur une requête a une plage de temps plus longue que celle d’une configuration de couverture de confirmation automatique correspondante. Par conséquent, la tâche de confirmation basée sur une requête traitera ses commandes prévisionnelles avant que la confirmation automatique ne soit déclenchée. Vous pouvez profiter de ce comportement pour planifier des commandes pour des fournisseurs spécifiques différemment des commandes pour des produits similaires d’autres fournisseurs.

> [!IMPORTANT]
> Avant que la fonctionnalité décrite dans cette section puisse être utilisée, la fonctionnalité [*Confirmation des commandes prévisionnelles avec filtrage*](#enable-features) doit être activée dans votre système, comme décrit au début de cette rubrique.

Pour confirmer une commande prévisionnelle à l’aide du processus de confirmation basé sur une requête, procédez comme suit :

1. Accédez à **Planification \> Planification \> Exécuter \> Confirmation des commandes prévisionnelles**.
1. Dans la boîte de dialogue **Confirmation des commandes prévisionnelles**, sur le raccourci **Paramètres**, définissez les options de base de traitement, de marquage et de regroupement. Ces options fonctionnent comme elles le font dans la boite de dialogue **Confirmation**. (Voir la section précédente pour les descriptions.) Ensuite, dans la section **Plan**, définissez les champs suivants qui sont propres à la boite de dialogue **Confirmation des commandes prévisionnelles** :

    - **Plan** – Sélectionnez le plan directeur à appliquer lors de la confirmation des commandes prévisionnelles trouvées par cette requête.
    - **Nombre de jours futurs de la plage de gestion de la confirmation** – Sélectionnez la durée dans l’avenir du calcul par la planification des divers besoins et autres éléments.
    - **Nombre de jours passés de la plage de gestion de la confirmation** – Sélectionnez la durée dans le passé du calcul par la planification des divers besoins et autres éléments.

    ![Raccourci Paramètres dans la boîte de dialogue Confirmation des commandes prévisionnelles.](./media/planned-order-firming-main-1.png "Raccourci Paramètres dans la boîte de dialogue Confirmation des commandes prévisionnelles")

1. Pour spécifier les enregistrements à inclure dans la commande, sélectionnez le bouton **Filtre** sur le raccourci **Enregistrements à inclure**. Une boîte de dialogue de requête standard apparaît, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Supply Chain Management. Les champs ici sont en lecture seule et affichent les valeurs liées à votre requête.

    ![Raccourci Enregistrements à inclure dans la boîte de dialogue Confirmation des commandes prévisionnelles.](./media/planned-order-firming-main-2.png "Raccourci Enregistrements à inclure dans la boîte de dialogue Confirmation des commandes prévisionnelles")

1. Sélectionnez **Aperçu** pour prévisualiser le contenu de votre commande confirmée, en fonction de vos paramètres jusqu’à présent. La liste des commandes prévisionnelles qui seront confirmées s’affiche sous forme de message. Vous pouvez ensuite ajuster vos paramètres selon vos besoins jusqu’à ce que l’aperçu affiche la commande confirmée qui vous convient.

    ![Exemple d’aperçu de commande confirmé.](./media/planned-order-firming-preview.png "Exemple d’aperçu de commande confirmé")

    > [!WARNING]
    > Cette fonctionnalité confirmera toutes les commandes prévisionnelles qui correspondent aux critères de filtrage. Une confirmation non critique des commandes prévisionnelles peut entraîner la création d’un grand nombre d’ordres d’achat, de transfert et de fabrication indésirables. Avant de continuer, utilisez toujours le bouton **Aperçu** pour valider les enregistrements qui seront inclus.

1. Sur le raccourci **Exécuter à l’arrière-plan**, configurez le processus pour qu’il s’exécute par lots, et/ou configurez un programme récurrent. Les champs fonctionnent comme pour d’autres types de [travaux d’arrière-plan](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Supply Chain Management.
1. Cliquez sur **OK** pour appliquer vos paramètres et générer des commandes confirmées.

## <a name="track-firmed-orders"></a>Suivre les commandes confirmées

Pour suivre une commande prévisionnelle qui a été confirmée, procédez comme suit :

1. [Ouvrir n’importe quelle page de liste de commandes prévisionnelles](approved-planned-order.md#view-planned-orders).
1. Ouvrez ou sélectionnez la commande prévisionnelle dont vous souhaitez effectuer le suivi.
1. Dans le volet Actions, sous l’onglet **Afficher**, dans le groupe **Vue**, sélectionnez **Confirmation de l’historique**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
