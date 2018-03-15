---
title: "Contenu Power BI de gestion des coûts"
description: "Cette rubrique décrit les données incluses dans le contenu Power BI de gestion des coûts."
author: YuyuScheller
manager: AnnBe
ms.date: 02/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7b5c4428c8610a7b2d4cf1a28287ba2bb1f9c2ea
ms.openlocfilehash: 6739d769c3f7876f67d80554743458b0abd5aae5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/06/2018

---

# <a name="cost-management-power-bi-content"></a>Contenu Power BI de gestion des coûts

[!include[banner](../includes/banner.md)]

> [!Note]
> Ce pack de contenu a été déconseillé comme indiqué dans [Packs de contenu Power BI publiés sur PowerBI.com](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features#power-bi-content-packs-published-to-powerbicom).


Cette rubrique décrit les données incluses dans le contenu Power BI de gestion des coûts. 

Le contenu Microsoft Power BI **Gestion des coûts** est destiné aux contrôleurs de gestion ou aux responsables du stock au sein de l'organisation. Le contenu Power BI **Gestion des coûts** donne un aperçu de la gestion du stock et du stock des travaux en cours, et explique comment le coût se répercute sur les stocks par catégorie dans le temps. Les informations peuvent également être utilisées comme complément détaillé au tableau d'analyse.

## <a name="key-measures"></a>Mesures clés

+ Solde d'ouverture
+ Solde de fin
+ Modification nette
+ Modification nette en %
+ Balance âgée

## <a name="key-performance-indicators"></a>Indicateurs de performances clés
+ Rotation des stocks
+ Précision du stock

La principale source de données pour CostAggregatedCostStatementEntryEntity est la table CostStatementCache. Cette table est gérée par la structure du cache d'ensemble de données. Par défaut, la table est mise à jour toutes les 24 heures, mais vous pouvez activer les mises à jour manuelles dans la configuration du cache de données. Vous pouvez ensuite effectuer une mise à jour manuelle dans l'espace de travail **Gestion des coûts** ou **Analyse des coûts**. Une fois la mise à jour de CostStatementCache exécutée, vous devez mettre à jour la connexion OData sur Power BI.com pour consulter les données mises à jour sur le site. Les mesures d'écart (achat, production) de ce contenu Power BI concernent uniquement les articles évalués selon la méthode de stock de coût standard. L'écart de production est calculé comme la différence entre le coût actif et le coût réalisé. L'écart de production est calculé lorsque l'ordre de fabrication a le statut **Terminé**. Pour plus d'informations sur les types d'écart de production et le calcul de chaque type, voir [À propos de l'analyse des écarts pour un ordre de fabrication terminé](https://technet.microsoft.com/en-us/library/gg242850.aspx)


## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le contenu Power BI
Le contenu comprend un ensemble de pages d'état. Chaque page contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables. Le tableau suivant donne une vue d'ensemble des visualisations dans le contenu Power BI **Gestion des coûts**.

| Page d'état | Graphiques | Titres |
|---|---|---|
|Stock global (valeur par défaut par période actuelle) |Précision |Mesures de stock :<br>Solde de fin de stock<br>Modification nette du stock<br>Modification nette du stock en %<br>|
| |Rotation des stocks | |
| |Solde de fin de stock par groupe de ressources | |
| |Modification nette du stock par nom de catégorie de niveau 1 et nom de catégorie de niveau 2| |
| |Écarts d'achat par groupe de ressources et nom de catégorie de niveau 3 | |
|Stock par site (valeur par défaut par période actuelle) |Solde de fin de stock par nom de site et groupe de ressources | |
| |Rotation des stocks par nom de site et groupe de ressources | |
| |Solde de fin de stock par ville et groupe de ressources | |
|Stock par groupe de ressources (valeur par défaut par période actuelle) |Mesures de stock | |
| |Précision du stock par montant par groupe de ressources | |
| |Rotation des stocks par montant par groupe de ressources | |
|Stock en cumul annuel (année actuelle et année précédente par défaut) |Mesures de stock | |
| |Indicateurs de performance clés du stock :<br>Rotation des stocks<br>Précision du stock | |
| |Solde de fin de stock par année et groupe de ressources | |
| |Écarts d'achat par année et nom de catégorie de niveau 3 | |
|Stock - Balance âgée (valeur par défaut par année en cours) |Stock - Balance âgée par trimestre et groupe de ressources | |
| |Stock - Balance âgée par trimestre et nom de site | |
|Travaux en cours globaux (valeur par défaut par période actuelle) |Modification nette des travaux en cours par nom de catégorie de niveau 1 et nom de catégorie de niveau 2 |Mesures des travaux en cours :<br>Solde de fin des travaux en cours<br>Modification nette des travaux en cours<br>Modification nette des travaux en cours en %<br> |
| |Écarts de production par groupe de ressources et nom de catégorie de niveau 3 | |
| |Modification nette des travaux en cours par groupe de ressources | |
|Travaux en cours par site (valeur par défaut par période actuelle) |Mesures des travaux en cours | |
| |Modification nette des travaux en cours par nom de site et nom de catégorie de niveau 2 | |
| |Écarts de production par nom de site et nom de catégorie de niveau 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Finance and Operations sont utilisées pour remplir les pages d'état dans le contenu Power BI **Gestion des coûts**. Ces données sont représentées sous forme de mesures globales stockées dans le magasin d'entité, qui est une base de données SQL Microsoft optimisée pour l'analyse. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md) Les mesures globales clés suivantes sont utilisées comme base du contenu.

| Entité            | Mesure globale clé | Source de données Finance and Operations | Champ             | Description                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entrées de relevé | Modification nette                | CostAggregatedCostStatementEntryEntity      | sum(\[Montant\])   | Montant en devise comptable |
| Entrées de relevé | Quantité de modification nette       | CostAggregatedCostStatementEntryEntity      | sum(\[Quantité\]) |                                   |

Le tableau suivant indique comment les mesures globales clés sont utilisées pour créer plusieurs mesures calculées dans l'ensemble de données du contenu.

| Mesure                                 | Méthode de calcul de la mesure                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Solde d'ouverture                       | \[Solde de fin\]-\[Modification nette\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Quantité de solde d'ouverture              | \[Quantité de solde de fin\]-\[Quantité de modification nette\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Solde de fin                          | CALCULATE(SUM(\[Montant\]), FILTER(ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]), 'Calendriers fiscaux'\[Date\] &lt;= MAX('Calendriers fiscaux'\[Date\])))                                                                                                                                                                                           |
| Quantité de solde de fin                 | CALCULATE(SUM(\[Quantité\]), FILTER(ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]), 'Comptabilités'\[Date\] &lt;= MAX('Calendriers fiscaux'\[Date\])))                                                                                                                                                                                         |
| Solde d'ouverture de stock             | CALCULATE(\[Solde d'ouverture\], 'Entrées de relevé'\[Type de relevé\] = "Stock")                                                                                                                                                                                                                                                                                                                                                                                      |
| Solde de fin de stock                | CALCULATE(\[Solde de fin\], 'Entrées de relevé'\[Type de relevé\] = "Stock")                                                                                                                                                                                                                                                                                                                                                                                         |
| Modification nette du stock                    | CALCULATE(\[Modification nette\], 'Entrées de relevé'\[Type de relevé\] = "Stock")                                                                                                                                                                                                                                                                                                                                                                                             |
| Quantité de modification nette du stock           | CALCULATE(\[Quantité de modification nette\], 'Entrées de relevé'\[Type de relevé\] = "Stock")                                                                                                                                                                                                                                                                                                                                                                                    |
| Modification nette du stock en %                  | IF(\[Solde de fin de stock\] = 0, 0, \[Modification nette du stock\] / \[Solde de fin de stock\])                                                                                                                                                                                                                                                                                                                                                                           |
| Rotation des stocks par montant                | if(OR(\[Solde moyen de stock\] &lt;= 0, \[Problèmes de stock vendu ou utilisé\] &gt;= 0), 0, ABS(\[Problèmes de stock vendu ou utilisé\])/\[Solde moyen de stock\])                                                                                                                                                                                                                                                                                                  |
| Solde moyen de stock               | (\[Solde de fin de stock\] + \[Solde d'ouverture de stock\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problèmes de stock vendu ou utilisé       | \[Stock vendu\] + \[Coût des matières utilisées dans le stock\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Coût des matières utilisées dans le stock        | CALCULATE(\[Modification nette du stock\], 'Entrées de relevé'\[Nom de catégorie - niveau 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Stock vendu                          | CALCULATE(\[Modification nette du stock\], 'Entrées de relevé'\[Nom de catégorie - niveau 2\_\] = "Vendu")                                                                                                                                                                                                                                                                                                                                                                             |
| Précision du stock par montant            | IF(\[Solde de fin de stock\] &lt;= 0, IF(OR(\[Montant de stock comptabilisé\] &lt;&gt; 0, \[Solde de fin de stock\] &lt; 0), 0, 1), MAX(0, (\[Solde de fin de stock\] - ABS(\[Montant de stock comptabilisé\]))/\[Solde de fin de stock\]))                                                                                                                                                                                                                              |
| Montant de stock comptabilisé                | CALCULATE(\[Modification nette du stock\], 'Entrées de relevé'\[Nom de catégorie - niveau 3\_\] = "Comptage")                                                                                                                                                                                                                                                                                                                                                                         |
| Stock - Balance âgée                         | if(ISBLANK(max('Calendriers fiscaux'\[Date\])), blank(), MAX(0, MIN(\[Quantité de réceptions de stock\], \[Quantité de solde de fin de stock\] - \[Quantité de réceptions de stock dans le futur\]))) \* \[Coût unitaire moyen de stock\]                                                                                                                                                                                                                                |
| Quantité de réceptions de stock       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Quantité de modification nette du stock\], 'Entrées de relevé'\[Quantité\] &gt; 0, FILTER(ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]), 'Calendriers fiscaux'\[Date\] &lt;= MAX('Calendriers fiscaux'\[Date\]))), CALCULATE(\[Quantité de modification nette du stock\], 'Entrées de relevé'\[Quantité\] &gt; 0)) |
| Quantité de solde de fin de stock | \[Quantité de solde de fin de stock\] + CALCULATE(\[Quantité de modification nette du stock\], FILTER(ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]), 'Calendriers fiscaux'\[Date\] &gt; max('Calendriers fiscaux'\[Date\]) ))                                                                                                                                 |
| Réceptions de stock dans le futur  | CALCULATE(\[Modification nette du stock\], 'Entrées de relevé'\[Montant\] &gt; 0, FILTER(ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]), 'Calendriers fiscaux'\[Date\] &gt; MAX('Calendriers fiscaux'\[Date\])))                                                                                                                                             |
| Coût unitaire moyen du stock                 | CALCULATE(\[Solde de fin de stock\] / \[Quantité de solde de fin de stock\],ALLEXCEPT('Calendriers fiscaux', 'Calendriers fiscaux'\[LedgerRecId\], 'entités'\[ID\], 'entités'\[Nom\], 'Comptabilités'\[Devise\], 'Comptabilités'\[Description\], 'Comptabilités'\[Nom\]))                                                                                                                                                                                                                 |
| Écarts d'achat                      | CALCULATE(SUM(\[Montant\]), 'Entrées de relevé'\[Nom de catégorie - niveau 2\_\] = "Approvisionné", 'Entrées de relevé'\[Type de relevé\] = "Écart")                                                                                                                                                                                                                                                                                                                              |
| Solde d'ouverture des travaux en cours                   | CALCULATE(\[Solde d'ouverture\], 'Entrées de relevé'\[Type de relevé\] = "Travaux en cours")                                                                                                                                                                                                                                                                                                                                                                                            |
| Solde de fin des travaux en cours                      | CALCULATE(\[Solde de fin\], 'Entrées de relevé'\[Type de relevé\] = "Travaux en cours")                                                                                                                                                                                                                                                                                                                                                                                               |
| Modification nette des travaux en cours                          | CALCULATE(\[Modification nette\], 'Entrées de relevé'\[Type de relevé\] = "Travaux en cours")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Modification nette des travaux en cours en %                        | IF(\[Solde de fin des travaux en cours\] = 0, 0, \[Modification nette des travaux en cours\] / \[Solde de fin des travaux en cours\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Écarts de production                    | CALCULATE(SUM(\[Montant\]), 'Entrées de relevé'\[Nom de catégorie - niveau 2\_\] = "ManufacturedCost", 'Entrées de relevé'\[Type de relevé\] = "Écart")                                                                                                                                                                                                                                                                                                                      |
| Nom de catégorie - niveau 1                 | switch(\[Nom de catégorie - niveau 1\_\], "Aucun", "Aucun", "NetSourcing", "Approvisionnement net", "NetUsage", "Utilisation nette", "NetConversionCost", "Coût de conversion net", "NetCostOfGoodsManufactured", "Coût net des marchandises fabriquées", "BeginningBalance", "Solde d'ouverture")                                                                                                                                                                                                         |
| Nom de catégorie - niveau 2                 | switch(\[Nom de catégorie - niveau 2\_\], "Aucun", "Aucun", "Approvisionné", "Approvisionné", "Cédé", "Cédé", "Transféré", "Transféré", "Vendu", "Vendu", "ConsumedMaterialsCost", "Coût des matières utilisées", "ConsumedManufacturingCost", "Coût de fabrication utilisé", "ConsumedOutsourcingCost", "Coût d'externalisation utilisé", "ConsumedIndirectCost", "Coût indirect utilisé", "ManufacturedCost", "Coût de fabrication", "Écarts", "Écarts")                            |
| Nom de catégorie - niveau 3                 | switch(\[Nom de catégorie - niveau 3\_\], "Aucun", "Aucun", "Comptage", "Aucun", "ProductionPriceVariance", "Prix de production", "QuantityVariance", "Quantité", "SubstitutionVariance", "Remplacement", "ScrapVariance", "Rebut", "LotSizeVariance", "Taille de lot", "RevaluationVariance", "Réévaluation", "PurchasePriceVariance", "Prix d'achat", "CostChangeVariance", "Modification de coût", "RoundingVariance", "Écart d'arrondi")                                                   |

Les dimensions clés suivantes sont utilisées comme filtres pour diviser les mesures globales afin d'obtenir une plus grande granularité et de fournir des données d'analyse plus approfondies.

| Entité           | Exemples d'attributs                       |
|------------------|----------------------------------------------|
| Entités         | ID, nom                                     |
| Calendriers fiscaux | Calendrier, mois, période, trimestre, année       |
| Objectifs de l'indicateur de performance clé        | Objectif de précision du stock, objectif de rotation des stocks |
| Comptabilités          | Devise, nom, description                  |
| Sites            | ID, nom, pays, ville                      |






