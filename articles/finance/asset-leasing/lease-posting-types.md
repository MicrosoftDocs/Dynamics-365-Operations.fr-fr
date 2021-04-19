---
title: Types de validations de baux
description: Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841139"
---
# <a name="lease-posting-types"></a><span data-ttu-id="d540c-103">Types de validations de baux</span><span class="sxs-lookup"><span data-stu-id="d540c-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d540c-104">Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.</span><span class="sxs-lookup"><span data-stu-id="d540c-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="d540c-105">Actif loué</span><span class="sxs-lookup"><span data-stu-id="d540c-105">Lease asset</span></span>

<span data-ttu-id="d540c-106">Le compte est associé au droit d’utilisation de l’actif (ROU).</span><span class="sxs-lookup"><span data-stu-id="d540c-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="d540c-107">Ce compte est débité lors de la comptabilisation initiale d’un contrat de location selon les nouvelles normes comptables des contrats de location, les normes comptables Codification Topic 842 (ASC 842) et l’International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="d540c-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="d540c-108">Pour un bail modifié, ce compte peut être soit débité, soit crédité, selon que la modification augmente ou diminue la dette locative.</span><span class="sxs-lookup"><span data-stu-id="d540c-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="d540c-109">**Exemples d’écritures de journal :** Reconnaissance initiale</span><span class="sxs-lookup"><span data-stu-id="d540c-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="d540c-110">**Débit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="d540c-111">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="d540c-112">Passif locatif</span><span class="sxs-lookup"><span data-stu-id="d540c-112">Lease liability</span></span>

<span data-ttu-id="d540c-113">Le compte est associé au passif locatif qui survient lorsque les paiements sont actualisés selon les nouvelles normes IFRS 16 et ASC 842.</span><span class="sxs-lookup"><span data-stu-id="d540c-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="d540c-114">Ce compte est crédité lorsqu’un contrat de location est initialement reconnu selon les nouvelles normes.</span><span class="sxs-lookup"><span data-stu-id="d540c-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="d540c-115">Il est débité pour les paiements de location et crédité pour les intérêts courus.</span><span class="sxs-lookup"><span data-stu-id="d540c-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="d540c-116">**Exemples d’écritures de journal :** Reconnaissance initiale</span><span class="sxs-lookup"><span data-stu-id="d540c-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="d540c-117">**Débit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="d540c-118">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="d540c-119">**Exemples d’écritures de journal :** Intérêts courus</span><span class="sxs-lookup"><span data-stu-id="d540c-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="d540c-120">**Débit :** Dépenses d’intérêts XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="d540c-121">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="d540c-122">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="d540c-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="d540c-123">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="d540c-124">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="d540c-125">Passif locatif à court terme</span><span class="sxs-lookup"><span data-stu-id="d540c-125">Short-term lease liability</span></span>

<span data-ttu-id="d540c-126">Le compte est associé au passif de location à court terme lorsque l’écriture de journal de reclassement de passif locatif à court terme est comptabilisée.</span><span class="sxs-lookup"><span data-stu-id="d540c-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="d540c-127">Ce compte est crédité du passif à court terme à partir du tableau d’amortissement du dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="d540c-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="d540c-128">Cependant, le même montant est débité le premier jour du mois suivant.</span><span class="sxs-lookup"><span data-stu-id="d540c-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="d540c-129">**Exemples d’écritures de journal :** Reclassement du passif locatif à court terme</span><span class="sxs-lookup"><span data-stu-id="d540c-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="d540c-130">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="d540c-131">**Crédit :** Passif locatif à court terme XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="d540c-132">**Débit :** Passif locatif à court terme XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="d540c-133">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="d540c-134">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="d540c-134">Depreciation expense</span></span>

<span data-ttu-id="d540c-135">Le compte est associé à la charge liée à l’amortissement du droit d’utilisation de l’actif selon IFRS 16, ASC 842 et aux contrats de location-financement selon IAS 17 et ASC 840.</span><span class="sxs-lookup"><span data-stu-id="d540c-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="d540c-136">Ce compte est débité lorsqu’un droit d’utilisation de l’actif est amorti chaque mois.</span><span class="sxs-lookup"><span data-stu-id="d540c-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="d540c-137">**Exemples d’écritures de journal :** régularisation d’amortissement</span><span class="sxs-lookup"><span data-stu-id="d540c-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="d540c-138">**Débit :** Dépenses d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="d540c-139">**Crédit :** Amortissement cumulé XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="d540c-140">Profit/perte suite à la modification du bail</span><span class="sxs-lookup"><span data-stu-id="d540c-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="d540c-141">Le compte est associé à tous les gains ou pertes résultant de modifications du bail.</span><span class="sxs-lookup"><span data-stu-id="d540c-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="d540c-142">Un gain peut survenir lors d’une modification de contrat de location si la modification diminue le passif de location d’un montant qui dépasse la valeur comptable du droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="d540c-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="d540c-143">Par exemple, un contrat de location a une valeur comptable actuelle du passif de location de 150 000 $ et une valeur comptable du droit d’utilisation de l’actif de 100 000 $.</span><span class="sxs-lookup"><span data-stu-id="d540c-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="d540c-144">Le bail est modifié, et cette modification produit une nouvelle valeur actuelle des futurs paiements minimaux de location (PVFMLP) de 40 000 $.</span><span class="sxs-lookup"><span data-stu-id="d540c-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="d540c-145">Par conséquent, le passif locatif sera débité de 110 000 $ (150 000 $ – 40 000 $).</span><span class="sxs-lookup"><span data-stu-id="d540c-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="d540c-146">Étant donné que le droit d’utilisation de l’actif est uniquement de 100 000 $, la diminution de 110 000 $ diminuera l’actif au-delà de 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="d540c-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="d540c-147">Par conséquent, les directives comptables indiquent que le solde doit être comptabilisé dans un compte de gain.</span><span class="sxs-lookup"><span data-stu-id="d540c-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="d540c-148">Dans ce cas, l’écriture de journal finale sera un débit du passif locatif pour 110 000 $, un crédit sur l’actif de location pour 100 000 $ et un crédit sur le compte de gain pour 10 000$.</span><span class="sxs-lookup"><span data-stu-id="d540c-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="d540c-149">**Exemples d’écritures de journal :** Modification de location</span><span class="sxs-lookup"><span data-stu-id="d540c-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="d540c-150">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="d540c-151">**Crédit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="d540c-152">**Crédit :** Gain XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="d540c-153">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="d540c-153">Accumulated depreciation</span></span>

<span data-ttu-id="d540c-154">Le compte est associé au compte de contre-actif du droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="d540c-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="d540c-155">Ce compte est crédité lorsqu’une dépense d’amortissement est validée.</span><span class="sxs-lookup"><span data-stu-id="d540c-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="d540c-156">**Exemples d’écritures de journal :** régularisation d’amortissement</span><span class="sxs-lookup"><span data-stu-id="d540c-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="d540c-157">**Débit :** Dépenses d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="d540c-158">**Crédit :** Dépense d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="d540c-159">Paiement variable</span><span class="sxs-lookup"><span data-stu-id="d540c-159">Variable payment</span></span>

<span data-ttu-id="d540c-160">Le compte est associé à des loyers variables qui sont produits par une réévaluation d’indice selon les contrats de location ASC 842, ASC 840 et IAS 17.</span><span class="sxs-lookup"><span data-stu-id="d540c-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="d540c-161">Dans l’échéancier des paiements de location, les paiements variables sont inclus dans la colonne **Paiement variable**.</span><span class="sxs-lookup"><span data-stu-id="d540c-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="d540c-162">Ce compte est débité lorsqu’une facture est créée sur une ligne d’échéancier de paiement qui contient un paiement variable.</span><span class="sxs-lookup"><span data-stu-id="d540c-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="d540c-163">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="d540c-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="d540c-164">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="d540c-165">**Débit :** Paiement variable XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="d540c-166">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="d540c-167">Actif du loyer reporté (passif)</span><span class="sxs-lookup"><span data-stu-id="d540c-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="d540c-168">Le compte est associé à l’actif ou au passif locatif différé qui est produit par un contrat de location-traitement différé.</span><span class="sxs-lookup"><span data-stu-id="d540c-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="d540c-169">Ce compte est débité lorsqu’une facture est imputée à un bail de traitement de loyer différé, si le montant du paiement du loyer est supérieur à la charge de loyer linéaire de la période.</span><span class="sxs-lookup"><span data-stu-id="d540c-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="d540c-170">Il est crédité si le paiement du loyer est inférieur au loyer linéaire de la période.</span><span class="sxs-lookup"><span data-stu-id="d540c-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="d540c-171">**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)</span><span class="sxs-lookup"><span data-stu-id="d540c-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="d540c-172">**Débit :** Frais de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="d540c-173">**Crédit :** Actif du loyer reporté XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="d540c-174">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="d540c-175">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="d540c-175">Lease expense</span></span>

<span data-ttu-id="d540c-176">Le compte est associé à la charge de location si le contrat de location est classé comme contrat de location avec traitement de loyer différé.</span><span class="sxs-lookup"><span data-stu-id="d540c-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="d540c-177">Ce compte est débité lorsqu’une facture est imputée à un bail de traitement à loyer différé.</span><span class="sxs-lookup"><span data-stu-id="d540c-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="d540c-178">**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)</span><span class="sxs-lookup"><span data-stu-id="d540c-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="d540c-179">**Débit :** Frais de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="d540c-180">**Crédit :** Actif du loyer reporté XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="d540c-181">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="d540c-182">Dépense de dépréciation</span><span class="sxs-lookup"><span data-stu-id="d540c-182">Impairment expense</span></span>

<span data-ttu-id="d540c-183">Le compte est comptabilisé lorsqu’un bail est déprécié.</span><span class="sxs-lookup"><span data-stu-id="d540c-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="d540c-184">Ce compte est débité, tandis que le compte de droit d’utilisation de l’actif est directement crédité.</span><span class="sxs-lookup"><span data-stu-id="d540c-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="d540c-185">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="d540c-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="d540c-186">**Débit :** Dépense de dépréciation XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="d540c-187">**Crédit :** Droit d’utilisation de l’actif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="d540c-188">Paiement de loyer</span><span class="sxs-lookup"><span data-stu-id="d540c-188">Lease payment</span></span>

<span data-ttu-id="d540c-189">Le compte est validé si le paramètre **Payer au fournisseur** est désactivé.</span><span class="sxs-lookup"><span data-stu-id="d540c-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="d540c-190">Ce compte est crédité à la place du montant payable au fournisseur si le paramètre est désactivé.</span><span class="sxs-lookup"><span data-stu-id="d540c-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="d540c-191">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="d540c-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="d540c-192">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="d540c-193">**Crédit :** Paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="d540c-194">Écritures de type de dépense</span><span class="sxs-lookup"><span data-stu-id="d540c-194">Expense type postings</span></span>

<span data-ttu-id="d540c-195">Le compte sélectionné pour chaque type de dépense est débité lorsqu’un paiement pour ce type de dépense est généré.</span><span class="sxs-lookup"><span data-stu-id="d540c-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="d540c-196">Par exemple, le compte spécifié pour le type de dépense **Assurance** est débité chaque fois qu’une facture ou une écriture de journal de paiement est créée à partir du barème des coûts exécutoire pour les dépenses d’assurance.</span><span class="sxs-lookup"><span data-stu-id="d540c-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="d540c-197">**Exemples d’écritures de journal :** Paiement de l’assurance</span><span class="sxs-lookup"><span data-stu-id="d540c-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="d540c-198">**Débit :** Compte de type de dépenses d’assurance XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="d540c-199">**Crédit :** Compte de compensation XXX</span><span class="sxs-lookup"><span data-stu-id="d540c-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="d540c-200">Le compte de contrepartie est sélectionné au niveau du contrat de location sur les lignes de l’échéancier de paiement des coûts exécutoires.</span><span class="sxs-lookup"><span data-stu-id="d540c-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="d540c-201">Ce compte de contrepartie peut être associé au fournisseur ou à un compte général.</span><span class="sxs-lookup"><span data-stu-id="d540c-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
