---
title: Enregistrer la réception de marchandises sur la commande fournisseur
description: Cette rubrique explique comment enregistrer la réception des marchandises directement sur une commande fournisseur.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd8ca2cbd24f326c4eaf9cd39e32de0eca81149d
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018604"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="61c42-103">Enregistrer la réception de marchandises sur la commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="61c42-103">Record the receipt of goods on the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61c42-104">Cette rubrique explique comment enregistrer la réception des marchandises directement sur une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="61c42-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="61c42-105">Il est également possible d'enregistrer l'accusé de réception de marchandises dans l'entrepôt, puis de l'enregistrer ultérieurement dans la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="61c42-105">It's also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="61c42-106">Cette tâche est généralement effectuée par un agent des achats ou un coordinateur de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="61c42-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="61c42-107">L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="61c42-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="61c42-108">L'exemple inclut des étapes pour créer une commande fournisseur simple de sorte que vous puissiez suivre la procédure comme un guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="61c42-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="61c42-109">Si vous suiviez cette procédure sur vos propres données, vous commenceriez par la sous-tâche **Enregistrer la réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="61c42-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="61c42-110">Préparer une nouvelle commande fournisseur pour la réception des marchandises</span><span class="sxs-lookup"><span data-stu-id="61c42-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="61c42-111">Allez dans **Volet de navigation > Modules > Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="61c42-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="61c42-112">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="61c42-112">Select **New**.</span></span>
3. <span data-ttu-id="61c42-113">Dans le champ **Compte fournisseur** , saisissez `US-101`.</span><span class="sxs-lookup"><span data-stu-id="61c42-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="61c42-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="61c42-114">Select **OK**.</span></span>
5. <span data-ttu-id="61c42-115">Dans le champ **Numéro d'article** , entrez `M0001`.</span><span class="sxs-lookup"><span data-stu-id="61c42-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="61c42-116">Entrez `5` dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="61c42-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="61c42-117">Dans le volet Action, sélectionnez **Achat**.</span><span class="sxs-lookup"><span data-stu-id="61c42-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="61c42-118">Sélectionnez **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="61c42-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="61c42-119">Enregistrer la réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="61c42-119">Record receipt of goods</span></span>
1. <span data-ttu-id="61c42-120">Dans le volet Actions, sélectionnez **Recevoir**.</span><span class="sxs-lookup"><span data-stu-id="61c42-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="61c42-121">Sélectionnez **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="61c42-121">Select **Product receipt**.</span></span> <span data-ttu-id="61c42-122">Le champ **Quantité** vous permet de choisir différentes options pour la quantité que vous voulez recevoir.</span><span class="sxs-lookup"><span data-stu-id="61c42-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="61c42-123">Par exemple, si une quantité a été précédemment enregistrée dans l'entrepôt, vous pouvez sélectionner **Quantité enregistrée**.</span><span class="sxs-lookup"><span data-stu-id="61c42-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="61c42-124">Pour cet exemple, utilisez la valeur **Quantité commandée**.</span><span class="sxs-lookup"><span data-stu-id="61c42-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="61c42-125">Développez la section **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="61c42-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="61c42-126">Tapez une valeur quelconque dans le champ **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="61c42-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="61c42-127">Ce champ permet d'entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="61c42-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="61c42-128">Développez la section **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="61c42-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="61c42-129">Définissez le champ **Quantité** sur « 4 ».</span><span class="sxs-lookup"><span data-stu-id="61c42-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="61c42-130">Ici vous pouvez spécifier manuellement la quantité reçue pour chaque ligne de la commande.</span><span class="sxs-lookup"><span data-stu-id="61c42-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="61c42-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="61c42-131">Select **OK**.</span></span> <span data-ttu-id="61c42-132">Les marchandises sont désormais enregistrées comme reçues sur la commande fournisseur, et un journal des accusés de réception de marchandises est créé comme document pour refléter ceci.</span><span class="sxs-lookup"><span data-stu-id="61c42-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="61c42-133">Vous pouvez utiliser l'action Accusé de réception de marchandises pour passer en revue les journaux créés avec la commande fournisseur, et voir ce qui a été reçu, et quand.</span><span class="sxs-lookup"><span data-stu-id="61c42-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

