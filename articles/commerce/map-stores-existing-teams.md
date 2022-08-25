---
title: Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams
description: Cet article explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 67a1a79dd74d411aa7e21000c8baaa8a069cede7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279117"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams

[!include [banner](includes/banner.md)]

Cet article explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.

Votre organisation peut avoir créé des équipes pour certains de vos magasins ou tous vos magasins avant l’intégration de Dynamics 365 Commerce et Microsoft Teams. Si tel est le cas, pour établir la synchronisation des tâches entre les PDV Commerce et Microsoft Teams, vous devez fournir le mappage des magasins et des équipes correspondantes dans Commerce Headquarters.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mapper les magasins et les équipes correspondantes dans Commerce Headquarters 

Pour mapper les magasins et les équipes correspondantes dans Commerce Headquarters, suivez ces étapes.

1. Accédez à **Administration système \> Espace de travail \> Gestion des données**.
1. Sélectionnez **Exporter**. 
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sous **Nom de groupe**, entrez « Exporter le mappage des équipes ».
1. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter une entité**. La boîte de dialogue **Ajouter une entité** apparaît.  
1. Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage d'équipes entre source et équipe**.
1. Dans la liste déroulante **Format de données cible**, sélectionnez **CSV**.
1. Sélectionnez **Ajouter**, puis sélectionnez **Fermer**.
1. En haut à gauche sous le volet Action, sélectionnez **Exporter maintenant**.
1. Sous **Statut de traitement d’entité**, sélectionnez **Télécharger un fichier**.
1. Dans le fichier CSV exporté, entrez des valeurs pour **SOURCETYPE**, **SOURCEID** et **TEAMID**, comme suit :
    - Pour **SOURCETYPE**, entrez « RetailStore ». 
    - Pour **SOURCEID**, entrez le numéro de magasin (par exemple, « 000135 » pour le magasin de San Francisco). Vous pouvez trouver les numéros de magasins sur **Commerce et détail \> Canaux \> Magasins**.
    - Pour **TEAMID**, entrez l’ID d’équipe correspondant à partir de Microsoft Teams (par exemple, « 5f8bc92b-6aa8-451e-85d1-3949c01ddc6c »). Vous pouvez trouver des informations sur l’ID d’équipe sur [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Enregistrez le fichier CSV sur votre ordinateur local.
1. Accédez à **Administration système \> Espace de travail \> Gestion des données**, puis sélectionnez **Importer**.
1. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**. La boîte de dialogue **Ajouter un fichier** apparaît.
1. Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage d'équipes entre source et équipe**.
1. Dans la liste déroulante **Format de données source**, sélectionnez **CSV**.
1. Sélectionnez **Charger et ajouter**, sélectionnez le fichier CSV que vous avez enregistré précédemment, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Ajouter un fichier**, sélectionnez **Fermer**.
1. Sur le volet Action, sélectionnez **Enregistrer**, puis sélectionnez **Importer**.

L’image d’exemple suivante montre le groupe **Exporter le mappage des équipes** dans Commerce avec les éléments **Ajouter une entité** et les en-têtes du fichier CSV exporté mis en surbrillance.

![Exporter le groupe de mappage des équipes dans Commerce avec les éléments ajouter une entité et les en-têtes du fichier CSV exporté mis en surbrillance.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Après avoir terminé les étapes précédentes, suivez les étapes dans [Synchroniser la gestion des tâches entre Microsoft Teams et les PDV](synchronize-tasks-teams-pos.md) pour synchroniser la gestion des tâches. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)
