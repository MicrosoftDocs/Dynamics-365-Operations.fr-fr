---
title: Syntaxe de requête et de filtrage avancé
description: Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez la boîte de dialogue Filtre/tri avancé ou l'opérateur de correspondances dans le volet Filtre ou les filtres d'en-tête de colonne de la grille.
author: jasongre
manager: AnnBe
ms.date: 01/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5a96921436311440ba60c3fa31135457cf9f291
ms.sourcegitcommit: 8585de8acf579bcc033671ef270fa9d92230121b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/02/2020
ms.locfileid: "2931286"
---
# <a name="advanced-filtering-and-query-syntax"></a><span data-ttu-id="9b03c-103">Syntaxe de requête et de filtrage avancée</span><span class="sxs-lookup"><span data-stu-id="9b03c-103">Advanced filtering and query syntax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b03c-104">Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez la boîte de dialogue Filtre/tri avancé ou l'opérateur de **correspondances** dans le volet Filtre ou les filtres d'en-tête de colonne de la grille.</span><span class="sxs-lookup"><span data-stu-id="9b03c-104">This article describes the filtering and query options that are available when you use the Advanced filter/sort dialog or the **matches** operator in the Filter pane or grid column header filters.</span></span>

## <a name="advanced-query-syntax"></a><span data-ttu-id="9b03c-105">Syntaxe de requête avancée</span><span class="sxs-lookup"><span data-stu-id="9b03c-105">Advanced query syntax</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9b03c-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9b03c-106">Syntax</span></span></th>
<th><span data-ttu-id="9b03c-107">Description du caractère</span><span class="sxs-lookup"><span data-stu-id="9b03c-107">Character description</span></span></th>
<th><span data-ttu-id="9b03c-108">Description </span><span class="sxs-lookup"><span data-stu-id="9b03c-108">Description</span></span></th>
<th><span data-ttu-id="9b03c-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="9b03c-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9b03c-110"><em>valeur</em></span><span class="sxs-lookup"><span data-stu-id="9b03c-110"><em>value</em></span></span></td>
<td><span data-ttu-id="9b03c-111">Égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-111">Equal to the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-112">Tapez la valeur à rechercher.</span><span class="sxs-lookup"><span data-stu-id="9b03c-112">Type the value to find.</span></span></td>
<td><span data-ttu-id="9b03c-113"><strong>Smith</strong> permet de rechercher &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-113"><strong>Smith</strong> finds &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-114">!<em>valeur</em> (point d'exclamation)</span><span class="sxs-lookup"><span data-stu-id="9b03c-114">!<em>value</em> (exclamation point)</span></span></td>
<td><span data-ttu-id="9b03c-115">Pas égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-115">Not equal to the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-116">Tapez un point d'exclamation, puis la valeur à exclure.</span><span class="sxs-lookup"><span data-stu-id="9b03c-116">Type an exclamation point and then the value to exclude.</span></span></td>
<td><span data-ttu-id="9b03c-117"><strong>!Smith</strong> permet de rechercher toutes les valeurs sauf &quot;Smith&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-117"><strong>!Smith</strong> finds all values except &quot;Smith&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-118"><em>valeur de début</em>..<em>valeur de fin</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="9b03c-118"><em>from-value</em>..<em>to-value</em> (double period)</span></span></td>
<td><span data-ttu-id="9b03c-119">Entre les deux valeurs séparées par deux points</span><span class="sxs-lookup"><span data-stu-id="9b03c-119">Between the two values that are separated by double periods</span></span></td>
<td><span data-ttu-id="9b03c-120">Tapez la valeur de début, puis deux points, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="9b03c-120">Type the from-value, then two periods, and then the to-value.</span></span></td>
<td><span data-ttu-id="9b03c-121"><strong>1..10</strong> permet de rechercher toutes les valeurs de 1 à 10.</span><span class="sxs-lookup"><span data-stu-id="9b03c-121"><strong>1..10</strong> finds all values from 1 through 10.</span></span> <span data-ttu-id="9b03c-122">Cependant, dans un champ de chaîne, <strong>A..C</strong> permet de trouver toutes les valeurs commençant par &quot;A&quot; et &quot;B&quot; et les valeurs exactement égales à &quot;C&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-122">However, in a string field, <strong>A..C</strong> finds all values that start with &quot;A&quot; and &quot;B&quot;, and values that are exactly equal to &quot;C&quot;.</span></span> <span data-ttu-id="9b03c-123">Par exemple, cette requête ne recherche pas &quot;Ca&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-123">For example, this query won't find &quot;Ca&quot;.</span></span> <span data-ttu-id="9b03c-124">Pour rechercher toutes les valeurs de &quot;A<em>&quot; à &quot;C</em>&quot;,tapez <strong>A..D</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-124">To find all values from &quot;A<em>&quot; through &quot;C</em>&quot;, type <strong>A..D</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-125">..<em>valeur</em> (deux points)</span><span class="sxs-lookup"><span data-stu-id="9b03c-125">..<em>value</em> (double period)</span></span></td>
<td><span data-ttu-id="9b03c-126">Inférieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-126">Less than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-127">Tapez deux points, puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="9b03c-127">Type two periods and then the value.</span></span></td>
<td><span data-ttu-id="9b03c-128"><strong>..1 000</strong> permet de rechercher les nombres inférieurs ou égaux à 1 000, par exemple &quot;100&quot;, &quot;999,95&quot; et &quot;1 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-128"><strong>..1000</strong> finds any number that is less than or equal to 1000, such as &quot;100&quot;, &quot;999.95&quot;, and &quot;1,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-129"><em>valeur</em>..</span><span class="sxs-lookup"><span data-stu-id="9b03c-129"><em>value</em>..</span></span> <span data-ttu-id="9b03c-130">(deux points)</span><span class="sxs-lookup"><span data-stu-id="9b03c-130">(double period)</span></span></td>
<td><span data-ttu-id="9b03c-131">Supérieur ou égal à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-131">Greater than or equal to the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-132">Tapez la valeur, puis deux points.</span><span class="sxs-lookup"><span data-stu-id="9b03c-132">Type the value and then two periods.</span></span></td>
<td><span data-ttu-id="9b03c-133"><strong>1000..</strong></span><span class="sxs-lookup"><span data-stu-id="9b03c-133"><strong>1000..</strong></span></span> <span data-ttu-id="9b03c-134">permet de rechercher les nombres supérieurs ou égaux à 1 000, par exemple &quot;1 000&quot;, &quot;1 000,01&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-134">finds any number that is greater than or equal to 1000, such as &quot;1,000&quot;, &quot;1,000.01&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-135">&gt;<em>valeur</em> (signe « supérieur à »)</span><span class="sxs-lookup"><span data-stu-id="9b03c-135">&gt;<em>value</em> (greater than sign)</span></span></td>
<td><span data-ttu-id="9b03c-136">Supérieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-136">Greater than the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-137">Tapez le signe « supérieur à » (<strong>&gt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="9b03c-137">Type a greater than sign (<strong>&gt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="9b03c-138"><strong>&gt;1 000</strong> permet de rechercher les nombres supérieurs à 1 000, par &quot;1000,01&quot;, &quot;20 000&quot; et &quot;1 000 000&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-138"><strong>&gt;1000</strong> finds any number that is greater than 1000, such as &quot;1000.01&quot;, &quot;20,000&quot;, and &quot;1,000,000&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-139">&lt;<em>valeur</em> (signe « inférieur à »)</span><span class="sxs-lookup"><span data-stu-id="9b03c-139">&lt;<em>value</em> (less than sign)</span></span></td>
<td><span data-ttu-id="9b03c-140">Inférieur à la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-140">Less than the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-141">Tapez le signe « inférieur à » (<strong>&lt;</strong>), puis la valeur.</span><span class="sxs-lookup"><span data-stu-id="9b03c-141">Type a less than sign (<strong>&lt;</strong>) and then the value.</span></span></td>
<td><span data-ttu-id="9b03c-142"><strong>&lt;1 000</strong> permet de rechercher les nombres inférieurs à 1 000, par exemple, &quot;999,99&quot;, &quot;1&quot; et &quot;-200&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-142"><strong>&lt;1000</strong> finds any number that is less than 1000, such as &quot;999.99&quot;, &quot;1&quot;, and &quot;-200&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-143"><em>valeur</em>\* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="9b03c-143"><em>value</em>\* (asterisk)</span></span></td>
<td><span data-ttu-id="9b03c-144">Commence par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-144">Starting from the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-145">Tapez la valeur de début, puis un astérisque (<strong>\*</strong>).</span><span class="sxs-lookup"><span data-stu-id="9b03c-145">Type the starting value and then an asterisk (<strong>\*</strong>).</span></span></td>
<td><span data-ttu-id="9b03c-146"><strong>S\*</strong> permet de rechercher les chaînes commençant par &quot;S&quot;, telles que &quot;Stockholm&quot;, &quot;Sydney&quot; et &quot;San Francisco&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-146"><strong>S\*</strong> finds any string that starts with &quot;S&quot;, such as &quot;Stockholm&quot;, &quot;Sydney&quot;, and &quot;San Francisco&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-147">\*<em>valeur</em> (astérisque)</span><span class="sxs-lookup"><span data-stu-id="9b03c-147">\*<em>value</em> (asterisk)</span></span></td>
<td><span data-ttu-id="9b03c-148">Finit par la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-148">Ending with the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-149">Tapez un astérisque, puis la valeur de fin.</span><span class="sxs-lookup"><span data-stu-id="9b03c-149">Type an asterisk and then the ending value.</span></span></td>
<td><span data-ttu-id="9b03c-150"><strong>\*est</strong> permet de rechercher les chaînes finissant par &quot;est&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-150"><strong>\*east</strong> finds any string that ends with &quot;east&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-151">*<em>valeur</em>* (astérisque)</span><span class="sxs-lookup"><span data-stu-id="9b03c-151">*<em>value</em>* (asterisk)</span></span></td>
<td><span data-ttu-id="9b03c-152">Contenant la valeur entrée</span><span class="sxs-lookup"><span data-stu-id="9b03c-152">Containing the value that is entered</span></span></td>
<td><span data-ttu-id="9b03c-153">Tapez un astérisque, puis une valeur, puis un autre astérisque.</span><span class="sxs-lookup"><span data-stu-id="9b03c-153">Type an asterisk, then a value, and then another asterisk.</span></span></td>
<td><span data-ttu-id="9b03c-154"><strong>*es*</strong> permet de rechercher les chaînes contenant &quot;es&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-154"><strong>*th*</strong> finds any string that contains &quot;th&quot;, such as &quot;Northeast&quot; and &quot;Southeast&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-155">?</span><span class="sxs-lookup"><span data-stu-id="9b03c-155">?</span></span> <span data-ttu-id="9b03c-156">(point d'interrogation)</span><span class="sxs-lookup"><span data-stu-id="9b03c-156">(question mark)</span></span></td>
<td><span data-ttu-id="9b03c-157">Contient un ou plusieurs caractères inconnus.</span><span class="sxs-lookup"><span data-stu-id="9b03c-157">Having one or more unknown characters</span></span></td>
<td><span data-ttu-id="9b03c-158">Tapez un point d'interrogation à la place des caractères inconnus dans la valeur.</span><span class="sxs-lookup"><span data-stu-id="9b03c-158">Type a question mark at the position of the unknown character in the value.</span></span></td>
<td><span data-ttu-id="9b03c-159"><strong>Sm?th</strong> permet de rechercher &quot;Smith&quot; et &quot;Smyth&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-159"><strong>Sm?th</strong> finds &quot;Smith&quot; and &quot;Smyth&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-160"><em>valeur</em>,<em>valeur</em> (virgule)</span><span class="sxs-lookup"><span data-stu-id="9b03c-160"><em>value</em>,<em>value</em> (comma)</span></span></td>
<td><span data-ttu-id="9b03c-161">Mise en correspondance des valeurs séparées par des virgules</span><span class="sxs-lookup"><span data-stu-id="9b03c-161">Matching the values that are separated by commas</span></span></td>
<td><span data-ttu-id="9b03c-162">Tapez tous les critères et séparez-les par des virgules.</span><span class="sxs-lookup"><span data-stu-id="9b03c-162">Type all your criteria, and separate them by using commas.</span></span></td>
<td><span data-ttu-id="9b03c-163"><strong>A, D, F, G</strong> permet de rechercher &quot;A&quot;, &quot;D&quot;, &quot;F&quot; et &quot;G&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-163"><strong>A, D, F, G</strong> finds exactly &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, and &quot;G&quot;.</span></span> <span data-ttu-id="9b03c-164"><strong>10, 20, 30, 100</strong> permet de rechercher &quot;10, 20, 30 et 100&quot;.</span><span class="sxs-lookup"><span data-stu-id="9b03c-164"><strong>10, 20, 30, 100</strong> finds exactly &quot;10, 20, 30, 100&quot;.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-165">"" (deux guillemets)</span><span class="sxs-lookup"><span data-stu-id="9b03c-165">"" (two double quotes)</span></span></td>
<td><span data-ttu-id="9b03c-166">Correspondance avec une valeur vide</span><span class="sxs-lookup"><span data-stu-id="9b03c-166">Matching a blank value</span></span></td>
<td><span data-ttu-id="9b03c-167">Tapez deux guillemets consécutifs pour filtrer les valeurs vides dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="9b03c-167">Type two consecutive double quotes to filter for blank values in that field.</span></span></td>
<td><span data-ttu-id="9b03c-168">Deux guillemets consécutifs (<strong>""</strong>) permettent de rechercher des lignes sans valeur pour la colonne actuelle.</span><span class="sxs-lookup"><span data-stu-id="9b03c-168">Two consecutive double quotes (<strong>""</strong>) finds rows with no value for the current column.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-169">(<span class="code">Instruction SQL</span>) (instructions SQL entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="9b03c-169">(<span class="code">SQL statement</span>) (SQL statement between parentheses)</span></span></td>
<td><span data-ttu-id="9b03c-170">Correspond à une requête définie.</span><span class="sxs-lookup"><span data-stu-id="9b03c-170">Matching a defined query</span></span></td>
<td><span data-ttu-id="9b03c-171">Tapez une instruction SQL entre parenthèses comme requête.</span><span class="sxs-lookup"><span data-stu-id="9b03c-171">Type a query as an SQL statement between parentheses.</span></span></td>
<td><span data-ttu-id="9b03c-172"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span><span class="sxs-lookup"><span data-stu-id="9b03c-172"><strong><span class="code">(data source.Fieldname != &quot;A&quot;)</span></strong></span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-173">Ma</span><span class="sxs-lookup"><span data-stu-id="9b03c-173">T</span></span></td>
<td><span data-ttu-id="9b03c-174">Date du jour</span><span class="sxs-lookup"><span data-stu-id="9b03c-174">Today's date</span></span></td>
<td><span data-ttu-id="9b03c-175">Tapez <strong>T</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-175">Type <strong>T</strong>.</span></span></td>
<td><span data-ttu-id="9b03c-176"><strong>T</strong> correspond à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="9b03c-176"><strong>T</strong> matches today's date.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-177">(methodName(parameters)) (méthode <strong>SysQueryRangeUtil</strong> entre parenthèses)</span><span class="sxs-lookup"><span data-stu-id="9b03c-177">(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> method between parentheses)</span></span></td>
<td><span data-ttu-id="9b03c-178">Mise en correspondance de la valeur ou de la plage de valeurs spécifiées par les paramètres de la méthode <strong>SysQueryRangeUtil</strong></span><span class="sxs-lookup"><span data-stu-id="9b03c-178">Matching the value or range of values that are specified by the parameters of the <strong>SysQueryRangeUtil</strong> method</span></span></td>
<td><span data-ttu-id="9b03c-179">Entrez une méthode <strong>SysQueryRangeUtil</strong> dont les paramètres spécifient la valeur ou la plage de valeurs.</span><span class="sxs-lookup"><span data-stu-id="9b03c-179">Type a <strong>SysQueryRangeUtil</strong> method that has parameters that specify the value or range of values.</span></span></td>
<td>
<ol>
<li><span data-ttu-id="9b03c-180">Cliquez sur <strong>Comptabilité client</strong> &gt; <strong>Factures</strong> &gt; <strong>Factures client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-180">Click <strong>Accounts receivable</strong> &gt; <strong>Invoices</strong> &gt; <strong>Open customer invoices</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-181">Appuyez sur Ctrl+Maj+F3 pour ouvrir la page <strong>Recherche</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-181">Press Ctrl+Shift+F3 to open the <strong>Inquiry</strong> page.</span></span></li>
<li><span data-ttu-id="9b03c-182">Sous l'onglet <strong>Plage</strong>, cliquez sur <strong>Ajouter</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-182">On the <strong>Range</strong> tab, click <strong>Add</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-183">Dans le champ <strong>Table</strong>, sélectionnez <strong>Transactions client en cours</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-183">In the <strong>Table</strong> field, select <strong>Open customer transactions</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-184">Dans le champ <strong>Champ</strong>, sélectionnez <strong>Date d'échéance</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-184">In the <strong>Field</strong> field, select <strong>Due date</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-185">Dans le champ <strong>Critères</strong>, entrez <strong>(yearRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-185">In the <strong>Criteria</strong> field, enter <strong>(yearRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-186">Cliquez sur <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-186">Click <strong>OK</strong>.</span></span> <span data-ttu-id="9b03c-187">La page de liste est mise à jour et répertorie les factures correspondant aux critères entrés.</span><span class="sxs-lookup"><span data-stu-id="9b03c-187">The list page is updated and lists the invoices that match the criterion that you entered.</span></span> <span data-ttu-id="9b03c-188">Pour cet exemple, les factures qui étaient dues dans les deux années précédentes sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="9b03c-188">For this example, invoices that were due in the previous two years are listed.</span></span></li>
</ol>
<span data-ttu-id="9b03c-189">Consultez le tableau de la section suivante pour obtenir des informations supplémentaires sur les méthodes de date <strong>SysQueryRangeUtil</strong>, ainsi que plusieurs exemples.</span><span class="sxs-lookup"><span data-stu-id="9b03c-189">See the table in the next section for additional details about <strong>SysQueryRangeUtil</strong> date methods, and several examples.</span></span></td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a><span data-ttu-id="9b03c-190">Requêtes de date avancées qui utilisent les méthodes SysQueryRangeUtil</span><span class="sxs-lookup"><span data-stu-id="9b03c-190">Advanced date queries that use SysQueryRangeUtil methods</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="9b03c-191">Méthode</span><span class="sxs-lookup"><span data-stu-id="9b03c-191">Method</span></span></th>
<th><span data-ttu-id="9b03c-192">Description</span><span class="sxs-lookup"><span data-stu-id="9b03c-192">Description</span></span></th>
<th><span data-ttu-id="9b03c-193">Exemple</span><span class="sxs-lookup"><span data-stu-id="9b03c-193">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9b03c-194">Jour (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-194">Day (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="9b03c-195">Permet de rechercher une date par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="9b03c-195">Find a date relative to the session date.</span></span> <span data-ttu-id="9b03c-196">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="9b03c-196">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-197"><strong>Le jour suivant</strong> – Entrez <strong>(Day(1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-197"><strong>Tomorrow</strong> – Enter <strong>(Day(1))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-198"><strong>Le jour même</strong> – Entrez <strong>(Day(0))</strong></span><span class="sxs-lookup"><span data-stu-id="9b03c-198"><strong>Today</strong> – Enter <strong>(Day(0))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-199"><strong>La veille</strong> – Entrez <strong>(Day(-1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-199"><strong>Yesterday</strong> – Enter <strong>(Day(-1))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-200">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-200">DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</span></span></td>
<td><span data-ttu-id="9b03c-201">Permet de rechercher une plage de dates par rapport à la date de la session.</span><span class="sxs-lookup"><span data-stu-id="9b03c-201">Find a range of dates relative to the session date.</span></span> <span data-ttu-id="9b03c-202">Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</span><span class="sxs-lookup"><span data-stu-id="9b03c-202">Positive values indicate future dates, and negative values indicate past dates.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-203"><strong>Les 30 derniers jours</strong> – Entrez <strong>(DayRange(-30,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-203"><strong>Last 30 days</strong> – Enter <strong>(DayRange(-30,0))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-204"><strong>Les 30 jours précédents et suivants</strong> – Entrez <strong>(DayRange(-30,30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-204"><strong>Previous 30 days and next 30 days</strong> – Enter <strong>(DayRange(-30,30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-205">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-205">GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="9b03c-206">Permet de rechercher toutes les dates après la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b03c-206">Find all dates after the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-207"><strong>Plus de 30 jours à compter de maintenant</strong> – Entrez <strong>(GreaterThanDate(30))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-207"><strong>More than 30 days from now</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-208">GreaterThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="9b03c-208">GreaterThanUtcNow ()</span></span></td>
<td><span data-ttu-id="9b03c-209">Permet de rechercher toutes les entrées de date/heure après l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="9b03c-209">Find all date/time entries after the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-210"><strong>Toutes les dates/heures à venir</strong> – Entrez <strong>(GreaterThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-210"><strong>All future date/times</strong> – Enter <strong>(GreaterThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-211">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-211">LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</span></span></td>
<td><span data-ttu-id="9b03c-212">Permet de rechercher toutes les dates avant la date relative spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b03c-212">Find all dates before the specified relative date.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-213"><strong>Moins de sept jours à compter de maintenant</strong> – Entrez <strong>(LessThanDate(7))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-213"><strong>Less than seven days from now</strong> – Enter <strong>(LessThanDate(7))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-214">LessThanUtcNow ()</span><span class="sxs-lookup"><span data-stu-id="9b03c-214">LessThanUtcNow ()</span></span></td>
<td><span data-ttu-id="9b03c-215">Permet de rechercher toutes les entrées de date/heure avant l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="9b03c-215">Find all date/time entries before the current time.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-216"><strong>Toutes les dates/heures passées</strong> – Entrez <strong>(LessThanUtcNow())</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-216"><strong>All past date/times</strong> – Enter <strong>(LessThanUtcNow())</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-217">MonthRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-217">MonthRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="9b03c-218">Permet de rechercher une plage de dates, en fonction des mois relatifs au mois actuel.</span><span class="sxs-lookup"><span data-stu-id="9b03c-218">Find a range of dates, based on months relative to the current month.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-219"><strong>Deux mois précédents</strong> – Entrez <strong>(MonthRange(-2,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-219"><strong>Previous two months</strong> – Enter <strong>(MonthRange(-2,0))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-220"><strong>Trois mois suivants</strong> – Entrez <strong>(MonthRange(0,3))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-220"><strong>Next three months</strong> – Enter <strong>(MonthRange(0,3))</strong>.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="9b03c-221">YearRange (_relativeFrom=0, _relativeTo=0)</span><span class="sxs-lookup"><span data-stu-id="9b03c-221">YearRange (_relativeFrom=0, _relativeTo=0)</span></span></td>
<td><span data-ttu-id="9b03c-222">Permet de rechercher une plage de dates, en fonction des années relatives à l'année actuelle.</span><span class="sxs-lookup"><span data-stu-id="9b03c-222">Find a range of dates, based on years relative to the current year.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="9b03c-223"><strong>Année suivante</strong> – Entrez <strong>(YearRange(0, 1))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-223"><strong>Next year</strong> – Enter <strong>(YearRange(0, 1))</strong>.</span></span></li>
<li><span data-ttu-id="9b03c-224"><strong>Année précédente</strong> – Entrez <strong>(YearRange(-1,0))</strong>.</span><span class="sxs-lookup"><span data-stu-id="9b03c-224"><strong>Previous year</strong> – Enter <strong>(YearRange(-1,0))</strong>.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
