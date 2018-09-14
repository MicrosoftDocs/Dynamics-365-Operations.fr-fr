--- 
title: "Création d'une commande fournisseur à partir d'une commande client"
description: "Cette procédure vous montre comment créer une commande fournisseur sur la base d'une commande client."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 7991476b86ace92cda513ae8906c62ba7fbbe915
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="7686e-103">Création d'une commande fournisseur à partir d'une commande client</span><span class="sxs-lookup"><span data-stu-id="7686e-103">Create a purchase order from a sales order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7686e-104">Cette procédure vous montre comment créer une commande fournisseur sur la base d'une commande client.</span><span class="sxs-lookup"><span data-stu-id="7686e-104">This procedure shows you how to create a purchase order that is based on a sales order.</span></span> <span data-ttu-id="7686e-105">Les quantités du produit dans la commande fournisseur sont alors désignées pour honorer la demande de la commande client d'origine.</span><span class="sxs-lookup"><span data-stu-id="7686e-105">The product's quantities on the purchase order are then designated to fulfill the demand of the originating sales order.</span></span> <span data-ttu-id="7686e-106">La satisfaction des commandes par ce moyen constitue une alternative à une méthode plus complète et plus optimisée de planification des besoins de distribution.</span><span class="sxs-lookup"><span data-stu-id="7686e-106">Fulfilling sales demand this way is an alternative to a more comprehensive and optimized method of Distribution Requirements Planning.</span></span> <span data-ttu-id="7686e-107">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="7686e-107">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="7686e-108">Création d'une commande fournisseur à partir d'une commande client</span><span class="sxs-lookup"><span data-stu-id="7686e-108">Create a purchase order from a sales order</span></span>
1. <span data-ttu-id="7686e-109">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="7686e-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="7686e-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7686e-110">Click New.</span></span>
3. <span data-ttu-id="7686e-111">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7686e-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7686e-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7686e-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7686e-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7686e-113">Click OK.</span></span>
6. <span data-ttu-id="7686e-114">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7686e-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7686e-115">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7686e-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7686e-116">Si vous utilisez USMF, vous pouvez sélectionner D0001.</span><span class="sxs-lookup"><span data-stu-id="7686e-116">If you're using USMF, you could select D0001.</span></span>  
8. <span data-ttu-id="7686e-117">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="7686e-117">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="7686e-118">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="7686e-118">Click Add line.</span></span>
10. <span data-ttu-id="7686e-119">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7686e-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="7686e-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7686e-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7686e-121">Si vous utilisez USMF, vous pouvez sélectionner T0020.</span><span class="sxs-lookup"><span data-stu-id="7686e-121">If you're using USMF, you could select T0020.</span></span>  
12. <span data-ttu-id="7686e-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7686e-122">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="7686e-123">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="7686e-123">In the Quantity field, enter a number.</span></span>
14. <span data-ttu-id="7686e-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7686e-124">Click Save.</span></span>
15. <span data-ttu-id="7686e-125">Cliquez sur Commandes client dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7686e-125">On the Action Pane, click Sales order.</span></span>
16. <span data-ttu-id="7686e-126">Cliquez sur Commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7686e-126">Click Purchase order.</span></span>
    * <span data-ttu-id="7686e-127">La page Créer une commande client répertorie toutes les lignes de commande client en cours qui ont été copiées à partir de la commande client.</span><span class="sxs-lookup"><span data-stu-id="7686e-127">The Create purchase order page lists all the open sales order lines which have been copied from the sales order.</span></span> <span data-ttu-id="7686e-128">Vous pouvez consulter les détails de la commande et, si nécessaire, vous pouvez modifier des détails sélectionnés tels que la quantité achetée et les conditions tarifaires avant de créer les achats.</span><span class="sxs-lookup"><span data-stu-id="7686e-128">You can review the order details, and if required, you can modify selected details such purchase quantity and pricing terms, before you create the purchases.</span></span>  
17. <span data-ttu-id="7686e-129">Sélectionnez l'option Inclure tout.</span><span class="sxs-lookup"><span data-stu-id="7686e-129">Select the Include all option.</span></span>
    * <span data-ttu-id="7686e-130">Si vous souhaitez générer des commandes fournisseur pour seulement un sous-ensemble des lignes de commande client, sélectionnez ce dernier individuellement.</span><span class="sxs-lookup"><span data-stu-id="7686e-130">If you want to generate purchase orders for only a subset of the sales order lines, select these individually.</span></span>  
    * <span data-ttu-id="7686e-131">Le champ Compte fournisseur peut ou non être déjà rempli avec un numéro de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7686e-131">The Vendor account field may or may not already be populated with a vendor number.</span></span> <span data-ttu-id="7686e-132">Si le fournisseur par défaut est paramétré pour le produit (dans la Couverture de l'article associée), alors ce fournisseur est copié dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="7686e-132">If the default vendor is set up for the product (on the associated Item coverage) then this vendor will be copied  to the line.</span></span> <span data-ttu-id="7686e-133">Dans le cas contraire, vous devez entrer un fournisseur manuellement.</span><span class="sxs-lookup"><span data-stu-id="7686e-133">Otherwise, you must enter a vendor manually.</span></span>  <span data-ttu-id="7686e-134">Dans ce guide, indépendamment du fait que le champ de compte fournisseur contienne déjà ou une valeur pas, les étapes suivantes vous demandent de sélectionner un fournisseur différent pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="7686e-134">In this guide, regardless of whether the Vendor account field already contains a value or not, the following steps instruct you to select a new vendor which is different for each line.</span></span>  
18. <span data-ttu-id="7686e-135">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7686e-135">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="7686e-136">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7686e-136">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="7686e-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7686e-137">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="7686e-138">Sélectionnez la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="7686e-138">Select the second order line.</span></span>
22. <span data-ttu-id="7686e-139">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7686e-139">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="7686e-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7686e-140">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="7686e-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7686e-141">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="7686e-142">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="7686e-142">Click Validate.</span></span>
26. <span data-ttu-id="7686e-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7686e-143">Click OK.</span></span>
    * <span data-ttu-id="7686e-144">Le message vous indique qu'une ou plusieurs commandes fournisseurs ont été créées.</span><span class="sxs-lookup"><span data-stu-id="7686e-144">The message informs you that one or more purchase orders have been created.</span></span> <span data-ttu-id="7686e-145">Le système génère une commande fournisseur distincte pour chaque fournisseur spécifié pour les lignes de commande client.</span><span class="sxs-lookup"><span data-stu-id="7686e-145">The system generates a separate purchase order for each vendor that you specified for the sales order lines.</span></span> <span data-ttu-id="7686e-146">Cela signifie que si plusieurs lignes de commande client doivent être fournies par le même fournisseur, une commande fournisseur unique avec plusieurs lignes est générée.</span><span class="sxs-lookup"><span data-stu-id="7686e-146">This means that if several sales order lines are to be supplied by the same vendor, a single purchase order with multiple lines will be generated.</span></span>  

## <a name="review-purchase-orders-created-from-sales-orders"></a><span data-ttu-id="7686e-147">Examiner les commandes fournisseurs créées à partir de commandes client</span><span class="sxs-lookup"><span data-stu-id="7686e-147">Review purchase orders created from sales orders</span></span>
1. <span data-ttu-id="7686e-148">Cliquez sur Général dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7686e-148">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="7686e-149">Cliquez sur Commandes associées.</span><span class="sxs-lookup"><span data-stu-id="7686e-149">Click Related orders.</span></span>
    * <span data-ttu-id="7686e-150">La page Commandes associées répertorie toutes les commandes créées à partir de la commande client.</span><span class="sxs-lookup"><span data-stu-id="7686e-150">The Related orders page lists all the orders that were created from the sales order.</span></span> <span data-ttu-id="7686e-151">Dans cet exemple, il existe deux commandes fournisseur générées pour deux fournisseurs distincts respectivement.</span><span class="sxs-lookup"><span data-stu-id="7686e-151">In this example, there are two purchase orders generated for two different vendors respectively.</span></span>  
3. <span data-ttu-id="7686e-152">Cliquez ici pour suivre le lien du champ Commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7686e-152">Click to follow the link in the Purchase order field.</span></span>
    * <span data-ttu-id="7686e-153">Chaque ligne de commande fournisseur est associée à la ligne de commande client ayant mené à l'achat.</span><span class="sxs-lookup"><span data-stu-id="7686e-153">Each purchase order line is associated with the sales order line that led to the purchase.</span></span> <span data-ttu-id="7686e-154">La relation avec la commande client est indiquée sous l'onglet Produit dans l'organisateur Détails de ligne et les champs Type de référence, Numéro de référence et Référence de lot.</span><span class="sxs-lookup"><span data-stu-id="7686e-154">The relation to the sales order is indicated on the Product tab in the Line details FastTab, in the Reference type, Reference number, and Reference lot fields.</span></span>  
4. <span data-ttu-id="7686e-155">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="7686e-155">Expand or collapse the Line details section.</span></span>
5. <span data-ttu-id="7686e-156">Cliquez sur l'onglet Produit.</span><span class="sxs-lookup"><span data-stu-id="7686e-156">Click the Product tab.</span></span>
    * <span data-ttu-id="7686e-157">Le Lot de référence garantit la facturation des coûts des achats en cours sur la commande client liée.</span><span class="sxs-lookup"><span data-stu-id="7686e-157">The Reference lot guarantees that the costs from the current purchase are charged on the attached sales order.</span></span>  
    * <span data-ttu-id="7686e-158">Vous pouvez accéder à la commande client d'origine en ouvrant le lien dans le champ Numéro de référence.</span><span class="sxs-lookup"><span data-stu-id="7686e-158">You can navigate to the originating sales order by opening the link in the Reference number field.</span></span>  


