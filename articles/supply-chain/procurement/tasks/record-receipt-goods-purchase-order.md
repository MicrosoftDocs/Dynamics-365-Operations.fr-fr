--- 
title: "Enregistrer la réception de marchandises sur la commande fournisseur"
description: "Cette procédure vous montre comment enregistrer la réception des marchandises directement sur une commande fournisseur."
author: FrankDahl
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 991d9923bc8ef9f411ef6120e63b8e31ccddf566
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="69629-103">Enregistrer la réception de marchandises sur la commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="69629-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="69629-104">Cette procédure vous montre comment enregistrer la réception des marchandises directement sur une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="69629-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="69629-105">Il est également possible d'enregistrer l'accusé de réception de marchandises dans l'entrepôt, puis de l'enregistrer ultérieurement dans la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="69629-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="69629-106">Cette tâche est généralement effectuée par un agent des achats ou un coordinateur de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="69629-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="69629-107">L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="69629-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="69629-108">L'exemple inclut des étapes pour créer une commande fournisseur simple de sorte que vous puissiez suivre la procédure comme un guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="69629-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="69629-109">Si vous suiviez cette procédure sur vos propres données, vous commenceriez par la sous-tâche Enregistrer la réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="69629-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="69629-110">Préparer une nouvelle commande fournisseur pour la réception des marchandises</span><span class="sxs-lookup"><span data-stu-id="69629-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="69629-111">Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="69629-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="69629-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="69629-112">Click New.</span></span>
3. <span data-ttu-id="69629-113">Tapez US-101 dans le champ Compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="69629-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="69629-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="69629-114">Click OK.</span></span>
5. <span data-ttu-id="69629-115">Entrez M0001 dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="69629-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="69629-116">Entrez 5 dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="69629-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="69629-117">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="69629-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="69629-118">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="69629-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="69629-119">Enregistrer la réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="69629-119">Record receipt of goods</span></span>
1. <span data-ttu-id="69629-120">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="69629-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="69629-121">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="69629-121">Click Product receipt.</span></span>
    * <span data-ttu-id="69629-122">Le champ Quantité vous permet de choisir différentes options pour la quantité que vous voulez recevoir.</span><span class="sxs-lookup"><span data-stu-id="69629-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="69629-123">Par exemple, si une quantité a été précédemment enregistrée dans l'entrepôt, vous pouvez sélectionner Quantité enregistrée.</span><span class="sxs-lookup"><span data-stu-id="69629-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="69629-124">Pour cet exemple, utilisez la valeur Quantité commandée.</span><span class="sxs-lookup"><span data-stu-id="69629-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="69629-125">Tapez une valeur quelconque dans le champ Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="69629-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="69629-126">Ce champ permet d'entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="69629-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="69629-127">Développez la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="69629-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="69629-128">Définir la Quantité sur « 4 ».</span><span class="sxs-lookup"><span data-stu-id="69629-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="69629-129">Ici vous pouvez spécifier manuellement la quantité reçue pour chaque ligne de la commande.</span><span class="sxs-lookup"><span data-stu-id="69629-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="69629-130">Réduisez la section Lignes.</span><span class="sxs-lookup"><span data-stu-id="69629-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="69629-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="69629-131">Click OK.</span></span>
    * <span data-ttu-id="69629-132">Les marchandises sont désormais enregistrées comme reçues sur la commande fournisseur, et un journal des accusés de réception de marchandises est créé comme document pour refléter ceci.</span><span class="sxs-lookup"><span data-stu-id="69629-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="69629-133">Vous pouvez utiliser l'action Accusé de réception de marchandises pour passer en revue les journaux créés avec la commande fournisseur, et voir ce qui a été reçu, et quand.</span><span class="sxs-lookup"><span data-stu-id="69629-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


