---
title: "Les ventes et les performances de rentabilité actionnent le contenu BI"
description: "Cette rubrique décrit ce qui est inclus dans Dynamics 365 pour les opérations - Les ventes et Feature Pack de contenu de performance de rentabilité pour le projet BI de courant de Microsoft. Elle explique comment accéder aux états inclus dans le pack de contenu et fournit des informations sur le modèle de données et des entités qui permettent de créer le pack de contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Les ventes et les performances de rentabilité actionnent le contenu BI

Cette rubrique décrit ce qui est inclus dans Dynamics 365 pour les opérations - Les ventes et Feature Pack de contenu de performance de rentabilité pour le projet BI de courant de Microsoft. Elle explique comment accéder aux états inclus dans le pack de contenu et fournit des informations sur le modèle de données et des entités qui permettent de créer le pack de contenu.

<a name="overview"></a>Vue d'ensemble
--------

Ce pack de contenu a été créé pour que les responsables des ventes supervisent les mesures de ventes clés du produit, du profit brut, et des marges bénéficiaires. Elle utilise des données transactionnelles de ventes de Dynamics 365 pour les opérations, et fournit une vue globale les chiffres de vente entreprise et une répartition de performances de vente pour les clients et les produits. En mettant en surbrillance change dans la croissance de produit et résultat dans le temps, des états peuvent être utilisés pour avertir les responsables sur positif ou négatif tend de clients individuels et les produits. La catégorie et les responsables régionaux le trouveront utile pour que les graphiques qui comparent le produit et la rentabilité de différents catégories de produits et groupes de clients entre eux pour choisir les retardataires et les chefs. Un état complet décrivant le produit du client individuel et la marge bénéficiaire offre aux responsables de compte une base de données indiquée pour les adapter les ventes et les efforts de marketing au profil respectif de chaque client. Les ventes et Feature Pack de contenu de performance de rentabilité permet aux responsables des ventes pour analyser les performances de vente par :

-   Produit, en cours date (par groupe de clients et les différents clients, les catégories de vente, et les différents produits et géographies)
-   Modification du produit, année du chiffre d'affaires (an par les régions et des catégories de vente par client)

La rentabilité peut être analysée par :

-   Marge brute et de marge bénéficiaire (par des groupes de clients et des catégories de vente de produit)
-   Modification de profit brut, année au-dessus an
-   Rentabilité de client (par produit et la marge brute)

## <a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
Les ventes et Feature Pack de contenu BI de courant de performance de rentabilité est publiées comme immobilisation d'implémentation aux Lifecycle Services (LCS) et peut être accessibles via Dynamics 365 pour les opérations. Pour plus d'informations sur la manière d'accéder à et lancer des états BI de courant, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>Mesures incluses dans le pack de contenu
Le pack de contenu comprend un état qui sont un ensemble de mesures visualisées comme graphiques, vignettes, et tables. Le tableau suivant fournit une vue d'ensemble une visualisation du pack de contenu.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| ** Page d'état **        | **Charts**                                 | ** Vignettes **                                               |
| Produit par le client    | Clients principal 10 par produit                | Produit total                                           |
|                        | Produit total par groupe de clients            | Croissance de produit de YOY                                      |
|                        | Produit moyen de client par groupe de clients | Marge brute                                            |
|                        | Produit et profit brut par groupe de clients   |                                                         |
| Sous-produit de produit     | Produit et profit brut par catégorie de vente   | Total \# de produits                                    |
|                        | Produits principal 10 par produit                 | Nombre total de produit actifs et pourcentage du total |
|                        | Produit total par catégorie de vente            | Numéro de produit pour le produit de 80%           |
| Produit par période\*    | Produit par mois                           | Croissance de produit de YOY                                      |
|                        | Écart de remorquage de produit, YOY             | Croissance % de produit de YOY                                    |
|                        | Écart de vente total par la zone de client    |                                                         |
| Produit par emplacement    | Produit de ventes par ville                      |                                                         |
|                        | Croissance % de produit de YOY                       |                                                         |
|                        | Produit de ventes par province                    |                                                         |
| Rentabilité client | Marge brute comparant le produit, par client   | Marge brute, marge brute, croissance de produit de YOY          |
| Analyse de rentabilité | Produit et profit brut par mois          |                                                         |
|                        | Clients principal 15 sur la marge brute           |                                                         |
|                        | Marge brute par mois, YOY                 |                                                         |

produit\* ce et la dernière année, et croissance par catégorie de vente.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les données d'opérations est utilisé pour remplir état dans Ventes et Feature Pack de contenu de performance de rentabilité. Cela est représenté comme mesures globales présentées dans le magasin d'entité, qui est une base de données SQL Microsoft optimisée pour analyses. Lisez plus {{à:about}} {{son:about}} le dans le blog [intégration BI de courant avec le magasin d'entité dans Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales dans ce pack de contenus est le sous-ensemble des mesures globales qui sont disponibles dans le cube ventes dans AX 2012 et Microsoft Dynamics® AX 2012 R3 de Dynamics. Dans le stade les mesures globales du cube dans le magasin d'entité vous devez les rendre déployables. Pour plus d'informations, voir la procédure dans la manière dont les mesures d'agrégat de stade dans le magasin d'entité dans le blog [intégration BI de courant avec le magasin d'entité dans Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures suivantes d'agrégat clé de l'entité de lignes de facture sont utilisées comme base du pack de contenu.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | ** Mesures globales de clé **               | ** Source de données pour Dynamics 365 pour les opérations ** | **Field**                                    | **Description**                          |
| Lignes de facture | Produit                                      | CustInvoiceTrans                                | SOMME (LineAmountMST)                           | Montant en devise comptable            |
|               | Coût des marchandises vendues                           | InventTrans                                     | SOMME (CostAmountPosted + CostAmountAdjustment) | Coût + ajustement                 |
|               | Montant – monnaie de compte de commission | CustInvoiceTrans                                | SOMME (CommissAmountMST)                        | Montant de la commission dans la devise comptable |

Le tableau suivant indique les mesures d'agrégat clé de l'entité de lignes de facture qui permettent de créer plusieurs mesures calculées dans l'ensemble du pack de contenu.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | ** Calculés comme **                                                                                |
| Profit brut      | SOMME (produit – COGS – commission – taxe (incluse dans le montant de la ligne de facture client))          |
| Marge brute      | SOMME (profit brut/(produit - taxe (incluse dans le montant de la ligne de facture client)))             |
| Produit l'année dernière | Le produit l'année dernière = CALCULENT (SOMME (« produit\]), SAMEPERIODLASTYEAR (date\]de lines'entity_PLACEHOLDER\[de facture\[de dates) |

Les dimensions suivantes clés dans ** cube ventes ** sont utilisées en tant que filtres pour découper les mesures en tranches globales pour honorer une plus grande granularité et analyses analytique plus approfondie.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | ** Exemples d'attributs **                           |
| Clients        | Groupes de clients, régions de client, adresse, secteur |
| Produits         | Numéro de produit, nom, nom de groupes d'articles       |
| Catégories de ventes | Noms des catégories de vente                                 |
| Entités juridiques   | Noms d'entité juridique                                   |
| dates ;            | dates ;                                                |

Par défaut, le pack de contenu affiche des données pour l'année civile en cours, mais vous pouvez ouvrir la section de filtres d'état et modifier le filtre date. Vous pouvez également modifier le filtre de la société.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)



