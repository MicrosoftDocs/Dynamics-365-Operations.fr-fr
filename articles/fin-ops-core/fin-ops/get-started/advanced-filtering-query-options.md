---
title: Syntaxe de requête et de filtrage avancée
description: Cette rubrique décrit les options de filtrage et de requête disponibles lorsque vous utilisez la boîte de dialogue Filtre/tri avancé ou l'opérateur de correspondances dans le volet Filtre ou les filtres d'en-tête de colonne de la grille.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
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
ms.openlocfilehash: 7a525422a091efe8ea88f42e91dc52488430cfe5
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112189"
---
# <a name="advanced-filtering-and-query-syntax"></a>Syntaxe de requête et de filtrage avancée

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les options de filtrage et de requête disponibles lorsque vous utilisez la boîte de dialogue Filtre/tri avancé ou l'opérateur de **correspondances** dans le volet Filtre ou les filtres d'en-tête de colonne de la grille.

## <a name="advanced-query-syntax"></a>Syntaxe de requête avancée

<table>
<thead>
<tr>
<th>Syntaxe</th>
<th>Description du caractère</th>
<th>Description </th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>valeur</em></td>
<td>Égal à la valeur entrée</td>
<td>Tapez la valeur à rechercher.</td>
<td><strong>Smith</strong> permet de rechercher &quot;Smith&quot;.</td>
</tr>
<tr>
<td>!<em>valeur</em> (point d'exclamation)</td>
<td>Pas égal à la valeur entrée</td>
<td>Tapez un point d'exclamation, puis la valeur à exclure.</td>
<td><strong>!Smith</strong> permet de rechercher toutes les valeurs sauf &quot;Smith&quot;.</td>
</tr>
<tr>
<td><em>valeur de début</em>..<em>valeur de fin</em> (deux points)</td>
<td>Entre les deux valeurs séparées par deux points</td>
<td>Tapez la valeur de début, puis deux points, puis la valeur de fin.</td>
<td><strong>1..10</strong> permet de rechercher toutes les valeurs de 1 à 10. Cependant, dans un champ de chaîne, <strong>A..C</strong> permet de trouver toutes les valeurs commençant par &quot;A&quot; et &quot;B&quot; et les valeurs exactement égales à &quot;C&quot;. Par exemple, cette requête ne recherche pas &quot;Ca&quot;. Pour rechercher toutes les valeurs de &quot;A<em>&quot; à &quot;C</em>&quot;,tapez <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>valeur</em> (deux points)</td>
<td>Inférieur ou égal à la valeur entrée</td>
<td>Tapez deux points, puis la valeur.</td>
<td><strong>..1 000</strong> permet de rechercher les nombres inférieurs ou égaux à 1 000, par exemple &quot;100&quot;, &quot;999,95&quot; et &quot;1 000&quot;.</td>
</tr>
<tr>
<td><em>valeur</em>.. (deux points)</td>
<td>Supérieur ou égal à la valeur entrée</td>
<td>Tapez la valeur, puis deux points.</td>
<td><strong>1000..</strong> permet de rechercher les nombres supérieurs ou égaux à 1 000, par exemple &quot;1 000&quot;, &quot;1 000,01&quot; et &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>valeur</em> (signe « supérieur à »)</td>
<td>Supérieur à la valeur entrée</td>
<td>Tapez le signe « supérieur à » (<strong>&gt;</strong>), puis la valeur.</td>
<td><strong>&gt;1 000</strong> permet de rechercher les nombres supérieurs à 1 000, par &quot;1000,01&quot;, &quot;20 000&quot; et &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>valeur</em> (signe « inférieur à »)</td>
<td>Inférieur à la valeur entrée</td>
<td>Tapez le signe « inférieur à » (<strong>&lt;</strong>), puis la valeur.</td>
<td><strong>&lt;1 000</strong> permet de rechercher les nombres inférieurs à 1 000, par exemple, &quot;999,99&quot;, &quot;1&quot; et &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>valeur</em>* (astérisque)</td>
<td>Commence par la valeur entrée</td>
<td>Tapez la valeur de début, puis un astérisque (<strong>*</strong>).</td>
<td><strong>S*</strong> permet de rechercher les chaînes commençant par &quot;S&quot;, telles que &quot;Stockholm&quot;, &quot;Sydney&quot; et &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>valeur</em> (astérisque)</td>
<td>Finit par la valeur entrée</td>
<td>Tapez un astérisque, puis la valeur de fin.</td>
<td><strong>*est</strong> permet de rechercher les chaînes finissant par &quot;est&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</td>
</tr>
<tr>
<td>*<em>valeur</em>* (astérisque)</td>
<td>Contenant la valeur entrée</td>
<td>Tapez un astérisque, puis une valeur, puis un autre astérisque.</td>
<td><strong>*es*</strong> permet de rechercher les chaînes contenant &quot;es&quot;, telles que &quot;nord-est&quot; et &quot;sud-est&quot;.</td>
</tr>
<tr>
<td>? (point d'interrogation)</td>
<td>Contient un ou plusieurs caractères inconnus.</td>
<td>Tapez un point d'interrogation à la place des caractères inconnus dans la valeur.</td>
<td><strong>Sm?th</strong> permet de rechercher &quot;Smith&quot; et &quot;Smyth&quot;.</td>
</tr>
<tr>
<td><em>valeur</em>,<em>valeur</em> (virgule)</td>
<td>Mise en correspondance des valeurs séparées par des virgules</td>
<td>Tapez tous les critères et séparez-les par des virgules.</td>
<td><strong>A, D, F, G</strong> permet de rechercher &quot;A&quot;, &quot;D&quot;, &quot;F&quot; et &quot;G&quot;. <strong>10, 20, 30, 100</strong> permet de rechercher &quot;10, 20, 30 et 100&quot;.</td>
</tr>
<tr>
<td>"" (deux guillemets)</td>
<td>Correspondance avec une valeur vide</td>
<td>Tapez deux guillemets consécutifs pour filtrer les valeurs vides dans ce champ.</td>
<td>Deux guillemets consécutifs (<strong>""</strong>) permettent de rechercher des lignes sans valeur pour la colonne actuelle.</td>
</tr>
<tr>
<td>(<span class="code">Requête Finance and Operations</span>) (Requête Finance and Operations entre parenthèses)</td>
<td>Correspond à une requête définie.</td>
<td>Tapez une requête en tant qu'instruction SQL entre parenthèses à l'aide du langage de requête Finance and Operations.</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       en tant que syntaxe pour une condition de filtre sur un champ à partir de la source de données racine ainsi qu'un champ d'une autre source de données (pour la page Tous les clients)</td>
</tr>
<tr>
<td>Ma</td>
<td>Date du jour</td>
<td>Tapez <strong>T</strong>.</td>
<td><strong>T</strong> correspond à la date du jour.</td>
</tr>
<tr>
<td>(methodName(parameters)) (méthode <strong>SysQueryRangeUtil</strong> entre parenthèses)</td>
<td>Mise en correspondance de la valeur ou de la plage de valeurs spécifiées par les paramètres de la méthode <strong>SysQueryRangeUtil</strong></td>
<td>Entrez une méthode <strong>SysQueryRangeUtil</strong> dont les paramètres spécifient la valeur ou la plage de valeurs.</td>
<td>
<ol>
<li>Cliquez sur <strong>Comptabilité client</strong> &gt; <strong>Factures</strong> &gt; <strong>Factures client en cours</strong>.</li>
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
<thead>
<tr>
<th>Méthode</th>
<th>Description</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr>
<td>Jour (_relativeDays=0)</td>
<td>Permet de rechercher une date par rapport à la date de la session. Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</td>
<td>
<ul>
<li><strong>Le jour suivant</strong> – Entrez <strong>(Day(1))</strong>.</li>
<li><strong>Le jour même</strong> – Entrez <strong>(Day(0))</strong></li>
<li><strong>La veille</strong> – Entrez <strong>(Day(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Permet de rechercher une plage de dates par rapport à la date de la session. Les valeurs positives indiquent les dates à venir, et les valeurs négatives indiquent les dates passées.</td>
<td>
<ul>
<li><strong>Les 30 derniers jours</strong> – Entrez <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>Les 30 jours précédents et suivants</strong> – Entrez <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Permet de rechercher toutes les dates après la date relative spécifiée.</td>
<td>
<ul>
<li><strong>Plus de 30 jours à compter de maintenant</strong> – Entrez <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Permet de rechercher toutes les entrées de date/heure après l'heure actuelle.</td>
<td>
<ul>
<li><strong>Toutes les dates/heures à venir</strong> – Entrez <strong>(GreaterThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Permet de rechercher toutes les dates avant la date relative spécifiée.</td>
<td>
<ul>
<li><strong>Moins de sept jours à compter de maintenant</strong> – Entrez <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Permet de rechercher toutes les entrées de date/heure avant l'heure actuelle.</td>
<td>
<ul>
<li><strong>Toutes les dates/heures passées</strong> – Entrez <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Permet de rechercher une plage de dates, en fonction des mois relatifs au mois actuel.</td>
<td>
<ul>
<li><strong>Deux mois précédents</strong> – Entrez <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Trois mois suivants</strong> – Entrez <strong>(MonthRange(0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Permet de rechercher une plage de dates, en fonction des années relatives à l'année actuelle.</td>
<td>
<ul>
<li><strong>Année suivante</strong> – Entrez <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Année précédente</strong> – Entrez <strong>(YearRange(-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>
