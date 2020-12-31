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
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 51d43c8e6d16201e1f8c392c13ead20287782dcc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443025"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="1460c-103">Calcul de taxe sur les lignes générales du journal</span><span class="sxs-lookup"><span data-stu-id="1460c-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="1460c-104">Cette rubrique explique comment les taxes sont calculées pour différents types de comptes (fournisseur, client, comptabilité et projet) sur les lignes générales du journal.</span><span class="sxs-lookup"><span data-stu-id="1460c-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="1460c-105">Ce processus peut être divisé en trois étapes :</span><span class="sxs-lookup"><span data-stu-id="1460c-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="1460c-106">Déterminez la direction de la taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="1460c-107">Déterminez le montant de taxe qui sera enregistré dans une table temporaire de taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="1460c-108">Déterminez le montant de la taxe et le compte sur le N° document.</span><span class="sxs-lookup"><span data-stu-id="1460c-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="1460c-109">Déterminer la direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-109">Determine the sales tax direction</span></span>

<span data-ttu-id="1460c-110">La façon dont la direction de la taxe est déterminée dépend du type de compte dans le N° document.</span><span class="sxs-lookup"><span data-stu-id="1460c-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="1460c-111">La direction de la taxe est déterminée par la combinaison du type de compte et du code taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="1460c-112">Les sections suivantes décrivent les possibilités en détail.</span><span class="sxs-lookup"><span data-stu-id="1460c-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="1460c-113">Le type de compte est Projet</span><span class="sxs-lookup"><span data-stu-id="1460c-113">Account type is Project</span></span>

<span data-ttu-id="1460c-114">Si un N° document a une ligne de journal où le type de compte est **Projet**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1460c-115">L’illustration suivante présente la règle.</span><span class="sxs-lookup"><span data-stu-id="1460c-115">The following illustration shows the rule.</span></span> <span data-ttu-id="1460c-116">Le points suivants affichent les directions possibles de taxe pour les comptes de projet.</span><span class="sxs-lookup"><span data-stu-id="1460c-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="1460c-117">•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1460c-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1460c-118">•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="1460c-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1460c-119">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-120">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-121">Sinon, la direction de la taxe est taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="1460c-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1460c-122">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="1460c-122">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes de projet](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="1460c-124">Le type de compte est Fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-124">Account type is Vendor</span></span>

<span data-ttu-id="1460c-125">Si un N° document a une ligne de journal où le type de compte est **Fournisseur**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1460c-126">Le points suivants affichent les directions possibles de taxe pour les comptes de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="1460c-127">•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1460c-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1460c-128">•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="1460c-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1460c-129">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-130">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe de Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-131">Sinon, la direction de la taxe est taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="1460c-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1460c-132">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="1460c-132">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes de fournisseur](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="1460c-134">Le type de compte est Client</span><span class="sxs-lookup"><span data-stu-id="1460c-134">Account type is Customer</span></span>

<span data-ttu-id="1460c-135">Si un N° document a une ligne de journal où le type de compte est **Client**, toutes les lignes du journal dans le N° document appliquent la même direction de taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1460c-136">Le points suivants affichent les directions possibles de taxe pour les comptes de client.</span><span class="sxs-lookup"><span data-stu-id="1460c-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="1460c-137">•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="1460c-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1460c-138">•   Si le code taxe est une TVA intracommunautaire, la direction de la taxe est Taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="1460c-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1460c-139">•   Si le code taxe est une taxe au preneur, la direction de la taxe est Taxe déductible.</span><span class="sxs-lookup"><span data-stu-id="1460c-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1460c-140">Sinon, la direction de la taxe est taxe de comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-141">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="1460c-141">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes client](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="1460c-143">Le type de compte est Comptabilité</span><span class="sxs-lookup"><span data-stu-id="1460c-143">Account type is Ledger</span></span>

<span data-ttu-id="1460c-144">L’illustration suivante présente la règle qui s’applique lorsqu’un N° document n’a que des lignes de journal où le type de compte est **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="1460c-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="1460c-145">Le points suivants affichent les directions possibles de taxe pour les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="1460c-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="1460c-146">•   Si le code taxe est une taxe d’utilisation, la direction de la taxe est Taxe d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1460c-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1460c-147">•   Si le code taxe est exempt de taxe d’utilisation, la direction de la taxe est Achat détaxé.</span><span class="sxs-lookup"><span data-stu-id="1460c-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1460c-148">Sinon, si le montant du journal est positif (débit), la direction de la taxe est Taxe déductible ; si le montant du journal est négatif (crédit), la direction de la taxe est Taxe de comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1460c-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1460c-149">Le diagramme suivant illustre la règle sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="1460c-149">The following diagram illustrates the rule graphically.</span></span>

![Options de direction de la taxe pour les comptes généraux](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="1460c-151">Remplacer la direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-151">Override the sales tax direction</span></span>

<span data-ttu-id="1460c-152">Vous pouvez remplacer la direction de la taxe lorsque le N° document contient uniquement les lignes dont le type de compte est **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="1460c-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="1460c-153">Accédez à **Comptabilité \> Plan de comptes \> Comptes \> Comptes principaux**, puis sélectionnez le raccourci **Remplacements des entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="1460c-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="1460c-154">Déterminer le montant de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-154">Determine the sales tax amount</span></span>

<span data-ttu-id="1460c-155">Cette section décrit la manière dont le signe du montant de taxe est calculé.</span><span class="sxs-lookup"><span data-stu-id="1460c-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Page des transactions de la taxe](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="1460c-157">Le tableau suivant montre la règle générique pour déterminer le signe des montants de taxe dans la table temporaire de taxe.</span><span class="sxs-lookup"><span data-stu-id="1460c-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="1460c-158">Montant de ligne du journal</span><span class="sxs-lookup"><span data-stu-id="1460c-158">Journal line amount</span></span> | <span data-ttu-id="1460c-159">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-159">Sales tax direction</span></span>  | <span data-ttu-id="1460c-160">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="1460c-161">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-161">Positive</span></span>            | <span data-ttu-id="1460c-162">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-162">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-163">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-163">Positive</span></span>              |
| <span data-ttu-id="1460c-164">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-164">Positive</span></span>            | <span data-ttu-id="1460c-165">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-165">Sales Tax Payable</span></span>    | <span data-ttu-id="1460c-166">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-166">Negative</span></span>              |
| <span data-ttu-id="1460c-167">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-167">Negative</span></span>            | <span data-ttu-id="1460c-168">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-168">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-169">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-169">Negative</span></span>              |
| <span data-ttu-id="1460c-170">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-170">Negative</span></span>            | <span data-ttu-id="1460c-171">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-171">Sales Tax Payable</span></span>    | <span data-ttu-id="1460c-172">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-172">Positive</span></span>              |

<span data-ttu-id="1460c-173">Il existe une règle spéciale pour les N° document uniquement avec les lignes **Projet** ou **Comptabilité**, lorsqu’un groupe de taxe ou un groupe de taxe d’article est sélectionné sur la ligne **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="1460c-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="1460c-174">Cette règle est contrôlée par la fonction Activer le calcul de taxe indépendant pour les journaux généraux.</span><span class="sxs-lookup"><span data-stu-id="1460c-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="1460c-175">Lorsque cette fonction est désactivée, le montant de la taxe de la ligne **Comptabilité** utilise la direction de débit/crédit de la ligne **Projet**.</span><span class="sxs-lookup"><span data-stu-id="1460c-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="1460c-176">Lorsque cette fonction est activée, le montant de la taxe de la ligne **Comptabilité** utilise sa propre direction de débit/crédit.</span><span class="sxs-lookup"><span data-stu-id="1460c-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="1460c-177">Les tableaux suivants indiquent la règle pour chaque scénario.</span><span class="sxs-lookup"><span data-stu-id="1460c-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="1460c-178">**Règle lorsque la fonctionnalité est activée**</span><span class="sxs-lookup"><span data-stu-id="1460c-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="1460c-179">Montant de ligne du journal du projet</span><span class="sxs-lookup"><span data-stu-id="1460c-179">Journal line amount of project</span></span> | <span data-ttu-id="1460c-180">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-180">Sales tax direction</span></span>  | <span data-ttu-id="1460c-181">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="1460c-182">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-182">Positive</span></span>                       | <span data-ttu-id="1460c-183">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-183">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-184">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-184">Positive</span></span>              |
| <span data-ttu-id="1460c-185">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-185">Negative</span></span>                       | <span data-ttu-id="1460c-186">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-186">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-187">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-187">Negative</span></span>              |

<span data-ttu-id="1460c-188">**Règle lorsque la fonctionnalité est désactivée**</span><span class="sxs-lookup"><span data-stu-id="1460c-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="1460c-189">Montant de ligne du journal de comptabilité</span><span class="sxs-lookup"><span data-stu-id="1460c-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="1460c-190">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-190">Sales tax direction</span></span>  | <span data-ttu-id="1460c-191">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="1460c-192">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-192">Positive</span></span>                       | <span data-ttu-id="1460c-193">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-193">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-194">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-194">Positive</span></span>              |
| <span data-ttu-id="1460c-195">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-195">Negative</span></span>                       | <span data-ttu-id="1460c-196">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-196">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-197">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="1460c-198">Déterminer le montant de la taxe et le compte sur le N° document</span><span class="sxs-lookup"><span data-stu-id="1460c-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="1460c-199">Lorsque vous validez des taxes, le compte principal est extrait du profil de groupe de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="1460c-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="1460c-200">Lorsque les taxes sont déductibles, le système utilise le compte Taxe déductible spécifié dans le profil.</span><span class="sxs-lookup"><span data-stu-id="1460c-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="1460c-201">Lorsque les taxes sont payables, le système utilise le compte Taxe de comptabilité fournisseur spécifié dans le profil.</span><span class="sxs-lookup"><span data-stu-id="1460c-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="1460c-202">Le tableau suivant présente la règle générique.</span><span class="sxs-lookup"><span data-stu-id="1460c-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="1460c-203">Direction de la taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-203">Sales tax direction</span></span>  | <span data-ttu-id="1460c-204">Signe du montant de taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-204">Sales tax amount sign</span></span> | <span data-ttu-id="1460c-205">Compte de taxe</span><span class="sxs-lookup"><span data-stu-id="1460c-205">Sales tax account</span></span>      | <span data-ttu-id="1460c-206">Montant du n° document</span><span class="sxs-lookup"><span data-stu-id="1460c-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="1460c-207">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-207">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-208">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-208">Positive</span></span>              | <span data-ttu-id="1460c-209">Compte de taxe de comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-209">Tax Receivable Account</span></span> | <span data-ttu-id="1460c-210">Positif (débit)</span><span class="sxs-lookup"><span data-stu-id="1460c-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="1460c-211">Taxe de Comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-211">Sales Tax Receivable</span></span> | <span data-ttu-id="1460c-212">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-212">Negative</span></span>              | <span data-ttu-id="1460c-213">Compte de taxe de comptabilité client</span><span class="sxs-lookup"><span data-stu-id="1460c-213">Tax Receivable Account</span></span> | <span data-ttu-id="1460c-214">Négatif (crédit)</span><span class="sxs-lookup"><span data-stu-id="1460c-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="1460c-215">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-215">Sales Tax Payable</span></span>    | <span data-ttu-id="1460c-216">Positif</span><span class="sxs-lookup"><span data-stu-id="1460c-216">Positive</span></span>              | <span data-ttu-id="1460c-217">Compte de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-217">Tax Payable Account</span></span>    | <span data-ttu-id="1460c-218">Négatif (crédit)</span><span class="sxs-lookup"><span data-stu-id="1460c-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="1460c-219">Taxe de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-219">Sales Tax Payable</span></span>    | <span data-ttu-id="1460c-220">Négatif</span><span class="sxs-lookup"><span data-stu-id="1460c-220">Negative</span></span>              | <span data-ttu-id="1460c-221">Compte de Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="1460c-221">Tax Payable Account</span></span>    | <span data-ttu-id="1460c-222">Positif (débit)</span><span class="sxs-lookup"><span data-stu-id="1460c-222">Positive (Debit)</span></span>  |
