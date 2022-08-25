---
title: Contenu Power BI Performances de rentabilité et de ventes
description: Cet article décrit ce qui est inclus dans le contenu Power BI des performances de rentabilité et de vente.
author: Henrikan
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.form: SalesProfitabilityPerformancePowerBI
ms.openlocfilehash: 77271ad9f5a1d7c131e1d7750de280f0c70daaa4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274657"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenu Power BI Performances de rentabilité et de ventes

[!include [banner](../includes/banner.md)]

Cet article décrit ce qui est inclus dans le contenu Microsoft Power BI **Performances de rentabilité et de ventes**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Performances de rentabilité et de vente** a été créé pour que les responsables des ventes surveillent les principaux éléments de mesure du produit, du profit brut et des marges bénéficiaires. Il utilise les données transactionnelles de ventes, et fournit une vue globale des chiffres de vente à l’échelle de l’entreprise et une répartition des performances de vente pour les clients et les produits.

Les états mettent l’accent sur les changements de croissance du produit et du profit au fil du temps. Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives pour chaque client et produit. En outre, les graphiques comparent le produit et la rentabilité pour différentes catégories de produits et groupes de clients. Ainsi, les responsables régionaux et de catégories peuvent identifier les meilleurs et les moins bons. Enfin, un état complet trace le produit d’un client individuel par rapport à la marge bénéficiaire. Ainsi, les responsables de compte ont une base étayée par des données pour adapter leurs efforts de vente et de marketing au profil respectif de chaque client.

Le contenu **Performances de rentabilité et de vente** permet aux directeurs commerciaux d’analyser les performances des ventes de plusieurs manières :

- Produit, en cumul annuel (par groupe de clients et clients individuels, catégories de vente et produits et géographies distincts)
- Modification du produit, en cumul annuel (par région de clientèle et catégories de vente)

La rentabilité peut être analysée de plusieurs manières :

- Marge brute et marge bénéficiaire (par groupes de clients et catégories de produit)
- Modification du profit brut, en cumul annuel
- Rentabilité de client (par produit par rapport à la marge brute)

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Performances de rentabilité et de vente** s’affiche sur la page **Performances de rentabilité et de vente** (**Ventes et marketing** \> **Recherches et états** \> **Analyse des performances de vente** \> **Performances de rentabilité et de vente**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le contenu Power BI **Performances de rentabilité et de vente** comprend un état constitué d’un ensemble d’éléments de mesure. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. Le tableau suivant offre une vue d’ensemble des visualisations proposées dans le contenu.

| Page d’état            | Graphiques                                     | Vignettes                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| Produit par client    | 10 meilleurs clients par produit                | Produit total                                           |
|                        | Produit total par groupe de clients            | Croissance du produit en cumul annuel                                      |
|                        | Produit client moyen par groupe de clients | Marge brute                                            |
|                        | Produit et profit brut par groupe de clients   |                                                         |
| Produit par produit     | Produit et profit brut par catégorie de vente   | \# total de produits                                    |
|                        | 10 meilleurs produits par produit                 | Nombre total de produit actifs et pourcentage du total |
|                        | Produit total par catégorie de vente            | Numéro de produit constituant 80 %% du produit           |
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

\* Produit cette année et l’année dernière, et croissance par catégorie de vente.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données suivantes sont utilisées pour remplir les pages d’état dans le contenu Power BI **Performances de rentabilité et de vente**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).

Les mesures agrégées de ce contenu sont le sous-ensemble de mesures agrégées qui étaient disponibles dans le cube des ventes dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3. Pour enregistrer les mesures globales du cube dans le magasin d’entités, vous devez les rendre déployables. Pour plus d’informations, voir la procédure d’enregistrement des mesures globales dans le magasin d’entités dans la publication de blog [Intégration de Power BI avec le magasin d’entités dans Dynamics](/archive/blogs/dynamicsaxbi/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update).

Les mesures globales clés suivantes de l’entité Lignes de facture sont utilisées comme base du contenu.

| Entité        | Mesures globales clés                   | Source de données pour Dynamics 365 | Champ                                        | Description                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Lignes de facture | Produit                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | Montant dans la monnaie de compte.            |
|               | Coût des marchandises vendues                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | Somme du montant du coût et de l’ajustement.    |
|               | Montant de la ligne de la commission – Devise comptable | CustInvoiceTrans             | SUM(CommissAmountMST)                        | Montant de la commission dans la devise comptable. |

Le tableau suivant indique comment les mesures globales clés de l’entité Lignes de facture sont utilisées pour créer plusieurs mesures calculées dans l’ensemble de données du contenu.

| Mesure           | Calcul                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Profit brut      | SUM(Produit – COGS – Commission –Taxe (y compris dans le montant de la ligne de la facture client))          |
| Marge brute      | SOMME(Produit brut / (Produit – Taxe (y compris dans le montant de la ligne de la facture client)))             |
| Produit l’année dernière | Produit l’année dernière = CALCULATE(SUM(’Lignes de facture’\[Produit\]), SAMEPERIODLASTYEAR(Dates\[Date\]) |

Les dimensions clés suivantes du cube des ventes sont utilisées comme filtres pour diviser les mesures agrégées, afin que vous puissiez atteindre une plus grande granularité et obtenir des aperçus analytiques plus approfondis.

| Entité           | Exemples d’attributs                               |
|------------------|------------------------------------------------------|
| Clients        | Groupes de clients, régions de clientèle, adresse, secteur |
| Produits         | Numéro de produit, Nom du produit, Nom des groupes d’articles       |
| Catégories de ventes | Noms de catégorie de vente                                 |
| Entités juridiques   | Noms d’entité juridique                                   |
| dates ;            | dates ;                                                |

Par défaut, le contenu affiche les données pour l’année civile en cours. Toutefois, vous pouvez modifier le filtre date dans la section de filtres d’état. Vous pouvez également modifier le filtre par société.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
