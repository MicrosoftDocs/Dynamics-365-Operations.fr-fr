--- 
title: "Créer des factures de commande client"
description: "Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="ff020-103">Créer des factures de commande client</span><span class="sxs-lookup"><span data-stu-id="ff020-103">Create sales order invoices</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff020-104">Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ff020-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="ff020-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ff020-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="ff020-106">Créer une facture à partir d'une commande client</span><span class="sxs-lookup"><span data-stu-id="ff020-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="ff020-107">Allez dans Comptabilité client > Commandes > Commandes client expédiées mais pas facturées.</span><span class="sxs-lookup"><span data-stu-id="ff020-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="ff020-108">Sélectionnez une commande client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ff020-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="ff020-109">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="ff020-110">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-110">Click Invoice.</span></span>
    * <span data-ttu-id="ff020-111">Notez que cette commande client a plusieurs bons de livraison associés.</span><span class="sxs-lookup"><span data-stu-id="ff020-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="ff020-112">Elle indique uniquement le mot <multiple> au lieu du numéro de bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff020-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="ff020-113">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="ff020-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="ff020-114">La validation doit être définie sur Oui pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="ff020-115">Vous pouvez également désactiver la validation et simplement imprimer la facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="ff020-116">Toutefois, vous pouvez obtenir le même résultat en créant une facture pro forma au lieu d'une facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="ff020-117">Cette option est utilisée pour les traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="ff020-117">This option is used for batch jobs.</span></span> <span data-ttu-id="ff020-118">La requête est exécutée lorsque le traitement par lots est exécuté.</span><span class="sxs-lookup"><span data-stu-id="ff020-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="ff020-119">Sélectionnez Après dans le champ Imprimer.</span><span class="sxs-lookup"><span data-stu-id="ff020-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="ff020-120">Sélectionnez Oui en regard de Imprimer la facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="ff020-121">La gestion de l'impression peut imprimer plusieurs copies de la facture et soumettre la facture par e-mail sous forme de fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="ff020-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="ff020-122">Sélectionnez Résumer dans le champ Imprimer les frais.</span><span class="sxs-lookup"><span data-stu-id="ff020-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="ff020-123">Sélectionnez Solde dans le champ Vérifier la limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="ff020-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="ff020-124">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="ff020-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="ff020-125">Combiner les commandes en une seule facture</span><span class="sxs-lookup"><span data-stu-id="ff020-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="ff020-126">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="ff020-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="ff020-127">Recherchez un client ayant plusieurs factures en cours.</span><span class="sxs-lookup"><span data-stu-id="ff020-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="ff020-128">Sélectionnez une commande client en cours.</span><span class="sxs-lookup"><span data-stu-id="ff020-128">Select an open sales order.</span></span>
4. <span data-ttu-id="ff020-129">Sélectionnez une autre commande client en cours pour le même client.</span><span class="sxs-lookup"><span data-stu-id="ff020-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="ff020-130">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="ff020-131">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-131">Click Invoice.</span></span>
7. <span data-ttu-id="ff020-132">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="ff020-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="ff020-133">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="ff020-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="ff020-134">Notez qu'il existe deux factures répertoriées dans la vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="ff020-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="ff020-135">À présent, nous allons les fusionner dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="ff020-136">Sélectionnez Compte de facturation dans le champ Mise à jour récapitulative pour.</span><span class="sxs-lookup"><span data-stu-id="ff020-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="ff020-137">Cliquez sur Organiser pour fusionner les commandes client dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="ff020-138">Les deux commandes client sont désormais fusionnées dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="ff020-139">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="ff020-139">Click Cancel.</span></span>
12. <span data-ttu-id="ff020-140">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="ff020-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="ff020-141">Valider les factures dans un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="ff020-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="ff020-142">Allez dans Comptabilité client > Factures > Facturation par traitement par lots > Facture.</span><span class="sxs-lookup"><span data-stu-id="ff020-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="ff020-143">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="ff020-143">Click Select.</span></span>
3. <span data-ttu-id="ff020-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ff020-144">Click OK.</span></span>
4. <span data-ttu-id="ff020-145">Cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ff020-145">Click Batch.</span></span>
5. <span data-ttu-id="ff020-146">Cliquez sur Oui pour activer le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ff020-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="ff020-147">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="ff020-147">Click Recurrence.</span></span>
7. <span data-ttu-id="ff020-148">Sélectionner Jours</span><span class="sxs-lookup"><span data-stu-id="ff020-148">Select Days</span></span>
8. <span data-ttu-id="ff020-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ff020-149">Click OK.</span></span>
9. <span data-ttu-id="ff020-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ff020-150">Click OK.</span></span>
10. <span data-ttu-id="ff020-151">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="ff020-151">Click Cancel.</span></span>
11. <span data-ttu-id="ff020-152">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="ff020-152">Click Yes.</span></span>


