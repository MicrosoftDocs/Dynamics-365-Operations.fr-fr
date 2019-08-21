---
title: Espace de travail mobile Contrôle des coûts
description: Cette rubrique fournit des informations sur l'espace de travail mobile Contrôle des coûts. Cet espace de travail permet aux responsables de centre de coût d'afficher des informations sur les performances du centre de coût à tout moment et n'importe où.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 82cabe93844cc27ae3c8470e3eecb902a3e5d089
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841631"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="8a8fe-104">Espace de travail mobile Contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="8a8fe-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a8fe-105">Cette rubrique fournit des informations sur l'espace de travail mobile **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="8a8fe-106">Cet espace de travail permet aux responsables de centre de coût d'afficher des informations sur les performances du centre de coût à tout moment et n'importe où.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="8a8fe-107">Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Microsoft Dynamics 365 for Unified Operations</span><span class="sxs-lookup"><span data-stu-id="8a8fe-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="8a8fe-108">Présentation</span><span class="sxs-lookup"><span data-stu-id="8a8fe-108">Overview</span></span>
<span data-ttu-id="8a8fe-109">L'espace de travail mobile **Contrôle des coûts** fournit une vue instantanée des performances actuelles des centres de coût en comparant les coûts réels aux coûts budgétés.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="8a8fe-110">Vous pouvez accéder au statut des éléments de coût individuels.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="8a8fe-111">Par exemple, un employé reçoit une invitation à une conférence internationale, mais l'organisation doit couvrir toutes les dépenses de déplacement.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="8a8fe-112">L'employé demande à son responsable s'il peut assister à la conférence.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="8a8fe-113">Le responsable ouvre rapidement l'espace de travail **Contrôle des coûts** sur son téléphone portable de voir s'il dispose du budget nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="8a8fe-114">Sécurité des données</span><span class="sxs-lookup"><span data-stu-id="8a8fe-114">Data security</span></span>
<span data-ttu-id="8a8fe-115">Les données de l'espace de travail **Contrôle des coûts** sont sécurisées par les informations d'identification de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="8a8fe-116">Les responsables de centre de coût sont uniquement autorisés à consulter les données de leur propre centre de coût.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="8a8fe-117">La sécurité au niveau de l'accès est gérée dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="8a8fe-118">Les contrôleurs de gestion définissent la configuration de l'espace de travail mobile **Contrôle des coûts** dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="8a8fe-119">Une fois que l'espace de travail est publié sur l'application mobile, il est disponible dans l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="8a8fe-120">Par conséquent, tous les responsables de centre de coût de l'organisation peuvent consultent les données au même format.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="8a8fe-121">Actions, vues et liens</span><span class="sxs-lookup"><span data-stu-id="8a8fe-121">Actions, views, and links</span></span>
<span data-ttu-id="8a8fe-122">L'espace de travail mobile **Contrôle des coûts** fournit les actions, les vues et les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="8a8fe-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="8a8fe-123">**Actions :**</span><span class="sxs-lookup"><span data-stu-id="8a8fe-123">**Actions:**</span></span>

    -   <span data-ttu-id="8a8fe-124">Utilisez **Sélectionner une configuration** pour sélectionner une mise en page.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="8a8fe-125">Utilisez **Sélectionner un objet de coût** pour sélectionner les centres de coût et filtrer les données en fonction.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="8a8fe-126">Les centres de coût qui figurent dans la liste dépendent de l'accès qui est accordé dans le module **Contrôle de gestion**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="8a8fe-127">**Vues :** selon la sélection des actions et la configuration du module **Contrôle de gestion**, vous pouvez afficher les informations suivantes dans les cartes :</span><span class="sxs-lookup"><span data-stu-id="8a8fe-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="8a8fe-128">Comparatif Réel/Budget (période actuelle)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="8a8fe-129">Comparatif Réel/Budget révisé (période actuelle)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="8a8fe-130">Réel/Budget (période précédente)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="8a8fe-131">Réel/Budget révisé (période précédente)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="8a8fe-132">Réel/Budget (année en cours)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="8a8fe-133">Réel/Budget révisé (année en cours)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="8a8fe-134">Les montants suivants sont affichés dans chaque carte : Réel, Budget, Écart, et Écart en %.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="8a8fe-135">**Liens :**</span><span class="sxs-lookup"><span data-stu-id="8a8fe-135">**Links:**</span></span>

    -   <span data-ttu-id="8a8fe-136">Détails pour la période actuelle</span><span class="sxs-lookup"><span data-stu-id="8a8fe-136">Details for current period</span></span>
    -   <span data-ttu-id="8a8fe-137">Détails pour la période précédente</span><span class="sxs-lookup"><span data-stu-id="8a8fe-137">Details for previous period</span></span>
    -   <span data-ttu-id="8a8fe-138">Détails pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="8a8fe-138">Details for year to date</span></span>

    <span data-ttu-id="8a8fe-139">Lorsque vous sélectionnez un lien, une carte est affichée pour chaque élément de coût.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="8a8fe-140">Les montants suivants sont affichés sur chaque carte : réel, budget, écart budgétaire, écart budgétaire en %, budget révisé, écart budgétaire révisé et écart budgétaire révisé en %.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="8a8fe-141">[![Carte pour un élément de coût ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a8fe-142">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8a8fe-142">Prerequisites</span></span>
<span data-ttu-id="8a8fe-143">Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="8a8fe-144">Conditions requises si vous utilisez Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8a8fe-144">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations</span></span>
<span data-ttu-id="8a8fe-145">Si Microsoft Dynamics 365 for Finance and Operationsa été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-145">If Microsoft Dynamics 365 for Finance and Operations has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="8a8fe-146">Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="8a8fe-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="8a8fe-147">Conditions requises si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="8a8fe-147">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="8a8fe-148">Si la version 1611 de Microsoft Dynamics 365 for Operations avec la mise à jour de plateforme 3 ou ultérieure a été déployée pour votre organisation, l'administrateur système doit effectuer les tâches préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-148">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8a8fe-149">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="8a8fe-149">Prerequisite</span></span></th>
<th><span data-ttu-id="8a8fe-150">Rôle</span><span class="sxs-lookup"><span data-stu-id="8a8fe-150">Role</span></span></th>
<th><span data-ttu-id="8a8fe-151">Description</span><span class="sxs-lookup"><span data-stu-id="8a8fe-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8a8fe-152">Implémenter KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="8a8fe-153">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="8a8fe-153">System administrator</span></span></td>

<td><span data-ttu-id="8a8fe-154">Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Contrôle des coûts</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="8a8fe-155">Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="8a8fe-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="8a8fe-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="8a8fe-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="8a8fe-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="8a8fe-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8a8fe-160">Publiez l'espace de travail mobile <strong>Contrôle des coûts</strong>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="8a8fe-161">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="8a8fe-161">System administrator</span></span></td>
<td><span data-ttu-id="8a8fe-162">Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="8a8fe-163">Télécharger et installer l'application mobile</span><span class="sxs-lookup"><span data-stu-id="8a8fe-163">Download and install the mobile app</span></span>
<span data-ttu-id="8a8fe-164">Téléchargez et installez l'application mobile Dynamics 365 for Unified Operations :</span><span class="sxs-lookup"><span data-stu-id="8a8fe-164">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="8a8fe-165">Pour téléphones Android</span><span class="sxs-lookup"><span data-stu-id="8a8fe-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="8a8fe-166">Pour les iPhones</span><span class="sxs-lookup"><span data-stu-id="8a8fe-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="8a8fe-167">Connexion à l'application mobile</span><span class="sxs-lookup"><span data-stu-id="8a8fe-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="8a8fe-168">Démarrez l'application sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="8a8fe-169">Entrez votre URL Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="8a8fe-170">Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="8a8fe-171">Entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="8a8fe-172">Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="8a8fe-173">Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="8a8fe-174">[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="8a8fe-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="8a8fe-175">Afficher les performances de votre centre de coût à l'aide de l'espace de travail mobile Contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="8a8fe-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="8a8fe-176">Sur votre appareil mobile, sélectionnez l'espace de travail **Contrôle des coûts**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="8a8fe-177">Sélectionnez **Contrôle des objets de coût**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="8a8fe-178">Sélectionnez **Actions**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="8a8fe-179">Sélectionnez **Sélectionner une configuration** pour sélectionner une mise en page de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="8a8fe-180">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-180">Select **Done**.</span></span>
6.  <span data-ttu-id="8a8fe-181">Sélectionnez **Actions**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="8a8fe-182">Sélectionnez **Sélectionner un objet de coût** pour sélectionner les centres de coût auxquels vous êtes autorisé à accéder.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="8a8fe-183">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-183">Select **Done**.</span></span>
9.  <span data-ttu-id="8a8fe-184">Affichez les performances globales de votre centre de coût.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="8a8fe-185">Sélectionnez le lien **Détails pour la période actuelle**.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="8a8fe-186">Affichez les performances des éléments de coût individuels.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="8a8fe-187">Vous pouvez également rechercher des éléments de coût spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8a8fe-187">You can also search for specific cost elements.</span></span>

