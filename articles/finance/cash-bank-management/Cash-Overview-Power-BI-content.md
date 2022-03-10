---
title: Contenu Power BI Vue d’ensemble des disponibilités
description: Cette rubrique décrit le contenu Power BI Vue d’ensemble des disponibilités. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: saraschi2
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3f7e0c792df8519f3bcb2ade2e29cc4c5c8e4730
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986406"
---
# <a name="cash-overview-power-bi-content"></a>Contenu de Power BI Vue d’ensemble des disponibilités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Vue d’ensemble des disponibilités**. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Vue d’ensemble des disponibilités** a été créé pour les personnes responsables de la trésorerie dans leur organisation. Le contenu Power BI **Vue d’ensemble des disponibilités** fournit une visibilité dans votre flux de trésorerie. Il fournit également des prévisions qui vous aideront à prendre les meilleures décisions et donc d’améliorer la santé de votre flux de trésorerie. Vous pouvez analyser les disponibilités par entité juridique, la devise, et le compte bancaire pour obtenir une meilleure compréhension des excédents et des déficits.

## <a name="setup-needed-to-view-power-bi-content"></a>Paramétrage requis pour afficher le contenu de Power BI

Le paramétrage suivant doit être réalisé pour que les données s’affichent dans les visuels **Vue d’ensemble des disponibilités** et **Gestion des banques** Power BI.

1. Accédez à **Administration système > Paramétrage > Paramètres système** pour définir la **Devise système** et le **Taux de change système**.
2. Accédez à **Comptabilité > Calendriers > Calendriers fiscaux** pour valider les dates du calendrier fiscal affecté à la période active.
3. Accédez à **Comptabilité > Configuration > Comptabilité** pour définir la **Devise comptable** et le **Type de taux de change**.
4. Définissez les taux de change entre les devises de transaction et la devise comptable, la devise comptable et la devise système, et entre la devise comptable et les devises bancaires. Pour ce faire, accédez à **Comptabilité > Devises > Taux de change des devises**.
5. Configurez et exécutez les prévisions de flux de trésorerie. Pour plus d’informations sur le paramétrage des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](./cash-flow-forecasting.md). 
6. Accédez à **Administration système > Paramétrage > Magasin des entités** pour actualiser la mesure de regroupement **LedgerCovLiquidityMeasurement**.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Les états du contenu Power BI **Vue d’ensemble des disponibilités** s’affichent dans les espaces de travail **Vue d’ensemble des disponibilités** et **Gestion des banques**.

Pour afficher les états de prévisions de flux de trésorerie avec des données, vous devez exécuter le processus de calcul de prévision à l’aide de la fonction **Calculer les prévisions de flux de trésorerie** de la zone de gestion bancaire et de liquidités. Il doit être terminé pour chaque société incluse dans la prévision.  Vous devez actualiser la mesure de regroupement LedgerCovLiquidityMeasurement sur la page **Magasin des entités**.  

À des fins de démonstration, vous pouvez ajouter des données de démonstration de prévisions de flux de trésorerie à l’aide de la page **Générer des données** du module de données de démonstration.  Ce script insèrera des données dans des tables de prévisions de flux de trésorerie pour renseigner rapidement les informations nécessaires pour les rapports.  Ce module est uniquement disponible si vous avez le modèle de suite de données de démonstration déployé dans l’environnement. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI

Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d’état du contenu Power BI **Vue d’ensemble des disponibilités**.

| Etat                                | Sommaire |
|---------------------------------------|----------|
| Vue d’ensemble des disponibilités – toutes les sociétés         | <ul><li>Encaissements et décaissements dans la devise système</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Vue d’ensemble des disponibilités – société actuelle       | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise comptable</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Prévisions du flux de trésorerie – Toutes les sociétés    | <ul><li>Encaissements et décaissements dans la devise système</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions de flux de trésorerie – devise de la société | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions des devises                     | <ul><li>Soldes de devise prévus</li><li>Synthèse quotidienne des devises</li><li>Détails des prévisions</li></ul> |
| Soldes bancaires                         | <ul><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li><li>Solde par compte bancaire</li><li>Solde par devise</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Le tableau suivant indique les entités sur lesquelles le contenu Power BI **Vue d’ensemble des disponibilités** est basé.

| Entité                                                                          | Sommaire |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Sociétés selon lesquelles filtrer les états |
| LedgerCovLiquidityMeasurement\_Date                                             | Dates selon lesquelles filtrer les états |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Solde bancaire réel et dernier solde bancaire prévu |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Détails de transaction prévus |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Synthèse des encaissements, décaissements et soldes en utilisant la devise comptable de chaque société |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Synthèse des encaissements, décaissements et soldes en utilisant la devise système de toutes les sociétés |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Synthèse des montants de transactions nets et solde des devises en utilisant la devise de transaction |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]