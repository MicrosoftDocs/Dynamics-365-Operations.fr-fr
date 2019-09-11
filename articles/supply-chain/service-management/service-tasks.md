---
title: Vue d'ensemble des tâches de service
description: Les tâches de service permettent de décrire la tâche à accomplir lors d'une commande de service. Les techniciens comme les clients ont accès à ces informations.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd7e5293ef506c6d785b420824f2c2a2c96112f7
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865891"
---
# <a name="service-tasks-overview"></a><span data-ttu-id="c986c-104">Vue d'ensemble des tâches de service</span><span class="sxs-lookup"><span data-stu-id="c986c-104">Service tasks overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c986c-105">Les tâches de service permettent de décrire la tâche à accomplir lors d'une commande de service.</span><span class="sxs-lookup"><span data-stu-id="c986c-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="c986c-106">Les techniciens comme les clients ont accès à ces informations.</span><span class="sxs-lookup"><span data-stu-id="c986c-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="c986c-107">Créez des tâches de service dans la page **Tâches de service**, puis associez-les à un accord de service ou une commande de service spécifique en créant des relations de tâches de service.</span><span class="sxs-lookup"><span data-stu-id="c986c-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="c986c-108">Chaque fois que vous créez une relation de tâches de service, vous pouvez créer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c986c-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="c986c-109">des notes internes relatives à la tâche, telles que des requêtes techniques détaillées que le technicien doit connaître ;</span><span class="sxs-lookup"><span data-stu-id="c986c-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="c986c-110">des notes externes que le client peut consulter.</span><span class="sxs-lookup"><span data-stu-id="c986c-110">External notes that the customer can see.</span></span> <span data-ttu-id="c986c-111">Celles-ci peuvent fournir des informations moins techniques sur la tâche en cours d'exécution, conformément à l'accord conclu entre le client et la société de service.</span><span class="sxs-lookup"><span data-stu-id="c986c-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="c986c-112">Dès que vous avez paramétré une relation de tâches de service entre une tâche de service et une commande ou un accord de service, vous pouvez spécifier cette tâche de service lors de la création de lignes de commande de service ou de lignes d'accord de service pour la commande de service active ou l'accord de service actif.</span><span class="sxs-lookup"><span data-stu-id="c986c-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="c986c-113">Lorsque vous générez des commandes de service à partir d'un accord de service, vous pouvez utiliser les tâches de service affectées à chaque ligne d'accord de service afin de regrouper les lignes de commande de service dans des commandes de service.</span><span class="sxs-lookup"><span data-stu-id="c986c-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="c986c-114">Créer une tâche de service</span><span class="sxs-lookup"><span data-stu-id="c986c-114">Create a service task</span></span>

1. <span data-ttu-id="c986c-115">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Tâches de service**.</span><span class="sxs-lookup"><span data-stu-id="c986c-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="c986c-116">Créez une ligne.</span><span class="sxs-lookup"><span data-stu-id="c986c-116">Create a new line.</span></span>
3. <span data-ttu-id="c986c-117">Entrez l'ID et la description du service.</span><span class="sxs-lookup"><span data-stu-id="c986c-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="c986c-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="c986c-118">Example</span></span>

<span data-ttu-id="c986c-119">Un technicien doit accomplir deux tâches au niveau d'un système d'engrenages (objet de service GB-1234) sur le site du client.</span><span class="sxs-lookup"><span data-stu-id="c986c-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="c986c-120">Un accord de service est créé pour le client, et plusieurs transactions sont associées aux tâches.</span><span class="sxs-lookup"><span data-stu-id="c986c-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="c986c-121">L'accord de service et les lignes de l'accord de service pour les deux tâches se présentent comme suit :</span><span class="sxs-lookup"><span data-stu-id="c986c-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="c986c-122">Accord de service</span><span class="sxs-lookup"><span data-stu-id="c986c-122">Service agreement</span></span>

| <span data-ttu-id="c986c-123">Projet</span><span class="sxs-lookup"><span data-stu-id="c986c-123">Project</span></span> | <span data-ttu-id="c986c-124">Accord de service</span><span class="sxs-lookup"><span data-stu-id="c986c-124">Service agreement</span></span> | <span data-ttu-id="c986c-125">Description </span><span class="sxs-lookup"><span data-stu-id="c986c-125">Description</span></span>                                  | <span data-ttu-id="c986c-126">Regrouper</span><span class="sxs-lookup"><span data-stu-id="c986c-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="c986c-127">9012</span><span class="sxs-lookup"><span data-stu-id="c986c-127">9012</span></span>    | <span data-ttu-id="c986c-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="c986c-128">000008\_001</span></span>       | <span data-ttu-id="c986c-129">Inspection et remplacement de routine – GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="c986c-130">Prime</span><span class="sxs-lookup"><span data-stu-id="c986c-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="c986c-131">Lignes d'accord de service</span><span class="sxs-lookup"><span data-stu-id="c986c-131">Service agreement lines</span></span>

| <span data-ttu-id="c986c-132">Description </span><span class="sxs-lookup"><span data-stu-id="c986c-132">Description</span></span>             | <span data-ttu-id="c986c-133">Type de transaction</span><span class="sxs-lookup"><span data-stu-id="c986c-133">Transaction type</span></span> | <span data-ttu-id="c986c-134">Objet du service</span><span class="sxs-lookup"><span data-stu-id="c986c-134">Service object</span></span> | <span data-ttu-id="c986c-135">Tâche de service</span><span class="sxs-lookup"><span data-stu-id="c986c-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="c986c-136">Inspection et nettoyage</span><span class="sxs-lookup"><span data-stu-id="c986c-136">Inspection and cleaning</span></span> | <span data-ttu-id="c986c-137">Heure</span><span class="sxs-lookup"><span data-stu-id="c986c-137">Hour</span></span>             | <span data-ttu-id="c986c-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-138">GB-1234</span></span>        | <span data-ttu-id="c986c-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-139">I/C - GB1234</span></span> |
| <span data-ttu-id="c986c-140">Déplacements</span><span class="sxs-lookup"><span data-stu-id="c986c-140">Travel</span></span>                  | <span data-ttu-id="c986c-141">Dépense</span><span class="sxs-lookup"><span data-stu-id="c986c-141">Expense</span></span>          | <span data-ttu-id="c986c-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-142">GB-1234</span></span>        | <span data-ttu-id="c986c-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-143">I/C - GB1234</span></span> |
| <span data-ttu-id="c986c-144">Matériaux</span><span class="sxs-lookup"><span data-stu-id="c986c-144">Materials</span></span>               | <span data-ttu-id="c986c-145">Article</span><span class="sxs-lookup"><span data-stu-id="c986c-145">Item</span></span>             | <span data-ttu-id="c986c-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-146">GB-1234</span></span>        | <span data-ttu-id="c986c-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-147">I/C - GB1234</span></span> |
| <span data-ttu-id="c986c-148">Remplacement de routine</span><span class="sxs-lookup"><span data-stu-id="c986c-148">Routine replacement</span></span>     | <span data-ttu-id="c986c-149">Heure</span><span class="sxs-lookup"><span data-stu-id="c986c-149">Hour</span></span>             | <span data-ttu-id="c986c-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-150">GB-1234</span></span>        | <span data-ttu-id="c986c-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-151">RR - GB1234</span></span>  |
| <span data-ttu-id="c986c-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="c986c-152">GR-1</span></span>                    | <span data-ttu-id="c986c-153">Article</span><span class="sxs-lookup"><span data-stu-id="c986c-153">Item</span></span>             | <span data-ttu-id="c986c-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-154">GB-1234</span></span>        | <span data-ttu-id="c986c-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-155">RR - GB1234</span></span>  |
| <span data-ttu-id="c986c-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="c986c-156">GR-5</span></span>                    | <span data-ttu-id="c986c-157">Article</span><span class="sxs-lookup"><span data-stu-id="c986c-157">Item</span></span>             | <span data-ttu-id="c986c-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-158">GB-1234</span></span>        | <span data-ttu-id="c986c-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-159">RR - GB1234</span></span>  |

<span data-ttu-id="c986c-160">Deux tâches de service sont associées aux lignes d'accord de service des deux tâches.</span><span class="sxs-lookup"><span data-stu-id="c986c-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="c986c-161">Ces tâches de service permettent de déterminer les transactions propres à chaque tâche.</span><span class="sxs-lookup"><span data-stu-id="c986c-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="c986c-162">Dans le premier cas, la tâche de service I/C - GB1234 caractérise toutes les lignes d'accord de service impliquées dans l'inspection et le nettoyage de l'objet GB-1234.</span><span class="sxs-lookup"><span data-stu-id="c986c-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="c986c-163">Dans le deuxième cas, la tâche de service RR - GB1234 caractérise toutes les lignes d'accord de service impliquées dans l'exécution d'une tâche de remplacement de routine.</span><span class="sxs-lookup"><span data-stu-id="c986c-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="c986c-164">Les relations de tâches de service qui lient les tâches de service à l'accord spécifique se présentent comme suit :</span><span class="sxs-lookup"><span data-stu-id="c986c-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="c986c-165">Tâches de service</span><span class="sxs-lookup"><span data-stu-id="c986c-165">Service tasks</span></span>

| <span data-ttu-id="c986c-166">Tâche de service</span><span class="sxs-lookup"><span data-stu-id="c986c-166">Service task</span></span> | <span data-ttu-id="c986c-167">Description </span><span class="sxs-lookup"><span data-stu-id="c986c-167">Description</span></span>                             | <span data-ttu-id="c986c-168">Note interne</span><span class="sxs-lookup"><span data-stu-id="c986c-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="c986c-169">Note externe</span><span class="sxs-lookup"><span data-stu-id="c986c-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="c986c-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-170">I/C - GB1234</span></span> | <span data-ttu-id="c986c-171">Inspection du système d'engrenages GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="c986c-172">Inspection visuelle et mécanique et nettoyage du système d'engrenages GB-1234.</span><span class="sxs-lookup"><span data-stu-id="c986c-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="c986c-173">Inspection de routine du système d'engrenages</span><span class="sxs-lookup"><span data-stu-id="c986c-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="c986c-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="c986c-174">RR - GB1234</span></span>  | <span data-ttu-id="c986c-175">Remplacement de routine de pièces du système d'engrenages GB-1234</span><span class="sxs-lookup"><span data-stu-id="c986c-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="c986c-176">Remplacement de service de routine des composants GR-1 et GR-5 (pour les systèmes d'engrenages fabriqués avant 2002, remplacer également le composant GR-2)</span><span class="sxs-lookup"><span data-stu-id="c986c-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="c986c-177">Remplacement de routine des pièces</span><span class="sxs-lookup"><span data-stu-id="c986c-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="c986c-178">Regrouper les commandes de service</span><span class="sxs-lookup"><span data-stu-id="c986c-178">Group service orders</span></span>

<span data-ttu-id="c986c-179">Lors de la création automatique de commandes de service, vous pouvez utiliser les tâches de service comme critères de regroupement.</span><span class="sxs-lookup"><span data-stu-id="c986c-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="c986c-180">Pour regrouper des commandes de service par tâches de service, vous devez spécifier dans l'accord de service que les commandes de service basées sur cet accord de service doivent être regroupées par ID de tâche de service comme critères de regroupement initial.</span><span class="sxs-lookup"><span data-stu-id="c986c-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="c986c-181">**Regroupement par tâche de service**</span><span class="sxs-lookup"><span data-stu-id="c986c-181">**Group by service task**</span></span>

1. <span data-ttu-id="c986c-182">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="c986c-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="c986c-183">Dans l'onglet **Paramétrage**, sélectionnez **Par tâche de service** dans le champ **Combiner les commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="c986c-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>


