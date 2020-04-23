---
title: Configurer l'intégration Common Data Service
description: Vous pouvez activer ou désactiver l'intégration entre Common Data Service et Dynamics 365 Human Resources. Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une entité pour aider à résoudre les problèmes de données entre les deux environnements.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 04280aa0908ed6dab86ef87b6c1843e4b4348e08
ms.sourcegitcommit: c9657b44adb9c1a77c7c2f6ab63a58cc848974ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198420"
---
# <a name="configure-common-data-service-integration"></a>Configurer l'intégration Common Data Service

Vous pouvez activer ou désactiver l'intégration entre Common Data Service et Dynamics 365 Human Resources. Vous pouvez également afficher les détails de la synchronisation, effacer les données de suivi et resynchroniser une entité pour aider à résoudre les problèmes de données entre les deux environnements.

Lorsque vous désactivez l'intégration, les utilisateurs peuvent apporter des modifications à Human Resources ou Common Data Service, mais ces modifications ne sont pas synchronisées entre les deux environnements.

Par défaut, l'intégration des données entre Human Resources et Common Data Service est désactivée.

Vous souhaiterez peut-être désactiver l'intégration dans ces situations :

- Vous remplissez des données via le Data Management Framework et devez importer les données plusieurs fois pour les avoir dans un état correct.

- Il y a des problèmes avec les données Human Resources ou Common Data Service. Si vous désactivez l'intégration, vous pouvez supprimer un enregistrement dans un environnement sans le supprimer dans l'autre. Lorsque vous réactivez l'intégration, l'enregistrement dans l'environnement où il n'a pas été supprimé est synchronisé avec l'environnement où il a été supprimé. La synchronisation commence la prochaine fois que le traitement par lots **Intégration Common Data Service en échec, demande de synchronisation** s'exécute.

> [!WARNING]
> Lorsque vous désactivez l'intégration des données, assurez-vous de ne pas modifier le même enregistrement dans les deux environnements. Lorsque vous réactivez l'intégration, l'enregistrement que vous avez modifié en dernier sera synchronisé. Par conséquent, si vous n'avez pas apporté les mêmes modifications à l'enregistrement dans les deux environnements, une perte de données peut se produire.

## <a name="access-the-common-data-service-integration-page"></a>Accéder à la page d'intégration de Common Data Service

1. Dans l'instance Human Resources où vous souhaitez afficher ou configurer les paramètres d'intégration avec Common Data Service, sélectionnez la vignette **Administration du système**.

    [![Vignette Administration du système](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Sélectionnez l'onglet **Liens**.

    [![Onglet Liens](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Sous **Intégrations**, sélectionnez **Configuration Common Data Service**.

    [![Lien Configuration Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Activer ou désactiver l'intégration des données entre Human Resources et Common Data Service

- Pour activer l'intégration, définissez l'option **Activer l'intégration à Common Data Service** sur **Oui**.

    > [!NOTE]
    > Lorsque vous activez l'intégration, les données seront synchronisées la prochaine fois que le traitement par lots **Intégration Common Data Service en échec, demande de synchronisation** s'exécute. Toutes les données doivent être disponibles une fois le travail par lots terminé.

- Pour désactiver l'intégration, définissez l'option sur **Non**.

[![Activer ou désactiver l'intégration Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

## <a name="view-data-integration-details"></a>Afficher les détails de l'intégration de données

Sur l'organisateur **Administration** de la page **Intégration Common Data Service**, vous pouvez voir comment les enregistrements sont liés entre Human Resources et Common Data Service.

- Pour afficher les enregistrements d'une entité, sélectionnez l'entité dans le champ **Nom d'entité CDS**. La grille affiche tous les enregistrements liés à l'entité sélectionnée.

[![Affichage des enregistrements d'une entité](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> Certaines entités Common Data Service ne sont pas actuellement répertoriées. Seules les entités qui prennent en charge l'utilisation de champs personnalisés apparaissent dans la grille. De nouvelles entités seront disponibles grâce dans les prochaines versions de Human Resources.

La grille comprend les champs suivants :

- **Nom de l'entité CDS** – Le nom de l'entité dans Common Data Service.
- **Référence d'entité CDS** - L'identifiant qui utilise Common Data Service pour identifier un enregistrement. Cette valeur équivaut à la valeur **RecId** dans Human Resources. Vous pouvez trouver l'identifiant lorsque vous ouvrez l'entité Common Data Service dans Microsoft Excel.
- **Nom de l'entité Human Resources** - L'entité qui a synchronisé les dernières données avec Common Data Service. L'entité peut avoir le préfixe Common Data Service ou un autre préfixe.
- **Référence Human Resources** - La valeur **RecId** associée à l'enregistrement dans Human Resources.
- **A été supprimé de CDS** - Une valeur qui indique si l'enregistrement a été supprimé de Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Supprimer l'association d'un enregistrement dans Human Resources depuis Common Data Service

Si vous rencontrez des problèmes lors de la synchronisation des données entre Human Resources et Common Data Service, vous pourrez peut-être les résoudre en effaçant le suivi et en laissant la table de suivi se resynchroniser. Si vous supprimez l'association, puis modifiez ou supprimez un enregistrement dans Common Data Service, les modifications ne seront pas synchronisées avec Human Resources. Si vous apportez des modifications à Human Resources, un nouvel enregistrement de suivi est créé et l'enregistrement est mis à jour dans Common Data Service.

- Pour supprimer l'association d'un enregistrement entre Human Resources et Common Data Service, sélectionnez l'entité dans le champ **Nom d'entité CDS**, puis sélectionnez **Effacer les informations de suivi**.

[![Effacement des informations de suivi](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Pour exécuter une synchronisation complète sur l'entité après avoir effacé le suivi, consultez la procédure suivante.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Synchroniser une entité entre Human Resources et Common Data Service

Utilisez cette procédure lorsque :

- Les modifications depuis Common Data Service prennent trop de temps pour apparaître dans Human Resources.

- Vous devez actualiser la table de suivi après avoir effacé le suivi.

Pour exécuter une synchronisation complète sur une entité entre Human Resources et Common Data Service :

1. Sélectionnez l'entité dans le champ **Nom de l'entité CDS**.

2. Sélectionnez **Synchroniser maintenant**.

[![Exécution d'une synchronisation complète](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


