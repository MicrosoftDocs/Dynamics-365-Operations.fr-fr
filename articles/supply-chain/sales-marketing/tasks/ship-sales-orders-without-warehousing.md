---
title: Expédier des commandes client sans entreposage
description: Ce guide montre comment mettre une commande client à jour lorsque les produits sont expédiés au client.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62bbd65e2d80dca5a07b761e1aa76f1894b667c1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843311"
---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="7b2f6-103">Expédier des commandes client sans entreposage</span><span class="sxs-lookup"><span data-stu-id="7b2f6-103">Ship sales orders without warehousing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7b2f6-104">Ce guide montre comment mettre une commande client à jour lorsque les produits sont expédiés au client.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="7b2f6-105">Ce guide s'applique au flux d'exécution non paramétré pour la gestion des entrepôts (ni entreposage de base ou avancé), et donc ne nécessite pas que le prélèvement des produits soit enregistré avant l'expédition.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="7b2f6-106">Vous pouvez exécuter cette procédure avec vos propres données ou avec la société fictive de démonstration USMF.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="7b2f6-107">Dans les deux cas, avant de commencer cette tâche, créez une commande client pour un produit inventorié avec une quantité supérieure à 1.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="7b2f6-108">Pour éviter une erreur de validation, vous devez vérifier que la quantité disponible du produit dans le site et l'entrepôt sélectionnés dans la commande couvre la quantité de la commande.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="7b2f6-109">Valider le bon de livraison pour une commande</span><span class="sxs-lookup"><span data-stu-id="7b2f6-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="7b2f6-110">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="7b2f6-111">Dans la liste, cherchez et sélectionnez la commande créée pour cette tâche.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="7b2f6-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7b2f6-113">Dans le volet Actions, cliquez sur Prélever et emballer.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="7b2f6-114">Cliquez sur Validation du bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="7b2f6-115">Développez ou réduisez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="7b2f6-116">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="7b2f6-117">D'autres options sont notamment Livrer maintenant et Prélevé.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="7b2f6-118">Si la ligne de commande doit être expédiée partiellement et que le champ Livrer maintenant de la ligne de commande contient une quantité, vous devez sélectionner Livrer maintenant.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="7b2f6-119">Si le flux d'exécution de votre organisation comprend le prélèvement comme un processus distinct qui est géré et enregistré avec une liste de prélèvements, vous devez sélectionner Prélevé.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="7b2f6-120">Vérifiez que l'option de validation est définie sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="7b2f6-121">Définissez l'option Imprimer le bon de livraison sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="7b2f6-122">L'onglet Vue d'ensemble contient une liste des bons de livraison à générer dans cette validation.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="7b2f6-123">Si vous expédiez une commande individuelle, il y aura généralement un bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="7b2f6-124">Toutefois, si les lignes de cette commande doivent être expédiées à partir de différents sites, la validation sera automatiquement fractionnée en le nombre approprié de documents.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="7b2f6-125">C'est une condition obligatoire qui ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="7b2f6-126">De même, la validation sera également fractionnée en plusieurs documents si les lignes de la commande doivent être expédiées à des adresses de livraison différentes, et que la stratégie de transport est paramétrée pour demander un fractionnement.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="7b2f6-127">Dans l'onglet Lignes, sélectionnez la rangée de la ligne de commande à expédier.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="7b2f6-128">Dans le champ Mettre à jour, entrez un nombre plus faible que la quantité originale.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="7b2f6-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-129">Click OK.</span></span>
12. <span data-ttu-id="7b2f6-130">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-130">Click Yes.</span></span>
13. <span data-ttu-id="7b2f6-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-131">Close the page.</span></span>
14. <span data-ttu-id="7b2f6-132">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="7b2f6-133">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-133">Click Change view.</span></span>
16. <span data-ttu-id="7b2f6-134">Cliquez sur Vue de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-134">Click Header view.</span></span>
    * <span data-ttu-id="7b2f6-135">Si toutes les lignes de la commande ont été entièrement expédiées, le statut de la commande passe de En cours à Livrée.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="7b2f6-136">Dans cet exemple, la ligne de commande a été partiellement expédiée.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="7b2f6-137">C'est pourquoi le statut de la commande demeure En cours.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="7b2f6-138">Le champ Statut de document est défini sur Bon de livraison parce qu'au moins une des lignes de commande a été expédiée.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="7b2f6-139">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="7b2f6-140">Cliquez sur Quantité de la ligne.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-140">Click Line quantity.</span></span>
19. <span data-ttu-id="7b2f6-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-141">Close the page.</span></span>
20. <span data-ttu-id="7b2f6-142">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="7b2f6-143">Cliquez sur Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-143">Click Packing slip.</span></span>
    * <span data-ttu-id="7b2f6-144">La page du journal des bons de livraison contient tous les documents de bon de livraison générés pour votre commande.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="7b2f6-145">Vous pouvez réviser les détails de chaque document et les imprimer, si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="7b2f6-145">You can review details of each document and print them, if you wish.</span></span>  

