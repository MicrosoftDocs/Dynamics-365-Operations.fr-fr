---
title: Créer des factures de commande client
description: Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba8e0f02f2d1eb12cecc2c434fbca1e198cddbe9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842951"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="541a5-103">Créer des factures de commande client</span><span class="sxs-lookup"><span data-stu-id="541a5-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="541a5-104">Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="541a5-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="541a5-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="541a5-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="541a5-106">Créer une facture à partir d'une commande client</span><span class="sxs-lookup"><span data-stu-id="541a5-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="541a5-107">Allez dans Comptabilité client > Commandes > Commandes client expédiées mais pas facturées.</span><span class="sxs-lookup"><span data-stu-id="541a5-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="541a5-108">Sélectionnez une commande client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="541a5-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="541a5-109">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="541a5-110">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-110">Click Invoice.</span></span>
    * <span data-ttu-id="541a5-111">Notez que cette commande client a plusieurs bons de livraison associés.</span><span class="sxs-lookup"><span data-stu-id="541a5-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="541a5-112">Elle indique uniquement le mot <multiple> au lieu du numéro de bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="541a5-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="541a5-113">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="541a5-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="541a5-114">La validation doit être définie sur Oui pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="541a5-115">Vous pouvez également désactiver la validation et simplement imprimer la facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="541a5-116">Toutefois, vous pouvez obtenir le même résultat en créant une facture pro forma au lieu d'une facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="541a5-117">Cette option est utilisée pour les traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="541a5-117">This option is used for batch jobs.</span></span> <span data-ttu-id="541a5-118">La requête est exécutée lorsque le traitement par lots est exécuté.</span><span class="sxs-lookup"><span data-stu-id="541a5-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="541a5-119">Sélectionnez Après dans le champ Imprimer.</span><span class="sxs-lookup"><span data-stu-id="541a5-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="541a5-120">Sélectionnez Oui en regard de Imprimer la facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="541a5-121">La gestion de l'impression peut imprimer plusieurs copies de la facture et soumettre la facture par e-mail sous forme de fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="541a5-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="541a5-122">Sélectionnez Résumer dans le champ Imprimer les frais.</span><span class="sxs-lookup"><span data-stu-id="541a5-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="541a5-123">Sélectionnez Solde dans le champ Vérifier la limite de crédit.</span><span class="sxs-lookup"><span data-stu-id="541a5-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="541a5-124">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="541a5-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="541a5-125">Combiner les commandes en une seule facture</span><span class="sxs-lookup"><span data-stu-id="541a5-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="541a5-126">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="541a5-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="541a5-127">Recherchez un client ayant plusieurs factures en cours.</span><span class="sxs-lookup"><span data-stu-id="541a5-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="541a5-128">Sélectionnez une commande client en cours.</span><span class="sxs-lookup"><span data-stu-id="541a5-128">Select an open sales order.</span></span>
4. <span data-ttu-id="541a5-129">Sélectionnez une autre commande client en cours pour le même client.</span><span class="sxs-lookup"><span data-stu-id="541a5-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="541a5-130">Dans le volet Actions, cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="541a5-131">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-131">Click Invoice.</span></span>
7. <span data-ttu-id="541a5-132">Développez la section Paramètres.</span><span class="sxs-lookup"><span data-stu-id="541a5-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="541a5-133">Sélectionnez « Tout » dans le champ Quantité.</span><span class="sxs-lookup"><span data-stu-id="541a5-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="541a5-134">Notez qu'il existe deux factures répertoriées dans la vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="541a5-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="541a5-135">À présent, nous allons les fusionner dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="541a5-136">Sélectionnez Compte de facturation dans le champ Mise à jour récapitulative pour.</span><span class="sxs-lookup"><span data-stu-id="541a5-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="541a5-137">Cliquez sur Organiser pour fusionner les commandes client dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="541a5-138">Les deux commandes client sont désormais fusionnées dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="541a5-139">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="541a5-139">Click Cancel.</span></span>
12. <span data-ttu-id="541a5-140">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="541a5-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="541a5-141">Valider les factures dans un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="541a5-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="541a5-142">Allez dans Comptabilité client > Factures > Facturation par traitement par lots > Facture.</span><span class="sxs-lookup"><span data-stu-id="541a5-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="541a5-143">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="541a5-143">Click Select.</span></span>
3. <span data-ttu-id="541a5-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="541a5-144">Click OK.</span></span>
4. <span data-ttu-id="541a5-145">Cliquez sur Traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="541a5-145">Click Batch.</span></span>
5. <span data-ttu-id="541a5-146">Cliquez sur Oui pour activer le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="541a5-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="541a5-147">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="541a5-147">Click Recurrence.</span></span>
7. <span data-ttu-id="541a5-148">Sélectionner Jours</span><span class="sxs-lookup"><span data-stu-id="541a5-148">Select Days</span></span>
8. <span data-ttu-id="541a5-149">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="541a5-149">Click OK.</span></span>
9. <span data-ttu-id="541a5-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="541a5-150">Click OK.</span></span>
10. <span data-ttu-id="541a5-151">Cliquez sur Annuler.</span><span class="sxs-lookup"><span data-stu-id="541a5-151">Click Cancel.</span></span>
11. <span data-ttu-id="541a5-152">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="541a5-152">Click Yes.</span></span>

