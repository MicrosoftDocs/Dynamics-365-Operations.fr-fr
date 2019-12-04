---
title: Vue d'ensemble de création des workflows
description: Cette rubrique illustre la création d'un workflow.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: a643be553f3fcdfbe53f2024982a596e498830a8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811288"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="553b8-103">Vue d'ensemble de création des workflows</span><span class="sxs-lookup"><span data-stu-id="553b8-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="553b8-104">Cette rubrique illustre la création d'un workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="553b8-105">Ouverture de l'éditeur de workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-105">Open the workflow editor</span></span>

<span data-ttu-id="553b8-106">Le module dans lequel vous travaillez détermine les types de workflow que vous pouvez créer.</span><span class="sxs-lookup"><span data-stu-id="553b8-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="553b8-107">Procédez comme suit pour sélectionner le type de workflow à créer et ouvrir l'éditeur de workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="553b8-108">Ouvrez le module pour lequel vous souhaitez créer un workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="553b8-109">Par exemple, pour créer un workflow pour les demandes d'achat, cliquez sur **Approvisionnements**.</span><span class="sxs-lookup"><span data-stu-id="553b8-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="553b8-110">Cliquez sur **Paramétrage** &gt; **\[Workflows de [nom du module\]**.</span><span class="sxs-lookup"><span data-stu-id="553b8-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="553b8-111">Sur la page de liste qui s'affiche, dans le volet Actions, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="553b8-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="553b8-112">Sur la page **Créer un workflow**, sélectionnez le type de workflow à créer, puis cliquez sur **Créer un workflow**.</span><span class="sxs-lookup"><span data-stu-id="553b8-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="553b8-113">L'éditeur de workflow s'affiche.</span><span class="sxs-lookup"><span data-stu-id="553b8-113">The workflow editor appears.</span></span> <span data-ttu-id="553b8-114">Vous pouvez à présent utiliser les procédures suivantes pour concevoir le workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="553b8-115">Dépôt d'éléments de workflow sur le canevas</span><span class="sxs-lookup"><span data-stu-id="553b8-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="553b8-116">La zone **Éléments du workflow** de l'éditeur de workflow contient les éléments que vous pouvez ajouter au workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="553b8-117">Pour ajouter des éléments au workflow, faites-les glisser sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="553b8-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="553b8-118">Connexion des éléments</span><span class="sxs-lookup"><span data-stu-id="553b8-118">Connect the elements</span></span>

<span data-ttu-id="553b8-119">Pour connecter deux éléments de workflow, maintenez le pointeur sur un élément jusqu'à l'affichage des points de connexion.</span><span class="sxs-lookup"><span data-stu-id="553b8-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="553b8-120">Cliquez sur un point de connexion et faites-le glisser sur un autre élément.</span><span class="sxs-lookup"><span data-stu-id="553b8-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="553b8-121">Connectez bien tous les éléments.</span><span class="sxs-lookup"><span data-stu-id="553b8-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="553b8-122">Configuration des propriétés du workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="553b8-123">Suivez la procédure suivante pour configurer les propriétés du workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="553b8-124">Cliquez sur le canevas pour être sûr qu'aucun élément de workflow n'est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="553b8-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="553b8-125">Cliquez sur **Propriétés** pour ouvrir la page **Propriétés** du workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="553b8-126">Suivez les procédures de la rubrique [Configurer les propriétés d'un workflow](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="553b8-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="553b8-127">Configuration des éléments du workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="553b8-128">Configurez tous les éléments que vous avez déposés sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="553b8-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="553b8-129">Pour plus d'informations sur la configuration des éléments de workflow, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="553b8-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="553b8-130">Configurer des tâches manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="553b8-131">Configurer des tâches automatiques dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="553b8-132">Configurer des processus d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="553b8-133">Configurer des étapes d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="553b8-134">Configurer des décisions manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="553b8-135">Configurer des décisions conditionnelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="553b8-136">Configurer des branches parallèles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="553b8-137">Configuration d'une branche parallèle</span><span class="sxs-lookup"><span data-stu-id="553b8-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="553b8-138">Configuration de workflows pour ligne</span><span class="sxs-lookup"><span data-stu-id="553b8-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="553b8-139">Résolution des erreurs et des avertissements</span><span class="sxs-lookup"><span data-stu-id="553b8-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="553b8-140">Le volet **Erreurs et avertissements** dans la partie inférieure de l'éditeur de workflow affiche les messages générés pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="553b8-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="553b8-141">Pour localiser l'élément concerné par l'erreur ou l'avertissement, double-cliquez sur le message d'erreur ou d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="553b8-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="553b8-142">Vous devez résoudre toutes les erreurs et les avertissements avant de rendre le workflow actif.</span><span class="sxs-lookup"><span data-stu-id="553b8-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="553b8-143">Enregistrement et activation du workflow</span><span class="sxs-lookup"><span data-stu-id="553b8-143">Save and activate the workflow</span></span>

<span data-ttu-id="553b8-144">Lorsque vous êtes prêts à enregistrer et à activer le workflow, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="553b8-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="553b8-145">Cliquez sur **Enregistrer et fermer** pour fermer l'éditeur de workflow et pour ouvrir la page **Sauvegarder le workflow**.</span><span class="sxs-lookup"><span data-stu-id="553b8-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="553b8-146">Entrez des commentaires sur les modifications apportées au workflow, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="553b8-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="553b8-147">Si toutes les erreurs et les avertissements ont été résolus, la page **Activer le workflow** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="553b8-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="553b8-148">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="553b8-148">Select one of the following options:</span></span>

    - <span data-ttu-id="553b8-149">Pour activer cette version du workflow, cliquez sur **Activer la nouvelle version**.</span><span class="sxs-lookup"><span data-stu-id="553b8-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="553b8-150">Lorsqu'un workflow est activé, les utilisateurs peuvent y soumettre des documents pour traitement.</span><span class="sxs-lookup"><span data-stu-id="553b8-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="553b8-151">Si vous ne souhaitez pas activer cette version, cliquez sur **Ne pas activer la nouvelle version**.</span><span class="sxs-lookup"><span data-stu-id="553b8-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="553b8-152">Vous pouvez activer le workflow ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="553b8-152">You can activate the workflow later.</span></span>
