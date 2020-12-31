---
title: Types de validations de baux
description: Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ceb4fbeb4dbf2f535e05a9d46c84169435d2803b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443381"
---
# <a name="lease-posting-types"></a><span data-ttu-id="6b4fc-103">Types de validations de baux</span><span class="sxs-lookup"><span data-stu-id="6b4fc-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b4fc-104">Cette rubrique décrit les types de validation utilisés pour les transactions de crédit-bail.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="6b4fc-105">Actif loué</span><span class="sxs-lookup"><span data-stu-id="6b4fc-105">Lease asset</span></span>

<span data-ttu-id="6b4fc-106">Le compte est associé au droit d’utilisation de l’actif (ROU).</span><span class="sxs-lookup"><span data-stu-id="6b4fc-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="6b4fc-107">Ce compte est débité lors de la comptabilisation initiale d’un contrat de location selon les nouvelles normes comptables des contrats de location, les normes comptables Codification Topic 842 (ASC 842) et l’International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="6b4fc-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="6b4fc-108">Pour un bail modifié, ce compte peut être soit débité, soit crédité, selon que la modification augmente ou diminue la dette locative.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="6b4fc-109">**Exemples d’écritures de journal :** Reconnaissance initiale</span><span class="sxs-lookup"><span data-stu-id="6b4fc-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="6b4fc-110">**Débit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="6b4fc-111">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="6b4fc-112">Passif locatif</span><span class="sxs-lookup"><span data-stu-id="6b4fc-112">Lease liability</span></span>

<span data-ttu-id="6b4fc-113">Le compte est associé au passif locatif qui survient lorsque les paiements sont actualisés selon les nouvelles normes IFRS 16 et ASC 842.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="6b4fc-114">Ce compte est crédité lorsqu’un contrat de location est initialement reconnu selon les nouvelles normes.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="6b4fc-115">Il est débité pour les paiements de location et crédité pour les intérêts courus.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="6b4fc-116">**Exemples d’écritures de journal :** Reconnaissance initiale</span><span class="sxs-lookup"><span data-stu-id="6b4fc-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="6b4fc-117">**Débit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="6b4fc-118">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="6b4fc-119">**Exemples d’écritures de journal :** Intérêts courus</span><span class="sxs-lookup"><span data-stu-id="6b4fc-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="6b4fc-120">**Débit :** Dépenses d’intérêts XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="6b4fc-121">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="6b4fc-122">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="6b4fc-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="6b4fc-123">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-124">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="6b4fc-125">Passif locatif à court terme</span><span class="sxs-lookup"><span data-stu-id="6b4fc-125">Short-term lease liability</span></span>

<span data-ttu-id="6b4fc-126">Le compte est associé au passif de location à court terme lorsque l’écriture de journal de reclassement de passif locatif à court terme est comptabilisée.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="6b4fc-127">Ce compte est crédité du passif à court terme à partir du tableau d’amortissement du dernier jour du mois.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="6b4fc-128">Cependant, le même montant est débité le premier jour du mois suivant.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="6b4fc-129">**Exemples d’écritures de journal :** Reclassement du passif locatif à court terme</span><span class="sxs-lookup"><span data-stu-id="6b4fc-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="6b4fc-130">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-131">**Crédit :** Passif locatif à court terme XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-132">**Débit :** Passif locatif à court terme XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-133">**Crédit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="6b4fc-134">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="6b4fc-134">Depreciation expense</span></span>

<span data-ttu-id="6b4fc-135">Le compte est associé à la charge liée à l’amortissement du droit d’utilisation de l’actif selon IFRS 16, ASC 842 et aux contrats de location-financement selon IAS 17 et ASC 840.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="6b4fc-136">Ce compte est débité lorsqu’un droit d’utilisation de l’actif est amorti chaque mois.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="6b4fc-137">**Exemples d’écritures de journal :** régularisation d’amortissement</span><span class="sxs-lookup"><span data-stu-id="6b4fc-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="6b4fc-138">**Débit :** Dépenses d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="6b4fc-139">**Crédit :** Amortissement cumulé XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="6b4fc-140">Profit/perte suite à la modification du bail</span><span class="sxs-lookup"><span data-stu-id="6b4fc-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="6b4fc-141">Le compte est associé à tous les gains ou pertes résultant de modifications du bail.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="6b4fc-142">Un gain peut survenir lors d’une modification de contrat de location si la modification diminue le passif de location d’un montant qui dépasse la valeur comptable du droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="6b4fc-143">Par exemple, un contrat de location a une valeur comptable actuelle du passif de location de 150 000 $ et une valeur comptable du droit d’utilisation de l’actif de 100 000 $.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="6b4fc-144">Le bail est modifié, et cette modification produit une nouvelle valeur actuelle des futurs paiements minimaux de location (PVFMLP) de 40 000 $.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="6b4fc-145">Par conséquent, le passif locatif sera débité de 110 000 $ (150 000 $ – 40 000 $).</span><span class="sxs-lookup"><span data-stu-id="6b4fc-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="6b4fc-146">Étant donné que le droit d’utilisation de l’actif est uniquement de 100 000 $, la diminution de 110 000 $ diminuera l’actif au-delà de 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="6b4fc-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="6b4fc-147">Par conséquent, les directives comptables indiquent que le solde doit être comptabilisé dans un compte de gain.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="6b4fc-148">Dans ce cas, l’écriture de journal finale sera un débit du passif locatif pour 110 000 $, un crédit sur l’actif de location pour 100 000 $ et un crédit sur le compte de gain pour 10 000$.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="6b4fc-149">**Exemples d’écritures de journal :** Modification de location</span><span class="sxs-lookup"><span data-stu-id="6b4fc-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="6b4fc-150">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-151">**Crédit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="6b4fc-152">**Crédit :** Gain XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="6b4fc-153">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="6b4fc-153">Accumulated depreciation</span></span>

<span data-ttu-id="6b4fc-154">Le compte est associé au compte de contre-actif du droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="6b4fc-155">Ce compte est crédité lorsqu’une dépense d’amortissement est validée.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="6b4fc-156">**Exemples d’écritures de journal :** régularisation d’amortissement</span><span class="sxs-lookup"><span data-stu-id="6b4fc-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="6b4fc-157">**Débit :** Dépenses d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="6b4fc-158">**Crédit :** Dépense d’amortissement XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="retained-earnings"></a><span data-ttu-id="6b4fc-159">Bénéfices non répartis</span><span class="sxs-lookup"><span data-stu-id="6b4fc-159">Retained earnings</span></span>

<span data-ttu-id="6b4fc-160">Compte associé à la facture aux bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-160">The account is associated with retained earnings.</span></span> <span data-ttu-id="6b4fc-161">Ce compte peut être débité ou crédité dans une écriture de journal d’ajustement de transition en utilisant la méthode rétrospective complète ou la méthode de l’option de rattrapage cumulatif A.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-161">This account might be either debited or credited in a transition adjustment journal entry by using the full retrospective method or the cumulative catch-up option A method.</span></span> <span data-ttu-id="6b4fc-162">La différence entre le droit d’utilisation de l’actif initial et le passif locatif est comptabilisée en bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-162">The difference between the initial ROU asset and lease liability is booked to retained earnings.</span></span> <span data-ttu-id="6b4fc-163">Dans de rares cas, les bénéfices non répartis peuvent également être affectés lors de la modification du contrat de location, si la classification d’un contrat de location est modifiée de financement en exploitation pour déprécier le droit d’utilisation de l’actif à la hausse ou à la baisse de sorte qu’il équivaut au passif de location.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-163">In rare cases, the retained earnings might also be affected during lease modification, if the classification of a lease is changed from finance to operating to write the ROU asset up or down so that it equals the lease liability.</span></span>

<span data-ttu-id="6b4fc-164">**Exemples d’écritures de journal :** Ajustement de transition (méthode rétrospective complète ou de rattrapage cumulatif option A)</span><span class="sxs-lookup"><span data-stu-id="6b4fc-164">**Example journal entries:** Transition adjustment (full retrospective or cumulative catch-up option A method)</span></span><br>
<span data-ttu-id="6b4fc-165">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-165">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-166">**Crédit :** Actif de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-166">**Credit:** Lease asset XXX</span></span><br>
<span data-ttu-id="6b4fc-167">**Crédit :** Bénéfices non répartis XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-167">**Credit:** Retained earnings XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="6b4fc-168">Paiement variable</span><span class="sxs-lookup"><span data-stu-id="6b4fc-168">Variable payment</span></span>

<span data-ttu-id="6b4fc-169">Le compte est associé à des loyers variables qui sont produits par une réévaluation d’indice selon les contrats de location ASC 842, ASC 840 et IAS 17.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-169">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="6b4fc-170">Dans l’échéancier des paiements de location, les paiements variables sont inclus dans la colonne **Paiement variable**.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-170">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="6b4fc-171">Ce compte est débité lorsqu’une facture est créée sur une ligne d’échéancier de paiement qui contient un paiement variable.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-171">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="6b4fc-172">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="6b4fc-172">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="6b4fc-173">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-173">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-174">**Débit :** Paiement variable XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-174">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="6b4fc-175">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-175">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="6b4fc-176">Actif du loyer reporté (passif)</span><span class="sxs-lookup"><span data-stu-id="6b4fc-176">Deferred rent asset (liability)</span></span>

<span data-ttu-id="6b4fc-177">Le compte est associé à l’actif ou au passif locatif différé qui est produit par un contrat de location-traitement différé.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-177">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="6b4fc-178">Ce compte est débité lorsqu’une facture est imputée à un bail de traitement de loyer différé, si le montant du paiement du loyer est supérieur à la charge de loyer linéaire de la période.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-178">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="6b4fc-179">Il est crédité si le paiement du loyer est inférieur au loyer linéaire de la période.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-179">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="6b4fc-180">**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)</span><span class="sxs-lookup"><span data-stu-id="6b4fc-180">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="6b4fc-181">**Débit :** Frais de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-181">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="6b4fc-182">**Crédit :** Actif du loyer reporté XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-182">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="6b4fc-183">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-183">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="6b4fc-184">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="6b4fc-184">Lease expense</span></span>

<span data-ttu-id="6b4fc-185">Le compte est associé à la charge de location si le contrat de location est classé comme contrat de location avec traitement de loyer différé.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-185">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="6b4fc-186">Ce compte est débité lorsqu’une facture est imputée à un bail de traitement à loyer différé.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-186">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="6b4fc-187">**Exemples d’écritures de journal :** Paiement de location (bail de traitement de loyer différé)</span><span class="sxs-lookup"><span data-stu-id="6b4fc-187">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="6b4fc-188">**Débit :** Frais de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-188">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="6b4fc-189">**Crédit :** Actif du loyer reporté XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-189">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="6b4fc-190">**Crédit :** Fournisseur payable/paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-190">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="6b4fc-191">Dépense de dépréciation</span><span class="sxs-lookup"><span data-stu-id="6b4fc-191">Impairment expense</span></span>

<span data-ttu-id="6b4fc-192">Le compte est comptabilisé lorsqu’un bail est déprécié.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-192">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="6b4fc-193">Ce compte est débité, tandis que le compte de droit d’utilisation de l’actif est directement crédité.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-193">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="6b4fc-194">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="6b4fc-194">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="6b4fc-195">**Débit :** Dépense de dépréciation XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-195">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="6b4fc-196">**Crédit :** Droit d’utilisation de l’actif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-196">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="6b4fc-197">Paiement de loyer</span><span class="sxs-lookup"><span data-stu-id="6b4fc-197">Lease payment</span></span>

<span data-ttu-id="6b4fc-198">Le compte est validé si le paramètre **Payer au fournisseur** est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-198">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="6b4fc-199">Ce compte est crédité à la place du montant payable au fournisseur si le paramètre est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-199">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="6b4fc-200">**Exemples d’écritures de journal :** Paiement de location</span><span class="sxs-lookup"><span data-stu-id="6b4fc-200">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="6b4fc-201">**Débit :** Passif locatif XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-201">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="6b4fc-202">**Crédit :** Paiement de location XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-202">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="6b4fc-203">Écritures de type de dépense</span><span class="sxs-lookup"><span data-stu-id="6b4fc-203">Expense type postings</span></span>

<span data-ttu-id="6b4fc-204">Le compte sélectionné pour chaque type de dépense est débité lorsqu’un paiement pour ce type de dépense est généré.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-204">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="6b4fc-205">Par exemple, le compte spécifié pour le type de dépense **Assurance** est débité chaque fois qu’une facture ou une écriture de journal de paiement est créée à partir du barème des coûts exécutoire pour les dépenses d’assurance.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-205">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="6b4fc-206">**Exemples d’écritures de journal :** Paiement de l’assurance</span><span class="sxs-lookup"><span data-stu-id="6b4fc-206">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="6b4fc-207">**Débit :** Compte de type de dépenses d’assurance XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-207">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="6b4fc-208">**Crédit :** Compte de compensation XXX</span><span class="sxs-lookup"><span data-stu-id="6b4fc-208">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="6b4fc-209">Le compte de contrepartie est sélectionné au niveau du contrat de location sur les lignes de l’échéancier de paiement des coûts exécutoires.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-209">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="6b4fc-210">Ce compte de contrepartie peut être associé au fournisseur ou à un compte général.</span><span class="sxs-lookup"><span data-stu-id="6b4fc-210">This offset account can associated with the vendor, or with a ledger account.</span></span>
