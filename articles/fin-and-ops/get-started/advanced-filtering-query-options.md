---
title: "Syntaxe de requête et de filtrage avancé"
description: "Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez l'opérateur de correspondances dans la boîte de dialogue Filtre/tri avancé."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 616366009ce7bf7135704e980becc331617cf5af
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="2b3f7-103">Syntaxe de requête et de filtrage avancé</span><span class="sxs-lookup"><span data-stu-id="2b3f7-103">Advanced filtering and query syntax</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2b3f7-104">Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez l'opérateur de correspondances dans la boîte de dialogue Filtre/tri avancé.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-104">This article describes the filtering and query options that are available when you use the "matches" operator in the Advanced filter/sort dialog.</span></span>

<a name="advanced-query-syntax"></a><span data-ttu-id="2b3f7-105">Syntaxe de requête avancée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-105">Advanced query syntax</span></span>
---------------------

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b3f7-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2b3f7-106">Syntax</span></span></th>
<th><span data-ttu-id="2b3f7-107">Description du caractère</span><span class="sxs-lookup"><span data-stu-id="2b3f7-107">Character description</span></span></th>
<th><span data-ttu-id="2b3f7-108">description ;</span><span class="sxs-lookup"><span data-stu-id="2b3f7-108">Description</span></span></th>
<th><span data-ttu-id="2b3f7-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="2b3f7-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2b3f7-110"><em>valeur</em></span><span class="sxs-lookup"><span data-stu-id="2b3f7-110"><em>value</em></span></span></td>
<td><span data-ttu-id="2b3f7-111">Égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-112">Tapez la valeur à rechercher.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="2b3f7-113"><strong>Smith</strong> permet de rechercher &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-114">!<em>valeur</em> (point d'exclamation)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="2b3f7-115">Pas égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-116">Tapez un point d'exclamation, puis la valeur à exclure.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="2b3f7-117"><strong>!Smith</strong> permet de rechercher toutes les valeurs sauf &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-118"><em>valeur de début</em>..<em>valeur de fin</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="2b3f7-119">Entre les deux valeurs séparées par deux points</span><span class="sxs-lookup"><span data-stu-id="2b3f7-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="2b3f7-120">Tapez la valeur de début, puis deux points, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="2b3f7-121"><strong>1..10</strong> permet de rechercher toutes les valeurs de 1 à 10.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="2b3f7-122">Cependant, dans un champ de chaîne, <strong>A..C</strong> permet de trouver toutes les valeurs commençant par &quot;A&quot; et &quot;B&quot; et les valeurs exactement égales à &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="2b3f7-123">Par exemple, cette requête ne recherche pas &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="2b3f7-124">Pour rechercher toutes les valeurs de &quot;A*&quot; à &quot;C*&quot;,tapez <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-124">To find all values from &quot;A*&quot; through &quot;C*&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-125">..<em>valeur</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="2b3f7-126">Inférieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-127">Tapez deux points, puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="2b3f7-128"><strong>..1 000</strong> permet de rechercher les nombres inférieurs ou égaux à 1 000, par exemple &quot;100&quot;, &quot;999,95&quot; et &quot;1 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-129"><em>valeur</em>..</span><span class="sxs-lookup"><span data-stu-id="2b3f7-129"><em>value</em>..</span></span> <span data-ttu-id="2b3f7-130">(deux points)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-130">(double period)</span></span></td>
<td><span data-ttu-id="2b3f7-131">Supérieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-132">Tapez la valeur, puis deux points.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="2b3f7-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="2b3f7-133"><strong>1000..</strong></span></span> <span data-ttu-id="2b3f7-134">permet de rechercher les nombres supérieurs ou égaux à 1 000, par exemple &quot;1 000&quot;, &quot;1 000,01&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-135">&gt;<em>valeur</em> (signe « supérieur à »)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="2b3f7-136">Supérieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-137">Tapez le signe « supérieur à » (<strong>&gt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="2b3f7-138"><strong>&gt;1 000</strong> permet de rechercher les nombres supérieurs à 1 000, par &quot;1000,01&quot;, &quot;20 000&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-139">&lt;<em>valeur</em> (signe « inférieur à »)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="2b3f7-140">Inférieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-141">Tapez le signe « inférieur à » (<strong>&lt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="2b3f7-142"><strong>&lt;1 000</strong> permet de rechercher les nombres inférieurs à 1 000, par exemple, &quot;999,99&quot;, &quot;1&quot; et &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-143"><em>valeur</em>* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-143"><em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="2b3f7-144">Commence par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-145">Tapez la valeur de début, puis un astérisque (<strong>*</strong>).</span><span class="sxs-lookup"><span data-stu-id="2b3f7-145">Type the starting value and then an asterisk (<strong>*</strong>).</span></span></td>
<td><span data-ttu-id="2b3f7-146"><strong>S*</strong> permet de rechercher les chaînes commençant par &quot;S&quot;, telles que &quot;Stockholm&quot;, &quot;Sydney&quot; et &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-146"><strong>S*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-147">*<em>valeur</em> (astérisque)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-147">*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="2b3f7-148">Finit par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-149">Tapez un astérisque, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="2b3f7-150"><strong>*est</strong> permet de rechercher les chaînes finissant par &quot;est&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-150"><strong>*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-151">*<em>valeur</em>* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="2b3f7-152">Contenant la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="2b3f7-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="2b3f7-153">Tapez un astérisque, puis une valeur, puis un autre astérisque.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="2b3f7-154"><strong>**es**</strong> permet de rechercher les chaînes contenant &quot;es&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-155">?</span><span class="sxs-lookup"><span data-stu-id="2b3f7-155">?</span></span> <span data-ttu-id="2b3f7-156">(point d'interrogation)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-156">(question mark)</span></span></td>
<td><span data-ttu-id="2b3f7-157">Contient un ou plusieurs caractères inconnus.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="2b3f7-158">Tapez un point d'interrogation à la place des caractères inconnus dans la valeur.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="2b3f7-159"><strong>Sm?th</strong> permet de rechercher &quot;Smith&quot; et &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-160"><em>valeur</em>,<em>valeur</em> (virgule)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="2b3f7-161">Mise en correspondance des valeurs séparées par des virgules</span><span class="sxs-lookup"><span data-stu-id="2b3f7-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="2b3f7-162">Tapez tous les critères et séparez-les par des virgules.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="2b3f7-163"><strong>A, D, F, G</strong> permet de rechercher &quot;A&quot;, &quot;D&quot;, &quot;F&quot; et &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="2b3f7-164"><strong>10, 20, 30, 100</strong> permet de rechercher &quot;10, 20, 30 et 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-165">(<span class="code">Instruction SQL</span>) (instructions SQL entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-165">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="2b3f7-166">Correspond à une requête définie.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-166">Matching a defined query</span></span></td>
<td><span data-ttu-id="2b3f7-167">Tapez une instruction SQL entre parenthèses comme requête.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-167">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="2b3f7-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="2b3f7-168"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-169">Ma</span><span class="sxs-lookup"><span data-stu-id="2b3f7-169">T</span></span></td>
<td><span data-ttu-id="2b3f7-170">Date du jour</span><span class="sxs-lookup"><span data-stu-id="2b3f7-170">Today's date</span></span></td>
<td><span data-ttu-id="2b3f7-171">Tapez <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-171">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="2b3f7-172"><strong>T</strong> correspond à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-172"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-173">(methodName(parameters)) (méthode <strong>SysQueryRangeUtil</strong> entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-173">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="2b3f7-174">Mise en correspondance de la valeur ou de la plage de valeurs spécifiées par les paramètres de la méthode <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="2b3f7-174">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="2b3f7-175">Entrez une méthode <strong>SysQueryRangeUtil</strong> dont les paramètres spécifient la valeur ou la plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-175">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td><ol>
<li><span data-ttu-id="2b3f7-176">Cliquez sur <strong>Comptabilité client</strong> &gt; <strong>Factures</strong> &gt; <strong>Factures client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-176">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-177">Appuyez sur Ctrl+Maj+F3 pour ouvrir la page <strong>Recherche</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-177">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="2b3f7-178">Sous l'onglet <strong>Plage</strong>, cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-178">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-179">Dans le champ <strong>Table</strong>, sélectionnez <strong>Transactions client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-179">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-180">Dans le champ <strong>Champ</strong>, sélectionnez <strong>Date d'échéance</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-180">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-181">Dans le champ <strong>Critères</strong>, entrez <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-181">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-182">Cliquez sur <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-182">Click <strong>OK</strong>.</span></span> <span data-ttu-id="2b3f7-183">La page de liste est mise à jour et répertorie les factures correspondant aux critères entrés.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-183">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="2b3f7-184">Pour cet exemple, les factures qui étaient dues dans les deux années précédentes sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-184">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="2b3f7-185">Consultez le tableau de la section suivante pour obtenir des informations supplémentaires sur les méthodes de date <strong>SysQueryRangeUtil</strong>, ainsi que plusieurs exemples.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-185">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="2b3f7-186">Requêtes de date avancées qui utilisent les méthodes SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="2b3f7-186">Advanced date queries that use SysQueryRangeUtil methods</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b3f7-187">Méthode</span><span class="sxs-lookup"><span data-stu-id="2b3f7-187">Method</span></span></th>
<th><span data-ttu-id="2b3f7-188">Description</span><span class="sxs-lookup"><span data-stu-id="2b3f7-188">Description</span></span></th>
<th><span data-ttu-id="2b3f7-189">Exemple</span><span class="sxs-lookup"><span data-stu-id="2b3f7-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2b3f7-190">Jour (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-190">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="2b3f7-191">Permet de rechercher une date par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-191">Find a date relative to the session date.</span></span> <span data-ttu-id="2b3f7-192">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-192">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-193"><strong>Le jour suivant</strong> – Entrez <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-193"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-194"><strong>Le jour même</strong> – Entrez <strong>(Day(0))</strong></span><span class="sxs-lookup"><span data-stu-id="2b3f7-194"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-195"><strong>La veille</strong> – Entrez <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-195"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-196">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="2b3f7-197">Permet de rechercher une plage de dates par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-197">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="2b3f7-198">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-198">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-199"><strong>Les 30 derniers jours</strong> – Entrez <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-199"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-200"><strong>Les 30 jours précédents et suivants</strong> – Entrez <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-200"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-201">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="2b3f7-202">Permet de rechercher toutes les dates après la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-202">Find all dates after the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-203"><strong>Plus de 30 jours à compter de maintenant</strong> – Entrez <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-203"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-204">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="2b3f7-204">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="2b3f7-205">Permet de rechercher toutes les entrées de date/heure après l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-205">Find all date/time entries after the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-206"><strong>Toutes les dates/heures à venir</strong> – Entrez <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-206"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-207">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="2b3f7-208">Permet de rechercher toutes les dates avant la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-208">Find all dates before the specified relative date.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-209"><strong>Moins de sept jours à compter de maintenant</strong> – Entrez <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-209"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-210">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="2b3f7-210">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="2b3f7-211">Permet de rechercher toutes les entrées de date/heure avant l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-211">Find all date/time entries before the current time.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-212"><strong>Toutes les dates/heures passées</strong> – Entrez <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-212"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b3f7-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-213">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="2b3f7-214">Permet de rechercher une plage de dates, en fonction des mois relatifs au mois actuel.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-214">Find a range of dates, based on months relative to the current month.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-215"><strong>Deux mois précédents</strong> – Entrez <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-215"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-216"><strong>Trois mois suivants</strong> – Entrez <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-216"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b3f7-217">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="2b3f7-217">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="2b3f7-218">Permet de rechercher une plage de dates, en fonction des années relatives à l'année actuelle.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-218">Find a range of dates, based on years relative to the current year.</span></span></td>
<td><ul>
<li><span data-ttu-id="2b3f7-219"><strong>Année suivante</strong> – Entrez <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-219"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="2b3f7-220"><strong>Année précédente</strong> – Entrez <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="2b3f7-220"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






