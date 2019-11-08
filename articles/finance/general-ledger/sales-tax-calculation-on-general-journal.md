---
title: Calcul de taxe sur les lignes générales du journal
description: Cette rubrique explique comment les taxes sont calculées pour différents types de comptes (fournisseur, client, comptabilité et projet) sur les lignes générales du journal.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: dd1df355d39065d6959915cc916987d3c58b15a6
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570192"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="6aeda-103">Calcul de taxe sur les lignes générales du journal</span><span class="sxs-lookup"><span data-stu-id="6aeda-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="6aeda-104">Cette rubrique explique comment les taxes sont calculées pour différents types de comptes (fournisseur, client, comptabilité et projet) sur les lignes générales du journal.</span><span class="sxs-lookup"><span data-stu-id="6aeda-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="6aeda-105">Ce processus peut être divisé en trois étapes :</span><span class="sxs-lookup"><span data-stu-id="6aeda-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="6aeda-106">Déterminez la direction de la taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="6aeda-107">Déterminez le montant de taxe qui sera enregistré dans une table temporaire de taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="6aeda-108">Déterminez le montant de la taxe et le compte sur le N° document.</span><span class="sxs-lookup"><span data-stu-id="6aeda-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="6aeda-109">Déterminer la direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-109">Determine the sales tax direction</span></span>

<span data-ttu-id="6aeda-110">La façon dont la direction de la taxe est déterminée dépend du type de compte dans le N° document.</span><span class="sxs-lookup"><span data-stu-id="6aeda-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="6aeda-111">La direction de la taxe est déterminée par la combinaison du type de compte et du code taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="6aeda-112">Les sections suivantes décrivent les possibilités en détail.</span><span class="sxs-lookup"><span data-stu-id="6aeda-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="6aeda-113">Le type de compte est Projet</span><span class="sxs-lookup"><span data-stu-id="6aeda-113">Account type is Project</span></span>

<span data-ttu-id="6aeda-114">Si un N° document a une ligne de journal où le type de compte est **Projet**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="6aeda-115">L'illustration suivante présente la règle.</span><span class="sxs-lookup"><span data-stu-id="6aeda-115">The following illustration shows the rule.</span></span> <span data-ttu-id="6aeda-116">Le points suivants affichent les directions possibles de taxe pour les comptes de projet.</span><span class="sxs-lookup"><span data-stu-id="6aeda-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="6aeda-117">•   Si le code taxe est une taxe d'utilisation, la direction de la taxe est Taxe d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="6aeda-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="6aeda-118">•   Si le code taxe est exempt de taxe d'utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="6aeda-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="6aeda-119">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-120">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-121">Sinon, la direction de la taxe est taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="6aeda-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="6aeda-122">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="6aeda-122">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes de projet](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="6aeda-124">Le type de compte est Fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-124">Account type is Vendor</span></span>

<span data-ttu-id="6aeda-125">Si un N° document a une ligne de journal où le type de compte est **Fournisseur**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="6aeda-126">Le points suivants affichent les directions possibles de taxe pour les comptes de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="6aeda-127">•   Si le code taxe est exempt de taxe d'utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="6aeda-127">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="6aeda-128">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="6aeda-128">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="6aeda-129">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="6aeda-129">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>


<span data-ttu-id="6aeda-130">Sinon, la direction de la taxe est taxe de comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-130">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-131">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="6aeda-131">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes de fournisseur](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="6aeda-133">Le type de compte est Client</span><span class="sxs-lookup"><span data-stu-id="6aeda-133">Account type is Customer</span></span>

<span data-ttu-id="6aeda-134">Si un N° document a une ligne de journal où le type de compte est **Client**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-134">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="6aeda-135">Le points suivants affichent les directions possibles de taxe pour les comptes de client.</span><span class="sxs-lookup"><span data-stu-id="6aeda-135">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="6aeda-136">•   Si le code taxe est une taxe d'utilisation, la direction de la taxe est Taxe d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="6aeda-136">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="6aeda-137">•   Si le code taxe est exempt de taxe d'utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="6aeda-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="6aeda-138">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-139">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-140">Sinon, la direction de la taxe est taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="6aeda-140">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="6aeda-141">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="6aeda-141">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes client](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="6aeda-143">Le type de compte est Comptabilité</span><span class="sxs-lookup"><span data-stu-id="6aeda-143">Account type is Ledger</span></span>

<span data-ttu-id="6aeda-144">L'illustration suivante présente la règle qui s'applique lorsqu'un N° document n'a que des lignes de journal où le type de compte est **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="6aeda-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="6aeda-145">Le points suivants affichent les directions possibles de taxe pour les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="6aeda-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="6aeda-146">•   Si le code taxe est une taxe d'utilisation, la direction de la taxe est Taxe d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="6aeda-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="6aeda-147">•   Si le code taxe est exempt de taxe d'utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="6aeda-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="6aeda-148">Sinon, si le montant du journal est positif (débit), la direction de la taxe est Taxe déductible ; si le montant du journal est négatif (crédit), la direction de la taxe est Taxe de comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6aeda-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="6aeda-149">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="6aeda-149">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes généraux](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="6aeda-151">Remplacer la direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-151">Override the sales tax direction</span></span>

<span data-ttu-id="6aeda-152">Vous pouvez remplacer la direction de la taxe lorsque le N° document contient uniquement les lignes dont le type de compte est **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="6aeda-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="6aeda-153">Accédez à **Comptabilité \> Plan de comptes \> Comptes \> Comptes principaux**, puis sélectionnez le raccourci **Remplacements des entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="6aeda-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="6aeda-154">Déterminer le montant de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-154">Determine the sales tax amount</span></span>

<span data-ttu-id="6aeda-155">Cette section décrit la manière dont le signe du montant de taxe est calculé.</span><span class="sxs-lookup"><span data-stu-id="6aeda-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Page des transactions de la taxe](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="6aeda-157">Le tableau suivant montre la règle générique pour déterminer le signe des montants de taxe dans la table temporaire de taxe.</span><span class="sxs-lookup"><span data-stu-id="6aeda-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="6aeda-158">Montant de ligne du journal</span><span class="sxs-lookup"><span data-stu-id="6aeda-158">Journal line amount</span></span> | <span data-ttu-id="6aeda-159">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-159">Sales tax direction</span></span>  | <span data-ttu-id="6aeda-160">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="6aeda-161">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-161">Positive</span></span>            | <span data-ttu-id="6aeda-162">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-162">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-163">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-163">Positive</span></span>              |
| <span data-ttu-id="6aeda-164">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-164">Positive</span></span>            | <span data-ttu-id="6aeda-165">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-165">Sales Tax Payable</span></span>    | <span data-ttu-id="6aeda-166">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-166">Negative</span></span>              |
| <span data-ttu-id="6aeda-167">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-167">Negative</span></span>            | <span data-ttu-id="6aeda-168">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-168">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-169">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-169">Negative</span></span>              |
| <span data-ttu-id="6aeda-170">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-170">Negative</span></span>            | <span data-ttu-id="6aeda-171">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-171">Sales Tax Payable</span></span>    | <span data-ttu-id="6aeda-172">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-172">Positive</span></span>              |

<span data-ttu-id="6aeda-173">Il existe une règle spéciale pour les N° document uniquement avec les lignes **Projet** ou **Comptabilité**, lorsqu'un groupe de taxe ou un groupe de taxe d'article est sélectionné sur la ligne **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="6aeda-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="6aeda-174">Cette règle est contrôlée par la fonction Activer le calcul de taxe indépendant pour les journaux généraux.</span><span class="sxs-lookup"><span data-stu-id="6aeda-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="6aeda-175">Lorsque cette fonction est désactivée, le montant de la taxe de la ligne **Comptabilité** utilise la direction de débit/crédit de la ligne **Projet**.</span><span class="sxs-lookup"><span data-stu-id="6aeda-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="6aeda-176">Lorsque cette fonction est activée, le montant de la taxe de la ligne **Comptabilité** utilise sa propre direction de débit/crédit.</span><span class="sxs-lookup"><span data-stu-id="6aeda-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="6aeda-177">Les tableaux suivants indiquent la règle pour chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="6aeda-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="6aeda-178">**Règle lorsque la fonctionnalité est activée**</span><span class="sxs-lookup"><span data-stu-id="6aeda-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="6aeda-179">Montant de ligne du journal du projet</span><span class="sxs-lookup"><span data-stu-id="6aeda-179">Journal line amount of project</span></span> | <span data-ttu-id="6aeda-180">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-180">Sales tax direction</span></span>  | <span data-ttu-id="6aeda-181">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="6aeda-182">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-182">Positive</span></span>                       | <span data-ttu-id="6aeda-183">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-183">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-184">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-184">Positive</span></span>              |
| <span data-ttu-id="6aeda-185">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-185">Negative</span></span>                       | <span data-ttu-id="6aeda-186">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-186">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-187">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-187">Negative</span></span>              |

<span data-ttu-id="6aeda-188">**Règle lorsque la fonctionnalité est désactivée**</span><span class="sxs-lookup"><span data-stu-id="6aeda-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="6aeda-189">Montant de ligne du journal de comptabilité</span><span class="sxs-lookup"><span data-stu-id="6aeda-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="6aeda-190">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-190">Sales tax direction</span></span>  | <span data-ttu-id="6aeda-191">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="6aeda-192">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-192">Positive</span></span>                       | <span data-ttu-id="6aeda-193">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-193">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-194">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-194">Positive</span></span>              |
| <span data-ttu-id="6aeda-195">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-195">Negative</span></span>                       | <span data-ttu-id="6aeda-196">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-196">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-197">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="6aeda-198">Déterminer le montant de la taxe et le compte sur le N° document</span><span class="sxs-lookup"><span data-stu-id="6aeda-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="6aeda-199">Lorsque vous validez des taxes, le compte principal est extrait du profil de groupe de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="6aeda-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="6aeda-200">Lorsque les taxes sont déductibles, le système utilise le compte Taxe déductible spécifié dans le profil.</span><span class="sxs-lookup"><span data-stu-id="6aeda-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="6aeda-201">Lorsque les taxes sont payables, le système utilise le compte Taxe de comptabilité fournisseur spécifié dans le profil.</span><span class="sxs-lookup"><span data-stu-id="6aeda-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="6aeda-202">Le tableau suivant présente la règle générique.</span><span class="sxs-lookup"><span data-stu-id="6aeda-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="6aeda-203">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-203">Sales tax direction</span></span>  | <span data-ttu-id="6aeda-204">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-204">Sales tax amount sign</span></span> | <span data-ttu-id="6aeda-205">Compte de taxe</span><span class="sxs-lookup"><span data-stu-id="6aeda-205">Sales tax account</span></span>      | <span data-ttu-id="6aeda-206">Montant du n° document</span><span class="sxs-lookup"><span data-stu-id="6aeda-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="6aeda-207">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-207">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-208">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-208">Positive</span></span>              | <span data-ttu-id="6aeda-209">Compte de taxe de comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-209">Tax Receivable Account</span></span> | <span data-ttu-id="6aeda-210">Positif (débit)</span><span class="sxs-lookup"><span data-stu-id="6aeda-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="6aeda-211">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-211">Sales Tax Receivable</span></span> | <span data-ttu-id="6aeda-212">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-212">Negative</span></span>              | <span data-ttu-id="6aeda-213">Compte de taxe de comptabilité client</span><span class="sxs-lookup"><span data-stu-id="6aeda-213">Tax Receivable Account</span></span> | <span data-ttu-id="6aeda-214">Négatif (crédit)</span><span class="sxs-lookup"><span data-stu-id="6aeda-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="6aeda-215">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-215">Sales Tax Payable</span></span>    | <span data-ttu-id="6aeda-216">Positif</span><span class="sxs-lookup"><span data-stu-id="6aeda-216">Positive</span></span>              | <span data-ttu-id="6aeda-217">Compte de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-217">Tax Payable Account</span></span>    | <span data-ttu-id="6aeda-218">Négatif (crédit)</span><span class="sxs-lookup"><span data-stu-id="6aeda-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="6aeda-219">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-219">Sales Tax Payable</span></span>    | <span data-ttu-id="6aeda-220">Négatif</span><span class="sxs-lookup"><span data-stu-id="6aeda-220">Negative</span></span>              | <span data-ttu-id="6aeda-221">Compte de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="6aeda-221">Tax Payable Account</span></span>    | <span data-ttu-id="6aeda-222">Positif (débit)</span><span class="sxs-lookup"><span data-stu-id="6aeda-222">Positive (Debit)</span></span>  |
