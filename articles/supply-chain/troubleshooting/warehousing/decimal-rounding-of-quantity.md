---
title: L’arrondi décimal de la quantité physique de mise à jour est incorrect
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui ne correspond pas à la précision décimale définie dans l’unité.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248781"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="551b0-103">L’arrondi décimal de la quantité physique de mise à jour est incorrect</span><span class="sxs-lookup"><span data-stu-id="551b0-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="551b0-104">Code d’erreur : SYS19589</span><span class="sxs-lookup"><span data-stu-id="551b0-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="551b0-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="551b0-105">Symptoms</span></span>

<span data-ttu-id="551b0-106">Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui ne correspond pas à la précision décimale définie dans l’unité.</span><span class="sxs-lookup"><span data-stu-id="551b0-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="551b0-107">Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="551b0-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="551b0-108">L’arrondi décimal de la quantité de mise à jour physique de l’unité %1 est incorrect.</span><span class="sxs-lookup"><span data-stu-id="551b0-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="551b0-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="551b0-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="551b0-110">Cause</span><span class="sxs-lookup"><span data-stu-id="551b0-110">Cause</span></span>

<span data-ttu-id="551b0-111">Le système évalue si l’arrondi décimal de la quantité d’expédition correspond à la précision décimale définie pour l’unité d’expédition.</span><span class="sxs-lookup"><span data-stu-id="551b0-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="551b0-112">Lorsque le système arrondit la quantité d’expédition au nombre de décimales spécifié, s’il constate que la quantité d’expédition arrondie ne correspond pas à la quantité d’expédition réelle, vous ne pouvez pas générer le bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="551b0-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="551b0-113">Par exemple, ce problème peut se produire si la quantité vendue est de 1,75 kilogramme (kg), mais que la précision décimale est définie sur *1*.</span><span class="sxs-lookup"><span data-stu-id="551b0-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="551b0-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="551b0-114">Resolution</span></span>

<span data-ttu-id="551b0-115">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="551b0-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="551b0-116">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="551b0-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="551b0-117">Passez en revue vos lignes de chargement et effectuez des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="551b0-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="551b0-118">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.</span><span class="sxs-lookup"><span data-stu-id="551b0-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="551b0-119">Passer en revue vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi</span><span class="sxs-lookup"><span data-stu-id="551b0-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="551b0-120">Suivez la procédure suivante pour passer en revue vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="551b0-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="551b0-121">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="551b0-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="551b0-122">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="551b0-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="551b0-123">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="551b0-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="551b0-124">Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.</span><span class="sxs-lookup"><span data-stu-id="551b0-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="551b0-125">Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="551b0-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="551b0-126">Sur l’onglet  **Détails de ligne**, sélectionnez **Commande**.</span><span class="sxs-lookup"><span data-stu-id="551b0-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="551b0-127">Définissez le champ **Quantité** sur la quantité prélevée (c’est-à-dire sur la valeur du champ **Quantité créée par le travail**), afin que la génération du bon de livraison soit possible.</span><span class="sxs-lookup"><span data-stu-id="551b0-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="551b0-128">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité</span><span class="sxs-lookup"><span data-stu-id="551b0-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="551b0-129">Procédez comme suit pour examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.</span><span class="sxs-lookup"><span data-stu-id="551b0-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="551b0-130">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="551b0-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="551b0-131">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="551b0-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="551b0-132">Dans le raccourci **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.</span><span class="sxs-lookup"><span data-stu-id="551b0-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="551b0-133">Notez la valeur des champs **Quantité** et **Unité**.</span><span class="sxs-lookup"><span data-stu-id="551b0-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="551b0-134">Accédez à **Administration d’organisation \> Unités \> Unités**.</span><span class="sxs-lookup"><span data-stu-id="551b0-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="551b0-135">Sélectionnez l’unité pour laquelle le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="551b0-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="551b0-136">Ajustez la valeur du champ **Précision décimale** selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="551b0-136">Adjust the value of the **Decimal precision** field as required.</span></span>
