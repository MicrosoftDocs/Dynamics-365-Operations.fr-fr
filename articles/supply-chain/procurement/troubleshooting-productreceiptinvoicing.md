---
title: Résoudre les problèmes liés aux accusés de réception de marchandises et à la facturation
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des accusés de réception de marchandises et la facturation.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018627"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="b1fd6-103">Résoudre les problèmes liés aux accusés de réception de marchandises et à la facturation</span><span class="sxs-lookup"><span data-stu-id="b1fd6-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="b1fd6-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des accusés de réception de marchandises et la facturation.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="b1fd6-105">Je ne peux pas valider plus d'une facture pour une ligne de commande fournisseur contenant des articles basés sur la catégorie.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="b1fd6-106">Une quantité est obligatoire si vous souhaitez valider des factures.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="b1fd6-107">Par conséquent, si la quantité totale d'une ligne n'a été facturée que pour un montant partiel, vous ne pourrez pas facturer le montant restant sur une autre facture.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="b1fd6-108">Je reçois une erreur "Référence d'objet non définie" lors de la confirmation de la commande fournisseur, ou une exception "Une exception a été levée par la cible d'un appel" se produit lors de la validation de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="b1fd6-109">Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="b1fd6-110">Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon* , allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="b1fd6-111">Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="b1fd6-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="b1fd6-112">Je ne peux pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="b1fd6-113">Vous ne pouvez pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur si les différentes lignes d'accusé de réception de marchandises ont des dates comptables différentes.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="b1fd6-114">Dans les versions antérieures de Microsoft Dynamics 365 Supply Chain Management, la consolidation était autorisée dans cette situation.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="b1fd6-115">Cependant, la pratique pouvait causer des erreurs.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-115">However, the practice is prone to error.</span></span> <span data-ttu-id="b1fd6-116">La date comptable sur les lignes de commande fournisseur qui sont créées ne doit pas différer de la date comptable sur les lignes d'accusé de réception de marchandises à partir desquelles ces lignes de commande fournisseur ont été créées.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="b1fd6-117">(La date comptable sur les lignes de commande fournisseur correspond à la date comptable sur l'en-tête de commande fournisseur.) Par conséquent, la consolidation de plusieurs accusés de réception de marchandises en une seule commande fournisseur n'est plus autorisée.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="b1fd6-118">La date comptable est utilisée, par exemple, pour les réservations budgétaires et les engagements.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="b1fd6-119">Par conséquent, elle doit être conservée pendant la transition de l'accusé de réception de marchandises à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="b1fd6-120">Lorsque les accusés de réception de marchandises sont annulés, les transactions peuvent être imputées sur un compte général suspendu.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1fd6-121">Description du problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-121">Issue description</span></span>

<span data-ttu-id="b1fd6-122">Si un accusé de réception de marchandises est annulé, le système autorise la validation des transactions sur les comptes généraux suspendus, même si les comptes principaux sont suspendus.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="b1fd6-123">Reproduire le problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-123">Reproduce the issue</span></span>

<span data-ttu-id="b1fd6-124">La procédure suivante montre comment reproduire le problème.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="b1fd6-125">Sur la page **Paramètres de la comptabilité fournisseur** , sur l'onglet **Général** , assurez-vous que l'option **Valider l'accusé de réception de marchandises dans la comptabilité** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="b1fd6-126">Créez une commande fournisseur et ajoutez une ligne de commande d'une quantité de *1 000* pour un produit.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="b1fd6-127">Confirmez la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="b1fd6-128">Validez l'accusé de réception de marchandises et vérifiez les bons.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="b1fd6-129">Suspendez les comptes principaux concernés, *200140* et *140200*.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="b1fd6-130">Annulez l'accusé de réception de marchandises validé.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="b1fd6-131">Notez que les transactions peuvent être validées sur les comptes généraux suspendus.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1fd6-132">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-132">Issue resolution</span></span>

<span data-ttu-id="b1fd6-133">Les transactions peuvent être validées sur les comptes généraux suspendus lorsque les accusés de réception de marchandise sont annulés, car ce comportement permet des validations correctes.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="b1fd6-134">Un numéro document d'accusé de réception de marchandises est consommé même si aucun document financier n'est généré lors de la réception de produit.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="b1fd6-135">Si l'option **Provisionner le passif sur l'accusé de réception de marchandises** est définie sur *Non* pour le groupe de modèles d'article, aucune validation dans la comptabilité n'aura lieu.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="b1fd6-136">Cependant, un événement physique sera enregistré à des fins de comptabilisation dans une comptabilité auxiliaire, et cet événement nécessite un numéro de document.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="b1fd6-137">Ce numéro de document est le numéro de document qui est référencé dans les mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="b1fd6-138">Nous vous recommandons de définir l'option **Provisionner le passif sur l'accusé de réception de marchandises** sur *Oui* , comme décrit dans l'article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="b1fd6-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes* , as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="b1fd6-139">Le paramètre Valider sur le compte de frais dans la comptabilité n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b1fd6-140">Description du problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-140">Issue description</span></span>

<span data-ttu-id="b1fd6-141">Ce problème se produit lorsqu'une commande fournisseur est facturée, si l'option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l'onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="b1fd6-142">Reproduire le problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-142">Reproduce the issue</span></span>

<span data-ttu-id="b1fd6-143">La procédure suivante montre comment reproduire le problème.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="b1fd6-144">Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="b1fd6-145">Sur l'onglet **Facture** , définissez l'option **Valider sur le compte de frais dans la comptabilité** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="b1fd6-146">Accédez à **Gestion des stocks \> Paramétrage \> Validation \> Validation**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="b1fd6-147">Sur l'onglet **Commande fournisseur** , assurez-vous d'avoir supprimé toutes les lignes de dépenses d'achat pour le produit.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="b1fd6-148">Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b1fd6-149">Création d'une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-149">Create a purchase order.</span></span> <span data-ttu-id="b1fd6-150">Dans le champ **Compte fournisseur** , sélectionnez *1001 Fournitures de bureau Acme*.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="b1fd6-151">Ajoutez une ligne de commande fournisseur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="b1fd6-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="b1fd6-152">**Numéro d'article :** *Projecteur laser D0011*</span><span class="sxs-lookup"><span data-stu-id="b1fd6-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="b1fd6-153">**Site :** *1*</span><span class="sxs-lookup"><span data-stu-id="b1fd6-153">**Site:** *1*</span></span>
    - <span data-ttu-id="b1fd6-154">**Entrepôt :** *11*</span><span class="sxs-lookup"><span data-stu-id="b1fd6-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="b1fd6-155">**Quantité :** *4*</span><span class="sxs-lookup"><span data-stu-id="b1fd6-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="b1fd6-156">Dans le volet Actions, sous l'onglet **Achats** , dans le groupe **Action** , cliquez sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="b1fd6-157">Dans le volet Actions, sous l'onglet **Recevoir** , dans le groupe **Générer** , sélectionnez **Accusé de réception de marchandises**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="b1fd6-158">Dans la boîte de dialogue **Validation de l’accusé de réception de produits** , dans le champ **Accusé de réception de produits** , entrez un nombre arbitraire, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="b1fd6-159">Dans le volet Actions, sous l'onglet **Facture** , dans le groupe **Générer** , sélectionnez **Facture**.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="b1fd6-160">Dans le champ **Numéro** , entrez un numéro arbitraire comme numéro de facture.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="b1fd6-161">Mettez à jour le statut de rapprochement et validez.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="b1fd6-162">Notez que vous recevez maintenant l'erreur suivante lorsque vous générez une facture à partir d'une commande fournisseur : "Le numéro de compte pour le type de transaction Dépenses d'achat pour le produit n'existe pas".</span><span class="sxs-lookup"><span data-stu-id="b1fd6-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b1fd6-163">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="b1fd6-163">Issue resolution</span></span>

<span data-ttu-id="b1fd6-164">Cela dépend des paramètres des factures et des groupes de factures.</span><span class="sxs-lookup"><span data-stu-id="b1fd6-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="b1fd6-165">Pour plus d'informations, consultez l'article de blog suivant : [Comptabilité pour les frais d'achat et la variation des stocks](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="b1fd6-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>
