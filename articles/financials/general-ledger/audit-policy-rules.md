---
title: "Règles de stratégie d'audit"
description: "Les stratégies d'audit permettent d'évaluer la conformité des états de dépenses, factures fournisseur et commandes fournisseur avec les règles de stratégie que vous créez. Toutes les règles associées à une stratégie d'audit sont exécutées en mode de traitement par lots selon le programme que vous spécifiez.  Chaque règle de stratégie est une instance d'un type de règle de stratégie. Pour chaque type de règle de stratégie, une seule règle de stratégie peut être active à la fois."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6bebe9ce83c4b979ffbb7c86ef67ad03a650e0c2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="audit-policy-rules"></a><span data-ttu-id="f4c86-106">Règles de stratégie d'audit</span><span class="sxs-lookup"><span data-stu-id="f4c86-106">Audit policy rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4c86-107">Les stratégies d'audit permettent d'évaluer la conformité des états de dépenses, factures fournisseur et commandes fournisseur avec les règles de stratégie que vous créez.</span><span class="sxs-lookup"><span data-stu-id="f4c86-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="f4c86-108">Toutes les règles associées à une stratégie d'audit sont exécutées en mode de traitement par lots selon le programme que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="f4c86-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="f4c86-109">Chaque règle de stratégie est une instance d'un type de règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="f4c86-110">Pour chaque type de règle de stratégie, une seule règle de stratégie peut être active à la fois.</span><span class="sxs-lookup"><span data-stu-id="f4c86-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="f4c86-111">Requêtes et types de requêtes</span><span class="sxs-lookup"><span data-stu-id="f4c86-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="f4c86-112">Lorsque vous créez une règle de stratégie d'audit, vous commencez par sélectionner un type de règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="f4c86-113">Celui-ci spécifie la requête AOA (arbre d'objets d'application) à utiliser comme point de départ pour créer la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="f4c86-114">Il spécifie également le type de requête à utiliser pour la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="f4c86-115">La requête détermine le document source évalué par la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="f4c86-116">Elle spécifie également les champs dans le document source qui identifient l'entité juridique et la date à utiliser lors de la sélection de documents pour audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="f4c86-117">Le type de requête contrôle les champs par défaut dans la page de requête et dans la page Règle de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="f4c86-118">Le tableau suivant indique les types de requêtes disponibles pour les règles de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4c86-119">Type de requête</span><span class="sxs-lookup"><span data-stu-id="f4c86-119">Query type</span></span></th>
<th><span data-ttu-id="f4c86-120">Objectif</span><span class="sxs-lookup"><span data-stu-id="f4c86-120">Purpose</span></span></th>
<th><span data-ttu-id="f4c86-121">Plus d'informations</span><span class="sxs-lookup"><span data-stu-id="f4c86-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f4c86-122">Conditionnelle</span><span class="sxs-lookup"><span data-stu-id="f4c86-122">Conditional</span></span></td>
<td><span data-ttu-id="f4c86-123">Permet d'évaluer les attributs de document source par rapport à des valeurs spécifiées.</span><span class="sxs-lookup"><span data-stu-id="f4c86-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f4c86-124">Regroupement</span><span class="sxs-lookup"><span data-stu-id="f4c86-124">Aggregate</span></span></td>
<td><span data-ttu-id="f4c86-125">Permet d'évaluer plusieurs documents sources ou lignes de document source par rapport à une règle de stratégie via le regroupement de valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="f4c86-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f4c86-126">Échantillonnage</span><span class="sxs-lookup"><span data-stu-id="f4c86-126">Sampling</span></span></td>
<td><span data-ttu-id="f4c86-127">Permet d'évaluer un pourcentage spécifié de documents sources sélectionnés au hasard en relation avec les violations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="f4c86-128">Lorsque vous sélectionnez cette option, utilisez la page Règle de stratégie d'audit pour spécifier le pourcentage de documents à sélectionner au hasard pour l'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f4c86-129">Doublon</span><span class="sxs-lookup"><span data-stu-id="f4c86-129">Duplicate</span></span></td>
<td><span data-ttu-id="f4c86-130">Permet d'évaluer des documents sources afin de déterminer s'ils contiennent des entrées en double dans des champs spécifiés.</span><span class="sxs-lookup"><span data-stu-id="f4c86-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="f4c86-131">Lorsque vous sélectionnez cette option, utilisez la page Règle de stratégie d'audit pour spécifier le nombre de jours que vous souhaitez ajouter au début de la plage de dates de sélection de documents dans le cadre de l'évaluation des documents en relation avec les entrées en double.</span><span class="sxs-lookup"><span data-stu-id="f4c86-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f4c86-132">Recherche de liste</span><span class="sxs-lookup"><span data-stu-id="f4c86-132">List search</span></span></td>
<td><span data-ttu-id="f4c86-133">Permet d'évaluer les documents sources pour des entités spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f4c86-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="f4c86-134">Le document racine de la requête définit le document en cours d'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="f4c86-135">La requête doit être une requête de liste qui inclut une référence à la table DirPartyTable.</span><span class="sxs-lookup"><span data-stu-id="f4c86-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="f4c86-136">Cette option peut être utilisée uniquement avec les requêtes AOA suivantes :</span><span class="sxs-lookup"><span data-stu-id="f4c86-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="f4c86-137"><span class="ui">AuditPolicyExpenseList</span> (États de dépenses au niveau des employés)</span><span class="sxs-lookup"><span data-stu-id="f4c86-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="f4c86-138"><span class="ui">AuditPolicyPurchList</span> (Commandes fournisseur au niveau des fournisseurs)</span><span class="sxs-lookup"><span data-stu-id="f4c86-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="f4c86-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Facture fournisseur au niveau des fournisseurs)</span><span class="sxs-lookup"><span data-stu-id="f4c86-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="f4c86-140">Lorsque vous sélectionnez cette option, spécifiez les entités contrôlées dans la page Règle de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f4c86-141">Recherche de mots-clés</span><span class="sxs-lookup"><span data-stu-id="f4c86-141">Keyword search</span></span></td>
<td><span data-ttu-id="f4c86-142">Permet d'évaluer les documents sources pour déterminer s'ils contiennent certains mots.</span><span class="sxs-lookup"><span data-stu-id="f4c86-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="f4c86-143">Lorsque vous sélectionnez cette option, entrez les mots à rechercher dans la page Règle de stratégie d'audit.</span><span class="sxs-lookup"><span data-stu-id="f4c86-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="f4c86-144">La page Règle de stratégie d'audit inclut des options qui vous permettent de spécifier les tables et champs à évaluer en relation avec les mots que vous avez entrés.</span><span class="sxs-lookup"><span data-stu-id="f4c86-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="f4c86-145">Paramètres courants</span><span class="sxs-lookup"><span data-stu-id="f4c86-145">Common parameters</span></span>
<span data-ttu-id="f4c86-146">L'ensemble des règles de stratégie pour une stratégie d'audit spécifique partagent les mêmes paramètres de lot et la même plage de dates de sélection de documents.</span><span class="sxs-lookup"><span data-stu-id="f4c86-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="f4c86-147">Ces paramètres sont spécifiés dans la page Options supplémentaires pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f4c86-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="additional-resources"></a><span data-ttu-id="f4c86-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f4c86-148">Additional resources</span></span>
--------

<span data-ttu-id="f4c86-149">[Violations et incidents de stratégie d'audit](audit-policy-violations-cases.md)
[Définir des stratégies d'audit pour les documents source](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="f4c86-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



