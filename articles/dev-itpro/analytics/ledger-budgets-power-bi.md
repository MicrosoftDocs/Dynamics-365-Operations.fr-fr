---
title: Contenu Power BI Comparatif Réel/Budget
description: Cette rubrique décrit le contenu Power BI Comparatif Réel/Budget. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553736"
---
# <a name="actual-vs-budget-power-bi-content"></a>Contenu Power BI Comparatif Réel/Budget

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le contenu Power BI **Comparatif Réel/Budget**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Comparatif Réel/Budget** a été créé pour les personnes chargées de surveiller le comparatif des performances de budget dans leur organisation. Le contenu Power BI **Comparatif Réel/Budget** fournit une visibilité dans les écarts de budget. Vous pouvez analyser le budget de l'année en cours par catégorie de compte, code budgétaire, compte principal, description de compte principal ou période fiscale pour obtenir une meilleure compréhension de la cause de tous les écarts.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Les états du contenu Power BI **Comparatif Réel/Budget** s'affichent dans les espaces de travail **Budget comptable et prévisions** et **CFO**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI
Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Comparatif Réel/Budget**.

| Etat                      | Métriques                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Dépenses - comparatif Réel/Budget | <ul><li>Dépenses totales de cette année</li><li>Dépenses totales de cette année</li></ul>  |
| Produit - Comparatif Réel/Budget  | <ul><li>Produit total de cette année</li><li>Produit total basé sur le budget de cette année</li><ul>     |
| Dépense                     | <ul><li>Dépenses totales de cette année</li><li>Objectif des dépenses basées sur le budget</li><ul> |
| Produit                     | <ul><li>Produit total de cette année</li><li>Objectif des produits basés sur le budget</li><ul>   |
| Revenu net                  | <ul><li>Revenu net de cette année</li><li>Objectif du revenu net basé sur le budget</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

| Entité                    | Sommaire                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Activités liées à la comptabilité | Montants des transactions pour la comptabilité                                       |
| Activités liées au budget         | Montants des transactions pour le registre budgétaire                                      |
| Comptes principaux             | Comptes principaux en fonction desquels filtrer les états                                               |
| Calendriers fiscaux          | Calendriers fiscaux en fonction desquels filtrer les états                                            |
| Comptabilités                   | Comptabilité permettant de filtrer l'état dans la comptabilité actuelle              |
| Codes budgétaires              | Codes budgétaires selon lesquels filtrer les états                                                |
| Entités juridiques            | Les entités juridiques permettant de filtrer l'état dans l'entité juridique actuelle |
