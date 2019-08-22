---
title: Contenu Power BI de gestion des dépenses
description: Cette rubrique décrit les données incluses dans le pack de contenu Power BI Gestion des dépenses.
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0dcb6114544b3817d8b80122a32759e67ad8dc94
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849657"
---
# <a name="expense-management-power-bi-content"></a>Contenu Power BI de gestion des dépenses

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les données incluses dans le contenu Power BI Gestion des dépenses. 

## <a name="overview"></a>Présentation
Deux packs de contenu Power BI sont disponibles pour être utilisés avec la Gestion des dépenses dans la version 8.1 et versions ultérieures. 
- Il existe un tableau de bord personnel conçu pour les employés qui soumettent des états de dépenses. 

  Ce tableau de bord est personnalisé pour fournir des informations importantes sur les montants qui ont été soumis et ne l'ont pas été, ainsi que l'historique et une analyse de l'historique des transactions de dépense. Le tableau de bord personnel est une seule page contenant les principales informations pour l'utilisateur.

- Il existe un concepteur de tableau de bord Administrateur conçu pour les employés et les responsables de la comptabilité fournisseur. Ce tableau de bord est adapté au suivi et à la génération d'états sur les dépenses générales des employés. Il fournit des éléments de mesure des dépense, telles que les dépenses qui n'ont pas été soumises, le kilométrage, et les montants moyens des états de dépenses. Il utilise des données transactionnelles et fournit une vue agrégée de la gestion des dépenses dans toutes les sociétés. Il fournit également une répartition par employé, avec la possibilité d'ajouter des données de dimension financière. Le contenu d'analyses de dépense Administrateur contient : 
  - Une page de vue d'ensemble avec les mesures principales sur les montants des dépenses et des aperçus des états des dépenses à l'état de brouillon, en cours, et terminés. 
  - Une page de statistiques d'employé pour examiner les détails concernant un employé par horaire, type de coût et groupe de statistiques. 
  - Une page de comparaison des employés pour comparer plusieurs employés au fil du temps. 

Tous les montants sont indiqués dans la devise de la société. Les données de toutes les sociétés sont affichées, mais si nécessaire vous pouvez ajouter un filtre de société. 

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Vous pouvez trouver le contenu Power BI Expense Admin Dashboard.pbix et Expense Personal Dashboard.pbix dans la bibliothèque des actifs partagés dans Microsoft Dynamics LCS (Lifecycle Services). Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
Le contenu est disponible dans l'espace de travail Gestion des dépenses comme contenu intégré de Power BI. Tout propriétaire de dépenses peut accéder à ses propres dépenses personnelles, tandis que seuls les employé et les responsables de la comptabilité fournisseur ont accès au contenu Administrateur pour afficher les données de dépenses de tous les utilisateurs.

## <a name="refreshing-the-power-bi-content"></a>Actualisation du contenu Power BI
Le contenu Power BI Gestion des dépenses nécessite que les mesures TrvBiExpenseMeasurement et BudgetActivityMeasure soient actualisées à partir du magasin des entités. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le contenu comprend un ensemble de pages d'état. Chaque page contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables. Le tableau suivant offre une vue d'ensemble des visualisations proposées dans le contenu Power BI.

**Analyses des dépenses personnelles**

| Page d'état | Visualisation                             |
|-------------|-------------------------------------------|
| Mes dépenses | Montant du kilométrage                         |
|             | États des dépenses en cours                |
|             | N° des dépenses non soumises               |
|             | Dépenses personnelles à payer              |
|             | Montant non soumis                        |
|             | Montant soumis                          |
|             | Montant en attente de remboursement             |
|             | États des dépenses avec les montants et le statut   |
|             | États des dépenses soumises mais non approuvées  |
|             | Dépenses par type de coût                     |
|             | Dépenses par marchand                      |
|             | Dépenses par dépenses traitées            |
|             | Dépenses par projet                       |
|             | Montant total des transactions au fil du temps        |

**Analyses des dépenses de l'administrateur**

| Page d'état         | Visualisation                           |           
|---------------------|-----------------------------------------|
| Vue d'ensemble des dépenses    | Montant de dépense - brouillon                   |
|                     | Nombre de lignes de dépense - brouillon           |
|                     | Lignes de dépense - brouillon                     |
|                     | Violations de stratégie pour l'état des dépenses        |
|                     | Montant restant                      |
|                     | Dépenses soumises mais non approuvées       |
|                     | Dépenses approuvées                       |
|                     | Montant total des dépenses                    |
|                     | Synthèses de l'état des dépenses                |
|                     | Dépenses par type de coût                   |
|                     | Dépenses par marchand                    |
|                     | Dépenses par employé                   |
|                     | Dépenses par projet                     |
| Comparaison des employés | Montants des dépenses                         |
|                     | Montants des dépenses au fil du temps par employé   |
| Statistiques d'employé | États des dépenses par type de coût            |
|                     | Dépenses personnelles                       |
|                     | États des dépenses de groupe de statistiques     |
