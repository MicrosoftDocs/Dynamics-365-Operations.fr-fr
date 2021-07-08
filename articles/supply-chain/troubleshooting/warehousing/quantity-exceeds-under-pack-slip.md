---
title: La quantité dépasse le pourcentage de sous-livraison lors de la génération du bon de livraison
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de sous-livraison.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249098"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="268d9-103">La quantité dépasse le pourcentage de sous-livraison lors de la génération du bon de livraison</span><span class="sxs-lookup"><span data-stu-id="268d9-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="268d9-104">Code d’erreur : SYS24921</span><span class="sxs-lookup"><span data-stu-id="268d9-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="268d9-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="268d9-105">Symptoms</span></span>

<span data-ttu-id="268d9-106">Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de sous-livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="268d9-107">Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="268d9-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="268d9-108">La livraison incomplète de la ligne est de %1 %, mais celle autorisée n’est que de %2 %.</span><span class="sxs-lookup"><span data-stu-id="268d9-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="268d9-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="268d9-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="268d9-110">Cause</span><span class="sxs-lookup"><span data-stu-id="268d9-110">Cause</span></span>

<span data-ttu-id="268d9-111">La quantité prélevée pour le chargement ou l’expédition est inférieure à la quantité commandée et n’est pas comprise dans la plage du pourcentage de sous-livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="268d9-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="268d9-112">Resolution</span></span>

<span data-ttu-id="268d9-113">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="268d9-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="268d9-114">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="268d9-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="268d9-115">Ajuster le pourcentage de sous-livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="268d9-116">Annuler et effectuer des ajustements.</span><span class="sxs-lookup"><span data-stu-id="268d9-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="268d9-117">Ajuster le pourcentage de sous-livraison</span><span class="sxs-lookup"><span data-stu-id="268d9-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="268d9-118">Suivez la procédure suivante pour ajuster le pourcentage de sous-livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="268d9-119">Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.</span><span class="sxs-lookup"><span data-stu-id="268d9-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="268d9-120">Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="268d9-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="268d9-121">Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client de l’article qui dépasse le pourcentage de sous-livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="268d9-122">Sur l’onglet  **Détails de ligne**, sélectionnez **Livraison**.</span><span class="sxs-lookup"><span data-stu-id="268d9-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="268d9-123">Définissez le champ **Sous-livraison** sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la génération du bon de livraison soit possible.</span><span class="sxs-lookup"><span data-stu-id="268d9-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="268d9-124">Annuler et effectuer des ajustements</span><span class="sxs-lookup"><span data-stu-id="268d9-124">Reverse and make adjustments</span></span>

<span data-ttu-id="268d9-125">Annulez tout ce qui a été validé pour le chargement (par exemple, le bon de livraison, la confirmation d’expédition et le travail), effectuez des ajustements de la commande client, relancez la commande vers l’entrepôt et terminez la procédure d’expédition.</span><span class="sxs-lookup"><span data-stu-id="268d9-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="268d9-126">Utilisez la procédure suivante pour annuler un bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="268d9-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="268d9-127">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="268d9-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="268d9-128">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler les bons de livraison**.</span><span class="sxs-lookup"><span data-stu-id="268d9-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="268d9-129">Utilisez la procédure suivante pour annuler une confirmation d’expédition.</span><span class="sxs-lookup"><span data-stu-id="268d9-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="268d9-130">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="268d9-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="268d9-131">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="268d9-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="268d9-132">Utilisez la procédure suivante pour annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="268d9-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="268d9-133">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="268d9-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="268d9-134">Dans le volet Actions, sous l’onglet  **Chargements**, dans le groupe  **Travail**, sélectionnez  **Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="268d9-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
