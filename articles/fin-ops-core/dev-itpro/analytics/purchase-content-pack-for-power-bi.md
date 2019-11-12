---
title: Contenu Power BI Analyse des dépenses et des achats
description: Cette rubrique décrit ce qui est inclus dans le contenu Power BI Analyse des dépenses d'achat. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d25bacc2ec1f8e13376b96e188b099a184f7f8c6
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569130"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Contenu Power BI Analyse des dépenses et des achats

[!include [banner](../includes/banner.md)]

Cette rubrique décrit ce qui est inclus dans le contenu Power BI **Analyse des dépenses d'achat**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Analyse des dépenses d'achat** a été conçu pour aider les directeurs des achats et autres gestionnaires qui sont responsables des budgets à effectuer le suivi des dépenses d'achat. Les gestionnaires peuvent analyser les dépenses d'achat des manières suivantes :

- Achat depuis le début de l'année (par groupe de fournisseurs et fournisseurs individuels, catégorie d'approvisionnement et produits individuels et emplacement du fournisseur)
- Changement d'achat d'une année sur l'autre (par groupe de fournisseurs et catégorie d'approvisionnement)

Le contenu utilise les données transactionnelles d'achats, et fournit une vue globale des chiffres d'achats à l'échelle de l'entreprise et une répartition des dépenses d'achat par fournisseur et produit. Les rapports mettent l'accent sur les changements dans les dépenses d'achat au fil du temps. Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit. En outre, les graphiques montrent les dépenses des différentes catégories d'approvisionnement et groupes de fournisseurs. Ainsi, les gestionnaires régionaux et de catégories peuvent utiliser les graphiques pour aider à identifier les changements dans le comportement des dépenses.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Analyse des dépenses d'achat** s'affiche sur la page **Analyse des dépenses et des achats** (**Approvisionnements** \> **Recherches et états** \> **Analyse des performances d'achat** \> **Analyse des dépenses et des achats**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le pack de contenu Power BI **Analyse des dépenses d'achat** comprend un état constitué d'un ensemble d'éléments de mesure. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. 

Les sections suivantes offrent une vue d'ensemble des visualisations.

### <a name="purchase-by-vendor-report-page"></a>Page État des achats par fournisseur
**Graphiques**
- Les 10 principaux vendeurs par achat (graphique à barres empilées)
- Achat total par groupe de fournisseurs / pays / nom (graphique à secteurs)
- Achat par groupe de fournisseurs / pays / nom (histogramme)
- Achat moyen par groupe de fournisseurs / pays / nom (histogramme)

**Vignettes**
- Total des achats
- Croissance des achats en cumul annuel
- Nombre total de fournisseurs
- Nombre total de fournisseurs actifs

**Exemple**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Page État des achats par produit

**Graphiques**
- Achat par catégorie d'approvisionnement / nom du produit (histogramme)
- Achat total par catégorie d'approvisionnement / nom du produit (graphique à secteurs)
- Les 10 principaux produits par achat (graphique à barres empilées)

**Vignettes**
- Nombre total de produits</li>
- Nombre total de produit actifs et pourcentage du total de produits
- Nombre de produits constituant 80 % de l'achat

**Exemple**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Page État des achats par période
Cette page affiche les achats de cette année et de l'année dernière, et la croissance par catégorie d'approvisionnement.

**Graphiques** 
- Achat par mois/jour (histogramme)
- Variation en cumul annuel des achats (graphique cascade)
- Croissance en cumul annuel des achats totaux (histogramme)
- Relevé d'approvisionnement (matrice)

**Vignettes**
- Croissance des achats en cumul annuel
- % de croissance des achats en cumul annuel

**Exemple**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Page État des achats par emplacement de fournisseur

**Graphiques**
- Achat par ville
- % de croissance en cumul annuel des achats
- Achat par pays

**Exemple**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Page État des analyses des dépenses d'achat par période

**Graphiques** 
- Achats de l'année en cours par mois / jour (graphique en courbes)
- Achats de l'année en cours et de l'année dernière (graphique en courbes et histogramme)

**Exemple**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Page État des analyses des dépenses d'achat par fournisseur

**Graphiques** 
- 10 principaux achats fournisseur en % (icône conique)
- 10 premiers fournisseurs avec dépenses augmentées en cumul annuel
- 10 premiers fournisseurs avec dépenses réduites en cumul annuel

**Exemple :** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Modèle de données et entités
Les données suivantes sont utilisées pour remplir les pages d'état dans le contenu Power BI **Analyse des dépenses d'achat**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md).

Les mesures globales dans ce pack de contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d'achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3. Pour enregistrer les mesures globales du cube dans le magasin d'entités, vous devez les rendre déployables. Pour plus d'informations, voir la procédure d'enregistrement des mesures globales dans le magasin d'entités dans [Vue d'ensemble de l'intégration de Power BI avec le magasin d'entités](power-bi-integration-entity-store.md). Les mesures globales clés suivantes sont disponibles directement depuis l'entité Lignes de facture et sont utilisées comme base du contenu.

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
