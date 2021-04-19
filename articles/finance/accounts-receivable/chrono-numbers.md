---
title: Numérotation chronologique des documents et des justificatifs
description: Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les documents applicables et les justificatifs associés.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: fe533052b0e5b04a7d27b954ba644761c631d6d7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838859"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="93440-103">Numérotation chronologique des documents et des justificatifs</span><span class="sxs-lookup"><span data-stu-id="93440-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="93440-104">Dans certains pays, il est obligatoire de numéroter les documents et les justificatifs associés dans l’ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="93440-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="93440-105">La chronologie doit être prise en charge par périodes.</span><span class="sxs-lookup"><span data-stu-id="93440-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="93440-106">Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="93440-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="93440-107">Pour répondre à cette exigence, une fonctionnalité de numérotation chronologique a été implémentée.</span><span class="sxs-lookup"><span data-stu-id="93440-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="93440-108">Cette rubrique explique comment configurer et utiliser des numéros chronologiques pour les documents applicables et les justificatifs associés.</span><span class="sxs-lookup"><span data-stu-id="93440-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93440-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="93440-109">Prerequisites</span></span>

<span data-ttu-id="93440-110">Dans l’espace de travail Gestion des fonctionnalités, activez la fonctionnalité **Numérotation chronologique**.</span><span class="sxs-lookup"><span data-stu-id="93440-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="93440-111">Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="93440-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="93440-112">Configurer la numérotation chronologique</span><span class="sxs-lookup"><span data-stu-id="93440-112">Configure chronological numbering</span></span>

<span data-ttu-id="93440-113">La numérotation chronologique affecte les documents suivants.</span><span class="sxs-lookup"><span data-stu-id="93440-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="93440-114">**Comptabilité client**</span><span class="sxs-lookup"><span data-stu-id="93440-114">**Accounts receivable**</span></span>
- <span data-ttu-id="93440-115">Facture client</span><span class="sxs-lookup"><span data-stu-id="93440-115">Customer invoice</span></span>
- <span data-ttu-id="93440-116">N° document de facture client</span><span class="sxs-lookup"><span data-stu-id="93440-116">Customer invoice voucher</span></span>
- <span data-ttu-id="93440-117">Avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="93440-117">Sales credit note</span></span>
- <span data-ttu-id="93440-118">N° document d’avoir sur vente</span><span class="sxs-lookup"><span data-stu-id="93440-118">Sales credit note voucher</span></span>
- <span data-ttu-id="93440-119">Facture financière</span><span class="sxs-lookup"><span data-stu-id="93440-119">Free text invoice</span></span>
- <span data-ttu-id="93440-120">N° document de facture financière</span><span class="sxs-lookup"><span data-stu-id="93440-120">Free text invoice voucher</span></span>
- <span data-ttu-id="93440-121">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="93440-121">Free text credit note</span></span>
- <span data-ttu-id="93440-122">N° document d’avoir financier</span><span class="sxs-lookup"><span data-stu-id="93440-122">Free text credit note voucher</span></span>
- <span data-ttu-id="93440-123">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="93440-123">Packing slip</span></span>
- <span data-ttu-id="93440-124">N° document de bon de livraison</span><span class="sxs-lookup"><span data-stu-id="93440-124">Packing slip voucher</span></span>
- <span data-ttu-id="93440-125">Document de correction du bon de livraison</span><span class="sxs-lookup"><span data-stu-id="93440-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="93440-126">N° document de note d’intérêt</span><span class="sxs-lookup"><span data-stu-id="93440-126">Interest note voucher</span></span>
- <span data-ttu-id="93440-127">N° document de lettre de relance</span><span class="sxs-lookup"><span data-stu-id="93440-127">Collection letter voucher</span></span>

<span data-ttu-id="93440-128">**Comptabilité fournisseur**</span><span class="sxs-lookup"><span data-stu-id="93440-128">**Accounts payable**</span></span>
- <span data-ttu-id="93440-129">N° document de facture</span><span class="sxs-lookup"><span data-stu-id="93440-129">Invoice voucher</span></span>
- <span data-ttu-id="93440-130">N° document d’avoir</span><span class="sxs-lookup"><span data-stu-id="93440-130">Credit note voucher</span></span>
- <span data-ttu-id="93440-131">N° document d’accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="93440-131">Product receipt voucher</span></span>

<span data-ttu-id="93440-132">**Gestion de projets**</span><span class="sxs-lookup"><span data-stu-id="93440-132">**Project management**</span></span>
- <span data-ttu-id="93440-133">Facture</span><span class="sxs-lookup"><span data-stu-id="93440-133">Invoice</span></span>
- <span data-ttu-id="93440-134">N° document de facture</span><span class="sxs-lookup"><span data-stu-id="93440-134">Invoice voucher</span></span>
- <span data-ttu-id="93440-135">Avoir</span><span class="sxs-lookup"><span data-stu-id="93440-135">Credit note</span></span>
- <span data-ttu-id="93440-136">N° document d’avoir</span><span class="sxs-lookup"><span data-stu-id="93440-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="93440-137">Définir des souches de numéros</span><span class="sxs-lookup"><span data-stu-id="93440-137">Define number sequences</span></span>

<span data-ttu-id="93440-138">Pour définir des souches de numéros, accédez à **Administration d’organisation** > **Souches de numéros** > **Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="93440-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="93440-139">Vous pouvez définir autant de souches de numéros que nécessaire pour couvrir les périodes concernées pour les documents requis.</span><span class="sxs-lookup"><span data-stu-id="93440-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="93440-140">Spécifiez une société pour chaque souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="93440-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="93440-141">Les segments des souches de numéros doivent être définis de manière à fournir l’ordre chronologique des périodes.</span><span class="sxs-lookup"><span data-stu-id="93440-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="93440-142">Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="93440-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Paramètres des séquences de numéros](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="93440-144">Configurer des groupes de souches de numéros</span><span class="sxs-lookup"><span data-stu-id="93440-144">Configure number sequence groups</span></span>

<span data-ttu-id="93440-145">Pour configurer des groupes de souches de numéros, accédez à **Comptabilité client** > **Paramétrage** > **Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="93440-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="93440-146">Dans l’onglet **Souches de numéros**, définissez autant de groupes de souches de numéros qu’il est nécessaire pour couvrir les périodes affectées.</span><span class="sxs-lookup"><span data-stu-id="93440-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="93440-147">Pour chaque groupe, dans la section **Référence**, sélectionnez l’une des références de document prises en charge et dans le champ **Code souche de numéros**, référez-vous à une souche de numéros qui a été précédemment créée pour la période concernée.</span><span class="sxs-lookup"><span data-stu-id="93440-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Paramétrage du groupe souche de numéros](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="93440-149">De même, configurez les groupes de souches de numéros dans les modules **Comptabilité fournisseur** et **Gestion et comptabilité du projet**.</span><span class="sxs-lookup"><span data-stu-id="93440-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="93440-150">Configurer la chronologie des groupes de souches de numéros</span><span class="sxs-lookup"><span data-stu-id="93440-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="93440-151">Pour configurer la chronologie des groupes de souches de numéros, accédez à **Administration d’organisation** > **Souches de numéros** > **Groupes de souches de numéros chronologiques**.</span><span class="sxs-lookup"><span data-stu-id="93440-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="93440-152">Définissez les conditions d’applicabilité des groupes de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="93440-152">Define the applicability conditions for number sequence groups.</span></span>

![Paramétrage des numéros chronologiques](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="93440-154">Champ</span><span class="sxs-lookup"><span data-stu-id="93440-154">Field</span></span>            | <span data-ttu-id="93440-155">Description</span><span class="sxs-lookup"><span data-stu-id="93440-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="93440-156">Date d’effet</span><span class="sxs-lookup"><span data-stu-id="93440-156">Effective</span></span>  | <span data-ttu-id="93440-157">La date de début de l’applicabilité du groupe de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="93440-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="93440-158">Expiration</span><span class="sxs-lookup"><span data-stu-id="93440-158">Expiration</span></span>      | <span data-ttu-id="93440-159">La date de fin de l’applicabilité du groupe de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="93440-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="93440-160">Si aucune date de fin n’est appliquée, sélectionnez **Jamais**.</span><span class="sxs-lookup"><span data-stu-id="93440-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="93440-161">Groupe souche de numéros</span><span class="sxs-lookup"><span data-stu-id="93440-161">Number sequence group</span></span> | <span data-ttu-id="93440-162">Groupe de souches de numéros qui sera utilisé pour générer des numéros de document pendant la période.</span><span class="sxs-lookup"><span data-stu-id="93440-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="93440-163">Groupe de souches de numéros d’origine</span><span class="sxs-lookup"><span data-stu-id="93440-163">Original number sequence group</span></span> | <span data-ttu-id="93440-164">Ce code de groupe de souches de numéros est utilisé pour un filtrage supplémentaire si les documents ont déjà un groupe de souches de numéros *permanent* attribué.</span><span class="sxs-lookup"><span data-stu-id="93440-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="93440-165">Une valeur vide est considérée comme une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="93440-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="93440-166">Si vous devez ignorer un groupe attribué au préalable, utilisez l’option **Par défaut** pour ce paramétrage.</span><span class="sxs-lookup"><span data-stu-id="93440-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="93440-167">Par défaut</span><span class="sxs-lookup"><span data-stu-id="93440-167">Default</span></span> | <span data-ttu-id="93440-168">Si cette option est activée, le système ignore le groupe de souches de numéros attribué au préalable et utilise uniquement les dates de début et de fin des périodes pour l’analyse d’applicabilité.</span><span class="sxs-lookup"><span data-stu-id="93440-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="93440-169">Si elle est désactivée, le système utilise la combinaison complète **Date d’effet** + **Expiration** + **Groupe de souches de numéros d’origine** pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="93440-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="93440-170">Validation de document</span><span class="sxs-lookup"><span data-stu-id="93440-170">Document posting</span></span>
<span data-ttu-id="93440-171">Lorsque vous validez un document, le groupe de souches de numéros d’origine approprié lui est affecté, en fonction de la date de validation du document, puis utilisé pour générer un numéro de document en fonction de la souche de numéros détectée.</span><span class="sxs-lookup"><span data-stu-id="93440-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="93440-172">Le système fournit un message concernant l’affectation des groupes de souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="93440-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Numéro de référence](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="93440-174">Pour certains pays, il existe déjà une logique spécifique pour la numérotation des documents.</span><span class="sxs-lookup"><span data-stu-id="93440-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="93440-175">Dans ce cas, la logique propre au pays remplacera la fonctionnalité **Numérotation chronologique**.</span><span class="sxs-lookup"><span data-stu-id="93440-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
