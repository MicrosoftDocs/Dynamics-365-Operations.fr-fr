---
title: "Factures financières dans le secteur public"
description: "Cette rubrique décrit la fonctionnalité de facture financière disponible pour le secteur public et répond aux questions courantes sur l'utilisation des classifications de facturation et des codes de facturation avec les factures financières."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustBillingClassification, CustBillingCode, CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 25821
ms.assetid: 483e2726-ec48-4d1f-82f5-bffddea301ce
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29ccac10cda612f3b8d393727ed157516e99835d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="free-text-invoices-in-the-public-sector"></a><span data-ttu-id="03a0b-103">Factures financières dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="03a0b-103">Free text invoices in the public sector</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="03a0b-104">Cette rubrique décrit la fonctionnalité de facture financière disponible pour le secteur public et répond aux questions courantes sur l'utilisation des classifications de facturation et des codes de facturation avec les factures financières.</span><span class="sxs-lookup"><span data-stu-id="03a0b-104">This topic describes the free text invoice functionality that is available for public sector as well as answers common questions about using billing classifications and billing codes with free text invoices.</span></span>

<a name="do-i-have-to-select-a-billing-classification-for-every-free-text-invoice"></a><span data-ttu-id="03a0b-105">Dois-je sélectionner une classification de facturation pour chaque facture financière ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-105">Do I have to select a billing classification for every free text invoice?</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="03a0b-106">Oui, lorsque les classifications de facturation sont activées, vous devez entrer une classification de facturation pour chaque facture financière.</span><span class="sxs-lookup"><span data-stu-id="03a0b-106">Yes, when billing classifications are enabled, you have to enter a billing classification for every free text invoice.</span></span> <span data-ttu-id="03a0b-107">La classification de facturation contrôle quels codes facturation vous pouvez entrer sur la facture.</span><span class="sxs-lookup"><span data-stu-id="03a0b-107">The billing classification controls which billing codes that you can enter on the invoice.</span></span> <span data-ttu-id="03a0b-108">Elle régit également les conditions générales de paiement, les souches de numéros et le traitement de la facture.</span><span class="sxs-lookup"><span data-stu-id="03a0b-108">It also governs payment terms and conditions, number sequences, and the processing of the invoice.</span></span> <span data-ttu-id="03a0b-109">Pour plus d'informations sur les classifications de facturation, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="03a0b-109">To learn more about billing classifications, see [Billing classifications and billing codes in the public sector](billing-classifications-billing-codes-public-sector.md).</span></span>

## <a name="what-happens-if-ive-already-created-free-text-invoices-when-i-enable-billing-classifications"></a><span data-ttu-id="03a0b-110">Que se passe-t-il si j'ai déjà créé des factures financières lorsque j'active les classifications de facturation ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-110">What happens if I’ve already created free text invoices when I enable billing classifications?</span></span>
<span data-ttu-id="03a0b-111">Si une facture n'était pas encore validée lorsque vous avez activé les classifications de facturation, vous devez affecter une classification de facturation à la facture avant de pouvoir la valider.</span><span class="sxs-lookup"><span data-stu-id="03a0b-111">If an invoice was not yet posted when you enabled billing classifications, you have to assign a billing classification to the invoice before you can post it.</span></span> <span data-ttu-id="03a0b-112">Lorsque vous ouvrez la page pour afficher la facture, vous obtenez un message indiquant que la classification de facturation est requise.</span><span class="sxs-lookup"><span data-stu-id="03a0b-112">When you open the page to view the invoice, you'll get a message telling you that the billing classification is required.</span></span>

## <a name="why-should-i-use-billing-codes-when-i-create-free-text-invoices"></a><span data-ttu-id="03a0b-113">Pourquoi utiliser les codes facturation lorsque je crée des factures financières ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-113">Why should I use billing codes when I create free text invoices?</span></span>
<span data-ttu-id="03a0b-114">Lorsque vous sélectionnez un code facturation, les valeurs par défaut sont automatiquement entrées dans de nombreux champs de la ligne de facture.</span><span class="sxs-lookup"><span data-stu-id="03a0b-114">When you select a billing code, default values are automatically entered in many fields on the invoice line.</span></span> <span data-ttu-id="03a0b-115">Cela rend la saisie de données plus rapide et plus exacte.</span><span class="sxs-lookup"><span data-stu-id="03a0b-115">This makes data entry faster and more accurate.</span></span> <span data-ttu-id="03a0b-116">Les codes facturation sont également utilisés avec les définitions de validation pour contrôler la façon dont les transactions de comptabilité client sont validées dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="03a0b-116">Billing codes are also used with posting definitions to control how Accounts receivable transactions are posted to the ledger.</span></span>

## <a name="im-creating-a-free-text-invoice-and-the-billing-code-that-i-want-to-use-isnt-available-what-should-i-do"></a><span data-ttu-id="03a0b-117">Je crée une facture financière, et le code facturation que je souhaite utiliser n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="03a0b-117">I’m creating a free text invoice, and the billing code that I want to use isn’t available.</span></span> <span data-ttu-id="03a0b-118">Que dois-je faire ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-118">What should I do?</span></span>
<span data-ttu-id="03a0b-119">Assurez-vous d'abord que la facture utilise la bonne classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="03a0b-119">First make sure that the invoice is using the right billing classification.</span></span> <span data-ttu-id="03a0b-120">Seuls certains codes facturation peuvent être utilisés avec chaque classification de facturation.</span><span class="sxs-lookup"><span data-stu-id="03a0b-120">Only certain billing codes can be used with each billing classification.</span></span> <span data-ttu-id="03a0b-121">Si la classification de facturation est correcte, vous devez alors sélectionner l'un des codes facturation disponibles pour la facture financière que vous créez.</span><span class="sxs-lookup"><span data-stu-id="03a0b-121">If the billing classification is correct, then you should select one of the billing codes that are available for the free text invoice that you are creating.</span></span>

## <a name="i-can-change-some-of-the-fields-on-my-free-text-invoices-all-of-the-time-and-i-can-change-all-of-the-fields-some-of-the-time-but-some-of-the-fields-i-can-only-change-some-of-the-time-whats-up-with-that"></a><span data-ttu-id="03a0b-122">Je peux modifier certains champs de mes factures financières à tout moment, et je peux modifier tous les champs une partie du temps.</span><span class="sxs-lookup"><span data-stu-id="03a0b-122">I can change some of the fields on my free text invoices all of the time, and I can change all of the fields some of the time.</span></span> <span data-ttu-id="03a0b-123">Mais je peux uniquement modifier certains champs une partie du temps.</span><span class="sxs-lookup"><span data-stu-id="03a0b-123">But some of the fields I can only change some of the time.</span></span> <span data-ttu-id="03a0b-124">Qu'est-ce que cela signifie ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-124">What’s up with that?</span></span>
<span data-ttu-id="03a0b-125">Les paramètres du code facturation contrôlent si vous pouvez modifier certains champs.</span><span class="sxs-lookup"><span data-stu-id="03a0b-125">Settings on the billing code control whether you can change certain fields.</span></span>

-   <span data-ttu-id="03a0b-126">Si le code facturation sur une ligne de facture financière n'autorise pas les modifications de taux sur la facture, vous ne pouvez pas modifier le montant, le prix unitaire ni les détails du montant sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="03a0b-126">If the billing code on a free text invoice line doesn’t allow rate changes on the invoice, you can’t change the amount, the unit price, or the amount details on the line.</span></span> 

> [!TIP] 
> <span data-ttu-id="03a0b-127">Si le champ **Le code facturation détermine** est défini à « prix unitaire », vous ne pouvez pas modifier le prix unitaire, mais vous pouvez modifier le montant indirectement en modifiant la quantité.</span><span class="sxs-lookup"><span data-stu-id="03a0b-127">If the **Billing code determines** field is set to unit price, you can’t change the unit price, but you can change the amount indirectly by changing the quantity.</span></span>

-   <span data-ttu-id="03a0b-128">Si le code facturation sur une ligne de facture financière n'autorise pas les modifications aux comptes généraux, vous ne pouvez pas modifier les répartitions comptables sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="03a0b-128">If the billing code on a free text invoice line doesn’t allow changes to the ledger accounts, you can’t change the accounting distributions on the line.</span></span> <span data-ttu-id="03a0b-129">Vous pouvez modifier le compte principal qui s'affiche sur la ligne de facture financière, mais cette modification a un impact uniquement sur ce qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="03a0b-129">You can change the main account that displays on the free text invoice line, but that change affects only what is displayed.</span></span> <span data-ttu-id="03a0b-130">Modifier le compte principal n'affecte pas les répartitions.</span><span class="sxs-lookup"><span data-stu-id="03a0b-130">Changing the main account does not affect the distributions.</span></span>
-   <span data-ttu-id="03a0b-131">Lorsqu'un projet est associé à la ligne de facture, le code facturation contrôle si vous pouvez modifier l'ID projet, la catégorie et le compte général.</span><span class="sxs-lookup"><span data-stu-id="03a0b-131">When there’s a project associated with the invoice line, the billing code controls whether you can change the project ID, category, and ledger account.</span></span> 

> [!TIP] 
> <span data-ttu-id="03a0b-132">Pour modifier le compte général pour les lignes de facture associées à des projets, les modifications doivent être autorisées à la fois sur le code facturation lui-même et dans la section Projets de la page Paramètres de la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="03a0b-132">To change the ledger account for invoice lines related to projects, changes have to be allowed both on the billing code itself and on the Projects section of the Accounts receivable parameters page.</span></span>

<span data-ttu-id="03a0b-133">Pour plus d'informations sur les codes facturation, voir [Classifications de facturation et codes facturation dans le secteur public](billing-classifications-billing-codes-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="03a0b-133">To learn more about billing codes, see [Billing classifications and billing codes in the public sector](billing-classifications-billing-codes-public-sector.md).</span></span>

## <a name="where-does-the-interest-code-on-a-free-text-invoice-come-from"></a><span data-ttu-id="03a0b-134">D'où vient le code intérêt sur une facture financière ?</span><span class="sxs-lookup"><span data-stu-id="03a0b-134">Where does the interest code on a free text invoice come from?</span></span>
<span data-ttu-id="03a0b-135">Le code intérêt peut être défini sur le code facturation, la classification de facturation ou le profil de validation.</span><span class="sxs-lookup"><span data-stu-id="03a0b-135">The interest code can be set on the billing code, the billing classification, or the posting profile.</span></span>






