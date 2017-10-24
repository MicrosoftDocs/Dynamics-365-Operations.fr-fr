---
title: "Contenu Power BI des performances financières"
description: "Cette rubrique décrit le contenu Power BI Performances financières. Elle décrit le tableau de bord et les états inclus, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: kweekley
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a501fcb851f1c201e03b59bb3ea951684c6e552
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="financial-performance-power-bi-content"></a>Contenu Power BI des performances financières

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Performances financières**. Elle décrit le tableau de bord et les états inclus, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Vous pouvez accéder au contenu Power BI **Performances financières** à partir de Microsoft Dynamics Lifecycle Services (LCS) et de PowerBI.com.

### <a name="available-from-lcs"></a>Disponible à partir de LCS
Le contenu Power BI **Performances financières** qui est disponible à partir de LCS prend en charge les versions suivantes :

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Juillet 2017)
- Microsoft Dynamics 365 for Operations version 1611 

Vous pouvez trouver le contenu Power BI dans la bibliothèque Actif partagé dans LCS. Pour savoir comment télécharger le pack de contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

### <a name="available-from-powerbicom"></a>Disponible dans PowerBI.com
Le contenu Power BI **Performances financières** disponible dans PowerBI.com prend en charge les versions 7.0 et 7.0.1 de Microsoft Dynamics AX. Pour plus d'informations sur la procédure de connexion et de chargement de vos données Dynamics AX, voir [Accéder au contenu Power BI depuis PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Paramétrage des comptes principaux
Comme les organisations souhaitent que les passifs et les montants du produit apparaissent comme des montants positifs dans les états, le paramétrage des comptes principaux est important. Pour faire apparaître ces comptes principaux comme montants positifs, le type de compte principal doit être défini sur **Passif** ou **Produit**. Lorsque ces types de comptes sont utilisés, la génération d'états via Power BI contrepasse les signes et affiche les montants comme positifs.

## <a name="dashboard-and-reports-that-are-included-in-the-power-bi-content"></a>Tableau de bord et états inclus dans le contenu Power BI
Le tableau de bord contient les vignettes résumées des données basées sur les états sous-jacents. Chaque vignette contient des informations résumées pour l'année en cours dans toutes les sociétés d'une organisation. Voici quelques-unes des vignettes :

- Espèces
- Produit total de cette année
- Dépenses totales de cette année
- Revenu net de cette année
- Taux rapide
- Dépenses totales de cette année par catégorie de compte
- Taux actuel
- Dette sur le total des immobilisations
- Produit réel par rapport à celui prévu
- Produit facturé cette année
- Taux de frais d'exploitation cette année
- Marge bénéficiaire de cette année
- Dépenses réelles par rapport à celles budgétées – Toutes les sociétés

Chaque vignette est soutenue par un état de prise en charge. Ces états contiennent des graphiques et des tables qui fournissent plus d'informations. Le tableau suivant décrit ces états.

| Etat                      | Les informations que l'état doit contenir |
|-----------------------------|--------------------------------------|
| Analyse des disponibilités               | Disponibilités par entité juridique, disponibilités par trimestre, disponibilités totales et disponibilités par compte<blockquote>[!NOTE]<br>Les informations relatives aux disponibilités par trimestre n'incluent pas les soldes d'ouverture dans le total du premier trimestre. Il présente le total des nouvelles transactions validées dans chaque trimestre.</blockquote> |
| Analyse du taux actuel      | Taux actuel par entité juridique, taux actuel par trimestre et soldes pour les immobilisations actuelles et le passif actuel. |
| Analyse du taux rapide        | Taux rapide par entité juridique, taux rapide par trimestre et soldes pour les disponibilités, comptabilité client et passif actuel |
| Analyse du coût des marchandises vendues | Coût des marchandises vendues (COGS) par entité juridique, coût des marchandises vendues cette année et l'année dernière par trimestre, coût des marchandises vendues par entité juridique, coût des marchandises vendues totales et coût des marchandises vendues en pourcentage des ventes |
| Analyse du fonds de roulement    | Fonds de roulement par entité juridique, fonds de roulement par trimestre, actifs actuels, passif en cours et fonds de roulement total |
| Analyse des immobilisations et des créances     | Rendement du total des actifs et endettement sur total des actifs par entité juridique, ratio d'endettement sur total des actifs et rendement du total des actifs par trimestre jusqu'à présent, immobilisations et passif |
| Analyse de marge bénéficiaire      | Marge bénéficiaire budgétée et réelle par entité juridique, marquage du profit par trimestre, pourcentage de marge bénéficiaire et marge bénéficiaire |
| Analyse du revenu net         | Revenu net réel et budgétaire par entité juridique, revenu net de cette année et de l'année dernière et dépenses en pourcentage de revenu net |
| Analyse des bénéfices           | Recettes budgétaires et réelles avant intérêts et taxes (EBIT) par entité juridique, EBIT de cette année et de l'année dernière, dépenses en pourcentage de produit, et dépenses budgétaires et réelles du produit |
| Analyse du produit            | Produit total, recettes budgétaires et réelles par entité juridique, produit total de cette année et de l'année dernière, écart du budget de produit par entité juridique, et produit total de cette période et de la période passée |
| Analyse des dépenses            | Dépenses totales, dépenses totales budgétaires et réelles par entité juridique, dépenses réelles et budgétaires par trimestre, dépenses totales par catégorie de compte, et taux de frais d'exploitation |
| Analyse de produit facturée     | Total de la comptabilité client, total de la comptabilité client par entité juridique, total de la comptabilité client par trimestre et soldes des comptes de ventes<blockquote>[!NOTE]<br>Les informations n'incluent pas les soldes d'ouverture des comptes généraux du module Comptabilité client. Elles indiquent le total des nouvelles transactions validées dans la comptabilité client.</blockquote> |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les entités suivantes ont été utilisées comme base du contenu Power BI **Performances financières** :

**Entités de données agrégées**

- **GeneralLedgerActivities** – Cette entité regroupe les soldes comptables par catégorie de compte.
- **BudgetActivities** – Cette entité regroupe les soldes budgétaires par catégorie de compte.

**Entités de données**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Comptabilités
- ChartofAccounts

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Les entités calculées sont utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le contenu. Par défaut, le contenu fournit des données pour les trois dernières années et une année dans le futur. Pour inclure des calculs supplémentaires dans vos rapports et dans le tableau de bord, vous pouvez modifier le [classeur Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ce classeur est le modèle de données par défaut utilisé pour créer le contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

