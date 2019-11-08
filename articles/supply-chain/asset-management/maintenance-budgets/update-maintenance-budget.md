---
title: Mettre à jour les budgets de maintenance
description: Cette rubrique explique comment mettre à jour un budget de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f3b771319eeb602a371500fdc69c68f88afe341
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571735"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="6c9e9-103">Mettre à jour les budgets de maintenance</span><span class="sxs-lookup"><span data-stu-id="6c9e9-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="6c9e9-104">La page **Lignes du budget de maintenance** présente toutes les lignes du budget créées pour le budget sélectionné sur la page **Budgets de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="6c9e9-105">(Pour plus d'informations, voir [Créer des budgets de maintenance](create-maintenance-budget.md).) Vous pouvez recalculer et ajuster les lignes du budget de maintenance jusqu'à ce que le budget de maintenance soit approuvé.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="6c9e9-106">Une fois la période du budget écoulée, et si les coûts ont été validés dans le module Gestion des actifs, vous pouvez également mettre à jour les lignes du budget avec les coûts réels.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="6c9e9-107">Recalculer un budget de maintenance</span><span class="sxs-lookup"><span data-stu-id="6c9e9-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="6c9e9-108">Vous pouvez recalculer un budget de maintenance sur la page **Lignes du budget de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="6c9e9-109">Lorsque vous recalculez un budget de maintenance, les lignes de budget existantes sont supprimées et un nouveau calcul est effectué.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="6c9e9-110">Sur la page **Lignes du budget de maintenance**, sélectionnez **Recalculer**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="6c9e9-111">Dans la boîte de dialogue **Recalculer le budget**, apportez les modifications requises pour le recalcul, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="6c9e9-112">De nouvelles lignes budgétaires sont créées conformément aux valeurs définies.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="6c9e9-113">Ajuster les lignes budgétaires</span><span class="sxs-lookup"><span data-stu-id="6c9e9-113">Adjust budget lines</span></span>

<span data-ttu-id="6c9e9-114">Plutôt que de recalculer l'intégralité du budget de maintenance, vous pouvez ajuster les lignes sélectionnées associées aux coûts budgétaires.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="6c9e9-115">Sur la page **Lignes du budget de maintenance**, sélectionnez les lignes pour mettre à jour le coût budgétaire.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="6c9e9-116">Sélectionnez **Ajuster**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="6c9e9-117">Pour ajouter un montant sur les lignes sélectionnées, activez la case à cocher **Ajouter le coût**, puis entrez la valeur dans le champ **Ajouter une valeur**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="6c9e9-118">Pour multiplier le coût budgétaire sur les lignes de budget sélectionnées par un facteur, activez la case à cocher **Multiplier le coût**, puis entrez le facteur dans le champ **Multiplier la valeur**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="6c9e9-119">Par exemple, si vous entrez **1,2** dans le champ **Multiplier la valeur**, vous augmentez le coût budgétaire sur les lignes sélectionnées par 20 %.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="6c9e9-120">Si vous entrez **0,7**, vous diminuez le coût budgétaire sur les lignes sélectionnées de 30 %.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="6c9e9-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-121">Select **OK**.</span></span>

<span data-ttu-id="6c9e9-122">Les lignes de budget sélectionnées sont mises à jour selon les valeurs que vous définissez à l'étape 3 ou 4.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="6c9e9-123">Mettre à jour les coûts réels</span><span class="sxs-lookup"><span data-stu-id="6c9e9-123">Update actual costs</span></span>

<span data-ttu-id="6c9e9-124">Une fois les dates des lignes budgétaires écoulées, et les coûts réels validés dans le module Gestion des actifs, vous pouvez mettre à jour les coûts réels sur le budget de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="6c9e9-125">Sur la page **Lignes du budget de maintenance**, sélectionnez **Mettre à jour le coût**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="6c9e9-126">Dans la boîte de dialogue **Calculer le coût réel**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="6c9e9-127">Les champs **Coût réel** sur les lignes du budget sont mis à jour si les coûts réels ont été validés.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="6c9e9-128">De nouvelles lignes budgétaires peuvent être générées si les nouveaux types d'actifs ont été créés depuis que vous avez créé le budget et si ces types d'actif ont été utilisés sur les actifs pour lesquels les ordres de travail ont été créés et pour lesquels les coûts associés ont été validés.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="6c9e9-129">Les nouvelles lignes budgétaires affichent uniquement les coûts réels, car aucun coût budgétaire n'a été calculé pour elles.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="6c9e9-130">Pour afficher une vue d'ensemble des coûts réels répartis en coûts préventifs, correctifs et d'investissement, vous pouvez effectuer un calcul pour la même période sur la page **Contrôle des coûts d'actifs**.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="6c9e9-131">Ajouter manuellement des lignes budgétaires</span><span class="sxs-lookup"><span data-stu-id="6c9e9-131">Manually add budget lines</span></span>

<span data-ttu-id="6c9e9-132">Sur la page **Lignes du budget de maintenance**, vous pouvez ajouter manuellement une nouvelle ligne de budget en sélectionnant **Nouveau**, puis en faisant des sélections sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="6c9e9-133">Voici quelques exemples de situations où cette approche peut être utile :</span><span class="sxs-lookup"><span data-stu-id="6c9e9-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="6c9e9-134">Vous savez que le reconditionnement de certains actifs est actuellement en phase de planification, mais les tâches associées n'ont pas encore été créées dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="6c9e9-135">Toutefois, vous souhaitez que les coûts budgétaires pour ces tâches sont incluses dans le budget de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="6c9e9-136">De nouveaux actifs ou types d'actifs ont été créés depuis la réalisation du budget de maintenance, mais les plans de maintenance n'ont pas encore été configurés sur ces actifs ou types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="6c9e9-137">Toutefois, vous souhaitez que les coûts budgétaires pour ces types d'actifs sont incluses dans le budget de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6c9e9-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>
