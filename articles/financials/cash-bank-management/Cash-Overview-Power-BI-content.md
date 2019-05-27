---
title: Contenu Power BI Vue d'ensemble des disponibilités
description: Cette rubrique décrit le contenu Power BI Vue d'ensemble des disponibilités. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5dccb5c5c6c336607603dfc7a935c039e5ac4aa5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568915"
---
# <a name="cash-overview-power-bi-content"></a>Contenu Power BI Vue d'ensemble des disponibilités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Vue d'ensemble des disponibilités**. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Vue d'ensemble des disponibilités** a été créé pour les personnes responsables de la trésorerie dans leur organisation. Le contenu Power BI **Vue d'ensemble des disponibilités** fournit une visibilité dans votre flux de trésorerie. Il fournit également des prévisions qui vous aideront à prendre les meilleures décisions et donc d'améliorer la santé de votre flux de trésorerie. Vous pouvez analyser les disponibilités par entité juridique, la devise, et le compte bancaire pour obtenir une meilleure compréhension des excédents et des déficits.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Les états du contenu Power BI **Vue d'ensemble des disponibilités** s'affichent dans les espaces de travail **Vue d'ensemble des disponibilités** et **Gestion des banques**.

Pour afficher les états de prévisions de flux de trésorerie avec des données, vous devez exécuter le processus de calcul de prévision à l'aide de la fonction **Calculer les prévisions de flux de trésorerie** de la zone de gestion bancaire et de liquidités.  Il doit être terminé pour chaque société incluse dans la prévision.  Vous devez actualiser la mesure de regroupement LedgerCovLiquidityMeasurement sur la page **Magasin des entités**.  

À des fins de démonstration, vous pouvez ajouter des données de démonstration de prévisions de flux de trésorerie à l'aide de la page **Générer des données** du module de données de démonstration.  Ce script insèrera des données dans des tables de prévisions de flux de trésorerie pour renseigner rapidement les informations nécessaires pour les rapports.  Ce module est uniquement disponible si vous avez le modèle de suite de données de démonstration déployé dans l'environnement. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI
Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Vue d'ensemble des disponibilités**.

| Etat                                | Sommaire |
|---------------------------------------|----------|
| Vue d'ensemble des disponibilités - toutes les sociétés         | <ul><li>Encaissements et décaissements dans la devise système</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Vue d'ensemble des disponibilités - société actuelle       | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise comptable</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Prévisions du flux de trésorerie – Toutes les sociétés    | <ul><li>Encaissements et décaissements dans la devise système</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions de flux de trésorerie - devise de la société | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions des devises                     | <ul><li>Soldes de devise prévus</li><li>Synthèse quotidienne des devises</li><li>Détails des prévisions</li></ul> |
| Soldes bancaires                         | <ul><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li><li>Solde par compte bancaire</li><li>Solde par devise</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Le tableau suivant indique les entités sur lesquelles le contenu Power BI **Vue d'ensemble des disponibilités** est basé.

| Entité                                                                          | Sommaire |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Sociétés selon lesquelles filtrer les états |
| LedgerCovLiquidityMeasurement\_Date                                             | Dates selon lesquelles filtrer les états |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Solde bancaire réel et dernier solde bancaire prévu |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Détails de transaction prévus |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Synthèse des encaissements, décaissements et soldes en utilisant la devise comptable de chaque société |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Synthèse des encaissements, décaissements et soldes en utilisant la devise système de toutes les sociétés |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Synthèse des montants de transactions nets et solde des devises en utilisant la devise de transaction |


