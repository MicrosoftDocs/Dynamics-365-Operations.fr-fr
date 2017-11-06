--- 
title: "Créer une règle de kanban à l'aide d'un événement de ligne de kanban"
description: "Cette procédure crée une règle de kanban à l'aide du paramètre d'événement de ligne kanban pour déclencher l'extraction d'une activité de processus."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9ef7b8e920d22cbc4f96676e68a263f2da7f232c
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="49433-103">Créer une règle de kanban à l'aide d'un événement de ligne de kanban</span><span class="sxs-lookup"><span data-stu-id="49433-103">Create a kanban rule using a kanban line event</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="49433-104">Cette procédure crée une règle de kanban à l'aide du paramètre d'événement de ligne kanban pour déclencher l'extraction d'une activité de processus.</span><span class="sxs-lookup"><span data-stu-id="49433-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="49433-105">La règle de kanban est déclenchée par une activité de processus kanban, avec une quantité égale ou supérieure à 25 pour chaque.</span><span class="sxs-lookup"><span data-stu-id="49433-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="49433-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="49433-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="49433-107">Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié dans un environnement lean.</span><span class="sxs-lookup"><span data-stu-id="49433-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="49433-108">Création d'une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="49433-108">Create a kanban rule</span></span>
1. <span data-ttu-id="49433-109">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="49433-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="49433-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="49433-110">Click New.</span></span>
3. <span data-ttu-id="49433-111">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».</span><span class="sxs-lookup"><span data-stu-id="49433-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="49433-112">Des kanbans sont alors générés directement à partir de la demande.</span><span class="sxs-lookup"><span data-stu-id="49433-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="49433-113">Cette option permet de paramétrer les règles qui définissent un scénario de fabrication à la commande.</span><span class="sxs-lookup"><span data-stu-id="49433-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="49433-114">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="49433-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="49433-115">Entrez ou sélectionnez SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="49433-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="49433-116">La première activité d'une règle de kanban de fabrication est une activité de processus dans le flux de production.</span><span class="sxs-lookup"><span data-stu-id="49433-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="49433-117">Lorsque vous sélectionnez l'activité, les dates de validité de l'activité sont copiées dans les dates de validité de la règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="49433-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="49433-118">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="49433-118">Expand the Details section.</span></span>
6. <span data-ttu-id="49433-119">Dans le champ Produit, tapez « L0001 ».</span><span class="sxs-lookup"><span data-stu-id="49433-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="49433-120">Développez la section Événements.</span><span class="sxs-lookup"><span data-stu-id="49433-120">Expand the Events section.</span></span>
8. <span data-ttu-id="49433-121">Dans le champ Événement de ligne de kanban, sélectionnez « Automatique ».</span><span class="sxs-lookup"><span data-stu-id="49433-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="49433-122">Ceci produit des kanbans d'événement à la demande.</span><span class="sxs-lookup"><span data-stu-id="49433-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="49433-123">Ce champ permet de configurer les règles de kanban qui réapprovisionnent les matières requises pour une activité de processus en aval.</span><span class="sxs-lookup"><span data-stu-id="49433-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="49433-124">Quand vous choisissez Automatique, les kanbans d'événement sont créés avec la demande.</span><span class="sxs-lookup"><span data-stu-id="49433-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="49433-125">Ce paramètre est recommandé si vous comptez exécuter la production le même jour.</span><span class="sxs-lookup"><span data-stu-id="49433-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="49433-126">Définissez la quantité d'événement minimale sur « 25 ».</span><span class="sxs-lookup"><span data-stu-id="49433-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="49433-127">Des kanbans d'événement sont créés lorsque la quantité de la demande est égale ou supérieure à ce champ.</span><span class="sxs-lookup"><span data-stu-id="49433-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="49433-128">C'est utile si vous voulez produire une quantité de commande inférieure au montant de ce champ sur une machine et supérieure au montant de ce champ sur une autre machine.</span><span class="sxs-lookup"><span data-stu-id="49433-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="49433-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="49433-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="49433-130">Créer une commande client et déclencher une chaîne kanban</span><span class="sxs-lookup"><span data-stu-id="49433-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="49433-131">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="49433-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="49433-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="49433-132">Click New.</span></span>
3. <span data-ttu-id="49433-133">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="49433-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="49433-134">Sélectionnez le compte client US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="49433-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="49433-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="49433-135">Click OK.</span></span>
5. <span data-ttu-id="49433-136">Entrez « L0001 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="49433-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="49433-137">L0001 représente l'article pour lequel la règle de kanban est créée.</span><span class="sxs-lookup"><span data-stu-id="49433-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="49433-138">Définir la Quantité sur « 27 ».</span><span class="sxs-lookup"><span data-stu-id="49433-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="49433-139">Puisque 27 est supérieur à la quantité minimum de 25 sur la règle de kanban, ceci déclenchera un kanban d'événement.</span><span class="sxs-lookup"><span data-stu-id="49433-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="49433-140">Dans le champ Site, tapez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="49433-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="49433-141">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="49433-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="49433-142">Sélectionner l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="49433-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="49433-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="49433-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="49433-144">Afficher le kanban produit par la règle de kanban</span><span class="sxs-lookup"><span data-stu-id="49433-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="49433-145">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="49433-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="49433-146">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="49433-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="49433-147">Développer la section Kanbans.</span><span class="sxs-lookup"><span data-stu-id="49433-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="49433-148">Notez qu'un kanban pour 27 a été créé pour traiter l'activité basée sur la règle de kanban créée.</span><span class="sxs-lookup"><span data-stu-id="49433-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="49433-149">Il s'agit de la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="49433-149">This is the last step.</span></span>  


