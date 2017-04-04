---
title: "Contenu BI de courant de gestion des coûts"
description: "Cette rubrique décrit ce qui est inclus dans le contenu BI de courant de gestion des coûts. Elle explique comment accéder aux états BI de courant, et fournit des informations sur le modèle de données et des entités qui permettent de créer le contenu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Contenu BI de courant de gestion des coûts

Cette rubrique décrit ce qui est inclus dans le contenu BI de courant de gestion des coûts. Elle explique comment accéder aux états BI de courant, et fournit des informations sur le modèle de données et des entités qui permettent de créer le contenu.

# <a name="overview"></a>Vue d'ensemble

** Gestion des coûts ** le contenu BI de courant de Microsoft est prévu pour des comptables ou des personnes de stock dans l'organisation responsable du stock. ** Gestion des coûts ** le contenu BI de courant fournit l'analyse gestionnaire dans le stock et le stock de (WIP) de travaux en cours, et la manière dont le coût des traverse par catégorie dans le temps. Ces informations peuvent également servir supplément détaillé au tableau d'analyse.

## <a name="key-measures"></a>Les mesures de clé

+ Solde d'ouverture
+ Solde de fin
+ Modification nette
+ Modifications nettes %
+ Balance âgée

## <a name="key-performance-indicators"></a>Indicateurs de performances clés
+ Rotation des stocks
+ Précision du stock

La principale source de données pour CostAggregatedCostStatementEntryEntity est la table de CostStatementCache. Cette table est gérée par la zone de cache d'ensemble de données. Par défaut, la table est mise à jour toutes les 24 heures, mais vous pouvez activer les mises à jour manuelles dans la configuration du cache de données. Vous pouvez ensuite effectuer une mise à jour manuelle dans ** gestion des coûts ** ou ** analyse des coûts ** l'espace de travail. Après la mise à jour de CostStatementCache soit exécutée, vous devez mettre à jour la connexion d'OData sur la puissance BI.com de consulter les données mises à jour sur le site. Les mesures d'écart (achat, production) dans ce contenu BI de courant concernent uniquement des articles qui valuated par la méthode de stock de coût standard. Écart de production est calculé comme la différence entre le coût actif et le coût réalisé. Écart de production est calculé lorsque l'ordre de fabrication a le statut ** terminé **. Pour plus d'informations sur l'écart de production types et la manière dont chaque type est calculé, voir [À propos de l'analyse des écarts pour un ordre de fabrication terminé] (https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Navigation dans le contenu BI de courant
** Gestion des coûts ** le contenu BI de courant est disponible dans PowerBI.com. Pour plus d'informations sur la procédure de connexion et charger votre Microsoft Dynamics 365 pour les données d'opérations, voir [contenu BI de courant d'accès de PowerBI.com] (power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le contenu BI de courant
Le contenu comprend un ensemble de pages du rapport. Chaque page sont un ensemble de mesures qui sont visualisées comme graphiques, vignettes, et tables. Le tableau suivant fournit une vue d'ensemble une visualisation dans ** gestion des coûts ** actionnent le contenu du projet BI.

| Page d'état | Graphiques | Titres |
|---|---|---|
|Combinaison de stock (par défaut par période actuelle) |Précision |Les mesures de stock :<br>Solde de fin de stock<br>Modification du réseau de stock<br>Modification % de réseau de stock<br>|
| |Rotation des stocks | |
| |Solde de fin de stock par groupe de ressources | |
| |Modification du réseau de stock par niveau 2 du niveau 1 de nom de la catégorie et le nom de la catégorie| |
| |Les écarts d'achat par groupe de ressources et la catégorie sont au niveau 3 | |
|Stock par site (valeur par défaut par période actuelle) |Solde de fin de stock par nom et le groupe de ressources de site | |
| |Tour de stock par nom et le groupe de ressources de site | |
| |Solde de fin de stock par ville et le groupe de ressources | |
|Copier le paramétrage du groupe de ressources (par défaut par période actuelle) |Les mesures de stock | |
| |Précision de stock par le montant par groupe de ressources | |
| |Tour de stock par le montant par groupe de ressources | |
|Stock YOY (année en cours par défaut {{contre:vs}} l'année précédente) |Les mesures de stock | |
| |Stock KPI :<br>Rotation des stocks<br>Précision du stock | |
| |Solde de fin de stock par année et groupe de ressources | |
| |Les écarts d'achat par année et catégorie sont au niveau 3 | |
|Stock âgé (par défaut par l'année en cours) |Stock âgé par le siège et le groupe de ressources | |
| |Stock par balance âgée le nom du trimestre et de site | |
|Combinaison de travaux en cours (par défaut par période actuelle) |Modification du réseau de travaux en cours par niveau 2 du niveau 1 de nom de la catégorie et le nom de la catégorie |Les mesures de travaux en cours de travaux en cours :<br>Solde de fin des travaux en cours<br>Modification du réseau de travaux en cours<br>Modification % de réseau de travaux en cours<br> |
| |Les écarts de production par groupe de ressources et la catégorie sont au niveau 3 | |
| |Modification du réseau de travaux en cours par groupe de ressources | |
|Travaux en cours par site (valeur par défaut par période actuelle) |Les mesures de travaux en cours de travaux en cours | |
| |La modification nette de travaux en cours par nom du site et la catégorie sont au niveau 2 | |
| |Les écarts de production par nom et la catégorie de site sont au niveau 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les opérations que les données sont utilisées pour remplir les pages de rapport dans ** gestion des coûts ** actionnent le contenu du projet BI. Ces données sont représentées comme mesures globales présentées dans le magasin d'entité, qui est une base de données SQL Microsoft qui est optimisée pour analyses. Pour plus d'informations, voir [vue d'ensemble de l'intégration BI de courant à magasin d'entité] (power-bi-integration-entity-store.md). Les mesures suivantes d'agrégat principaux sont utilisées comme base du contenu.

| Entité            | Mesure globale de clé | Source de données pour Dynamics 365 pour les opérations | Champ             | description ;                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entrées de relevé | Modification nette                | CostAggregatedCostStatementEntryEntity      | somme (montant d'\[\])   | Montant dans la devise comptable |
| Entrées de relevé | Quantité nette de modification       | CostAggregatedCostStatementEntryEntity      | somme (quantité\]\[) |                                   |

Le tableau suivant indique les mesures d'agrégat clés permettent de créer plusieurs mesures calculées dans l'ensemble du contenu.

| Mesure                                 | Procédure de la mesure est calculée                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Solde d'ouverture                       | modification\]de réseau d'\]-\[de solde de fin d'\[                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Quantité de solde d'ouverture              | Quantité\]de modification nette\]-\[de quantité de solde de fin\[                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Solde de fin                          | CALCULEZ (SOMME (montant\[\]), FILTRE (ALLEXCEPT (« calendriers fiscaux, « calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]d'entities'entity_PLACEHOLDER\[, « nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[, « description\]de Ledgers'entity_PLACEHOLDER\[, « nom\]de Ledgers'entity_PLACEHOLDER\[), « date fiscale\] de calendars' &lt;entity_PLACEHOLDER\= [MAX ('date fiscale\]de calendars'entity_PLACEHOLDER\[)))                                                                                                                                                                                           |
| Terminer la quantité de solde                 | CALCULEZ (SOMME quantité\]), FILTRE (ALLEXCEPT (« calendriers fiscaux, « calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]d'entities'entity_PLACEHOLDER\[, « nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[, « description\]de Ledgers'entity_PLACEHOLDER\[, « nom\](\[de Ledgers'entity_PLACEHOLDER\[), « date fiscale\] de calendars' &lt;entity_PLACEHOLDER\= [MAX (« date fiscale\]de calendars'entity_PLACEHOLDER\[)))                                                                                                                                                                                         |
| Mouvement le solde d'ouverture             | CALCULEZ (solde d'ouverture\]\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « stock »)                                                                                                                                                                                                                                                                                                                                                                                      |
| Solde de fin de stock                | CALCULEZ (solde\]de fin\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « stock »)                                                                                                                                                                                                                                                                                                                                                                                         |
| Modification du réseau de stock                    | CALCULEZ (modification\]de réseau\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « stock »)                                                                                                                                                                                                                                                                                                                                                                                             |
| Quantité de modification nette de stock           | CALCULEZ (quantité\]de modification nette\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « stock »)                                                                                                                                                                                                                                                                                                                                                                                    |
| Modification % de réseau de stock                  | IF (solde\] de fin de stock\[= 0, 0,\]solde de fin de stock\] / \[de modification nette de stock \[)                                                                                                                                                                                                                                                                                                                                                                           |
| Tour de stock par le montant                | si (OU (solde moyen\] de stock\[&lt;= 0, problèmes vendus ou consommés\] de stock \[&gt;= 0), 0, ABS (sorties vendus ou consommés\]de stock\[)/solde moyen\]stock\[)                                                                                                                                                                                                                                                                                                  |
| Solde moyen de stock               | () de\]de solde d'ouverture de stock\] + \[de solde de clôture de stock\[/2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problèmes vendus ou consommés de stock       | le stock\[vendu le coût\]de matériel consommé par stock\] + \[                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Coût de matériel consommé par stock        | CALCULEZ (modification\]de réseau de stock\[, « nom de la catégorie D " entries'entity_PLACEHOLDER\[de relevé - niveau 2\_\] = « ConsumedMaterialsCost »)                                                                                                                                                                                                                                                                                                                                                            |
| Stock vendu                          | CALCULEZ (modification\]de réseau de stock\[, « nom de la catégorie D " entries'entity_PLACEHOLDER\[de relevé - niveau 2\_\] = « vendu »)                                                                                                                                                                                                                                                                                                                                                                             |
| Précision de stock par le montant            | IF (solde\] de fin de stock\[&lt;= 0, IF (OU (montant compté\] 0, &lt;&gt; solde\] 0 de stock\[de fin de stock &lt; \[), 0, 1), MAX (0, (solde\] - ABS (montant compté de fin de stock\[\]de stock\[))\]/solde de fin stock\[))                                                                                                                                                                                                                              |
| Montant compté de stock                | CALCULEZ (modification\]de réseau de stock\[, « nom de la catégorie D " entries'entity_PLACEHOLDER\[de relevé - niveau 3\_\] = « espèces »)                                                                                                                                                                                                                                                                                                                                                                         |
| Stock - Balance âgée                         | si (ISBLANK (maximale ('date fiscale\]de calendars'entity_PLACEHOLDER\[)), vide (), MAX (0, MIN (Quantité âgée\]de réceptions de stock\[, quantité âgée à l'avenir\]de réceptions de fin de stock \[de solde de quantité de stock âgé\] - \[))) coût unitaire\]d'avg de stock d'\* \[                                                                                                                                                                                                                                |
| Quantité âgée des réceptions de stock       | IF (le minDate\] = \[\[minDateAllSelected\], CALCULENT (quantité\]de modification nette de stock\[, « quantité\] 0, &gt; le FILTRE (ALLEXCEPT (« calendriers fiscaux « , le calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]D " entities'entity_PLACEHOLDER\[« , le nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[« , la description de\]Ledgers'entity_PLACEHOLDER\[, le nom « \]" D entries'entity_PLACEHOLDER\[de relevé de Ledgers'entity_PLACEHOLDER\[), « date fiscale\] de calendars' &lt;entity_PLACEHOLDER\= [MAX (« date fiscale\]de calendars'entity_PLACEHOLDER\[))), CALCULEZ (quantité\]de modification nette de stock\[, « quantité\] 0 D " entries' &gt; entity_PLACEHOLDER\[de relevé)) |
| Quantité âgée de solde de clôture de stock | la quantité\] de solde de clôture de stock\[+ CALCULENT (quantité\], FILTRE (ALLEXCEPT (« calendriers fiscaux, « calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]d'entities'entity_PLACEHOLDER\[, « nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[, « description\]de Ledgers'entity_PLACEHOLDER\[, « nom\]de modification nette de stock\[de Ledgers'entity_PLACEHOLDER\[), « date fiscale\] de calendars' &gt; entity_PLACEHOLDER\[maximum (« date fiscale\]de calendars'entity_PLACEHOLDER\[)))                                                                                                                                 |
| Réceptions âgées de stock à l'avenir  | CALCULEZ (modification\]de réseau de stock\[, « montant\] 0, &gt; FILTRE (ALLEXCEPT (« calendriers fiscaux, « calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]d'entities'entity_PLACEHOLDER\[, « nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[, « description\]de Ledgers'entity_PLACEHOLDER\[, « nom\]D " entries'entity_PLACEHOLDER\[de relevé de Ledgers'entity_PLACEHOLDER\[), « date fiscale\] de calendars' &gt; entity_PLACEHOLDER\[MAX (« date fiscale\]de calendars'entity_PLACEHOLDER\[)))                                                                                                                                             |
| Coût unitaire d'avg de stock                 | CALCULEZ (quantité\], ALLEXCEPT (« calendriers fiscaux, « calendars'entity_PLACEHOLDER\[fiscal LedgerRecId\], « ID\]d'entities'entity_PLACEHOLDER\[, « nom\]D " entities'entity_PLACEHOLDER\[, « devise\]de Ledgers'entity_PLACEHOLDER\[, « description\]de Ledgers'entity_PLACEHOLDER\[, « nom\]de solde de clôture de stock\] / \[de solde de clôture de stock\[de Ledgers'entity_PLACEHOLDER\[))                                                                                                                                                                                                                 |
| Achetez des écarts                      | CALCULEZ (SOMME (montant\[\]), « nom de la catégorie D " entries'entity_PLACEHOLDER\[de relevé - niveau 2\_\] = « obtenu », « type\] de relevé D " entries'entity_PLACEHOLDER\[de relevé = « écart »)                                                                                                                                                                                                                                                                                                                              |
| Solde d'ouverture des travaux en cours                   | CALCULEZ (solde d'ouverture\]\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « travaux en cours »)                                                                                                                                                                                                                                                                                                                                                                                            |
| Solde de fin des travaux en cours                      | CALCULEZ (solde\]de fin\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « travaux en cours »)                                                                                                                                                                                                                                                                                                                                                                                               |
| Modification du réseau de travaux en cours                          | CALCULEZ (modification\]de réseau\[,\] « type de relevé D " entries'entity_PLACEHOLDER\[de relevé = « travaux en cours »)                                                                                                                                                                                                                                                                                                                                                                                                   |
| Modification % de réseau de travaux en cours                        | IF (solde\] de fin des travaux en cours de\[= 0, 0,\]solde de fin des travaux en cours de\] / \[de modification nette de travaux en cours de \[)                                                                                                                                                                                                                                                                                                                                                                                             |
| Écarts de production                    | CALCULEZ (SOMME (montant\[\]), « nom de la catégorie D " entries'entity_PLACEHOLDER\[de relevé - niveau 2\_\] = « ManufacturedCost », « type\] de relevé D " entries'entity_PLACEHOLDER\[de relevé = « écart »)                                                                                                                                                                                                                                                                                                                      |
| Nom de catégorie - niveau 1                 | basculez (nom de la catégorie\[- Niveau 1\_\], « aucun « , « aucun « , « NetSourcing « , « l'accès net « , « NetUsage « , « utiliser nette « , « NetConversionCost « , « la conversion nette de coût « , « NetCostOfGoodsManufactured « , « prennent le coût net de marchandises fabriqués « , « BeginningBalance », « solde d'ouverture »)                                                                                                                                                                                                         |
| Nom de catégorie - niveau 2                 | basculez (nom de la catégorie\[- Niveau 2\_\], « aucun « , « aucun « , « obtenu « , « obtenu « , « vendu « , « vendu « , « transféré « , « transféré « , « vendu « , « vendu « , « ConsumedMaterialsCost « , « matériel consommé coût « , « ConsumedManufacturingCost « , « fabrication consommée de coût « , « ConsumedOutsourcingCost « , « Délocalisation " consommé coût « , « ConsumedIndirectCost « , « coût indirect consommé « , « ManufacturedCost « , « a fabriqué le coût », « écarts », « écarts »)                            |
| Nom de catégorie - niveau 3                 | basculez (nom de la catégorie\[- niveau 3\_\], prix « aucun », « aucun », « en », « aucun », « ProductionPriceVariance « , « de production », Taille « QuantityVariance », « quantité », « SubstitutionVariance », « substitution », « ScrapVariance », « rebut », « LotSizeVariance « , « de lot », « RevaluationVariance « , « réévaluation « , « PurchasePriceVariance « , « prix d'achat « , « CostChangeVariance « , « modification de coûts « , « RoundingVariance « , « arrondi l'écart »)                                                   |

Les dimensions suivantes principaux sont utilisées en tant que filtres pour découper les mesures en tranches globales pour honorer une plus grande granularité et livrer des analyses analytique plus approfondie.

| Entité           | Exemples d'attributs                       |
|------------------|----------------------------------------------|
| Entités         | ID, nom                                     |
| Calendriers fiscaux | Calendrier, mois, période, trimestre, année       |
| Objectifs de l'indicateur de performance clé        | Objectif de précision de stock, Objectif de tour de stock |
| Comptabilités          | Devise, nom, description                  |
| Sites            | ID, nom, pays, ville                      |

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)



