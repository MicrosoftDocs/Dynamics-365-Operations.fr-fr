---
title: "Violations et incidents de stratégie d'audit"
description: "Cet article décrit la manière dont les incident d'audit sont générés à la suite de violations des règles de stratégie d'audit. Il inclut également des informations sur les différentes manières dont les stratégies d'audit utilisent la plage de dates de sélection de document."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 24ee0dbf01208f8decc167e11e84191eaae03edf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="41d33-104">Violations et incidents de stratégie d'audit</span><span class="sxs-lookup"><span data-stu-id="41d33-104">Audit policy violations and cases</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="41d33-105">Cet article décrit la manière dont les incident d'audit sont générés à la suite de violations des règles de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="41d33-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="41d33-106">Il inclut également des informations sur les différentes manières dont les stratégies d'audit utilisent la plage de dates de sélection de document.</span><span class="sxs-lookup"><span data-stu-id="41d33-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="41d33-107">Génération des incidents d'audit</span><span class="sxs-lookup"><span data-stu-id="41d33-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="41d33-108">Les stratégies d'audit permettent d'identifier les états de dépenses, commandes fournisseur et factures fournisseur non conformes aux règles métier définies et configurées en tant que règles de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="41d33-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="41d33-109">Les stratégies d'audit sont exécutées en mode de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="41d33-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="41d33-110">Lorsque vous exécutez une stratégie d'audit, toutes les règles de stratégie qui lui appartiennent sont exécutées simultanément.</span><span class="sxs-lookup"><span data-stu-id="41d33-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="41d33-111">Chaque règle de stratégie évalue un ensemble de documents.</span><span class="sxs-lookup"><span data-stu-id="41d33-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="41d33-112">La règle de stratégie sélectionne des documents compris dans la plage de dates de sélection des documents et qui correspondent aux critères spécifiés.</span><span class="sxs-lookup"><span data-stu-id="41d33-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="41d33-113">Par exemple, une règle de stratégie peut sélectionner les états de dépenses dont le prix des repas est supérieur à 50,00.</span><span class="sxs-lookup"><span data-stu-id="41d33-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="41d33-114">Une autre règle de stratégie peut sélectionner les factures fournisseur payables à un fournisseur spécifique.</span><span class="sxs-lookup"><span data-stu-id="41d33-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="41d33-115">Pour chaque document sélectionné dans l'ensemble, une violation est générée.</span><span class="sxs-lookup"><span data-stu-id="41d33-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="41d33-116">Cette violation correspond à un enregistrement qui indique qu'un document particulier, tel que la facture 12345, n'est pas conforme à la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="41d33-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="41d33-117">Plusieurs enregistrements de violation d'audit sont regroupés et associés aux demandes de devis d'audit.</span><span class="sxs-lookup"><span data-stu-id="41d33-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="41d33-118">Par défaut, les incidents de chaque stratégie d'audit sont regroupés par règle de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="41d33-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="41d33-119">Si vous le souhaitez, vous pouvez sélectionner d'autres critères de regroupement à l'aide de la page **Critères de regroupement des incidents**.</span><span class="sxs-lookup"><span data-stu-id="41d33-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="41d33-120">Par exemple, vous pouvez regrouper les en-têtes de dépenses par ID projet et les factures fournisseur par compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="41d33-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="41d33-121">Dans ce cas, toutes les violations d'en-tête de dépenses avec le même ID projet sont regroupées dans le même incident, et toutes les factures fournisseur avec le même compte fournisseur sont regroupées dans le même incident.</span><span class="sxs-lookup"><span data-stu-id="41d33-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="41d33-122">Pour les règles de stratégie d'audit basées sur le type de requête **Doublon**, les violations ne sont pas regroupées par règle de stratégie ou en fonction des critères spécifiés dans la page **Critères de regroupement des incidents**.</span><span class="sxs-lookup"><span data-stu-id="41d33-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="41d33-123">Au lieu de cela, elles sont regroupées par les critères indiqués dans la règle de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="41d33-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="41d33-124">Par exemple, si une règle de stratégie recherche dans les états de dépenses les dépenses en double possédant les mêmes montants, ID marchand et dates, toutes les dépenses dont les champs spécifient des valeurs identiques constituent un incident.</span><span class="sxs-lookup"><span data-stu-id="41d33-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="41d33-125">Toutes les dépenses qui ont des valeurs différentes font partie d'un incident distinct.</span><span class="sxs-lookup"><span data-stu-id="41d33-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="41d33-126">Une fois les incidents d'audit générés, ils sont gérés à l'aide des processus habituels de gestion des incidents.</span><span class="sxs-lookup"><span data-stu-id="41d33-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="41d33-127">Plages de dates de sélection des documents</span><span class="sxs-lookup"><span data-stu-id="41d33-127">Document selection date ranges</span></span>
<span data-ttu-id="41d33-128">Lorsqu'une stratégie d'audit est exécutée, chaque règle de stratégie sélectionne les documents du type indiqué dont la date est comprise dans la plage de dates de sélection des documents.</span><span class="sxs-lookup"><span data-stu-id="41d33-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="41d33-129">La plage de dates de sélection des documents est spécifiée dans la page **Options supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="41d33-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="41d33-130">De nombreux documents sont associés à plusieurs dates.</span><span class="sxs-lookup"><span data-stu-id="41d33-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="41d33-131">Le champ Date utilisé par la règle de stratégie d'audit est spécifié dans la page **Type de règle de stratégie**.</span><span class="sxs-lookup"><span data-stu-id="41d33-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="41d33-132">Voici quelques autres manières dont une stratégie d'audit utilise la plage de dates de sélection des documents :</span><span class="sxs-lookup"><span data-stu-id="41d33-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="41d33-133">La stratégie utilise la version de chaque règle de stratégie effective le dernier jour de la plage de dates de sélection des documents.</span><span class="sxs-lookup"><span data-stu-id="41d33-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="41d33-134">Vous pouvez voir les dates d'effet de chaque règle de stratégie dans la page de liste **Stratégies d'audit**.</span><span class="sxs-lookup"><span data-stu-id="41d33-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="41d33-135">La stratégie utilise les nœuds d'organisation qui sont associés à la stratégie le dernier jour de la plage de dates de sélection des documents.</span><span class="sxs-lookup"><span data-stu-id="41d33-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="41d33-136">Seuls les nœuds d'organisation actuellement associés à la stratégie s'affichent dans la page de liste **Stratégies d'audit**.</span><span class="sxs-lookup"><span data-stu-id="41d33-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="41d33-137">Pour les règles de stratégie basées sur un type de requête **Recherche de liste**, la stratégie évalue les documents pour des entités contrôlées qui sont effectives le dernier jour de la plage de dates de sélection des documents.</span><span class="sxs-lookup"><span data-stu-id="41d33-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="41d33-138">Pour plus d'informations, voir [Règles de stratégie d'audit](audit-policy-rules.md)</span><span class="sxs-lookup"><span data-stu-id="41d33-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>




