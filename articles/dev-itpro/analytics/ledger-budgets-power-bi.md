---
title: "Contenu Power BI Comparatif Réel/Budget"
description: "Cette rubrique décrit le contenu Power BI Comparatif Réel/Budget. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: afa8e07505283531c97663f35b208d82d69d2b42
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Contenu Power BI Comparatif Réel/Budget

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Power BI **Comparatif Réel/Budget**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu. 

# <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Comparatif Réel/Budget** a été créé pour les personnes chargées de surveiller le comparatif des performances de budget dans leur organisation. Le contenu Power BI **Comparatif Réel/Budget** fournit une visibilité dans les écarts de budget. Vous pouvez analyser le budget de l'année en cours par catégorie de compte, code budgétaire, compte principal, description de compte principal ou période fiscale pour obtenir une meilleure compréhension de la cause de tous les écarts. 

# <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Si vous utilisez les états de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017), le contenu Power BI **Comparatif Réel/Budget** s'affiche dans les espaces de travail **Budget comptable et prévisions** et **CFO**.

# <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI
Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Comparatif Réel/Budget**.

| Etat                      | Métriques |
|-----------------------------|---------|
| Dépenses - comparatif Réel/Budget | <ul><li>Dépenses totales de cette année</li><li>Dépenses totales de cette année</li></ul> |
| Produit - Comparatif Réel/Budget  | <ul><li>Produit total de cette année</li><li>Produit total basé sur le budget de cette année</li><ul> |
| Dépense                     | <ul><li>Dépenses totales de cette année</li><li>Objectif des dépenses basées sur le budget </li><ul> |
| Produit                     | <ul><li>Produit total de cette année</li><li>Objectif des produits basés sur le budget </li><ul> |
| Revenu net                  | <ul><li>Revenu net de cette année</li><li>Objectif du revenu net basé sur le budget </li><ul> |

## <a name="extending-the-power-bi-content"></a>Extension du contenu Power BI
Grâce aux packs de contenu disponibles dans Microsoft Dynamics Lifecycle Services (LCS), vous pouvez fournir une analyse approfondie aux personnes qui ne se connectent pas à Microsoft Dynamics 365. Vous pouvez modifier ces packs de contenu pour qu'ils permettent d'inclure d'autres rapports ou visuels, et de publier les packs de contenu via votre locataire Power BI.com pour analyse. 

Le contenu Power BI **Comparatif Réel/Budget** se trouve dans la bibliothèque de ressources partagées dans LCS. Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

# <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

| Entité                    | Sommaire |
|---------------------------|----------|
| Activités liées à la comptabilité | Montants des transactions pour la comptabilité |
| Activités liées au budget         | Montants des transactions pour le registre budgétaire |
| Comptes principaux             | Comptes principaux en fonction desquels filtrer les états |
| Calendriers fiscaux          | Calendriers fiscaux en fonction desquels filtrer les états |
| Comptabilités                   | Comptabilité permettant de filtrer l'état dans la comptabilité actuelle |
| Codes budgétaires              | Codes budgétaires selon lesquels filtrer les états |
| Entités juridiques            | Les entités juridiques permettant de filtrer l'état dans l'entité juridique actuelle |

