---
title: Répartitions comptables et écritures de journal pour les factures financières
description: Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière. Chaque montant qui doit être pris en compte lorsque la facture financière est journalisée aura une ou plusieurs répartitions comptables.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e3e1e0a757dcd51edcd38bb348e52b756e57334
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188756"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a><span data-ttu-id="20b9b-104">Répartitions comptables et écritures de journal pour les factures financières</span><span class="sxs-lookup"><span data-stu-id="20b9b-104">Accounting distributions and subledger entries for free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20b9b-105">Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="20b9b-106">Chaque montant qui doit être pris en compte lorsque la facture financière est journalisée aura une ou plusieurs répartitions comptables.</span><span class="sxs-lookup"><span data-stu-id="20b9b-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

## <a name="accounting-distributions"></a><span data-ttu-id="20b9b-107">Répartitions comptables</span><span class="sxs-lookup"><span data-stu-id="20b9b-107">Accounting distributions</span></span>

<span data-ttu-id="20b9b-108">Vous pouvez utiliser les boutons suivants de la page Facture financière pour afficher et éventuellement modifier les répartitions comptables pour chaque montant de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="20b9b-109">**Répartir les montants** : Permet d’afficher et de modifier les répartitions comptables pour une ligne individuelle et toutes les lignes enfants, telles que des taxes ou des frais.</span><span class="sxs-lookup"><span data-stu-id="20b9b-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="20b9b-110">Vous pouvez également afficher et modifier les répartitions comptables de la ligne enfant directement dans la page Transactions de taxe ou la page Transactions de frais.</span><span class="sxs-lookup"><span data-stu-id="20b9b-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="20b9b-111">Modifiez les montants d’en-tête de facture financière, comme les frais ou les arrondis de devise.</span><span class="sxs-lookup"><span data-stu-id="20b9b-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="20b9b-112">Modifiez les montants de la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="20b9b-113">**Afficher les distributions** : Permet d’afficher les répartitions comptables pour toutes les lignes du document.</span><span class="sxs-lookup"><span data-stu-id="20b9b-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="20b9b-114">Vous ne pouvez pas modifier les répartitions comptables de cette vue.</span><span class="sxs-lookup"><span data-stu-id="20b9b-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="20b9b-115">Afficher les montants d’en-tête et de ligne.</span><span class="sxs-lookup"><span data-stu-id="20b9b-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="20b9b-116">Répartition des montants</span><span class="sxs-lookup"><span data-stu-id="20b9b-116">Distributing amounts</span></span>
<span data-ttu-id="20b9b-117">Lorsque vous entrez une facture financière, chaque montant est réparti comme suit.</span><span class="sxs-lookup"><span data-stu-id="20b9b-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20b9b-118">Type de montant en devises</span><span class="sxs-lookup"><span data-stu-id="20b9b-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="20b9b-119">Origine de l’affichage du compte principal</span><span class="sxs-lookup"><span data-stu-id="20b9b-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="20b9b-120">L’ordre de priorité qui détermine la dimension financière par défaut s’affiche</span><span class="sxs-lookup"><span data-stu-id="20b9b-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="20b9b-121">Ligne de facture financière</span><span class="sxs-lookup"><span data-stu-id="20b9b-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="20b9b-122">Compte général de la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="20b9b-123">Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</span><span class="sxs-lookup"><span data-stu-id="20b9b-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="20b9b-124">Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-125">Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-126">Utilisez les valeurs de dimension financière par défaut du compte général de la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="20b9b-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="20b9b-127">Ligne de facture financière pour une combinaison numéro d’immobilisation et modèle de valeur</span><span class="sxs-lookup"><span data-stu-id="20b9b-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="20b9b-128"><strong>Remarque </strong></span><span class="sxs-lookup"><span data-stu-id="20b9b-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="20b9b-129">Le compte principal sur la ligne de facture financière correspond au compte de la cession d’immobilisation.</span><span class="sxs-lookup"><span data-stu-id="20b9b-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="20b9b-130">Compte général de la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="20b9b-131">Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-132">Utilisez les valeurs de dimension financière par défaut du compte général de la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="20b9b-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="20b9b-133">Montant de remise de facture financière</span><span class="sxs-lookup"><span data-stu-id="20b9b-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="20b9b-134">Le champ Compte principal pour les remises client de la page Escomptes de règlement.</span><span class="sxs-lookup"><span data-stu-id="20b9b-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="20b9b-135">Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</span><span class="sxs-lookup"><span data-stu-id="20b9b-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="20b9b-136">Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-137">Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-138">Utilisez les valeurs de dimension financière par défaut du compte général de la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="20b9b-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="20b9b-139">Montant de la taxe de la facture financière</span><span class="sxs-lookup"><span data-stu-id="20b9b-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="20b9b-140">Le champ Taxe collectée de la page Groupes de validations dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="20b9b-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="20b9b-141">Utilisez les dimensions financières définies sur le montant de la ligne de facture financière ou les répartitions pour le montant de la ligne de frais.</span><span class="sxs-lookup"><span data-stu-id="20b9b-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="20b9b-142">Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-143">Utilisez les valeurs de dimension financière par défaut du compte général de la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="20b9b-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="20b9b-144">Montant de la ligne de frais de la facture financière</span><span class="sxs-lookup"><span data-stu-id="20b9b-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="20b9b-145">Le champ Compte à créditer de la page Code frais.</span><span class="sxs-lookup"><span data-stu-id="20b9b-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="20b9b-146">Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</span><span class="sxs-lookup"><span data-stu-id="20b9b-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="20b9b-147">Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-148">Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="20b9b-149">Utilisez les valeurs de dimension financière par défaut du compte général de la page Plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="20b9b-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="20b9b-150">Répartition des taxes</span><span class="sxs-lookup"><span data-stu-id="20b9b-150">Distributing taxes</span></span>
<span data-ttu-id="20b9b-151">Il est impossible de créer des répartitions comptables pour les taxes tant que ces dernières n’ont pas été calculées.</span><span class="sxs-lookup"><span data-stu-id="20b9b-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="20b9b-152">Pour calculer les taxes, vous devez effectuer l’une des tâches suivantes dans la page Facture financière :</span><span class="sxs-lookup"><span data-stu-id="20b9b-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="20b9b-153">Afficher la taxe.</span><span class="sxs-lookup"><span data-stu-id="20b9b-153">View the sales tax.</span></span>
-   <span data-ttu-id="20b9b-154">Afficher le total de la facture.</span><span class="sxs-lookup"><span data-stu-id="20b9b-154">View the invoice total.</span></span>
-   <span data-ttu-id="20b9b-155">Afficher le flux de trésorerie.</span><span class="sxs-lookup"><span data-stu-id="20b9b-155">View the cash flow.</span></span>
-   <span data-ttu-id="20b9b-156">Afficher les répartitions comptables pour la facture financière entière.</span><span class="sxs-lookup"><span data-stu-id="20b9b-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="20b9b-157">Afficher le journal de comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="20b9b-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="20b9b-158">Journaux de comptabilité auxiliaires pour les factures financières</span><span class="sxs-lookup"><span data-stu-id="20b9b-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="20b9b-159">Avant de valider une facture financière, vous pouvez afficher l’écriture de compte complète de la facture, qui inclut des débits et des crédits, pour vérifier que la facture est imputée dans les comptes corrects.</span><span class="sxs-lookup"><span data-stu-id="20b9b-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="20b9b-160">Cette vue de l’écriture de compte complète est appelée écriture de journal de comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="20b9b-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="20b9b-161">Si l’écriture de journal de comptabilité auxiliaire est incorrecte lorsque vous en affichez un aperçu avant de journaliser la facture financière, vous ne pouvez pas la modifier.</span><span class="sxs-lookup"><span data-stu-id="20b9b-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="20b9b-162">Vous devez plutôt modifier les répartitions comptables ou le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="20b9b-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="20b9b-163">Les répartitions comptables permettent de définir un côté de l’écriture de compte, de débit ou de crédit.</span><span class="sxs-lookup"><span data-stu-id="20b9b-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="20b9b-164">L’écriture de compte de journal de comptabilité auxiliaire de contrepartie est créée à l’aide des profils de validation, par exemple le compte client ou la taxe.</span><span class="sxs-lookup"><span data-stu-id="20b9b-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]