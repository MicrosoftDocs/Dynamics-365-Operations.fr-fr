---
title: La quantité physique restante dans l’unité ne doit pas être nulle
description: Lorsque vous générez un bon de livraison, les données qui lui sont fournies ont une quantité de stock non nulle mais une quantité de vente nulle.
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
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248780"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="dab4b-103">La quantité physique restante dans l’unité ne doit pas être nulle</span><span class="sxs-lookup"><span data-stu-id="dab4b-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="dab4b-104">Code d’erreur : SYS19591</span><span class="sxs-lookup"><span data-stu-id="dab4b-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="dab4b-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="dab4b-105">Symptoms</span></span>

<span data-ttu-id="dab4b-106">Lorsque vous générez un bon de livraison, les données qui lui sont fournies ont une quantité de stock non nulle mais une quantité de vente nulle.</span><span class="sxs-lookup"><span data-stu-id="dab4b-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="dab4b-107">Lorsque vous essayez de générer le bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="dab4b-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="dab4b-108">La quantité physique restante dans l’unité %1 doit être différente de zéro.</span><span class="sxs-lookup"><span data-stu-id="dab4b-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="dab4b-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="dab4b-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="dab4b-110">Cause</span><span class="sxs-lookup"><span data-stu-id="dab4b-110">Cause</span></span>

<span data-ttu-id="dab4b-111">Le système évalue la quantité physique restante dans l’unité de stock et la quantité physique restante dans l’unité d’expédition.</span><span class="sxs-lookup"><span data-stu-id="dab4b-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="dab4b-112">Si le système constate que la quantité physique restante dans l’unité d’expédition est 0 (zéro), mais que la quantité physique restante dans l’unité de stock n’est pas 0, vous ne pouvez pas générer le bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="dab4b-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="dab4b-113">Par exemple, ce problème peut se produire si l’unité de vente et l’unité de stock de l’article sont différentes, et que la conversion entre les unités n’est pas précise.</span><span class="sxs-lookup"><span data-stu-id="dab4b-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="dab4b-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="dab4b-114">Resolution</span></span>

<span data-ttu-id="dab4b-115">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="dab4b-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="dab4b-116">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="dab4b-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="dab4b-117">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="dab4b-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="dab4b-118">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="dab4b-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="dab4b-119">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.</span><span class="sxs-lookup"><span data-stu-id="dab4b-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="dab4b-120">Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente.</span><span class="sxs-lookup"><span data-stu-id="dab4b-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="dab4b-121">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent</span><span class="sxs-lookup"><span data-stu-id="dab4b-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="dab4b-122">Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="dab4b-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="dab4b-123">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="dab4b-124">Sélectionnez le chargement pour lequel l’expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="dab4b-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="dab4b-125">Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="dab4b-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="dab4b-126">Notez la valeur du champ **Quantité créée**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="dab4b-127">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="dab4b-128">Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="dab4b-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="dab4b-129">Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.</span><span class="sxs-lookup"><span data-stu-id="dab4b-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="dab4b-130">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi</span><span class="sxs-lookup"><span data-stu-id="dab4b-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="dab4b-131">Procédez comme suit pour examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi.</span><span class="sxs-lookup"><span data-stu-id="dab4b-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="dab4b-132">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="dab4b-133">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="dab4b-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="dab4b-134">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="dab4b-135">Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui dépasse la livraison excédentaire.</span><span class="sxs-lookup"><span data-stu-id="dab4b-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="dab4b-136">Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="dab4b-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="dab4b-137">Sur l’onglet  **Détails de ligne**, sélectionnez **Commande**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="dab4b-138">Définissez le champ **Quantité** sur la quantité prélevée (c’est-à-dire sur la valeur du champ **Quantité créée par le travail**), afin que la génération du bon de livraison soit possible.</span><span class="sxs-lookup"><span data-stu-id="dab4b-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="dab4b-139">Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité</span><span class="sxs-lookup"><span data-stu-id="dab4b-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="dab4b-140">Procédez comme suit pour examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.</span><span class="sxs-lookup"><span data-stu-id="dab4b-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="dab4b-141">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="dab4b-142">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="dab4b-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="dab4b-143">Dans le raccourci **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.</span><span class="sxs-lookup"><span data-stu-id="dab4b-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="dab4b-144">Notez la valeur des champs **Quantité** et **Unité**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="dab4b-145">Accédez à **Administration d’organisation \> Unités \> Unités**.</span><span class="sxs-lookup"><span data-stu-id="dab4b-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="dab4b-146">Sélectionnez l’unité pour laquelle le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="dab4b-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="dab4b-147">Ajustez la valeur du champ **Précision décimale** selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="dab4b-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="dab4b-148">Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente</span><span class="sxs-lookup"><span data-stu-id="dab4b-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="dab4b-149">Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente.</span><span class="sxs-lookup"><span data-stu-id="dab4b-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="dab4b-150">Envisagez de reconfigurer l’unité de mesure de l’article selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="dab4b-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
