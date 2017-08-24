---
title: Contenu Power BI pour les performances de production
description: "Cette rubrique décrit ce qui est inclus dans le contenu Power BI Performances de production. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: sericks
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1945d137b337508a1850e3e679a60487aecb6b84
ms.openlocfilehash: fa93249d2dba0e6f72d394daa6a125f29a062594
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="production-performance-power-bi-content"></a>Contenu Power BI pour les performances de production

[!include[banner](../includes/banner.md)]

Cette rubrique décrit ce qui est inclus dans le contenu Microsoft Power BI **Performances de production**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Performances de production** est destiné aux responsables de production ou aux personnes au sein de l'organisation qui sont chargées du contrôle de la production.

Les états inclus vous permettent d'utiliser Power BI pour surveiller les performances des opérations de fabrication par rapport à l'exécution dans les délais, la qualité et le coût. Les états utilisent les données transactionnelles provenant des ordres de fabrication et des lots de commandes, et fournissent une vue globale des mesures de production à l'échelle de l'entreprise et une répartition des mesures par produit et ressource.

Le contenu Power BI met l'accent sur la capacité de l'organisation à terminer la production à temps et en entier. Les performances futures sont projetées en fonction des plans de production. Les états complets fournissent des informations détaillées sur les défauts de produit qui sont causés par la production, ainsi que les taux de défectuosité pour les ressources et les opérations.

Ce contenu Power BI vous permet également d'analyser les écarts de production. Les écarts de production sont calculés comme la différence entre le coût estimé et le coût réalisé. Les écarts de production sont calculés lorsque les ordres de fabrication ou les lots de commandes atteignent l'état **Terminé**.

Le contenu Power BI **Performances de production** inclut les données provenant des ordres de fabrication et des lots de commandes. Les états n'incluent pas les données liées aux productions de kanban.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Si vous utilisez la mise à jour de juillet 2017 de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, le contenu Power BI **Performances de production** s'affiche sur la page **Performances de production** (**Contrôle de la production** > **Recherches et états** > **Analyse des performances de production** > **Performances de production**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le contenu Power BI

Le contenu Power BI **Performances de production** comprend un ensemble de pages d'état. Chaque page contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables.

Le tableau suivant offre une vue d'ensemble des visualisations incluses.

| Page d'état                                | Graphiques                                               | Vignettes |
|--------------------------------------------|------------------------------------------------------|-------|
| Performances de production                     | <ul><li>Nombre de productions par date</li><li>Nombre de productions par groupe de produits et d'articles</li><li>Nombre de productions planifiées par date</li><li>10 derniers produits à temps et complet</li></ul> | <ul><li>Nombre total de commandes</li><li>Pourcentage à temps et complet</li><li>Pourcentage incomplet</li><li>Pourcentage en avance</li><li>Pourcentage en retard</li></ul> |
| Défauts par produit                         | <ul><li>Taux de défectuosité (ppm) par date</li><li>Taux de défectuosité (ppm) par groupe de produits et d'articles</li><li>Quantité produite par date</li><li>10 premiers produits par taux effectif</li></ul> | <ul><li>Taux de défectuosité (ppm)</li><li>Quantité défectueuse</li><li>Quantité totale</li></ul> |
| Tendance des défauts par produit                   | Taux de défectuosité (ppm) par quantité produite | Taux de défectuosité (ppm) |
| Défauts par ressource                        | <ul><li>Taux de défectuosité (ppm) par date</li><li>Taux de défectuosité (ppm) par ressource et site</li><li>Taux de défectuosité (ppm) par opération</li><li>10 premières ressources par taux de défectuosité</li></ul> | Quantité défectueuse |
| Tendance des défauts par ressource                  | Taux de défectuosité (ppm) par quantité traitée | |
| Écarts de production pour le coût de revient par commande | <ul><li>Écart de production par date et type de groupe de coûts</li><li>Écart de production par site et type de groupe de coûts</li><li>10 premiers produits avec un écart de production défavorable</li><li>10 premiers produits avec un écart de production défavorable par ressource</li></ul> | <ul><li>Coût réalisé</li><li>Écart de production</li><li>Pourcentage d'écart de production</li></ul> |

## <a name="extending-the-power-bi-content"></a>Extension du contenu Power BI
Grâce aux packs de contenu disponibles dans Microsoft Dynamics Lifecycle Services (LCS), vous pouvez fournir une analyse approfondie aux personnes qui ne se connectent pas à Microsoft Dynamics 365. Vous pouvez modifier ces packs de contenu pour qu'ils permettent d'inclure d'autres rapports ou visuels, et de publier les packs de contenu via votre locataire Power BI.com pour analyse.

Le contenu Power BI **Performances de production** se trouve dans la bibliothèque de ressources partagées dans LCS. Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

Veillez à télécharger le contenu **Performances de production** qui s'applique à la version de Dynamics 365 que vous utilisez.

> [!NOTE]
> Si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations, le KB 4011327 doit être consulté au préalable pour ce contenu Power BI. Une fois que vous êtes connecté à LCS, vous pouvez accéder à la Base de connaissances à l'adresse https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données suivantes sont utilisées pour les pages d'état dans le contenu Power BI **Performances de production**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour en savoir plus sur le magasin d'entités, voir [Intégration de Power BI avec le magasin d'entités](power-bi-integration-entity-store.md).

Le tableau suivant affiche les mesures globales clés qui sont utilisées comme base du contenu Power BI.

| Entité                   | Mesures globales clés  | Source de données Finance and Operations | Champ              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

Le tableau suivant indique comment les mesures globales clés sont utilisées pour créer plusieurs mesures calculées dans l'ensemble de données du contenu.

| Mesure                  | Méthode de calcul de la mesure |
|--------------------------|-------------------------------|
| Écart de production, pourcentage   | SUM('Écart de production'[Écart de production]) / SUM('Écart de production'[Coût estimé]) |
| Tous les ordres prévisionnels       | COUNTROWS('Ordre de fabrication prévisionnel') |
| En avance                    | COUNTROWS(FILTER('Ordre de fabrication prévisionnel', 'Ordre de fabrication prévisionnel'[Date de fin prévue] \< 'Ordre de fabrication prévisionnel'[Date de besoin])) |
| En retard                     | COUNTROWS(FILTER('Ordre de fabrication prévisionnel', 'Ordre de fabrication prévisionnel'[Date de fin prévue] \> 'Ordre de fabrication prévisionnel'[Date de besoin])) |
| À temps                  | COUNTROWS(FILTER('Ordre de fabrication prévisionnel', 'Ordre de fabrication prévisionnel'[Date de fin prévue] = 'Ordre de fabrication prévisionnel'[Date de besoin])) |
| Pourcentage à temps                | IF ( 'Ordre de fabrication prévisionnel'[À temps] \<\> 0, 'Ordre de fabrication prévisionnel'[À temps], IF ('Ordre de fabrication prévisionnel'[Tous les ordres prévisionnels] \<\> 0, 0, BLANK()) ) / 'Ordre de fabrication prévisionnel'[Tous les ordres prévisionnels] |
| Terminée                | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Déclaré terminé] = TRUE)) |
| Taux de défectuosité (ppm)     | IF( 'Ordre de fabrication'[Quantité totale] = 0, BLANK(), (SUM('Ordre de fabrication'[Quantité défectueuse]) / 'Ordre de fabrication'[Quantité totale]) \* 1000000) |
| Taux de production différé  | 'Ordre de fabrication'[En retard \#] / 'Ordre de fabrication'[Terminé] |
| En avance et complet          | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Complet] = TRUE && 'Ordre de fabrication'[En avance] = TRUE)) |
| En avance \#                 | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[En avance] = TRUE)) |
| Pourcentage en avance                  | IFERROR( IF('Ordre de fabrication'[En avance \#] \<\> 0, 'Ordre de fabrication'[En avance \#], IF('Ordre de fabrication'[Nombre total de commandes] = 0, BLANK(), 0)) / 'Ordre de fabrication'[Nombre total de commandes], BLANK()) |
| Incomplet               | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Complet] = FALSE && 'Ordre de fabrication'[Déclaré terminé] = TRUE)) |
| Pourcentage incomplet             | IFERROR( IF('Ordre de fabrication'[Incomplet] \<\> 0, 'Ordre de fabrication'[Incomplet], IF('Ordre de fabrication'[Nombre total de commandes] = 0, BLANK(), 0)) / 'Ordre de fabrication'[Nombre total de commandes], BLANK()) |
| Différé               | 'Ordre de fabrication'[Déclaré terminé] = TRUE && 'Ordre de fabrication'[Valeur différée] = 1 |
| En avance                 | 'Ordre de fabrication'[Déclaré terminé] = TRUE && 'Ordre de fabrication'[Jours de retard] \< 0 |
| Complet               | 'Ordre de fabrication'[Quantité correcte] \>= 'Ordre de fabrication'[Quantité prévue] |
| Déclaré terminé                | 'Ordre de fabrication'[Valeur de l'état de production] = 5 \|\| 'Ordre de fabrication'[Valeur de l'état de production] = 7 |
| En retard et complet           | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Complet] = TRUE && 'Ordre de fabrication'[Différé] = TRUE)) |
| En retard \#                  | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Différé] = TRUE)) |
| Pourcentage en retard                   | IFERROR( IF('Ordre de fabrication'[En retard \#] \<\> 0, 'Ordre de fabrication'[En retard \#], IF('Ordre de fabrication'[Nombre total de commandes] = 0, BLANK(), 0)) / 'Ordre de fabrication'[Nombre total de commandes], BLANK()) |
| À temps et complet        | COUNTROWS(FILTER('Ordre de fabrication', 'Ordre de fabrication'[Complet] = TRUE && 'Ordre de fabrication'[Différé] = FALSE && 'Ordre de fabrication'[En avance] = FALSE)) |
| Pourcentage à temps et complet      | IFERROR( IF('Ordre de fabrication'[À temps et complet] \<\> 0, 'Ordre de fabrication'[À temps et complet], IF('Ordre de fabrication'[Terminé] = 0, BLANK(), 0)) / 'Ordre de fabrication'[Terminé], BLANK()) |
| Nombre total de commandes             | COUNTROWS('Ordre de fabrication') |
| Quantité totale           | SUM('Ordre de fabrication'[Quantité correcte]) + SUM('Ordre de fabrication'[Quantité défectueuse]) |
| Taux de défectuosité (ppm)        | IF( 'Transactions de gamme'[Quantité traitée] = 0, BLANK(), (SUM('Transactions de gamme'[Quantité défectueuse]) / 'Transactions de gamme'[Quantité traitée]) \* 1000000) |
| Taux de défectuosité mixte (ppm) | IF( 'Transactions de gamme'[Quantité mixte totale] = 0, BLANK(), (SUM('Transactions de gamme'[Quantité défectueuse]) / 'Transactions de gamme'[Quantité mixte totale]) \* 1000000) |
| Quantité traitée       | SUM('Transactions de gamme'[Quantité correcte]) + SUM('Transactions de gamme'[Quantité défectueuse]) |
| Quantité mixte totale     | SUM('Ordre de fabrication'[Quantité correcte]) + SUM('Transactions de gamme'[Quantité défectueuse]) |

Le tableau suivant affiche les dimensions clés utilisées comme filtres pour diviser les mesures globales afin d'atteindre une meilleure granularité et d'obtenir une analyse plus approfondie.

| Entité                    | Exemples d'attributs                                        |
|---------------------------|---------------------------------------------------------------|
| Date de déclaration de fin | Décalage de la date (déclaré terminé), du mois et de l'année de fin                 |
| Date de fin                | Décalage du mois de fin et mois                                  |
| Date de besoin          | Décalage du mois de la date de besoin et date de besoin            |
| Date de la transaction de gamme    | Décalage du mois de la transaction de gamme et date                       |
| Sites                     | ID de sites, nom du site, région, et ville                          |
| Entités                  | ID et nom                                                   |
| Ressources                 | ID de ressource, nom de la ressource, type de ressource et groupe de ressources |
| Produits                  | Numéro de produit, nom du produit, ID d'article et groupe d'articles         |

## <a name="additional-resources"></a>Ressources supplémentaires

Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

- [Entités de données](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities)
- [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Ajout de vignettes Power BI aux espaces de travail](/dynamics365/unified-operations/dev-itpro/analytics/configure-power-bi-integration)

