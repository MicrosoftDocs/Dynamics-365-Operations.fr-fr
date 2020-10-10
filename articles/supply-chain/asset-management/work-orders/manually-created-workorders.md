---
title: Ordres de travail créés manuellement
description: Cette rubrique explique comment créer des ordres de travail manuellement dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a4b148d9ac5d032d2caa5fcea0398a5a3726f0e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888975"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="6eeca-103">Ordres de travail créés manuellement</span><span class="sxs-lookup"><span data-stu-id="6eeca-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="6eeca-104">Vous pouvez créer des ordres de travail manuellement de deux façons :</span><span class="sxs-lookup"><span data-stu-id="6eeca-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="6eeca-105">Sur la page **Tous les ordres de travail** ou **Ordres de travail actifs**</span><span class="sxs-lookup"><span data-stu-id="6eeca-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="6eeca-106">Sur la page **Toutes les demandes de maintenance** ou **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="6eeca-107">Créer un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="6eeca-107">Create work order</span></span>

1. <span data-ttu-id="6eeca-108">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6eeca-109">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-109">Select **New**.</span></span>

3. <span data-ttu-id="6eeca-110">Dans la boîte de dialogue **Créer un ordre de travail**, sélectionnez un ordre de travail dans le champ **Type d'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="6eeca-111">Le cas échéant, sélectionnez une **Description**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="6eeca-112">Dans le champ **Actif**, sélectionnez l'actif.</span><span class="sxs-lookup"><span data-stu-id="6eeca-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="6eeca-113">Lorsque vous sélectionnez un actif, trois onglets peuvent être disponibles dans le menu déroulant **Actif** :</span><span class="sxs-lookup"><span data-stu-id="6eeca-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="6eeca-114">**Actifs actifs** - Cet onglet contient la liste de tous les actifs avec un état de cycle de vie de l'actif « Actif ».</span><span class="sxs-lookup"><span data-stu-id="6eeca-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="6eeca-115">**Vue des actifs** - Cet onglet affiche une arborescence des postes techniques et les actifs qui y sont installés.</span><span class="sxs-lookup"><span data-stu-id="6eeca-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="6eeca-116">**Mes actifs** - Cet onglet contient les actifs associées aux postes techniques auxquels vous (le collaborateur connecté au système) pouvez être affecté.</span><span class="sxs-lookup"><span data-stu-id="6eeca-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="6eeca-117">(Pour plus d'informations sur le paramétrage, voir [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md).) Si aucun poste technique n'est paramétré sur un collaborateur dans [Agents de maintenance et groupes de collaborateurs](../setup-for-objects/workers-and-worker-groups.md), l'onglet **Mes actifs** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="6eeca-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="6eeca-118">Dans le champ **Type de tâche de maintenance**, sélectionnez le type de tâche de maintenance pour l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="6eeca-119">Si nécessaire, sélectionnez **Variante de type de tâche de maintenance** et **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="6eeca-120">Si nécessaire, vous pouvez modifier le niveau de service des ordres de travail dans le champ **Niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="6eeca-121">Sélectionnez les dates de **début prévue** et de **fin prévue** dans les champs associés.</span><span class="sxs-lookup"><span data-stu-id="6eeca-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="6eeca-122">Cliquez sur **OK** pour créer l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="6eeca-123">Dans la page de liste **Tous les ordres de travail**, vous pouvez modifier l'ordre de travail comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="6eeca-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="6eeca-124">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="6eeca-124">Note the following points:</span></span>

- <span data-ttu-id="6eeca-125">Dans la vue des détails de la page de liste **Tous les ordres de travail**, vous pouvez ajouter plusieurs actifs à un ordre de travail en ajoutant des lignes sur l'organisateur **Tâches de maintenance des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="6eeca-126">Sur un actif, vous ne pouvez sélectionner que les types de tâche de maintenance définis sur le type d'actif qui est sélectionné pour l'actif.</span><span class="sxs-lookup"><span data-stu-id="6eeca-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="6eeca-127">Si vous modifiez un niveau de service d'actif ou un élément critique d'actif après l'avoir utilisé sur un ordre de travail, le niveau de service ou l'élément critique sur l'ordre de travail n'est pas mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="6eeca-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="6eeca-128">Pour plus d'informations sur les niveaux de service et les éléments critiques, voir [Niveaux de service de l'actif](../setup-for-objects/object-priorities.md) et [Types critiques de l'actif](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="6eeca-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="6eeca-129">L'élément critique sur un ordre de travail est recalculé chaque fois qu'une tâche d'ordre de travail est ajoutée ou supprimée de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="6eeca-130">Dans la vue détaillée **Tous les ordres de travail** > onglet **En-tête** > organisateur **Programme**, dans le champ **Groupe responsable** ou **Responsable**, vous pouvez sélectionner un groupe d'agents de maintenance responsable ou un agent de maintenance responsable.</span><span class="sxs-lookup"><span data-stu-id="6eeca-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="6eeca-131">Ces paramètres ne peuvent pas être modifiés lorsque l'ordre de travail est actif.</span><span class="sxs-lookup"><span data-stu-id="6eeca-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="6eeca-132">Par exemple, ils peuvent être modifiés lorsque l'état du cycle de vie de l'ordre de travail change.</span><span class="sxs-lookup"><span data-stu-id="6eeca-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="6eeca-133">La sélection automatique effectuée lors de la création des ordres de travail est basée sur le paramétrage sur la page **Agents de maintenance responsables**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="6eeca-134">Si vous ajoutez ou supprimez des tâches d'ordres de travail après avoir créé un ordre de travail, et si le champ **Groupe responsable** et le champ **Responsable** sont vides lorsque vous mettez à jour l'ordre de travail, le module Gestion des actifs essaie de rechercher un groupe d'agents de maintenance responsable ou un agent de maintenance responsable pour une correspondance possible sur la page de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="6eeca-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="6eeca-135">Si le champ **Groupe responsable** ou **Responsable** est déjà renseigné lorsque vous mettez un ordre de travail à jour, aucune modification n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="6eeca-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="6eeca-136">Pour plus d'informations sur les agents de maintenance responsables et les groupes collaborateurs, voir [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="6eeca-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="6eeca-137">Sur la page [Statut de maintenance](../controlling-and-reporting/maintenance-status.md), vous pouvez effectuer un calcul pour obtenir une vue d'ensemble de la charge de travail concernant les ordres de travail entrants et terminés.</span><span class="sxs-lookup"><span data-stu-id="6eeca-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="6eeca-138">Dans la vue détaillée de la page **Tous les ordres de travail**, sous l'organisateur **Détails de la ligne**, vous pouvez utiliser les champs **Latitude** et **Longitude** pour ajouter des coordonnées géographiques pour l'actif sélectionné sur la tâche d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="6eeca-139">Créer un ordre de travail associé</span><span class="sxs-lookup"><span data-stu-id="6eeca-139">Create related work order</span></span>

<span data-ttu-id="6eeca-140">Vous pouvez créer un ordre de travail associé à un ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="6eeca-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="6eeca-141">Cette capacité est utile si, par exemple, vous souhaitez utiliser des ordres de travail principaux et secondaires.</span><span class="sxs-lookup"><span data-stu-id="6eeca-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="6eeca-142">Un nouvel ordre de travail est basé sur une tâche d'ordre de travail depuis un ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="6eeca-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="6eeca-143">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6eeca-144">Sélectionnez l'ordre de travail pour lequel créer un ordre de travail associé.</span><span class="sxs-lookup"><span data-stu-id="6eeca-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="6eeca-145">Dans le volet Actions, sous l'onglet **Ordre de travail**, dans le groupe **Nouveau**, sélectionnez **Ordre de travail associé**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="6eeca-146">Dans la boîte de dialogue **Créer un ordre de travail associé**, dans le champ **Tâche d'ordre de travail**, sélectionnez l'ordre de travail pour lequel créer un ordre de travail associé.</span><span class="sxs-lookup"><span data-stu-id="6eeca-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="6eeca-147">Sélectionnez un type de tâche de maintenance dans le champ **Type de tâche de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="6eeca-148">Sélectionnez une variante et une transaction associées au type de tâche de maintenance dans les champs **Variante du type de tâche de maintenance** et **Transaction**; au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="6eeca-149">Si cet ordre de travail est le premier ordre de travail associé créé pour l'ordre de travail sélectionné, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6eeca-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="6eeca-150">Sélectionnez l'option **Nouvel ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="6eeca-151">Dans le champ **Type d'ordre de travail**, sélectionnez un type d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="6eeca-152">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="6eeca-153">Dans le champ **Niveau de service**, modifiez le niveau de service des ordres de travail au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="6eeca-154">Dans les champs **Début prévu** et **Fin prévue**, sélectionnez les dates de début et de fin prévues.</span><span class="sxs-lookup"><span data-stu-id="6eeca-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="6eeca-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-155">Select **OK**.</span></span> <span data-ttu-id="6eeca-156">Le nouvel ordre de travail associé est affiché sur la page de liste **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="6eeca-157">Si l'ordre de travail pour lequel vous créez cet ordre de travail associé a déjà des ordres de travail associés, procédez comme suit pour ajouter une nouvelle tâche d'ordre de travail à un ordre de travail associé existant :</span><span class="sxs-lookup"><span data-stu-id="6eeca-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="6eeca-158">Sélectionnez l'option **Ajouter à l'ordre de travail associé**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="6eeca-159">Dans le champ **Ordre de travail**, sélectionnez l'ordre de travail associé auquel vous souhaitez ajouter une nouvelle tâche d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="6eeca-160">Dans le champ **Niveau de service**, modifiez le niveau de service des ordres de travail au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="6eeca-161">Dans les champs **Début prévu** et **Fin prévue**, modifiez les dates de début et de fin prévues au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="6eeca-162">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-162">Select **OK**.</span></span> <span data-ttu-id="6eeca-163">La tâche de l'ordre de travail est ajoutée à l'ordre de travail associé existant.</span><span class="sxs-lookup"><span data-stu-id="6eeca-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="6eeca-164">L'illustration suivante présente un exemple de la boîte de dialogue **Créer un ordre de travail associé**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Figure 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="6eeca-166">Si vous avez configuré un masque d'ordre de travail associé dans **Paramètres de gestion des actifs** > **onglet Ordres de travail** > **Masque de l'ordre de travail associé**, les ID des ordres de travail sont créés selon la configuration du masque.</span><span class="sxs-lookup"><span data-stu-id="6eeca-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="6eeca-167">Si aucun masque de l'ordre de travail associé n'est configuré, l'ID de l'ordre de travail suivant disponible est utilisé pour les ordres de travail associés.</span><span class="sxs-lookup"><span data-stu-id="6eeca-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="6eeca-168">Copier un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="6eeca-168">Copy a work order</span></span>

<span data-ttu-id="6eeca-169">Vous pouvez créer rapidement un ordre de travail depuis un ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="6eeca-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="6eeca-170">Cette manière d'utiliser les ordres de travail diffère de la création des ordres de travail selon les [plans de maintenance](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="6eeca-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="6eeca-171">Cela est utile si, par exemple, un ordre de travail contient de nombreuses tâches d'ordre de travail et que les différentes tâches doivent être effectuées sur différents actifs à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="6eeca-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="6eeca-172">Sélectionnez **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6eeca-173">Sélectionnez l'ordre de travail à partir duquel copier le contenu.</span><span class="sxs-lookup"><span data-stu-id="6eeca-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="6eeca-174">Dans le volet Actions > onglet **Ordre de travail** > groupe **Nouveau**, sélectionnez **Copier l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="6eeca-175">Le paramétrage des ordres de travail depuis l'ordre de travail sélectionné s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6eeca-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="6eeca-176">Vous pouvez modifier certains champs, au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="6eeca-177">Sélectionnez **OK** pour créer l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="6eeca-178">Dans la page de liste **Tous les ordres de travail**, vous pouvez modifier l'ordre de travail comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="6eeca-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="6eeca-179">Lorsque l'ordre des travail est créé, certaines informations sont copiées directement depuis l'ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="6eeca-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="6eeca-180">Les informations sur les prévisions, les outils, les listes de contrôle de maintenance, le poste technique, les adresses et la planification ne sont pas copiées.</span><span class="sxs-lookup"><span data-stu-id="6eeca-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="6eeca-181">Au lieu de cela, elles ont initialisées par le paramétrage actuel du module Gestion d'actifs.</span><span class="sxs-lookup"><span data-stu-id="6eeca-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="6eeca-182">Par conséquent, si ces informations ont été modifiées entre le moment où le premier ordre de travail a été créé et le moment où vous avez créé une copie de l'ordre de travail, les modifications sont incluses dans le nouvel ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="6eeca-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="6eeca-183">Des exemples incluent des prévisions ou des mises à jour des listes de contrôle de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6eeca-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="6eeca-184">L'illustration suivante présente un exemple de la boîte de dialogue **Copier un ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Figure 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="6eeca-186">Créer un ordre de travail à partir d'une demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="6eeca-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="6eeca-187">Sélectionnez **Gestion des actifs** > **Commun** > **Demandes de maintenance** > **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="6eeca-188">Sélectionnez la demande de maintenance pour laquelle créer un ordre de travail et cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="6eeca-189">Dans le volet Actions > onglet **Demande de maintenance** > groupe **Nouveau**, sélectionnez **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="6eeca-190">Dans la boîte de dialogue **Ordre de travail**, définissez les champs.</span><span class="sxs-lookup"><span data-stu-id="6eeca-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="6eeca-191">Si un type de tâche de maintenance a été sélectionné dans la demande de maintenance, vous pouvez sélectionner un autre type de tâche de maintenance, lorsque vous créez l'ordre de travail, au besoin.</span><span class="sxs-lookup"><span data-stu-id="6eeca-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="6eeca-192">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-192">Select **OK**.</span></span> <span data-ttu-id="6eeca-193">Un message vous informe qu'un ordre de travail a été créé.</span><span class="sxs-lookup"><span data-stu-id="6eeca-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="6eeca-194">Pour afficher les ordres de travail associés à une demande de maintenance, dans les listes **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, sélectionnez la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6eeca-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="6eeca-195">Ensuite, dans le volet Actions, sous l'onglet **Demande de maintenance**, dans le groupe **Nouveau**, sélectionnez **Ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="6eeca-196">L'illustration suivante présente un exemple de la boîte de dialogue **Créer un ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="6eeca-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Figure 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="6eeca-198">Si vous souhaitez que les ordres de travail soient créés automatiquement, vous pouvez planifier des tâches de plan de maintenance, ou paramétrer la « Création automatique » des [plans de maintenance](../preventive-and-reactive-maintenance/maintenance-plans.md) ou des [visites de maintenance](../preventive-and-reactive-maintenance/maintenance-rounds.md) sur un actif.</span><span class="sxs-lookup"><span data-stu-id="6eeca-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="6eeca-199">Les ordres de travail créés depuis les demandes de maintenance sur la page de liste **Tout le programme de maintenance** sont des types de tâches de maintenance sélectionnés dans les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="6eeca-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>

