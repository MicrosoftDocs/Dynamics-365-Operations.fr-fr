---
title: Syntaxe de requête et de filtrage avancée
description: Cette rubrique décrit les options de filtrage et de requête pour la boîte de dialogue Filtre/tri avancé et l’opérateur de correspondances dans le volet Filtre ou les filtres d’en-tête de colonne de la grille.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdb55a9552759e5f2b670a4eeb4e5d6572ebfb77
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744097"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="88cf8-103">Syntaxe de requête et de filtrage avancée</span><span class="sxs-lookup"><span data-stu-id="88cf8-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88cf8-104">Cette rubrique décrit les options de filtrage et de requête disponibles lorsque vous utilisez la boîte de dialogue Filtre/tri avancé ou l’opérateur de **correspondances** dans le volet Filtre ou les filtres d’en-tête de colonne de la grille.</span><span class="sxs-lookup"><span data-stu-id="88cf8-104">This topic describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="88cf8-105">Syntaxe de requête avancée</span><span class="sxs-lookup"><span data-stu-id="88cf8-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="88cf8-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="88cf8-106">Syntax</span></span></th>
<th><span data-ttu-id="88cf8-107">Description du caractère</span><span class="sxs-lookup"><span data-stu-id="88cf8-107">Character description</span></span></th>
<th><span data-ttu-id="88cf8-108">Description</span><span class="sxs-lookup"><span data-stu-id="88cf8-108">Description</span></span></th>
<th><span data-ttu-id="88cf8-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="88cf8-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="88cf8-110"><em>valeur</em></span><span class="sxs-lookup"><span data-stu-id="88cf8-110"><em>value</em></span></span></td>
<td><span data-ttu-id="88cf8-111">Égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-112">Tapez la valeur à rechercher.</span><span class="sxs-lookup"><span data-stu-id="88cf8-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="88cf8-113"><strong>Smith</strong> permet de rechercher &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-114">!<em>valeur</em> (point d’exclamation)</span><span class="sxs-lookup"><span data-stu-id="88cf8-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="88cf8-115">Pas égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-116">Tapez un point d’exclamation, puis la valeur à exclure.</span><span class="sxs-lookup"><span data-stu-id="88cf8-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="88cf8-117"><strong>!Smith</strong> permet de rechercher toutes les valeurs sauf &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-118"><em>valeur de début</em>..<em>valeur de fin</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="88cf8-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="88cf8-119">Entre les deux valeurs séparées par deux points</span><span class="sxs-lookup"><span data-stu-id="88cf8-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="88cf8-120">Tapez la valeur de début, puis deux points, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="88cf8-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="88cf8-121"><strong>1..10</strong> permet de rechercher toutes les valeurs de 1 à 10.</span><span class="sxs-lookup"><span data-stu-id="88cf8-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="88cf8-122">Cependant, dans un champ de chaîne, <strong>A..C</strong> permet de trouver toutes les valeurs commençant par &quot;A&quot; et &quot;B&quot; et les valeurs exactement égales à &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="88cf8-123">Par exemple, cette requête ne recherche pas &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="88cf8-124">Pour rechercher toutes les valeurs de &quot;A<em>&quot; à &quot;C</em>&quot;,tapez <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-125">..<em>valeur</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="88cf8-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="88cf8-126">Inférieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-127">Tapez deux points, puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="88cf8-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="88cf8-128"><strong>..1 000</strong> permet de rechercher les nombres inférieurs ou égaux à 1 000, par exemple &quot;100&quot;, &quot;999,95&quot; et &quot;1 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-129"><em>valeur</em>..</span><span class="sxs-lookup"><span data-stu-id="88cf8-129"><em>value</em>..</span></span> <span data-ttu-id="88cf8-130">(deux points)</span><span class="sxs-lookup"><span data-stu-id="88cf8-130">(double period)</span></span></td>
<td><span data-ttu-id="88cf8-131">Supérieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-132">Tapez la valeur, puis deux points.</span><span class="sxs-lookup"><span data-stu-id="88cf8-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="88cf8-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="88cf8-133"><strong>1000..</strong></span></span> <span data-ttu-id="88cf8-134">permet de rechercher les nombres supérieurs ou égaux à 1 000, par exemple &quot;1 000&quot;, &quot;1 000,01&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-135">&gt;<em>valeur</em> (signe « supérieur à »)</span><span class="sxs-lookup"><span data-stu-id="88cf8-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="88cf8-136">Supérieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-137">Tapez le signe « supérieur à » (<strong>&gt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="88cf8-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="88cf8-138"><strong>&gt;1 000</strong> permet de rechercher les nombres supérieurs à 1 000, par &quot;1000,01&quot;, &quot;20 000&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-139">&lt;<em>valeur</em> (signe « inférieur à »)</span><span class="sxs-lookup"><span data-stu-id="88cf8-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="88cf8-140">Inférieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-141">Tapez le signe « inférieur à » (<strong>&lt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="88cf8-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="88cf8-142"><strong>&lt;1 000</strong> permet de rechercher les nombres inférieurs à 1 000, par exemple, &quot;999,99&quot;, &quot;1&quot; et &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-143"><em>valeur</em>\* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="88cf8-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="88cf8-144">Commence par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-145">Tapez la valeur de début, puis un astérisque (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="88cf8-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="88cf8-146"><strong>S\*</strong> permet de rechercher les chaînes commençant par &quot;S&quot;, telles que &quot;Stockholm&quot;, &quot;Sydney&quot; et &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-147">\*<em>valeur</em> (astérisque)</span><span class="sxs-lookup"><span data-stu-id="88cf8-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="88cf8-148">Finit par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-149">Tapez un astérisque, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="88cf8-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="88cf8-150"><strong>\*est</strong> permet de rechercher les chaînes finissant par &quot;est&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-151">*<em>valeur</em>* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="88cf8-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="88cf8-152">Contenant la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="88cf8-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="88cf8-153">Tapez un astérisque, puis une valeur, puis un autre astérisque.</span><span class="sxs-lookup"><span data-stu-id="88cf8-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="88cf8-154"><strong>*es*</strong> permet de rechercher les chaînes contenant &quot;es&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-155">?</span><span class="sxs-lookup"><span data-stu-id="88cf8-155">?</span></span> <span data-ttu-id="88cf8-156">(point d’interrogation)</span><span class="sxs-lookup"><span data-stu-id="88cf8-156">(question mark)</span></span></td>
<td><span data-ttu-id="88cf8-157">Contient un ou plusieurs caractères inconnus.</span><span class="sxs-lookup"><span data-stu-id="88cf8-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="88cf8-158">Tapez un point d’interrogation à la place des caractères inconnus dans la valeur.</span><span class="sxs-lookup"><span data-stu-id="88cf8-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="88cf8-159"><strong>Sm?th</strong> permet de rechercher &quot;Smith&quot; et &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-160"><em>valeur</em>,<em>valeur</em> (virgule)</span><span class="sxs-lookup"><span data-stu-id="88cf8-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="88cf8-161">Mise en correspondance des valeurs séparées par des virgules</span><span class="sxs-lookup"><span data-stu-id="88cf8-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="88cf8-162">Tapez tous les critères et séparez-les par des virgules.</span><span class="sxs-lookup"><span data-stu-id="88cf8-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="88cf8-163"><strong>A, D, F, G</strong> permet de rechercher &quot;A&quot;, &quot;D&quot;, &quot;F&quot; et &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="88cf8-164"><strong>10, 20, 30, 100</strong> permet de rechercher &quot;10, 20, 30 et 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="88cf8-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-165">"" (deux guillemets)</span><span class="sxs-lookup"><span data-stu-id="88cf8-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="88cf8-166">Correspondance avec une valeur vide</span><span class="sxs-lookup"><span data-stu-id="88cf8-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="88cf8-167">Tapez deux guillemets consécutifs pour filtrer les valeurs vides dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="88cf8-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="88cf8-168">Deux guillemets consécutifs (<strong>""</strong>) permettent de rechercher des lignes sans valeur pour la colonne actuelle.</span><span class="sxs-lookup"><span data-stu-id="88cf8-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-169">(<span class="code">Requête Finance and Operations</span>) (Requête Finance and Operations entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="88cf8-169">(<span class="code">Finance and Operations query</span>) (Finance and Operations query between parentheses)</span></span></td>
<td><span data-ttu-id="88cf8-170">Correspond à une requête définie.</span><span class="sxs-lookup"><span data-stu-id="88cf8-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="88cf8-171">Tapez une requête en tant qu’instruction SQL entre parenthèses à l’aide du langage de requête Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="88cf8-171">Type a query as an SQL statement between parentheses using the Finance and Operations query language.</span></span></td>
  <td><span data-ttu-id="88cf8-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span><span class="sxs-lookup"><span data-stu-id="88cf8-172"><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong></span></span><br><br> 
       <span data-ttu-id="88cf8-173">en tant que syntaxe pour une condition de filtre sur un champ à partir de la source de données racine ainsi qu’un champ d’une autre source de données (pour la page Tous les clients)</span><span class="sxs-lookup"><span data-stu-id="88cf8-173">as an example of syntax for a filter condition on a field from the root datasource as well as a field from a different datasource (for the All customers page)</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-174">Ma</span><span class="sxs-lookup"><span data-stu-id="88cf8-174">T</span></span></td>
<td><span data-ttu-id="88cf8-175">Date du jour</span><span class="sxs-lookup"><span data-stu-id="88cf8-175">Today's date</span></span></td>
<td><span data-ttu-id="88cf8-176">Tapez <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-176">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="88cf8-177"><strong>T</strong> correspond à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="88cf8-177"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-178">(methodName(parameters)) (méthode <strong>SysQueryRangeUtil</strong> entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="88cf8-178">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="88cf8-179">Mise en correspondance de la valeur ou de la plage de valeurs spécifiées par les paramètres de la méthode <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="88cf8-179">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="88cf8-180">Entrez une méthode <strong>SysQueryRangeUtil</strong> dont les paramètres spécifient la valeur ou la plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="88cf8-180">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="88cf8-181">Cliquez sur <strong>Comptabilité client</strong> &gt; <strong>Factures</strong> &gt; <strong>Factures client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-181">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-182">Appuyez sur Ctrl+Maj+F3 pour ouvrir la page <strong>Recherche</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-182">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="88cf8-183">Sous l’onglet <strong>Plage</strong>, cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-183">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-184">Dans le champ <strong>Table</strong>, sélectionnez <strong>Transactions client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-184">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-185">Dans le champ <strong>Champ</strong>, sélectionnez <strong>Date d’échéance</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-185">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-186">Dans le champ <strong>Critères</strong>, entrez <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-186">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-187">Cliquez sur <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-187">Click <strong>OK</strong>.</span></span> <span data-ttu-id="88cf8-188">La page de liste est mise à jour et répertorie les factures correspondant aux critères entrés.</span><span class="sxs-lookup"><span data-stu-id="88cf8-188">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="88cf8-189">Pour cet exemple, les factures qui étaient dues dans les deux années précédentes sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="88cf8-189">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="88cf8-190">Consultez le tableau de la section suivante pour obtenir des informations supplémentaires sur les méthodes de date <strong>SysQueryRangeUtil</strong>, ainsi que plusieurs exemples.</span><span class="sxs-lookup"><span data-stu-id="88cf8-190">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="88cf8-191">Requêtes de date avancées qui utilisent les méthodes SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="88cf8-191">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="88cf8-192">Méthode</span><span class="sxs-lookup"><span data-stu-id="88cf8-192">Method</span></span></th>
<th><span data-ttu-id="88cf8-193">Description</span><span class="sxs-lookup"><span data-stu-id="88cf8-193">Description</span></span></th>
<th><span data-ttu-id="88cf8-194">Exemple</span><span class="sxs-lookup"><span data-stu-id="88cf8-194">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="88cf8-195">Jour (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-195">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="88cf8-196">Permet de rechercher une date par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="88cf8-196">Find a date relative to the session date.</span></span> <span data-ttu-id="88cf8-197">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="88cf8-197">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-198"><strong>Le jour suivant</strong> – Entrez <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-198"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-199"><strong>Le jour même</strong> – Entrez <strong>(Day(0))</strong></span><span class="sxs-lookup"><span data-stu-id="88cf8-199"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-200"><strong>La veille</strong> – Entrez <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-200"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-201">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="88cf8-202">Permet de rechercher une plage de dates par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="88cf8-202">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="88cf8-203">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="88cf8-203">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-204"><strong>Les 30 derniers jours</strong> – Entrez <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-204"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-205"><strong>Les 30 jours précédents et suivants</strong> – Entrez <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-205"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-206">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="88cf8-207">Permet de rechercher toutes les dates après la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="88cf8-207">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-208"><strong>Plus de 30 jours à compter de maintenant</strong> – Entrez <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-208"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-209">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="88cf8-209">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="88cf8-210">Permet de rechercher toutes les entrées de date/heure après l’heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="88cf8-210">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-211"><strong>Toutes les dates/heures à venir</strong> – Entrez <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-211"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-212">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="88cf8-213">Permet de rechercher toutes les dates avant la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="88cf8-213">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-214"><strong>Moins de sept jours à compter de maintenant</strong> – Entrez <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-214"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-215">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="88cf8-215">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="88cf8-216">Permet de rechercher toutes les entrées de date/heure avant l’heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="88cf8-216">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-217"><strong>Toutes les dates/heures passées</strong> – Entrez <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-217"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-218">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="88cf8-219">Permet de rechercher une plage de dates, en fonction des mois relatifs au mois actuel.</span><span class="sxs-lookup"><span data-stu-id="88cf8-219">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-220"><strong>Deux mois précédents</strong> – Entrez <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-220"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-221"><strong>Trois mois suivants</strong> – Entrez <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-221"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="88cf8-222">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="88cf8-222">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="88cf8-223">Permet de rechercher une plage de dates, en fonction des années relatives à l’année actuelle.</span><span class="sxs-lookup"><span data-stu-id="88cf8-223">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="88cf8-224"><strong>Année suivante</strong> – Entrez <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-224"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="88cf8-225"><strong>Année précédente</strong> – Entrez <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="88cf8-225"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]