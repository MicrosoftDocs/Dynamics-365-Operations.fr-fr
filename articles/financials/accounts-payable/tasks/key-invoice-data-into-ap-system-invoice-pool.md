---
title: Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures
description: Ce guide de tâche va vous indiquer comment utiliser le registre des factures pour créer des factures.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b4e9a52a383d4acc0bf2adc669fd88c0c0f7402
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550349"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="99e7a-103">Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures</span><span class="sxs-lookup"><span data-stu-id="99e7a-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99e7a-104">Ce guide de tâche va vous indiquer comment utiliser le registre des factures pour créer des factures.</span><span class="sxs-lookup"><span data-stu-id="99e7a-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="99e7a-105">Utilisez ensuite le regroupement de factures pour mettre en correspondance la facture avec une commande fournisseur et finalisez la dépense dans la page de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="99e7a-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="99e7a-106">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="99e7a-106">Create a purchase order</span></span>
1. <span data-ttu-id="99e7a-107">Allez dans Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="99e7a-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="99e7a-108">Cliquez sur Nouveau pour créer une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="99e7a-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="99e7a-109">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="99e7a-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="99e7a-110">Sélectionnez le fournisseur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="99e7a-110">Select the vendor from the list.</span></span> <span data-ttu-id="99e7a-111">Par exemple, fournisseur 1001.</span><span class="sxs-lookup"><span data-stu-id="99e7a-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="99e7a-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="99e7a-112">Click OK.</span></span>
6. <span data-ttu-id="99e7a-113">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="99e7a-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="99e7a-114">Recherchez le numéro d'article de services dans la liste.</span><span class="sxs-lookup"><span data-stu-id="99e7a-114">Find the services item number in the list.</span></span> <span data-ttu-id="99e7a-115">Par exemple, sélectionnez S0001.</span><span class="sxs-lookup"><span data-stu-id="99e7a-115">For example, select S0001.</span></span>
8. <span data-ttu-id="99e7a-116">Cliquez sur le numéro d'article et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="99e7a-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="99e7a-117">Le montant HT est de 75,00 €.</span><span class="sxs-lookup"><span data-stu-id="99e7a-117">The net amount is 75.00.</span></span>  <span data-ttu-id="99e7a-118">Il s'agit du montant attendu sur la facture.</span><span class="sxs-lookup"><span data-stu-id="99e7a-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="99e7a-119">Dans le volet Actions, cliquez sur Achat.</span><span class="sxs-lookup"><span data-stu-id="99e7a-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="99e7a-120">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="99e7a-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="99e7a-121">Créer et valider une facture</span><span class="sxs-lookup"><span data-stu-id="99e7a-121">Create and post and invoice</span></span>
1. <span data-ttu-id="99e7a-122">Accédez à Comptabilité fournisseur > Factures > Registre des factures.</span><span class="sxs-lookup"><span data-stu-id="99e7a-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="99e7a-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="99e7a-123">Click New.</span></span>
3. <span data-ttu-id="99e7a-124">Ouvrez la recherche pour sélectionner le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="99e7a-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="99e7a-125">Sélectionnez le nom du registre des factures à utiliser.</span><span class="sxs-lookup"><span data-stu-id="99e7a-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="99e7a-126">Cliquez sur Lignes pour ouvrir le registre, puis entrez des lignes de dépense.</span><span class="sxs-lookup"><span data-stu-id="99e7a-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="99e7a-127">Sélectionnez un fournisseur dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="99e7a-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="99e7a-128">Par exemple, cliquez sur fournisseur 1001.</span><span class="sxs-lookup"><span data-stu-id="99e7a-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="99e7a-129">Entrez le numéro de la facture dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="99e7a-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="99e7a-130">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="99e7a-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="99e7a-131">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="99e7a-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="99e7a-132">Dans le champ Commande fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="99e7a-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="99e7a-133">Sélectionnez la commande fournisseur que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="99e7a-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="99e7a-134">Dans le champ Approbateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="99e7a-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="99e7a-135">Mettez un approbateur en surbrillance et cliquez sur Sélectionner pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="99e7a-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="99e7a-136">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="99e7a-136">Click Post.</span></span>
15. <span data-ttu-id="99e7a-137">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="99e7a-137">Close the form.</span></span>
16. <span data-ttu-id="99e7a-138">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="99e7a-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="99e7a-139">Ouvrez une facture à partir du regroupement et faites-la correspondre à une commande fournisseur pour terminer le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="99e7a-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="99e7a-140">Accédez à Comptabilité fournisseur > Factures > Registre des factures.</span><span class="sxs-lookup"><span data-stu-id="99e7a-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="99e7a-141">Cliquez sur Commande fournisseur pour créer une facture fournisseur à partir de la facture dans le registre.</span><span class="sxs-lookup"><span data-stu-id="99e7a-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="99e7a-142">Sélectionnez la facture que vous souhaitez réviser.</span><span class="sxs-lookup"><span data-stu-id="99e7a-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="99e7a-143">Cliquez sur Mettre à jour le statut de rapprochement pour terminer le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="99e7a-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="99e7a-144">Dans le volet Actions, cliquez sur Options.</span><span class="sxs-lookup"><span data-stu-id="99e7a-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="99e7a-145">Cliquez sur Changer de vue.</span><span class="sxs-lookup"><span data-stu-id="99e7a-145">Click Change view.</span></span>
7. <span data-ttu-id="99e7a-146">Cliquez sur Vue grille.</span><span class="sxs-lookup"><span data-stu-id="99e7a-146">Click Grid view.</span></span>
8. <span data-ttu-id="99e7a-147">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="99e7a-147">Click Post.</span></span>
9. <span data-ttu-id="99e7a-148">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="99e7a-148">Close the form.</span></span>
10. <span data-ttu-id="99e7a-149">Allez dans Comptabilité fournisseur > Fournisseurs > Fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="99e7a-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="99e7a-150">Sélectionnez le fournisseur qui était sur la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="99e7a-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="99e7a-151">Par exemple, sélectionnez fournisseur 1001.</span><span class="sxs-lookup"><span data-stu-id="99e7a-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="99e7a-152">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="99e7a-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="99e7a-153">Dans le volet Actions, cliquez sur Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="99e7a-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="99e7a-154">Cliquez sur Transactions.</span><span class="sxs-lookup"><span data-stu-id="99e7a-154">Click Transactions.</span></span>
15. <span data-ttu-id="99e7a-155">Sélectionnez la facture que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="99e7a-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="99e7a-156">La régularisation du registre des factures a été contrepassée et validée dans le compte de dépenses approprié.</span><span class="sxs-lookup"><span data-stu-id="99e7a-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

