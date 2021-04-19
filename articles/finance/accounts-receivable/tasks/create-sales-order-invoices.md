---
title: Créer des factures de commande client
description: Ce guide de tâche décrit la facturation d’une commande client, notamment la fusion des factures et le traitement par lots.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 984bb482f357e35dcfa4c08597a6be9e39817b98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837103"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="ea8d9-103">Créer des factures de commande client</span><span class="sxs-lookup"><span data-stu-id="ea8d9-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ea8d9-104">Ce guide de tâche décrit la facturation d’une commande client, notamment la fusion des factures et le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="ea8d9-105">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="ea8d9-106">Créer une facture à partir d’une commande client</span><span class="sxs-lookup"><span data-stu-id="ea8d9-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="ea8d9-107">Accédez au **volet Navigation > Modules > Comptabilité client > Commandes > Commandes client expédiées mais pas facturées**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="ea8d9-108">Sélectionnez une commande client dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="ea8d9-109">Dans le **volet Actions**, cliquez sur **Facture > Générer > Facture**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="ea8d9-110">Notez que cette commande client a plusieurs bons de livraison associés.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="ea8d9-111">Elle indique uniquement le mot <multiple> au lieu du numéro de bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="ea8d9-112">Développez la section **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="ea8d9-113">La validation doit être définie sur Oui pour valider la facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="ea8d9-114">Vous pouvez également désactiver la validation et simplement imprimer la facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="ea8d9-115">Toutefois, vous pouvez obtenir le même résultat en créant une facture pro forma au lieu d’une facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="ea8d9-116">Cette option est utilisée pour les traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-116">This option is used for batch jobs.</span></span> <span data-ttu-id="ea8d9-117">La requête est exécutée lorsque le traitement par lots est exécuté.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="ea8d9-118">Sélectionnez Après dans le champ **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="ea8d9-119">Sélectionnez **Oui** en regard de **Imprimer la facture**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="ea8d9-120">La gestion de l’impression peut imprimer plusieurs copies de la facture et soumettre la facture par e-mail sous forme de fichier PDF.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="ea8d9-121">Sélectionnez Résumer dans le champ **Imprimer les frais**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="ea8d9-122">Dans le champ **Vérifier la limite de crédit**, sélectionnez Solde.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="ea8d9-123">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="ea8d9-124">Combiner les commandes en une seule facture</span><span class="sxs-lookup"><span data-stu-id="ea8d9-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="ea8d9-125">Allez dans **Volet de navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="ea8d9-126">Recherchez un client ayant plusieurs factures en cours.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="ea8d9-127">Sélectionnez plusieurs commandes client en cours du même client.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="ea8d9-128">Dans le **volet Actions**, cliquez sur **Facture > Générer > Facture**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="ea8d9-129">Développez la section **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="ea8d9-130">Dans le champ **Quantité**, sélectionnez ’Tout’.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="ea8d9-131">Notez qu’il existe deux factures répertoriées dans la vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="ea8d9-132">À présent, nous allons les fusionner dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="ea8d9-133">Sélectionnez Compte de facturation dans le champ **Mise à jour récapitulative pour** .</span><span class="sxs-lookup"><span data-stu-id="ea8d9-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="ea8d9-134">Cliquez sur **Organiser** pour fusionner les commandes client dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="ea8d9-135">Les deux commandes client sont désormais fusionnées dans une seule facture.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="ea8d9-136">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="ea8d9-137">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="ea8d9-138">Valider les factures dans un traitement par lots</span><span class="sxs-lookup"><span data-stu-id="ea8d9-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="ea8d9-139">Accédez à **Volet de navigation > Modules > Comptabilité client > Factures > Facturation par traitement par lots > Facture**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="ea8d9-140">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-140">Click **Select**.</span></span>
3. <span data-ttu-id="ea8d9-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-141">Click **OK**.</span></span>
4. <span data-ttu-id="ea8d9-142">Cliquez sur **Lots**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-142">Click **Batch**.</span></span>
5. <span data-ttu-id="ea8d9-143">Sélectionnez sur **Oui** dans **Traitement par lots**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="ea8d9-144">Cliquez sur **Répétition**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="ea8d9-145">Sélectionnez **Jours**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-145">Select **Days**.</span></span>
8. <span data-ttu-id="ea8d9-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-146">Click **OK**.</span></span>
9. <span data-ttu-id="ea8d9-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-147">Click **OK**.</span></span>
10. <span data-ttu-id="ea8d9-148">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="ea8d9-149">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-149">Click **Yes**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]