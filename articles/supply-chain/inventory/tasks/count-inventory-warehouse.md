---
title: Énumérer le stock dans un entrepôt
description: Cette rubrique décrit le processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53e9457074b696efaf5958b3a3b4616f06f5a6ff
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145756"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="a45d3-103">Énumérer le stock dans un entrepôt</span><span class="sxs-lookup"><span data-stu-id="a45d3-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a45d3-104">Cette rubrique décrit le processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a45d3-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="a45d3-105">Cette procédure s'applique à la fonctionnalité « entreposage de base », disponible dans le module Gestion des stocks, et pas à la fonctionnalité d'entreposage disponible dans le module Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="a45d3-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="a45d3-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="a45d3-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="a45d3-107">Si vous utilisez vos propres données, vérifiez que vous avez des produits et des emplacements configurés, et que vous avez créé un nom de journal de stock pour les journaux de comptage.</span><span class="sxs-lookup"><span data-stu-id="a45d3-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="a45d3-108">Le comptage de stock est normalement effectué par un employé de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="a45d3-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="a45d3-109">Créer un journal de comptage du stock</span><span class="sxs-lookup"><span data-stu-id="a45d3-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="a45d3-110">Accédez à **Volet de navigation > Modules > Gestion des stocks > Entrées de journal > Inventaire des articles > Comptage**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="a45d3-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-111">Select **New**.</span></span>
3. <span data-ttu-id="a45d3-112">Dans le champ **Nom**, sélectionnez le nom du journal d'inventaire de stock que vous souhaitez utiliser dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a45d3-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="a45d3-113">Certains autres champs seront remplis en fonction du paramétrage du nom du journal de comptage du stock que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a45d3-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="a45d3-114">Dans le champ **Collaborateur**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="a45d3-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a45d3-115">Dans la liste, **sélectionnez** le collaborateur que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="a45d3-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="a45d3-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="a45d3-117">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="a45d3-117">Create journal lines</span></span>
1. <span data-ttu-id="a45d3-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-118">Select **New**.</span></span>
2. <span data-ttu-id="a45d3-119">Dans le champ **Numéro d'article**, sélectionnez l'enregistrement souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a45d3-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a45d3-120">Si vous utilisez les données de démonstration de la société USMF, sélectionnez **A0001**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="a45d3-121">Dans le champ **Site**, sélectionnez l'enregistrement souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a45d3-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a45d3-122">Si vous utilisez les données de démonstration de la société USMF, sélectionnez le site **2**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="a45d3-123">Dans le champ **Entrepôt**, sélectionnez l'enregistrement souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a45d3-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a45d3-124">Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'entrepôt **24**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="a45d3-125">Dans le champ **Emplacement**, sélectionnez l'enregistrement souhaité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a45d3-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="a45d3-126">Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'emplacement **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="a45d3-127">Dans le champ Compté, entrer un nombre.</span><span class="sxs-lookup"><span data-stu-id="a45d3-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="a45d3-128">Si vous entrez un nombre compté local différent du nombre indiqué dans le champ **Disponible**, le champ **Quantité** est mis à jour pour indiquer l'écart.</span><span class="sxs-lookup"><span data-stu-id="a45d3-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="a45d3-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="a45d3-130">Valider le journal de comptage du stock</span><span class="sxs-lookup"><span data-stu-id="a45d3-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="a45d3-131">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-131">Select **Post**.</span></span> <span data-ttu-id="a45d3-132">Lorsque vous validez un journal de comptage du stock, si la quantité comptée diffère de la quantité déclarée dans le champ **Disponible** quand un bon de réception ou de sortir du stock est validé, le niveau et la valeur du stock sont modifiés et les transactions comptables sont générées.</span><span class="sxs-lookup"><span data-stu-id="a45d3-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="a45d3-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="a45d3-134">Afficher les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="a45d3-134">View inventory transactions</span></span>
1. <span data-ttu-id="a45d3-135">Sélectionnez le **stock**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="a45d3-136">Sélectionnez les **transactions**.</span><span class="sxs-lookup"><span data-stu-id="a45d3-136">Select **Transactions**.</span></span> <span data-ttu-id="a45d3-137">Voici que vous pouvez afficher toutes les transactions associées qui seront créées lorsque vous validerez votre journal de comptage du stock.</span><span class="sxs-lookup"><span data-stu-id="a45d3-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

