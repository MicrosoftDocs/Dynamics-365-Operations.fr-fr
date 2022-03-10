---
title: Configurer l’intégration de Dataverse
description: Cette rubrique décrit l’intégration entre les applications Microsoft Dataverse et Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4e68142045b72b139bdda8be707a73e21e568fd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065449"
---
# <a name="configure-dataverse-integration"></a>Configurer l’intégration de Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez activer ou désactiver l’intégration entre Microsoft Dataverse et Dynamics 365 Human Resources. Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une table pour aider à résoudre les problèmes de données entre les deux environnements.

> [!NOTE]
> Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

Lorsque vous désactivez l’intégration, les utilisateurs peuvent apporter des modifications à Human Resources ou Dataverse, mais ces modifications ne sont pas synchronisées entre les deux environnements.

Par défaut, l’intégration des données entre Human Resources et Dataverse est désactivée.

Vous souhaiterez peut-être désactiver l’intégration dans ces situations :

- Vous remplissez des données via le Data Management Framework et devez importer les données plusieurs fois pour les avoir dans un état correct.

- Il y a des problèmes avec les données Human Resources ou Dataverse. Si vous désactivez l’intégration, vous pouvez supprimer un enregistrement dans un environnement sans le supprimer dans l’autre. Lorsque vous réactivez l’intégration, l’enregistrement dans l’environnement où il n’a pas été supprimé est synchronisé avec l’environnement où il a été supprimé. La synchronisation commence la prochaine fois que le traitement par lots **Intégration Dataverse en échec, demande de synchronisation** s’exécute.

> [!WARNING]
> Lorsque vous désactivez l’intégration des données, assurez-vous de ne pas modifier le même enregistrement dans les deux environnements. Lorsque vous réactivez l’intégration, l’enregistrement que vous avez modifié en dernier sera synchronisé. Par conséquent, si vous n’avez pas apporté les mêmes modifications à l’enregistrement dans les deux environnements, une perte de données peut se produire.

## <a name="access-the-dataverse-integration-page"></a>Accéder à la page d’intégration de Dataverse

1. Dans l’instance Human Resources où vous souhaitez afficher ou configurer les paramètres d’intégration avec Dataverse, sélectionnez la vignette **Administration du système**.

    [![Vignette Administration du système.](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Sélectionnez l’onglet **Liens**.

    [![Onglet Liens.](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Sous **Intégrations**, sélectionnez **Configuration Dataverse**.

    [![Lien Configuration Dataverse.](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Activer ou désactiver l’intégration des données entre Human Resources et Dataverse

- Pour activer l’intégration, définissez l’option **Activer l’intégration Dataverse** sur **Oui** sur la page **Intégration Microsoft Dataverse**.

    > [!NOTE]
    > Lorsque vous activez l’intégration, les données seront synchronisées la prochaine fois que le traitement par lots **Intégration Dataverse en échec, demande de synchronisation** s’exécute. Toutes les données doivent être disponibles une fois le travail par lots terminé.

- Pour désactiver l’intégration, définissez l’option sur **Non**.

[![Activer ou désactiver l’intégration Dataverse.](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> Il est vivement recommandé de désactiver l’intégration de Dataverse lors de l’exécution des tâches de migration des données. Les chargements de données volumineuses peuvent avoir une incidence significative sur les performances. Par exemple, le chargement de 2 000 collaborateurs peut prendre plusieurs heures lorsque l’intégration est activée et moins d’une heure lorsqu’elle est désactivée. Les chiffres fournis dans cet exemple ne servent qu’à des fins de démonstration. La durée exacte nécessaire pour importer des enregistrements peut varier considérablement en fonction de nombreux facteurs.

## <a name="view-data-integration-details"></a>Afficher les détails de l’intégration de données

Sur le raccourci **Administration** de la page **Intégration Microsoft Dataverse**, vous pouvez voir comment les lignes sont liées entre Human Resources et Dataverse.

- Pour afficher les lignes d’un tableau, sélectionnez le tableau dans le champ **Table Dataverse**. La grille affiche toutes les lignes liées à la table sélectionnée.

> [!NOTE]
> Certaines tables Dataverse ne sont pas actuellement répertoriées. Seules les tables qui prennent en charge l’utilisation de champs personnalisés apparaissent dans la grille. De nouvelles tables seront disponibles grâce dans les prochaines versions de Human Resources.

La grille comprend les champs suivants :

- **Table Dataverse** – Le nom de la table dans Dataverse.
- **Référence de table Dataverse** – L’identifiant qui utilise Dataverse pour identifier un enregistrement. Cette valeur équivaut à la valeur **RecId** dans Human Resources. Vous pouvez trouver l’identifiant lorsque vous ouvrez la table Dataverse dans Microsoft Excel.
- **Nom de l’entité Human Resources** – L’entité Human Resources qui a synchronisé les dernières données avec Dataverse. L’entité peut avoir le préfixe Dataverse ou un autre préfixe.
- **Référence Human Resources** – La valeur **RecId** associée à l’enregistrement dans Human Resources.
- **Supprimé de Dataverse** – Une valeur qui indique si la ligne a été supprimée de Dataverse.

> [!NOTE]
> Les enregistrements dans Human Resources correspondent aux lignes dans Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Supprimer l’association d’un enregistrement dans Human Resources à partir d’une ligne Dataverse

Si vous rencontrez des problèmes lors de la synchronisation des données entre Human Resources et Dataverse, vous pourrez peut-être les résoudre en effaçant le suivi et en laissant la table de suivi se resynchroniser. Si vous supprimez l’association, puis modifiez ou supprimez une ligne dans Dataverse, les modifications ne seront pas synchronisées avec Human Resources. Si vous apportez des modifications à Human Resources, un nouvel enregistrement de suivi est créé et la ligne est mise à jour dans Dataverse.

- Pour supprimer l’association d’un enregistrement Human Resources et une ligne Dataverse, sélectionnez la table dans le champ **Table Dataverse**, puis sélectionnez **Effacer les informations de suivi**.

[![Effacement des informations de suivi.](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Pour exécuter une synchronisation complète sur la table après avoir effacé le suivi, consultez la procédure suivante.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Synchroniser une table entre Human Resources et Dataverse

Utilisez cette procédure lorsque :

- Les modifications depuis Dataverse prennent trop de temps pour apparaître dans Human Resources.

- Vous devez actualiser la table de suivi après avoir effacé le suivi.

Pour exécuter une synchronisation complète sur une table entre Human Resources et Dataverse :

1. Sélectionnez la table dans le champ **Table Dataverse**.

2. Sélectionnez **Synchroniser maintenant**.

[![Exécution d’une synchronisation complète.](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Voir également :

[Tables Dataverse](hr-developer-entities.md)<br>
[Configurer des tables virtuelles Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[FAQ sur les tables virtuelles de Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Mises à jour de la terminologie](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
