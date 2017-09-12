---
title: "Créer et tenir à jour un blocage du stock"
description: "Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock."
author: perlynne
manager: AnnBe
ms.date: 12/02/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 7272349cf16b9459823a752b8d3df915f42606ef
ms.contentlocale: fr-fr
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-maintain-inventory-blocking"></a><span data-ttu-id="a28c1-103">Créer et tenir à jour un blocage du stock</span><span class="sxs-lookup"><span data-stu-id="a28c1-103">Create and maintain inventory blocking</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a28c1-104">Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock.</span><span class="sxs-lookup"><span data-stu-id="a28c1-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="a28c1-105">Vous pouvez exécuter la procédure dans la société USMF fictive avec les valeurs d'exemple affichées.</span><span class="sxs-lookup"><span data-stu-id="a28c1-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="a28c1-106">Vous devez posséder d'un article avec le stock physique disponible avant de commencer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a28c1-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="a28c1-107">Créer un blocage du stock</span><span class="sxs-lookup"><span data-stu-id="a28c1-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="a28c1-108">Allez dans Gestion des stocks > Tâches périodiques > Blocage du stock.</span><span class="sxs-lookup"><span data-stu-id="a28c1-108">Go to Inventory management > Periodic tasks > Inventory blocking.</span></span>
2. <span data-ttu-id="a28c1-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a28c1-109">Click New.</span></span>
3. <span data-ttu-id="a28c1-110">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a28c1-110">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a28c1-111">Dans la liste, sélectionnez l'article que vous souhaitez choisir.</span><span class="sxs-lookup"><span data-stu-id="a28c1-111">In the list, select the item you want to choose.</span></span>
    * <span data-ttu-id="a28c1-112">Sélectionnez un numéro d'article avec le stock physique disponible à bloquer.</span><span class="sxs-lookup"><span data-stu-id="a28c1-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="a28c1-113">Si vous utilisez USMF, vous pouvez sélectionner l'article M9201.</span><span class="sxs-lookup"><span data-stu-id="a28c1-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="a28c1-114">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="a28c1-114">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a28c1-115">Si vous utilisez l'article M9201, vous devez sélectionner inférieur à 200.</span><span class="sxs-lookup"><span data-stu-id="a28c1-115">If you’re using item M9201, you need to select less than 200.</span></span>  
6. <span data-ttu-id="a28c1-116">Activez ou désactivez l'extension de la section Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="a28c1-116">Toggle the expansion of the Inventory dimensions section.</span></span>
7. <span data-ttu-id="a28c1-117">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a28c1-117">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a28c1-118">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="a28c1-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a28c1-119">Si vous utilisez l'article M9201, vous pouvez sélectionner l'entrepôt 51.</span><span class="sxs-lookup"><span data-stu-id="a28c1-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="a28c1-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a28c1-120">Click Save.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="a28c1-121">Mettre à jour les conditions du blocage du stock</span><span class="sxs-lookup"><span data-stu-id="a28c1-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="a28c1-122">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="a28c1-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a28c1-123">Mettez à jour le champ de quantité en stock pour refléter la quantité à bloquer.</span><span class="sxs-lookup"><span data-stu-id="a28c1-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="a28c1-124">Entrez une date dans le champ Date prévue.</span><span class="sxs-lookup"><span data-stu-id="a28c1-124">In the Expected date field, enter a date.</span></span>
    * <span data-ttu-id="a28c1-125">Vous souhaitez peut-être indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation en affectant une date prévue.</span><span class="sxs-lookup"><span data-stu-id="a28c1-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="a28c1-126">Si l'option Réceptions prévues est sélectionnée pour le blocage du stock, (elle l'est par défaut lorsque vous créez manuellement un blocage), cette date s'affiche sur la transaction attendue.</span><span class="sxs-lookup"><span data-stu-id="a28c1-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="a28c1-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a28c1-127">Click Save.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="a28c1-128">Supprimer le blocage du stock</span><span class="sxs-lookup"><span data-stu-id="a28c1-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="a28c1-129">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="a28c1-129">Click Delete.</span></span>
2. <span data-ttu-id="a28c1-130">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="a28c1-130">Click Yes.</span></span>
3. <span data-ttu-id="a28c1-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a28c1-131">Close the page.</span></span>

