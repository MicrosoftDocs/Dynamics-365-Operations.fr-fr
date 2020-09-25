---
title: Espace de travail mobile Contrôle des coûts
description: Cette rubrique fournit des informations sur l’espace de travail mobile Contrôle des coûts. Cet espace de travail permet aux responsables de centre de coût d’afficher des informations sur les performances du centre de coût à tout moment et n’importe où.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 22acdcfbecc1efe78a1b1be87e40b2e7d23506fc
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759446"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="d288d-104">Espace de travail mobile Contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="d288d-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d288d-105">Cette rubrique fournit des informations sur l’espace de travail mobile **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="d288d-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="d288d-106">Cet espace de travail permet aux responsables de centre de coût d’afficher des informations sur les performances du centre de coût à tout moment et n’importe où.</span><span class="sxs-lookup"><span data-stu-id="d288d-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="d288d-107">Cet espace de travail mobile est destiné à être utilisé avec l’application mobile Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d288d-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="d288d-108">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="d288d-108">Overview</span></span>
<span data-ttu-id="d288d-109">L’espace de travail mobile **Contrôle des coûts** fournit une vue instantanée des performances actuelles des centres de coût en comparant les coûts réels aux coûts budgétés.</span><span class="sxs-lookup"><span data-stu-id="d288d-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="d288d-110">Vous pouvez accéder au statut des éléments de coût individuels.</span><span class="sxs-lookup"><span data-stu-id="d288d-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="d288d-111">Par exemple, un employé reçoit une invitation à une conférence internationale, mais l’organisation doit couvrir toutes les dépenses de déplacement.</span><span class="sxs-lookup"><span data-stu-id="d288d-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="d288d-112">L’employé demande à son responsable s’il peut assister à la conférence.</span><span class="sxs-lookup"><span data-stu-id="d288d-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="d288d-113">Le responsable ouvre rapidement l’espace de travail **Contrôle des coûts** sur son téléphone portable de voir s’il dispose du budget nécessaire.</span><span class="sxs-lookup"><span data-stu-id="d288d-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="d288d-114">Sécurité des données</span><span class="sxs-lookup"><span data-stu-id="d288d-114">Data security</span></span>
<span data-ttu-id="d288d-115">Les données de l’espace de travail **Contrôle des coûts** sont sécurisées par les informations d’identification de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d288d-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="d288d-116">Les responsables de centre de coût sont uniquement autorisés à consulter les données de leur propre centre de coût.</span><span class="sxs-lookup"><span data-stu-id="d288d-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="d288d-117">La sécurité au niveau de l’accès est gérée dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="d288d-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="d288d-118">Les contrôleurs de gestion définissent la configuration de l’espace de travail mobile **Contrôle des coûts** dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="d288d-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="d288d-119">Une fois que l’espace de travail est publié sur l’application mobile, il est disponible dans l’application mobile.</span><span class="sxs-lookup"><span data-stu-id="d288d-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="d288d-120">Par conséquent, tous les responsables de centre de coût de l’organisation peuvent consultent les données au même format.</span><span class="sxs-lookup"><span data-stu-id="d288d-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="d288d-121">Actions, vues et liens</span><span class="sxs-lookup"><span data-stu-id="d288d-121">Actions, views, and links</span></span>
<span data-ttu-id="d288d-122">L’espace de travail mobile **Contrôle des coûts** fournit les actions, les vues et les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="d288d-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="d288d-123">**Actions :**</span><span class="sxs-lookup"><span data-stu-id="d288d-123">**Actions:**</span></span>

    -   <span data-ttu-id="d288d-124">Utilisez **Sélectionner une configuration** pour sélectionner une mise en page.</span><span class="sxs-lookup"><span data-stu-id="d288d-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="d288d-125">Utilisez **Sélectionner un objet de coût** pour sélectionner les centres de coût et filtrer les données en fonction.</span><span class="sxs-lookup"><span data-stu-id="d288d-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="d288d-126">Les centres de coût qui figurent dans la liste dépendent de l’accès qui est accordé dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="d288d-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="d288d-127">**Vues :** selon la sélection des actions et la configuration du module **Contrôle de gestion**, vous pouvez afficher les informations suivantes dans les cartes :</span><span class="sxs-lookup"><span data-stu-id="d288d-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="d288d-128">Comparatif Réel/Budget (période actuelle)</span><span class="sxs-lookup"><span data-stu-id="d288d-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="d288d-129">Comparatif Réel/Budget révisé (période actuelle)</span><span class="sxs-lookup"><span data-stu-id="d288d-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="d288d-130">Réel/Budget (période précédente)</span><span class="sxs-lookup"><span data-stu-id="d288d-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="d288d-131">Réel/Budget révisé (période précédente)</span><span class="sxs-lookup"><span data-stu-id="d288d-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="d288d-132">Réel/Budget (année en cours)</span><span class="sxs-lookup"><span data-stu-id="d288d-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="d288d-133">Réel/Budget révisé (année en cours)</span><span class="sxs-lookup"><span data-stu-id="d288d-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="d288d-134">Les montants suivants sont affichés dans chaque carte : Réel, Budget, Écart, et Écart en %.</span><span class="sxs-lookup"><span data-stu-id="d288d-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="d288d-135">**Liens :**</span><span class="sxs-lookup"><span data-stu-id="d288d-135">**Links:**</span></span>

    -   <span data-ttu-id="d288d-136">Détails pour la période actuelle</span><span class="sxs-lookup"><span data-stu-id="d288d-136">Details for current period</span></span>
    -   <span data-ttu-id="d288d-137">Détails pour la période précédente</span><span class="sxs-lookup"><span data-stu-id="d288d-137">Details for previous period</span></span>
    -   <span data-ttu-id="d288d-138">Détails pour l’année en cours</span><span class="sxs-lookup"><span data-stu-id="d288d-138">Details for year to date</span></span>

    <span data-ttu-id="d288d-139">Lorsque vous sélectionnez un lien, une carte est affichée pour chaque élément de coût.</span><span class="sxs-lookup"><span data-stu-id="d288d-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="d288d-140">Les montants suivants sont affichés sur chaque carte : réel, budget, écart budgétaire, écart budgétaire en %, budget révisé, écart budgétaire révisé et écart budgétaire révisé en %.</span><span class="sxs-lookup"><span data-stu-id="d288d-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="d288d-141">[![Carte pour un élément de coût ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="d288d-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d288d-142">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d288d-142">Prerequisites</span></span>
<span data-ttu-id="d288d-143">Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d288d-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a><span data-ttu-id="d288d-144">Conditions requises si vous utilisez Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="d288d-144">Prerequisites if you use Microsoft Dynamics 365 Finance</span></span>
<span data-ttu-id="d288d-145">Si Finance a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="d288d-145">If Finance has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="d288d-146">Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="d288d-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="d288d-147">Conditions requises si vous utilisez la version 1611 avec Platform Update 3 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="d288d-147">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="d288d-148">Si la version 1611 avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="d288d-148">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d288d-149">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="d288d-149">Prerequisite</span></span></th>
<th><span data-ttu-id="d288d-150">Rôle</span><span class="sxs-lookup"><span data-stu-id="d288d-150">Role</span></span></th>
<th><span data-ttu-id="d288d-151">Description</span><span class="sxs-lookup"><span data-stu-id="d288d-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d288d-152">Implémenter KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="d288d-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="d288d-153">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d288d-153">System administrator</span></span></td>

<td><span data-ttu-id="d288d-154">Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Contrôle des coûts</strong>.</span><span class="sxs-lookup"><span data-stu-id="d288d-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="d288d-155">Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="d288d-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="d288d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</span><span class="sxs-lookup"><span data-stu-id="d288d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="d288d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</span><span class="sxs-lookup"><span data-stu-id="d288d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="d288d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</span><span class="sxs-lookup"><span data-stu-id="d288d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="d288d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</span><span class="sxs-lookup"><span data-stu-id="d288d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d288d-160">Publiez l’espace de travail mobile <strong>Contrôle des coûts</strong>.</span><span class="sxs-lookup"><span data-stu-id="d288d-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="d288d-161">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="d288d-161">System administrator</span></span></td>
<td><span data-ttu-id="d288d-162">Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="d288d-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d288d-163">Télécharger et installer l’application mobile</span><span class="sxs-lookup"><span data-stu-id="d288d-163">Download and install the mobile app</span></span>
<span data-ttu-id="d288d-164">Télécharger et installer l’application mobile Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="d288d-164">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="d288d-165">Pour téléphones Android</span><span class="sxs-lookup"><span data-stu-id="d288d-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="d288d-166">Pour les iPhones</span><span class="sxs-lookup"><span data-stu-id="d288d-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d288d-167">Connexion à l’application mobile</span><span class="sxs-lookup"><span data-stu-id="d288d-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="d288d-168">Démarrez l’application sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="d288d-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="d288d-169">Entrez votre URL Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d288d-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="d288d-170">Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d288d-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d288d-171">Entrez vos informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="d288d-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="d288d-172">Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent.</span><span class="sxs-lookup"><span data-stu-id="d288d-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d288d-173">Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.</span><span class="sxs-lookup"><span data-stu-id="d288d-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="d288d-174">[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="d288d-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="d288d-175">Afficher les performances de votre centre de coût à l’aide de l’espace de travail mobile Contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="d288d-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="d288d-176">Sur votre appareil mobile, sélectionnez l’espace de travail **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="d288d-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="d288d-177">Sélectionnez **Contrôle des objets de coût**.</span><span class="sxs-lookup"><span data-stu-id="d288d-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="d288d-178">Sélectionnez **Actions**.</span><span class="sxs-lookup"><span data-stu-id="d288d-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="d288d-179">Sélectionnez **Sélectionner une configuration** pour sélectionner une mise en page de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="d288d-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="d288d-180">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="d288d-180">Select **Done**.</span></span>
6.  <span data-ttu-id="d288d-181">Sélectionnez **Actions**.</span><span class="sxs-lookup"><span data-stu-id="d288d-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="d288d-182">Sélectionnez **Sélectionner un objet de coût** pour sélectionner les centres de coût auxquels vous êtes autorisé à accéder.</span><span class="sxs-lookup"><span data-stu-id="d288d-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="d288d-183">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="d288d-183">Select **Done**.</span></span>
9.  <span data-ttu-id="d288d-184">Affichez les performances globales de votre centre de coût.</span><span class="sxs-lookup"><span data-stu-id="d288d-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="d288d-185">Sélectionnez le lien **Détails pour la période actuelle**.</span><span class="sxs-lookup"><span data-stu-id="d288d-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="d288d-186">Affichez les performances des éléments de coût individuels.</span><span class="sxs-lookup"><span data-stu-id="d288d-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="d288d-187">Vous pouvez également rechercher des éléments de coût spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d288d-187">You can also search for specific cost elements.</span></span>

