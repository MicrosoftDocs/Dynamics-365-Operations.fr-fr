---
title: "Contenu BI de courant d&quot;analyse de contrôle de gestion"
description: "Cette rubrique décrit ce qui est inclus dans le contenu BI de courant d&quot;analyse de contrôle de gestion. Elle explique comment accéder aux états BI de courant, et fournit des informations sur le modèle de données et des entités utilisés pour établir le contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>Contenu BI de courant d'analyse de contrôle de gestion

Cette rubrique décrit ce qui est inclus dans le contenu BI de courant d'analyse de contrôle de gestion. Elle explique comment accéder aux états BI de courant, et fournit des informations sur le modèle de données et des entités utilisés pour établir le contenu.

<a name="overview"></a>Vue d'ensemble
--------

** Analyse de contrôle de gestion ** le contenu BI de courant de Microsoft est prévu pour les contrôleurs ou toute personne de coût chargé d'exécuter le contrôle des coûts d'une organisation. Il inclut les mesures principales, telles que le coût, l'étendue, et le taux de coût par coût réel, coûts budgétaires, et coûts budgétaires flexibles. Elle utilise des données de transaction de contrôle de gestion dans Microsoft Dynamics 365 pour les opérations et fournit une vue globale des coûts pour l'organisation dans la devise de déclaration. Les responsables peuvent filtrer les données par objet de coût pour exécuter le contrôle des coûts de leurs unités organisationnelles, même si l'organisation peut avoir plusieurs entités juridiques. Comme ** analyse de contrôle de gestion ** le contenu BI de courant met les écarts en surbrillance entre les coûts réels et les coûts budgétés, qui peut annoncer des responsables sur le positif ou négatif tend pour ses unités opérationnelles. Les responsables peuvent en boîte le zoom avant aux hiérarchies de l'élément de coût ou aux éléments individuels de coût permet d'obtenir une analyse détaillée dans la manière dont les écarts de coûts sont survenus, puis d'agir d'effet. ** Analyse de contrôle de gestion ** le contenu BI de courant permet d'évaluer les comptables analyse la manière dont le coût traverse les objets de l'organisation. Pour en savoir plus sur le contrôle de gestion, voir [page d'accueil de contrôle de gestion] (comptabilité de /dynamics365/operations/financials/cost/contrôle de gestion - home-page.md). En définissant la sécurité de niveau d'accès dans le contrôle de gestion et en combinant avec la sécurité au niveau de la ligne en BI de courant, vous pouvez octroyer tous les propriétaires d'objet de coût que l'accès au ** analyse de contrôle de gestion ** actionnent le contenu du projet BI. Toutes les données des visualisation ensuite sont filtrées selon le niveau d'accès qui est contrôlée dans le contrôle de gestion. Pour en savoir plus sur la sécurité de niveau d'accès et de la sécurité au niveau de la ligne, voir [paramétrer la sécurité du contenu de contrôle de gestion pour BI de courant] (setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Navigation dans le contenu BI de courant
Vous pouvez trouver que ** analyse de contrôle de gestion ** actionnez le contenu BI dans la bibliothèque partagé d'immobilisations dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d'informations sur le chargement le contenu et le connecter à votre Dynamics 365 pour les données d'opérations, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md). ** Remarque : ** KB4011327 ** ** est une condition préalable ** analyse de contrôle de gestion ** au contenu BI de courant.  Après avoir signer électroniquement dans aux Lifecycle Services, vous pouvez accéder à la Base de connaissances ici : <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le contenu BI de courant
Le contenu comprend un ensemble de pages du rapport. Chaque page sont un ensemble de mesures qui sont visualisées comme graphiques, vignettes, et tables. Le tableau suivant fournit une vue d'ensemble une visualisation dans ** analyse de contrôle de gestion ** actionnent le contenu du projet BI.

| Page d'état                      | Graphique                                                                                                                         | Vignette                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Contrôle des coûts par exercice    | Coût réel et coûts budgétaires par niveau de la hiérarchie d'élément de coût                                                                   | Coût réel {{contre:vs}} le coût budgétaire                    |
|                                  | Écart de budget par niveau de la hiérarchie d'élément de coût                                                                               | Taux de coût réel {{contre:vs}} le taux de coût budgétaire          |
|                                  | Écart de budget principal 10 en pourcentage par l'élément de coût                                                                          | Ampleur réelle {{contre:vs}} l'étendue de budget          |
| Contrôle des coûts par Année en cours     | Coût réel et coûts budgétaires par période d'année civile                                                                           | Coût réel {{contre:vs}} le coût budgétaire                    |
|                                  | Écart de budget par période d'année civile                                                                                       | Taux de coût réel {{contre:vs}} le taux de coût budgétaire          |
|                                  | Écart de budget principal 10 en pourcentage par l'élément de coût                                                                          | Ampleur réelle {{contre:vs}} l'étendue de budget          |
| Taux de coût par l'exercice         | Taux de coût réel par le comportement de coût                                                                                             | Taux de coût réel {{contre:vs}} le taux de coût budgétaire          |
|                                  | Le taux de coût réel, écart du taux de coût budgétaire, pourcentage du taux de coût budgétaire et coûts budgétaires par le taux niveau de la hiérarchie d'élément de coût | Ampleur réelle {{contre:vs}} l'étendue de budget          |
|                                  | Écart de budget par niveau de la hiérarchie d'élément de coût                                                                               |                                               |
|                                  | Écart de budget principal 10 en pourcentage par l'élément de coût                                                                          |                                               |
| Budget flexible par exercice | Coût réel, coûts budgétaires et budget flexible de coûts par niveau de la hiérarchie d'élément de coût                                             | Ampleur réelle {{contre:vs}} l'étendue de budget          |
|                                  | Écart de budget et écart de budget flexible par niveau de la hiérarchie d'élément de coût                                                  | Coût réel {{contre:vs}} le coût de budget flexible           |
|                                  | Coût réel, coûts budgétaires et coût flexible par niveau de hiérarchie de comportement de coût et d'élément de coût                                  | Taux de coût réel {{contre:vs}} le taux de coût du budget flexible |
| Relevé de coût par période fiscale  | Coût réel par nom membres de dimension de niveau de la hiérarchie d'élément de coût et d'objet de coût                                             |                                               |
|                                  | Coût réel par nom membres de dimension de nom membres de dimension d'objet de coût et d'élément de coût                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les opérations que les données sont utilisées pour remplir les pages de rapport dans ** analyse de contrôle de gestion ** actionnent le contenu du projet BI. Ces données sont représentées comme mesures globales présentées dans le magasin d'entité, qui est une base de données SQL Microsoft qui est optimisée pour analyses. Pour plus d'informations, voir [vue d'ensemble de l'intégration BI de courant à magasin d'entité] (power-bi-integration-entity-store.md). Les mesures suivantes d'agrégat principaux sont utilisées comme base du contenu.

| Entité                  | Mesure globale de clé | Source de données pour Dynamics 365 pour les opérations | Champ     | description ;                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Entrées de contrôle de gestion | SOMME (montant)               | CAMDATAAggregatedCostEntry                  | Montant    | Montant dans la devise comptable de contrôle de gestion |
| Entrées statistiques     | SOMME (étendue)            | CAMDATAAggregatedStatisctialEntry           | Ampleur |                                               |

Le tableau suivant indique les mesures d'agrégat clés permettent de créer plusieurs mesures calculées dans l'ensemble du contenu.

| Mesure                                       | Procédure de la mesure est calculée                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Coût réel                                   | CALCULEZ (« mesure\]d'entries'entity_PLACEHOLDER\[de contrôle de gestion, 'VALEUR\] de versions'entity_PLACEHOLDER\[ISSOURCEVERSIONBUDGET\_de transaction = 0)            |
| Coût budgétaire                                   | CALCULEZ (« mesure\]d'entries'entity_PLACEHOLDER\[de contrôle de gestion, 'VALEUR\] de versions'entity_PLACEHOLDER\[ISSOURCEVERSIONBUDGET\_de transaction = 1)            |
| Écart de coûts budgétaires                          | coût réel\]\] - \[de coûts budgétaires\[                                                                                      |
| Pourcentage d'écart de budget                    | IF (coûts budgétaires\]\[= 0, vide (), coûts budgétaires\]\] / \[d'écart de budget \[)                                                |
| Ampleur réelle                              | CALCULEZ (« entries'entity_PLACEHOLDER\[statistique FullMagnitude\], « VALEUR\] de versions'entity_PLACEHOLDER\[ISSOURCEVERSIONBUDGET\_de transaction = 0)          |
| Ampleur de budget                              | CALCULEZ (\[FullMagnitude\], 'VALEUR\] de versions'entity_PLACEHOLDER\[ISSOURCEVERSIONBUDGET\_de transaction = 1)                               |
| Écart statistique de budget                   | étendue réelle\]\] - \[d'extension de budget\[                                                                            |
| Pourcentage statistiques d'écart de budget        | IF (étendue\] de budget\[= 0, vide (), étendue statistique\]de budget\] / \[d'écart de budget \[)                          |
| Taux de coût réel                              | IF (étendue réelle\]\[= 0, VIDE (), étendue réelle\]\] / \[de coût réel \[)                                          |
| Taux de coût du budget                              | IF (étendue\] de budget\[= 0, VIDE (), étendue\]de budget\] / \[de coûts budgétaires \[)                                          |
| Écart de taux de coût budgétaire                     | \]taux de coût réel\] - \[de taux de coût budgété\[                                                                            |
| Pourcentage d'écart de taux de coût budgétaire          | IF (coûts budgétaires\]\[= 0, vide (),\]taux de coût budgété\] / \[d'écart de taux de coût budgété \[)                                 |
| Coût budgétaire fixe                             | CALCULEZ (coûts budgétaires\]\[, 'entries'entity_PLACEHOLDER\[COSTBEHAVIOR\] de contrôle de gestion = 1)                                              |
| Coût budgétaire variable                          | CALCULEZ (coûts budgétaires\]\[, 'entries'entity_PLACEHOLDER\[COSTBEHAVIOR\] de contrôle de gestion = 2)                                              |
| Coût fixe de budget flexible                    | \[Coût budgétaire fixe\]                                                                                                  |
| Coût variable de budget flexible                 | IF (étendue\] de budget\[= 0, VIDE (), (étendue variable\]de budget\] / \[de coûts budgétaires\[) étendue réelle\]\* \[)       |
| Coût de budget flexible                          | \[est résolu le coût variable\]de budget flexible\] + \[de coûts budgétaires flexibles                                                     |
| Écart de budget flexible                      | le budget flexible\[coûte le coût réel\]\] - \[                                                                             |
| Pourcentage d'écart de budget flexible           | IF (le budget flexible\[évalue les coûts\] = 0, VIDE (), le budget flexible\] / \[d'écart de budget flexible \[évalue les coûts\])                     |
| Taux de coût de budget flexible                     | IF (l'étendue réelle\]\[= 0, VIDE (), budget flexible \[évalue les coûts\] / \[l'étendue réelle\])                                 |
| Écart de taux de coût du budget flexible            | \]taux de coût réel\] - \[de taux de coût du budget flexible\[                                                                   |
| Pourcentage d'écart de taux de coût du budget flexible | IF (taux de coût\] de budget flexible\[= 0, VIDE (), taux de coût\]de budget flexible\] / \[d'écart de taux de coût du budget flexible \[) |

Les dimensions suivantes principaux sont utilisées en tant que filtres pour découper les mesures en tranches globales pour honorer une plus grande granularité et livrer des analyses analytique plus approfondie.

| Entité                             | Exemples d'attributs                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Comptabilités de contrôle de gestion            | Comptabilité de contrôle de gestion                                                                                               |
| Unités de contrôle des coûts                 | Nom de l'unité de contrôle des coûts                                                                                               |
| Dimensions d'éléments de coût            | Nom de la dimension d'éléments de coût, le nom du membre de dimension d'élément de coût, description membres de dimension d'élément de coût          |
| Dimensions d'objets de coût             | Nom de la dimension d'objet de coût, le nom du membre de dimension d'objet de coût, description membres de dimension d'objet de coût              |
| Dimensions statistiques             | Nom statistiques de dimension, nom statistique membres de dimension, description statistique membres de dimension              |
| Hiérarchies de dimension d'objet de coût  | Nom de hiérarchie de dimension d'objet de coût, le niveau de hiérarchie de dimension d'objet de coût, arborescence de hiérarchie de dimension d'objet de coût    |
| Hiérarchies de dimension d'élément de coût | Nom de hiérarchie de dimensions d'article de coût, le niveau de hiérarchie de dimensions d'article de coût, arborescence de hiérarchie de dimensions d'article de coût |
| Hiérarchies statistiques de dimension  | Nom statistiques de hiérarchie de dimension, statistique niveau de hiérarchie de dimension, arborescence statistiques de hiérarchie de dimension    |
| Versions de transaction               | Nom de la version                                                                                                         |
| Calendriers fiscaux                   | Calendrier, description du calendrier                                                                                       |
| Explore                       | Année civile                                                                                                        |
| Périodes fiscales                     | Période d'année civile                                                                                                 |

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)
-   [Sécurité de paramétrage pour le contenu de contrôle de gestion pour BI de courant] (setup-security-cost-accounting-content-pack.md)


