---
title: "Contenu Power BI Vue d'ensemble des disponibilités"
description: "Cette rubrique décrit le contenu Power BI Vue d'ensemble des disponibilités. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: saraschi2
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e969c2033463d565ce782c7dc8cfc4b458349289
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="cash-overview-power-bi-content"></a>Contenu Power BI Vue d'ensemble des disponibilités

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Vue d'ensemble des disponibilités**. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Vue d'ensemble des disponibilités** a été créé pour les personnes responsables de la trésorerie dans leur organisation. Le contenu Power BI **Vue d'ensemble des disponibilités** fournit une visibilité dans votre flux de trésorerie. Il fournit également des prévisions qui vous aideront à prendre les meilleures décisions et donc d'améliorer la santé de votre flux de trésorerie. Vous pouvez analyser les disponibilités par entité juridique, la devise, et le compte bancaire pour obtenir une meilleure compréhension des excédents et des déficits.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Si vous utilisez la mise à jour de juillet 2017 de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, les états du contenu Power BI **Vue d'ensemble des disponibilités** s'affichent dans les espaces de travail **Vue d'ensemble des disponibilités** et **Gestion des banques**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI
Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Vue d'ensemble des disponibilités**.

| Etat                                | Sommaire |
|---------------------------------------|----------|
| Vue d'ensemble des disponibilités - toutes les sociétés         | <ul><li>Encaissements et décaissements dans la devise système</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Vue d'ensemble des disponibilités - société actuelle       | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Soldes de devise prévus</li><li>Solde bancaire total dans la devise comptable</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li></ul> |
| Prévisions du flux de trésorerie – Toutes les sociétés    | <ul><li>Encaissements et décaissements dans la devise système</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions de flux de trésorerie - devise de la société | <ul><li>Encaissements et décaissements dans la devise comptable</li><li>Synthèse des prévisions quotidiennes</li><li>Détails des prévisions</li></ul> |
| Prévisions des devises                     | <ul><li>Soldes de devise prévus</li><li>Synthèse quotidienne des devises</li><li>Détails des prévisions</li></ul> |
| Soldes bancaires                         | <ul><li>Solde bancaire total dans la devise du système</li><li>Solde par entité juridique</li><li>Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</li><li>Solde par compte bancaire</li><li>Solde par devise</li></ul> |

## <a name="extending-the-power-bi-content"></a>Extension du contenu Power BI
Vous pouvez fournir une analyse approfondie aux utilisateurs qui ne s'enregistrent pas dans Dynamics 365 à l'aide des packs de contenu disponibles dans Lifecycle Services (LCS). Ces packs de contenu peuvent être modifiés pour inclure d'autres rapports ou visuels, puis être publiés via votre locataire Power BI.com pour analyse. 

Le contenu Power BI **Vue d'ensemble des disponibilités** se trouve dans la bibliothèque de ressources partagées dans LCS. Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

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

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les graphiques et les états utilisés dans le contenu Power BI **Vue d'ensemble des disponibilités**. Pour inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier Power BI à partir de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un contenu et des tableaux de bord de l'organisation contenant les informations que vous avez ajoutées.

