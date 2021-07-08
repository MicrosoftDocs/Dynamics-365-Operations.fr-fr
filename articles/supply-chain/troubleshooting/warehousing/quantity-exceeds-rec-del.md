---
title: La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée.
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse la quantité de travail qui a été prélevée et réservée pour la commande client.
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
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249103"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="6ec26-103">La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée</span><span class="sxs-lookup"><span data-stu-id="6ec26-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="6ec26-104">Code d’erreur : SYS7676</span><span class="sxs-lookup"><span data-stu-id="6ec26-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="6ec26-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="6ec26-105">Symptoms</span></span>

<span data-ttu-id="6ec26-106">Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse la quantité de travail qui a été prélevée et réservée pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="6ec26-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="6ec26-107">Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="6ec26-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="6ec26-108">La quantité que vous essayez de mettre à jour dépasse la quantité reçue/livrée.</span><span class="sxs-lookup"><span data-stu-id="6ec26-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="6ec26-109">Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="6ec26-110">Cause</span><span class="sxs-lookup"><span data-stu-id="6ec26-110">Cause</span></span>

<span data-ttu-id="6ec26-111">La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="6ec26-112">Par exemple, ce problème peut se produire si la quantité de la ligne de chargement, la quantité créée par le travail ou la quantité prélevée n’est pas précise.</span><span class="sxs-lookup"><span data-stu-id="6ec26-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="6ec26-113">Résolution</span><span class="sxs-lookup"><span data-stu-id="6ec26-113">Resolution</span></span>

<span data-ttu-id="6ec26-114">Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue.</span><span class="sxs-lookup"><span data-stu-id="6ec26-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="6ec26-115">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="6ec26-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="6ec26-116">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="6ec26-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="6ec26-117">Ajustez la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="6ec26-118">Annulez tous les enregistrements de prélèvement et refaites le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="6ec26-119">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent</span><span class="sxs-lookup"><span data-stu-id="6ec26-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="6ec26-120">Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="6ec26-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="6ec26-121">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="6ec26-122">Sélectionnez le chargement pour lequel l’expédition ne peut pas être générée.</span><span class="sxs-lookup"><span data-stu-id="6ec26-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="6ec26-123">Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="6ec26-124">Notez la valeur du champ **Quantité créée**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="6ec26-125">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="6ec26-126">Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="6ec26-127">Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.</span><span class="sxs-lookup"><span data-stu-id="6ec26-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="6ec26-128">Ajuster la quantité de la ligne de chargement</span><span class="sxs-lookup"><span data-stu-id="6ec26-128">Adjust the load line quantity</span></span>

<span data-ttu-id="6ec26-129">Suivez la procédure suivante pour ajuster la quantité de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="6ec26-130">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="6ec26-131">Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.</span><span class="sxs-lookup"><span data-stu-id="6ec26-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="6ec26-132">Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="6ec26-133">Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.</span><span class="sxs-lookup"><span data-stu-id="6ec26-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="6ec26-134">Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="6ec26-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="6ec26-135">Définissez le champ **Réduire la ligne de chargement** de manière à refléter les ajustements sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="6ec26-136">Annuler tous les enregistrements de prélèvement et refaire le prélèvement</span><span class="sxs-lookup"><span data-stu-id="6ec26-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="6ec26-137">Si quelqu’un a utilisé l’enregistrement de prélèvement pour fermer une ligne de chargement sans travail, un écart peut se produire entre la quantité de la ligne de chargement et la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="6ec26-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="6ec26-138">Dans ce cas, l’enregistrement manuel du prélèvement doit être annulé et le prélèvement doit ensuite être effectué à l’aide de l’application mobile Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="6ec26-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="6ec26-139">Utilisez la procédure suivante pour annuler l’enregistrement du prélèvement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="6ec26-140">Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.</span><span class="sxs-lookup"><span data-stu-id="6ec26-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="6ec26-141">Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="6ec26-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="6ec26-142">Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client pour laquelle l’enregistrement du prélèvement a été effectué.</span><span class="sxs-lookup"><span data-stu-id="6ec26-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="6ec26-143">Sélectionnez **Mettre à jour la ligne \> Prélever** pour annuler le prélèvement des articles.</span><span class="sxs-lookup"><span data-stu-id="6ec26-143">Select **Update line \> Pick** to unpick the items.</span></span>
