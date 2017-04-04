---
title: "Syntaxe avancée de requête et de filtrage"
description: "Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez l&quot;opérateur de correspondances dans la boîte de dialogue Filtre/tri avancé."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysQueryForm
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 5ee7a04572e350a7c08d0418bade6d332aa920c6
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-filtering-and-query-syntax"></a>Syntaxe avancée de requête et de filtrage

Cet article décrit les options de filtrage et de requête disponibles lorsque vous utilisez l'opérateur de correspondances dans la boîte de dialogue Filtre/tri avancé.

<a name="advanced-query-syntax"></a>Syntaxe de requête avancée
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
<th>Syntaxe</th>
<th>Description du caractère</th>
<th>description ;</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>valeur</em></td>
<td>Égal à la valeur entrée</td>
<td>Tapez la valeur à rechercher.</td>
<td><strong>Smith</strong> recherche &quot;Smith&quot;.</td>
</tr>
<tr class="even">
<td>!<em>valeur</em> (point d'exclamation)</td>
<td>Pas égal à la valeur entrée</td>
<td>Tapez un point d'exclamation, puis la valeur à exclure.</td>
<td><strong>! Smith</strong> permet &quot;de trouver toutes les valeurs sauf Smith&quot;.</td>
</tr>
<tr class="odd">
<td><em>valeur de début</em>..<em>valeur de fin</em> (deux points)</td>
<td>Entre les deux valeurs séparées par deux points</td>
<td>Tapez la valeur de début, puis deux points, puis la valeur de fin.</td>
<td><strong>1..10</strong> permet de trouver toutes les valeurs comprises entre 1 et 10. Toutefois, dans un champ de chaîne, <strong>A.C permet</strong> permet de trouver toutes les valeurs commençant &quot;par A&quot; et &quot;B&quot;, et les valeurs qui sont précisément égale &quot;au C&quot;. Par exemple, cette requête ne &quot;trouveront pas le CA.&quot; Pour rechercher toutes les valeurs &quot;d'A*&quot; via &quot;C*&quot;, type <strong>A.D</strong>.</td>
</tr>
<tr class="even">
<td>..<em>valeur</em> (deux points)</td>
<td>Inférieur ou égal à la valeur entrée</td>
<td>Tapez deux points, puis la valeur.</td>
<td><strong>. .1000</strong> recherche n'importe quel nombre qui est inférieur ou égal à 1000, tel &quot;que 100&quot;, &quot;999,95&quot;, et &quot;1.000&quot;.</td>
</tr>
<tr class="odd">
<td><em>valeur</em>.. (deux points)</td>
<td>Supérieur ou égal à la valeur entrée</td>
<td>Tapez la valeur, puis deux points.</td>
<td><strong>1000..</strong> recherche n'importe quel nombre supérieur ou égal à 1000, tel &quot;que 1.000&quot;, &quot;1.000,01&quot;, et &quot;1.000.000&quot;.</td>
</tr>
<tr class="even">
<td>&gt;<em>valeur</em> (supérieur à le signe)</td>
<td>Supérieur à la valeur entrée</td>
<td>Tapez un meilleur que chèque (<strong>&gt;</strong>) puis la valeur.</td>
<td><strong>&gt;1 000</strong> contrôler tout valeur supérieure à 1000, tel &quot;que 1000,01&quot;, &quot;20.000&quot;, et &quot;1.000.000&quot;.</td>
</tr>
<tr class="odd">
<td>&lt;<em>valeur</em> (moins que le signe)</td>
<td>Inférieur à la valeur entrée</td>
<td>Tapez moins que chèque (<strong>&lt;</strong>) puis la valeur.</td>
<td><strong>&lt;1 000</strong> contrôler tout valeur inférieure à 1000, tel &quot;que 999,99&quot;, &quot;1&quot;, et &quot;-200&quot;.</td>
</tr>
<tr class="even">
<td><em>valeur</em>* (astérisque)</td>
<td>Commence par la valeur entrée</td>
<td>Tapez la valeur de début puis un astérisque (<strong>*</strong>).</td>
<td><strong>S*</strong> permet de trouver les chaînes commençant &quot;par S&quot;, tel &quot;que Stockholm&quot;, &quot;Sydney&quot;, et &quot;Saint-Nazaire&quot;.</td>
</tr>
<tr class="odd">
<td>*<em>value</em> (asterisk)</td>
<td>Finit par la valeur entrée</td>
<td>Tapez un astérisque, puis la valeur de fin.</td>
<td><strong>*east</strong> prend toute chaîne qui se termine par l'est&quot;, par exemple &quot;le "&quot; et &quot;les sud-est&quot;.</td>
</tr>
<tr class="even">
<td>*<em>valeur</em>* (astérisque)</td>
<td>Contenant la valeur entrée</td>
<td>Tapez un astérisque, puis une valeur, puis un autre astérisque.</td>
<td><strong>*th*</strong> permet de trouver les chaînes contenant &quot;th&quot;, comme &quot;le "&quot; et &quot;les sud-est&quot;.</td>
</tr>
<tr class="odd">
<td>? (point d'interrogation)</td>
<td>Contient un ou plusieurs caractères inconnus.</td>
<td>Tapez un point d'interrogation à la place des caractères inconnus dans la valeur.</td>
<td><strong>Sm ? Th</strong> recherche &quot;Smith&quot; et &quot;Smyth&quot;.</td>
</tr>
<tr class="even">
<td><em>valeur</em>,<em>valeur</em> (virgule)</td>
<td>Mise en correspondance des valeurs séparées par des virgules</td>
<td>Tapez tous les critères et séparez-les par des virgules.</td>
<td><strong>A, D, F, G</strong> trouver &quot;trouver&quot;&quot;10&quot;, &quot;20&quot;, 30 &quot;,&quot;<strong>10, 20, 30, 100</strong> 100 A &quot;, de D, de F, et de G&quot;.</td>
</tr>
<tr class="odd">
<td>(<span class="code">Instruction SQL</span>) (instructions SQL entre parenthèses)</td>
<td>Correspond à une requête définie.</td>
<td>Tapez une instruction SQL entre parenthèses comme requête.</td>
<td><strong><span class="code">(source de données. Fieldname ! = &quot;A&quot;)</span></strong></td>
</tr>
<tr class="even">
<td>Ma</td>
<td>Date du jour</td>
<td>Tapez <strong>T</strong>.</td>
<td><strong>T</strong> correspond à la date du jour.</td>
</tr>
<tr class="odd">
<td>(methodName(parameters)) (méthode <strong>SysQueryRangeUtil</strong> entre parenthèses)</td>
<td>Mise en correspondance de la valeur ou de la plage de valeurs spécifiées par les paramètres de la méthode <strong>SysQueryRangeUtil</strong></td>
<td>Entrez une méthode <strong>SysQueryRangeUtil</strong> dont les paramètres spécifient la valeur ou la plage de valeurs.</td>
<td><ol>
<li>Cliquez <strong>Ventes</strong> &gt; <strong>Factures</strong> &gt; <strong>Factures client en cours</strong>sur.</li>
<li>Appuyez sur Ctrl+Maj+F3 pour ouvrir la page <strong>Recherche</strong>.</li>
<li>Sous l'onglet <strong>Plage</strong>, cliquez sur <strong>Ajouter</strong>.</li>
<li>Dans le champ <strong>Table</strong>, sélectionnez <strong>Transactions client en cours</strong>.</li>
<li>Dans le champ <strong>Champ</strong>, sélectionnez <strong>Date d'échéance</strong>.</li>
<li>Dans le champ <strong>Critères</strong>, entrez <strong>(yearRange(-2,0))</strong>.</li>
<li>Cliquez sur <strong>OK</strong>. La page de liste est mise à jour et répertorie les factures correspondant aux critères entrés. Pour cet exemple, les factures qui étaient dues dans les deux années précédentes sont répertoriées.</li>
</ol>
Consultez le tableau de la section suivante pour obtenir des informations supplémentaires sur les méthodes de date <strong>SysQueryRangeUtil</strong>, ainsi que plusieurs exemples.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Requêtes de date avancées qui utilisent les méthodes SysQueryRangeUtil
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Méthode</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Jour (_relativeDays=0)</td>
<td>Permet de rechercher une date par rapport à la date de la session. Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</td>
<td><ul>
<li><strong>Le jour suivant</strong> – Entrez <strong>(Day(1))</strong>.</li>
<li><strong>Le jour même</strong> – Entrez <strong>(Day(0))</strong></li>
<li><strong>La veille</strong> – Entrez <strong>(Day(-1))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Permet de rechercher une plage de dates par rapport à la date de la session. Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</td>
<td><ul>
<li><strong>Les 30 derniers jours</strong> – Entrez <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>Les 30 jours précédents et suivants</strong> – Entrez <strong>(DayRange(-30,30))</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Permet de rechercher toutes les dates après la date relative spécifiée.</td>
<td><ul>
<li><strong>Plus de 30 jours à compter de maintenant</strong> – Entrez <strong>(GreaterThanDate(30))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>GreaterThanUtcNow ()</td>
<td>Permet de rechercher toutes les entrées de date/heure après l'heure actuelle.</td>
<td><ul>
<li><strong>Toutes les dates/heures à venir</strong> – Entrez <strong>(GreaterThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Permet de rechercher toutes les dates avant la date relative spécifiée.</td>
<td><ul>
<li><strong>Moins de sept jours à compter de maintenant</strong> – Entrez <strong>(LessThanDate(7))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>LessThanUtcNow ()</td>
<td>Permet de rechercher toutes les entrées de date/heure avant l'heure actuelle.</td>
<td><ul>
<li><strong>Toutes les dates/heures passées</strong> – Entrez <strong>(LessThanUtcNow())</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Permet de rechercher une plage de dates, en fonction des mois relatifs au mois actuel.</td>
<td><ul>
<li><strong>Deux mois précédents</strong> – Entrez <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Trois mois suivants</strong> – Entrez <strong>(MonthRange(0,3))</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Permet de rechercher une plage de dates, en fonction des années relatives à l'année actuelle.</td>
<td><ul>
<li><strong>Année suivante</strong> – Entrez <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Année précédente</strong> – Entrez <strong>(YearRange(-1,0))</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>




