---
title: Délégation d’éléments de travail dans un workflow
description: Si vous pensez vous absenter du bureau ou être dans l’incapacité d’agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d’autres utilisateurs.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48d8fd06217d318fa8208e11ffa5624f6be25be1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796704"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="c0fdb-103">Délégation d’éléments de travail dans un workflow</span><span class="sxs-lookup"><span data-stu-id="c0fdb-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="c0fdb-104">Délégation manuelle d’un élément de travail</span><span class="sxs-lookup"><span data-stu-id="c0fdb-104">Manually delegate a work item</span></span>

<span data-ttu-id="c0fdb-105">Pour déléguer un élément de travail individuel, sélectionnez l’option **Déléguer** dans le menu **Workflow** puis entrez l’utilisateur à qui déléguer l’élément de travail en y ajoutant un commentaire.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="c0fdb-106">Cela réaffectera l’élément de travail à cet utilisateur afin qu’il puisse l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="c0fdb-107">Délégation manuelle de plusieurs éléments de travail</span><span class="sxs-lookup"><span data-stu-id="c0fdb-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="c0fdb-108">Plusieurs éléments de travail peuvent être délégués ensemble à partir de la page **Éléments de travail qui me sont affectés**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="c0fdb-109">Les types de workflow suivants sont éligibles pour la délégation en masse : workflow d’approbation des contrats d’achat, workflow de commande fournisseur, révision de la demande d’achat et workflow de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="c0fdb-110">La fonctionnalité **Déléguer plusieurs éléments de travail** est désactivée par défaut et peut être activée dans **Espaces de travail > Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="c0fdb-111">Contactez votre administrateur système pour obtenir de l’aide pour activer cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="c0fdb-112">Allez dans **Commun > Commun > Éléments de travail > Éléments de travail qui me sont affectés**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="c0fdb-113">Sélectionnez les éléments de travail qui seront délégués.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="c0fdb-114">Cliquez sur le menu **Déléguer des éléments de travail**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="c0fdb-115">Dans le champ **Utilisateur**, sélectionnez l’utilisateur auquel déléguer les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="c0fdb-116">Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="c0fdb-117">Cliquez le bouton **Déléguer des éléments de travail** pour terminer la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="c0fdb-118">Déléguer automatiquement des éléments de travail</span><span class="sxs-lookup"><span data-stu-id="c0fdb-118">Automatically delegate work items</span></span>

<span data-ttu-id="c0fdb-119">Si vous prévoyez de vous absenter du bureau ou être indisponible d’une manière quelconque pour agir sur des éléments de travail pendant une période donnée, vous pouvez automatiquement déléguer de nouveaux éléments de travail à d’autres utilisateurs à l’aide de la page **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="c0fdb-120">Paramétrage de la délégation automatique</span><span class="sxs-lookup"><span data-stu-id="c0fdb-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="c0fdb-121">Accédez à **Commun > Paramétrage > Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="c0fdb-122">Cliquez sur **Workflow** et vérifiez que la section Délégation est développée.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="c0fdb-123">Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d’autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d’éléments de travail sont délégués.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="c0fdb-124">Pour créer une règle de délégation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0fdb-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="c0fdb-125">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-125">Click **Add**.</span></span>
4. <span data-ttu-id="c0fdb-126">Sélectionnez une option dans le champ **Étendue**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-126">In the **Scope** field, select an option:</span></span>
    - <span data-ttu-id="c0fdb-127">Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="c0fdb-128">Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="c0fdb-129">Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-129">If you select this option, you must select the type of workflow in the **Name** field.</span></span>
    - <span data-ttu-id="c0fdb-130">Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="c0fdb-131">Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-131">If you select this option, you must select the workflow in the **Name** field.</span></span>  
5. <span data-ttu-id="c0fdb-132">Dans le champ **Nom** :</span><span class="sxs-lookup"><span data-stu-id="c0fdb-132">In the **Name** field:</span></span>
    - <span data-ttu-id="c0fdb-133">Pour l’étendue **Module**, sélectionnez le module cible.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-133">For **Module** scope, select the target module.</span></span>
    - <span data-ttu-id="c0fdb-134">Pour l’étendue **Workflow**, sélectionnez le workflow cible.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-134">For **Workflow** scope, select the target workflow.</span></span>
6. <span data-ttu-id="c0fdb-135">Dans le champ **Déléguer**, sélectionnez l’utilisateur auquel déléguer les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-135">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="c0fdb-136">Utilisez les champs **Date/heure de début** et **Date/heure de fin** pour spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-136">Use the **Start date/time** and **End date/time** fields to specify when you want the work items to be automatically delegated.</span></span>  
7. <span data-ttu-id="c0fdb-137">Dans le champ **Date/heure de début**, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-137">In the **Start date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="c0fdb-138">Dans le champ **Date/heure de fin**, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-138">In the **End date/time** field, enter a date and time.</span></span>
9. <span data-ttu-id="c0fdb-139">Activez la case à cocher **Activé** pour activer la règle de délégation.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-139">Select the **Enabled** check box to activate the delegation rule.</span></span> 
10. <span data-ttu-id="c0fdb-140">Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-140">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
