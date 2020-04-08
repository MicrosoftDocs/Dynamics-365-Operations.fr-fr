---
title: Transférer du stock physique au sein de l'entrepôt
description: Cette procédure vous accompagne dans le processus de création et de validation d'un journal de transfert de stock en vue d'enregistrer le mouvement d'un article à partir d'un emplacement dans un entrepôt vers un autre.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 899701413814ce38a4367618ed72d1039eca0bf8
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148168"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="8e4fc-103">Transférer du stock physique au sein de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="8e4fc-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8e4fc-104">Cette procédure vous accompagne dans le processus de création et de validation d'un journal de transfert de stock en vue d'enregistrer le mouvement d'un article à partir d'un emplacement dans un entrepôt vers un autre.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="8e4fc-105">Avant de commencer, vous devez avoir configuré un nom de journal de stock pour les transferts de stock.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="8e4fc-106">Vous pouvez suivre cette procédure avec les données de démonstration de la société fictive USMF à l'aide des valeurs d'exemple affichées, ou utiliser vos propres données si vous avez des produits et des emplacements configurés.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="8e4fc-107">Ces tâches sont normalement effectuées par un employé de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="8e4fc-108">Créer un journal de transfert de stock</span><span class="sxs-lookup"><span data-stu-id="8e4fc-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="8e4fc-109">Dans le **Volet de navigation**, accédez à **Gestion des stocks > Entrées de journal > Articles > Transfert**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="8e4fc-110">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-110">Click **New**.</span></span>
3. <span data-ttu-id="8e4fc-111">Dans le champ **Nom**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="8e4fc-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-112">Click **OK**.</span></span> <span data-ttu-id="8e4fc-113">Il existe l'option pour spécifie les dimensions « À partir de » et « Vers » pour chaque ligne de journal.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="8e4fc-114">Ce sont des éléments essentiels pour ce type de journal.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-114">These are essential for this journal type.</span></span> <span data-ttu-id="8e4fc-115">Vous pouvez transférer des articles à des emplacements en utilisant des règles différentes.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="8e4fc-116">Dans cet exemple nous allons transférer un article au sein du même entrepôt, à partir d'un emplacement contrôlé par contenant vers un emplacement qui ne fait pas l'objet d'un contrôle de contenant.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="8e4fc-117">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="8e4fc-117">Create journal lines</span></span>
1. <span data-ttu-id="8e4fc-118">Dans l'**organisateur Lignes du journal**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="8e4fc-119">Entrez ou sélectionnez une valeur dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-120">Si vous utilisez USMF, vous pouvez sélectionner A0001.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="8e4fc-121">Dans le champ **Site d'origine**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-122">Si vous utilisez USMF, vous pouvez sélectionner 2.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="8e4fc-123">Dans le champ **Site de destination**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-124">Si vous utilisez USMF, vous pouvez sélectionner 2.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="8e4fc-125">Dans le champ **Entrepôt d'origine**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-126">Si vous utilisez USMF, vous pouvez sélectionner 24.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="8e4fc-127">Dans le champ **Entrepôt de destination**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-128">Si vous utilisez USMF, vous pouvez sélectionner 24.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="8e4fc-129">Saisissez ou sélectionnez une valeur dans le champ **Emplacement d'origine**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-130">Si vous utilisez USMF, vous pouvez sélectionner FL-001.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="8e4fc-131">Saisissez ou sélectionnez une valeur dans le champ **Emplacement de destination**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-132">Si vous utilisez USMF, vous pouvez sélectionner BULK-001.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="8e4fc-133">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="8e4fc-134">Dans l'organisateur **Détails de ligne**, cliquez sur l'onglet **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="8e4fc-135">Dans **Des dimensions de stock**, dans le champ **Contenant**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="8e4fc-136">Si vous utilisez USMF, vous pouvez sélectionner 24.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="8e4fc-137">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="8e4fc-138">Valider le journal de transfert de stock</span><span class="sxs-lookup"><span data-stu-id="8e4fc-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="8e4fc-139">Dans le volet **Actions**, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-139">On the **Action pane**, click **Post**.</span></span>
2. <span data-ttu-id="8e4fc-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="8e4fc-141">Afficher les mouvements de stock</span><span class="sxs-lookup"><span data-stu-id="8e4fc-141">View inventory transactions</span></span>
1. <span data-ttu-id="8e4fc-142">Cliquez sur **Stock**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="8e4fc-143">Cliquez sur **Transactions**.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-143">Click **Transactions**.</span></span> <span data-ttu-id="8e4fc-144">Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.</span><span class="sxs-lookup"><span data-stu-id="8e4fc-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

