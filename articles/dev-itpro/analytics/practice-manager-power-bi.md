---
title: Contenu Power BI Gestionnaire de pratique
description: Cette rubrique décrit les données incluses dans le contenu Power BI du gestionnaire de pratique. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: KimANelson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c526bc42595c20024016d0d7da78b8638b0daa4b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850095"
---
# <a name="practice-manager-power-bi-content"></a>Contenu Power BI Gestionnaire de pratique

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les données incluses dans le contenu Power BI **Gestionnaire de pratique**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Gestionnaire de pratique** a été créé pour les gestionnaires de pratique et les chefs de projet. Il fournit des mesures clés associées aux projets sur lesquels l'organisation travaille. Le tableau de bord fournit une vue d'ensemble des projets et des clients associés. Un filtre au niveau de l'état peut être utilisé pour générer un état pour des entités juridiques spécifiques. Ce contenu Power BI extrait des données des mesures globales comptables du projet.

Le contenu Power BI **Gestionnaire de pratique** contient cinq pages d'état : une page de vue d'ensemble et quatre pages qui fournissent des détails des coûts de projet, des produits, de la gestion de la valeur gagnée et des mesures horaires qui sont répartis sur différentes dimensions.

Tous les montants du contenu sont indiqués dans la devise du système. Vous pouvez définir la devise du système dans la page **Paramètres système**.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Le contenu Power BI **Gestionnaire de pratique** s'affiche dans l'espace de travail **Gestion de projets**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI

Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Gestionnaire de pratique**.

| Page d'état       | Métriques |
|-------------------|---------|
| Vue d'ensemble des projets | <ul><li>Projets créés</li><li>Projets estimés</li><li>Projets en cours</li><li>Produit réel par client</li><li>Marge budgétaire brute par projet</li><li>Vue d'ensemble de la gestion de la valeur gagnée</li></ul> |
| Charge              | <ul><li>Coût réel et budgété par mois</li><li>Coût réel et budgété par année</li><li>Coût réel et budgété par catégorie</li><li>Coût réel par type de transaction</li></ul> |
| Produit           | <ul><li>Produit réel par mois</li><li>Produit réel par code postal</li><li>Produit réel et budgété par catégorie</li><li>Produit réel par secteur d'activité du client</li></ul> |
| EVM               | Indice de performance des coûts et de l'échéancier par projet |
| Heures             | <ul><li>Heures utilisées facturables réelles, heures non facturables réelles et heures budgétées</li><li>Heures utilisées facturables réelles et heures non facturables réelles par projet</li><li>Heures utilisées facturables réelles et heures non facturables réelles par ressource</li><li>Taux d'heures facturables réelles par projet</li><li>Taux d'heures facturables réelles par ressource</li></ul> |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Vous pouvez également utiliser la fonctionnalité Exporter les données sous-jacentes pour exporter les données sous-jacentes qui sont résumées dans une visualisation.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données suivantes sont utilisées pour remplir les pages d'état dans le contenu Power BI **Gestionnaire de pratique**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md).

Les sections suivantes décrivent les mesures globales utilisées dans chaque entité.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Entité : ProjectAccountingCube\_ActualHourUtilization
**Source de données :** ProjEmplTrans

| Mesure globale clé      | Champ                              | Description |
|--------------------------------|------------------------------------|-------------|
| Heures utilisées facturables réelles | Sum(ActualUtilizationBillableRate) | Total des heures utilisées facturables réelles. |
| Heures de la charge facturable réelles   | Sum(ActualBurdenBillableRate)      | Total du taux de charge réel. |

### <a name="entity-projectaccountingcube_actuals"></a>Entité : ProjectAccountingCube\_Actuals
**Source de données :** ProjTransPosting

| Mesure globale clé | Champ              | Description |
|---------------------------|--------------------|-------------|
| Produit réel            | Sum(ActualRevenue) | Total du produit validé pour toutes les transactions. |
| Coût réel               | Sum(ActualCost)    | Total du coût validé pour tous les types de transactions. |

### <a name="entity-projectaccountingcube_customer"></a>Entité : ProjectAccountingCube\_Customer
**Source de données :** CustTable

| Mesure globale clé | Champ                                             | Description  |
|---------------------------|---------------------------------------------------|-------------|
| Nombre de projets        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | Nombre de projets disponibles. |

### <a name="entity-projectaccountingcube_forecasts"></a>Entité : ProjectAccountingCube\_Forecasts
**Source de données :** ProjTransBudget

| Mesure globale clé | Champ                  | Description |
|---------------------------|------------------------|-------------|
| Coût budgétaire               | Sum(BudgetCost)        | Total du coût prévisionnel pour tous les types de transactions. |
| Produit budgété            | Sum(BudgetRevenue)     | Total du produit provisionné/facturé prévisionnel. |
| Marge budgétaire brute       | Sum(BudgetGrossMargin) | Différence entre la somme du produit prévisionnel total et la somme du coût prévisionnel total. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Entité : ProjectAccountingCube\_ProjectPlanCostsView
**Source de données :** Project

| Mesure globale clé | Champ                    | Description |
|---------------------------|--------------------------|-------------|
| Coût planifié              | Sum(SumOfTotalCostPrice) | Prix de revient total pour les estimations pour tous les types de transactions de projet avec des tâches planifiées. |

### <a name="entity-projectaccountingcube_projects"></a>Entité : ProjectAccountingCube\_Projects
**Source de données :** Project

| Mesure globale clé    | Champ | Description  |
|------------------------------|-------|-------------|
| Indice de performances des coûts       | ProjectAccountingCube\_Projects\[Valeur gagnée\] ÷ ProjectAccountingCube\_Projects\[Coût réel total des tâches terminées\] | Calcul de la valeur gagnée totale divisée par le coût réel total. |
| Indice de performances de l'échéancier   | ProjectAccountingCube\_Projects\[Valeur gagnée\] ÷ ProjectAccountingCube\_Projects\[Coût prévisionnel total des tâches terminées\] | Calcul de la valeur gagnée totale divisée par le coût prévu total. |
| Pourcentage de travail terminé | Pourcentage de travail terminé = ProjectAccountingCube\_Projects\[Coût réel total des tâches terminées\] ÷ (ProjectAccountingCube\_Projects\[Coût réel total des tâches terminées\] + ProjectAccountingCube\_Projects\[Coût prévisionnel total du projet\] – ProjectAccountingCube\_Projects\[Coût prévisionnel total des tâches terminées\]) | Pourcentage total de travail terminé basé sur le coût réel total des tâches terminées et le coût prévisionnel du projet. |
| Taux d'heures facturables réelles  | ProjectAccountingCube\_Projects\[Heures utilisées facturables réelles totales du projet\] ÷(ProjectAccountingCube\_Projects\[Heures utilisées facturables réelles totales du projet\] + ProjectAccountingCube\_Projects\[Heures non facturables réelles totales du projet\]) | Le nombre total d'heures facturables réelles, en fonction des heures d'utilisation et des heures de charge. |
| Valeur gagnée                 | ProjectAccountingCube\_Projects\[Coût prévisionnel total du projet\] × ProjectAccountingCube\_Projects\[Pourcentage de travail terminé\] | Coût prévisionnel total multiplié par le pourcentage de travail terminé. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Entité : ProjectAccountingCube\_TotalEstimatedCosts 
**Source de données :** ProjTable

| Mesure globale clé       | Champ               | Description |
|---------------------------------|---------------------|-------------|
| Coût prévisionnel de l'activité terminée | Sum(TotalCostPrice) | Prix de revient total pour les estimations pour tous les types de transactions de projet avec des tâches terminées. |
