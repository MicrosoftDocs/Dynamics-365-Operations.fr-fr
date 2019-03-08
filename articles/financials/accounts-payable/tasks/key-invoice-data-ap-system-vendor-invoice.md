---
title: Données de facture clés dans le système de comptabilité fournisseur à l'aide de la facture fournisseur
description: Ce guide de tâche vous aidera à créer une facture fournisseur à partir d'une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l'accusé de réception et de la facture (rapprochement à trois facteurs).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359104"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="5e85a-103">Données de facture clés dans le système de comptabilité fournisseur à l'aide de la facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="5e85a-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e85a-104">Ce guide de tâche vous aidera à créer une facture fournisseur à partir d'une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l'accusé de réception et de la facture (rapprochement à trois facteurs).</span><span class="sxs-lookup"><span data-stu-id="5e85a-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="5e85a-105">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="5e85a-105">Create a purchase order</span></span>
1. <span data-ttu-id="5e85a-106">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5e85a-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="5e85a-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5e85a-107">Click New.</span></span>
3. <span data-ttu-id="5e85a-108">Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5e85a-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5e85a-109">Recherchez un fournisseur à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="5e85a-109">Find a vendor to select.</span></span> <span data-ttu-id="5e85a-110">Par exemple, faites défiler l'écran jusqu'à US-104.</span><span class="sxs-lookup"><span data-stu-id="5e85a-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="5e85a-111">Sélectionnez le fournisseur US-104.</span><span class="sxs-lookup"><span data-stu-id="5e85a-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="5e85a-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5e85a-112">Click OK.</span></span>
7. <span data-ttu-id="5e85a-113">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5e85a-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5e85a-114">Sélectionnez un article en stock.</span><span class="sxs-lookup"><span data-stu-id="5e85a-114">Select an inventory item.</span></span> <span data-ttu-id="5e85a-115">Sélectionnez le numéro d'article 1000, par exemple.</span><span class="sxs-lookup"><span data-stu-id="5e85a-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="5e85a-116">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="5e85a-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="5e85a-117">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="5e85a-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="5e85a-118">Vous pouvez remplacer la stratégie de rapprochement pour n'utiliser aucun rapprochement, utiliser le rapprochement à deux facteurs ou le rapprochement à trois facteurs.</span><span class="sxs-lookup"><span data-stu-id="5e85a-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="5e85a-119">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="5e85a-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="5e85a-120">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5e85a-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="5e85a-121">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="5e85a-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="5e85a-122">Recevoir les produits</span><span class="sxs-lookup"><span data-stu-id="5e85a-122">Receive the products</span></span>
1. <span data-ttu-id="5e85a-123">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="5e85a-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="5e85a-124">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="5e85a-124">Click Product receipt.</span></span>
3. <span data-ttu-id="5e85a-125">Dans le champ Accusé de réception de marchandises, entrez le numéro d'accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="5e85a-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="5e85a-126">Par exemple, entrez PR123.</span><span class="sxs-lookup"><span data-stu-id="5e85a-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="5e85a-127">Cliquez sur OK pour valider l'accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="5e85a-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="5e85a-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5e85a-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="5e85a-129">Créer une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="5e85a-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="5e85a-130">Accédez à Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur reçues mais pas facturées.</span><span class="sxs-lookup"><span data-stu-id="5e85a-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="5e85a-131">Sélectionnez la commande fournisseur que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="5e85a-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="5e85a-132">Cliquez sur Facture dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5e85a-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="5e85a-133">Cliquez sur Facture.</span><span class="sxs-lookup"><span data-stu-id="5e85a-133">Click Invoice.</span></span>
5. <span data-ttu-id="5e85a-134">Entrez le numéro de la facture dans le champ Numéro.</span><span class="sxs-lookup"><span data-stu-id="5e85a-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="5e85a-135">Entrez une valeur dans le champ Description de la facture.</span><span class="sxs-lookup"><span data-stu-id="5e85a-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="5e85a-136">Entrez une date dans le champ Date de facture.</span><span class="sxs-lookup"><span data-stu-id="5e85a-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="5e85a-137">Entrez 1200 dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="5e85a-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="5e85a-138">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="5e85a-138">Click Add line.</span></span>
10. <span data-ttu-id="5e85a-139">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="5e85a-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="5e85a-140">Dans la liste, recherchez le numéro d'article de frais d'installation.</span><span class="sxs-lookup"><span data-stu-id="5e85a-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="5e85a-141">Par exemple, S0001.</span><span class="sxs-lookup"><span data-stu-id="5e85a-141">For example, S0001</span></span>
12. <span data-ttu-id="5e85a-142">Sélectionnez le numéro d'article de frais d'installation.</span><span class="sxs-lookup"><span data-stu-id="5e85a-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="5e85a-143">Notez qu'aucun rapprochement n'a été effectué depuis que vous avez apporté des modifications.</span><span class="sxs-lookup"><span data-stu-id="5e85a-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="5e85a-144">Cliquez sur Mettre à jour le statut de rapprochement.</span><span class="sxs-lookup"><span data-stu-id="5e85a-144">Click Update match status.</span></span>
14. <span data-ttu-id="5e85a-145">Cliquez sur Revoir dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5e85a-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="5e85a-146">Cliquez sur Mise en correspondance des détails.</span><span class="sxs-lookup"><span data-stu-id="5e85a-146">Click Matching details.</span></span>
    * <span data-ttu-id="5e85a-147">La nouvelle ligne avec les services n'a pas besoin d'être mise en correspondance, le statut indique donc « Non exécuté ».</span><span class="sxs-lookup"><span data-stu-id="5e85a-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="5e85a-148">Sélectionnez l'accusé de réception de marchandises pour l'article en stock que vous avez reçu.</span><span class="sxs-lookup"><span data-stu-id="5e85a-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="5e85a-149">La ligne contenant l'accusé de réception de marchandises a été rapprochée, mais elle a échoué car il y a une incohérence au niveau de la quantité ou du prix.</span><span class="sxs-lookup"><span data-stu-id="5e85a-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="5e85a-150">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="5e85a-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="5e85a-151">Maintenant que le prix unitaire correspond, le statut est mis à jour et indique Transmis.</span><span class="sxs-lookup"><span data-stu-id="5e85a-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="5e85a-152">Si votre stratégie autorise les écarts ou si le rapprochement n'est qu'un avertissement, vous pouvez toujours valider la facture.</span><span class="sxs-lookup"><span data-stu-id="5e85a-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="5e85a-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5e85a-153">Close the page.</span></span>
19. <span data-ttu-id="5e85a-154">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="5e85a-154">Click Post.</span></span>
20. <span data-ttu-id="5e85a-155">Permet de fermer l'écran.</span><span class="sxs-lookup"><span data-stu-id="5e85a-155">Close the form.</span></span>
    * <span data-ttu-id="5e85a-156">Notez que la commande fournisseur n'est plus répertoriée comme étant reçue mais non facturée.</span><span class="sxs-lookup"><span data-stu-id="5e85a-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

