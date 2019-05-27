---
title: Créer une commande de réapprovisionnement avec consignation
description: Cette procédure indique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549876"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="9f808-103">Créer une commande de réapprovisionnement avec consignation</span><span class="sxs-lookup"><span data-stu-id="9f808-103">Create a consignment replenishment order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f808-104">Cette procédure indique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation.</span><span class="sxs-lookup"><span data-stu-id="9f808-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="9f808-105">Elle décrit également comment enregistrer une réception de produits afin que le stock de consignation soit enregistré comme stock disponible appartenant au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f808-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="9f808-106">Cette procédure est généralement effectuée par un professionnel de l'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="9f808-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="9f808-107">Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="9f808-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="9f808-108">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9f808-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="9f808-109">Créer une commande de réapprovisionnement avec consignation</span><span class="sxs-lookup"><span data-stu-id="9f808-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="9f808-110">Allez dans Approvisionnements > Consignation > Commandes de réapprovisionnement avec consignation.</span><span class="sxs-lookup"><span data-stu-id="9f808-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="9f808-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="9f808-111">Click New.</span></span>
3. <span data-ttu-id="9f808-112">Dans le champ Compte fournisseur, sélectionnez le fournisseur US-104.</span><span class="sxs-lookup"><span data-stu-id="9f808-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="9f808-113">Vous devez sélectionner un fournisseur qui est enregistré comme propriétaire dans la page Propriétaires du stock.</span><span class="sxs-lookup"><span data-stu-id="9f808-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="9f808-114">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9f808-114">Click OK.</span></span>
5. <span data-ttu-id="9f808-115">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="9f808-115">Click Add line.</span></span>
6. <span data-ttu-id="9f808-116">Dans le champ Numéro d'article, tapez M9211CI.</span><span class="sxs-lookup"><span data-stu-id="9f808-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="9f808-117">Vous devez sélectionner un article qui est paramétré pour le stock de consignation.</span><span class="sxs-lookup"><span data-stu-id="9f808-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="9f808-118">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="9f808-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="9f808-119">Dans le champ Date de livraison demandée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="9f808-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="9f808-120">Les dates demandées et confirmées sont utilisées par le moteur MRP pour l'arrivée prévue des marchandises.</span><span class="sxs-lookup"><span data-stu-id="9f808-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="9f808-121">Dans le champ Date de livraison confirmée, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="9f808-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="9f808-122">Développez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="9f808-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="9f808-123">Cliquez sur l'onglet Dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="9f808-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="9f808-124">Pour afficher le propriétaire dans le champ Propriétaire des dimensions de stock, actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="9f808-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="9f808-125">Le fournisseur US-104 est à présent répertorié comme propriétaire.</span><span class="sxs-lookup"><span data-stu-id="9f808-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="9f808-126">Vérifier le statut du mouvement de stock</span><span class="sxs-lookup"><span data-stu-id="9f808-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="9f808-127">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="9f808-127">Click Inventory.</span></span>
2. <span data-ttu-id="9f808-128">Cliquez sur Transactions.</span><span class="sxs-lookup"><span data-stu-id="9f808-128">Click Transactions.</span></span>
3. <span data-ttu-id="9f808-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9f808-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9f808-130">Notez que le champ Réception est défini sur Commandé.</span><span class="sxs-lookup"><span data-stu-id="9f808-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="9f808-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9f808-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="9f808-132">Recevoir articles</span><span class="sxs-lookup"><span data-stu-id="9f808-132">Receive items</span></span>
1. <span data-ttu-id="9f808-133">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="9f808-133">Click Product receipt.</span></span>
2. <span data-ttu-id="9f808-134">Dans le champ Accusé de réception de marchandises externe, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="9f808-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="9f808-135">Dans le champ Quantité, entrez un nombre inférieur au nombre indiqué ici.</span><span class="sxs-lookup"><span data-stu-id="9f808-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span> 
4. <span data-ttu-id="9f808-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="9f808-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="9f808-137">Vérifier le stock disponible</span><span class="sxs-lookup"><span data-stu-id="9f808-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="9f808-138">Cliquez sur Stock.</span><span class="sxs-lookup"><span data-stu-id="9f808-138">Click Inventory.</span></span>
2. <span data-ttu-id="9f808-139">Cliquez sur Disponible.</span><span class="sxs-lookup"><span data-stu-id="9f808-139">Click On-hand.</span></span>
3. <span data-ttu-id="9f808-140">Cliquez sur Vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="9f808-140">Click Overview.</span></span>
    * <span data-ttu-id="9f808-141">Les articles reçus comme stock de consignation appartenant au fournisseur sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="9f808-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="9f808-142">La quantité restante sur la commande de réapprovisionnement avec consignation est affichée dans le champ Total commandé.</span><span class="sxs-lookup"><span data-stu-id="9f808-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="9f808-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="9f808-143">Close the page.</span></span>
5. <span data-ttu-id="9f808-144">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="9f808-144">Click Close.</span></span>

