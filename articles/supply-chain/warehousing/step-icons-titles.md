---
title: Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management
description: Cette rubrique décrit comment affecter des icônes et des titres d’étape pour les flux de tâches nouveaux ou personnalisés pour l’application mobile Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049362"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="74d25-103">Affecter des icônes et des titres d’étape pour l’application mobile Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="74d25-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74d25-104">Cette rubrique décrit comment affecter des icônes d’étape et des titres d’étape pour les flux de tâches nouveaux ou personnalisés pour l’application mobile Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="74d25-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="74d25-105">Les illustrations suivantes montrent comment les icônes et les titres d’étape apparaissent dans l’application mobile Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="74d25-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="74d25-106">![Exemple d’une icône d’étape et d’un titre d’étape dans l’application mobile Warehouse Management](media/step-icon-example.png "Exemple d’une icône d’étape et d’un titre d’étape dans l’application mobile Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="74d25-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="74d25-107">Activer cette fonctionnalité dans votre système</span><span class="sxs-lookup"><span data-stu-id="74d25-107">Turn on this feature in your system</span></span>

<span data-ttu-id="74d25-108">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="74d25-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="74d25-109">Les administrateurs peuvent utiliser les paramètres de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="74d25-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="74d25-110">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="74d25-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="74d25-111">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="74d25-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="74d25-112">**Nom de la fonctionnalité :** *Paramètres utilisateur, icônes et titres des étapes de la nouvelle application d’entrepôt*</span><span class="sxs-lookup"><span data-stu-id="74d25-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="74d25-113">ID, classes et icônes d’étape standard</span><span class="sxs-lookup"><span data-stu-id="74d25-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="74d25-114">Chaque étape d’un flux de tâches est identifiée par un ID d’étape, et chaque ID d’étape a une classe d’étape correspondante.</span><span class="sxs-lookup"><span data-stu-id="74d25-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="74d25-115">L’icône et le titre de l’étape sont spécifiés dans chaque classe d’étape.</span><span class="sxs-lookup"><span data-stu-id="74d25-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="74d25-116">ID d’étape et classes d’étape</span><span class="sxs-lookup"><span data-stu-id="74d25-116">Step IDs and step classes</span></span>

<span data-ttu-id="74d25-117">Le tableau suivant répertorie chaque ID d’étape actuellement disponible et sa classe d’étape correspondante.</span><span class="sxs-lookup"><span data-stu-id="74d25-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="74d25-118">Le nom de contrôle du champ de saisie principal est utilisé comme ID d’étape.</span><span class="sxs-lookup"><span data-stu-id="74d25-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="74d25-119">Pour obtenir un exemple qui montre comment ces ID et classes d’étape sont utilisés, consultez l’implémentation de la méthode `WHSMobileAppStepInfoBuilder.stepId()` dans la section [Exemple : affecter des icônes et des titres d’étape pour un flux personnalisé](#example) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="74d25-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="74d25-120">ID d’étape</span><span class="sxs-lookup"><span data-stu-id="74d25-120">Step ID</span></span> | <span data-ttu-id="74d25-121">Classe d’étape</span><span class="sxs-lookup"><span data-stu-id="74d25-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="74d25-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-122">BatchDisposition</span></span> | <span data-ttu-id="74d25-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="74d25-124">Transporteur</span><span class="sxs-lookup"><span data-stu-id="74d25-124">Carrier</span></span> | <span data-ttu-id="74d25-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="74d25-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="74d25-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-126">CatchWeight</span></span> | <span data-ttu-id="74d25-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="74d25-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="74d25-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="74d25-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="74d25-130">CatchWeightTag</span></span> | <span data-ttu-id="74d25-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="74d25-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="74d25-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="74d25-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="74d25-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="74d25-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="74d25-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="74d25-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="74d25-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="74d25-136">CheckDigit</span></span> | <span data-ttu-id="74d25-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="74d25-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="74d25-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-138">ClusterId</span></span> | <span data-ttu-id="74d25-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="74d25-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="74d25-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="74d25-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="74d25-142">ClusterPosition</span></span> | <span data-ttu-id="74d25-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="74d25-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="74d25-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="74d25-144">ConfigId</span></span> | <span data-ttu-id="74d25-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="74d25-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="74d25-146">Confirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-146">Confirmation</span></span> | <span data-ttu-id="74d25-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="74d25-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="74d25-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="74d25-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="74d25-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="74d25-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="74d25-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="74d25-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="74d25-154">ContainerType</span></span> | <span data-ttu-id="74d25-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="74d25-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="74d25-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="74d25-156">CountingReasonCode</span></span> | <span data-ttu-id="74d25-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="74d25-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="74d25-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="74d25-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="74d25-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="74d25-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="74d25-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="74d25-160">CycleCountQty1</span></span> | <span data-ttu-id="74d25-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="74d25-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="74d25-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="74d25-162">CycleCountQty2</span></span> | <span data-ttu-id="74d25-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="74d25-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="74d25-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="74d25-164">CycleCountQty3</span></span> | <span data-ttu-id="74d25-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="74d25-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="74d25-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="74d25-166">CycleCountQty4</span></span> | <span data-ttu-id="74d25-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="74d25-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="74d25-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="74d25-168">Disposition</span></span> | <span data-ttu-id="74d25-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="74d25-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="74d25-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="74d25-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="74d25-172">DriverCheckInId</span></span> | <span data-ttu-id="74d25-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="74d25-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="74d25-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="74d25-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="74d25-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="74d25-176">DriverCheckOutId</span></span> | <span data-ttu-id="74d25-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="74d25-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="74d25-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="74d25-178">ExpDate</span></span> | <span data-ttu-id="74d25-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="74d25-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="74d25-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-180">FromBatchDisposition</span></span> | <span data-ttu-id="74d25-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="74d25-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="74d25-182">FromInventoryStatus</span></span> | <span data-ttu-id="74d25-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="74d25-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="74d25-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="74d25-184">FullQty</span></span> | <span data-ttu-id="74d25-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="74d25-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="74d25-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="74d25-186">InboundPut</span></span> | <span data-ttu-id="74d25-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="74d25-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="74d25-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="74d25-188">InventBatchId</span></span> | <span data-ttu-id="74d25-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="74d25-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="74d25-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="74d25-190">InventColorId</span></span> | <span data-ttu-id="74d25-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="74d25-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="74d25-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-192">InventLocation</span></span> | <span data-ttu-id="74d25-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="74d25-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-194">InventLocationId</span></span> | <span data-ttu-id="74d25-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="74d25-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="74d25-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="74d25-196">InventSerialId</span></span> | <span data-ttu-id="74d25-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="74d25-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="74d25-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="74d25-198">InventSizeId</span></span> | <span data-ttu-id="74d25-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="74d25-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="74d25-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="74d25-200">InventStatusId</span></span> | <span data-ttu-id="74d25-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="74d25-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="74d25-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="74d25-202">InventStyleId</span></span> | <span data-ttu-id="74d25-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="74d25-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="74d25-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="74d25-204">InventVersionId</span></span> | <span data-ttu-id="74d25-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="74d25-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="74d25-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="74d25-206">ItemId</span></span> | <span data-ttu-id="74d25-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="74d25-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="74d25-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="74d25-208">ITMContainerID</span></span> | <span data-ttu-id="74d25-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="74d25-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="74d25-210">ITMShipmentID</span></span> | <span data-ttu-id="74d25-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="74d25-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="74d25-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="74d25-212">KanbanCardId</span></span> | <span data-ttu-id="74d25-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="74d25-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="74d25-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="74d25-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="74d25-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="74d25-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="74d25-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="74d25-216">KanbanOrCardId</span></span> | <span data-ttu-id="74d25-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="74d25-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="74d25-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-218">LicensePlateId</span></span> | <span data-ttu-id="74d25-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="74d25-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="74d25-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-220">LoadId</span></span> | <span data-ttu-id="74d25-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="74d25-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="74d25-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="74d25-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="74d25-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="74d25-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-224">LocOrLP</span></span> | <span data-ttu-id="74d25-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="74d25-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="74d25-226">LocOrLP_From</span></span> | <span data-ttu-id="74d25-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="74d25-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="74d25-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="74d25-228">LocOrLP_To</span></span> | <span data-ttu-id="74d25-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="74d25-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="74d25-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="74d25-230">LocOrLPCheck</span></span> | <span data-ttu-id="74d25-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="74d25-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="74d25-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-232">LocVerification</span></span> | <span data-ttu-id="74d25-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="74d25-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="74d25-234">LPAdjustIn</span></span> | <span data-ttu-id="74d25-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="74d25-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="74d25-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="74d25-236">LPBreakChildLP</span></span> | <span data-ttu-id="74d25-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="74d25-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="74d25-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-238">LPBreakParentLP</span></span> | <span data-ttu-id="74d25-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="74d25-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="74d25-240">LPBuildChildLP</span></span> | <span data-ttu-id="74d25-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="74d25-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="74d25-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-242">LPBuildParentLP</span></span> | <span data-ttu-id="74d25-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="74d25-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-244">LPVerification</span></span> | <span data-ttu-id="74d25-245">WHSMobileAppStepLPVérification</span><span class="sxs-lookup"><span data-stu-id="74d25-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="74d25-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-246">MergeContainerId</span></span> | <span data-ttu-id="74d25-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="74d25-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-248">MixedLPLineNum</span></span> | <span data-ttu-id="74d25-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="74d25-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="74d25-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="74d25-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="74d25-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="74d25-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="74d25-252">MovementConfirmCancel</span></span> | <span data-ttu-id="74d25-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="74d25-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="74d25-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-254">NewCaptureWeight</span></span> | <span data-ttu-id="74d25-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="74d25-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="74d25-256">NewQty</span></span> | <span data-ttu-id="74d25-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="74d25-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="74d25-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="74d25-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="74d25-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="74d25-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="74d25-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="74d25-260">OutboundPut</span></span> | <span data-ttu-id="74d25-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="74d25-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="74d25-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-262">OutboundWeight</span></span> | <span data-ttu-id="74d25-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="74d25-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-264">OverridePutNewLocation</span></span> | <span data-ttu-id="74d25-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="74d25-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="74d25-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="74d25-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-268">POLineNum</span></span> | <span data-ttu-id="74d25-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="74d25-270">N° commande</span><span class="sxs-lookup"><span data-stu-id="74d25-270">PONum</span></span> | <span data-ttu-id="74d25-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="74d25-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="74d25-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="74d25-272">PositionFull</span></span> | <span data-ttu-id="74d25-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="74d25-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="74d25-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="74d25-274">PositionFullQty</span></span> | <span data-ttu-id="74d25-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="74d25-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="74d25-276">Concentration</span><span class="sxs-lookup"><span data-stu-id="74d25-276">Potency</span></span> | <span data-ttu-id="74d25-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="74d25-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="74d25-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="74d25-278">PrinterName</span></span> | <span data-ttu-id="74d25-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="74d25-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="74d25-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="74d25-280">ProdId</span></span> | <span data-ttu-id="74d25-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="74d25-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="74d25-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="74d25-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="74d25-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-284">ProductConfirmation</span></span> | <span data-ttu-id="74d25-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="74d25-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="74d25-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="74d25-288">Placer</span><span class="sxs-lookup"><span data-stu-id="74d25-288">Put</span></span> | <span data-ttu-id="74d25-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="74d25-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="74d25-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-290">PutawayClusterId</span></span> | <span data-ttu-id="74d25-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="74d25-292">Qté</span><span class="sxs-lookup"><span data-stu-id="74d25-292">Qty</span></span> | <span data-ttu-id="74d25-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="74d25-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="74d25-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="74d25-294">QtyAdjust</span></span> | <span data-ttu-id="74d25-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="74d25-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="74d25-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="74d25-296">QtyShort</span></span> | <span data-ttu-id="74d25-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="74d25-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="74d25-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-298">QtyToConsume</span></span> | <span data-ttu-id="74d25-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="74d25-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="74d25-300">QtyToPick</span></span> | <span data-ttu-id="74d25-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="74d25-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="74d25-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="74d25-302">QtyToPut</span></span> | <span data-ttu-id="74d25-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="74d25-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="74d25-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="74d25-304">QtyToScrap</span></span> | <span data-ttu-id="74d25-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="74d25-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="74d25-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-306">QtyVerification</span></span> | <span data-ttu-id="74d25-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="74d25-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="74d25-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="74d25-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="74d25-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="74d25-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="74d25-310">ReasonString</span></span> | <span data-ttu-id="74d25-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="74d25-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="74d25-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-312">RecvLocationId</span></span> | <span data-ttu-id="74d25-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="74d25-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-314">RemoveContainerId</span></span> | <span data-ttu-id="74d25-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="74d25-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="74d25-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="74d25-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="74d25-318">RMANum</span></span> | <span data-ttu-id="74d25-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="74d25-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="74d25-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="74d25-320">ShortPickReason</span></span> | <span data-ttu-id="74d25-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="74d25-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="74d25-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-322">SortConOrLP</span></span> | <span data-ttu-id="74d25-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="74d25-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-324">SortLicensePlateId</span></span> | <span data-ttu-id="74d25-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="74d25-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="74d25-326">SortPositionId</span></span> | <span data-ttu-id="74d25-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="74d25-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="74d25-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="74d25-328">SortVerification</span></span> | <span data-ttu-id="74d25-329">WHSMobileAppStepSortVérification</span><span class="sxs-lookup"><span data-stu-id="74d25-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="74d25-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-330">StartLocationId</span></span> | <span data-ttu-id="74d25-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="74d25-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="74d25-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="74d25-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-334">TargetLicensePlateId</span></span> | <span data-ttu-id="74d25-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="74d25-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-336">TOLineNum</span></span> | <span data-ttu-id="74d25-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="74d25-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-338">ToLocation</span></span> | <span data-ttu-id="74d25-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="74d25-340">TONum</span><span class="sxs-lookup"><span data-stu-id="74d25-340">TONum</span></span> | <span data-ttu-id="74d25-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="74d25-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="74d25-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="74d25-342">ToWarehouse</span></span> | <span data-ttu-id="74d25-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="74d25-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="74d25-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-344">TransportLoadId</span></span> | <span data-ttu-id="74d25-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="74d25-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="74d25-346">WaveLabelId</span></span> | <span data-ttu-id="74d25-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="74d25-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="74d25-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="74d25-348">WaveLblQty</span></span> | <span data-ttu-id="74d25-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="74d25-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="74d25-350">Pondération</span><span class="sxs-lookup"><span data-stu-id="74d25-350">Weight</span></span> | <span data-ttu-id="74d25-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="74d25-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-352">WeightToConsume</span></span> | <span data-ttu-id="74d25-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="74d25-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="74d25-354">WHSAdjustmentType</span></span> | <span data-ttu-id="74d25-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="74d25-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="74d25-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="74d25-356">WHSReceivingException</span></span> | <span data-ttu-id="74d25-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="74d25-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="74d25-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="74d25-358">WHSWorkException</span></span> | <span data-ttu-id="74d25-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="74d25-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="74d25-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="74d25-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="74d25-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="74d25-362">WMSLocationId</span></span> | <span data-ttu-id="74d25-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="74d25-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="74d25-364">WorkId</span></span> | <span data-ttu-id="74d25-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="74d25-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="74d25-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="74d25-366">WorkIdToCancel</span></span> | <span data-ttu-id="74d25-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="74d25-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="74d25-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="74d25-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="74d25-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="74d25-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="74d25-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="74d25-370">WorkPoolId</span></span> | <span data-ttu-id="74d25-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="74d25-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="74d25-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="74d25-372">ZoneId</span></span> | <span data-ttu-id="74d25-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="74d25-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="74d25-374">Icônes d’étape disponibles</span><span class="sxs-lookup"><span data-stu-id="74d25-374">Available step icons</span></span>

<span data-ttu-id="74d25-375">Le système comprend une collection d’icônes d’étape standard que vous pouvez également utiliser pour vos étapes personnalisées.</span><span class="sxs-lookup"><span data-stu-id="74d25-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="74d25-376">Vous ne pouvez pas actuellement charger des icônes d’étape personnalisées.</span><span class="sxs-lookup"><span data-stu-id="74d25-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="74d25-377">Par conséquent, vous devez toujours sélectionner l’une des icônes d’étape standard.</span><span class="sxs-lookup"><span data-stu-id="74d25-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="74d25-378">Le tableau suivant présente chaque icône d’étape standard actuellement disponible et son nom.</span><span class="sxs-lookup"><span data-stu-id="74d25-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Icône d’étape À propos"><br><span data-ttu-id="74d25-380">À propos</span><span class="sxs-lookup"><span data-stu-id="74d25-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Icône d’étape Ajouter un contenant ou un article"><br><span data-ttu-id="74d25-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="74d25-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icône d’étape Disposition de lot"><br><span data-ttu-id="74d25-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icône d’étape Transporteur"><br><span data-ttu-id="74d25-386">Transporteur</span><span class="sxs-lookup"><span data-stu-id="74d25-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icône d’étape Balise de poids variable"><br><span data-ttu-id="74d25-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="74d25-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icône d’étape Poids de la balise de poids variable"><br><span data-ttu-id="74d25-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icône d’étape Chiffre de contrôle"><br><span data-ttu-id="74d25-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="74d25-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icône d’étape ID de vérification à l’entrée et à la sortie"><br><span data-ttu-id="74d25-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="74d25-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icône d’étape Contenant enfant"><br><span data-ttu-id="74d25-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="74d25-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icône d’étape ID de cluster"><br><span data-ttu-id="74d25-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icône d’étape Position du cluster"><br><span data-ttu-id="74d25-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="74d25-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icône d’étape ID de configuration"><br><span data-ttu-id="74d25-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="74d25-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icône d’étape Champ configuré"><br><span data-ttu-id="74d25-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="74d25-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icône d’étape Conteneur ou contenant"><br><span data-ttu-id="74d25-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icône d’étape Consolider à partir de l’ID de contenant"><br><span data-ttu-id="74d25-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="74d25-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icône d’étape Consolider sur l’ID de contenant"><br><span data-ttu-id="74d25-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="74d25-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icône d’étape Type de conteneur"><br><span data-ttu-id="74d25-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="74d25-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icône d’étape Inventaire"><br><span data-ttu-id="74d25-414">Comptage</span><span class="sxs-lookup"><span data-stu-id="74d25-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icône d’étape Code motif d’inventaire"><br><span data-ttu-id="74d25-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="74d25-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icône d’étape Code pays d’origine"><br><span data-ttu-id="74d25-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="74d25-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icône d’étape Disposition"><br><span data-ttu-id="74d25-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="74d25-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icône d’étape Terminé"><br><span data-ttu-id="74d25-422">Terminé</span><span class="sxs-lookup"><span data-stu-id="74d25-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icône d’étape Confirmation de la vérification à l’arrivée du chauffeur"><br><span data-ttu-id="74d25-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icône d’étape ID de vérification à l’arrivée du chauffeur"><br><span data-ttu-id="74d25-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="74d25-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icône d’étape ID de vérification au départ du chauffeur"><br><span data-ttu-id="74d25-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="74d25-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icône d’étape Date d’expiration"><br><span data-ttu-id="74d25-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="74d25-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icône d’étape Champ"><br><span data-ttu-id="74d25-432">Champ</span><span class="sxs-lookup"><span data-stu-id="74d25-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icône d’étape À partir de la disposition de lot"><br><span data-ttu-id="74d25-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="74d25-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icône d’étape À partir du statut du stock"><br><span data-ttu-id="74d25-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="74d25-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icône d’étape ID d’attribut"><br><span data-ttu-id="74d25-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="74d25-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icône d’étape ID de traitement par lots du stock"><br><span data-ttu-id="74d25-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="74d25-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icône d’étape ID de couleur du stock"><br><span data-ttu-id="74d25-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="74d25-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icône d’étape Emplacement du stock"><br><span data-ttu-id="74d25-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icône d’étape ID de série du stock"><br><span data-ttu-id="74d25-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="74d25-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icône d’étape ID de taille du stock"><br><span data-ttu-id="74d25-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="74d25-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icône d’étape ID de statut du stock"><br><span data-ttu-id="74d25-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="74d25-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icône d’étape ID de style du stock"><br><span data-ttu-id="74d25-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="74d25-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icône d’étape ID de version du stock"><br><span data-ttu-id="74d25-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="74d25-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icône d’étape ID d’article"><br><span data-ttu-id="74d25-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="74d25-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icône d’étape ID de conteneur ITM"><br><span data-ttu-id="74d25-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="74d25-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Icône d’étape ID d’expédition ITM"><br><span data-ttu-id="74d25-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="74d25-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icône d’étape ID de carte kanban"><br><span data-ttu-id="74d25-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="74d25-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icône d’étape ID de kanban ou de carte"><br><span data-ttu-id="74d25-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="74d25-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icône d’étape ID de contenant"><br><span data-ttu-id="74d25-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="74d25-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icône d’étape ID de chargement"><br><span data-ttu-id="74d25-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icône d’étape Position de l’emplacement ou du contenant"><br><span data-ttu-id="74d25-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="74d25-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icône d’étape Emplacement ou contenant"><br><span data-ttu-id="74d25-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="74d25-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icône d’étape Vérification de l’emplacement ou du contenant"><br><span data-ttu-id="74d25-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="74d25-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icône d’étape À partir de l’emplacement ou du contenant"><br><span data-ttu-id="74d25-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="74d25-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icône d’étape Vers l’emplacement ou le contenant"><br><span data-ttu-id="74d25-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="74d25-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icône d’étape Long processus terminé"><br><span data-ttu-id="74d25-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="74d25-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icône d’étape Décomposer le contenant parent en contenants"><br><span data-ttu-id="74d25-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icône d’étape Fusionner l’ID de conteneur"><br><span data-ttu-id="74d25-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="74d25-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icône d’étape Numéro de ligne de contenant mixte"><br><span data-ttu-id="74d25-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icône d’étape Poids sortant"><br><span data-ttu-id="74d25-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="74d25-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icône d’étape Propriétaire"><br><span data-ttu-id="74d25-490">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="74d25-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icône d’étape Contenant parent"><br><span data-ttu-id="74d25-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="74d25-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icône d’étape Veuillez confirmer"><br><span data-ttu-id="74d25-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="74d25-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icône d’étape Numéro de ligne de commande fournisseur"><br><span data-ttu-id="74d25-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icône d’étape Numéro de commande fournisseur"><br><span data-ttu-id="74d25-498">N° commande</span><span class="sxs-lookup"><span data-stu-id="74d25-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icône d’étape Poste complet"><br><span data-ttu-id="74d25-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="74d25-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icône d’étape Potence"><br><span data-ttu-id="74d25-502">Concentration</span><span class="sxs-lookup"><span data-stu-id="74d25-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icône d’étape Nom de l’imprimante"><br><span data-ttu-id="74d25-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="74d25-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icône d’étape ID de production"><br><span data-ttu-id="74d25-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="74d25-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icône d’étape Confirmation du produit"><br><span data-ttu-id="74d25-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icône d’étape Stockage"><br><span data-ttu-id="74d25-510">Placer</span><span class="sxs-lookup"><span data-stu-id="74d25-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icône d’étape ID de cluster de stockage"><br><span data-ttu-id="74d25-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="74d25-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icône d’étape Quantité"><br><span data-ttu-id="74d25-514">Qté</span><span class="sxs-lookup"><span data-stu-id="74d25-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icône d’étape Ajuster la quantité dans"><br><span data-ttu-id="74d25-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="74d25-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icône d’étape Quantité partielle"><br><span data-ttu-id="74d25-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="74d25-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icône d’étape Quantité à consommer"><br><span data-ttu-id="74d25-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icône d’étape Quantité à stocker"><br><span data-ttu-id="74d25-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="74d25-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icône d’étape Quantité à mettre au rebut"><br><span data-ttu-id="74d25-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="74d25-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icône d’étape Confirmation de la quantité"><br><span data-ttu-id="74d25-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="74d25-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icône d’étape Déclarer la tâche comme terminée"><br><span data-ttu-id="74d25-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="74d25-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icône d’étape ID de l’emplacement de réception"><br><span data-ttu-id="74d25-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="74d25-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icône d’étape Supprimer l’ID de conteneur"><br><span data-ttu-id="74d25-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="74d25-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icône d’étape Numéro RMA"><br><span data-ttu-id="74d25-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="74d25-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icône d’étape Sélectionner une commande"><br><span data-ttu-id="74d25-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="74d25-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icône d’étape Motif de prélèvement partiel"><br><span data-ttu-id="74d25-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="74d25-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icône d’étape ID de poste de tri"><br><span data-ttu-id="74d25-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="74d25-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icône d’étape ID de contenant cible"><br><span data-ttu-id="74d25-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icône d’étape Vers le numéro de ligne"><br><span data-ttu-id="74d25-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="74d25-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icône d’étape Vers l’emplacement"><br><span data-ttu-id="74d25-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="74d25-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icône d’étape Vers le numéro"><br><span data-ttu-id="74d25-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="74d25-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icône d’étape Vers l’entrepôt"><br><span data-ttu-id="74d25-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="74d25-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icône d’étape ID de chargement de transport"><br><span data-ttu-id="74d25-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="74d25-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icône d’étape ID de lot fournisseur"><br><span data-ttu-id="74d25-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="74d25-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icône d’étape ID d’étiquette de vague"><br><span data-ttu-id="74d25-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="74d25-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icône d’étape Quantité d’étiquettes de vague"><br><span data-ttu-id="74d25-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="74d25-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icône d’étape Poids"><br><span data-ttu-id="74d25-560">Pondération</span><span class="sxs-lookup"><span data-stu-id="74d25-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icône d’étape Poids à consommer"><br><span data-ttu-id="74d25-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="74d25-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icône d’étape Type d’ajustement WHS"><br><span data-ttu-id="74d25-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="74d25-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icône d’étape Exception de réception WHS"><br><span data-ttu-id="74d25-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="74d25-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icône d’étape ID d’emplacement WMS"><br><span data-ttu-id="74d25-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="74d25-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icône d’étape ID de travail"><br><span data-ttu-id="74d25-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="74d25-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icône d’étape ID de travail à annuler"><br><span data-ttu-id="74d25-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="74d25-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icône d’étape ID de contenant de travail"><br><span data-ttu-id="74d25-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="74d25-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icône d’étape Cluster de stockage des ID de contenant de travail"><br><span data-ttu-id="74d25-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="74d25-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icône d’étape ID de groupe de travail"><br><span data-ttu-id="74d25-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="74d25-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icône d’étape ID de zone"><br><span data-ttu-id="74d25-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="74d25-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="74d25-581">Exemple : affecter des icônes et des titres d’étape pour un flux personnalisé</span><span class="sxs-lookup"><span data-stu-id="74d25-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="74d25-582">Cet exemple explique comment configurer des icônes et des titres d’étape pour un flux de tâches personnalisé.</span><span class="sxs-lookup"><span data-stu-id="74d25-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="74d25-583">Le scénario repose sur un exemple de flux de tâches personnalisé qui est présenté et exploré plus en détail dans le billet de blog suivant : [Personnalisation de l’application mobile d’entreposage](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="74d25-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="74d25-584">Le flux de tâches fonctionne de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="74d25-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="74d25-585">L’application affiche une page qui invite le collaborateur à fournir un ID de conteneur (par exemple, en scannant un code-barres).</span><span class="sxs-lookup"><span data-stu-id="74d25-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="74d25-586">Si l’ID de conteneur est valide, l’application ouvre une nouvelle page qui invite le collaborateur à entrer le poids.</span><span class="sxs-lookup"><span data-stu-id="74d25-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="74d25-587">(Si l’ID de conteneur n’est pas valide, le collaborateur est renvoyé vers la première page.)</span><span class="sxs-lookup"><span data-stu-id="74d25-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="74d25-588">Lorsque le collaborateur entre un poids valide, le système stocke le poids et renvoie le collaborateur vers la première page.</span><span class="sxs-lookup"><span data-stu-id="74d25-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="74d25-589">L’illustration suivante présente ce flux de tâches.</span><span class="sxs-lookup"><span data-stu-id="74d25-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="74d25-590">![Diagramme du flux de tâches](media/step-icons-example-task-flow.png "Diagramme du flux de tâches")</span><span class="sxs-lookup"><span data-stu-id="74d25-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="74d25-591">Créer une classe d’étape pour la page de saisie du conteneur</span><span class="sxs-lookup"><span data-stu-id="74d25-591">Create a step class for the container input page</span></span>

<span data-ttu-id="74d25-592">La page de saisie du conteneur permet au collaborateur de scanner ou d’entrer un ID de conteneur.</span><span class="sxs-lookup"><span data-stu-id="74d25-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="74d25-593">![Page de saisie du conteneur](media/step-icons-example-container-input.png "Page de saisie du conteneur")</span><span class="sxs-lookup"><span data-stu-id="74d25-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="74d25-594">Dans la page de saisie du conteneur, le nom de contrôle du champ de saisie est `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="74d25-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="74d25-595">Comme ce nom de contrôle ne figure pas sur la [liste des ID d’étape](#step-ids-classes), vous ne trouverez pas d’étape existante basée sur celui-ci.</span><span class="sxs-lookup"><span data-stu-id="74d25-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="74d25-596">Par conséquent, vous devez créer une classe d’étape qui représente l’étape.</span><span class="sxs-lookup"><span data-stu-id="74d25-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="74d25-597">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="74d25-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="74d25-598">L’identificateur de l’icône d’étape est stocké dans le membre de la classe `defaultStepIcon`, et le titre de l’étape est stocké dans le membre de la classe `defaultStepTitle`.</span><span class="sxs-lookup"><span data-stu-id="74d25-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="74d25-599">Pour affecter une icône d’étape, définissez `defaultStepIcon` sur l’un des ID d’icône répertoriés dans la section [Icônes d’étape disponibles](#step-icons) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="74d25-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="74d25-600">Utiliser une icône et un titre d’étape standard ou personnalisé pour la saisie du poids</span><span class="sxs-lookup"><span data-stu-id="74d25-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="74d25-601">La page de saisie du poids permet au collaborateur de saisir un poids.</span><span class="sxs-lookup"><span data-stu-id="74d25-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="74d25-602">![Page de saisie du poids](media/step-icons-example-weight-input.png "Page de saisie du poids")</span><span class="sxs-lookup"><span data-stu-id="74d25-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="74d25-603">Dans la page de saisie du poids, le nom de contrôle du champ de saisie est `Weight`, qui figure dans la [liste des ID d’étape](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="74d25-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="74d25-604">Par conséquent, si l’icône et le titre de l’étape définis dans la classe `WHSMobileAppStepWeight` vous conviennent, vous n’avez rien à changer pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="74d25-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="74d25-605">Cependant, si vous préférez utiliser une autre icône ou un autre titre pour cette étape, vous pouvez remplacer la méthode `stepId()` ou la méthode `stepInfo()` dans la classe du générateur.</span><span class="sxs-lookup"><span data-stu-id="74d25-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="74d25-606">Chaque flux de tâches a son propre générateur d’informations sur les étapes.</span><span class="sxs-lookup"><span data-stu-id="74d25-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="74d25-607">Remplacer la méthode stepId()</span><span class="sxs-lookup"><span data-stu-id="74d25-607">Override the stepId() method</span></span>

<span data-ttu-id="74d25-608">L’exemple suivant montre une façon de modifier une classe de constructeur en remplaçant la méthode `stepId()`.</span><span class="sxs-lookup"><span data-stu-id="74d25-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="74d25-609">Vous créez ensuite une classe d’étape pour l’étape `NewWeight`.</span><span class="sxs-lookup"><span data-stu-id="74d25-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="74d25-610">Le code doit ressembler au code de l’exemple `ContainerId` présenté plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="74d25-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="74d25-611">Remplacer la méthode stepInfo()</span><span class="sxs-lookup"><span data-stu-id="74d25-611">Override the stepInfo() method</span></span>

<span data-ttu-id="74d25-612">L’exemple suivant montre une façon de modifier une classe de constructeur en remplaçant la méthode `stepInfo()`.</span><span class="sxs-lookup"><span data-stu-id="74d25-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="74d25-613">Vous construisez ensuite un objet `WHSMobileAppStepInfo` et définissez directement l’icône et/ou le titre.</span><span class="sxs-lookup"><span data-stu-id="74d25-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74d25-614">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="74d25-614">Additional resources</span></span>

- [<span data-ttu-id="74d25-615">Installer et connecter l’application mobile Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="74d25-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="74d25-616">Paramètres utilisateur d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="74d25-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
