---
title: "État du bordereau de paiement pour l'Europe"
description: "Cette rubrique fournit des informations sur les états de bordereau de paiement pour l'Europe."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OMLegalEntities, ProjFormletterParameters, CustFormletterParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 213cabd17b24471cfc4657a433c7ad02ac03b24a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="payment-slip-report-for-europe"></a><span data-ttu-id="f3127-103">État du bordereau de paiement pour l'Europe</span><span class="sxs-lookup"><span data-stu-id="f3127-103">Payment slip report for Europe</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="f3127-104">Cette rubrique fournit des informations sur les états de bordereau de paiement pour l'Europe.</span><span class="sxs-lookup"><span data-stu-id="f3127-104">This topic provides information about payment slip reports for Europe.</span></span>

<span data-ttu-id="f3127-105">La fonctionnalité pour les états de bordereau de paiement est disponible pour les entités juridiques dont l'adresse principale est située au Danemark, en Belgique, en Norvège, en Suisse ou en Finlande.</span><span class="sxs-lookup"><span data-stu-id="f3127-105">The functionality for payment slip reports is available for legal entities that have their primary address in Denmark, Belgium, Norway, Switzerland, or Finland.</span></span> <span data-ttu-id="f3127-106">Les entreprises associent souvent les bordereaux de paiement imprimés aux factures pour fournir une référence de paiement pour la validation et le règlement.</span><span class="sxs-lookup"><span data-stu-id="f3127-106">Businesses often attach printed payment slips to invoices to provide a payment reference for posting and settlement.</span></span> <span data-ttu-id="f3127-107">Les bordereaux de paiement peuvent être utilisés pour les factures de projet ou de service, les lettres de relance, les notes d'intérêt et les relevés de compte, en plus des factures client et des factures financières.</span><span class="sxs-lookup"><span data-stu-id="f3127-107">The payment slip can be used for project or service invoices, collection letters, interest notes, and account statements, in addition to sales invoices and free text invoices.</span></span>

## <a name="set-up-a-creditor-id-number-denmark-only"></a><span data-ttu-id="f3127-108">Paramétrage d'un ID créditeur (Danemark uniquement)</span><span class="sxs-lookup"><span data-stu-id="f3127-108">Set up a creditor ID number (Denmark only)</span></span>
<span data-ttu-id="f3127-109">Suivez les étapes ci-après pour entrer l'ID créditeur de votre société.</span><span class="sxs-lookup"><span data-stu-id="f3127-109">Follow these steps to enter your company's creditor identification (ID) number.</span></span> <span data-ttu-id="f3127-110">Votre institution financière fournit ce numéro.</span><span class="sxs-lookup"><span data-stu-id="f3127-110">Your financial institution provides this number.</span></span> <span data-ttu-id="f3127-111">Il sert de référence lorsque les paiements client sont reçus via les institutions financières.</span><span class="sxs-lookup"><span data-stu-id="f3127-111">It's used as a reference when customer payments are received through financial institutions.</span></span>

1.  <span data-ttu-id="f3127-112">Cliquez sur **Administration d'organisation** &gt; **Paramétrage** &gt; **Organisation** &gt; **Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="f3127-112">Click **Organization administration** &gt; **Setup** &gt; **Organization** &gt; **Legal entities**.</span></span>
2.  <span data-ttu-id="f3127-113">Dans l'organisateur **Informations sur le compte en banque**, dans le champ **ID créditeur financier**, entrez votre ID créditeur à huit chiffres.</span><span class="sxs-lookup"><span data-stu-id="f3127-113">On the **Bank account information** FastTab, in the **FI-Creditor ID** field, enter your unique eight-digit creditor ID number.</span></span>
3.  <span data-ttu-id="f3127-114">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="f3127-114">Close the form to save your changes.</span></span>

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a><span data-ttu-id="f3127-115">Paramétrage d'un format de bordereau de paiement associé aux factures, notes d'intérêt, lettres de relance et relevés de compte</span><span class="sxs-lookup"><span data-stu-id="f3127-115">Set up a payment slip attachment format for invoices, interest notes, collection letters, and account statements</span></span>
<span data-ttu-id="f3127-116">Suivez les étapes ci-après pour paramétrer un format pour les bordereaux de paiement associés aux factures client, aux factures financières, aux notes d'intérêt, aux lettres de relance et aux relevés de compte.</span><span class="sxs-lookup"><span data-stu-id="f3127-116">Follow these steps to set up a format for payment slip attachments that accompany sales invoices, free text invoices, interest notes, collection letters, and account statements.</span></span>

1.  <span data-ttu-id="f3127-117">Cliquez sur **Comptabilité client** &gt; **Paramétrage** &gt; **Écrans** &gt; **Paramétrage d'écran**.</span><span class="sxs-lookup"><span data-stu-id="f3127-117">Click **Accounts receivable** &gt; **Setup** &gt; **Forms** &gt; **Form setup**.</span></span>
2.  <span data-ttu-id="f3127-118">Sous l'onglet **Facture**, dans le champ **Document de paiement associé de facture client**, sélectionnez le format du bordereau de paiement associé.</span><span class="sxs-lookup"><span data-stu-id="f3127-118">On the **Invoice** tab, in the **Associated payment attachment on customer invoice** field, select the payment slip attachment format.</span></span>
3.  <span data-ttu-id="f3127-119">Sous les onglets **Facture financière**, **Note d'intérêt**, **Lettre de relance** et **Relevé de compte**, sélectionnez un format de bordereau de paiement associé pour chaque type de document.</span><span class="sxs-lookup"><span data-stu-id="f3127-119">On the **Free text invoice**, **Interest note**, **Collection letter**, and **Account statement** tabs, select a payment slip attachment format for each document type.</span></span>
4.  <span data-ttu-id="f3127-120">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="f3127-120">Close the form to save your changes.</span></span>

<span data-ttu-id="f3127-121">Suivez les étapes ci-après pour paramétrer un format pour les bordereaux de paiement associés aux factures de projet.</span><span class="sxs-lookup"><span data-stu-id="f3127-121">Follow these steps to set up a format for payment slip attachments that accompany project invoices.</span></span>

1.  <span data-ttu-id="f3127-122">Cliquez sur **Gestion de projet et comptabilité** &gt; **Paramétrage** &gt; **Écrans** &gt; **Paramétrage d'écran**.</span><span class="sxs-lookup"><span data-stu-id="f3127-122">Click **Project management and accounting** &gt; **Setup** &gt; **Forms** &gt; **Form setup**.</span></span>
2.  <span data-ttu-id="f3127-123">Dans le champ **Document de paiement associé**, sélectionnez le format du bordereau de paiement associé.</span><span class="sxs-lookup"><span data-stu-id="f3127-123">In the **Associated payment attachment** field, select the payment slip attachment format.</span></span>

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a><span data-ttu-id="f3127-124">Affectation d'un format de bordereau de paiement associé à un compte client</span><span class="sxs-lookup"><span data-stu-id="f3127-124">Assign a payment slip attachment format to a customer account</span></span>
<span data-ttu-id="f3127-125">Après avoir paramétré le format du bordereau de paiement associé aux factures client, aux factures financières, aux notes d'intérêt, aux lettres de relance, aux relevés de compte et aux factures de projet, vous pouvez affecter des formats spécifiques au client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f3127-125">After you set up the payment slip attachment format for sales invoices, free text invoices, interest notes, collection letters, account statements, and project invoices, you can assign specific formats for a selected customer.</span></span>

1.  <span data-ttu-id="f3127-126">Cliquez sur **Comptabilité client** &gt; **Commun** &gt; **Clients** &gt; **Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="f3127-126">Click **Accounts receivable** &gt; **Common** &gt; **Customers** &gt; **All customers**.</span></span>
2.  <span data-ttu-id="f3127-127">Créez un client ou sélectionnez-en un.</span><span class="sxs-lookup"><span data-stu-id="f3127-127">Create a new customer, or select an existing customer.</span></span>
3.  <span data-ttu-id="f3127-128">Dans l'organisateur **Facture et livraison**, dans les champs **Sur une facture client**, **Sur une facture financière**, **Sur une note d'intérêt**, **Sur une lettre de relance**, **Sur une facture de projet** et **Sur un relevé de compte**, sélectionnez le format des bordereaux de paiement associés aux documents de chaque type qui sont envoyés au client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f3127-128">On the **Invoice and delivery** FastTab, in the **On a customer invoice**, **On a free text invoice**, **On an interest note**, **On a collection letter**, **On a project invoice**, and **On an account statement** fields, select the format for payment slip attachments that will accompany documents of each type that are sent to the selected customer.</span></span>
4.  <span data-ttu-id="f3127-129">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="f3127-129">Close the form to save your changes.</span></span>





