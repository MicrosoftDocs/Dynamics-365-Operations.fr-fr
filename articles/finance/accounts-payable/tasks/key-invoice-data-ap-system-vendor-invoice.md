---
title: Données de facture clés dans la comptabilité fournisseur à l’aide d’une facture fournisseur
description: Ce guide de tâche vous aidera à créer une facture fournisseur à partir d’une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l’accusé de réception et de la facture (rapprochement à trois facteurs).
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d3f9fc1fb7724632dbc9c4c3e1e28c6e85eaf61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827792"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="d98fc-103">Données de facture clés dans la comptabilité fournisseur à l’aide d’une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="d98fc-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d98fc-104">Ce guide de tâche vous aidera à créer une facture fournisseur à partir d’une commande fournisseur et à afficher les résultats du rapprochement de la commande fournisseur, de l’accusé de réception et de la facture (rapprochement à trois facteurs).</span><span class="sxs-lookup"><span data-stu-id="d98fc-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="d98fc-105">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="d98fc-105">Create a purchase order</span></span>
1. <span data-ttu-id="d98fc-106">Dans le volet de navigation, allez dans **Modules > Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="d98fc-107">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-107">Click **New**.</span></span>
3. <span data-ttu-id="d98fc-108">Dans le champ **Compte fournisseur**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d98fc-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d98fc-109">Recherchez un fournisseur à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="d98fc-109">Find a vendor to select.</span></span> <span data-ttu-id="d98fc-110">Par exemple, faites défiler l’écran jusqu’à US-104.</span><span class="sxs-lookup"><span data-stu-id="d98fc-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="d98fc-111">Sélectionnez le fournisseur US-104.</span><span class="sxs-lookup"><span data-stu-id="d98fc-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="d98fc-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-112">Click **OK**.</span></span>
7. <span data-ttu-id="d98fc-113">Dans le champ **Numéro d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d98fc-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="d98fc-114">Sélectionnez un article en stock.</span><span class="sxs-lookup"><span data-stu-id="d98fc-114">Select an inventory item.</span></span> <span data-ttu-id="d98fc-115">Sélectionnez le numéro d’article 1000, par exemple.</span><span class="sxs-lookup"><span data-stu-id="d98fc-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="d98fc-116">Développez le raccourci **Détails de ligne**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="d98fc-117">Cliquez sur l’onglet **Paramétrage**. Vous pouvez remplacer la stratégie de rapprochement pour n’utiliser aucun rapprochement, utiliser le rapprochement à deux facteurs ou le rapprochement à trois facteurs.</span><span class="sxs-lookup"><span data-stu-id="d98fc-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="d98fc-118">Dans le volet Actions, cliquez sur **Achat**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="d98fc-119">Cliquez sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="d98fc-120">Recevoir les produits</span><span class="sxs-lookup"><span data-stu-id="d98fc-120">Receive the products</span></span>
1. <span data-ttu-id="d98fc-121">Dans le volet Action, cliquez sur **Recevoir**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="d98fc-122">Cliquez sur **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="d98fc-123">Dans le champ **Accusé de réception de marchandises**, entrez le numéro d’accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="d98fc-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="d98fc-124">Par exemple, entrez PR123.</span><span class="sxs-lookup"><span data-stu-id="d98fc-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="d98fc-125">Cliquez sur **OK** pour valider l’accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="d98fc-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="d98fc-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d98fc-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="d98fc-127">Créer une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="d98fc-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="d98fc-128">Dans le volet de navigation, allez dans **Modules > Comptabilité fournisseur > Commandes fournisseur > Commandes fournisseur reçues mais pas facturées**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="d98fc-129">Sélectionnez la commande fournisseur que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="d98fc-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="d98fc-130">Cliquez sur **Facture** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="d98fc-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="d98fc-131">Cliquez sur **Facture**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="d98fc-132">Entrez le numéro de la facture dans le champ **Numéro**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="d98fc-133">Entrez une valeur dans le champ **Description de la facture**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="d98fc-134">Entrez une date dans le champ **Date de facture**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="d98fc-135">Entrez 1 200 dans le champ **Prix unitaire**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="d98fc-136">Cliquez sur **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-136">Click **Add line**.</span></span>
10. <span data-ttu-id="d98fc-137">Dans le champ **Numéro d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="d98fc-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="d98fc-138">Dans la liste, recherchez le numéro d’article de frais d’installation.</span><span class="sxs-lookup"><span data-stu-id="d98fc-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="d98fc-139">Par exemple, S0001.</span><span class="sxs-lookup"><span data-stu-id="d98fc-139">For example, S0001</span></span>
12. <span data-ttu-id="d98fc-140">Sélectionnez le numéro d’article de frais d’installation.</span><span class="sxs-lookup"><span data-stu-id="d98fc-140">Select the installation charge item number.</span></span> <span data-ttu-id="d98fc-141">Notez qu’aucun rapprochement n’a été effectué depuis que vous avez apporté des modifications.</span><span class="sxs-lookup"><span data-stu-id="d98fc-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="d98fc-142">Cliquez sur **Mettre à jour le statut de rapprochement**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="d98fc-143">Cliquez sur **Revoir** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="d98fc-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="d98fc-144">Cliquez sur **Mise en correspondance des détails**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-144">Click **Matching details**.</span></span> <span data-ttu-id="d98fc-145">La nouvelle ligne avec les services n’a pas besoin d’être mise en correspondance, le statut indique donc « Non exécuté ».</span><span class="sxs-lookup"><span data-stu-id="d98fc-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="d98fc-146">Sélectionnez l’accusé de réception de marchandises pour l’article en stock que vous avez reçu.</span><span class="sxs-lookup"><span data-stu-id="d98fc-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="d98fc-147">La ligne contenant l’accusé de réception de marchandises a été rapprochée, mais elle a échoué car il y a une incohérence au niveau de la quantité ou du prix.</span><span class="sxs-lookup"><span data-stu-id="d98fc-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="d98fc-148">Entrez un nombre dans le champ **Prix unitaire**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="d98fc-149">Maintenant que le prix unitaire correspond, le statut est mis à jour et indique Transmis.</span><span class="sxs-lookup"><span data-stu-id="d98fc-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="d98fc-150">Si votre stratégie autorise les écarts ou si le rapprochement n’est qu’un avertissement, vous pouvez toujours valider la facture.</span><span class="sxs-lookup"><span data-stu-id="d98fc-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="d98fc-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d98fc-151">Close the page.</span></span>
19. <span data-ttu-id="d98fc-152">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="d98fc-152">Click **Post**.</span></span>
20. <span data-ttu-id="d98fc-153">Permet de fermer l’écran.</span><span class="sxs-lookup"><span data-stu-id="d98fc-153">Close the form.</span></span> <span data-ttu-id="d98fc-154">Notez que la commande fournisseur n’est plus répertoriée comme étant reçue mais non facturée.</span><span class="sxs-lookup"><span data-stu-id="d98fc-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]