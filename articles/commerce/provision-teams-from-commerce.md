---
title: Configuration de Microsoft Teams à partir de Dynamics 365 Commerce
description: Cette rubrique décrit comment provisionner Microsoft Teams en utilisant les données organisationnelles de Dynamics 365 Commerce.
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
ms.openlocfilehash: 1cb28fb50bdc972d1dae6d03a45f70a2f3a63357
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022444"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="ff9c9-103">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ff9c9-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff9c9-104">Cette rubrique décrit comment provisionner Microsoft Teams en utilisant les données organisationnelles de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ff9c9-105">Dynamics 365 Commerce offre un moyen simple de provisionner Teams si vous n’avez pas encore configuré d’équipes pour vos magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="ff9c9-106">En tirant parti des informations bien définies de Commerce que vous souhaitez utiliser dans Teams, vous pouvez aider les employés de votre magasin à se familiariser avec Teams.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="ff9c9-107">Ces informations comprennent la hiérarchie organisationnelle, le nom des magasins, les informations sur les employés et les comptes Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ff9c9-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="ff9c9-108">Le processus de configuration de Teams comporte deux étapes principales :</span><span class="sxs-lookup"><span data-stu-id="ff9c9-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="ff9c9-109">Dans Teams, créez une équipe pour chaque magasin de vente au détail et ajoutez des employés de magasin en tant que membres de l’équipe appropriée.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="ff9c9-110">Si un employé est associé à plusieurs magasins de détail, son appartenance d’équipe reflétera ce fait.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="ff9c9-111">Une équipe de communication comprenant des membres directeurs régionaux sera créée pour faciliter la publication des tâches à partir de Teams.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="ff9c9-112">Chargez votre hiérarchie organisationnelle de Commerce vers Teams.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="ff9c9-113">Configuration de Teams dans Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="ff9c9-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="ff9c9-114">Avant de configurer Microsoft Teams, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff9c9-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="ff9c9-115">Confirmez que tous les directeurs régionaux ont été nommés responsables des communications.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="ff9c9-116">Confirmez que le compte Azure de chaque responsable et employé de magasin a été associé à l’enregistrement d’employé de ce responsable ou de cet employé dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="ff9c9-117">Pour configurer Teams dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="ff9c9-118">Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="ff9c9-119">Dans le volet Actions, sélectionnez **Configurer Teams**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="ff9c9-120">Un traitement par lots nommé **Configuration de Teams** est créé.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="ff9c9-121">Accédez à **Administration système \> Recherches \> Traitements par lots** et recherchez le travail le plus récent ayant la description **Configuration de Teams**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="ff9c9-122">Attendez que ce travail soit terminé.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="ff9c9-123">Si aucun de vos directeurs régionaux, directeurs de magasin et employés de magasin n’a été associé à une licence Teams, le message d’erreur suivant peut s’afficher : « Impossible de récupérer les catégories de SKU applicables pour l’utilisateur ».</span><span class="sxs-lookup"><span data-stu-id="ff9c9-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="ff9c9-124">Pour corriger le problème, sélectionnez **Synchroniser les équipes et les membres** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="ff9c9-125">Valider la configuration de Teams dans le centre d’administration de Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="ff9c9-126">Pour valider la configuration de Microsoft Teams dans le centre d’administration de Microsoft Teams, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="ff9c9-127">Accédez au [Centre d’administration de Teams](https://admin.teams.microsoft.com/) et connectez-vous en tant qu’administrateur de votre locataire de e-commerce.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="ff9c9-128">Dans le volet de navigation de gauche, sélectionnez **Teams** pour le développer, puis sélectionnez **Gérer les équipes**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="ff9c9-129">Confirmez qu’une équipe a été créée pour chaque magasin de détail Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="ff9c9-130">Sélectionnez une équipe et confirmez que les employés du magasin y ont été ajoutés en tant que membres.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="ff9c9-131">Dans le volet de navigation de gauche, sélectionnez **Utilisateurs** et confirmez que tous les employés de tous les magasins ont été ajoutés en tant qu’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="ff9c9-132">L’illustration suivante montre un exemple de la page **Gérer les équipes** dans le centre d’administration de Teams.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Exemple de la page Gérer les équipes dans le centre d’administration de Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="ff9c9-134">Charger une hiérarchie organisationnelle de Commerce vers Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="ff9c9-135">La hiérarchie organisationnelle de Commerce peut être utilisée dans Microsoft Teams pour publier des tâches à destination de certains ou de tous les magasins qui utilisent la même structure hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="ff9c9-136">Pour charger une hiérarchie organisationnelle Commerce vers Teams, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="ff9c9-137">Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration de canal \> Configuration de l’intégration Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="ff9c9-138">Sélectionnez **Télécharger la hiérarchie de ciblage**, puis sélectionnez **Magasins de vente au détail par région** pour télécharger un fichier de valeurs séparées par des virgules (CSV) de la hiérarchie organisationnelle.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="ff9c9-139">Installez le module Microsoft Teams Powershell en suivant les étapes de [Installer Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="ff9c9-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="ff9c9-140">Lorsque vous êtes invité dans la fenêtre Teams PowerShell, connectez-vous à l’aide du compte administrateur de votre locataire Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="ff9c9-141">Suivez les étapes de [Configurer la hiérarchie de ciblage de votre équipe](/microsoftteams/set-up-your-team-hierarchy) pour charger le fichier CSV pour la hiérarchie de ciblage.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-141">Follow the steps in [Set up your team targeting hierarchy](/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="ff9c9-142">Vérifiez que la hiérarchie organisationnelle a été chargée vers Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="ff9c9-143">Pour vérifier que la hiérarchie organisationnelle a été chargée vers Microsoft Teams, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="ff9c9-144">Connectez-vous à Teams en tant que responsable de la communication.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="ff9c9-145">Dans le volet de navigation de gauche, sélectionnez **Tâches du planificateur**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="ff9c9-146">Sur l’onglet **Listes publiées**, créez une nouvelle liste contenant une tâche factice.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="ff9c9-147">Sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-147">Select **Publish**.</span></span> <span data-ttu-id="ff9c9-148">La hiérarchie organisationnelle doit apparaître dans la boîte de dialogue **Sélectionner les destinataires de la publication**, comme indiqué dans l’exemple de l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="ff9c9-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Exemple de hiérarchie organisationnelle dans la boîte de dialogue Sélectionner les destinataires de la publication](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="ff9c9-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ff9c9-150">Additional resources</span></span>

[<span data-ttu-id="ff9c9-151">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="ff9c9-152">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="ff9c9-153">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ff9c9-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="ff9c9-154">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="ff9c9-155">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="ff9c9-156">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ff9c9-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)