---
title: FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cet article donne des réponses aux questions fréquentes relatives à l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
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
ms.openlocfilehash: 79e8c6899d84c3d6147c0a0c2834a7ad2f7b6927
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292052"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams

[!include [banner](includes/banner.md)]

Cet article donne des réponses aux questions fréquentes relatives à l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Qui dans le magasin devient propriétaire d’une équipe lors du provisionnement de Teams à partir de Commerce ? 

Tous les directeurs de magasin sont automatiquement ajoutés en tant que propriétaires du groupe d’équipes correspondant afin qu’ils puissent effectuer des opérations telles que l’ajout d’un canal privé et l’ajout ou la suppression de membres. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Comment attribuer le rôle de « responsable de la communication » à un employé dans Commerce Headquarters ? 

Les responsables de la communication dans Microsoft Teams ont la possibilité de créer et de publier des listes de tâches. Les employés de l’organisation qui doivent devenir responsables de la communication doivent se voir attribuer le rôle de « Gestionnaire des tâches de vente au détail » dans Commerce Headquarters.

Pour attribuer le rôle de gestionnaire des tâches de vente au détail à un employé dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Employés \> Utilisateurs**.
1. Sélectionnez un employé.
1. Dans le raccourci **Rôle de l’utilisateur**, sélectionnez **Affecter des rôles**.
1. Dans la boîte de dialogue **Affecter des rôles à l’utilisateur**, sélectionnez le rôle **Gestionnaire des tâches de vente au détail**, puis sélectionnez **OK**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Comment rendre une hiérarchie d’organisation spécifique disponible pour le chargement dans Microsoft Teams ?

Dans Commerce Headquarters, la hiérarchie de chaque organisation est associée à un ou plusieurs objectifs. Assurez-vous que la hiérarchie que vous souhaitez provisionner dans Microsoft Teams a l’objectif **Génération d’états sur les ventes au détail** qui lui est associé, comme indiqué dans l’exemple suivant. 

![Exemple d’objectif de hiérarchie d’organisation dans Commerce Headquarters.](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Comment autoriser les employés des magasins de vente au détail à se connecter au point de vente Commerce (PDV) à l’aide de Azure Active Directory (Azure AD) ?

Pour plus d’informations sur la configuration de l’expérience de connexion au PDV Commerce pour utiliser l’authentification Azure AD, voir [Autoriser l’authentification Azure Active Directory pour la connexion au PDV ](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Comment mapper les magasins et les équipes correspondantes dans Commerce Headquarters si mon organisation a déjà créé des équipes dans Microsoft Teams ?

Pour plus d’informations sur la façon de mapper les magasins et les équipes s’il existe des équipes préexistantes, voir [Mapper les magasins et les équipes correspondantes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Comment effacer le jeton d’API Microsoft Graph stocké dans le stockage de session ?

Un utilisateur qui s’est connecté au point de vente (PDV) avec un compte Azure Active Directory (Azure AD) doit se déconnecter du PDV ou fermer l’application pour effacer le stockage de session. 

> [!TIP]
> Une bonne pratique recommandée consiste à toujours demander aux employés du magasin de verrouiller le terminal de point de vente ou de se déconnecter de leur session lorsqu’ils n’utilisent pas le terminal. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>Que se passe-t-il si un magasin n’a pas de directeur de magasin ?

Si un magasin n’a pas de directeur, un groupe d’équipes ne sera pas créé pour le magasin ou dans Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>Que se passe-t-il si un directeur de magasin quitte l’entreprise ?

Toute personne ayant le rôle de propriétaire peut ajouter un nouveau directeur de magasin dans Commerce Headquarters et reconfigurer Teams afin que le nouveau responsable dispose des privilèges nécessaires dans Teams pour le groupe. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams](commerce-teams-integration.md)

[Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams](enable-teams-integration.md)

[Configuration de Microsoft Teams à partir de Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gérer les rôles utilisateur dans Microsoft Teams](manage-user-roles-teams.md)

[Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md)
