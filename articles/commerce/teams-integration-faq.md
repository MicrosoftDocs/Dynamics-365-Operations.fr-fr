---
title: FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cette rubrique donne des réponses aux questions fréquentes relatives à l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3fc7cff0a3f8d0fbfb196ec5951b138088afece7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019468"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="80a94-103">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a94-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80a94-104">Cette rubrique donne des réponses aux questions fréquentes relatives à l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="80a94-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="80a94-105">Qui dans le magasin devient propriétaire d’une équipe lors du provisionnement de Teams à partir de Commerce ?</span><span class="sxs-lookup"><span data-stu-id="80a94-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="80a94-106">Tous les directeurs de magasin sont automatiquement ajoutés en tant que propriétaires du groupe d’équipes correspondant afin qu’ils puissent effectuer des opérations telles que l’ajout d’un canal privé et l’ajout ou la suppression de membres.</span><span class="sxs-lookup"><span data-stu-id="80a94-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="80a94-107">Comment attribuer le rôle de « responsable de la communication » à un employé dans Commerce Headquarters ?</span><span class="sxs-lookup"><span data-stu-id="80a94-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="80a94-108">Les responsables de la communication dans Microsoft Teams ont la possibilité de créer et de publier des listes de tâches.</span><span class="sxs-lookup"><span data-stu-id="80a94-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="80a94-109">Les employés de l’organisation qui doivent devenir responsables de la communication doivent se voir attribuer le rôle de « Gestionnaire des tâches de vente au détail » dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="80a94-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="80a94-110">Pour attribuer le rôle de gestionnaire des tâches de vente au détail à un employé dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="80a94-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="80a94-111">Accédez à **Commerce et vente au détail \> Employés \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="80a94-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="80a94-112">Sélectionnez un employé.</span><span class="sxs-lookup"><span data-stu-id="80a94-112">Select an employee.</span></span>
1. <span data-ttu-id="80a94-113">Dans le raccourci **Rôle de l’utilisateur**, sélectionnez **Affecter des rôles**.</span><span class="sxs-lookup"><span data-stu-id="80a94-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="80a94-114">Dans la boîte de dialogue **Affecter des rôles à l’utilisateur**, sélectionnez le rôle **Gestionnaire des tâches de vente au détail**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="80a94-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="80a94-115">Comment rendre une hiérarchie d’organisation spécifique disponible pour le chargement dans Microsoft Teams ?</span><span class="sxs-lookup"><span data-stu-id="80a94-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="80a94-116">Dans Commerce Headquarters, la hiérarchie de chaque organisation est associée à un ou plusieurs objectifs.</span><span class="sxs-lookup"><span data-stu-id="80a94-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="80a94-117">Assurez-vous que la hiérarchie que vous souhaitez provisionner dans Microsoft Teams a l’objectif **Génération d’états sur les ventes au détail** qui lui est associé, comme indiqué dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="80a94-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Exemple d’objectif de hiérarchie d’organisation dans Commerce Headquarters](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="80a94-119">Comment autoriser les employés des magasins de vente au détail à se connecter au point de vente Commerce (PDV) à l’aide de Azure Active Directory (Azure AD) ?</span><span class="sxs-lookup"><span data-stu-id="80a94-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="80a94-120">Pour plus d’informations sur la configuration de l’expérience de connexion au PDV Commerce pour utiliser l’authentification Azure AD, voir [Autoriser l’authentification Azure Active Directory pour la connexion au PDV ](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="80a94-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="80a94-121">Comment mapper les magasins et les équipes correspondantes dans Commerce Headquarters si mon organisation a déjà créé des équipes dans Microsoft Teams ?</span><span class="sxs-lookup"><span data-stu-id="80a94-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="80a94-122">Pour plus d’informations sur la façon de mapper les magasins et les équipes s’il existe des équipes préexistantes, voir [Mapper les magasins et les équipes correspondantes si votre organisation a des équipes préexistantes dans Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="80a94-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="80a94-123">Comment effacer le jeton d’API Microsoft Graph stocké dans le stockage de session ?</span><span class="sxs-lookup"><span data-stu-id="80a94-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="80a94-124">Un utilisateur qui s’est connecté au point de vente (PDV) avec un compte Azure Active Directory (Azure AD) doit se déconnecter du PDV ou fermer l’application pour effacer le stockage de session.</span><span class="sxs-lookup"><span data-stu-id="80a94-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="80a94-125">Une bonne pratique recommandée consiste à toujours demander aux employés du magasin de verrouiller le terminal de point de vente ou de se déconnecter de leur session lorsqu’ils n’utilisent pas le terminal.</span><span class="sxs-lookup"><span data-stu-id="80a94-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="80a94-126">Que se passe-t-il si un magasin n’a pas de directeur de magasin ?</span><span class="sxs-lookup"><span data-stu-id="80a94-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="80a94-127">Si un magasin n’a pas de directeur, un groupe d’équipes ne sera pas créé pour le magasin ou dans Teams.</span><span class="sxs-lookup"><span data-stu-id="80a94-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="80a94-128">Que se passe-t-il si un directeur de magasin quitte l’entreprise ?</span><span class="sxs-lookup"><span data-stu-id="80a94-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="80a94-129">Toute personne ayant le rôle de propriétaire peut ajouter un nouveau directeur de magasin dans Commerce Headquarters et reconfigurer Teams afin que le nouveau responsable dispose des privilèges nécessaires dans Teams pour le groupe.</span><span class="sxs-lookup"><span data-stu-id="80a94-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="80a94-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="80a94-130">Additional resources</span></span>

[<span data-ttu-id="80a94-131">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a94-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="80a94-132">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a94-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="80a94-133">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="80a94-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="80a94-134">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="80a94-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="80a94-135">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a94-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="80a94-136">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80a94-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
