---
title: "Analyse des dépenses d&quot;achat de contenu Power BI"
description: "Cette rubrique décrit ce qui est inclus dans le pack de contenu Analyse des dépenses d&quot;achat pour Microsoft Power BI. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ad0ee95113d05710cccc1a5e9d215b38244c2047
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Analyse des dépenses d'achat de contenu Power BI

[!include[banner](../includes/banner.md)]


Cette rubrique décrit ce qui est inclus dans le pack de contenu Analyse des dépenses d'achat pour Microsoft Power BI. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="overview"></a>Vue d'ensemble
--------

Le pack de contenu des analyses des dépenses pour Microsoft Power BI a été créé pour les gestionnaires et les directeurs des achats qui sont responsables des budgets. Il a été conçu pour les aider à garder un œil sur les dépenses d'achat. Il utilise les données transactionnelles d'achats de Microsoft Dynamics 365 for Operations, et fournit une vue globale des chiffres d'achats à l'échelle de l'entreprise et une répartition des dépenses d'achat par fournisseur et produit. Les rapports mettent l'accent sur les changements dans les dépenses d'achat au fil du temps. Par conséquent, ils peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit. Les graphiques montrent les dépenses des différentes catégories d'approvisionnement et groupes de fournisseurs. Les gestionnaires régionaux et de catégories pourraient trouver utile d'utiliser ces tableaux pour aider à identifier les changements dans le comportement des dépenses. Le pack de contenu permet aux directeurs des achats et autres gestionnaires qui sont responsables des budgets d'analyser les dépenses d'achat des manières suivantes :

-   Achat depuis le début de l'année (par groupe de fournisseurs et fournisseurs individuels, catégorie d'approvisionnement et produits individuels et emplacement du fournisseur)
-   Changement d'achat d'une année sur l'autre (par groupe de fournisseurs et catégorie d'approvisionnement)

## <a name="accessing-the-content-pack"></a>Accès au pack de contenu
Le pack de contenu Analyse des dépenses d'achat est publié comme élément d'implémentation dans Microsoft Dynamics Lifecycle Services (LCS) et peut être accessible à partir de Microsoft Dynamics 365 for Operations. Pour plus d'informations sur l'accès et l'ouverture des états Power BI, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).
Remarque : le KB 4011327 doit être consulté au prélable pour ce contenu Power BI. Une fois que vous êtes connecté à Lifecycle Services, vous pouvez accéder à la Base de connaissances ici : https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="metrics-that-are-included-in-the-content-pack"></a>Métrises incluses dans le pack de contenu
Le pack de contenu Analyse des dépenses d'achat comprend un état constitué d'un ensemble d'éléments de mesure. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. Le tableau suivant offre une vue d'ensemble des visualisations proposées dans le pack de contenu.

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
Les données Dynamics 365 for Operations sont utilisées pour l'état du pack de contenu des analyses des dépenses d'achat. Ces données sont représentées sous forme de mesures globales stockées dans le magasin d'entité, qui est une base de données SQL Microsoft optimisée pour l'analyse. Pour plus d'informations sur le magasin d'entité, voir la publication de blog [Intégration de Power BI avec le magasin d'entités dans Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales dans ce pack de contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d'achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3. Pour enregistrer les mesures globales du cube dans le magasin d'entités, vous devez les rendre déployables. Pour plus d'informations, voir la procédure d'enregistrement des mesures globales dans le magasin d'entités dans la publication de blog [Intégration de Power BI avec le magasin d'entités dans Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales clés suivantes sont disponibles directement depuis l'entité Lignes de facture et sont utilisées comme base du pack de contenu.

| Entité        | Mesures globales clés | Source de données pour Dynamics 365 for Operations | Champ              | description ;                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Lignes de facture | Achats                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Montant en devise comptable |

Le tableau suivant indique les mesures principales qui sont calculées dans le pack de contenu de l'entité Lignes de facture.

| Mesure               | Calcul                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Achats de l'année en cours | Achat de l'année en cours = SUM('Invoice lines'\[Purchase\])                                            |
| Achats l'année dernière    | Achats l'année dernière = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\])) |
| Croissance des achats en cumul annuel   | Croissance d'achat en cumul annuel = \[Purchase current year\] – \[Purchase last year\]                            |

Les dimensions clés suivantes dans le pack de contenu sont utilisées comme filtres pour diviser les mesures globales afin d'atteindre une meilleure granularité et une analyse plus approfondie.

| Entité                 | Exemples d'attributs                                |
|------------------------|-------------------------------------------------------|
| Fournisseurs                | Groupes de fournisseurs, Pays ou régions des fournisseurs, Nom du fournisseur |
| Produits               | Numéro de produit, Nom du produit, Nom des groupes d'articles        |
| Catégories d'approvisionnement | Catégorie d'approvisionnement, Noms des catégories d'approvisionnement      |
| Entités juridiques         | Nom de l'entité juridique                                     |
| dates ;                  | Dates, Contrepartie de l'année                                    |

Par défaut, les données du pack de contenu pour l'année civile en cours. Toutefois, vous pouvez modifier le filtre date dans la section de filtres d'état. Vous pouvez également modifier le filtre par société.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)





