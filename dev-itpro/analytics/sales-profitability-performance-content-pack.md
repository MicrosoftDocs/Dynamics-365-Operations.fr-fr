---
title: "Contenu Power BI des performances de rentabilité et de vente"
description: "Cette rubrique décrit ce qui est inclus dans Dynamics 365 for Operations - Pack de contenu Performances de rentabilité et de vente pour Microsoft Power BI. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 357f7071d801b13518c83170f8d0e7946dd9dede
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenu Power BI des performances de rentabilité et de vente

[!include[banner](../includes/banner.md)]


Cette rubrique décrit ce qui est inclus dans Dynamics 365 for Operations - Pack de contenu Performances de rentabilité et de vente pour Microsoft Power BI. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="overview"></a>Vue d'ensemble
--------

Ce pack de contenu a été créé pour que les responsables des ventes surveillent les principaux éléments de mesure du produit, du profit brut et des marges bénéficiaires. Il utilise les données transactionnelles de ventes de Dynamics 365 for Operations, et fournit une vue globale des chiffres de vente à l'échelle de l'entreprise et une répartition de performances de vente pour les clients et les produits. En mettant en lumière les changements de croissance du produit et du profit au fil du temps, les états peuvent servir à alerter les responsables des tendances positives ou négatives par client et par produit, individuellement. Les responsables régionaux et de catégorie trouveront l'utilité de ces graphiques qui comparent le produit et la rentabilité pour différentes catégories de produits et groupes de clients pour identifier parmi eux les meilleurs et les moins bons. Un état complet qui trace le produit d'un client individuel par rapport à la marge bénéficiaire offre aux responsables de compte une base étayée par des données pour adapter leurs efforts de vente et de marketing au profil respectif de chaque client. Le pack de contenu Performances de rentabilité et de vente permet aux directeurs commerciaux d'analyser les performances des ventes par :

-   Produit, en cumul annuel (par groupe de clients et clients individuels, catégories de vente et produits et géographies distincts)
-   Modification du produit, en cumul annuel (par région de clientèle et catégories de vente)

La rentabilité peut être analysée par :

-   Marge brute et marge bénéficiaire (par groupes de clients et catégories de produit)
-   Modification du profit brut, en cumul annuel
-   Rentabilité de client (par produit par rapport à la marge brute)

## <a name="accessing-the-content-pack"></a>Accès au pack de contenu
Le pack de contenu Performance de rentabilité et de vente pour Power BI est publié comme élément d'implémentation dans le cycle LCS (Lifecycle Services) est est accessible à partir de Dynamics 365 for Operations. Pour plus d'informations sur l'accès et l'utilisation des états Power BI, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).
**Remarque :** le KB 4011327 doit être consulté au prélable pour ce contenu Power BI. Une fois que vous êtes connecté à Lifecycle Services, vous pouvez accéder à la Base de connaissances ici : <a href="https://fix.lcs.dynamics.com/issue/results/?q=kb4011327">https://fix.lcs.dynamics.com/issue/results/?q=kb4011327</a>.

## <a name="metrics-included-in-the-content-pack"></a>Éléments de mesures compris dans le pack de contenu
Le pack de contenu comprend un état constitué d'un ensemble d'éléments de mesure visualisés sous forme de graphiques, vignettes et tableaux. Le tableau suivant offre une vue d'ensemble des visualisations proposées dans le pack de contenu.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Page d'état**        | **Graphiques**                                 | **Vignettes**                                               |
| Produit par client    | 10 meilleurs clients par produit                | Produit total                                           |
|                        | Produit total par groupe de clients            | Croissance du produit en cumul annuel                                      |
|                        | Produit client moyen par groupe de clients | Marge brute                                            |
|                        | Produit et profit brut par groupe de clients   |                                                         |
| Produit par produit     | Produit et profit brut par catégorie de vente   | \# total de produits                                    |
|                        | 10 meilleurs produits par produit                 | Nombre total de produit actifs et pourcentage du total |
|                        | Produit total par catégorie de vente            | Numéro de produit constituant 80 % du produit           |
| Produit par période\*    | Produit par mois                           | Croissance du produit en cumul annuel                                      |
|                        | Variance du produit, en cumul annuel             | Croissance du produit en %                                    |
|                        | Variance des ventes totales par région de clientèle    |                                                         |
| Produit par emplacement    | Produit de vente par ville                      |                                                         |
|                        | Croissance du produit en %                       |                                                         |
|                        | Produit de vente par région                    |                                                         |
| Rentabilité client | Marge brute par apport au produit, par client   | Profit brut, marge brute, croissance de produit en cumul annuel          |
| Analyse de rentabilité | Produit et profit brut par mois          |                                                         |
|                        | 15 meilleurs clients par marge brute           |                                                         |
|                        | Marge brute par mois, en cumul annuel                 |                                                         |

\* Produit cette année et l'année dernière, et croissance par catégorie de vente.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Dynamics 365 for Operations sont utilisées pour remplir l'état du pack de contenu Performances de rentabilité et de vente. Elles sont représentées sous forme de mesures globales stockées dans le magasin d'entité, qui est une base de données SQL Microsoft optimisée pour l'analyse. Pour en savoir plus, lisez le blog [Intégration de Power BI avec le magasin d'entités dans Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales dans ce pack de contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube de vente dans Dynamics AX 2012 et AX 2012 R3. Pour enregistrer les mesures globales du cube dans le magasin d'entités, vous devez les rendre déployables. Pour plus d'informations, voir la procédure d'enregistrement des mesures globales dans le magasin d'entités dans le blog [Intégration de Power BI avec le magasin d'entités dans Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Les mesures globales clés suivantes de l'entité Lignes de facture sont utilisées comme base du pack de contenu.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entité**    | **Mesures globales clés**               | **Source de données pour Dynamics 365 for Operations** | **Champ**                                    | **Description**                          |
| Lignes de facture | Produit                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Montant en devise comptable            |
|               | Coût des marchandises vendues                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Montant du coût + ajustement                 |
|               | Montant de la ligne de la commission – Devise comptable | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Montant de la commission dans la devise comptable |

Le tableau suivant indique comment les mesures globales clés de l'entité Lignes de facture sont utilisées pour créer plusieurs mesures calculées dans l'ensemble de données du pack de contenu.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Mesure**       | **Calculé comme**                                                                                |
| Profit brut      | SUM(Produit – COGS – Commission –Taxe (y compris dans le montant de la ligne de la facture client)          |
| Marge brute      | SOMME(Produit brut / (Produit - Taxe (y compris dans le montant de la ligne de la facture client)))             |
| Produit l'année dernière | Produit l'année dernière = CALCULATE(SUM('Lignes de facture'\[Produit\]), SAMEPERIODLASTYEAR(Dates\[Date\]) |

Les dimensions clés suivantes dans le **Cube de vente** sont utilisées comme filtres pour diviser les mesures globales afin d'atteindre une meilleure granularité et une analyse plus approfondie.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entité**       | **Exemples d'attributs**                           |
| Clients        | Groupes de clients, régions de clientèle, adresse, secteur |
| Produits         | Numéro de produit, Nom du produit, Nom des groupes d'articles       |
| Catégories de ventes | Noms de catégorie de vente                                 |
| Entités juridiques   | Noms d'entité juridique                                   |
| dates ;            | dates ;                                                |

Par défaut, le pack de contenu affiche les données pour l'année civile en cours, mais vous pouvez ouvrir la section de filtres de l'état et modifier le filtre de date. Vous pouvez également modifier le filtre par société.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)





