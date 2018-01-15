---
title: Inventaire tournant
description: "Cet article décrit la manière dont vous pouvez utiliser l'inventaire tournant associé à la solution de stockage disponible dans le module Gestion des entrepôts. Cet article ne s'applique pas à la solution de stockage disponible dans la Gestion des stocks."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ddb035eaa496a7c84f117f0523d509eccdf58505
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="cycle-counting"></a><span data-ttu-id="69527-104">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-104">Cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="69527-105">Cet article décrit la manière dont vous pouvez utiliser l'inventaire tournant associé à la solution de stockage disponible dans le module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="69527-105">This article describes how you can use cycle counting with the warehousing solution that is available in Warehouse management.</span></span> <span data-ttu-id="69527-106">Cet article ne s'applique pas à la solution de stockage disponible dans la Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="69527-106">This article doesn't apply to the warehousing solution that's available in Inventory management.</span></span>

<span data-ttu-id="69527-107">L'inventaire tournant est un processus d'entrepôt qui permet d'auditer les articles en stock disponibles.</span><span class="sxs-lookup"><span data-stu-id="69527-107">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="69527-108">Le processus d'inventaire tournant peut être décrit en trois étapes :</span><span class="sxs-lookup"><span data-stu-id="69527-108">The cycle counting process can be described in three steps:</span></span>

1.  <span data-ttu-id="69527-109">**Créer un travail d'inventaire tournant** – Un travail d'inventaire tournant peut être créé automatiquement en fonction des paramètres de seuil pour des articles ou à l'aide d'un plan d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-109">**Create cycle counting work** – Cycle counting work can be created automatically, based on threshold parameters for items or by using a cycle counting plan.</span></span> <span data-ttu-id="69527-110">Vous pouvez également créer manuellement un travail d'inventaire tournant en utilisant les paramètres de l'article ou de l'entrepôt dans la page **Travail d'inventaire tournant par article** ou la page **Travail d'inventaire tournant par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="69527-110">Alternatively, you can manually create cycle counting work by using the item or warehouse parameters on the **Cycle count work by item** page or the **Cycle count work by location** page.</span></span>
2.  <span data-ttu-id="69527-111">**Traiter l'inventaire tournant** – Après avoir créé le travail d'inventaire tournant, vous effectuez le travail d'inventaire tournant en comptant les articles dans un emplacement d'entrepôt puis vous utilisez un appareil mobile pour entrer le résultat dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="69527-111">**Process the cycle count** – After cycle counting work is created, you do the cycle counting work by counting items in a warehouse location and then using a mobile device to enter the result in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="69527-112">Sinon, vous pouvez compter les articles dans un emplacement d'entrepôt sans créer de travail d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-112">Alternatively, you can count items in a warehouse location without creating cycle counting work.</span></span> <span data-ttu-id="69527-113">Ce processus est également appelé *inventaire tournant ponctuel*.</span><span class="sxs-lookup"><span data-stu-id="69527-113">This process is referred to as *spot cycle counting*.</span></span>
3.  <span data-ttu-id="69527-114">**Corriger des différences dans la valeur comptabilisée** – Après la réalisation d'un inventaire tournant, les articles présentant des différences au niveau de la valeur comptabilisée ont un statut de travail de **Révision en attente** dans la page **Tout le travail**.</span><span class="sxs-lookup"><span data-stu-id="69527-114">**Resolve differences in the counted value** – After a cycle count, any items that have differences in the counted value will have a work status of **Pending review** on the **All work** page.</span></span> <span data-ttu-id="69527-115">Vous pouvez résoudre ces différences dans la page **Révision en attente de travail d'inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="69527-115">You can resolve these differences on the **Cycle count work pending review** page.</span></span>

<span data-ttu-id="69527-116">L'illustration suivante indique comment effectuer le processus d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-116">The following illustration shows the cycle counting process.</span></span> ![Flux de processus pour l'inventaire tournant](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a><span data-ttu-id="69527-118">Conditions requises pour l'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-118">Cycle counting prerequisites</span></span>
<span data-ttu-id="69527-119">Le tableau suivant indique les conditions requises devant être mises en place avant d'utiliser l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-119">The following table shows the prerequisites that must be in place before you can use cycle counting.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69527-120">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="69527-120">Prerequisite</span></span></th>
<th><span data-ttu-id="69527-121">Description</span><span class="sxs-lookup"><span data-stu-id="69527-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="69527-122">Article</span><span class="sxs-lookup"><span data-stu-id="69527-122">Item</span></span></td>
<td><span data-ttu-id="69527-123">L'article doit être activé pour les processus de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="69527-123">The item must be enabled for warehouse management processes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69527-124">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="69527-124">Warehouse</span></span></td>
<td><span data-ttu-id="69527-125">L'entrepôt doit être activé pour les processus de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="69527-125">The warehouse must be enabled for warehouse management processes.</span></span> <span data-ttu-id="69527-126">Pour activer l'entrepôt pour les processus de gestion des entrepôts, dans la page <strong>Entrepôts</strong>, sélectionnez l'entrepôt, puis activez l'option <strong>Utiliser les processus de gestion des entrepôts</strong>.</span><span class="sxs-lookup"><span data-stu-id="69527-126">To enable the warehouse for warehouse management processes, on the <strong>Warehouses</strong> page, select the warehouse, and then select the <strong>Use warehouse management processes</strong> option.</span></span> <span data-ttu-id="69527-127">Pour autoriser des collaborateurs à déplacer des palettes pendant un inventaire tournant, dans l'organisateur <strong>Gestion des entrepôts</strong>, sélectionnez l'option <strong>Autoriser les déplacements de palettes pendant l'inventaire tournant</strong>.</span><span class="sxs-lookup"><span data-stu-id="69527-127">To enable workers to move pallets during a cycle count, on the <strong>Warehouse management</strong> FastTab, select the <strong>Allow pallet moves during cycle counting</strong> option.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="69527-128">Pools de travail</span><span class="sxs-lookup"><span data-stu-id="69527-128">Work pools</span></span></td>
<td><span data-ttu-id="69527-129">Facultatif : Créez un pool de travail pour isoler le travail d'entrepôt selon le type de travail (dans ce cas, un travail d'inventaire tournant).</span><span class="sxs-lookup"><span data-stu-id="69527-129">Optional: Create a work pool to segregate the warehouse work, based on the type of work (in this case, cycle counting work).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69527-130">Lieux</span><span class="sxs-lookup"><span data-stu-id="69527-130">Locations</span></span></td>
<td><span data-ttu-id="69527-131">Activez l'inventaire tournant pour les emplacements.</span><span class="sxs-lookup"><span data-stu-id="69527-131">Enable cycle counting for locations.</span></span> <span data-ttu-id="69527-132">Pour autoriser un inventaire tournant pour un emplacement d'entrepôt, dans la page <strong>Profils d'emplacement</strong>, sélectionnez l'option <strong>Autoriser l'inventaire tournant</strong>.</span><span class="sxs-lookup"><span data-stu-id="69527-132">To enable cycle counting for a warehouse location, on the <strong>Location profiles</strong> page, select the <strong>Allow cycle counting</strong> option.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="69527-133">Paramètres de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="69527-133">Warehouse management parameters</span></span></td>
<td><span data-ttu-id="69527-134">Définissez les paramètres de l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-134">Set up parameters for cycle counting.</span></span> <span data-ttu-id="69527-135">Dans la page <strong>Paramètres de gestion des entrepôts</strong>, spécifiez le code type d'ajustement par défaut, l'ID de la classe de travail et la priorité du travail pour l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-135">On the <strong>Warehouse management parameters</strong> page, specify the default adjustment type code, work class ID, and work priority for cycle counting.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69527-136">Appareil mobile</span><span class="sxs-lookup"><span data-stu-id="69527-136">Mobile device</span></span></td>
<td><ul>
<li><span data-ttu-id="69527-137">Créez une option de menu pour l'une des méthodes suivantes dans la page <strong>Options de menu d'appareil mobile</strong> :</span><span class="sxs-lookup"><span data-stu-id="69527-137">Create a menu item for one of the following methods on the <strong>Mobile device menu items</strong> page:</span></span>
<ul>
<li><span data-ttu-id="69527-138">Inventaire tournant dirigé par utilisateur</span><span class="sxs-lookup"><span data-stu-id="69527-138">User directed cycle counting</span></span></li>
<li><span data-ttu-id="69527-139">Inventaire tournant dirigé par le système</span><span class="sxs-lookup"><span data-stu-id="69527-139">System directed cycle counting</span></span></li>
<li><span data-ttu-id="69527-140">Regroupement d'inventaires tournants</span><span class="sxs-lookup"><span data-stu-id="69527-140">Cycle count grouping</span></span></li>
<li><span data-ttu-id="69527-141">Inventaire tournant ponctuel</span><span class="sxs-lookup"><span data-stu-id="69527-141">Spot cycle counting</span></span></li>
</ul>
</li>
<li><span data-ttu-id="69527-142">Paramétrez un menu pour l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="69527-142">Set up a menu for the mobile device.</span></span></li>
<li><span data-ttu-id="69527-143">Créez un compte d'utilisateur de travail et affectez un menu d'appareil mobile à l'ID utilisateur de travail.</span><span class="sxs-lookup"><span data-stu-id="69527-143">Create a work user account, and assign a mobile device menu to the work user ID.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="69527-144">Tâche associée de paramétrage</span><span class="sxs-lookup"><span data-stu-id="69527-144">Related setup task</span></span></td>
<td><span data-ttu-id="69527-145">Paramétrez un plan d'inventaire tournant pour un emplacement d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="69527-145">Set up a cycle counting plan for a warehouse location.</span></span></td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a><span data-ttu-id="69527-146">Créer automatiquement un travail d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-146">Automatically create cycle counting work</span></span>
<span data-ttu-id="69527-147">Il existe deux manières de planifier la création récurrente du travail d'inventaire tournant : le paramétrage des seuils d'inventaire tournant ou celui des plans d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-147">There are two ways to schedule recurring creation of cycle counting work: set up cycle counting thresholds or set up cycle counting plans.</span></span>

-   <span data-ttu-id="69527-148">Un seuil d'inventaire tournant indique la limite de quantité ou de pourcentage des articles en stock.</span><span class="sxs-lookup"><span data-stu-id="69527-148">A cycle counting threshold indicates the quantity or percentage limit of inventory items.</span></span> <span data-ttu-id="69527-149">Le travail d'inventaire tournant est automatiquement créé lorsque la limite de seuil est atteinte.</span><span class="sxs-lookup"><span data-stu-id="69527-149">Cycle counting work is automatically created when the threshold limit is reached.</span></span>
-   <span data-ttu-id="69527-150">Un plan d'inventaire tournant crée un travail d'inventaire tournant immédiatement ou périodiquement par le biais d'un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="69527-150">A cycle counting plan creates cycle counting work either immediately or periodically through a batch job.</span></span> <span data-ttu-id="69527-151">Lorsqu'un travail d'inventaire tournant est créé, la ligne de travail d'inventaire comprend des informations sur l'emplacement d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="69527-151">When cycle counting work is created, the counting work line includes information about the location to count.</span></span> <span data-ttu-id="69527-152">Le stock disponible associé à cet emplacement n'est pas bloqué et il est donc disponible pour la réservation et le traitement sortant, même si un travail d'inventaire en cours existe.</span><span class="sxs-lookup"><span data-stu-id="69527-152">The on-hand inventory that is associated with this location isn't blocked, and is therefore available for reservation and outbound processing, even though open counting work exists.</span></span>

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a><span data-ttu-id="69527-153">Créer un inventaire tournant basé sur des paramètres de seuil pour les articles</span><span class="sxs-lookup"><span data-stu-id="69527-153">Create cycle counting work, based on threshold parameters for items</span></span>

<span data-ttu-id="69527-154">Le travail d'inventaire tournant peut être créé lorsque le nombre d'articles passe en dessous d'une valeur de seuil spécifique dans un emplacement.</span><span class="sxs-lookup"><span data-stu-id="69527-154">Cycle counting work can be created when the number of items falls below a specific threshold value in a location.</span></span> <span data-ttu-id="69527-155">Par exemple, supposons que vous ayez 60 articles dans un emplacement dont le seuil d'inventaire tournant est de 40.</span><span class="sxs-lookup"><span data-stu-id="69527-155">For example, there are 60 items in a location that has a cycle counting threshold of 40.</span></span> <span data-ttu-id="69527-156">Lors d'une transaction de commande client, 25 articles sont prélevés de l'emplacement et placés dans un emplacement temporaire.</span><span class="sxs-lookup"><span data-stu-id="69527-156">During a sales order transaction, 25 items are picked from the location and put in a staging location.</span></span> <span data-ttu-id="69527-157">Étant donné que le nombre d'articles restants, 35, est inférieur à la quantité de seuil, un travail d'inventaire tournant est automatiquement créé pour l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="69527-157">Because the new item count, 35, is less than the threshold quantity, cycle counting work is automatically created for the location.</span></span>

### <a name="schedule-cycle-counting-work"></a><span data-ttu-id="69527-158">Planification d'un travail d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-158">Schedule cycle counting work</span></span>

<span data-ttu-id="69527-159">Vous pouvez programmer des plans d'inventaire tournant pour créer le travail d'inventaire tournant immédiatement ou périodiquement.</span><span class="sxs-lookup"><span data-stu-id="69527-159">You can schedule cycle counting plans to create cycle counting work immediately or periodically.</span></span> <span data-ttu-id="69527-160">En paramétrant des plans de cycle d'inventaire, vous pouvez contrôler le pool de travail pour lequel le travail d'inventaire tournant est créé, le nombre maximal d'inventaires tournants créés pour des articles dans différents emplacements et le nombre de jours avant le prochain inventaire de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="69527-160">By setting up cycle counting plans, you can control the work pool that cycle counting work is created for, the maximum number of cycle counts that are created for items in different locations, and the number of days before a warehouse location is counted again.</span></span> <span data-ttu-id="69527-161">Par exemple, un article est disponible dans trois emplacements de l'entrepôt et le nombre maximal d'inventaires tournants est défini sur **2**.</span><span class="sxs-lookup"><span data-stu-id="69527-161">For example, an item is available in three locations in the warehouse, and the maximum number of cycle counts is set to **2**.</span></span> <span data-ttu-id="69527-162">Dans ce cas, lorsque vous exécutez le plan d'inventaire tournant, deux inventaires tournants sont créés pour les deux emplacements dans lesquels l'article est présent.</span><span class="sxs-lookup"><span data-stu-id="69527-162">In this case, when you run the cycle counting plan, two cycle counts are created for the two locations where the item is present.</span></span> <span data-ttu-id="69527-163">Autre exemple, vous définissez le nombre de jours entre les inventaires tournants sur **5**.</span><span class="sxs-lookup"><span data-stu-id="69527-163">As another example, you set the number of days between cycle counts to **5**.</span></span> <span data-ttu-id="69527-164">Dans ce cas, le travail d'inventaire tournant est créé tous les cinq jours.</span><span class="sxs-lookup"><span data-stu-id="69527-164">In this case, cycle counting work is created every five days.</span></span> <span data-ttu-id="69527-165">Toutefois, si le travail d'inventaire tournant est traité le jour 3, le travail d'inventaire tournant suivant sera créé cinq jours après le traitement du dernier inventaire tournant, le jour 8.</span><span class="sxs-lookup"><span data-stu-id="69527-165">However, if cycle counting work is processed on day 3, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>

## <a name="create-cycle-counting-work-manually"></a><span data-ttu-id="69527-166">Création manuelle d'un travail d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-166">Create cycle counting work manually</span></span>
<span data-ttu-id="69527-167">Pour créer manuellement un cycle d'inventaire tournant, utilisez les pages **Inventaire tournant par article** ou **Travail d'inventaire tournant par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="69527-167">To create cycle counting work manually, you can use the **Cycle count work by item** or **Cycle count work by location** page.</span></span> <span data-ttu-id="69527-168">Vous pouvez spécifier le nombre maximal d'inventaires tournants à créer.</span><span class="sxs-lookup"><span data-stu-id="69527-168">You can specify the maximum number of cycle counts to create.</span></span> <span data-ttu-id="69527-169">Par exemple, si le responsable d'entrepôt spécifie une valeur de **5**, alors le travail d'inventaire tournant est créé pour cinq emplacements, même si l'article est présent dans 10 emplacements.</span><span class="sxs-lookup"><span data-stu-id="69527-169">For example, if the warehouse manager specifies a value of **5**, cycle counting work is created for five locations, even if the item is present in 10 locations.</span></span> <span data-ttu-id="69527-170">Vous pouvez également choisir un ID de pool de travail auquel attribuer les ID de travail d'inventaire tournant créés.</span><span class="sxs-lookup"><span data-stu-id="69527-170">You can also select a work pool ID to assign the cycle counting work IDs that are created to.</span></span> <span data-ttu-id="69527-171">Lorsqu'un ID de pool de travail est traité pour l'inventaire tournant, les ID de travail d'inventaire tournant qui sont affectés au pool de travail sont traités comme un groupe.</span><span class="sxs-lookup"><span data-stu-id="69527-171">When a work pool ID is processed for cycle counting, the cycle counting work IDs that are assigned to the work pool are processed as a group.</span></span>

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a><span data-ttu-id="69527-172">Effectuer un inventaire tournant en utilisant un appareil mobile</span><span class="sxs-lookup"><span data-stu-id="69527-172">Perform a cycle count by using a mobile device</span></span>
<span data-ttu-id="69527-173">Il existe plusieurs méthodes pour traiter un travail d'inventaire tournant à l'aide de Finance and Operations sur un appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="69527-173">There are several methods for processing cycle counting work by using Finance and Operations on a mobile device:</span></span>

-   <span data-ttu-id="69527-174">**Dirigé par l'utilisateur** – Le collaborateur peut préciser un ID de travail d'inventaire tournant qui a le statut **Ouvert**.</span><span class="sxs-lookup"><span data-stu-id="69527-174">**User directed** – The worker can specify a cycle counting work ID that has a status of **Open**.</span></span>
-   <span data-ttu-id="69527-175">**Dirigé par le système** – Finance and Operations attribue un ID de travail d'inventaire au collaborateur.</span><span class="sxs-lookup"><span data-stu-id="69527-175">**System directed** – Finance and Operations assigns a cycle counting work ID to the worker.</span></span>
-   <span data-ttu-id="69527-176">**Regroupement d'inventaires tournants** – Le collaborateur peut regrouper plusieurs ID de travail d'inventaire tournant qui sont spécifiques à un emplacement, à une zone ou à un pool de travail.</span><span class="sxs-lookup"><span data-stu-id="69527-176">**Cycle count grouping** – The worker can group cycle counting work IDs that are specific to a particular location, zone, or work pool.</span></span>
-   <span data-ttu-id="69527-177">**Inventaire tournant ponctuel** – Le collaborateur peut compter les articles dans un emplacement d'entrepôt à tout moment, sans créer de travail d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-177">**Spot cycle counting** – The worker can count items in a warehouse location at any time, without creating cycle counting work.</span></span> <span data-ttu-id="69527-178">Pour effectuer l'inventaire tournant ponctuel dans un emplacement, le travailleur entre l'ID de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="69527-178">To perform spot cycle counting in a location, the worker enters the location ID.</span></span>

<span data-ttu-id="69527-179">L'exemple suivant montre comment vous pouvez effectuer un inventaire tournant ponctuel à l'aide d'un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="69527-179">The following example shows how you can perform spot cycle counting by using a mobile device.</span></span> <span data-ttu-id="69527-180">Les instructions que le travailleur voit sur le périphérique varient selon le paramétrage de l'élément de menu pour l'inventaire tournant ponctuel.</span><span class="sxs-lookup"><span data-stu-id="69527-180">The instructions that the worker sees on the device vary, depending on the setup of the menu item for spot cycle counting.</span></span>

1.  <span data-ttu-id="69527-181">Sur l'appareil mobile, sélectionnez l'option de menu pour traiter le travail d'inventaire tournant ponctuel.</span><span class="sxs-lookup"><span data-stu-id="69527-181">On the mobile device, select the menu item to process spot cycle counting work.</span></span>
2.  <span data-ttu-id="69527-182">Enregistrez l'emplacement pour lequel vous voulez effectuer l'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="69527-182">Register the location to perform spot cycle counting for.</span></span>
3.  <span data-ttu-id="69527-183">Enregistrez et confirmez le numéro d'article et la quantité de l'article compté.</span><span class="sxs-lookup"><span data-stu-id="69527-183">Register and confirm the item number and the counted item quantity.</span></span> <span data-ttu-id="69527-184">**Remarque :** Le statut du travail d'inventaire tournant est mis à jour sur **Révision en attente** ou **Clôturé** dans la page **Tout le travail**, selon les paramètres définis dans la page **Collaborateur**.</span><span class="sxs-lookup"><span data-stu-id="69527-184">**Note:** The status of the cycle counting work is updated to either **Pending review** or **Closed** on the **All work** page, depending on the parameters that are set on the **Worker** page.</span></span>
4.  <span data-ttu-id="69527-185">Facultatif : Répétez l'étape 3 pour les articles restants de l'emplacement et confirmez qu'il n'existe aucun article supplémentaire disponible pour le comptage.</span><span class="sxs-lookup"><span data-stu-id="69527-185">Optional: Repeat step 3 for the remaining items in the location, and confirm that no additional items are available for counting.</span></span>

## <a name="resolve-cycle-counting-differences"></a><span data-ttu-id="69527-186">Résoudre les différences de l'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="69527-186">Resolve cycle counting differences</span></span>
<span data-ttu-id="69527-187">Une différence au niveau de l'inventaire tournant se produit dans les scénarios suivants si l'option **Superviseur d'inventaire tournant** est réglée sur **Non** pour un ID utilisateur de travail :</span><span class="sxs-lookup"><span data-stu-id="69527-187">A cycle counting difference occurs in the following scenarios if the **Is a cycle count supervisor** option is set to **No** for a work user ID:</span></span>

-   <span data-ttu-id="69527-188">La valeur d'inventaire tournant n'est pas comprise dans les limites d'écart spécifiées dans les champs **Limite maximale du pourcentage** ou **Limite maximale de la quantité** dans la page **Utilisateurs du travail**.</span><span class="sxs-lookup"><span data-stu-id="69527-188">The counted value isn't within the deviation limits that are specified in the **Maximum percentage limit** or **Maximum quantity limit** fields on the **Work users** page.</span></span> <span data-ttu-id="69527-189">Par exemple, la quantité de stock disponible dans un emplacement est de 50 et la limite d'écart pour l'utilisateur de travail est de 10.</span><span class="sxs-lookup"><span data-stu-id="69527-189">For example, the on-hand inventory quantity in a location is 50, and the deviation limit for the work user is 10.</span></span> <span data-ttu-id="69527-190">Si l'utilisateur de travail entre une valeur qui n'est pas comprise entre 40 et 60, une différence se produit.</span><span class="sxs-lookup"><span data-stu-id="69527-190">If the work user enters a value that isn't between 40 and 60, a difference occurs.</span></span>
-   <span data-ttu-id="69527-191">La valeur d'inventaire tournant diffère de la quantité de stock disponible et aucune limite d'écart n'est définie.</span><span class="sxs-lookup"><span data-stu-id="69527-191">The counted value differs from the on-hand inventory quantity, and no deviation limits are set.</span></span>

<span data-ttu-id="69527-192">Ajustez les différences dans la valeur d'inventaire puis acceptez la valeur d'inventaire dans la page **Inventaire tournant en attente de révision**.</span><span class="sxs-lookup"><span data-stu-id="69527-192">You can adjust differences in the counted value and then accept the counted value on the **Cycle count pending review** page.</span></span> <span data-ttu-id="69527-193">Vous pouvez vérifier le compte modifié de la quantité d'articles dans la page **Disponible par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="69527-193">You can verify the modified count of the item quantity on the **On hand by location** page.</span></span> <span data-ttu-id="69527-194">La valeur d'inventaire est rejetée si la différence ne peut pas être approuvée.</span><span class="sxs-lookup"><span data-stu-id="69527-194">The counted value is rejected if the difference can't be approved.</span></span>

# <a name="see-also"></a><span data-ttu-id="69527-195">Voir également :</span><span class="sxs-lookup"><span data-stu-id="69527-195">See also</span></span>
[<span data-ttu-id="69527-196">Configurer des appareils mobiles pour un travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="69527-196">Configure mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)



