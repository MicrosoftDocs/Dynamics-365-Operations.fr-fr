---
title: La quantité dépasse le pourcentage de livraison excédentaire lors de la génération du bon de livraison
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de livraison excédentaire.
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
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249100"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="0e831-103">La quantité dépasse le pourcentage de livraison excédentaire lors de la génération du bon de livraison</span><span class="sxs-lookup"><span data-stu-id="0e831-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="0e831-104">Code d’erreur : SYS24920</span><span class="sxs-lookup"><span data-stu-id="0e831-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="0e831-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="0e831-105">Symptoms</span></span>

<span data-ttu-id="0e831-106">Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="0e831-107">Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="0e831-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="0e831-108">La livraison excessive de la ligne est de %1 %, mais celle autorisée n’est que de %2 %.</span><span class="sxs-lookup"><span data-stu-id="0e831-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="0e831-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="0e831-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="0e831-110">Cause</span><span class="sxs-lookup"><span data-stu-id="0e831-110">Cause</span></span>

<span data-ttu-id="0e831-111">La quantité prélevée pour le chargement ou l’expédition est supérieure à la quantité commandée et n’est pas comprise dans la plage du pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="0e831-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="0e831-112">Resolution</span></span>

<span data-ttu-id="0e831-113">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="0e831-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="0e831-114">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e831-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="0e831-115">Ajustez la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="0e831-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="0e831-116">Ajustez le pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="0e831-117">Annuler et effectuer des ajustements.</span><span class="sxs-lookup"><span data-stu-id="0e831-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="0e831-118">Ajuster la quantité de la ligne de chargement</span><span class="sxs-lookup"><span data-stu-id="0e831-118">Adjust the load line quantity</span></span>

<span data-ttu-id="0e831-119">Suivez la procédure suivante pour ajuster la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="0e831-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="0e831-120">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="0e831-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0e831-121">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="0e831-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="0e831-122">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="0e831-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="0e831-123">Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui dépasse le pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="0e831-124">Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="0e831-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="0e831-125">Sur l’onglet  **Détails de ligne**, sélectionnez **Commande**.</span><span class="sxs-lookup"><span data-stu-id="0e831-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="0e831-126">Définissez le champ **Quantité** sur la quantité prélevée (c’est-à-dire sur la valeur du champ **Quantité créée par le travail**), afin que la génération du bon de livraison soit possible.</span><span class="sxs-lookup"><span data-stu-id="0e831-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="0e831-127">Ajuster le pourcentage de livraison excédentaire</span><span class="sxs-lookup"><span data-stu-id="0e831-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="0e831-128">Suivez la procédure suivante pour ajuster le pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="0e831-129">Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.</span><span class="sxs-lookup"><span data-stu-id="0e831-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="0e831-130">Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="0e831-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="0e831-131">Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client de l’article qui dépasse le pourcentage de livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="0e831-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="0e831-132">Sur l’onglet  **Détails de ligne**, sélectionnez **Livraison**.</span><span class="sxs-lookup"><span data-stu-id="0e831-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="0e831-133">Définissez le champ **Livraison excédentaire** sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la génération du bon de livraison soit possible.</span><span class="sxs-lookup"><span data-stu-id="0e831-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="0e831-134">Annuler et effectuer des ajustements</span><span class="sxs-lookup"><span data-stu-id="0e831-134">Reverse and make adjustments</span></span>

<span data-ttu-id="0e831-135">Annulez tout ce qui a été validé pour le chargement (par exemple, le bon de livraison, la confirmation d’expédition et le travail), effectuez des ajustements de la commande client, relancez la commande vers l’entrepôt et terminez la procédure d’expédition.</span><span class="sxs-lookup"><span data-stu-id="0e831-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="0e831-136">Utilisez la procédure suivante pour annuler un bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="0e831-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="0e831-137">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="0e831-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0e831-138">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler les bons de livraison**.</span><span class="sxs-lookup"><span data-stu-id="0e831-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="0e831-139">Utilisez la procédure suivante pour annuler une confirmation d’expédition.</span><span class="sxs-lookup"><span data-stu-id="0e831-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="0e831-140">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="0e831-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0e831-141">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="0e831-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="0e831-142">Utilisez la procédure suivante pour annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="0e831-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="0e831-143">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="0e831-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0e831-144">Dans le volet Actions, sous l’onglet  **Chargements**, dans le groupe  **Travail**, sélectionnez  **Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="0e831-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
