--- 
title: "Créer une règle de kanban d'événement de vente"
description: "Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 33ae479a8479732a1857577743a22068d2059a47
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="60ee9-103">Créer une règle de kanban d'événement de vente</span><span class="sxs-lookup"><span data-stu-id="60ee9-103">Create a sales event kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="60ee9-104">Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="60ee9-105">La règle de kanban d'événement réalise le réapprovisionnement des besoins provenant des lignes de commande client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="60ee9-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="60ee9-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="60ee9-107">Elle est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié.</span><span class="sxs-lookup"><span data-stu-id="60ee9-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="60ee9-108">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="60ee9-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="60ee9-109">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="60ee9-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="60ee9-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="60ee9-110">Click New.</span></span>
3. <span data-ttu-id="60ee9-111">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».</span><span class="sxs-lookup"><span data-stu-id="60ee9-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="60ee9-112">Le fait de sélectionner Événement signifie que la règle de kanban est déclenchée par un événement, par exemple par la création d'une ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="60ee9-113">Cela s'applique aux domaines où chaque kanban doit couvrir une demande spécifique.</span><span class="sxs-lookup"><span data-stu-id="60ee9-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="60ee9-114">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="60ee9-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="60ee9-115">Sélectionnez Assemblage final.</span><span class="sxs-lookup"><span data-stu-id="60ee9-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="60ee9-116">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="60ee9-116">Expand the Details section.</span></span>
6. <span data-ttu-id="60ee9-117">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="60ee9-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="60ee9-118">Sélectionnez L0050.</span><span class="sxs-lookup"><span data-stu-id="60ee9-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="60ee9-119">Définir un événement</span><span class="sxs-lookup"><span data-stu-id="60ee9-119">Define an event</span></span>
1. <span data-ttu-id="60ee9-120">Développez la section Événements.</span><span class="sxs-lookup"><span data-stu-id="60ee9-120">Expand the Events section.</span></span>
2. <span data-ttu-id="60ee9-121">Dans le champ Événement de vente, sélectionnez « Automatique ».</span><span class="sxs-lookup"><span data-stu-id="60ee9-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="60ee9-122">En sélectionnant l'événement de vente Automatique, cette règle de kanban sera déclenchée automatiquement lorsqu'une ligne de vente correspondra au produit et à l'emplacement de réception.</span><span class="sxs-lookup"><span data-stu-id="60ee9-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="60ee9-123">Dans cette procédure, il s'agit du produit L0050 dans l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="60ee9-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="60ee9-124">Définissez la quantité d'événement minimale sur « 50 ».</span><span class="sxs-lookup"><span data-stu-id="60ee9-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="60ee9-125">Avec une quantité minimale d'événement de 50, la règle de kanban ne sera déclenchée que par les événements d'une quantité de 50 ou davantage.</span><span class="sxs-lookup"><span data-stu-id="60ee9-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="60ee9-126">Développez la section Flux de production.</span><span class="sxs-lookup"><span data-stu-id="60ee9-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="60ee9-127">Notez que l'emplacement de réception est l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="60ee9-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="60ee9-128">Cela signifie que cette règle de kanban sera déclenchée pour cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="60ee9-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="60ee9-129">Dans cet exemple, une ligne de vente du produit L0050, avec une quantité de 50 ou plus, dans l'entrepôt 13, déclenchera cette règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="60ee9-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="60ee9-130">Créer une ligne de vente pour déclencher une règle de kanban d'événement</span><span class="sxs-lookup"><span data-stu-id="60ee9-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="60ee9-131">Allez dans Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="60ee9-132">Un avertissement s'affiche lorsque la règle de kanban est enregistrée, ce qui signifie que les kanbans sont créés en temps réel lors de la création de commande client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="60ee9-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="60ee9-133">Click New.</span></span>
3. <span data-ttu-id="60ee9-134">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="60ee9-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="60ee9-135">Par exemple, sélectionnez US-003.</span><span class="sxs-lookup"><span data-stu-id="60ee9-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="60ee9-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="60ee9-136">Click OK.</span></span>
5. <span data-ttu-id="60ee9-137">Entrez « L0050 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="60ee9-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="60ee9-138">Dans le champ Site, tapez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="60ee9-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="60ee9-139">Sélectionnez Site 1 car l'entrepôt 13 se trouve sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="60ee9-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="60ee9-140">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="60ee9-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="60ee9-141">Définissez Entrepôt sur 13.</span><span class="sxs-lookup"><span data-stu-id="60ee9-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="60ee9-142">Définir la Quantité sur « 75 ».</span><span class="sxs-lookup"><span data-stu-id="60ee9-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="60ee9-143">Entrez une quantité de 50 ou supérieure, pour déclencher la règle de kanban créée.</span><span class="sxs-lookup"><span data-stu-id="60ee9-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="60ee9-144">Vérifier que le kanban est créé</span><span class="sxs-lookup"><span data-stu-id="60ee9-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="60ee9-145">Cliquez sur Produit et approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="60ee9-145">Click Product and supply.</span></span>
2. <span data-ttu-id="60ee9-146">Cliquez sur Afficher l'arborescence d'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="60ee9-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="60ee9-147">Notez qu'un kanban est créé avec la même quantité que la ligne de vente.</span><span class="sxs-lookup"><span data-stu-id="60ee9-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="60ee9-148">Vous pouvez également afficher les sorties de matériel nécessaires pour produire le L0050.</span><span class="sxs-lookup"><span data-stu-id="60ee9-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="60ee9-149">Il s'agit de la dernière étape de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="60ee9-149">This is the last step in this procedure.</span></span>  


