---
title: Contenu Power BI Gestion des coûts
description: Cet article décrit les données incluses dans le contenu Power BI Gestion des coûts.
author: JennySong-SH
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.industry: Manufacturing
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
ms.openlocfilehash: 11b414c8c352ac0a6307584ef14bcc13122f4573
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267346"
---
# <a name="cost-management-power-bi-content"></a>Contenu Power BI Gestion des coûts

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

Le contenu Microsoft Power BI **Gestion des coûts** est prévu pour des comptables de stock ou des personnes de l’organisation responsables ou intéressés par le statut du stock ou des travaux en cours, ou responsables ou intéressés par l’analyse des écarts de coûts standard.

Ce contenu Power BI fournit un format catégorisé qui vous aide à surveiller les performances des stocks et à visualiser la manière dont le coût circulent. Vous pouvez obtenir des analyses managériales telles que le taux de rotation, le nombre de jours pendant lequel le stock est disponible, la précision, et la « classification ABC » à votre niveau agrégé préféré (société, article, groupe d’articles, ou site). Les informations rendues disponibles peuvent également être utilisées comme complément détaillé au tableau d’analyse.

Le contenu Power BI est basé sur la mesure agrégée **CostObjectStatementCacheMonthly**, qui a la table **CostObjectStatementCache** comme principale source de données. Cette table est gérée par la structure du cache d’ensemble de données. Par défaut, la table est mise à jour toutes les 24 heures, mais vous modifier la fréquence de mise à jour ou activer les mises à jour manuelles dans la configuration du cache du jeu de données. Des mises à jour manuelles peuvent être effectuées dans l’espace de travail **Administration des coûts** ou l’espace de travail **Analyse des coûts**.

Après chaque mise à jour de la table **CostObjectStatementCache**, la mesure associée **CostObjectStatementCacheMonthly** doit être mise à jour avant que les données des visualisation Power BI soient mises à jour.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Le contenu Power BI de **Gestion des coûts** est affiché dans les espaces de travail **Administration des coûts** et **Analyse des coûts**.

L’espace de travail **Administration des coûts** contient les onglets suivants :

- **Vue d’ensemble** – Cet onglet affiche les données d’application.
- **Statut de la comptabilité de stock** – Cet onglet affiche le contenu Power BI.
- **Statut de la comptabilité de fabrication** – Cet onglet affiche le contenu Power BI.

L’espace de travail **Analyse des coûts** contient les onglets suivants :

- **Vue d’ensemble** – Cet onglet affiche les données d’application.
- **Analyse de la comptabilité de stock** – Cet onglet affiche le contenu Power BI.
- **Analyse de la comptabilité de fabrication** – Cet onglet affiche le contenu Power BI.
- **Analyse des écarts de coût standard** – Cet onglet affiche le contenu Power BI.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Pages d’états incluses dans le pack de contenu Power BI

Le contenu Power BI **Gestion des coûts** inclut un ensemble de pages d’état composé d’un ensemble de mesures. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. 

Les tableaux suivants fournissent une vue d’ensemble des visualisations dans le contenu Power BI **Gestion des coûts**.

### <a name="inventory-accounting-status"></a>Statut de la comptabilité de stock

| Page d’état                               | Visualisation                                   |
|-------------------------------------------|-------------------------------------------------|
| Vue d’ensemble du stock                        | Solde d’ouverture                               |
|                                           | Modification nette                                      |
|                                           | % de modification nette                                    |
|                                           | Solde de fin                                  |
|                                           | Précision du stock                              |
|                                           | Taux de rotation du stock                        |
|                                           | Nombre de jours de stock disponible                          |
|                                           | Produit actif au cours de la période                        |
|                                           | Objets de coûts actifs au cours de la période                   |
|                                           | Solde par groupe d’articles                           |
|                                           | Solde par site                                 |
|                                           | Déclaration par catégorie                           |
|                                           | Modification nette par trimestre                           |
| Vue d’ensemble du stock par site et par groupe d’articles | Précision du stock par site                      |
|                                           | Taux de rotation du stock par site                |
|                                           | Solde de fin de stock par site                |
|                                           | Précision du stock par groupe d’articles                |
|                                           | Taux de rotation du stock par groupe d’articles          |
|                                           | Solde de fin de stock par site et groupe d’articles |
| Relevé de stock                       | Relevé de stock                             |
| Relevé de stock par site               | Relevé de stock par site                     |
| Relevé de stock par hiérarchie de produits  | Relevé de stock                             |
| Relevé de stock par hiérarchie de produits  | Relevé de stock par site                     |

### <a name="manufacturing-accounting-status"></a>Statut de la comptabilité de fabrication

| Page d’état                | Visualisation                       |
|----------------------------|-------------------------------------|
| Vue d’ensemble des travaux en cours de l’année en cours           | Solde d’ouverture                   |
|                            | Modification nette                          |
|                            | % de modification nette                        |
|                            | Solde de fin                      |
|                            | Ratio chiffre d’affaires des travaux en cours                  |
|                            | Jours de travaux en cours disponibles                    |
|                            | Objet de coûts actif au cours de la période        |
|                            | Modification nette par groupe de ressources        |
|                            | Solde par site                     |
|                            | Déclaration par catégorie               |
|                            | Modification nette par trimestre               |
| relevé des travaux en cours              | Solde d’ouverture                   |
|                            | Solde de fin                      |
|                            | Relevé des travaux en cours en cours par catégorie           |
| Relevé des travaux en cours en cours par site      | Solde d’ouverture                   |
|                            | Solde de fin                      |
|                            | Relevé des travaux en cours par catégorie et par site  |
| Relevé des travaux en cours en cours par hiérarchie | Solde d’ouverture                   |
|                            | Solde de fin                      |
|                            | Relevé des travaux en cours par hiérarchie de catégories |

### <a name="inventory-accounting-analysis"></a>Analyse de la comptabilité de stock

| Page d’état        | Visualisation                                                                |
|--------------------|------------------------------------------------------------------------------|
| Détails du stock  | 10 premières ressources par solde de fin                                           |
|                    | 10 premières ressources par augmentation de modification nette                                      |
|                    | 10 premières ressources par diminution de modification nette                                      |
|                    | 10 premières ressources par taux de rotation du stock                                 |
|                    | Ressources par taux de rotation de stock bas et solde de fin au-dessus du seuil |
|                    | 10 premières ressources par précision faible                                             |
| Classification ABC | Solde de fin de stock                                                     |
|                    | Matière utilisée                                                            |
|                    | Vendu (COGS)                                                                  |
| Tendances de stock   | Solde de fin de stock                                                     |
|                    | Modification nette du stock                                                         |
|                    | Taux de rotation du stock                                                     |
|                    | Précision du stock                                                           |

### <a name="manufacturing-accounting-analysis"></a>Analyse de la comptabilité de fabrication

| Page d’état | Visualisation      |
|-------------|--------------------|
| Tendances des travaux en cours  | Solde de fin des travaux en cours |
|             | Modification nette des travaux en cours     |
|             | Ratio chiffre d’affaires des travaux en cours |

### <a name="std-cost-variance-analysis"></a>Analyse des écarts de coût standard

| Page d’état                             | Visualisation                                        |
|-----------------------------------------|------------------------------------------------------|
| Écart de prix d’achat (coût std.) année en cours | Solde d’achat                                     |
|                                         | Écart de prix d’achat                              |
|                                         | Taux d’écart de prix d’achat                        |
|                                         | Écart par groupe d’articles                               |
|                                         | Écart par site                                     |
|                                         | Prix d’achat par trimestre                            |
|                                         | Prix d’achat par trimestre et groupe d’articles             |
|                                         | 10 premières ressources par taux de prix d’achat défavorable |
|                                         | 10 premières ressources par taux de prix d’achat favorable   |
| Écart de production (coût std.) année en cours     | Coût de fabrication                                    |
|                                         | Écart de production                                  |
|                                         | Taux d’écart de production                            |
|                                         | Écart par groupe d’articles                               |
|                                         | Écart par site                                     |
|                                         | Écart de production par trimestre                       |
|                                         | Écart de production par trimestre et type d’écart     |
|                                         | 10 premières ressources par écart de production défavorable  |
|                                         | 10 premières ressources par écart de production favorable    |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données de l’application sont utilisées pour remplir les pages d’état dans le contenu Power BI **Gestion des coûts**. Ces données sont représentées sous forme de mesures globales stockées dans le magasin d’entité, qui est une base de données Microsoft SQL Server optimisée pour l’analyse. Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).

Les mesures globales clés des objets suivants sont utilisées comme base du contenu Power BI.

| Objet                          | Mesures globales clés | Source de données de finances et d’opérations | Champ               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Montant                     | CostObjectStatementCache               | Montant              |
| CostObjectStatementCacheMonthly | Quantité                   | CostObjectStatementCache               | Qté                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

Le tableau suivant montre les mesures clés calculées dans le contenu Power BI.

| Mesure                            | Calcul |
|------------------------------------|-------------|
| Solde d’ouverture                  | Solde de début = \[Solde de fin\]-\[Modification nette\] |
| Qté du solde de début             | Qté du solde de début = \[Qté solde de fin\]-\[Qté modification nette\] |
| Solde de fin                     | Solde de fin = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Qté de solde de fin                | Qté de solde de fin = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Modification nette                         | Modification nette = SUM(\[AMOUNT\]) |
| Qté modification nette                    | Qté modification nette = SUM(\[QTY\]) |
| Taux de rotation du stock par montant | Taux de rotation du stock par montant = if(OR(\[Solde moyen de stock\] \<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[Problèmes de stock vendu ou utilisé\])/\[Solde moyen de stock\]) |
| Solde moyen de stock          | Solde moyen de stock = ((\[Solde de fin\] + \[Solde de début\]) / 2) |
| Nombre de jours de stock disponible             | Nombre de jours de stock disponible = 365/CostObjectStatementEntries\[Taux de rotation du stock par montant\] |
| Précision du stock                 | Précision de l’inventaire par montant = IF(\[Solde de clôture\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[Solde de clôture\] \< 0), 0, 1), MAX(0, (\[Solde de clôture\] – ABS(\[Montant compté en stock\]))/\[Solde de clôture\])) |

Les dimensions clés suivantes sont utilisées comme filtres pour diviser les mesures globales afin d’atteindre une meilleure granularité et d’obtenir une analyse plus approfondie.


| Entité                                                  | Exemples d’attributs                          |
|---------------------------------------------------------|-------------------------------------------------|
| Produits                                                | Numéro de produit, Nom du produit, Unité, Groupes d’articles |
| Hiérarchies de catégories (affectées au rôle Gestion des coûts) | Hiérarchie de catégories, niveau de catégorie              |
| Entités juridiques                                          | Noms d’entité juridique                              |
| Calendriers fiscaux                                        | Calendrier fiscal, Année, Trimestre, Période, Mois   |
| Site                                                    | ID, Nom, Adresse, Région, Pays               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

