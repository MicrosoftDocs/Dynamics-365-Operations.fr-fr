---
title: Envoyer et approuver le budget du projet
description: Cette procédure décrit comment créer et envoyer le budget d'un projet.
author: mkirknel
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14683554c45db72061ecbbf4a528656df3132692
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207443"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="273a8-103">Envoyer et approuver le budget du projet</span><span class="sxs-lookup"><span data-stu-id="273a8-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="273a8-104">Cette procédure décrit comment créer et envoyer le budget d'un projet.</span><span class="sxs-lookup"><span data-stu-id="273a8-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="273a8-105">Lors de la création d'un budget de projet, vous pouvez entrer les produits et coûts estimés pour un projet, puis les utiliser pour contrôler les transactions de projet réelles.</span><span class="sxs-lookup"><span data-stu-id="273a8-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="273a8-106">Dans la budgétisation de projet, tous les budgets d'origine et révisions doivent être transmis au workflow de projet pour approbation.</span><span class="sxs-lookup"><span data-stu-id="273a8-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="273a8-107">Le workflow renforce le contrôle sur le processus et crée un enregistrement d'historique des modifications.</span><span class="sxs-lookup"><span data-stu-id="273a8-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="273a8-108">Cette tâche a été créé à l'aide de l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="273a8-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="273a8-109">Dans le **volet de navigation**, accédez à **Modules > Gestion et comptabilité du projet > Projets > Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="273a8-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="273a8-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="273a8-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="273a8-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="273a8-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="273a8-112">Dans le **volet Action**, cliquez sur **Plan**.</span><span class="sxs-lookup"><span data-stu-id="273a8-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="273a8-113">Cliquez sur **Budget de projet**.</span><span class="sxs-lookup"><span data-stu-id="273a8-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="273a8-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="273a8-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="273a8-115">Développez l'organisateur **Coût**.</span><span class="sxs-lookup"><span data-stu-id="273a8-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="273a8-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="273a8-116">Click **New**.</span></span>
9. <span data-ttu-id="273a8-117">Dans le champ **Type de transaction**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="273a8-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="273a8-118">Saisissez ou sélectionnez une valeur dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="273a8-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="273a8-119">Dans le champ **Budget d'origine**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="273a8-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="273a8-120">Développez l'organisateur **Produits**.</span><span class="sxs-lookup"><span data-stu-id="273a8-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="273a8-121">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="273a8-121">Click **New**.</span></span>
14. <span data-ttu-id="273a8-122">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="273a8-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="273a8-123">Dans le champ **Type de transaction**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="273a8-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="273a8-124">Saisissez ou sélectionnez une valeur dans le champ **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="273a8-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="273a8-125">Dans le champ **Budget d'origine**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="273a8-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="273a8-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="273a8-126">Click **Save**.</span></span>
19. <span data-ttu-id="273a8-127">Cliquez sur **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="273a8-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="273a8-128">Cliquez sur **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="273a8-128">Click **Submit**.</span></span>
21. <span data-ttu-id="273a8-129">Dans le champ **Commentaire**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="273a8-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="273a8-130">Cliquez sur **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="273a8-130">Click **Submit**.</span></span>

