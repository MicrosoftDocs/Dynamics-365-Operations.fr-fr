---
title: Intégration du client Microsoft Project
description: La planification et la tenue à jour d'un programme de projet peuvent être complexes, les gestionnaires de projets doivent donc utiliser des outils pour les aider à gérer cette tâche. L'intégration avec le client Microsoft Project prend en charge l'ouverture et la gestion de la structure de répartition du travail pour un projet.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 04b76b6c097a82e73aba007bff82b58dbbd6eb17
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838341"
---
# <a name="microsoft-project-client-integration"></a><span data-ttu-id="c3d03-104">Intégration du client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3d03-105">La planification et la tenue à jour d'un programme de projet peuvent être complexes, les gestionnaires de projets doivent donc utiliser des outils pour les aider à gérer cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c3d03-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="c3d03-106">L'intégration avec le client Microsoft Project prend en charge l'ouverture et la gestion de la structure de répartition du travail pour un projet.</span><span class="sxs-lookup"><span data-stu-id="c3d03-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="c3d03-107">Le gestionnaire de projets peut publier les modifications dans la structure de répartition du travail de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c3d03-107">The project manager can publish any changes back to the Finance and Operations project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="c3d03-108">Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, mise à jour de juillet, vous devez installer KB 4054797 et 4055884.</span><span class="sxs-lookup"><span data-stu-id="c3d03-108">If you are using Microsoft Dynamics 365 for Finance and Operations, July update, you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="c3d03-109">Configurer le complément du client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="c3d03-110">Pour activer l'intégration avec le client Microsoft Project, un complément Microsoft Dynamics 365 doit être installé dans l'application cliente Microsoft Project de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3d03-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="c3d03-111">Pour ce faire, ouvrez l'espace de travail **Gestion des projets**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="c3d03-112">•   Cliquez sur **Configurer le complément du client du projet** dans la section **Liens** > **Paramétrage** de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="c3d03-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="c3d03-113">•   Cliquez sur **Ouvrir**, puis sur **Exécuter** lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="c3d03-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="c3d03-114">Ouvrir et modifier une structure de répartition du travail existante dans le client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="c3d03-115">Si un projet dans Finance and Operations a déjà créé une structure de répartition du travail, celle-ci peut être ouverte dans l'application cliente Microsoft Project si son statut est Brouillon.</span><span class="sxs-lookup"><span data-stu-id="c3d03-115">If a project in Finance and Operations already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="c3d03-116">Pour l'ouvrir à partir de la page **Projet**, cliquez sur le lien **Ouvrir dans Microsoft Project** dans l'onglet **Plan**. Il est également possible d'ouvrir cette page à partir de l'application cliente Microsoft Project en cliquant sur **Ouvrir** dans l'onglet **Microsoft Dynamics 365**. Sélectionnez **Entité juridique** et **Projet** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c3d03-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="c3d03-117">Si vous utilisez Internet Explorer comme navigateur, vous devez cliquer sur **Enregistrer** pour ouvrir manuellement le fichier à partir de l'emplacement de téléchargement du fichier.</span><span class="sxs-lookup"><span data-stu-id="c3d03-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="c3d03-118">Ou, cliquez sur **Enregistrer et ouvrir** pour ouvrir le fichier dans le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="c3d03-119">Ne renommez pas le nom du fichier lors de l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c3d03-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="c3d03-120">Avant d'apporter des modifications au fichier à l'aide du client Microsoft Project, vous devez l'extraire. Cliquez sur **Extraction** dans l'onglet **Microsoft Dynamics 365**. Cela empêche d'autres utilisateurs de modifier en même temps la structure de répartition du travail depuis Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c3d03-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance and Operations at the same time.</span></span> <span data-ttu-id="c3d03-121">Pour publier la structure de répartition du travail après avoir effectué les modifications, cliquez sur **Archivage** dans l'onglet **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="c3d03-122">Si une équipe de projet a déjà été ajoutée au projet dans Finance and Operations, la liste des ressources est renseignée avec les membres de l'équipe.</span><span class="sxs-lookup"><span data-stu-id="c3d03-122">If a project team has already been added to the project in Finance and Operations, the resource list will be populated with the team members.</span></span> <span data-ttu-id="c3d03-123">Si une équipe de projet n'a pas encore été ajoutée au projet, vous pouvez sélectionner des ressources et créer l'équipe dans le client Microsoft Project en cliquant sur le bouton **Ressources** dans l'onglet **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="c3d03-124">Les données suivantes sont synchronisées dans Finance and Operations dans le cadre du processus d'archivage :</span><span class="sxs-lookup"><span data-stu-id="c3d03-124">The following data will be synced back to Finance and Operations as part of the check in process:</span></span>

<span data-ttu-id="c3d03-125">•   Nom de la tâche</span><span class="sxs-lookup"><span data-stu-id="c3d03-125">•   Task name</span></span>

<span data-ttu-id="c3d03-126">•   Date de début</span><span class="sxs-lookup"><span data-stu-id="c3d03-126">•   Start date</span></span>

<span data-ttu-id="c3d03-127">•   Date de fin</span><span class="sxs-lookup"><span data-stu-id="c3d03-127">•   Finish date</span></span>

<span data-ttu-id="c3d03-128">•   Prédécesseurs</span><span class="sxs-lookup"><span data-stu-id="c3d03-128">•   Predecessors</span></span>

<span data-ttu-id="c3d03-129">•   Noms des ressources</span><span class="sxs-lookup"><span data-stu-id="c3d03-129">•   Resource names</span></span>

<span data-ttu-id="c3d03-130">•   Catégorie</span><span class="sxs-lookup"><span data-stu-id="c3d03-130">•   Category</span></span>

<span data-ttu-id="c3d03-131">•   Catégorie des ressources</span><span class="sxs-lookup"><span data-stu-id="c3d03-131">•   Resource category</span></span>

<span data-ttu-id="c3d03-132">•   Heures de travail</span><span class="sxs-lookup"><span data-stu-id="c3d03-132">•   Work hours</span></span>

<span data-ttu-id="c3d03-133">•   Notes</span><span class="sxs-lookup"><span data-stu-id="c3d03-133">•   Notes</span></span>

<span data-ttu-id="c3d03-134">•   Priorité</span><span class="sxs-lookup"><span data-stu-id="c3d03-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="c3d03-135">Si vous ajoutez d'autres colonnes au fichier du client Microsoft Project, celles-ci ne sont pas enregistrées dans le fichier et ne s'affichent pas lors de la réouverture du fichier.</span><span class="sxs-lookup"><span data-stu-id="c3d03-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="c3d03-136">Créer la structure de répartition du travail pour un projet existant à l'aide du client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="c3d03-137">Pour créer une structure de répartition du travail à l'aide du client Microsoft Project, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3d03-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="c3d03-138">Ouvrez le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c3d03-139">Sur l'onglet **Microsoft Dynamics 365**, cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="c3d03-140">Sélectionnez l'**Entité juridique** du projet.</span><span class="sxs-lookup"><span data-stu-id="c3d03-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="c3d03-141">Sélectionnez le **Projet**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="c3d03-142">Cliquez sur **Extraction** sur l'onglet **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="c3d03-143">Lorsque vous êtes prêt à publier le fichier dans Finance and Operations, cliquez sur **Archivage** dans l'onglet **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-143">When ready to publish to Finance and Operations, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="c3d03-144">Remplacer la structure de répartition du travail existante pour un projet existant à l'aide du client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="c3d03-145">Pour créer une structure de répartition du travail à l'aide du client Microsoft Project et remplacer une structure de répartition du travail existante pour un projet existant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3d03-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="c3d03-146">Ouvrez le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c3d03-147">Créez le programme dans le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="c3d03-148">Sous l'onglet **Microsoft Dynamics 365**, cliquez sur **Enregistrer les modifications** > **Remplacer un projet existant**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="c3d03-149">Sélectionnez l'**Entité juridique** du projet.</span><span class="sxs-lookup"><span data-stu-id="c3d03-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="c3d03-150">Sélectionnez le **Projet**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="c3d03-151">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="c3d03-152">Créer un projet à partir du client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c3d03-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="c3d03-153">Ouvrez le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c3d03-154">Créez le programme dans le client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c3d03-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="c3d03-155">Sous l'onglet **Microsoft Dynamics 365**, cliquez sur **Enregistrer les modifications** > **Enregistrer vers un nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="c3d03-156">Sélectionnez l'**Entité juridique** du projet.</span><span class="sxs-lookup"><span data-stu-id="c3d03-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="c3d03-157">Entrez l'**ID projet**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c3d03-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="c3d03-158">Entrez le **Nom du projet**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="c3d03-159">Sélectionnez le **Type de projet**, le **Groupe de projets** et l'**ID contrat de projet**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="c3d03-160">Vous pouvez également créer un contrat de projet en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="c3d03-161">Sélectionnez le **Calendrier** à utiliser pour les ressources.</span><span class="sxs-lookup"><span data-stu-id="c3d03-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="c3d03-162">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d03-162">Click **OK**.</span></span>
