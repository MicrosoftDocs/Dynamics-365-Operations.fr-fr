---
title: "Définitions d'états dans le générateur d'états financiers"
description: "Cet article fournit des informations sur les définitions d'état. Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état. Une définition d'état fournit également les paramètres et les options pour la personnalisation d’un état."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96090a3ae15294d98d6207c8eb4a1e58429ca9eb
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="report-definitions-in-financial-report-designer"></a>Définitions d'états dans le générateur d'états financiers

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les définitions d'état. Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état. Une définition d'état fournit également les paramètres et les options pour la personnalisation d’un état. 

Une définition d'état est un composant d'état (ou bloc élémentaire) qui utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour créer un état. De plus, la définition de rapport comporte un grand nombre d'options et de paramètres pour personnaliser un rapport. Après avoir défini des définitions de ligne et des définitions de colonne, vous devez les combiner dans une définition d'état. À ce stade, vous définissez également d'autres aspects des définitions, comme le niveau de détail et la date de l'état. Vous pouvez ensuite enregistrer et générer l'état. Les états financiers offrent les niveaux de détail suivants :

-   Financier
-   Financier et Compte
-   Financier, Compte et Transaction

Toutefois, en fonction de la manière dont les données sont enregistrées dans le système ERP Microsoft Dynamics, les détails des transactions peuvent ne pas être disponibles dans les états.

## <a name="create-a-report-definition"></a>Créer une définition d'état
1.  Dans le générateur d'état, dans le menu **Fichier**, cliquez sur **Nouveau**, puis sélectionnez **Définition d'état**.
2.  Spécifiez les informations appropriées dans les onglets **État**, **Sortie et distribution**, **En-têtes et pieds de page** et **Paramètres**.

## <a name="contents-of-a-report-definition"></a>Contenu d'une définition d'état
Le tableau suivant décrit les onglets dans une définition d'état, ainsi que la manière dont les informations sont utilisées.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Onglet</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Etat</td>
<td>Créer un état, configurer un état, ou modifier un état existant.</td>
</tr>
<tr class="even">
<td>Sortie et distribution</td>
<td>Modifier le type de sortie et la destination de l'état.</td>
</tr>
<tr class="odd">
<td>En-têtes et pieds de page</td>
<td>Définir et mettre en forme les en-têtes et les pieds de page de l'état. Par exemple, vous pouvez ajouter du texte ou des images à l'en-tête ou au pied de page. Les états financiers prennent en charge les fichiers image .bmp, .jpg, et .png. Vous pouvez également ajouter des codes d'insertion automatique pour insérer d'autres informations, telles que le nom de la société, un nom d'état, ou un numéro de page.</td>
</tr>
<tr class="even">
<td>Paramètres</td>
<td>Spécifier des paramètres de définition d'état, tels que les paramètres suivants :
<ul>
<li>Mise en forme et arrondi des montants</li>
<li>Mise en forme des états détaillés</li>
<li>Mise en forme des arborescences de génération d'états</li>
<li>Générer un état sur les exceptions</li>
<li>Spécifier la conversion de devises</li>
<li>Sous-total et filtrage des détails du compte</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Voir également :
--------

[États financiers](financial-reporting-intro.md)




