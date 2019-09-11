---
title: Ordres de travail créés manuellement
description: Cette rubrique explique comment créer des ordres de travail manuellement dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875650"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="fd659-103">Ordres de travail créés manuellement</span><span class="sxs-lookup"><span data-stu-id="fd659-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="fd659-104">Vous pouvez créer des ordres de travail manuellement de deux façons :</span><span class="sxs-lookup"><span data-stu-id="fd659-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="fd659-105">dans **Tous les ordres de travail** ou **Ordres de travail actifs**</span><span class="sxs-lookup"><span data-stu-id="fd659-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="fd659-106">dans **Toutes les demandes de maintenance** ou **Demandes de maintenance actives** ou **Mes demandes de maintenance de poste technique**.</span><span class="sxs-lookup"><span data-stu-id="fd659-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="fd659-107">Créer un ordre de travail</span><span class="sxs-lookup"><span data-stu-id="fd659-107">Create work order</span></span>

1. <span data-ttu-id="fd659-108">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="fd659-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fd659-109">Cliquez sur le bouton **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fd659-109">Click the **New** button.</span></span>

3. <span data-ttu-id="fd659-110">Dans le menu déroulant **Créer le bon de travail**, sélectionnez un type d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="fd659-111">Le cas échéant, sélectionnez une description.</span><span class="sxs-lookup"><span data-stu-id="fd659-111">If required, select a description.</span></span>

5. <span data-ttu-id="fd659-112">Sélectionnez l'actif pour l'ordre de travail ainsi que le type de tâche de maintenance.</span><span class="sxs-lookup"><span data-stu-id="fd659-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="fd659-113">Lorsque vous sélectionnez un actif, trois onglets peuvent être disponibles : L'onglet **Mes actifs** contient des actifs associés à des postes techniques dans lesquels vous (l'agent de maintenance connecté au système) pouvez être affecté(e) (configuré dans [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="fd659-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="fd659-114">Si aucun poste technique n'est paramétré sur un agent de maintenance dans l'écran [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md), l'onglet **Mes actifs** ne sera pas visible.</span><span class="sxs-lookup"><span data-stu-id="fd659-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="fd659-115">L'onglet **Actifs actifs** contient la liste de tous les actifs avec l'état de cycle de vie de l'actif « Actif ».</span><span class="sxs-lookup"><span data-stu-id="fd659-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="fd659-116">L'onglet **Vue des actifs** affiche une arborescence des postes techniques et des actifs installés sur ces emplacements.</span><span class="sxs-lookup"><span data-stu-id="fd659-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="fd659-117">Si nécessaire, sélectionnez **Variante de type de tâche de maintenance** et **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="fd659-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="fd659-118">Si nécessaire, vous pouvez modifier le niveau de service des ordres de travail dans le champ **Niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="fd659-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="fd659-119">Sélectionnez les dates de début et de fin prévues dans les champs associés.</span><span class="sxs-lookup"><span data-stu-id="fd659-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="fd659-120">Cliquez sur **OK** pour créer un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="fd659-121">Modifiez l'ordre de travail dans **Tous les ordres de travail**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fd659-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="fd659-122">Dans **Tous les ordres de travail**, vous pouvez ajouter plusieurs actifs à un ordre de travail dans la vue détaillée en ajoutant des lignes sur l'organisateur **Tâches de maintenance des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="fd659-123">Sur un actif, vous ne pouvez sélectionner que les types de tâche de maintenance définis sur le type d'actif sélectionné pour l'actif.</span><span class="sxs-lookup"><span data-stu-id="fd659-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="fd659-124">Si vous avez modifié un niveau de service d'actif ou un élément critique d'actif après les avoir utilisés sur un ordre de travail (consultez [Niveaux de service d'actif](../setup-for-objects/object-priorities.md) associez et [Criticalities d'immobilisation](../setup-for-objects/object-criticalities.md)), le niveau de service ou l'élément critique sur l'ordre de travail qui n'est pas mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="fd659-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="fd659-125">L'élément critique sur un ordre de travail est recalculé chaque fois qu'une ligne d'ordre de travail est ajoutée ou supprimée de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="fd659-126">Dans la vue détaillée **Tous les ordres de travail** Vue détaillée > vue **En-tête** > organisateur **Programme**, vous pouvez sélectionner un groupe d'agents de maintenance responsable ou un agent de maintenance responsable dans les champs **Groupe responsable** ou **Responsable**.</span><span class="sxs-lookup"><span data-stu-id="fd659-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="fd659-127">Ces paramètres peuvent être modifiés dans la mesure où l'ordre de travail est actif, par exemple, lorsque l'état du cycle de vie de l'ordre de travail change.</span><span class="sxs-lookup"><span data-stu-id="fd659-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="fd659-128">La sélection automatique effectuée lors de la création des ordres de travail est basée sur le paramétrage dans **Agents de maintenance responsables**.</span><span class="sxs-lookup"><span data-stu-id="fd659-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="fd659-129">Si vous ajoutez ou supprimez des tâches d'ordres de travail après avoir créé un ordre de travail, et si le champ **Groupe responsable** et le champ **Responsable** sont vides lorsque vous mettez à jour l'ordre de travail, le module Gestion des actifs recherche une correspondance possible dans le formulaire de paramétrage pour un groupe d'agents de maintenance responsable ou un agent de maintenance responsable.</span><span class="sxs-lookup"><span data-stu-id="fd659-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="fd659-130">Si le champ **Groupe responsable** ou le champ **Responsable** est déjà rempli lorsque vous mettez un ordre de travail à jour, aucune modification n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="fd659-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="fd659-131">Dans **Statut de maintenance**, vous pouvez effectuer un calcul pour obtenir une vue d'ensemble de la charge de travail concernant les ordres de travail entrants et terminés.</span><span class="sxs-lookup"><span data-stu-id="fd659-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="fd659-132">Dans l'organisateur **Détails de ligne**, utilisez les champs **Latitude** et **Longitude** pour ajouter des coordonnées géographiques pour l'actif sélectionné sur la tâche de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="fd659-133">Créer un ordre de travail associé</span><span class="sxs-lookup"><span data-stu-id="fd659-133">Create related work order</span></span>

<span data-ttu-id="fd659-134">Vous pouvez créer un ordre de travail associé à un ordre de travail existant, par exemple, si vous souhaitez travailler avec les ordres de travail principaux et secondaires.</span><span class="sxs-lookup"><span data-stu-id="fd659-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="fd659-135">Un nouvel ordre de travail est basé sur une tâche d'ordre de travail depuis un ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="fd659-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="fd659-136">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="fd659-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fd659-137">Sélectionnez l'ordre de travail pour lequel vous souhaitez effectuer un ordre de travail associé.</span><span class="sxs-lookup"><span data-stu-id="fd659-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="fd659-138">Cliquez sur **Ordre de travail associé**.</span><span class="sxs-lookup"><span data-stu-id="fd659-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="fd659-139">Dans la boîte de dialogue de menu déroulant **Créer un ordre de travail associé**, sélectionnez la tâche de l'ordre de travail pour laquelle vous souhaitez créer un ordre de travail associé dans le champ **Tâche de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="fd659-140">Sélectionnez un type de tâche de maintenance dans le champ **Type de tâche de maintenance** et, le cas échéant, une variante du type de tâche de maintenance associée et la transaction dans les champs **Variante de type de tâche de maintenance** et **Transaction**.</span><span class="sxs-lookup"><span data-stu-id="fd659-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="fd659-141">Si c'est le premier ordre de travail associé effectué, cliquez sur la case d'option **Nouvel ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="fd659-142">Sélectionnez un **Type d'ordre de travail** et une **Description** dans les champs associés.</span><span class="sxs-lookup"><span data-stu-id="fd659-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="fd659-143">Si nécessaire, modifiez le niveau de service des ordres de travail dans le champ **Niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="fd659-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="fd659-144">Insérez les dates de début et de fin prévues dans les champs associés.</span><span class="sxs-lookup"><span data-stu-id="fd659-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="fd659-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd659-145">Click **OK**.</span></span> <span data-ttu-id="fd659-146">Le nouvel ordre de travail associé est affiché dans la liste **Tous les ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="fd659-147">Si vous créez un ordre de travail associé sur un ordre de travail qui a déjà des ordres de travail associés, vous pouvez ajouter la tâche de l'ordre de travail à un ordre de travail déjà associé.</span><span class="sxs-lookup"><span data-stu-id="fd659-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="fd659-148">Cela est effectué en cliquant sur la case d'option **Ajouter à l'ordre de travail associé** à l'étape 6.</span><span class="sxs-lookup"><span data-stu-id="fd659-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="fd659-149">Puis vous sélectionnez l'ordre de travail associé auquel vous souhaitez ajouter une nouvelle tâche d'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="fd659-150">Modifiez les champs **Niveau de service**, **Début prévu** et **Fin prévue**, le cas échéant, et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd659-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="fd659-151">La tâche de l'ordre de travail est ajoutée à l'ordre de travail associé existant.</span><span class="sxs-lookup"><span data-stu-id="fd659-151">The work order job is added to the existing related work order.</span></span>


![Figure 1](media/03-work-orders.png)

<span data-ttu-id="fd659-153">**Remarque :** Si vous avez configuré un masque d'ordre de travail associé dans **Paramètres de gestion des actifs** > **Ordres de travail** lien > **Masque de l'ordre de travail associé**, les ID des ordres de travail seront créés selon la configuration du masque.</span><span class="sxs-lookup"><span data-stu-id="fd659-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="fd659-154">Si aucun masque de l'ordre de travail associé n'est configuré, l'ID de l'ordre de travail suivant disponible sera utilisé pour les ordres de travail associés.</span><span class="sxs-lookup"><span data-stu-id="fd659-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="fd659-155">Copier l'ordre de travail</span><span class="sxs-lookup"><span data-stu-id="fd659-155">Copy work order</span></span>

<span data-ttu-id="fd659-156">Il est possible de créer rapidement un ordre de travail récents depuis un ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="fd659-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="fd659-157">Cette manière d'utiliser les ordres de travail diffère de la création des ordres de travail selon les plans de maintenance.</span><span class="sxs-lookup"><span data-stu-id="fd659-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="fd659-158">Cela est utile si, par exemple, vous avez un ordre de travail contenant de nombreuses tâches d'ordre de travail avec différentes tâches sur différents actifs qui doivent être terminées à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="fd659-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="fd659-159">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="fd659-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fd659-160">Sélectionnez l'ordre de travail à partir duquel vous souhaitez copier le contenu.</span><span class="sxs-lookup"><span data-stu-id="fd659-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="fd659-161">Cliquez sur **Copier l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-161">Click **Copy work order**.</span></span> <span data-ttu-id="fd659-162">Le paramétrage des ordres de travail depuis l'ordre de travail sélectionné s'affiche.</span><span class="sxs-lookup"><span data-stu-id="fd659-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="fd659-163">Si nécessaire, vous pouvez modifier certains champs.</span><span class="sxs-lookup"><span data-stu-id="fd659-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="fd659-164">Cliquez sur **OK** pour créer l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="fd659-165">Modifiez l'ordre de travail dans **Tous les ordres de travail**, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fd659-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="fd659-166">Lorsque l'ordre des travail est créé, certaines informations sont copiées directement depuis l'ordre de travail existant.</span><span class="sxs-lookup"><span data-stu-id="fd659-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="fd659-167">Les informations concernant les prévisions, les outils, les listes de contrôle de maintenance, le poste technique, les adresses et la planification ne sont pas copiés, mais initialisés depuis le paramétrage actuel dans le module Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="fd659-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="fd659-168">Cela signifie que si des modifications ont été apportées à ces données à la création du premier ordre de travail jusqu'à ce que vous effectuiez une copie de l'ordre de travail, ces modifications sont incluses dans le nouvel ordre de travail que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="fd659-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="fd659-169">Des exemples de modifications sont les prévisions ou les listes de contrôle de maintenance mises à jour.</span><span class="sxs-lookup"><span data-stu-id="fd659-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Figure 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="fd659-171">Créer un ordre de travail à partir d'une demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="fd659-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="fd659-172">Cliquez sur **Gestion des actifs** > **Commun** > **Demandes de maintenance** > **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="fd659-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="fd659-173">Sélectionnez la demande de maintenance pour laquelle vous souhaitez créer un ordre de travail et cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fd659-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="fd659-174">Dans **Tous les demandes**, cliquez sur **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="fd659-175">Complétez le menu déroulant **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="fd659-176">Si un type de tâche de maintenance a été sélectionné dans la demande de maintenance, vous pouvez sélectionner un autre type de tâche de maintenance, au besoin, lorsque vous créez l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="fd659-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="fd659-177">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd659-177">Click **OK**.</span></span> <span data-ttu-id="fd659-178">Vous allez voir un message vous informant que l'ordre de travail a été créé.</span><span class="sxs-lookup"><span data-stu-id="fd659-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="fd659-179">Si vous souhaitez afficher les ordres de travail qui sont associés à une demande de maintenance, sélectionnez la demande de maintenance dans les listes **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**, puis cliquez sur le bouton **Ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="fd659-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Figure 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="fd659-181">Les ordres de travail peuvent également être créés automatiquement lors de la planification des tâches de plan de maintenance, ou en paramétrant la « Création automatique » des plans de maintenance ou des visites de maintenance sur un actif.</span><span class="sxs-lookup"><span data-stu-id="fd659-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="fd659-182">Les ordres de travail créés depuis les demandes de maintenance dans **Programme de maintenance** sont créés avec des types de tâches de maintenance sélectionnés dans les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="fd659-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

