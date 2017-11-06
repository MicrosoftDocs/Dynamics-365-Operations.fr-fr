---
title: "Utilisation des workflows pour gérer les informations des employés"
description: "Cette rubrique explique comment les Ressources humaines peuvent utiliser la capacité de workflow pour gérer les informations des employés. Par exemple, vous pouvez associer un workflow avec un poste et configurer un workflow d'approbation qui démarre lorsque les employés modifient leur enregistrement."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47c569f3531bf00795078b7b042bf899b51bad8d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="39b67-104">Utilisation des workflows pour gérer les informations des employés</span><span class="sxs-lookup"><span data-stu-id="39b67-104">Use workflows to manage employee information</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="39b67-105">Cette rubrique explique comment les Ressources humaines peuvent utiliser la capacité de workflow pour gérer les informations des employés.</span><span class="sxs-lookup"><span data-stu-id="39b67-105">This topic explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="39b67-106">Par exemple, vous pouvez associer un workflow avec un poste et configurer un workflow d'approbation qui démarre lorsque les employés modifient leur enregistrement.</span><span class="sxs-lookup"><span data-stu-id="39b67-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="39b67-107">La capacité de workflow pour les ressources humaines fournit de nombreux workflows pour gérer les activités des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="39b67-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="39b67-108">En outre, de nombreuses options sont disponibles pour modifier des workflows spécifiques et les associer à une hiérarchie de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="39b67-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="39b67-109">Les workflows sont disponibles pour faciliter la gestion des modifications de plusieurs types standard d'informations des employés.</span><span class="sxs-lookup"><span data-stu-id="39b67-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="39b67-110">Vous pouvez associer un workflow à un poste.</span><span class="sxs-lookup"><span data-stu-id="39b67-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="39b67-111">Ensuite, si les employés modifient leur enregistrement d'employé, un workflow nécessitant une approbation démarre que les nouvelles informations soient enregistrées.</span><span class="sxs-lookup"><span data-stu-id="39b67-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="39b67-112">Les workflows sont prédéfinis pour les types d'informations suivants, afin de vous aider à gérer efficacement les modifications et à tenir à jour les données des employés :</span><span class="sxs-lookup"><span data-stu-id="39b67-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="39b67-113">Numéros d'identifications</span><span class="sxs-lookup"><span data-stu-id="39b67-113">Identification numbers</span></span>
-   <span data-ttu-id="39b67-114">Cours</span><span class="sxs-lookup"><span data-stu-id="39b67-114">Courses</span></span>
-   <span data-ttu-id="39b67-115">Formation</span><span class="sxs-lookup"><span data-stu-id="39b67-115">Education</span></span>
-   <span data-ttu-id="39b67-116">Image</span><span class="sxs-lookup"><span data-stu-id="39b67-116">Image</span></span>
-   <span data-ttu-id="39b67-117">Articles empruntés</span><span class="sxs-lookup"><span data-stu-id="39b67-117">Loaned items</span></span>
-   <span data-ttu-id="39b67-118">Expérience professionnelle</span><span class="sxs-lookup"><span data-stu-id="39b67-118">Professional experience</span></span>
-   <span data-ttu-id="39b67-119">Expérience de projet</span><span class="sxs-lookup"><span data-stu-id="39b67-119">Project experience</span></span>
-   <span data-ttu-id="39b67-120">Qualifications</span><span class="sxs-lookup"><span data-stu-id="39b67-120">Skills</span></span>
-   <span data-ttu-id="39b67-121">Postes de confiance</span><span class="sxs-lookup"><span data-stu-id="39b67-121">Positions of trust</span></span>
-   <span data-ttu-id="39b67-122">Actions des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="39b67-122">Human resources actions</span></span>
-   <span data-ttu-id="39b67-123">Inscriptions aux cours</span><span class="sxs-lookup"><span data-stu-id="39b67-123">Course registration</span></span>

<span data-ttu-id="39b67-124">Lorsque des employés sont engagés, transférés ou licenciés, le workflow peut inclure un processus de révision.</span><span class="sxs-lookup"><span data-stu-id="39b67-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="39b67-125">Ainsi, un document peut être révisé, ou les conditions d'une action peuvent être définies dans le cadre du workflow.</span><span class="sxs-lookup"><span data-stu-id="39b67-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="39b67-126">Lorsque le processus de révision est terminé, le document ou l'action est terminé, puis le workflow passe à l'étape d'approbation finale.</span><span class="sxs-lookup"><span data-stu-id="39b67-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="39b67-127">Associer un workflow à une hiérarchie de postes</span><span class="sxs-lookup"><span data-stu-id="39b67-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="39b67-128">Vous pouvez associer un workflow avec n'importe quelle hiérarchie que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="39b67-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="39b67-129">Par exemple, si un poste est associé à une hiérarchie de génération d'états matricielle, vous pouvez configurer un workflow qui achemine les dépenses pour un projet spécifique vers le chef du projet au lieu du responsable de l'employé associé à ce poste.</span><span class="sxs-lookup"><span data-stu-id="39b67-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="39b67-130">Pour créer un workflow ou modifier un workflow existant, dans la page **Workflow des ressources humaines**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="39b67-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="39b67-131">Sélectionnez un workflow dans la liste pour démarrer le concepteur de workflow.</span><span class="sxs-lookup"><span data-stu-id="39b67-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="39b67-132">Vous pouvez utiliser le concepteur pour créer un workflow ou modifier les étapes d'un workflow existant.</span><span class="sxs-lookup"><span data-stu-id="39b67-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="39b67-133">Lorsque vous modifiez un workflow existant, vos modifications sont enregistrées sous une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="39b67-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="39b67-134">Par conséquent, vous pouvez toujours revenir à une version précédente, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="39b67-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="39b67-135">Configurer un workflow des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="39b67-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="39b67-136">Pour configurer un workflow de base qui démarre lorsque des employés demandent de modifier leur identification personnelle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="39b67-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="39b67-137">Dans la page **Workflows des ressources humaines**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="39b67-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="39b67-138">Dans la liste des workflows disponibles, sélectionnez **Numéros d'identification**.</span><span class="sxs-lookup"><span data-stu-id="39b67-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="39b67-139">Cliquez sur **Exécuter** pour démarrer le concepteur de workflow, puis entrez votre nom d'utilisateur et votre mot de passe à l'invite.</span><span class="sxs-lookup"><span data-stu-id="39b67-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="39b67-140">Faites glisser l'élément **Approuver le numéro d'identification** de la liste des éléments de workflow vers le canevas du concepteur.</span><span class="sxs-lookup"><span data-stu-id="39b67-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="39b67-141">Reliez l'élément d'approbation à **Démarrer** et **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="39b67-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="39b67-142">Double-cliquez sur **Approuver l'élément**, puis cliquez avec le bouton droit et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="39b67-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="39b67-143">Procédez comme suit pour ajouter des instructions relatives à un élément de travail :</span><span class="sxs-lookup"><span data-stu-id="39b67-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="39b67-144">Sélectionnez **Affectation**, puis sélectionnez **Hiérarchie** sous le type d'affectation.</span><span class="sxs-lookup"><span data-stu-id="39b67-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="39b67-145">Sous la sélection **Hiérarchie**, sélectionnez **Hiérarchie configurable**.</span><span class="sxs-lookup"><span data-stu-id="39b67-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="39b67-146">Ajoutez une condition d'arrêt, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="39b67-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="39b67-147">Entrez les instructions supplémentaires (il ne doit exister aucun avertissement supplémentaire).</span><span class="sxs-lookup"><span data-stu-id="39b67-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="39b67-148">Cliquez sur **Enregistrer et fermer**.</span><span class="sxs-lookup"><span data-stu-id="39b67-148">Click **Save and close**.</span></span> <span data-ttu-id="39b67-149">Activez le nouveau workflow lorsque la boîte de dialogue s'ouvre, puis sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="39b67-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="39b67-150">Accédez à **Ressources humaines** &gt; **Postes** &gt; **Types de hiérarchie de postes**.</span><span class="sxs-lookup"><span data-stu-id="39b67-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="39b67-151">Sélectionnez **Matrice**.</span><span class="sxs-lookup"><span data-stu-id="39b67-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="39b67-152">Ajoutez le workflow **Numéro d'identification du collaborateur** à la liste.</span><span class="sxs-lookup"><span data-stu-id="39b67-152">Add the **Worker identification number** workflow to the list.</span></span>





