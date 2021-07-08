---
title: La quantité prélevée n’est pas suffisante lors de la génération du bon de livraison
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité prélevée qui ne correspond pas à la quantité créée par le travail sur la ligne de chargement.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249102"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="d047e-103">La quantité prélevée n’est pas suffisante lors de la génération du bon de livraison</span><span class="sxs-lookup"><span data-stu-id="d047e-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="d047e-104">Code d’erreur : SYS54073</span><span class="sxs-lookup"><span data-stu-id="d047e-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="d047e-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="d047e-105">Symptoms</span></span>

<span data-ttu-id="d047e-106">Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité prélevée qui ne correspond pas à la quantité créée par le travail sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="d047e-107">Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="d047e-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="d047e-108">Comme %1 ont été prélevés, impossible de mettre à jour %2, le solde devant être égal à %3.</span><span class="sxs-lookup"><span data-stu-id="d047e-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="d047e-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="d047e-110">Cause</span><span class="sxs-lookup"><span data-stu-id="d047e-110">Cause</span></span>

<span data-ttu-id="d047e-111">Le bon de livraison ne peut pas être généré dans son état actuel car l’une des conditions suivantes peut exister :</span><span class="sxs-lookup"><span data-stu-id="d047e-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="d047e-112">Le travail associé n’a pas encore été sélectionné et déplacé vers le lieu d’expédition final.</span><span class="sxs-lookup"><span data-stu-id="d047e-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="d047e-113">La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="d047e-114">La quantité de la ligne de chargement, la quantité créée par le travail et la quantité prélevée ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="d047e-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="d047e-115">Résolution</span><span class="sxs-lookup"><span data-stu-id="d047e-115">Resolution</span></span>

<span data-ttu-id="d047e-116">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="d047e-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="d047e-117">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d047e-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="d047e-118">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="d047e-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="d047e-119">Ajustez la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="d047e-120">Annulez tous les enregistrements de prélèvement et refaites le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="d047e-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="d047e-121">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent</span><span class="sxs-lookup"><span data-stu-id="d047e-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="d047e-122">Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="d047e-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="d047e-123">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="d047e-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="d047e-124">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="d047e-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="d047e-125">Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="d047e-126">Notez la valeur du champ **Quantité créée**.</span><span class="sxs-lookup"><span data-stu-id="d047e-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="d047e-127">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="d047e-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="d047e-128">Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="d047e-129">Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.</span><span class="sxs-lookup"><span data-stu-id="d047e-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="d047e-130">Ajuster la quantité de la ligne de chargement</span><span class="sxs-lookup"><span data-stu-id="d047e-130">Adjust the load line quantity</span></span>

<span data-ttu-id="d047e-131">Suivez la procédure suivante pour ajuster la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="d047e-132">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="d047e-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="d047e-133">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="d047e-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="d047e-134">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="d047e-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="d047e-135">Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.</span><span class="sxs-lookup"><span data-stu-id="d047e-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="d047e-136">Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="d047e-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="d047e-137">Définissez le champ **Réduire la ligne de chargement** de manière à refléter les ajustements sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="d047e-138">Annuler tous les enregistrements de prélèvement et refaire le prélèvement</span><span class="sxs-lookup"><span data-stu-id="d047e-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="d047e-139">Le problème peut se produire parce que quelqu’un a utilisé l’enregistrement du prélèvement pour fermer une ligne de chargement sans travail.</span><span class="sxs-lookup"><span data-stu-id="d047e-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="d047e-140">Dans ce cas, l’enregistrement manuel du prélèvement doit être annulé et le prélèvement doit ensuite être effectué à l’aide de l’application mobile Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="d047e-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="d047e-141">Utilisez la procédure suivante pour annuler l’enregistrement du prélèvement.</span><span class="sxs-lookup"><span data-stu-id="d047e-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="d047e-142">Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.</span><span class="sxs-lookup"><span data-stu-id="d047e-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="d047e-143">Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="d047e-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="d047e-144">Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client pour laquelle l’enregistrement du prélèvement a été effectué.</span><span class="sxs-lookup"><span data-stu-id="d047e-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="d047e-145">Sélectionnez **Mettre à jour la ligne \> Prélever** pour annuler le prélèvement des articles.</span><span class="sxs-lookup"><span data-stu-id="d047e-145">Select **Update line \> Pick** to unpick the items.</span></span>
