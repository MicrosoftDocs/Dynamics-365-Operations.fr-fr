---
title: Ajuster les niveaux des stocks dans l’entrepôt (entreposage de base)
description: Cette procédure vous accompagne au long du processus de création et de validation d’un journal d’ajustement du stock afin d’ajuster les niveaux de stock des produits dans l’entrepôt.
author: MarkusFogelberg
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bba1df70cd23a29ddffad96a4a581154619dc74
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834143"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="659c5-103">Ajuster les niveaux des stocks dans l’entrepôt (entreposage de base)</span><span class="sxs-lookup"><span data-stu-id="659c5-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="659c5-104">Cette procédure vous accompagne au long du processus de création et de validation d’un journal d’ajustement du stock afin d’ajuster les niveaux de stock des produits dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="659c5-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="659c5-105">Avant de commencer, vous devez avoir configuré un nom de journal de stock pour les ajustements du stock.</span><span class="sxs-lookup"><span data-stu-id="659c5-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="659c5-106">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="659c5-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="659c5-107">Ces tâches sont normalement effectuées par un employé de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="659c5-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="659c5-108">Créer un journal d’ajustement du stock</span><span class="sxs-lookup"><span data-stu-id="659c5-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="659c5-109">Accédez à Gestion des stocks > Entrées de journal > Articles > Ajustement d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="659c5-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="659c5-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="659c5-110">Click New.</span></span>
3. <span data-ttu-id="659c5-111">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="659c5-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="659c5-112">Dans la liste, cliquez sur le nom du journal d’ajustement du stock que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="659c5-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="659c5-113">Certains autres champs seront remplis en fonction du paramétrage du nom du journal d’ajustement du stock que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="659c5-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="659c5-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="659c5-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="659c5-115">Créer des lignes de journal</span><span class="sxs-lookup"><span data-stu-id="659c5-115">Create journal lines</span></span>
1. <span data-ttu-id="659c5-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="659c5-116">Click New.</span></span>
2. <span data-ttu-id="659c5-117">Dans la liste, marquez le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="659c5-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="659c5-118">Dans le champ Numéro d’article, sélectionnez un article.</span><span class="sxs-lookup"><span data-stu-id="659c5-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="659c5-119">Si vous utilisez les données de démonstration de la société USMF, entrez « D0001 ».</span><span class="sxs-lookup"><span data-stu-id="659c5-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="659c5-120">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="659c5-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="659c5-121">Sélectionnez un site dans la liste.</span><span class="sxs-lookup"><span data-stu-id="659c5-121">In the list, select a site.</span></span>
6. <span data-ttu-id="659c5-122">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="659c5-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="659c5-123">Sélectionnez un entrepôt dans la liste.</span><span class="sxs-lookup"><span data-stu-id="659c5-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="659c5-124">Si vous avez sélectionné un article avec Emplacement comme dimension obligatoire, vous devez indiquer l’emplacement ici.</span><span class="sxs-lookup"><span data-stu-id="659c5-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="659c5-125">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="659c5-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="659c5-126">Le champ Prix de revient permet de spécifier le coût unitaire des réceptions de stock.</span><span class="sxs-lookup"><span data-stu-id="659c5-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="659c5-127">Si le coût n’est pas spécifié pour le numéro d’article ou si vous souhaitez le modifier manuellement, vous pouvez le faire ici.</span><span class="sxs-lookup"><span data-stu-id="659c5-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="659c5-128">Contrôler et valider le journal d’ajustement du stock</span><span class="sxs-lookup"><span data-stu-id="659c5-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="659c5-129">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="659c5-129">Click Validate.</span></span>
2. <span data-ttu-id="659c5-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="659c5-130">Click OK.</span></span>
3. <span data-ttu-id="659c5-131">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="659c5-131">Click Post.</span></span>
    * <span data-ttu-id="659c5-132">Lorsque vous validez ce type de journal, une réception ou une sortie de stock est validée, le niveau et la valeur du stock sont modifiés et des écritures comptables sont générées.</span><span class="sxs-lookup"><span data-stu-id="659c5-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="659c5-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="659c5-133">Click OK.</span></span>
5. <span data-ttu-id="659c5-134">Permet de fermer l’écran.</span><span class="sxs-lookup"><span data-stu-id="659c5-134">Close the form.</span></span>
6. <span data-ttu-id="659c5-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="659c5-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]