--- 
title: "Créer un ordre de fabrication"
description: "Cette procédure permet d'indiquer comment créer un ordre de fabrication."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 730adcea0ac59f683ecae8cbb62025bd7db75c55
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-production-order"></a><span data-ttu-id="1a9eb-103">Créer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1a9eb-103">Create a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1a9eb-104">Cette procédure permet d'indiquer comment créer un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="1a9eb-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1a9eb-106">Il s'agit de la première des sept procédures expliquant le cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="1a9eb-107">Créer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1a9eb-107">Create a production order</span></span>
1. <span data-ttu-id="1a9eb-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="1a9eb-109">Cliquez sur Nouvel ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-109">Click New production order.</span></span>
3. <span data-ttu-id="1a9eb-110">Entrez « D0001 » dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="1a9eb-111">Entrez une date dans le champ Livraison.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="1a9eb-112">La date de livraison indique à quel moment l'ordre de fabrication doit se terminer afin de livrer à temps.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="1a9eb-113">Cette date peut être utilisée dans le processus de planification.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="1a9eb-114">Vous pouvez par exemple planifier la commande rétrospectivement à partir de la date de livraison.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="1a9eb-115">Définir la Quantité sur « 20 ».</span><span class="sxs-lookup"><span data-stu-id="1a9eb-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="1a9eb-116">Remarque : Le champ Numéro de nomenclature affiche automatiquement le numéro de la nomenclature active pour l'article actuel, mais vous pouvez modifier la nomenclature pour l'ordre de fabrication en sélectionnant une nomenclature active dans la liste des versions de nomenclature approuvées.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="1a9eb-117">Remarque : Le champ Numéro de gamme affiche automatiquement le numéro de la gamme active pour l'article actuel, mais vous pouvez modifier la gamme pour l'ordre de fabrication en sélectionnant une gamme active dans la liste des versions de gamme approuvées.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="1a9eb-118">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="1a9eb-119">Valider l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1a9eb-119">Validate the production order</span></span>
1. <span data-ttu-id="1a9eb-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1a9eb-121">Cliquez sur le lien du numéro de l'ordre de fabrication que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="1a9eb-122">Cela ouvre la page de détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="1a9eb-123">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-123">Click Edit.</span></span>
3. <span data-ttu-id="1a9eb-124">Entrez une date dans le champ Livraison.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="1a9eb-125">Vous pouvez par exemple modifier la date de livraison de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="1a9eb-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-126">Click Save.</span></span>
5. <span data-ttu-id="1a9eb-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="1a9eb-128">Mettre à jour la nomenclature</span><span class="sxs-lookup"><span data-stu-id="1a9eb-128">Update the BOM</span></span>
1. <span data-ttu-id="1a9eb-129">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="1a9eb-130">Cliquez sur Nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-130">Click BOM.</span></span>
    * <span data-ttu-id="1a9eb-131">Ouvrez la page Nomenclature pour valider les données de nomenclature copiées à partir des données par défaut lorsque l'ordre de fabrication a été créé.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="1a9eb-132">Dans cette procédure, vous devez mettre à jour la quantité d'une nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="1a9eb-133">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-133">Click Edit.</span></span>
4. <span data-ttu-id="1a9eb-134">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1a9eb-135">La modification de la quantité de la ligne de nomenclature affecte l'estimation des coûts de la consommation de matières pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="1a9eb-136">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-136">Click Save.</span></span>
6. <span data-ttu-id="1a9eb-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="1a9eb-138">Mettre à jour la gamme de production</span><span class="sxs-lookup"><span data-stu-id="1a9eb-138">Update the production route</span></span>
1. <span data-ttu-id="1a9eb-139">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="1a9eb-140">Cliquez sur Gamme</span><span class="sxs-lookup"><span data-stu-id="1a9eb-140">Click Route.</span></span>
    * <span data-ttu-id="1a9eb-141">Ouvrez la page Gamme pour valider les données de la gamme de production copiées à partir des données par défaut lorsque la commande a été créée.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="1a9eb-142">Dans cette procédure, vous devez mettre à jour la quantité pour l'une des opérations de la gamme de production.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="1a9eb-143">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1a9eb-144">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-144">Click Edit.</span></span>
5. <span data-ttu-id="1a9eb-145">Dans le champ Qté à traiter , entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="1a9eb-146">Le fait de modifier le temps d'exécution affecte la consommation de gamme estimée et le coût de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="1a9eb-147">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-147">Click Save.</span></span>
7. <span data-ttu-id="1a9eb-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1a9eb-148">Close the page.</span></span>

