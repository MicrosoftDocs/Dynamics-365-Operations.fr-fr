---
title: Créer et tenir à jour un blocage du stock
description: Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock.
author: perlynne
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2408addea3615ffe6dbc4db8baecfdef6a65e839
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145822"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="9a4f5-103">Créer et tenir à jour un blocage du stock</span><span class="sxs-lookup"><span data-stu-id="9a4f5-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a4f5-104">Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="9a4f5-105">Vous pouvez exécuter la procédure dans la société USMF fictive avec les valeurs d'exemple affichées.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="9a4f5-106">Vous devez posséder d'un article avec le stock physique disponible avant de commencer cette procédure.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="9a4f5-107">Créer un blocage du stock</span><span class="sxs-lookup"><span data-stu-id="9a4f5-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="9a4f5-108">Dans le **volet de navigation**, accédez à **Modules > Gestion des stocks > Tâches périodiques > Blocage du stock**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="9a4f5-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-109">Click **New**.</span></span>
3. <span data-ttu-id="9a4f5-110">Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9a4f5-111">Dans la liste, sélectionnez l'article que vous souhaitez choisir.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="9a4f5-112">Sélectionnez un numéro d'article avec le stock physique disponible à bloquer.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="9a4f5-113">Si vous utilisez USMF, vous pouvez sélectionner l'article M9201.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="9a4f5-114">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="9a4f5-115">Si vous utilisez l'article M9201, vous devez sélectionner inférieur à 200.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="9a4f5-116">Développez le raccourci **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="9a4f5-117">Dans le champ **Entrepôt**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9a4f5-118">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="9a4f5-119">Si vous utilisez l'article M9201, vous pouvez sélectionner l'entrepôt 51.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="9a4f5-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="9a4f5-121">Mettre à jour les conditions du blocage du stock</span><span class="sxs-lookup"><span data-stu-id="9a4f5-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="9a4f5-122">Dans le raccourci **Général**, entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="9a4f5-123">Mettez à jour le champ de quantité en stock pour refléter la quantité à bloquer.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="9a4f5-124">Entrez une date dans le champ **Date prévue**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="9a4f5-125">Vous souhaitez peut-être indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation en affectant une date prévue.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="9a4f5-126">Si l'option Réceptions prévues est sélectionnée pour le blocage du stock, (elle l'est par défaut lorsque vous créez manuellement un blocage), cette date s'affiche sur la transaction attendue.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="9a4f5-127">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="9a4f5-128">Supprimer le blocage du stock</span><span class="sxs-lookup"><span data-stu-id="9a4f5-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="9a4f5-129">Dans le **volet Actions**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-129">On the **Action pane**, click **Delete**.</span></span>
2. <span data-ttu-id="9a4f5-130">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-130">Click **Yes**.</span></span>
3. <span data-ttu-id="9a4f5-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9a4f5-131">Close the page.</span></span>

