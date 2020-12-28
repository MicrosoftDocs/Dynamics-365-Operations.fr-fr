---
title: Corriger les informations de suivi de stock
description: Cette procédure vous guide dans le processus de création et de validation d'un journal de transfert de stock afin de corriger les informations de suivi de stock.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8a488d4c30923445b3ebc2626a79b8fa45012c7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428156"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="25af9-103">Corriger les informations de suivi de stock</span><span class="sxs-lookup"><span data-stu-id="25af9-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25af9-104">Cette procédure vous guide dans le processus de création et de validation d'un journal de transfert de stock afin de corriger les informations de suivi de stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="25af9-105">Dans cet exemple, nous allons mettre à jour les informations d'un article contrôlé via le traitement par lots en modifiant un traitement par lots incorrectement enregistré vers un autre traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="25af9-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="25af9-106">Vous pouvez parcourir cette procédure dans la société fictive de démonstration USPI ou en utilisant vos propres données.</span><span class="sxs-lookup"><span data-stu-id="25af9-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="25af9-107">Si vous utilisez vos propres données, vous devez posséder un article pour lequel le traitement par lots est activé, et qui ne doit pas être contrôlé par emplacement.</span><span class="sxs-lookup"><span data-stu-id="25af9-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="25af9-108">Vous devez également avoir configuré un nom de journal de stock pour les transferts de stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="25af9-109">Ces tâches sont normalement effectuées par un employé de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="25af9-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="25af9-110">Créer un journal de transfert de stock</span><span class="sxs-lookup"><span data-stu-id="25af9-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="25af9-111">Accédez à Transférer.</span><span class="sxs-lookup"><span data-stu-id="25af9-111">Go to Transfer.</span></span>
2. <span data-ttu-id="25af9-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="25af9-112">Click New.</span></span>
3. <span data-ttu-id="25af9-113">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="25af9-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="25af9-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25af9-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="25af9-115">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="25af9-115">Create journal lines</span></span>
1. <span data-ttu-id="25af9-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="25af9-116">Click New.</span></span>
2. <span data-ttu-id="25af9-117">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="25af9-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="25af9-118">Si vous utilisez USPI, sélectionnez l'article M5003.</span><span class="sxs-lookup"><span data-stu-id="25af9-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="25af9-119">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="25af9-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="25af9-120">Cliquez sur l'onglet Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="25af9-121">Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="25af9-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="25af9-122">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="25af9-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="25af9-123">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="25af9-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="25af9-124">Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="25af9-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="25af9-125">Valider le journal</span><span class="sxs-lookup"><span data-stu-id="25af9-125">Post the journal</span></span>
1. <span data-ttu-id="25af9-126">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="25af9-126">Click Post.</span></span>
2. <span data-ttu-id="25af9-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25af9-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="25af9-128">Vérifier les informations de suivi</span><span class="sxs-lookup"><span data-stu-id="25af9-128">Check tracing information</span></span>
1. <span data-ttu-id="25af9-129">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-129">Click Inventory.</span></span>
2. <span data-ttu-id="25af9-130">Cliquez sur Traçabilité.</span><span class="sxs-lookup"><span data-stu-id="25af9-130">Click Trace.</span></span>
3. <span data-ttu-id="25af9-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="25af9-131">Click OK.</span></span>
    * <span data-ttu-id="25af9-132">À l'aide de ces informations de suivi, vous pouvez effectuer un suivi à rebours du traitement par lots à partir duquel vous avez corrigé le stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="25af9-133">Vous pouvez également utiliser la page Suivi des articles pour afficher ces informations.</span><span class="sxs-lookup"><span data-stu-id="25af9-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="25af9-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="25af9-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="25af9-135">Vérifier les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="25af9-135">Check inventory transactions</span></span>
1. <span data-ttu-id="25af9-136">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="25af9-136">Click Inventory.</span></span>
2. <span data-ttu-id="25af9-137">Cliquez sur Transactions.</span><span class="sxs-lookup"><span data-stu-id="25af9-137">Click Transactions.</span></span>
    * <span data-ttu-id="25af9-138">Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.</span><span class="sxs-lookup"><span data-stu-id="25af9-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

