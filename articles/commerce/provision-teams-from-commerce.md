---
title: Configuration de Microsoft Teams à partir de Dynamics 365 Commerce
description: Cet article décrit comment provisionner Microsoft Teams en utilisant les données organisationnelles de Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3dc9d0f20ec251f0908dda0017adaaeac1b43856
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868933"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Configuration de Microsoft Teams à partir de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cet article décrit comment provisionner Microsoft Teams en utilisant les données organisationnelles de Dynamics 365 Commerce.

Dynamics 365 Commerce offre un moyen simple de provisionner Teams si vous n’avez pas encore configuré d’équipes pour vos magasins de vente au détail. En tirant parti des informations bien définies de Commerce que vous souhaitez utiliser dans Teams, vous pouvez aider les employés de votre magasin à se familiariser avec Teams. Ces informations comprennent la hiérarchie organisationnelle, le nom des magasins, les informations sur les employés et les comptes Azure Active Directory (Azure AD). 

Le processus de configuration de Teams comporte deux étapes principales :

1. Dans Teams, créez une équipe pour chaque magasin de vente au détail et ajoutez des employés de magasin en tant que membres de l’équipe appropriée. Si un employé est associé à plusieurs magasins de détail, son appartenance d’équipe reflétera ce fait. Une équipe de communication comprenant des membres directeurs régionaux sera créée pour faciliter la publication des tâches à partir de Teams.
1. Chargez votre hiérarchie organisationnelle de Commerce vers Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Configuration de Teams dans Commerce Headquarters

Avant de configurer Microsoft Teams, effectuez les tâches suivantes :

- Confirmez que tous les directeurs régionaux ont été nommés responsables des communications.
- Confirmez que le compte Azure de chaque responsable et employé de magasin a été associé à l’enregistrement d’employé de ce responsable ou de cet employé dans Commerce Headquarters.

Pour configurer Teams dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.
1. Dans le volet Actions, sélectionnez **Configurer Teams**. Un traitement par lots nommé **Configuration de Teams** est créé.
1. Accédez à **Administration système \> Recherches \> Traitements par lots** et recherchez le travail le plus récent ayant la description **Configuration de Teams**. Attendez que ce travail soit terminé.

> [!TIP]
> Si aucun de vos directeurs régionaux, directeurs de magasin et employés de magasin n’a été associé à une licence Teams, le message d’erreur suivant peut s’afficher : « Impossible de récupérer les catégories de SKU applicables pour l’utilisateur ». Pour corriger le problème, sélectionnez **Synchroniser les équipes et les membres** dans le volet Actions.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Valider la configuration de Teams dans le centre d’administration de Teams

Pour valider la configuration de Microsoft Teams dans le centre d’administration de Microsoft Teams, procédez comme suit.
    
1. Accédez au [Centre d’administration de Teams](https://admin.teams.microsoft.com/) et connectez-vous en tant qu’administrateur de votre locataire de e-commerce.
1. Dans le volet de navigation de gauche, sélectionnez **Teams** pour le développer, puis sélectionnez **Gérer les équipes**.
1. Confirmez qu’une équipe a été créée pour chaque magasin de détail Commerce.
1. Sélectionnez une équipe et confirmez que les employés du magasin y ont été ajoutés en tant que membres.
1. Dans le volet de navigation de gauche, sélectionnez **Utilisateurs** et confirmez que tous les employés de tous les magasins ont été ajoutés en tant qu’utilisateurs.

L’illustration suivante montre un exemple de la page **Gérer les équipes** dans le centre d’administration de Teams.

![Exemple de la page Gérer les équipes dans le centre d’administration de Teams.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Charger une hiérarchie organisationnelle de Commerce vers Teams
    
La hiérarchie organisationnelle de Commerce peut être utilisée dans Microsoft Teams pour publier des tâches à destination de certains ou de tous les magasins qui utilisent la même structure hiérarchique.

Pour charger une hiérarchie organisationnelle Commerce vers Teams, procédez comme suit.
    
1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration de canal \> Configuration de l’intégration Microsoft Teams**.
1. Sélectionnez **Télécharger la hiérarchie de ciblage**, puis sélectionnez **Magasins de vente au détail par région** pour télécharger un fichier de valeurs séparées par des virgules (CSV) de la hiérarchie organisationnelle.
1. Installez le module Microsoft Teams Powershell en suivant les étapes de [Installer Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).
1. Lorsque vous êtes invité dans la fenêtre Teams PowerShell, connectez-vous à l’aide du compte administrateur de votre locataire Azure AD.
1. Suivez les étapes de [Configurer la hiérarchie de ciblage de votre équipe](/microsoftteams/set-up-your-team-hierarchy) pour charger le fichier CSV pour la hiérarchie de ciblage.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Vérifiez que la hiérarchie organisationnelle a été chargée vers Teams

Pour vérifier que la hiérarchie organisationnelle a été chargée vers Microsoft Teams, procédez comme suit.

1. Connectez-vous à Teams en tant que responsable de la communication.
1. Dans le volet de navigation de gauche, sélectionnez **Tâches du planificateur**.
1. Sur l’onglet **Listes publiées**, créez une nouvelle liste contenant une tâche factice.
1. Sélectionnez **Publier**. La hiérarchie organisationnelle doit apparaître dans la boîte de dialogue **Sélectionner les destinataires de la publication**, comme indiqué dans l’exemple de l’illustration suivante.

![Exemple de hiérarchie organisationnelle dans la boîte de dialogue Sélectionner les destinataires de la publication.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md)

[FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams](teams-integration-faq.md)