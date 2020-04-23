---
title: Créer une règle de kanban d'événement de ligne de nomenclature
description: Cette tâche se concentre sur le paramétrage nécessaire pour créer une règle de kanban d'événement pour vérifier l'approvisionnement des lignes de nomenclature de production dans un environnement de fabrication en mode mixte et classique.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 698b7af3bc8e2146aaf86fb5e04dd123ea6d5153
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210914"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="12538-103">Créer une règle de kanban d'événement de ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="12538-103">Create a BOM line event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12538-104">Cette tâche se concentre sur le paramétrage nécessaire pour créer une règle de kanban d'événement pour vérifier l'approvisionnement des lignes de nomenclature de production dans un environnement de fabrication en mode mixte et classique.</span><span class="sxs-lookup"><span data-stu-id="12538-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="12538-105">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="12538-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="12538-106">Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié.</span><span class="sxs-lookup"><span data-stu-id="12538-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="12538-107">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="12538-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="12538-108">Accédez à Contrôle de la production > Tâches périodiques > Calcul de quantité de kanban > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="12538-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="12538-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="12538-109">Click New.</span></span>
3. <span data-ttu-id="12538-110">Sélectionnez Prélèvement dans le champ Type.</span><span class="sxs-lookup"><span data-stu-id="12538-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="12538-111">Le type de prélèvement permet de créer des kanbans de transfert.</span><span class="sxs-lookup"><span data-stu-id="12538-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="12538-112">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».</span><span class="sxs-lookup"><span data-stu-id="12538-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="12538-113">La stratégie d'événement est activée pour créer le transfert des kanbans selon un événement.</span><span class="sxs-lookup"><span data-stu-id="12538-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="12538-114">Plus loin dans le guide de tâche, nous le déclencherons en estimant un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="12538-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="12538-115">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="12538-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="12538-116">Entrez ou sélectionnez ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="12538-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="12538-117">Cette activité de transfert a l'entrepôt de sortie et l'emplacement 12, ce qui signifie que les matériaux sont déplacés vers l'emplacement 12 dans l'entrepôt 12.</span><span class="sxs-lookup"><span data-stu-id="12538-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="12538-118">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="12538-118">Expand the Details section.</span></span>
7. <span data-ttu-id="12538-119">Dans le champ Produit, saisissez ou sélectionnez M0001.</span><span class="sxs-lookup"><span data-stu-id="12538-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="12538-120">Développez la section Événements.</span><span class="sxs-lookup"><span data-stu-id="12538-120">Expand the Events section.</span></span>
9. <span data-ttu-id="12538-121">Dans le champ Événement de ligne de nomenclature, sélectionnez « Automatique ».</span><span class="sxs-lookup"><span data-stu-id="12538-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="12538-122">Si le champ Événement de ligne de nomenclature est défini sur Automatique, le kanban est créé pour répondre aux besoins en matériaux pour les lignes de nomenclature de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="12538-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="12538-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12538-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="12538-124">Créer et modifier un nouvel ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="12538-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="12538-125">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="12538-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="12538-126">Cliquez sur Nouvel ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="12538-126">Click New production order.</span></span>
3. <span data-ttu-id="12538-127">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="12538-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="12538-128">Entrez ou sélectionnez L0001.</span><span class="sxs-lookup"><span data-stu-id="12538-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="12538-129">Nous utilisons l'article L0001 car l'article M0001 est inclus dans la nomenclature pour l'article L0001.</span><span class="sxs-lookup"><span data-stu-id="12538-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="12538-130">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="12538-130">Click Create.</span></span>
5. <span data-ttu-id="12538-131">Dans la liste, cliquez sur le lien dans la ligne pour L0001.</span><span class="sxs-lookup"><span data-stu-id="12538-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="12538-132">Cliquez sur Nomenclature.</span><span class="sxs-lookup"><span data-stu-id="12538-132">Click BOM.</span></span>
7. <span data-ttu-id="12538-133">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="12538-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="12538-134">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="12538-134">Click Edit.</span></span>
9. <span data-ttu-id="12538-135">Sélectionnez Approvisionnement invariable dans le champ Type de ligne.</span><span class="sxs-lookup"><span data-stu-id="12538-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="12538-136">L'approvisionnement invariable est sélectionné pour déclencher la création d'approvisionnement d'un kanban.</span><span class="sxs-lookup"><span data-stu-id="12538-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="12538-137">Sélectionnez Non dans le champ Consommation de ressource.</span><span class="sxs-lookup"><span data-stu-id="12538-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="12538-138">Si vous décochez la case à cocher Consommation de ressource cela permet de modifier l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="12538-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="12538-139">Développez la section Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="12538-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="12538-140">Dans le champ Entrepôt, tapez « 12 ».</span><span class="sxs-lookup"><span data-stu-id="12538-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="12538-141">L'entrepôt est défini sur 12 car il s'agit de l'entrepôt de sortie pour l'activité de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12538-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="12538-142">Tapez « 12 » dans le champ Emplacement.</span><span class="sxs-lookup"><span data-stu-id="12538-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="12538-143">L'emplacement est défini sur 12 car il s'agit de l'emplacement de sortie pour l'activité de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="12538-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="12538-144">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12538-144">Close the page.</span></span>
15. <span data-ttu-id="12538-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12538-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="12538-146">Estimer l'ordre de fabrication et afficher le kanban créé</span><span class="sxs-lookup"><span data-stu-id="12538-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="12538-147">Cliquez sur Estimer.</span><span class="sxs-lookup"><span data-stu-id="12538-147">Click Estimate.</span></span>
    * <span data-ttu-id="12538-148">L'estimation de l'ordre de fabrication déclenche la création du kanban associé pour fournir l'article M0001.</span><span class="sxs-lookup"><span data-stu-id="12538-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="12538-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="12538-149">Click OK.</span></span>
3. <span data-ttu-id="12538-150">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12538-150">Close the page.</span></span>
4. <span data-ttu-id="12538-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="12538-151">Close the page.</span></span>
5. <span data-ttu-id="12538-152">Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="12538-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="12538-153">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="12538-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="12538-154">Sélectionnez la règle de kanban d'événement créée pour l'article M0001.</span><span class="sxs-lookup"><span data-stu-id="12538-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="12538-155">Développer la section Kanbans.</span><span class="sxs-lookup"><span data-stu-id="12538-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="12538-156">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="12538-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="12538-157">Notez le kanban créé pour fournir M0001 pour l'ordre de fabrication estimé.</span><span class="sxs-lookup"><span data-stu-id="12538-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="12538-158">Il s'agit de la dernière étape.</span><span class="sxs-lookup"><span data-stu-id="12538-158">This is the last step!</span></span>  

