---
title: "Contenu Power BI Analyse des dépenses d'achat"
description: "Cette rubrique décrit ce qui est inclus dans le contenu Power BI Analyse des dépenses d'achat. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: aac6439bb54b3b9cab066b06c01763e880efef8e
ms.openlocfilehash: 07b6f433a8355d7f9ed6dce8e26f78d38a86a713
ms.contentlocale: fr-fr
ms.lasthandoff: 12/18/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenu Power BI Analyse des dépenses d'achat

[!INCLUDE [banner](../includes/banner.md)]

Cette rubrique décrit ce qui est inclus dans le contenu Microsoft Power BI **Analyse des dépenses d'achat**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Analyse des dépenses d'achat** a été conçu pour aider les directeurs des achats et autres gestionnaires qui sont responsables des budgets à garder un œil sur les dépenses d'achat. Les gestionnaires peuvent analyser les dépenses d'achat des manières suivantes :

-   Achat depuis le début de l'année (par groupe de fournisseurs et fournisseurs individuels, catégorie d'approvisionnement et produits individuels et emplacement du fournisseur)
-   Changement d'achat d'une année sur l'autre (par groupe de fournisseurs et catégorie d'approvisionnement)

Le contenu utilise les données transactionnelles d'achats, et fournit une vue globale des chiffres d'achats à l'échelle de l'entreprise et une répartition des dépenses d'achat par fournisseur et produit. Les rapports mettent l'accent sur les changements dans les dépenses d'achat au fil du temps. Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit. En outre, les graphiques montrent les dépenses des différentes catégories d'approvisionnement et groupes de fournisseurs. Ainsi, les gestionnaires régionaux et de catégories peuvent utiliser les graphiques pour aider à identifier les changements dans le comportement des dépenses.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Analyse des dépenses d'achat** s'affiche sur la page **Analyse des dépenses et des achats** (**Approvisionnements** > **Recherches et états** > **Analyse des performances d'achat** > **Analyse des dépenses et des achats**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le contenu Power BI
Le contenu Power BI **Analyse des dépenses d'achat** comprend un état constitué d'un ensemble d'éléments de mesure. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. Le tableau suivant offre une vue d'ensemble des visualisations.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Page d'état</th>
<th>Graphiques</th>
<th>Vignettes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Achat par fournisseur</td>
<td><ul>
<li>Les 10 principaux vendeurs par achat (graphique à barres empilées)</li>
<li>Achat total par groupe de fournisseurs / pays / nom (graphique à secteurs)</li>
<li>Achat par groupe de fournisseurs / pays / nom (histogramme)</li>
<li>Achat moyen par groupe de fournisseurs / pays / nom (histogramme)</li>
</ul></td>
<td><ul>
<li>Total des achats</li>
<li>Croissance des achats en cumul annuel</li>
<li>Nombre total de fournisseurs</li>
<li>Nombre total de fournisseurs actifs</li>
</ul></td>
</tr>
<tr class="even">
<td>Achat par produit</td>
<td><ul>
<li>Achat par catégorie d'approvisionnement / nom du produit (histogramme)</li>
<li>Achat total par catégorie d'approvisionnement / nom du produit (graphique à secteurs)</li>
<li>Les 10 principaux produits par achat (graphique à barres empilées)</li>
</ul></td>
<td><ul>
<li>Nombre total de produits</li>
<li>Nombre total de produit actifs et pourcentage du total de produits</li>
<li>Nombre de produits constituant 80 % de l'achat</li>
</ul></td>
</tr>
<tr class="odd">
<td>Achat par période*</td>
<td><ul>
<li>Achat par mois/jour (histogramme)</li>
<li>Variation en cumul annuel des achats (graphique cascade)</li>
<li>Croissance en cumul annuel des achats totaux (histogramme)</li>
<li>Relevé d'approvisionnement (matrice)</li>
</ul></td>
<td><ul>
<li>Croissance des achats en cumul annuel</li>
<li>% de croissance des achats en cumul annuel</li>
</ul></td>
</tr>
<tr class="even">
<td>Achat par emplacement de fournisseur</td>
<td><ul>
<li>Achat par ville</li>
<li>% de croissance en cumul annuel des achats</li>
<li>Achat par pays</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Analyse des dépenses d'achat par période</td>
<td><ul>
<li>Achats de l'année en cours par mois / jour (graphique en courbes)</li>
<li>Achats de l'année en cours et de l'année dernière (graphique en courbes et histogramme)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Analyse des dépenses d'achat par fournisseur</td>
<td><ul>
<li>10 principaux achats fournisseur en % (icône conique)</li>
<li>10 premiers fournisseurs avec dépenses augmentées en cumul annuel</li>
<li>10 premiers fournisseurs avec dépenses réduites en cumul annuel</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Achats cette année et l'année dernière, et croissance par catégorie d'approvisionnement

## <a name="data-model-and-entities"></a>Modèle de données et entités
Les données suivantes sont utilisées pour remplir les pages d'état dans le contenu Power BI **Analyse des dépenses d'achat**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md)

Les mesures globales dans ce contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d'achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3. Pour enregistrer les mesures globales du cube dans le magasin d'entités, vous devez les rendre déployables. Pour plus d'informations, voir la procédure d'enregistrement des mesures globales dans le magasin d'entités dans [Vue d'ensemble de l'intégration de Power BI avec le magasin d'entités](power-bi-integration-entity-store.md). Les mesures globales clés suivantes sont disponibles directement depuis l'entité Lignes de facture et sont utilisées comme base du contenu.

| Entité        | Mesures globales clés | Source de données                                 | Champ              | Description                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Lignes de facture | Achats                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Montant dans la monnaie de compte. |

Le tableau suivant indique les mesures principales du contenu qui sont calculées à partir de l'entité Lignes de facture.

| Mesure               | Calcul                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Achats de l'année en cours | Achat de l'année en cours = SUM('Invoice lines'\[Purchase\])                                            |
| Achats l'année dernière    | Achats l'année dernière = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\])) |
| Croissance des achats en cumul annuel   | Croissance d'achat en cumul annuel = \[Purchase current year\] – \[Purchase last year\]                            |

Les dimensions clés suivantes dans le contenu sont utilisées comme filtres pour diviser les mesures globales afin d'atteindre une meilleure granularité et d'obtenir une analyse plus approfondie.

| Entité                 | Exemples d'attributs                                |
|------------------------|-------------------------------------------------------|
| Fournisseurs                | Groupes de fournisseurs, Pays ou régions des fournisseurs, Nom du fournisseur |
| Produits               | Numéro de produit, Nom du produit, Nom des groupes d'articles        |
| Catégories d'approvisionnement | Catégorie d'approvisionnement, Noms des catégories d'approvisionnement      |
| Entités juridiques         | Nom de l'entité juridique                                     |
| dates ;                  | Dates, Contrepartie de l'année                                    |

Par défaut, le contenu affiche les données pour l'année civile en cours. Toutefois, vous pouvez modifier le filtre date dans la section de filtres d'état. Vous pouvez également modifier le filtre par société.

