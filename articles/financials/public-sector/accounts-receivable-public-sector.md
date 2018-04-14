---
title: "Comptabilité client dans le secteur public"
description: "Cette rubrique décrit la fonctionnalité de Comptabilité client disponible pour le secteur public."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceJournal, CustParameters, CustTradingPartnerCode
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 26281
ms.assetid: a411ec87-a209-471c-a141-5f5a92f2e45e
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: aff05047ceee7c994532851808474e63fb422517
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="accounts-receivable-in-the-public-sector"></a><span data-ttu-id="ff7df-103">Comptabilité client dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="ff7df-103">Accounts receivable in the public sector</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="ff7df-104">Cette rubrique décrit la fonctionnalité de Comptabilité client disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="ff7df-104">This topic describes the Accounts receivable functionality that is available for the public sector.</span></span>

<a name="how-do-i-set-accounts-receivable-parameters-for-the-public-sector"></a><span data-ttu-id="ff7df-105">Comment définir les paramètres de comptabilité client pour le secteur public ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-105">How do I set Accounts receivable parameters for the public sector?</span></span>
------------------------------------------------------------------

<span data-ttu-id="ff7df-106">La plupart des paramètres de comptabilité client sont définis de la même manière si vous êtes dans le secteur public ou le secteur privé.</span><span class="sxs-lookup"><span data-stu-id="ff7df-106">Most Accounts receivable parameters are set the same way whether you’re in the public sector or the private sector.</span></span> <span data-ttu-id="ff7df-107">Toutefois, les paramètres requis pour les classifications de facturation et les codes facturation sont utilisés uniquement par le secteur public.</span><span class="sxs-lookup"><span data-stu-id="ff7df-107">However, the parameters that are required for billing classifications and billing codes are used only by the public sector.</span></span> <span data-ttu-id="ff7df-108">Pour plus d'informations, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ff7df-108">For more information, see [Billing classifications and billing codes in the public sector](billing-classifications-billing-codes-public-sector.md).</span></span>

-   <span data-ttu-id="ff7df-109">Pour activer l'utilisation des classifications de facturation et des codes facturation, dans la section **Général**, dans l'organisateur **Paramétrage des ventes**, sélectionnez **Utiliser les classifications de facturation**.</span><span class="sxs-lookup"><span data-stu-id="ff7df-109">To enable the use of billing classifications and billing codes, in the **General** section, on the **Sales setup** FastTab, select **Use billing classifications**.</span></span>
-   <span data-ttu-id="ff7df-110">Pour octroyer la priorité au règlement des factures financières, voir les paramètres requis dans [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md) et [Factures financières dans le secteur public](free-text-invoices-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ff7df-110">To prioritize the settlement of free text invoices, see the required parameter settings in [Settlement priority in the public sector](settlement-priority-public-sector.md) and [Free text invoices in the public sector](free-text-invoices-public-sector.md).</span></span>
-   <span data-ttu-id="ff7df-111">Pour utiliser les codes facturation avec la comptabilité de projet, sélectionnez l'option permettant d'afficher les champs associés au projet dans les factures financières.</span><span class="sxs-lookup"><span data-stu-id="ff7df-111">To use billing codes with Project accounting, select the option to display project-related fields on free text invoices.</span></span> <span data-ttu-id="ff7df-112">Lorsque vous procédez ainsi, deux choses se produisent :</span><span class="sxs-lookup"><span data-stu-id="ff7df-112">When you do this, two things happen:</span></span>
    -   <span data-ttu-id="ff7df-113">Les champs associés au projet sont affichés à la fois dans les factures financières et les codes facturation.</span><span class="sxs-lookup"><span data-stu-id="ff7df-113">Project-related fields are displayed both on free text invoices and on billing codes.</span></span>
    -   <span data-ttu-id="ff7df-114">Le compte général associé au projet est automatiquement utilisé dans la facture financière.</span><span class="sxs-lookup"><span data-stu-id="ff7df-114">The ledger account related to the project is automatically used on the free text invoice.</span></span> <span data-ttu-id="ff7df-115">Pour autoriser les utilisateurs à modifier le compte général dans la facture financière et dans les répartitions comptables, sélectionnez l'option permettant d'autoriser la modification du numéro du compte général.</span><span class="sxs-lookup"><span data-stu-id="ff7df-115">To allow users to change the ledger account on the free text invoice and in the accounting distributions, select the option to allow the ledger account number to be changed.</span></span>

## <a name="how-do-i-control-the-settlement-order-for-accounts-receivable-transactions"></a><span data-ttu-id="ff7df-116">Comment contrôler l'ordre de règlement pour les transactions de comptabilité client ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-116">How do I control the settlement order for Accounts receivable transactions?</span></span>
<span data-ttu-id="ff7df-117">Vous pouvez utiliser les classifications de facturation avec d'autres attributs de facturation pour contrôler l'ordre de règlement de vos transactions de comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="ff7df-117">You can use billing classifications along with other billing attributes to control the order that your Accounts receivable transactions are settled in.</span></span> <span data-ttu-id="ff7df-118">Pour plus d'informations, voir [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ff7df-118">For details, see [Settlement priority in the public sector](settlement-priority-public-sector.md).</span></span>

## <a name="is-there-an-easy-way-to-review-reimbursement-transactions"></a><span data-ttu-id="ff7df-119">Existe-t-il une manière simple d'examiner les transactions de remboursement ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-119">Is there an easy way to review reimbursement transactions?</span></span>
<span data-ttu-id="ff7df-120">Vous pouvez utiliser les classifications de facturation pour créer une transaction de remboursement distincte pour chaque classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="ff7df-120">You can use billing classifications to create a separate reimbursement transaction for each billing classification.</span></span> <span data-ttu-id="ff7df-121">Lorsque vous procédez ainsi, les transactions de remboursement sont regroupées par l'écriture de type de validation de solde client et la classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="ff7df-121">When you do this, reimbursement transactions are grouped by the unique customer balance posting type entry and billing classification.</span></span> <span data-ttu-id="ff7df-122">Pour plus d'informations, voir [Remboursements dans le secteur public](reimbursements-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ff7df-122">For details, see [Reimbursements in the public sector](reimbursements-public-sector.md).</span></span>

## <a name="where-are-the-trading-partner-codes-that-i-need-for-gfrs-and-facts-i-reporting"></a><span data-ttu-id="ff7df-123">Où sont les codes partenaire commercial dont j'ai besoin pour la génération d'états GFRS et FACTS I ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-123">Where are the trading partner codes that I need for GFRS and FACTS I reporting?</span></span>
<span data-ttu-id="ff7df-124">Les codes partenaire commercial, qui sont nécessaires dans le cadre de la génération d'états GFRS et FACTS I, sont établis par le ministère des Finances américain.</span><span class="sxs-lookup"><span data-stu-id="ff7df-124">The trading partner codes required for GFRS and FACTS I reporting are established by the US Department of the Treasury.</span></span> <span data-ttu-id="ff7df-125">Toute organisation qui respecte les règles du gouvernement des États-Unis sur la génération d'états pour la comptabilité client doit ajouter des codes de partenaire commercial à ses informations de compte client pour les agences avec lesquelles elle entretient des relations commerciales.</span><span class="sxs-lookup"><span data-stu-id="ff7df-125">Any organization that follows U.S. governmental reporting rules for accounts receivables should add trading partner codes to their customer account information for the agencies they do business with.</span></span> <span data-ttu-id="ff7df-126">Par exemple, si votre agence entretient des relations commerciales avec la Federal Trade Commission, accédez à la page **Codes partenaire commercial** et créez le code partenaire commercial 29.</span><span class="sxs-lookup"><span data-stu-id="ff7df-126">For example, if your agency does business with the Federal Trade Commission, you’d go to the **Trading partner codes** page and create trading partner code 29.</span></span> <span data-ttu-id="ff7df-127">Ensuite, sur la page de détails du client pour la FTC, vous entrez 29 dans le champ **Code partenaire commercial**.</span><span class="sxs-lookup"><span data-stu-id="ff7df-127">Then, on the customer detail page for the FTC, you’d enter 29 in the **Trading partner code** field.</span></span>

### <a name="i-created-default-financial-dimensions-for-a-customer-group-but-one-customer-in-the-group-needs-a-different-value-for-one-of-the-financial-dimensions-whats-the-easiest-way-to-handle-this"></a><span data-ttu-id="ff7df-128">J'ai créé des dimensions financières par défaut pour un groupe de clients, mais un client du groupe a besoin d'une valeur différente pour l'une des dimensions financières.</span><span class="sxs-lookup"><span data-stu-id="ff7df-128">I created default financial dimensions for a customer group, but one customer in the group needs a different value for one of the financial dimensions.</span></span> <span data-ttu-id="ff7df-129">Quelle est la manière la plus simple de procéder ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-129">What’s the easiest way to handle this?</span></span>

<span data-ttu-id="ff7df-130">Vous pouvez conserver les dimensions financières par défaut pour le groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="ff7df-130">You can keep the default financial dimensions for the customer group.</span></span> <span data-ttu-id="ff7df-131">Accédez simplement à l'enregistrement client pour le client qui a besoin d'une valeur différente, puis entrez les dimensions financières par défaut pour le client.</span><span class="sxs-lookup"><span data-stu-id="ff7df-131">Just go to the customer record for the customer that needs a different value, and enter default financial dimensions for the customer.</span></span> <span data-ttu-id="ff7df-132">Les dimensions financières par défaut du client remplaceront les dimensions financières par défaut qui ont été définies pour le groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="ff7df-132">The customer’s default financial dimensions will override the default financial dimensions that were set for the customer group.</span></span>

## <a name="what-can-i-use-accounts-receivable-posting-definitions-for"></a><span data-ttu-id="ff7df-133">À quelles fins puis-je utiliser les définitions de validation de la comptabilité client ?</span><span class="sxs-lookup"><span data-stu-id="ff7df-133">What can I use Accounts receivable posting definitions for?</span></span>
<span data-ttu-id="ff7df-134">Vous pouvez utiliser les définitions de validation pour créer des lignes de journal de comptabilité auxiliaire pour les transactions d'origine qui répondent aux critères sélectionnés, par exemple, pour générer plusieurs écritures comptables équilibrées basées sur des attributs tels que des types de transactions et des comptes.</span><span class="sxs-lookup"><span data-stu-id="ff7df-134">You can use posting definitions to create subledger journal lines for originating transactions that meet selected criteria - for example, to generate multiple, balanced, ledger entries based on attributes such as transaction types and accounts.</span></span> <span data-ttu-id="ff7df-135">Pour plus d'informations sur les définitions de validation, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="ff7df-135">To learn more about posting definitions, see [Posting definitions in the public sector](posting-definitions-public-sector.md).</span></span>

<a name="see-also"></a><span data-ttu-id="ff7df-136">Voir également :</span><span class="sxs-lookup"><span data-stu-id="ff7df-136">See also</span></span>
--------

[<span data-ttu-id="ff7df-137">Ventes</span><span class="sxs-lookup"><span data-stu-id="ff7df-137">Accounts receivable</span></span>](..\accounts-receivable\accounts-receivable.md)

[<span data-ttu-id="ff7df-138">Créer un code facturation</span><span class="sxs-lookup"><span data-stu-id="ff7df-138">Create a billing code</span></span>](tasks/create-billing-code-public-sector.md)

[<span data-ttu-id="ff7df-139">Créer une classification de facturation</span><span class="sxs-lookup"><span data-stu-id="ff7df-139">Create a billing classification</span></span>](tasks/create-billing-classification-public-sector.md)

[<span data-ttu-id="ff7df-140">Créer et affecter un code partenaire commercial</span><span class="sxs-lookup"><span data-stu-id="ff7df-140">Create and assign a trading partner code</span></span>](tasks/create-assign-trading-partner-code-public-sector.md)



