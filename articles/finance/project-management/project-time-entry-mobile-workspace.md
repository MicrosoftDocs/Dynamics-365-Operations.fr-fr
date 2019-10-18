---
title: Espace de travail mobile de saisie de l'heure du projet
description: Cette rubrique fournit des informations sur l'espace de travail mobile Saisie des heures du projet. Cet espace de travail permet aux utilisateurs d'entrer et de gagner du temps sur un projet à l'aide d'un appareil mobile.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ee11f7f392676adb59bd25f6549737482faf5fdb
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250367"
---
# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="2ec92-104">Espace de travail mobile de saisie de l'heure du projet</span><span class="sxs-lookup"><span data-stu-id="2ec92-104">Project time entry mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ec92-105">Cette rubrique fournit des informations sur l'espace de travail mobile **Saisie des heures du projet**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="2ec92-106">Cet espace de travail permet aux utilisateurs d'entrer et de gagner du temps sur un projet à l'aide d'un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="2ec92-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="2ec92-107">Cet espace de travail mobile est destiné à être utilisé avec l'application mobile Dynamics 365 Unified Ops.</span><span class="sxs-lookup"><span data-stu-id="2ec92-107">This mobile workspace is intended to be used with the Dynamics 365 Unified Ops mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="2ec92-108">Présentation</span><span class="sxs-lookup"><span data-stu-id="2ec92-108">Overview</span></span>
<span data-ttu-id="2ec92-109">Dans le cadre de leur travail quotidien, les collaborateurs qui travaillent à un projet sont souvent sur site ou en voyage.</span><span class="sxs-lookup"><span data-stu-id="2ec92-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="2ec92-110">L'espace de travail mobile **Saisie des heures du projet** permet aux utilisateurs d'entrer les heures facturables ou non facturables pour un projet sur l'appareil mobile de leur choix.</span><span class="sxs-lookup"><span data-stu-id="2ec92-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="2ec92-111">Par conséquent, ils peuvent enregistrer les heures à tout moment et n'importe où.</span><span class="sxs-lookup"><span data-stu-id="2ec92-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="2ec92-112">Ils peuvent également afficher les heures déjà consignées.</span><span class="sxs-lookup"><span data-stu-id="2ec92-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="2ec92-113">Spécifiquement, dans l'espace de travail mobile **Saisie des heures du projet**, les utilisateurs peuvent effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ec92-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="2ec92-114">Pour n'importe quelle date sélectionnée, il permet d'entrer le nombre d'heures que vous avez passées sur une tâche spécifique.</span><span class="sxs-lookup"><span data-stu-id="2ec92-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="2ec92-115">Il permet de lancer une recherche par nom de projet ou client pour entrer les heures correspondantes.</span><span class="sxs-lookup"><span data-stu-id="2ec92-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="2ec92-116">Il permet de spécifier la catégorie et l'activité qui correspondent aux heures.</span><span class="sxs-lookup"><span data-stu-id="2ec92-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="2ec92-117">Il permet d'enregistrer les heures facturables ou non facturables pour le projet.</span><span class="sxs-lookup"><span data-stu-id="2ec92-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="2ec92-118">Facultatif : il permet de saisir des commentaires externes ou internes.</span><span class="sxs-lookup"><span data-stu-id="2ec92-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ec92-119">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2ec92-119">Prerequisites</span></span>
<span data-ttu-id="2ec92-120">Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2ec92-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-dynamics-365-finance"></a><span data-ttu-id="2ec92-121">Conditions requises si vous utilisez Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="2ec92-121">Prerequisites if you use Dynamics 365 Finance</span></span>
<span data-ttu-id="2ec92-122">Si Finance a été déployé pour votre organisation, l'administrateur système doit publier l'espace de travail mobile **Saisie du temps de projet**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-122">If Finance has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="2ec92-123">Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="2ec92-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="2ec92-124">Conditions requises si vous utilisez la version 1611 avec Platform Update 3 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="2ec92-124">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="2ec92-125">Si la version 1611 avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l'administrateur système doit effectuer les tâches préalables suivantes.</span><span class="sxs-lookup"><span data-stu-id="2ec92-125">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2ec92-126">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="2ec92-126">Prerequisite</span></span></th>
<th><span data-ttu-id="2ec92-127">Rôle</span><span class="sxs-lookup"><span data-stu-id="2ec92-127">Role</span></span></th>
<th><span data-ttu-id="2ec92-128">Description</span><span class="sxs-lookup"><span data-stu-id="2ec92-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="2ec92-129">Implémenter KB 4018050.</span><span class="sxs-lookup"><span data-stu-id="2ec92-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="2ec92-130">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2ec92-130">System administrator</span></span></td>
<td><span data-ttu-id="2ec92-131">Le KB 4018050 est une mise à jour X++ ou un correctif de métadonnées qui contient l'espace de travail mobile <strong>Saisie des heures du projet</strong>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="2ec92-132">Pour implémenter le KB 4018050, un administrateur système doit procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="2ec92-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="2ec92-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Télécharger le correctif de métadonnées depuis Microsoft Dynamics Lifecycle Services</a>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="2ec92-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installez le correctif de métadonnées</a>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="2ec92-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Créez un module déployable</a> contenant les modèles <strong>ApplicationSuite</strong> et <strong>ProjectMobile</strong>, et téléchargez le module déployable vers LCS.</span><span class="sxs-lookup"><span data-stu-id="2ec92-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="2ec92-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Appliquer le package déployable</a>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2ec92-137">Publiez l'espace de travail mobile <strong>Saisie des heures du projet</strong>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="2ec92-138">Administrateur système</span><span class="sxs-lookup"><span data-stu-id="2ec92-138">System administrator</span></span></td>
<td><span data-ttu-id="2ec92-139">Voir <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publier un espace de travail mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="2ec92-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="2ec92-140">Télécharger et installer l'application mobile</span><span class="sxs-lookup"><span data-stu-id="2ec92-140">Download and install the mobile app</span></span>

<span data-ttu-id="2ec92-141">Télécharger et installer l'application mobile Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="2ec92-141">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="2ec92-142">Pour téléphones Android</span><span class="sxs-lookup"><span data-stu-id="2ec92-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="2ec92-143">Pour les iPhones</span><span class="sxs-lookup"><span data-stu-id="2ec92-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="2ec92-144">Connexion à l'application mobile</span><span class="sxs-lookup"><span data-stu-id="2ec92-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="2ec92-145">Démarrez l'application sur votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="2ec92-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="2ec92-146">Entrez votre URL Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2ec92-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="2ec92-147">Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d'utilisateur et mot de passe.</span><span class="sxs-lookup"><span data-stu-id="2ec92-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="2ec92-148">Entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="2ec92-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="2ec92-149">Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s'affichent.</span><span class="sxs-lookup"><span data-stu-id="2ec92-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="2ec92-150">Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.</span><span class="sxs-lookup"><span data-stu-id="2ec92-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="2ec92-151">[![Extraire pour actualiser](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="2ec92-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="2ec92-152">Entrer les heures en utilisant l'espace de travail mobile Saisie des heures du projet</span><span class="sxs-lookup"><span data-stu-id="2ec92-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="2ec92-153">Sur votre appareil mobile, sélectionnez l'espace de travail **Saisie des heures du projet**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="2ec92-154">Sélectionnez **Saisie des heures**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-154">Select **Time entry**.</span></span> <span data-ttu-id="2ec92-155">Les dates civiles pour la semaine en cours sont affichées.</span><span class="sxs-lookup"><span data-stu-id="2ec92-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="2ec92-156">Pour une date sélectionnée, choisissez &gt; **Action** **Nouvelle saisie**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="2ec92-157">Entrez le nombre d'heures.</span><span class="sxs-lookup"><span data-stu-id="2ec92-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="2ec92-158">Sélectionnez le projet concerné par la saisie d'heures.</span><span class="sxs-lookup"><span data-stu-id="2ec92-158">Select the project for the time entry.</span></span> <span data-ttu-id="2ec92-159">Une liste affiche les projets chargés dans votre application pour l'utilisation hors ligne.</span><span class="sxs-lookup"><span data-stu-id="2ec92-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="2ec92-160">Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre.</span><span class="sxs-lookup"><span data-stu-id="2ec92-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="2ec92-161">Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="2ec92-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="2ec92-162">Si votre projet ne figure pas dans la liste, sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="2ec92-163">Recherchez par nom, ou lancez une recherche par nom de projet ou de client.</span><span class="sxs-lookup"><span data-stu-id="2ec92-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="2ec92-164">Permet de sélectionner une catégorie.</span><span class="sxs-lookup"><span data-stu-id="2ec92-164">Select a category.</span></span> <span data-ttu-id="2ec92-165">Une liste affiche les catégories chargées dans votre application pour l'utilisation hors ligne.</span><span class="sxs-lookup"><span data-stu-id="2ec92-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="2ec92-166">Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre.</span><span class="sxs-lookup"><span data-stu-id="2ec92-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="2ec92-167">Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="2ec92-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="2ec92-168">Si votre catégorie ne figure pas dans la liste, sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="2ec92-169">Recherchez par catégorie, ou lancez une rechercher par nom de catégorie.</span><span class="sxs-lookup"><span data-stu-id="2ec92-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="2ec92-170">Permet de sélectionner une activité.</span><span class="sxs-lookup"><span data-stu-id="2ec92-170">Select an activity.</span></span> <span data-ttu-id="2ec92-171">Une liste affiche les activités chargées dans votre application pour l'utilisation hors ligne.</span><span class="sxs-lookup"><span data-stu-id="2ec92-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="2ec92-172">Par défaut, jusqu'à 50 éléments sont chargés, mais votre développeur peut modifier ce nombre.</span><span class="sxs-lookup"><span data-stu-id="2ec92-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="2ec92-173">Pour plus d'informations, voir [Plateforme mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="2ec92-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="2ec92-174">Si votre activité ne figure pas dans la liste, sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="2ec92-175">Recherchez par numéro d'activité, ou lancez une rechercher par objectif.</span><span class="sxs-lookup"><span data-stu-id="2ec92-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="2ec92-176">Sélectionner la propriété de ligne.</span><span class="sxs-lookup"><span data-stu-id="2ec92-176">Select the line property.</span></span>
12. <span data-ttu-id="2ec92-177">Facultatif : saisissez des commentaires externes et internes.</span><span class="sxs-lookup"><span data-stu-id="2ec92-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="2ec92-178">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="2ec92-178">Select **Done**.</span></span>
