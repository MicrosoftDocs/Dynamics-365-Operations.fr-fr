---
title: Facture et n° document chronologiques
description: Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264514
ms.search.region: France
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5e18dbb9684e9916e86b5b8a8a5b7d6cbe2f49ee
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915261"
---
# <a name="chronological-invoice-and-voucher-numbers"></a><span data-ttu-id="f4373-103">Facture et n° document chronologiques</span><span class="sxs-lookup"><span data-stu-id="f4373-103">Chronological invoice and voucher numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4373-104">Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="f4373-104">This topic explains how to set up and use chronological numbers for invoices and vouchers in Accounts receivable.</span></span>  

<span data-ttu-id="f4373-105">Dans certains pays, il est obligatoire que toutes les factures et les documents associés émis soient numérotés dans l'ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="f4373-105">In some countries, there is a legal requirement that all invoices and related vouchers that are issued be numbered in chronological order.</span></span> <span data-ttu-id="f4373-106">La chronologie doit être prise en charge par les périodes fiscales.</span><span class="sxs-lookup"><span data-stu-id="f4373-106">The chronology must be supported by fiscal periods.</span></span> <span data-ttu-id="f4373-107">Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f4373-107">All the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="f4373-108">Dans une période fiscale, l'ordre chronologique n'est pas obligatoire, mais il ne doit y avoir aucun écart dans la numérotation.</span><span class="sxs-lookup"><span data-stu-id="f4373-108">Within one fiscal period, chronological order isn't mandatory, but there must be no gaps in the numbering.</span></span> <span data-ttu-id="f4373-109">Pour répondre à cette exigence, la numérotation chronologique dans le module Comptabilité client affecte les documents suivants :</span><span class="sxs-lookup"><span data-stu-id="f4373-109">To meet this requirement, chronological numbering in Accounts receivable affects the following documents:</span></span>

-   <span data-ttu-id="f4373-110">Facture financière</span><span class="sxs-lookup"><span data-stu-id="f4373-110">Free text invoice</span></span>
-   <span data-ttu-id="f4373-111">N° document de facture financière</span><span class="sxs-lookup"><span data-stu-id="f4373-111">Free text invoice voucher</span></span>
-   <span data-ttu-id="f4373-112">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="f4373-112">Free text credit note</span></span>
-   <span data-ttu-id="f4373-113">N° document d'avoir financier</span><span class="sxs-lookup"><span data-stu-id="f4373-113">Free text credit note voucher</span></span>
-   <span data-ttu-id="f4373-114">Facture client</span><span class="sxs-lookup"><span data-stu-id="f4373-114">Sales invoice</span></span>
-   <span data-ttu-id="f4373-115">Document de facture client</span><span class="sxs-lookup"><span data-stu-id="f4373-115">Sales invoice voucher</span></span>
-   <span data-ttu-id="f4373-116">Avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="f4373-116">Sales credit note</span></span>
-   <span data-ttu-id="f4373-117">N° document d'avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="f4373-117">Sales credit note voucher</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4373-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f4373-118">Prerequisites</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4373-119">Catégorie</span><span class="sxs-lookup"><span data-stu-id="f4373-119">Category</span></span></th>
<th><span data-ttu-id="f4373-120">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="f4373-120">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f4373-121">Activation des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="f4373-121">Feature activation</span></span></td>
<td><span data-ttu-id="f4373-122">Dans l'espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Numérotation chronologique**.</span><span class="sxs-lookup"><span data-stu-id="f4373-122">In the **Feature management** workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="f4373-123">Pour plus d'informations, voir [Vue d'ensemble de la gestion des fonctionnalités](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4373-123">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f4373-124">Pays/région</span><span class="sxs-lookup"><span data-stu-id="f4373-124">Country/region</span></span></td>
<td><span data-ttu-id="f4373-125">Si l'adresse principale de l'entité juridique est en <strong>France</strong>, définissez également l'option <strong>Numérotation chronologique</strong> sur <strong>Oui</strong> sur la page <strong>Paramètres de la comptabilité client</strong> sous l'onglet <strong>Mises à jour</strong>.</span><span class="sxs-lookup"><span data-stu-id="f4373-125">If the primary address of the legal entity is in <strong>France</strong> then additionally set the <strong>Chronological numbering</strong> option to <strong>Yes</strong> on the <strong>Accounts receivable parameters</strong> page, on the <strong>Updates</strong> tab.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f4373-126">Tâches associées de paramétrage</span><span class="sxs-lookup"><span data-stu-id="f4373-126">Related setup tasks</span></span></td>
<td><span data-ttu-id="f4373-127">Dans la page <strong>Souches de numéros</strong>, définissez autant de souches de numéros qu'il est nécessaire pour couvrir les périodes fiscales affectées.</span><span class="sxs-lookup"><span data-stu-id="f4373-127">On the <strong>Number sequences</strong> page, define as many number sequences as you require to cover the affected fiscal periods.</span></span> <span data-ttu-id="f4373-128">Vous devez spécifier une société pour chaque souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="f4373-128">You should specify a company for each number sequence.</span></span> <span data-ttu-id="f4373-129">Les segments des souches de numéros doivent être définis de manière à fournir l'ordre chronologique des périodes.</span><span class="sxs-lookup"><span data-stu-id="f4373-129">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="f4373-130">Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="f4373-130">For example, the segment names can contain a special prefix that identifies a specific period.</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-chronological-numbering"></a><span data-ttu-id="f4373-131">Paramétrer la numérotation chronologique</span><span class="sxs-lookup"><span data-stu-id="f4373-131">Set up chronological numbering</span></span>
### <a name="accounts-receivable-parameters"></a><span data-ttu-id="f4373-132">Paramètres de la comptabilité client</span><span class="sxs-lookup"><span data-stu-id="f4373-132">Accounts receivable parameters</span></span>

<span data-ttu-id="f4373-133">Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, par exemple **Facture financière**.</span><span class="sxs-lookup"><span data-stu-id="f4373-133">On the **Accounts receivable parameters** page, on the **Number sequences** tab, select one of the supported references, such as **Free text invoice**.</span></span> <span data-ttu-id="f4373-134">Cliquez ensuite sur le bouton **Paramétrage de la numérotation chronologique** qui sera disponible pour les références prises en charge.</span><span class="sxs-lookup"><span data-stu-id="f4373-134">Then click the **Chronological numbering setup** button that will be available for the supported references.</span></span> <span data-ttu-id="f4373-135">Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.</span><span class="sxs-lookup"><span data-stu-id="f4373-135">On the **Chronological numbering setup** page, define the date-effective number sequences that have valid periods.</span></span>

![Paramétrage des numéros chronologiques](media/emea-chronological-numbering.jpg)

### <a name="number-sequence-groups"></a><span data-ttu-id="f4373-137">Groupes de souches de numéros</span><span class="sxs-lookup"><span data-stu-id="f4373-137">Number sequence groups</span></span>

<span data-ttu-id="f4373-138">Si différents clients utilisent différents modèles de numérotation, vous devez paramétrer la numérotation chronologique au niveau du groupe de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="f4373-138">If different customers use different patterns for numbering, you must set up chronological numbering at the level of the number sequence group.</span></span> <span data-ttu-id="f4373-139">Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, puis cliquez sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="f4373-139">On the **Accounts receivable parameters** page, on the **Number sequences** tab, select one of the supported references, and then click **Group**.</span></span> <span data-ttu-id="f4373-140">Dans la page **Groupe de souches de numéros**, sélectionnez un groupe existant ou créez-en un.</span><span class="sxs-lookup"><span data-stu-id="f4373-140">On the **Number sequence group** page, select an existing group, or create a new group.</span></span> <span data-ttu-id="f4373-141">Dans la section **Référence**, sélectionnez l'une des références prises en charge, puis cliquez sur **Paramétrage de la numérotation chronologique**.</span><span class="sxs-lookup"><span data-stu-id="f4373-141">In the **Reference** section, select one of the supported references, and then click **Chronological numbering setup**.</span></span> <span data-ttu-id="f4373-142">Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.</span><span class="sxs-lookup"><span data-stu-id="f4373-142">On the **Chronological numbering setup** page, define date-effective number sequences that have valid periods.</span></span>

## <a name="invoice-posting"></a><span data-ttu-id="f4373-143">Validation de facture</span><span class="sxs-lookup"><span data-stu-id="f4373-143">Invoice posting</span></span>
<span data-ttu-id="f4373-144">Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un numéro.</span><span class="sxs-lookup"><span data-stu-id="f4373-144">When you post an invoice or a credit note, the appropriate number sequence is used to generate a number.</span></span> <span data-ttu-id="f4373-145">Cette souche de numéros est sélectionnée selon la période valide contenant la date de la facture.</span><span class="sxs-lookup"><span data-stu-id="f4373-145">This number sequence is selected based on the valid period that contains the invoice date.</span></span> <span data-ttu-id="f4373-146">La numérotation chronologique spécifique au client a une priorité plus élevée que la numérotation chronologique.</span><span class="sxs-lookup"><span data-stu-id="f4373-146">Customer-specific chronological numbering has higher priority than chronological numbering.</span></span>

### <a name="dates-control"></a><span data-ttu-id="f4373-147">Contrôle des dates</span><span class="sxs-lookup"><span data-stu-id="f4373-147">Dates control</span></span>

<span data-ttu-id="f4373-148">Le système effectue un contrôle supplémentaire des dates de factures pour les factures clients :</span><span class="sxs-lookup"><span data-stu-id="f4373-148">The system performs an additional invoice dates control for customer invoices:</span></span> 

- <span data-ttu-id="f4373-149">La validation de nouvelles factures avec des dates antérieures à la date de la dernière facture validée est interdite si aucun code motif n'est défini.</span><span class="sxs-lookup"><span data-stu-id="f4373-149">Posting new invoices with dates earlier than the date of the latest posted invoice is forbidden if no reason code is defined.</span></span> <span data-ttu-id="f4373-150">Pour activer la validation, un code motif doit être saisi soit dans un en-tête de facture/commande, soit dans l'une des lignes.</span><span class="sxs-lookup"><span data-stu-id="f4373-150">To enable posting, a reason code must be entered either in an invoice/order header or in one of the lines.</span></span>
- <span data-ttu-id="f4373-151">Un avertissement est émis si la nouvelle date de facturation est postérieure à la date système.</span><span class="sxs-lookup"><span data-stu-id="f4373-151">A warning is raised if the new invoice date is later than the system date.</span></span>
