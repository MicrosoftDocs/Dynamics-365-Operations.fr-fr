---
title: Corriger les informations de suivi de stock
description: "Cette procédure vous guide dans le processus de création et de validation d'un journal de transfert de stock afin de corriger les informations de suivi de stock."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: e28d10646f01604098de8cedc30c8c7a7c89866b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/12/2017

---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="bfd37-103">Corriger les informations de suivi de stock</span><span class="sxs-lookup"><span data-stu-id="bfd37-103">Correct inventory tracking information</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bfd37-104">Cette procédure vous guide dans le processus de création et de validation d'un journal de transfert de stock afin de corriger les informations de suivi de stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="bfd37-105">Dans cet exemple, nous allons mettre à jour les informations d'un article contrôlé via le traitement par lots en modifiant un traitement par lots incorrectement enregistré vers un autre traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="bfd37-105">In this example, we’ll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="bfd37-106">Vous pouvez parcourir cette procédure dans la société fictive de démonstration USPI ou en utilisant vos propres données.</span><span class="sxs-lookup"><span data-stu-id="bfd37-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="bfd37-107">Si vous utilisez vos propres données, vous devez posséder un article pour lequel le traitement par lots est activé, et qui ne doit pas être contrôlé par emplacement.</span><span class="sxs-lookup"><span data-stu-id="bfd37-107">If you use your own data, you need to have an item that’s batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="bfd37-108">Vous devez également avoir configuré un nom de journal de stock pour les transferts de stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="bfd37-109">Ces tâches sont normalement effectuées par un employé de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="bfd37-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="bfd37-110">Créer un journal de transfert de stock</span><span class="sxs-lookup"><span data-stu-id="bfd37-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="bfd37-111">Accédez à Transférer.</span><span class="sxs-lookup"><span data-stu-id="bfd37-111">Go to Transfer.</span></span>
2. <span data-ttu-id="bfd37-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bfd37-112">Click New.</span></span>
3. <span data-ttu-id="bfd37-113">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bfd37-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="bfd37-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bfd37-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="bfd37-115">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="bfd37-115">Create journal lines</span></span>
1. <span data-ttu-id="bfd37-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bfd37-116">Click New.</span></span>
2. <span data-ttu-id="bfd37-117">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="bfd37-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="bfd37-118">Si vous utilisez USPI, sélectionnez l'article M5003.</span><span class="sxs-lookup"><span data-stu-id="bfd37-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="bfd37-119">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="bfd37-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="bfd37-120">Cliquez sur l'onglet Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="bfd37-121">Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="bfd37-122">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="bfd37-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="bfd37-123">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="bfd37-124">Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="bfd37-125">Valider le journal</span><span class="sxs-lookup"><span data-stu-id="bfd37-125">Post the journal</span></span>
1. <span data-ttu-id="bfd37-126">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="bfd37-126">Click Post.</span></span>
2. <span data-ttu-id="bfd37-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bfd37-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="bfd37-128">Vérifier les informations de suivi</span><span class="sxs-lookup"><span data-stu-id="bfd37-128">Check tracing information</span></span>
1. <span data-ttu-id="bfd37-129">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-129">Click Inventory.</span></span>
2. <span data-ttu-id="bfd37-130">Cliquez sur Traçabilité.</span><span class="sxs-lookup"><span data-stu-id="bfd37-130">Click Trace.</span></span>
3. <span data-ttu-id="bfd37-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="bfd37-131">Click OK.</span></span>
    * <span data-ttu-id="bfd37-132">À l'aide de ces informations de suivi, vous pouvez effectuer un suivi à rebours du traitement par lots à partir duquel vous avez corrigé le stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="bfd37-133">Vous pouvez également utiliser la page Suivi des articles pour afficher ces informations.</span><span class="sxs-lookup"><span data-stu-id="bfd37-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="bfd37-134">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bfd37-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="bfd37-135">Vérifier les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="bfd37-135">Check inventory transactions</span></span>
1. <span data-ttu-id="bfd37-136">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="bfd37-136">Click Inventory.</span></span>
2. <span data-ttu-id="bfd37-137">Cliquez sur Transactions.</span><span class="sxs-lookup"><span data-stu-id="bfd37-137">Click Transactions.</span></span>
    * <span data-ttu-id="bfd37-138">Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.</span><span class="sxs-lookup"><span data-stu-id="bfd37-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

