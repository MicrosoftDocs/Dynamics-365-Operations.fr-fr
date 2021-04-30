---
title: Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams
description: Cette rubrique explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5a711c1057b87bd792755ef91a84d1c28879c590
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908493"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams

[!include [banner](includes/banner.md)]

Cette rubrique explique comment mapper les magasins et les équipes correspondantes dans Dynamics 365 Commerce Headquarters si votre organisation a déjà créé des équipes dans Microsoft Teams avant l’intégration de Commerce.

Votre organisation peut avoir créé des équipes pour certains magasins ou tous avant l’intégration de Dynamics 365 Commerce et Microsoft Teams. Si tel est le cas, pour établir la synchronisation des tâches entre les PDV Commerce et Microsoft Teams, vous devez fournir le mappage des magasins et des équipes correspondantes dans Commerce Headquarters.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mapper les magasins et les équipes correspondantes dans Commerce Headquarters 

Pour mapper les magasins et les équipes correspondantes dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Administration système \> Espace de travail \> Gestion des données**.
1. Sélectionnez **Exporter**. 
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Sous **Nom de groupe**, entrez « Exporter le mappage des équipes ».
1. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter une entité**. La boîte de dialogue **Ajouter une entité** apparaît.  
1. Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage Teams entre la source et les équipes**.
1. Dans la liste déroulante **Format de données cible**, sélectionnez **CSV**.
1. Sélectionnez **Ajouter**, puis sélectionnez **Fermer**.
1. En haut à gauche sous le volet Actions, sélectionnez **Exporter maintenant**.
1. Sous **Statut de traitement de l’entité**, sélectionnez **Télécharger un fichier**.
1. Dans le fichier CSV exporté, saisissez des valeurs pour **SOURCETYPE**, **SOURCEID** et **TEAMID**, comme suit :
    - Pour **SOURCETYPE**, saisissez « RetailStore ». 
    - Pour **SOURCEID**, entrez le numéro de magasin (par exemple, « 000135 » pour le magasin de San Francisco). Vous pouvez trouver les numéros de magasins dans **Retail et Commerce \> Canaux \> Magasins**.
    - Pour **TEAMID**, saisissez l’ID d’équipe correspondant à partir de Microsoft Teams (par exemple, « 5f8bc92b-6aa8-451e-85d1-3949c01ddc6c »). Vous pouvez trouver des informations sur l’ID d’équipe sur [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Enregistrez le fichier CSV sur votre ordinateur local.
1. Accédez à **Administration système \> Espace de travail \> Gestion des données**, puis sélectionnez **Importer**.
1. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**. La boîte de dialogue **Ajouter un fichier** apparaît.
1. Dans la liste déroulante **Nom de l’entité**, sélectionnez **Mappage Teams entre la source et les équipes**.
1. Dans la liste déroulante **Format de données source**, sélectionnez **CSV**.
1. Sélectionnez **Charger et ajouter**, sélectionnez le fichier CSV que vous avez enregistré précédemment, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Ajouter un fichier**, sélectionnez **Fermer**.
1. Sur le volet Actions, sélectionnez **Enregistrer**, puis sélectionnez **Importer**.

L’image d’exemple suivante montre le groupe **Exporter le mappage des équipes** dans Commerce avec les éléments **Ajouter une entité** et les en-têtes du fichier CSV exporté mis en surbrillance.

![Exporter le mappage des équipes dans Commerce avec les éléments Ajouter une entité et les en-têtes du fichier CSV exporté mis en surbrillance](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Après avoir terminé les étapes précédentes, suivez les étapes de la rubrique [Synchroniser la gestion des tâches entre Microsoft Teams et les PDV](synchronize-tasks-teams-pos.md) pour synchroniser la gestion des tâches. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)
