---
title: Créer une commande de réapprovisionnement avec consignation
description: Cette rubrique explique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation.
author: mkirknel
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 766f29f7511c16eccd37e93f2de366ac23c35545
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145799"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="bd979-103">Créer une commande de réapprovisionnement avec consignation</span><span class="sxs-lookup"><span data-stu-id="bd979-103">Create a consignment replenishment order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd979-104">Cette rubrique explique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation.</span><span class="sxs-lookup"><span data-stu-id="bd979-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="bd979-105">Elle décrit également comment enregistrer une réception de produits afin que le stock de consignation soit enregistré comme stock disponible appartenant au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bd979-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="bd979-106">Cette procédure est généralement effectuée par un professionnel de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="bd979-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="bd979-107">Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="bd979-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="bd979-108">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bd979-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="bd979-109">Créer une commande de réapprovisionnement avec consignation</span><span class="sxs-lookup"><span data-stu-id="bd979-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="bd979-110">Dans le volet de navigation, accédez à **Modules > Approvisionnements > Consignation > Commandes de réapprovisionnement avec consignation**.</span><span class="sxs-lookup"><span data-stu-id="bd979-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="bd979-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bd979-111">Select **New**.</span></span>
3. <span data-ttu-id="bd979-112">Dans le champ **Compte fournisseur**, sélectionnez le fournisseur **US-104** (vous devez sélectionner un fournisseur qui est enregistré comme propriétaire dans la page **propriétaires du stock**).</span><span class="sxs-lookup"><span data-stu-id="bd979-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="bd979-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd979-113">Select **OK**.</span></span>
5. <span data-ttu-id="bd979-114">Sélectionnez **Ajouter la ligne**.</span><span class="sxs-lookup"><span data-stu-id="bd979-114">Select **Add line**.</span></span>
6. <span data-ttu-id="bd979-115">Dans le champ **Numéro d’article**, tapez `M9211CI` (vous devez sélectionner un article qui est paramétré pour un stock de consignation).</span><span class="sxs-lookup"><span data-stu-id="bd979-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="bd979-116">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="bd979-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="bd979-117">Entrez une date dans le champ **Date de livraison demandée**.</span><span class="sxs-lookup"><span data-stu-id="bd979-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="bd979-118">Les dates demandées et confirmées sont utilisées par le moteur MRP pour l'arrivée prévue des marchandises.</span><span class="sxs-lookup"><span data-stu-id="bd979-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="bd979-119">Entrez une date dans le champ **Date de livraison confirmée**.</span><span class="sxs-lookup"><span data-stu-id="bd979-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="bd979-120">Développez la section **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="bd979-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="bd979-121">Cliquez sur l'onglet **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="bd979-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="bd979-122">Actualisez la page pour afficher le propriétaire dans le champ **Propriétaire des dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="bd979-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="bd979-123">Le fournisseur US-104 est à présent répertorié comme propriétaire.</span><span class="sxs-lookup"><span data-stu-id="bd979-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="bd979-124">Vérifier le statut du mouvement de stock</span><span class="sxs-lookup"><span data-stu-id="bd979-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="bd979-125">Sélectionnez le **stock**.</span><span class="sxs-lookup"><span data-stu-id="bd979-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="bd979-126">Sélectionnez les **transactions**.</span><span class="sxs-lookup"><span data-stu-id="bd979-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="bd979-127">Dans la ligne souhaitée, notez que le champ **Réception** est défini sur **Commandé**.</span><span class="sxs-lookup"><span data-stu-id="bd979-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="bd979-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bd979-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="bd979-129">Recevoir articles</span><span class="sxs-lookup"><span data-stu-id="bd979-129">Receive items</span></span>
1. <span data-ttu-id="bd979-130">Sélectionnez **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="bd979-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="bd979-131">Tapez une valeur dans le champ **Accusé de réception de marchandises externe**.</span><span class="sxs-lookup"><span data-stu-id="bd979-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="bd979-132">Dans le champ **Quantité**, entrez un nombre inférieur au nombre indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="bd979-132">In the **Quantity** field, enter a number that's lower than the number that's shown there.</span></span> 
4. <span data-ttu-id="bd979-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd979-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="bd979-134">Vérifier le stock disponible</span><span class="sxs-lookup"><span data-stu-id="bd979-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="bd979-135">Sélectionnez le **stock**.</span><span class="sxs-lookup"><span data-stu-id="bd979-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="bd979-136">Sélectionner **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="bd979-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="bd979-137">Sélectionnez **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="bd979-137">Select **Overview**.</span></span> <span data-ttu-id="bd979-138">Les articles reçus comme stock de consignation appartenant au fournisseur sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="bd979-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="bd979-139">La quantité restante sur la commande de réapprovisionnement avec consignation est affichée dans le champ **Total commandé**.</span><span class="sxs-lookup"><span data-stu-id="bd979-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="bd979-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bd979-140">Close the page.</span></span>

