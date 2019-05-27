---
title: Numéros de facture et de document chronologiques pour la France
description: Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client pour les entités juridiques en France.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, NumberSequenceGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264514
ms.search.region: France
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eb28fb0baec5860482ec53a78ff92599cc2286d9
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537944"
---
# <a name="chronological-invoice-and-voucher-numbers-for-france"></a><span data-ttu-id="aeffc-103">Numéros de facture et de document chronologiques pour la France</span><span class="sxs-lookup"><span data-stu-id="aeffc-103">Chronological invoice and voucher numbers for France</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aeffc-104">Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client pour les entités juridiques en France.</span><span class="sxs-lookup"><span data-stu-id="aeffc-104">This topic explains how to set up and use chronological numbers for invoices and vouchers in Accounts receivable for legal entities in France.</span></span>  

<span data-ttu-id="aeffc-105">En France, il est obligatoire que toutes les factures et les documents associés émis soient numérotés dans l'ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="aeffc-105">In France, there is a legal requirement that all invoices and related vouchers that are issued be numbered in chronological order.</span></span> <span data-ttu-id="aeffc-106">La chronologie doit être prise en charge par les périodes fiscales.</span><span class="sxs-lookup"><span data-stu-id="aeffc-106">The chronology must be supported by fiscal periods.</span></span> <span data-ttu-id="aeffc-107">Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="aeffc-107">All the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="aeffc-108">Dans une période fiscale, l'ordre chronologique n'est pas obligatoire, mais il ne doit y avoir aucun écart dans la numérotation.</span><span class="sxs-lookup"><span data-stu-id="aeffc-108">Within one fiscal period, chronological order isn't mandatory, but there must be no gaps in the numbering.</span></span> <span data-ttu-id="aeffc-109">Pour répondre à cette exigence, la numérotation chronologique dans le module Comptabilité client affecte les documents suivants :</span><span class="sxs-lookup"><span data-stu-id="aeffc-109">To meet this requirement, chronological numbering in Accounts receivable affects the following documents:</span></span>

-   <span data-ttu-id="aeffc-110">Facture financière</span><span class="sxs-lookup"><span data-stu-id="aeffc-110">Free text invoice</span></span>
-   <span data-ttu-id="aeffc-111">N° document de facture financière</span><span class="sxs-lookup"><span data-stu-id="aeffc-111">Free text invoice voucher</span></span>
-   <span data-ttu-id="aeffc-112">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="aeffc-112">Free text credit note</span></span>
-   <span data-ttu-id="aeffc-113">N° document d'avoir financier</span><span class="sxs-lookup"><span data-stu-id="aeffc-113">Free text credit note voucher</span></span>
-   <span data-ttu-id="aeffc-114">Facture client</span><span class="sxs-lookup"><span data-stu-id="aeffc-114">Sales invoice</span></span>
-   <span data-ttu-id="aeffc-115">Document de facture client</span><span class="sxs-lookup"><span data-stu-id="aeffc-115">Sales invoice voucher</span></span>
-   <span data-ttu-id="aeffc-116">Avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="aeffc-116">Sales credit note</span></span>
-   <span data-ttu-id="aeffc-117">N° document d'avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="aeffc-117">Sales credit note voucher</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aeffc-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="aeffc-118">Prerequisites</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aeffc-119">Catégorie</span><span class="sxs-lookup"><span data-stu-id="aeffc-119">Category</span></span></th>
<th><span data-ttu-id="aeffc-120">Logiciel requis</span><span class="sxs-lookup"><span data-stu-id="aeffc-120">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aeffc-121">Pays/région</span><span class="sxs-lookup"><span data-stu-id="aeffc-121">Country/region</span></span></td>
<td><span data-ttu-id="aeffc-122">L'adresse principale de l'entité juridique doit être en France.</span><span class="sxs-lookup"><span data-stu-id="aeffc-122">The primary address of the legal entity must be in France.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aeffc-123">Tâches associées de paramétrage</span><span class="sxs-lookup"><span data-stu-id="aeffc-123">Related setup tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="aeffc-124">Dans la page <strong>Paramètres de la comptabilité client</strong>, sous l'onglet <strong>Mises à jour</strong>, définissez l'option <strong>Numérotation chronologique</strong> sur <strong>Oui</strong>.</span><span class="sxs-lookup"><span data-stu-id="aeffc-124">On the <strong>Accounts receivable parameters</strong> page, on the <strong>Updates</strong> tab, set the <strong>Chronological numbering</strong> option to <strong>Yes</strong>.</span></span></li>
<li><span data-ttu-id="aeffc-125">Dans la page <strong>Souches de numéros</strong>, définissez autant de souches de numéros qu'il est nécessaire pour couvrir les périodes fiscales affectées.</span><span class="sxs-lookup"><span data-stu-id="aeffc-125">On the <strong>Number sequences</strong> page, define as many number sequences as you require to cover the affected fiscal periods.</span></span> <span data-ttu-id="aeffc-126">Vous devez spécifier une société pour chaque souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="aeffc-126">You should specify a company for each number sequence.</span></span> <span data-ttu-id="aeffc-127">Les segments des souches de numéros doivent être définis de manière à fournir l'ordre chronologique des périodes.</span><span class="sxs-lookup"><span data-stu-id="aeffc-127">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="aeffc-128">Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="aeffc-128">For example, the segment names can contain a special prefix that identifies a specific period.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="set-up-chronological-numbering"></a><span data-ttu-id="aeffc-129">Paramétrer la numérotation chronologique</span><span class="sxs-lookup"><span data-stu-id="aeffc-129">Set up chronological numbering</span></span>
### <a name="accounts-receivable-parameters"></a><span data-ttu-id="aeffc-130">Paramètres de la comptabilité client</span><span class="sxs-lookup"><span data-stu-id="aeffc-130">Accounts receivable parameters</span></span>

<span data-ttu-id="aeffc-131">Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, par exemple **Facture financière**.</span><span class="sxs-lookup"><span data-stu-id="aeffc-131">On the **Accounts receivable parameters** page, on the **Number sequences** tab, select one of the supported references, such as **Free text invoice**.</span></span> <span data-ttu-id="aeffc-132">Cliquez ensuite sur le bouton **Paramétrage de la numérotation chronologique** qui sera disponible pour les références prises en charge.</span><span class="sxs-lookup"><span data-stu-id="aeffc-132">Then click the **Chronological numbering setup** button that will be available for the supported references.</span></span> <span data-ttu-id="aeffc-133">Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.</span><span class="sxs-lookup"><span data-stu-id="aeffc-133">On the **Chronological numbering setup** page, define the date-effective number sequences that have valid periods.</span></span>

### <a name="number-sequence-groups"></a><span data-ttu-id="aeffc-134">Groupes de souches de numéros</span><span class="sxs-lookup"><span data-stu-id="aeffc-134">Number sequence groups</span></span>

<span data-ttu-id="aeffc-135">Si différents clients utilisent différents modèles de numérotation, vous devez paramétrer la numérotation chronologique au niveau du groupe de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="aeffc-135">If different customers use different patterns for numbering, you must set up chronological numbering at the level of the number sequence group.</span></span> <span data-ttu-id="aeffc-136">Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, puis cliquez sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="aeffc-136">On the **Accounts receivable parameters** page, on the **Number sequences** tab, select one of the supported references, and then click **Group**.</span></span> <span data-ttu-id="aeffc-137">Dans la page **Groupe de souches de numéros**, sélectionnez un groupe existant ou créez-en un.</span><span class="sxs-lookup"><span data-stu-id="aeffc-137">On the **Number sequence group** page, select an existing group, or create a new group.</span></span> <span data-ttu-id="aeffc-138">Dans la section **Référence**, sélectionnez l'une des références prises en charge, puis cliquez sur **Paramétrage de la numérotation chronologique**.</span><span class="sxs-lookup"><span data-stu-id="aeffc-138">In the **Reference** section, select one of the supported references, and then click **Chronological numbering setup**.</span></span> <span data-ttu-id="aeffc-139">Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.</span><span class="sxs-lookup"><span data-stu-id="aeffc-139">On the **Chronological numbering setup** page, define date-effective number sequences that have valid periods.</span></span>

## <a name="invoice-posting"></a><span data-ttu-id="aeffc-140">Validation de facture</span><span class="sxs-lookup"><span data-stu-id="aeffc-140">Invoice posting</span></span>
<span data-ttu-id="aeffc-141">Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un numéro.</span><span class="sxs-lookup"><span data-stu-id="aeffc-141">When you post an invoice or a credit note, the appropriate number sequence is used to generate a number.</span></span> <span data-ttu-id="aeffc-142">Cette souche de numéros est sélectionnée selon la période valide contenant la date de la facture.</span><span class="sxs-lookup"><span data-stu-id="aeffc-142">This number sequence is selected based on the valid period that contains the invoice date.</span></span> <span data-ttu-id="aeffc-143">La numérotation chronologique spécifique au client a une priorité plus élevée que la numérotation chronologique.</span><span class="sxs-lookup"><span data-stu-id="aeffc-143">Customer-specific chronological numbering has higher priority than chronological numbering.</span></span>



