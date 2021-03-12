---
title: Créer une règle de kanban d'événement de vente
description: Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd8d55619f52fcd1beff7a27ff814b3dc00dd25a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998626"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="7c9bb-103">Créer une règle de kanban d'événement de vente</span><span class="sxs-lookup"><span data-stu-id="7c9bb-103">Create a sales event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7c9bb-104">Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="7c9bb-105">La règle de kanban d'événement réalise le réapprovisionnement des besoins provenant des lignes de commande client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="7c9bb-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7c9bb-107">Elle est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="7c9bb-108">Créer une règle de kanban</span><span class="sxs-lookup"><span data-stu-id="7c9bb-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="7c9bb-109">Accédez aux règles de kanban.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="7c9bb-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-110">Click New.</span></span>
3. <span data-ttu-id="7c9bb-111">Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».</span><span class="sxs-lookup"><span data-stu-id="7c9bb-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="7c9bb-112">Le fait de sélectionner Événement signifie que la règle de kanban est déclenchée par un événement, par exemple par la création d'une ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="7c9bb-113">Cela s'applique aux domaines où chaque kanban doit couvrir une demande spécifique.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="7c9bb-114">Entrez ou sélectionnez une valeur dans le champ Première activité de plan.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="7c9bb-115">Sélectionnez Assemblage final.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="7c9bb-116">Développez la section Détails.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-116">Expand the Details section.</span></span>
6. <span data-ttu-id="7c9bb-117">Dans le champ Produit, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="7c9bb-118">Sélectionnez L0050.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="7c9bb-119">Définir un événement</span><span class="sxs-lookup"><span data-stu-id="7c9bb-119">Define an event</span></span>
1. <span data-ttu-id="7c9bb-120">Développez la section Événements.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-120">Expand the Events section.</span></span>
2. <span data-ttu-id="7c9bb-121">Dans le champ Événement de vente, sélectionnez « Automatique ».</span><span class="sxs-lookup"><span data-stu-id="7c9bb-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="7c9bb-122">En sélectionnant l'événement de vente Automatique, cette règle de kanban sera déclenchée automatiquement lorsqu'une ligne de vente correspondra au produit et à l'emplacement de réception.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="7c9bb-123">Dans cette procédure, il s'agit du produit L0050 dans l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="7c9bb-124">Définissez la quantité d'événement minimale sur « 50 ».</span><span class="sxs-lookup"><span data-stu-id="7c9bb-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="7c9bb-125">Avec une quantité minimale d'événement de 50, la règle de kanban ne sera déclenchée que par les événements d'une quantité de 50 ou davantage.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="7c9bb-126">Développez la section Flux de production.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="7c9bb-127">Notez que l'emplacement de réception est l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="7c9bb-128">Cela signifie que cette règle de kanban sera déclenchée pour cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="7c9bb-129">Dans cet exemple, une ligne de vente du produit L0050, avec une quantité de 50 ou plus, dans l'entrepôt 13, déclenchera cette règle de kanban.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="7c9bb-130">Créer une ligne de vente pour déclencher une règle de kanban d'événement</span><span class="sxs-lookup"><span data-stu-id="7c9bb-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="7c9bb-131">Allez dans Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="7c9bb-132">Un avertissement s'affiche lorsque la règle de kanban est enregistrée, ce qui signifie que les kanbans sont créés en temps réel lors de la création de commande client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="7c9bb-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-133">Click New.</span></span>
3. <span data-ttu-id="7c9bb-134">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="7c9bb-135">Par exemple, sélectionnez US-003.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="7c9bb-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-136">Click OK.</span></span>
5. <span data-ttu-id="7c9bb-137">Entrez « L0050 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="7c9bb-138">Dans le champ Site, tapez « 1 ».</span><span class="sxs-lookup"><span data-stu-id="7c9bb-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="7c9bb-139">Sélectionnez Site 1 car l'entrepôt 13 se trouve sur le site 1.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="7c9bb-140">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="7c9bb-141">Définissez Entrepôt sur 13.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="7c9bb-142">Définir la Quantité sur « 75 ».</span><span class="sxs-lookup"><span data-stu-id="7c9bb-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="7c9bb-143">Entrez une quantité de 50 ou supérieure, pour déclencher la règle de kanban créée.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="7c9bb-144">Vérifier que le kanban est créé</span><span class="sxs-lookup"><span data-stu-id="7c9bb-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="7c9bb-145">Cliquez sur Produit et approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-145">Click Product and supply.</span></span>
2. <span data-ttu-id="7c9bb-146">Cliquez sur Afficher l'arborescence d'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="7c9bb-147">Notez qu'un kanban est créé avec la même quantité que la ligne de vente.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="7c9bb-148">Vous pouvez également afficher les sorties de matériel nécessaires pour produire le L0050.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="7c9bb-149">Il s'agit de la dernière étape de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7c9bb-149">This is the last step in this procedure.</span></span>  

