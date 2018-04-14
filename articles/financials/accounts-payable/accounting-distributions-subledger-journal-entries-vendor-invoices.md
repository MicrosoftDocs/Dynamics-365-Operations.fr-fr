---
title: "Répartitions comptables et écritures de journal de comptabilité auxiliaire pour les factures fournisseur"
description: "Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont la dépense, l'immobilisation, la taxe ou les frais seront reportés sur la facture fournisseur. Chaque montant qui doit être pris en compte lorsque la facture fournisseur est journalisée aura une ou plusieurs répartitions comptables."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 510e3ac8bbec891436eaf6849dfe00b68ba2eb40
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a><span data-ttu-id="edd15-104">Répartitions comptables et écritures de journal de comptabilité auxiliaire pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="edd15-104">Accounting distributions and subledger journal entries for vendor invoices</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="edd15-105">Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont la dépense, l'immobilisation, la taxe ou les frais seront reportés sur la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="edd15-106">Chaque montant qui doit être pris en compte lorsque la facture fournisseur est journalisée aura une ou plusieurs répartitions comptables.</span><span class="sxs-lookup"><span data-stu-id="edd15-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="edd15-107">Répartitions comptables</span><span class="sxs-lookup"><span data-stu-id="edd15-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="edd15-108">Vous pouvez utiliser les boutons suivants de la page Facture fournisseur pour afficher et éventuellement modifier les répartitions comptables pour chaque montant de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="edd15-109">**Répartir des montants** – permet d'afficher et de modifier les répartitions comptables pour une ligne individuelle et toutes les lignes enfants, telles que les taxes ou des frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="edd15-110">Vous pouvez également afficher et modifier les répartitions comptables de la ligne enfant directement dans la page Transactions de taxe ou la page Transactions de frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="edd15-111">Modifiez les montants d'en-tête de facture fournisseur, comme les frais ou les arrondis de devise.</span><span class="sxs-lookup"><span data-stu-id="edd15-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="edd15-112">Modifiez les montants de ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="edd15-113">**Afficher les distributions** – Permet d'afficher les répartitions comptables pour toutes les lignes du document.</span><span class="sxs-lookup"><span data-stu-id="edd15-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="edd15-114">Vous ne pouvez pas modifier les répartitions comptables de cette vue.</span><span class="sxs-lookup"><span data-stu-id="edd15-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="edd15-115">Afficher les montants d'en-tête et de ligne.</span><span class="sxs-lookup"><span data-stu-id="edd15-115">View header and line amounts.</span></span>

<span data-ttu-id="edd15-116">Si la facture fournisseur fait référence à une commande fournisseur, vous pouvez fractionner et modifier les répartitions comptables pour les lignes contenant un article qui n'est pas stocké.</span><span class="sxs-lookup"><span data-stu-id="edd15-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="edd15-117">Si la ligne de facture fournisseur ne fait pas référence à une ligne de commande fournisseur, vous pouvez également supprimer une répartition comptable.</span><span class="sxs-lookup"><span data-stu-id="edd15-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="edd15-118">Vous ne pouvez pas fractionner ou supprimer des lignes pour les frais, les taxes et les remises ligne.</span><span class="sxs-lookup"><span data-stu-id="edd15-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="edd15-119">Vous pouvez modifier le compte général, mais vous ne pouvez pas modifier les montants ou les pourcentages.</span><span class="sxs-lookup"><span data-stu-id="edd15-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="edd15-120">Si la ligne parente contient un article qui n'est pas stocké et les répartitions comptables sont fractionnées, la ligne enfant fractionne automatiquement pour faire correspondre les dimensions financières de la ligne parente.</span><span class="sxs-lookup"><span data-stu-id="edd15-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="edd15-121">Les répartitions comptables de la ligne enfant ne peuvent pas être fractionnées ni supprimées, mais selon le paramétrage de la ligne enfant, vous pouvez modifier le compte général pour les répartitions comptables de la ligne enfant.</span><span class="sxs-lookup"><span data-stu-id="edd15-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="edd15-122">Répartition des montants</span><span class="sxs-lookup"><span data-stu-id="edd15-122">Distributing amounts</span></span>
<span data-ttu-id="edd15-123">Lorsque vous entrez une facture fournisseur, chaque montant est réparti comme suit.</span><span class="sxs-lookup"><span data-stu-id="edd15-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edd15-124">Type de ligne de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="edd15-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="edd15-125">Ordre de priorité qui détermine à partir de quel emplacement le compte principal par défaut s'affiche</span><span class="sxs-lookup"><span data-stu-id="edd15-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="edd15-126">L'ordre de priorité qui détermine la dimension financière par défaut s'affiche</span><span class="sxs-lookup"><span data-stu-id="edd15-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="edd15-127">Produit stocké</span><span class="sxs-lookup"><span data-stu-id="edd15-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-128">La répartition comptable pour la ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="edd15-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-129">Le champ Compte principal lorsque Dépenses d'achat pour le produit est sélectionné dans la page Validation.</span><span class="sxs-lookup"><span data-stu-id="edd15-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-130">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-131">Utilisez les valeurs de dimension financière par défaut de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-132">Catégorie d'approvisionnement, ou produit non stocké.</span><span class="sxs-lookup"><span data-stu-id="edd15-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-133">La répartition comptable pour a ligne de commande fournisseur, si la ligne de facture fournisseur fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-134">Le champ Compte principal lorsque Dépenses d'achat pour dépense est sélectionné dans la page Validation.</span><span class="sxs-lookup"><span data-stu-id="edd15-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-135">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-136">Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</span><span class="sxs-lookup"><span data-stu-id="edd15-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="edd15-137">Utilisez les valeurs de dimension financière par défaut de la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="edd15-138">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-139">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="edd15-140">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="edd15-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-141">La répartition comptable pour a ligne de commande fournisseur, si la ligne de facture fournisseur fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-142">Si Acquisition est sélectionné dans le champ Type de transaction de l'écran Facture fournisseur, le champ Compte principal lorsque Acquisition est sélectionné dans la page Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="edd15-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="edd15-143">Si Ajustement d'acquisition est sélectionné dans le champ Type de transaction, le champ Compte principal lorsque Ajustement d'acquisition est sélectionné dans la page Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="edd15-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-144">Utilisez la répartition comptable pour la ligne de commande fournisseur si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-145">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-146">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-147">Projet défini sur la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-148">La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-149">Si Solde est sélectionné dans le champ Valider les coûts - Article de la page Groupes de projets, le champ Compte principal lorsque Coût est sélectionné dans la page Paramétrage de la validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="edd15-150">Si Résultats est sélectionné dans le champ Valider les coûts - Article de la page Groupes de projets, le champ Compte principal lorsque Coût - Article est sélectionné dans la page Paramétrage de la validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-151">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="edd15-152">Remise ligne</span><span class="sxs-lookup"><span data-stu-id="edd15-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-153">La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-154">Le champ Compte principal lorsque Remise est sélectionné dans la page Validation.</span><span class="sxs-lookup"><span data-stu-id="edd15-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="edd15-155">Si aucun compte principal de remise n'est défini dans le profil de validation, la répartition comptable du prix global de la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-156">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-157">Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-158">Utilisez les valeurs de dimensions financières pour la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-159">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-160">Frais en relation avec les achats, entrés sous l'onglet Prix et remise de la ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="edd15-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-161">La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-162">Répartition comptable du prix global sur la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-163">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-164">Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="edd15-165">Frais de ligne</span><span class="sxs-lookup"><span data-stu-id="edd15-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-166">La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-167">Si Compte général est sélectionné dans le champ Type de débit de l'écran Code frais, le champ Compte à débiter de la page Code frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="edd15-168">Si Article est sélectionné dans le champ Type de débit de l'écran Code frais, la répartition comptable pour le prix global sur la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-169">Si Client/Fournisseur est sélectionné dans le champ Type de débit de l'écran Code frais, le champ Compte à créditer de la page Code frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-170">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-171">Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-172">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-173">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-174">Taxe, qui remplit la condition suivante :</span><span class="sxs-lookup"><span data-stu-id="edd15-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="edd15-175">L'option Appliquer les règles de la taxe américaine est sélectionnée dans la page Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="edd15-176">La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-177">Répartition comptable du prix global ou des frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-178">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-179">Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-180">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="edd15-181">Taxe, qui remplit les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="edd15-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="edd15-182">L'option Appliquer les règles de la taxe américaine est désactivée dans la page Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="edd15-183">Le champ Taxe d'utilisation pour le groupe de taxe est désactivé dans la page Groupes de taxe.</span><span class="sxs-lookup"><span data-stu-id="edd15-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="edd15-184">Si le montant de la taxe est récupérable, le champ Taxe déductible de la page Groupes de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="edd15-185">Si le montant de la taxe n'est pas récupérable, le prix global ou la répartition comptable pour les frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-186">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-187">Utilisez les dimensions financières du prix global ou des répartitions comptables pour les frais de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-188">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-189">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-190">Taxe, qui remplit les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="edd15-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="edd15-191">L'option Appliquer les règles de la taxe américaine est désactivée dans la page Paramètres de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="edd15-192">Le champ Taxe d'utilisation pour le groupe de taxe est sélectionné dans la page Groupes de taxe.</span><span class="sxs-lookup"><span data-stu-id="edd15-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="edd15-193">Si le montant de la taxe est récupérable, le champ Taxe déductible de la page Groupes de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="edd15-194">Si le montant de la taxe n'est pas récupérable, le champ Dépenses de taxe d'utilisation de la page Groupes de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="edd15-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-195">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-196">Utilisez les dimensions financières du prix global ou des répartitions comptables pour les frais de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-197">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-198">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="edd15-199">Frais d'en-tête</span><span class="sxs-lookup"><span data-stu-id="edd15-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-200">Si Compte général est sélectionné dans le champ Type de débit de l'écran Code frais, le champ Compte à débiter de la page Code frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="edd15-201">Si Client/Fournisseur est sélectionné dans le champ Type de débit de l'écran Code frais, le champ Compte à créditer de la page Code frais.</span><span class="sxs-lookup"><span data-stu-id="edd15-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-202">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-203">Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</span><span class="sxs-lookup"><span data-stu-id="edd15-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="edd15-204">Utilisez les valeurs du modèle par défaut de dimension financière de l'en-tête de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="edd15-205">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-206">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="edd15-207">Remise d'en-tête</span><span class="sxs-lookup"><span data-stu-id="edd15-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="edd15-208">Le champ Compte principal pour le type de validation de remise sur la facture fournisseur dans la page Comptes pour transactions automatiques.</span><span class="sxs-lookup"><span data-stu-id="edd15-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="edd15-209">Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="edd15-210">Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-211">Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="edd15-212">Utilisez les valeurs de dimension financière par défaut du compte principal dans la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="edd15-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="edd15-213">Répartition des taxes</span><span class="sxs-lookup"><span data-stu-id="edd15-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="edd15-214">Il est impossible de créer des répartitions comptables pour les taxes tant que ces dernières n'ont pas été calculées.</span><span class="sxs-lookup"><span data-stu-id="edd15-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="edd15-215">Pour calculer les taxes, vous devez effectuer l'une des tâches suivantes dans la page Facture fournisseur :</span><span class="sxs-lookup"><span data-stu-id="edd15-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="edd15-216">Afficher le total de la facture.</span><span class="sxs-lookup"><span data-stu-id="edd15-216">View the invoice total.</span></span>
-   <span data-ttu-id="edd15-217">Afficher la taxe.</span><span class="sxs-lookup"><span data-stu-id="edd15-217">View the sales tax.</span></span>
-   <span data-ttu-id="edd15-218">Afficher le journal de comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="edd15-218">View the subledger journal.</span></span>
-   <span data-ttu-id="edd15-219">Afficher les répartitions comptables pour toute la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="edd15-220">Placer une facture fournisseur en attente.</span><span class="sxs-lookup"><span data-stu-id="edd15-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="edd15-221">Valider la facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="edd15-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="edd15-222">Journaux de comptabilité auxiliaire pour les factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="edd15-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="edd15-223">Avant de valider une facture fournisseur, vous pouvez afficher l'écriture comptable complète de la facture, qui inclut des débits et des crédits, pour vérifier que la facture est validée dans les comptes corrects.</span><span class="sxs-lookup"><span data-stu-id="edd15-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="edd15-224">Cette vue de l'écriture de compte complète est appelée écriture de journal de comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="edd15-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="edd15-225">Si l'écriture de journal de comptabilité auxiliaire est incorrecte lorsque vous en affichez un aperçu avant de journaliser la facture fournisseur, vous ne pouvez pas la modifier.</span><span class="sxs-lookup"><span data-stu-id="edd15-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="edd15-226">Vous devez plutôt modifier les répartitions comptables ou le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="edd15-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="edd15-227">Les répartitions comptables permettent de définir un côté de l'écriture de compte, de débit ou de crédit.</span><span class="sxs-lookup"><span data-stu-id="edd15-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="edd15-228">L'écriture de compte de journal de comptabilité auxiliaire de contrepartie est créée à l'aide des profils de validation, par exemple le compte fournisseur ou la taxe.</span><span class="sxs-lookup"><span data-stu-id="edd15-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>






