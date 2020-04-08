---
title: Envoyer et approuver le budget du projet
description: Cette procédure décrit comment créer et envoyer le budget d'un projet.
author: mkirknel
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7aa7c301946b92b956f4b1b0f92985451ffe917e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149433"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="a59bb-103">Envoyer et approuver le budget du projet</span><span class="sxs-lookup"><span data-stu-id="a59bb-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a59bb-104">Cette procédure décrit comment créer et envoyer le budget d'un projet.</span><span class="sxs-lookup"><span data-stu-id="a59bb-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="a59bb-105">Lors de la création d'un budget de projet, vous pouvez entrer les produits et coûts estimés pour un projet, puis les utiliser pour contrôler les transactions de projet réelles.</span><span class="sxs-lookup"><span data-stu-id="a59bb-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="a59bb-106">Dans la budgétisation de projet, tous les budgets d'origine et révisions doivent être transmis au workflow de projet pour approbation.</span><span class="sxs-lookup"><span data-stu-id="a59bb-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="a59bb-107">Le workflow renforce le contrôle sur le processus et crée un enregistrement d'historique des modifications.</span><span class="sxs-lookup"><span data-stu-id="a59bb-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="a59bb-108">Cette tâche a été créé à l'aide de l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="a59bb-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="a59bb-109">Dans le **volet de navigation**, accédez à **Modules > Gestion et comptabilité du projet > Projets > Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="a59bb-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a59bb-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a59bb-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a59bb-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a59bb-112">Dans le **volet Action**, cliquez sur **Plan**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="a59bb-113">Cliquez sur **Budget de projet**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="a59bb-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="a59bb-115">Développez l'organisateur **Coût**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="a59bb-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-116">Click **New**.</span></span>
9. <span data-ttu-id="a59bb-117">Dans le champ **Type de transaction**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="a59bb-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="a59bb-118">Saisissez ou sélectionnez une valeur dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="a59bb-119">Dans le champ **Budget d'origine**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="a59bb-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="a59bb-120">Développez l'organisateur **Produits**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="a59bb-121">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-121">Click **New**.</span></span>
14. <span data-ttu-id="a59bb-122">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a59bb-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="a59bb-123">Dans le champ **Type de transaction**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="a59bb-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="a59bb-124">Saisissez ou sélectionnez une valeur dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="a59bb-125">Dans le champ **Budget d'origine**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="a59bb-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="a59bb-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-126">Click **Save**.</span></span>
19. <span data-ttu-id="a59bb-127">Cliquez sur **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="a59bb-128">Cliquez sur **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-128">Click **Submit**.</span></span>
21. <span data-ttu-id="a59bb-129">Dans le champ **Commentaire**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a59bb-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="a59bb-130">Cliquez sur **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="a59bb-130">Click **Submit**.</span></span>

