---
title: Énumérer le stock dans un entrepôt
description: Cette procédure vous accompagne au long du processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c0bbfe8f86d27f81b0d577ed89dfa34ebcf3f18
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353469"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="4f95b-103">Énumérer le stock dans un entrepôt</span><span class="sxs-lookup"><span data-stu-id="4f95b-103">Count inventory in a warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4f95b-104">Cette procédure vous accompagne au long du processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4f95b-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="4f95b-105">Cette procédure s'applique à la fonctionnalité « entreposage de base », disponible dans le module Gestion des stocks, et pas à la fonctionnalité d'entreposage disponible dans le module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="4f95b-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="4f95b-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="4f95b-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="4f95b-107">Si vous utilisez vos propres données, vérifiez que vous avez des produits et des emplacements configurés, et que vous avez créé un nom de journal de stock pour les journaux de comptage.</span><span class="sxs-lookup"><span data-stu-id="4f95b-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="4f95b-108">Le comptage de stock est normalement effectué par un employé de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4f95b-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="4f95b-109">Créer un journal de comptage du stock</span><span class="sxs-lookup"><span data-stu-id="4f95b-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="4f95b-110">Accédez à Gestion des stocks > Entrées de journal > Inventaire des articles > Comptage.</span><span class="sxs-lookup"><span data-stu-id="4f95b-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="4f95b-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4f95b-111">Click New.</span></span>
3. <span data-ttu-id="4f95b-112">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4f95b-113">Dans la liste, cliquez sur le nom du journal de comptage du stock que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="4f95b-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="4f95b-114">Certains autres champs seront remplis en fonction du paramétrage du nom du journal de comptage du stock que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4f95b-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="4f95b-115">Dans le champ Collaborateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="4f95b-116">Dans la liste, sélectionnez le collaborateur que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="4f95b-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="4f95b-117">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="4f95b-117">Click Select.</span></span>
8. <span data-ttu-id="4f95b-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4f95b-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="4f95b-119">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="4f95b-119">Create journal lines</span></span>
1. <span data-ttu-id="4f95b-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="4f95b-120">Click New.</span></span>
2. <span data-ttu-id="4f95b-121">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4f95b-122">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f95b-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f95b-123">Si vous utilisez les données de démonstration de la société USMF, sélectionnez « A0001 ».</span><span class="sxs-lookup"><span data-stu-id="4f95b-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="4f95b-124">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="4f95b-125">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f95b-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f95b-126">Si vous utilisez les données de démonstration de la société USMF, sélectionnez le site « 2 ».</span><span class="sxs-lookup"><span data-stu-id="4f95b-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="4f95b-127">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="4f95b-128">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f95b-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f95b-129">Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'entrepôt « 24 ».</span><span class="sxs-lookup"><span data-stu-id="4f95b-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="4f95b-130">Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="4f95b-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="4f95b-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f95b-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4f95b-132">Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'emplacement « BULK-001 ».</span><span class="sxs-lookup"><span data-stu-id="4f95b-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="4f95b-133">Dans le champ Compté, entrer un nombre.</span><span class="sxs-lookup"><span data-stu-id="4f95b-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="4f95b-134">Si vous entrez un nombre compté local différent du nombre indiqué dans le champ Disponible, le champ Quantité est mis à jour pour indiquer l'écart.</span><span class="sxs-lookup"><span data-stu-id="4f95b-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="4f95b-135">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="4f95b-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="4f95b-136">Valider le journal de comptage du stock</span><span class="sxs-lookup"><span data-stu-id="4f95b-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="4f95b-137">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="4f95b-137">Click Post.</span></span>
    * <span data-ttu-id="4f95b-138">Lorsque vous validez un journal de comptage du stock, si la quantité comptée diffère de la quantité déclarée dans le champ Disponible quand un bon de réception ou de sortir du stock est validé, le niveau et la valeur du stock sont modifiés et les transactions comptables sont générées.</span><span class="sxs-lookup"><span data-stu-id="4f95b-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="4f95b-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="4f95b-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="4f95b-140">Afficher les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="4f95b-140">View inventory transactions</span></span>
1. <span data-ttu-id="4f95b-141">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="4f95b-141">Click Inventory.</span></span>
2. <span data-ttu-id="4f95b-142">Cliquez sur Transactions.</span><span class="sxs-lookup"><span data-stu-id="4f95b-142">Click Transactions.</span></span>
    * <span data-ttu-id="4f95b-143">Voici que vous pouvez afficher toutes les transactions associées qui seront créées lorsque vous validerez votre journal de comptage du stock.</span><span class="sxs-lookup"><span data-stu-id="4f95b-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

