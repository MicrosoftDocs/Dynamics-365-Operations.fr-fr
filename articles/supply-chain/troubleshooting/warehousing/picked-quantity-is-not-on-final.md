---
title: Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés
description: Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301303"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="cf763-103">Vous ne pouvez pas confirmer une expédition car les articles n’ont pas été retirés</span><span class="sxs-lookup"><span data-stu-id="cf763-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="cf763-104">Code d’erreur : LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="cf763-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="cf763-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="cf763-105">Symptoms</span></span>

<span data-ttu-id="cf763-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="cf763-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="cf763-107">Certains des articles nécessaires pour le chargement %1 n’ont pas encore été prélevés et ont été déplacés vers l’emplacement d’expédition final.</span><span class="sxs-lookup"><span data-stu-id="cf763-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="cf763-108">Par conséquent, vous ne pouvez pas confirmer l’expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="cf763-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="cf763-109">Cause</span><span class="sxs-lookup"><span data-stu-id="cf763-109">Cause</span></span>

<span data-ttu-id="cf763-110">Le chargement ou l’expédition ne peut pas être confirmé dans son état actuel car l’une des conditions suivantes peut exister :</span><span class="sxs-lookup"><span data-stu-id="cf763-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="cf763-111">Le travail associé n’a pas encore été sélectionné et déplacé vers le lieu d’expédition final.</span><span class="sxs-lookup"><span data-stu-id="cf763-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="cf763-112">La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="cf763-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="cf763-113">La directive d’emplacement a été configurée avec l’emplacement d’emballage comme emplacement d’expédition final lors de l’utilisation de la conteneurisation du modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="cf763-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="cf763-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="cf763-114">Resolution</span></span>

<span data-ttu-id="cf763-115">Le chargement ou l’expédition est actuellement dans un état d’échec.</span><span class="sxs-lookup"><span data-stu-id="cf763-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="cf763-116">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cf763-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="cf763-117">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="cf763-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="cf763-118">Annuler les ID de travail qui ont été créés avec l’emplacement d’emballage comme emplacement d’expédition final, reconfigurer la directive d’emplacement et relancer le chargement.</span><span class="sxs-lookup"><span data-stu-id="cf763-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="cf763-119">Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent</span><span class="sxs-lookup"><span data-stu-id="cf763-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="cf763-120">Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="cf763-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="cf763-121">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="cf763-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="cf763-122">Sélectionnez le chargement pour lequel l’expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="cf763-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="cf763-123">Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="cf763-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="cf763-124">Notez la valeur du champ **Quantité créée**.</span><span class="sxs-lookup"><span data-stu-id="cf763-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="cf763-125">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="cf763-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="cf763-126">Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="cf763-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="cf763-127">Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.</span><span class="sxs-lookup"><span data-stu-id="cf763-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="cf763-128">Annuler les ID de travail qui ont été créés avec l’emplacement d’emballage comme emplacement d’expédition final, reconfigurer la directive d’emplacement et relancer le chargement</span><span class="sxs-lookup"><span data-stu-id="cf763-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="cf763-129">Procédez comme suit pour annuler les ID de travail qui ont l’emplacement d’emballage comme emplacement final de placement avec la conteneurisation automatisée en place.</span><span class="sxs-lookup"><span data-stu-id="cf763-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="cf763-130">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="cf763-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="cf763-131">La boîte de dialogue **Annuler le travail** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="cf763-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="cf763-132">Dans le champ **ID de travail**, spécifiez l’ID du travail que vous souhaitez annuler.</span><span class="sxs-lookup"><span data-stu-id="cf763-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="cf763-133">L’ID de travail sélectionné doit avoir une valeur **Statut de travail** *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.</span><span class="sxs-lookup"><span data-stu-id="cf763-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="cf763-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf763-134">Select **OK**.</span></span>
1. <span data-ttu-id="cf763-135">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="cf763-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="cf763-136">Répétez cette procédure pour les autres ID de travail si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="cf763-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="cf763-137">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="cf763-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="cf763-138">Utilisez la procédure suivante pour reconfigurer la directive d’emplacement afin qu’elle n’utilise pas l’emplacement d’emballage comme emplacement d’expédition final lorsque la conteneurisation automatisée est configurée pour le modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="cf763-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="cf763-139">Allez dans **Gestion des entrepôts \> Paramétrage \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="cf763-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="cf763-140">Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="cf763-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="cf763-141">Sélectionnez la directive d’emplacement que vous utilisez pour la conteneurisation automatisée.</span><span class="sxs-lookup"><span data-stu-id="cf763-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="cf763-142">Dans la barre d’outils du raccourci **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="cf763-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="cf763-143">Dans la boîte de dialogue de l’éditeur de requêtes, sur l’onglet **Plange**, recherchez la ligne où **Champ** est défini sur *Profil d’emplacement*, et vérifiez que le champ **Critères** pour cette ligne n’est pas défini sur un profil d’emplacement qui a un **Type d’emplacement** défini sur *Emballage*.</span><span class="sxs-lookup"><span data-stu-id="cf763-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="cf763-144">Ajustez le champ **Critères** pour corriger l’emplacement final.</span><span class="sxs-lookup"><span data-stu-id="cf763-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="cf763-145">Utilisez la procédure suivante pour libérer le chargement et créer des ID de travail avec l’emplacement d’expédition final correct.</span><span class="sxs-lookup"><span data-stu-id="cf763-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="cf763-146">Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.</span><span class="sxs-lookup"><span data-stu-id="cf763-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="cf763-147">Dans la section **Chargements**, trouvez le chargement qui doit être libéré.</span><span class="sxs-lookup"><span data-stu-id="cf763-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="cf763-148">Dans la barre d’outils de la section **Chargements**, sélectionnez **Lancer \> Lancement dans l’entrepôt** pour lancer le chargement sélectionné dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="cf763-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="cf763-149">Répétez cette procédure pour les autres chargements si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="cf763-149">Repeat this procedure for the other loads as needed.</span></span>
