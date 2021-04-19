---
title: Configuration de la validation de la gestion des remises
description: Cette rubrique décrit le paramétrage des profils de validation. Les profils de validation sont utilisés pour déterminer la validation des écritures pour les lignes de calcul de la gestion des remises.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: e79feb567a48d08a9063bf20cface3c5c7fe8ecc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831744"
---
# <a name="rebate-management-posting-setup"></a><span data-ttu-id="86b2c-104">Configuration de la validation de la gestion des remises</span><span class="sxs-lookup"><span data-stu-id="86b2c-104">Rebate management posting setup</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="86b2c-105">Les profils de validation de la gestion des remises sont utilisés pour déterminer la validation des écritures pour les lignes de calcul de la gestion des remises.</span><span class="sxs-lookup"><span data-stu-id="86b2c-105">Rebate management posting profiles are used to determine posting entries for Rebate management calculation lines.</span></span> <span data-ttu-id="86b2c-106">Lorsqu’un profil de validation est sélectionné dans l’en-tête de l’accord, il s’applique à toutes les lignes de l’accord.</span><span class="sxs-lookup"><span data-stu-id="86b2c-106">When a posting profile is selected on the deal header, it applies to all deal lines.</span></span>

<span data-ttu-id="86b2c-107">Cette fonctionnalité fonctionne dans toutes les entreprises (entités juridiques).</span><span class="sxs-lookup"><span data-stu-id="86b2c-107">This feature works across companies (legal entities).</span></span> <span data-ttu-id="86b2c-108">Vous pouvez spécifier l’entreprise pour laquelle les provisions seront constituées et par laquelle les réclamations seront payées.</span><span class="sxs-lookup"><span data-stu-id="86b2c-108">You can specify the company that provisions will be accrued to and that claims will be paid by.</span></span> <span data-ttu-id="86b2c-109">Vous pouvez également définir différents comptes de débit de provision et comptes de crédit d’annulation par société comptable source.</span><span class="sxs-lookup"><span data-stu-id="86b2c-109">You can also set different provision debit accounts and write-off credit accounts per source posting company.</span></span>

<span data-ttu-id="86b2c-110">Pour configurer les profils de validation de la gestion des remises pour les clients et les fournisseurs, accédez à **Gestion des remises \> Configuration de la validation de la gestion des remises \> Profils de validation de la gestion des remises**.</span><span class="sxs-lookup"><span data-stu-id="86b2c-110">To set up Rebate management posting profiles for customers and vendors, go to **Rebate management \> Rebate management posting setup \> Rebate management posting profiles**.</span></span> <span data-ttu-id="86b2c-111">La page **Profils de validation de la gestion des remises** comprend un volet de liste qui affiche tous vos profils existants.</span><span class="sxs-lookup"><span data-stu-id="86b2c-111">The **Rebate management posting profiles** page includes a list pane that shows all your existing profiles.</span></span> <span data-ttu-id="86b2c-112">Vous pouvez utiliser les boutons du volet Actions pour ajouter des profils à la liste ou en supprimer.</span><span class="sxs-lookup"><span data-stu-id="86b2c-112">You can use the buttons on the Action Pane to add profiles to the list or remove them.</span></span>

<span data-ttu-id="86b2c-113">Les sections restantes de cette rubrique décrivent comment utiliser les champs disponibles lorsque vous créez ou modifiez un profil.</span><span class="sxs-lookup"><span data-stu-id="86b2c-113">The remaining sections of this topic describe how to use the available fields when you create or edit a profile.</span></span>

## <a name="posting-profile-header"></a><span data-ttu-id="86b2c-114">En-tête du profil de validation</span><span class="sxs-lookup"><span data-stu-id="86b2c-114">Posting profile header</span></span>

<span data-ttu-id="86b2c-115">Le tableau suivant décrit les paramètres disponibles dans la section d’en-tête de chaque profil de validation de la gestion des remises.</span><span class="sxs-lookup"><span data-stu-id="86b2c-115">The following table describes the settings that are available in the header section of each Rebate management posting profile.</span></span>

| <span data-ttu-id="86b2c-116">Champ</span><span class="sxs-lookup"><span data-stu-id="86b2c-116">Field</span></span> | <span data-ttu-id="86b2c-117">Description</span><span class="sxs-lookup"><span data-stu-id="86b2c-117">Description</span></span> |
|---|---|
| <span data-ttu-id="86b2c-118">Profil de validation</span><span class="sxs-lookup"><span data-stu-id="86b2c-118">Posting profile</span></span> | <span data-ttu-id="86b2c-119">Entrez un nom unique pour le profil.</span><span class="sxs-lookup"><span data-stu-id="86b2c-119">Enter a unique name for the profile.</span></span> |
| <span data-ttu-id="86b2c-120">Description</span><span class="sxs-lookup"><span data-stu-id="86b2c-120">Description</span></span> | <span data-ttu-id="86b2c-121">Entrez une description du profil.</span><span class="sxs-lookup"><span data-stu-id="86b2c-121">Enter a description of the profile.</span></span> |
| <span data-ttu-id="86b2c-122">Module</span><span class="sxs-lookup"><span data-stu-id="86b2c-122">Module</span></span> | <span data-ttu-id="86b2c-123">Sélectionnez le type de remises et de redevances auquel le profil est associé (*Client* ou *Fournisseur*).</span><span class="sxs-lookup"><span data-stu-id="86b2c-123">Select the type of rebates and royalties that the profile is associated with (*Customer* or *Vendor*).</span></span> |
| <span data-ttu-id="86b2c-124">Type</span><span class="sxs-lookup"><span data-stu-id="86b2c-124">Type</span></span> | <span data-ttu-id="86b2c-125">Sélectionnez le type de profil (*Remise* ou *Redevances*).</span><span class="sxs-lookup"><span data-stu-id="86b2c-125">Select the profile type (*Rebate* or *Royalty*).</span></span> |
| <span data-ttu-id="86b2c-126">Type de paiement</span><span class="sxs-lookup"><span data-stu-id="86b2c-126">Payment type</span></span> | <p><span data-ttu-id="86b2c-127">Ce champ détermine le format du résultat de la remise validée.</span><span class="sxs-lookup"><span data-stu-id="86b2c-127">This field determines the format of the posted rebate output.</span></span><p><p><span data-ttu-id="86b2c-128">Quand le champ **Type** est défini sur *Remise*, les valeurs suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="86b2c-128">When the **Type** field is set to *Rebate*, the following values are available:</span></span></p><ul><li><span data-ttu-id="86b2c-129">*Aucune* : il n’y a pas de type de validation par défaut.</span><span class="sxs-lookup"><span data-stu-id="86b2c-129">*None* – There is no default posting type.</span></span> <span data-ttu-id="86b2c-130">Par conséquent, vous devez définir le type lorsque vous effectuez le traitement.</span><span class="sxs-lookup"><span data-stu-id="86b2c-130">Therefore, you must define the type when you do the processing.</span></span></li><li><span data-ttu-id="86b2c-131">*Payer en utilisant la comptabilité fournisseur* : lorsque vous validez la remise, une facture fournisseur est créée pour le fournisseur bénéficiaire de la remise qui est configuré sur le client de la remise.</span><span class="sxs-lookup"><span data-stu-id="86b2c-131">*Pay using accounts payable* – When you post the rebate, a vendor invoice for the remittance vendor that is set up on the rebate customer is created.</span></span></li><li><span data-ttu-id="86b2c-132">*Déductions client* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</span><span class="sxs-lookup"><span data-stu-id="86b2c-132">*Customer deductions* – When you post the rebate, a customer deduction journal for the rebate customer is created.</span></span></li><li><span data-ttu-id="86b2c-133">*Déductions client sur facture fiscale* : lorsque vous validez la remise, une facture financière pour le client de la remise est créée.</span><span class="sxs-lookup"><span data-stu-id="86b2c-133">*Tax invoice customer deductions* – When you post the rebate, a free text invoice for the rebate customer is created.</span></span></li><li><span data-ttu-id="86b2c-134">*Dépense de commerce* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</span><span class="sxs-lookup"><span data-stu-id="86b2c-134">*Trade spending* – When you post the rebate, a customer deduction journal for the rebate customer is created.</span></span></li><li><span data-ttu-id="86b2c-135">*Génération de rapport* : lorsque vous validez la remise, un journal de déduction client pour le client de la remise est créé.</span><span class="sxs-lookup"><span data-stu-id="86b2c-135">*Reporting* – When you post the rebate, a customer deduction journal for the rebate customer is created.</span></span></li></ul><p><span data-ttu-id="86b2c-136">Quand le champ **Type** est défini sur *Redevance*, les valeurs suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="86b2c-136">When the **Type** field is set to *Royalty*, the following values are available:</span></span></p><ul><li><span data-ttu-id="86b2c-137">*Aucune* : il n’y a pas de type de validation par défaut.</span><span class="sxs-lookup"><span data-stu-id="86b2c-137">*None* – There is no default posting type.</span></span> <span data-ttu-id="86b2c-138">Par conséquent, vous devez définir le type lorsque vous effectuez le traitement.</span><span class="sxs-lookup"><span data-stu-id="86b2c-138">Therefore, you must define the type when you do the processing.</span></span></li><li><span data-ttu-id="86b2c-139">*Payer en utilisant la comptabilité fournisseur* : lorsque vous validez la remise, une facture fournisseur est créée pour le compte fournisseur bénéficiaire de la remise.</span><span class="sxs-lookup"><span data-stu-id="86b2c-139">*Pay using accounts payable* – When you post the rebate, a vendor invoice for the rebate vendor account is created.</span></span></li><li><span data-ttu-id="86b2c-140">*Génération de rapport* : lorsque vous validez la remise, une facture fournisseur est créée pour le compte fournisseur bénéficiaire de la remise.</span><span class="sxs-lookup"><span data-stu-id="86b2c-140">*Reporting* – When you post the rebate, a vendor invoice for the rebate vendor account is created.</span></span></li></ul><p><span data-ttu-id="86b2c-141">Pour plus d’informations, voir la section [Types de paiement](#payment-types) suivante.</span><span class="sxs-lookup"><span data-stu-id="86b2c-141">For more information, see the [Payment types](#payment-types) section that follows.</span></span> |
| <span data-ttu-id="86b2c-142">Société</span><span class="sxs-lookup"><span data-stu-id="86b2c-142">Company</span></span> | <span data-ttu-id="86b2c-143">Sélectionnez l’entreprise (entité juridique) pour laquelle les provisions seront constituées et par laquelle les réclamations seront payées.</span><span class="sxs-lookup"><span data-stu-id="86b2c-143">Select the company (legal entity) that provisions will be accrued to and that claims will be paid by.</span></span> |

### <a name="payment-types"></a><span data-ttu-id="86b2c-144">Types de paiements</span><span class="sxs-lookup"><span data-stu-id="86b2c-144">Payment types</span></span>

<span data-ttu-id="86b2c-145">Le tableau suivant résume la manière dont les différents paramètres du champ **Type de paiement** affectent l’endroit où les paiements sont validés.</span><span class="sxs-lookup"><span data-stu-id="86b2c-145">The following table summarizes how the various settings of the **Payment type** field affect where payments are posted.</span></span> <span data-ttu-id="86b2c-146">Les paiements peuvent être validés sur un compte client, un compte fournisseur ou un compte de remise, selon la transaction cible et le type de remise.</span><span class="sxs-lookup"><span data-stu-id="86b2c-146">Payments can be posted to a customer account, vendor account, or remittance account, depending on the target transaction and the rebate type.</span></span>

| <span data-ttu-id="86b2c-147">Type de paiement</span><span class="sxs-lookup"><span data-stu-id="86b2c-147">Payment type</span></span> | <span data-ttu-id="86b2c-148">Type de transaction cible</span><span class="sxs-lookup"><span data-stu-id="86b2c-148">Target transaction type</span></span> | <span data-ttu-id="86b2c-149">Type de remise</span><span class="sxs-lookup"><span data-stu-id="86b2c-149">Rebate type</span></span> | <span data-ttu-id="86b2c-150">Paiement à (compte de facturation)</span><span class="sxs-lookup"><span data-stu-id="86b2c-150">Payment to (invoice account)</span></span> |
|---|---|---|---|
| <span data-ttu-id="86b2c-151">Payer à l’aide de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-151">Pay using accounts payable</span></span> | <span data-ttu-id="86b2c-152">Journal des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-152">Vendor invoice journal</span></span> | <span data-ttu-id="86b2c-153">Remise client</span><span class="sxs-lookup"><span data-stu-id="86b2c-153">Customer rebate</span></span> | <span data-ttu-id="86b2c-154">Compte fournisseur de remise du client</span><span class="sxs-lookup"><span data-stu-id="86b2c-154">Customer's remittance vendor account</span></span> |
| <span data-ttu-id="86b2c-155">Payer à l’aide de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-155">Pay using accounts payable</span></span> | <span data-ttu-id="86b2c-156">Journal des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-156">Vendor invoice journal</span></span> | <span data-ttu-id="86b2c-157">Redevance client</span><span class="sxs-lookup"><span data-stu-id="86b2c-157">Customer royalty</span></span> | <span data-ttu-id="86b2c-158">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-158">Vendor account</span></span> |
| <span data-ttu-id="86b2c-159">Payer à l’aide de la comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-159">Pay using accounts payable</span></span> | <span data-ttu-id="86b2c-160">Journal des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-160">Vendor invoice journal</span></span> | <span data-ttu-id="86b2c-161">Remise fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-161">Vendor rebate</span></span> | <span data-ttu-id="86b2c-162">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-162">Vendor account</span></span> |
| <span data-ttu-id="86b2c-163">Déductions client</span><span class="sxs-lookup"><span data-stu-id="86b2c-163">Customer deductions</span></span> | <span data-ttu-id="86b2c-164">Journal quotidien</span><span class="sxs-lookup"><span data-stu-id="86b2c-164">Daily journal</span></span> | <span data-ttu-id="86b2c-165">Remise client</span><span class="sxs-lookup"><span data-stu-id="86b2c-165">Customer rebate</span></span> | <span data-ttu-id="86b2c-166">Compte client</span><span class="sxs-lookup"><span data-stu-id="86b2c-166">Customer account</span></span> |
| <span data-ttu-id="86b2c-167">Déductions client sur facture fiscale</span><span class="sxs-lookup"><span data-stu-id="86b2c-167">Tax invoice customer deductions</span></span> | <span data-ttu-id="86b2c-168">Facture financière</span><span class="sxs-lookup"><span data-stu-id="86b2c-168">Free text invoice</span></span> | <span data-ttu-id="86b2c-169">Remise client</span><span class="sxs-lookup"><span data-stu-id="86b2c-169">Customer rebate</span></span> | <span data-ttu-id="86b2c-170">Compte client</span><span class="sxs-lookup"><span data-stu-id="86b2c-170">Customer account</span></span> |
| <span data-ttu-id="86b2c-171">Dépense de commerce</span><span class="sxs-lookup"><span data-stu-id="86b2c-171">Trade spending</span></span> | <span data-ttu-id="86b2c-172">Journal quotidien</span><span class="sxs-lookup"><span data-stu-id="86b2c-172">Daily journal</span></span> | <span data-ttu-id="86b2c-173">Remise client</span><span class="sxs-lookup"><span data-stu-id="86b2c-173">Customer rebate</span></span> | <span data-ttu-id="86b2c-174">Compte client</span><span class="sxs-lookup"><span data-stu-id="86b2c-174">Customer account</span></span> |
| <span data-ttu-id="86b2c-175">Génération d’états</span><span class="sxs-lookup"><span data-stu-id="86b2c-175">Reporting</span></span> | <span data-ttu-id="86b2c-176">Journal quotidien</span><span class="sxs-lookup"><span data-stu-id="86b2c-176">Daily journal</span></span> | <span data-ttu-id="86b2c-177">Remise client</span><span class="sxs-lookup"><span data-stu-id="86b2c-177">Customer rebate</span></span> | <span data-ttu-id="86b2c-178">Compte client</span><span class="sxs-lookup"><span data-stu-id="86b2c-178">Customer account</span></span> |
| <span data-ttu-id="86b2c-179">Génération d’états</span><span class="sxs-lookup"><span data-stu-id="86b2c-179">Reporting</span></span> | <span data-ttu-id="86b2c-180">Journal des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-180">Vendor invoice journal</span></span> | <span data-ttu-id="86b2c-181">Redevance client</span><span class="sxs-lookup"><span data-stu-id="86b2c-181">Customer royalty</span></span> | <span data-ttu-id="86b2c-182">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-182">Vendor account</span></span> |
| <span data-ttu-id="86b2c-183">Génération d’états</span><span class="sxs-lookup"><span data-stu-id="86b2c-183">Reporting</span></span> | <span data-ttu-id="86b2c-184">Journal des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-184">Vendor invoice journal</span></span> | <span data-ttu-id="86b2c-185">Remise fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-185">Vendor rebate</span></span> | <span data-ttu-id="86b2c-186">Compte fournisseur</span><span class="sxs-lookup"><span data-stu-id="86b2c-186">Vendor account</span></span> |

> [!NOTE]
> <span data-ttu-id="86b2c-187">Tenez compte des points suivants lors de la configuration des [accords de gestion des remises](rebate-management-deals.md) :</span><span class="sxs-lookup"><span data-stu-id="86b2c-187">Consider the following points when you set up [Rebate management deals](rebate-management-deals.md):</span></span>
>
> - <span data-ttu-id="86b2c-188">Pour les accords où le champ **Rapprochement par** est défini sur *Accord*, vous ne pouvez pas utiliser le compte d’accord dynamique lors de la validation.</span><span class="sxs-lookup"><span data-stu-id="86b2c-188">For deals where the **Reconcile by** field is set to *Deal*, you can't use the dynamic deal account during posting.</span></span> <span data-ttu-id="86b2c-189">Vous devez utiliser un compte client ou fournisseur spécifié.</span><span class="sxs-lookup"><span data-stu-id="86b2c-189">You must use a specified customer or vendor account.</span></span>
> - <span data-ttu-id="86b2c-190">Pour les accords où le champ **Rapprochement par** est défini sur *Ligne*, vous pouvez utiliser un profil de validation qui est compensé par un compte d’accord dynamique sur la ligne d’accord, car le client est défini par ligne d’accord.</span><span class="sxs-lookup"><span data-stu-id="86b2c-190">For deals where the **Reconcile by** field is set to *Line*, you can use a posting profile that offsets to a dynamic deal account on the deal line, because the customer is set per deal line.</span></span>

## <a name="posting-fasttab"></a><span data-ttu-id="86b2c-191">Raccourci Validation</span><span class="sxs-lookup"><span data-stu-id="86b2c-191">Posting FastTab</span></span>

<span data-ttu-id="86b2c-192">Le tableau suivant décrit les champs disponibles dans le raccourci **Validation** de chaque profil de validation de la gestion des remises.</span><span class="sxs-lookup"><span data-stu-id="86b2c-192">The following table describes the fields that are available on the **Posting** FastTab of each Rebate management posting profile.</span></span>

| <span data-ttu-id="86b2c-193">Champ</span><span class="sxs-lookup"><span data-stu-id="86b2c-193">Field</span></span> | <span data-ttu-id="86b2c-194">Description</span><span class="sxs-lookup"><span data-stu-id="86b2c-194">Description</span></span> |
|---|---|
| <span data-ttu-id="86b2c-195">Type de crédit</span><span class="sxs-lookup"><span data-stu-id="86b2c-195">Credit type</span></span> | <span data-ttu-id="86b2c-196">Sélectionnez s’il faut créditer un compte général ou un client ou un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="86b2c-196">Select whether to credit a ledger account, or a customer or vendor.</span></span> |
| <span data-ttu-id="86b2c-197">Compte à créditer</span><span class="sxs-lookup"><span data-stu-id="86b2c-197">Credit account</span></span> | <span data-ttu-id="86b2c-198">Le compte sur lequel les montants de crédit sont imputés lorsque des provisions de remise sont constituées.</span><span class="sxs-lookup"><span data-stu-id="86b2c-198">The account that credit amounts are posted to when rebate provisions are made.</span></span> <span data-ttu-id="86b2c-199">Ce compte sera également utilisé comme compte de débit lorsque la remise sera validée pour créditer le client.</span><span class="sxs-lookup"><span data-stu-id="86b2c-199">This account will also be used as the debit account when the rebate is posted to credit the customer.</span></span> |
| <span data-ttu-id="86b2c-200">Nom de journal</span><span class="sxs-lookup"><span data-stu-id="86b2c-200">Name of journal</span></span><br><span data-ttu-id="86b2c-201">(dans la section **Provision**)</span><span class="sxs-lookup"><span data-stu-id="86b2c-201">(In the **Provision** section)</span></span> | <span data-ttu-id="86b2c-202">Sélectionnez le nom du journal à utiliser pour enregistrer la provision validée.</span><span class="sxs-lookup"><span data-stu-id="86b2c-202">Select the name of the journal to use to record the posted provision.</span></span> |
| <span data-ttu-id="86b2c-203">Type</span><span class="sxs-lookup"><span data-stu-id="86b2c-203">Type</span></span> | <span data-ttu-id="86b2c-204">Sélectionnez s’il faut valider la remise sur un compte général ou un client ou un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="86b2c-204">Select whether to post the rebate to a ledger account, or to a customer or vendor.</span></span> <span data-ttu-id="86b2c-205">Si le champ **Type de paiement** de l’en-tête est défini sur *Déductions client sur facture fiscale*, ce champ est défini sur *Client/Fournisseur*.</span><span class="sxs-lookup"><span data-stu-id="86b2c-205">If the **Payment type** field on the header is set to *Tax invoice customer deductions*, this field is set to *Customer/Vendor*.</span></span> |
| <span data-ttu-id="86b2c-206">Utiliser un compte source</span><span class="sxs-lookup"><span data-stu-id="86b2c-206">Use account source</span></span> | <p><span data-ttu-id="86b2c-207">Vous devez sélectionner l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b2c-207">Select one of the following values:</span></span></p><ul><li><span data-ttu-id="86b2c-208">*Aucun* : si vous sélectionnez cette valeur, vous devez spécifier un compte dans le champ **Compte de remise**.</span><span class="sxs-lookup"><span data-stu-id="86b2c-208">*None* – If you select this value, you must specify an account in the **Rebate account** field.</span></span></li><li><span data-ttu-id="86b2c-209">*Compte d’accord* : utilisez le compte client ou fournisseur spécifié sur la ligne de remise.</span><span class="sxs-lookup"><span data-stu-id="86b2c-209">*Deal Account* – Use the customer or vendor account that is specified on the rebate line.</span></span> <span data-ttu-id="86b2c-210">Vous ne pouvez sélectionner cette valeur que pour les accords où le champ **Rapprochement par** est défini sur *Ligne* et les lignes d’accord où le champ **Code de compte** est défini sur *Table*.</span><span class="sxs-lookup"><span data-stu-id="86b2c-210">You can select this value only for deals where the **Reconcile by** field is set to *Line* and deal lines where the **Account code** field is set to *Table*.</span></span> <span data-ttu-id="86b2c-211">Cela ne s’applique pas aux profils de validation des redevances client.</span><span class="sxs-lookup"><span data-stu-id="86b2c-211">It doesn't apply to customer royalty posting profiles.</span></span></li></ul> |
| <span data-ttu-id="86b2c-212">Compte de remise</span><span class="sxs-lookup"><span data-stu-id="86b2c-212">Rebate account</span></span> | <span data-ttu-id="86b2c-213">Le compte sur lequel les dépenses de remise seront imputés.</span><span class="sxs-lookup"><span data-stu-id="86b2c-213">The account that actual rebates expense will be posted to.</span></span> |
| <span data-ttu-id="86b2c-214">Nom de journal</span><span class="sxs-lookup"><span data-stu-id="86b2c-214">Name of journal</span></span><br><span data-ttu-id="86b2c-215">(Dans la section **Gestion des remises**)</span><span class="sxs-lookup"><span data-stu-id="86b2c-215">(In the **Rebate management** section)</span></span> | <span data-ttu-id="86b2c-216">Sélectionnez le nom du journal à utiliser pour valider un avoir pour le montant de la remise au client.</span><span class="sxs-lookup"><span data-stu-id="86b2c-216">Select the name of the journal to use to post a credit note for the rebate amount to the customer.</span></span> <span data-ttu-id="86b2c-217">Ce champ n’est pas disponible quand le champ **Type de paiement** de l’en-tête est défini sur *Déductions client sur facture fiscale*.</span><span class="sxs-lookup"><span data-stu-id="86b2c-217">This field is unavailable when the **Payment type** field on the header is set to *Tax invoice customer deductions*.</span></span> |
| <span data-ttu-id="86b2c-218">Groupe de taxe d’article</span><span class="sxs-lookup"><span data-stu-id="86b2c-218">Item sales tax group</span></span> | <span data-ttu-id="86b2c-219">Précisez si la remise est taxable.</span><span class="sxs-lookup"><span data-stu-id="86b2c-219">Specify whether the rebate is taxable.</span></span> |
| <span data-ttu-id="86b2c-220">Nom de journal</span><span class="sxs-lookup"><span data-stu-id="86b2c-220">Name of journal</span></span><br><span data-ttu-id="86b2c-221">(Dans la section **Annulation**)</span><span class="sxs-lookup"><span data-stu-id="86b2c-221">(In the **Write off** section)</span></span> | <span data-ttu-id="86b2c-222">Si la remise validée n’est pas égale à la provision, la différence peut être annulée.</span><span class="sxs-lookup"><span data-stu-id="86b2c-222">If the rebate that is posted doesn't equal the provision, the difference can be written off.</span></span> <span data-ttu-id="86b2c-223">Sélectionnez le nom du journal à utiliser pour enregistrer l’annulation validée.</span><span class="sxs-lookup"><span data-stu-id="86b2c-223">Select the name of the journal to use to record the posted write-off.</span></span> |

## <a name="posting-by-company-fasttab"></a><span data-ttu-id="86b2c-224">Raccourci Annulation par entreprise</span><span class="sxs-lookup"><span data-stu-id="86b2c-224">Posting by company FastTab</span></span>

<span data-ttu-id="86b2c-225">Le raccourci **Validation par entreprise** de chaque profil de validation de la gestion des remises vous permet de spécifier le compte de validation utilisé par chaque société (entité juridique) dans la grille.</span><span class="sxs-lookup"><span data-stu-id="86b2c-225">The **Posting by company** FastTab of each Rebate management posting profile lets you specify the posting account that is used by each company (legal entity) in the grid.</span></span>

<span data-ttu-id="86b2c-226">Utiliser les boutons sur la barre d’outils pour ajouter des sociétés à la grille ou en supprimer.</span><span class="sxs-lookup"><span data-stu-id="86b2c-226">Use the buttons on the toolbar to add companies to the grid and remove them.</span></span> <span data-ttu-id="86b2c-227">Chaque fois que vous ajoutez une ligne à la grille, utilisez le champ **Société** pour spécifier l’entité juridique de cette ligne.</span><span class="sxs-lookup"><span data-stu-id="86b2c-227">Each time that you add a row to the grid, use the **Company** field to specify the legal entity for that row.</span></span> <span data-ttu-id="86b2c-228">Le champ **Nom** est alors défini automatiquement.</span><span class="sxs-lookup"><span data-stu-id="86b2c-228">The **Name** field is then set automatically.</span></span>

<span data-ttu-id="86b2c-229">Sélectionnez la ligne pour chaque société, puis entrez les informations suivantes en utilisant les champs sous la grille :</span><span class="sxs-lookup"><span data-stu-id="86b2c-229">Select the row for each company, and then enter the following information by using the fields below the grid:</span></span>

- <span data-ttu-id="86b2c-230">**Type de débit** : sélectionnez s’il faut débiter un compte général ou un client ou un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="86b2c-230">**Debit type** – Select whether to debit a ledger account, or a customer or vendor.</span></span>
- <span data-ttu-id="86b2c-231">**Compte de débit** : entrez le compte sur lequel le montant du débit est imputé lorsque les provisions de remise sont constituées.</span><span class="sxs-lookup"><span data-stu-id="86b2c-231">**Debit account** – Enter the account that the debit amount is posted to when rebate provisions are made.</span></span>
- <span data-ttu-id="86b2c-232">**Compte principal** : sélectionnez le compte principal pour les annulations.</span><span class="sxs-lookup"><span data-stu-id="86b2c-232">**Main account** – Select the main account for write-offs.</span></span>