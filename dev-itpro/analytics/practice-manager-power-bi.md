---
title: Contenu Power BI du gestionnaire de pratique
description: "Cette rubrique décrit les données incluses dans le contenu Power BI du gestionnaire de pratique. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Contenu Power BI du gestionnaire de pratique

[!include[banner](../includes/banner.md)]


Cette rubrique décrit ce qui est inclus dans le contenu Microsoft Power BI **Gestionnaire de pratique**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Gestionnaire de pratique** a été créé pour les gestionnaires de pratique et les chefs de projet. Il fournit des mesures clés associées aux projets sur lesquels l'organisation travaille. Le tableau de bord fournit une vue d'ensemble des projets et des clients associés. Un filtre au niveau de l'état peut être utilisé pour générer un état pour des entités juridiques spécifiques. Ce contenu Power BI extrait des données des mesures globales comptables du projet pour Microsoft Dynamics 365 for Operations.

Le contenu Power BI **Gestionnaire de pratique** contient cinq pages d'état : une page de vue d'ensemble et quatre pages qui fournissent des détails des coûts de projet, des produits, de la gestion de la valeur gagnée et des mesures horaires qui sont répartis sur différentes dimensions.

Tous les montants du contenu sont indiqués dans la devise du système. Vous pouvez définir la devise du système dans la page **Paramètres système**.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Vous trouverez le contenu Power BI **Gestionnaire de pratique** dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données Dynamics 365 for Operations, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI

Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Gestionnaire de pratique**.

| Page d'état                                          | Métriques               |
|------------------------------------------------------|-----------------------------------------------|
| Tableau de bord  | Projets créés<br>Projets estimés<br>Projets en cours<br>Nombre de projets par phase<br>Nombre de projets par ville<br>Produit réel par client<br>Marge budgétaire brute par projet<br>Vue d'ensemble de la gestion de la valeur gagnée |
| Charge                                                 | Coût réel et budgété par mois<br>Coût réel et budgété par année<br>Coût réel et budgété par catégorie<br>Coût réel par type de transaction       |
| Produit                                              | Produit réel par mois<br>Produit réel par code postal<br>Produit réel et budgété par catégorie<br>Produit réel par secteur d'activité du client        |
| EVM                                                  | Indice de performance des coûts et de l'échéancier par projet                 |
| Heures                                                | Heures utilisées facturables réelles, heures non facturables réelles et heures budgétées<br>Heures utilisées facturables réelles et heures non facturables réelles par projet<br>Heures utilisées facturables réelles et heures non facturables réelles par ressource<br>Taux d'heures facturables réelles par projet<br>Taux d'heures facturables réelles par ressource |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Vous pouvez également utiliser la fonctionnalité Exporter les données sous-jacentes pour exporter les données sous-jacentes qui sont résumées dans une visualisation.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données Dynamics 365 for Operations sont utilisées pour remplir les pages d'état dans le contenu Power BI **Gestionnaire de pratique**. Ces données sont représentées sous forme de mesures globales stockées dans le magasin d'entité, qui est une base de données SQL Microsoft optimisée pour l'analyse. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md)

Les sections suivantes expliquent les mesures globales utilisées dans chaque entité.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entité : ProjectAccountingCube_ActualHourUtilization
**Source de données** : ProjEmplTrans

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Total des heures utilisées facturables réelles |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Total du taux de charge réel             |

### <a name="entity-projectaccountingcubeactuals"></a>Entité : ProjectAccountingCube_Actuals
**Source de données** : ProjTransPosting

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Total du produit validé pour toutes les transactions |   
| ActualCost   |                             Sum(ActualCost)           |    Total du coût validé pour tous les types de transactions    |

### <a name="entity-projectaccountingcubecustomer"></a>Entité : ProjectAccountingCube_Customer
**Source de données** : CustTable

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Nombre de projets        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Nombre de projets disponibles    |


### <a name="entity-projectaccountingcubeforecasts"></a>Entité : ProjectAccountingCube_Forecasts
**Source de données** : ProjTransBudget

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Total du coût prévisionnel pour tous les types de transactions     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    Total du produit provisionné/facturé prévisionnel         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Différence entre la somme du produit prévisionnel total et la somme du coût prévisionnel total

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entité : ProjectAccountingCube_ProjectPlanCostsView
**Source de données** : Project

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Prix de revient total pour les estimations pour tous les types de transactions de projet avec des tâches planifiées |

### <a name="entity-projectaccountingcubeprojects"></a>Entité : ProjectAccountingCube_Projects
**Source de données** : Project

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Indice de performances des coûts  |ProjectAccountingCube_Projects[Valeur gagnée] / ProjectAccountingCube_Projects[Coût réel total des tâches terminées] |     Calcul de la valeur gagnée totale divisée par le coût réel total|
|  Indice de performances de l'échéancier |ProjectAccountingCube_Projects[Valeur gagnée] / ProjectAccountingCube_Projects[Coût prévisionnel total des tâches terminées]|Calcul de la valeur gagnée totale divisée par le coût prévisionnel total |
|Pourcentage de travail terminé |Pourcentage de travail terminé = ProjectAccountingCube_Projects[Coût réel total des tâches terminées] / ProjectAccountingCube_Projects[Coût réel total des tâches terminées] + ProjectAccountingCube_Projects[Coût prévisionnel total du projet] - ProjectAccountingCube_Projects [Coût prévisionnel total des tâches terminées])|Pourcentage total de travail terminé basé sur le coût réel total des tâches terminées et le coût prévisionnel du projet|
|Taux d'heures facturables réelles du projet|ProjectAccountingCube_Projects [Heures utilisées facturables réelles totales du projet /(ProjectAccountingCube_Projects [Heures utilisées facturables réelles totales du projet] + ProjectAccountingCube_Projects [Heures non facturables réelles totales du projet])|Heures facturables réelles totales basées sur les heures utilisées + charge|
|Valeur gagnée|ProjectAccountingCube_Projects[Coût prévisionnel total du projet] * ProjectAccountingCube_Projects[Pourcentage de travail terminé]|Coût prévisionnel total multiplié par le pourcentage de travail terminé|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entité : ProjectAccountingCube_TotalEstimatedCosts 
**Source de données** : ProjTable

| Mesure globale clé                | Champ                                | Description                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Prix de revient total pour les estimations pour tous les types de transactions de projet avec des tâches terminées|

## <a name="additional-resources"></a>Ressources supplémentaires

Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

- [Entités de données](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Configurer l'intégration Power BI pour les espaces de travail](configure-power-bi-integration.md)

