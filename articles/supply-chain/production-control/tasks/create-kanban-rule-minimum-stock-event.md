---
title: Créer une règle de kanban à l'aide d'un événement de stock minimal
description: Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban à l'aide d'un événement de stock minimal pour s'assurer qu'un produit spécifique est toujours disponible à un emplacement spécifique.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a9ba8ec2abb26e3b9ee7e14bdf882c1ffcb205b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311080"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="dd403-103">Créer une règle de kanban à l'aide d'un événement de stock minimal</span><span class="sxs-lookup"><span data-stu-id="dd403-103">Create a kanban rule using a minimum stock event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd403-104">Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban à l'aide d'un événement de stock minimal pour s'assurer qu'un produit spécifique est toujours disponible à un emplacement spécifique.</span><span class="sxs-lookup"><span data-stu-id="dd403-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="dd403-105">Une règle de kanban est créée pour transférer le matériel vers l'emplacement quand le niveau d'inventaire chute en-dessous de 200 pièces.</span><span class="sxs-lookup"><span data-stu-id="dd403-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="dd403-106">L'exécution du traitement de l'événement de l'origine des besoins permet de créer les kanbans nécessaires.</span><span class="sxs-lookup"><span data-stu-id="dd403-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="dd403-107">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="dd403-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="dd403-108">Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié dans un environnement lean.</span><span class="sxs-lookup"><span data-stu-id="dd403-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="dd403-109">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="dd403-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="dd403-110">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="dd403-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="dd403-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="dd403-111">Click New.</span></span>
3. <span data-ttu-id="dd403-112">Sélectionnez Prélèvement dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="dd403-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="dd403-113">Ce type permet de créer des kanbans de transfert.</span><span class="sxs-lookup"><span data-stu-id="dd403-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="dd403-114">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».</span><span class="sxs-lookup"><span data-stu-id="dd403-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="dd403-115">La stratégie d'événement est utilisée pour créer le transfert des kanbans selon un événement.</span><span class="sxs-lookup"><span data-stu-id="dd403-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="dd403-116">Plus tard dans la procédure, vous déclencherez des kanbans de transfert à l'aide du réapprovisionnement de stock.</span><span class="sxs-lookup"><span data-stu-id="dd403-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="dd403-117">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="dd403-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="dd403-118">Entrez ou sélectionnez ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="dd403-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="dd403-119">Cette activité de transfert a l'entrepôt de sortie et l'emplacement 12, ce qui signifie que les matériaux sont déplacés vers l'emplacement 12 dans l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="dd403-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="dd403-120">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="dd403-120">Expand the Details section.</span></span>
7. <span data-ttu-id="dd403-121">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dd403-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="dd403-122">Sélectionnez M0007.</span><span class="sxs-lookup"><span data-stu-id="dd403-122">Select M0007.</span></span>  
8. <span data-ttu-id="dd403-123">Développez la section Événements.</span><span class="sxs-lookup"><span data-stu-id="dd403-123">Expand the Events section.</span></span>
9. <span data-ttu-id="dd403-124">Sélectionnez « Traitement par lots » dans le champ Événement de réapprovisionnement de stock.</span><span class="sxs-lookup"><span data-stu-id="dd403-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="dd403-125">Ceci crée des kanbans pour répondre aux besoins en matériaux à l'emplacement associé pendant le traitement d'événement de l'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="dd403-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="dd403-126">Définissez la quantité minimale pour l'article.</span><span class="sxs-lookup"><span data-stu-id="dd403-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="dd403-127">Cliquez pour suivre le lien dans le champ Produit.</span><span class="sxs-lookup"><span data-stu-id="dd403-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="dd403-128">Cliquez pour suivre le lien dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="dd403-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="dd403-129">Augmentez le récapitulatif de l'image du produit.</span><span class="sxs-lookup"><span data-stu-id="dd403-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="dd403-130">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="dd403-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="dd403-131">Cliquez sur Couverture de l'article.</span><span class="sxs-lookup"><span data-stu-id="dd403-131">Click Item coverage.</span></span>
6. <span data-ttu-id="dd403-132">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="dd403-132">Click New.</span></span>
7. <span data-ttu-id="dd403-133">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd403-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="dd403-134">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="dd403-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="dd403-135">Définissez Entrepôt sur 12.</span><span class="sxs-lookup"><span data-stu-id="dd403-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="dd403-136">Définissez Minimum sur 200.</span><span class="sxs-lookup"><span data-stu-id="dd403-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="dd403-137">Exécuter le job de création d'événement de traitement par lots</span><span class="sxs-lookup"><span data-stu-id="dd403-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="dd403-138">Allez dans Contrôle de la production > Tâches périodiques > Traitement par lots de tâche de Kanban > Traitement d'événements d'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="dd403-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="dd403-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="dd403-139">Click OK.</span></span>
3. <span data-ttu-id="dd403-140">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="dd403-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="dd403-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="dd403-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="dd403-142">Sélectionnez la règle de kanban créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="dd403-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="dd403-143">Développer la section Kanbans.</span><span class="sxs-lookup"><span data-stu-id="dd403-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="dd403-144">Notez qu'un kanban a été créé pour transférer le matériel nécessaire vers l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="dd403-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  

