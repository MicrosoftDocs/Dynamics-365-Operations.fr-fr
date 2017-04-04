---
title: Contenu financier BI de courant de performances
description: "Cette rubrique décrit Microsoft Dynamics 365 du pack financier de contenu de performances des opérations pour le projet BI de courant de Microsoft. Elle décrit le tableau de bord et les états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Contenu financier BI de courant de performances

Cette rubrique décrit Microsoft Dynamics 365 du pack financier de contenu de performances des opérations pour le projet BI de courant de Microsoft. Elle décrit le tableau de bord et les états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu.

<a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
--------------------------

Deux versions du pack financier de contenu de performances sont disponibles. Une version est disponible à partir de Microsoft Dynamics Lifecycle Services (LCS), et d'autres est disponible dans PowerBI.com.

-   ** Version qui est disponible dans des lettres de crédit : ** Le pack financier de contenu de performances qui est disponible à des lettres de crédit prend en charge Microsoft Dynamics 365 pour la version 1611 d'opérations. Recevez un pack de contenu de la bibliothèque partagé d'immobilisation dans des lettres de crédit. Pour plus d'informations sur le chargement le contenu comprimez- et connectez- le à votre Microsoft Dynamics 365 pour les données d'opérations, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).
-   ** Version qui est disponible dans PowerBI.com : ** Le pack financier de contenu de performances disponible dans PowerBI.com prend en charge les versions 7,0 et 7.0.1 de Microsoft Dynamics AX. Pour plus d'informations sur la procédure de connexion et charger votre Dynamics 365 pour les données d'opérations, voir [contenu BI de courant d'accès de PowerBI.com] (power-bi-home-page.md).

## <a name="main-account-setup"></a>Paramétrage de compte principal
Comme les organisations souhaitent passifs et les montants de produit à afficher sous forme de montants positifs dans les états, le paramétrage des comptes principaux dans Dynamics 365 pour les opérations est important. Pour que ces comptes principaux sont affichées comme montants positifs, le type de compte principal doit être défini ** passif ** ou ** produit **. Lorsque ces types de comptes sont utilisés, d'organigramme d'entreprise via le projet BI de courant de Microsoft renversera les signes et d'afficher les montants en tant que positif.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Aperçu interactif et états inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données Dynamics 365 for Operations, vos données financières s'affichent dans le tableau de bord et les états. Si ce n'est jamais utilisé le projet BI de courant de péremption, vous souhaitez plus {{à:about}} {{son:about}} sujet sous l'onglet [page guidée d'enseignement pour BI de courant] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Le tableau de bord contient les vignettes résumées des données basées sur les états sous-jacents. Chaque vignette contient des informations résumées pour l'année en cours dans toutes les sociétés d'une organisation. Voici certaines des vignettes :

-   Espèces
-   Produit total de cette année
-   Dépenses totales de cette année
-   Revenu net de cette année
-   Taux rapide
-   Dépenses totales de cette année par catégorie de compte
-   Taux actuel
-   Dette sur le total des immobilisations
-   Produit réel par rapport à celui prévu
-   Produit facturé cette année
-   Taux de frais d'exploitation cette année
-   Marge bénéficiaire de cette année
-   Dépenses réelles par rapport à celles budgétées – Toutes les sociétés

Chaque vignette est subis suite à un état de prise en charge. Ces états contiennent des graphiques et des tables qui fournissent plus d'informations. Le tableau suivant décrit ces états.

| Etat                      | Les informations que l'état doit contenir                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Analyse des disponibilités               | Disponibilités par entité juridique, disponibilités par trimestre, liquide de total, et disponibilités par compte ** note : ** ** Les disponibilités par le siège ** l'état n'inclut pas de solde d'ouverture dans le total du premier trimestre. Elle présente le total des transactions validées dans chaque trimestre.                                                                                |
| Analyse du taux actuel      | Taux actuel par entité juridique, taux actuel par trimestre et soldes pour les immobilisations actuelles et le passif actuel.                                                                                                                                                                                                                              |
| Analyse du taux rapide        | Ratio de trésorerie par entité juridique, ratio de trésorerie par trimestre, et soldes pour les disponibilités, Ventes, et les dettes d'exploitation                                                                                                                                                                                                                      |
| Analyse du coût des marchandises vendues | Coût des marchandises vendues (COGS) par entité juridique, coût des marchandises vendues cette année et l'année dernière par trimestre, coût des marchandises vendues par entité juridique, coût des marchandises vendues totales et coût des marchandises vendues en pourcentage des ventes                                                                                                                                                                                   |
| Analyse du fonds de roulement    | Fonds de roulement par entité juridique, fonds de roulement par trimestre, actifs actuels, passif en cours et fonds de roulement total                                                                                                                                                                                                                   |
| Analyse des immobilisations et des créances     | Rendement du total des actifs et endettement sur total des actifs par entité juridique, ratio d'endettement sur total des actifs et rendement du total des actifs par trimestre jusqu'à présent, immobilisations et passif                                                                                                                                                                                     |
| Analyse de marge bénéficiaire      | Marge bénéficiaire budgétée et réelle par entité juridique, marquage du profit par trimestre, pourcentage de marge bénéficiaire et marge bénéficiaire                                                                                                                                                                                                                       |
| Analyse du revenu net         | Revenu net réel et budgétaire par entité juridique, revenu net de cette année et de l'année dernière et dépenses en pourcentage de revenu net                                                                                                                                                                                                                       |
| Analyse des bénéfices           | Recettes budgétaires et réelles avant intérêts et taxes (EBIT) par entité juridique, EBIT de cette année et de l'année dernière, dépenses en pourcentage de produit, et dépenses budgétaires et réelles du produit                                                                                                                                                          |
| Analyse du produit            | Produit total, recettes budgétaires et réelles par entité juridique, produit total de cette année et de l'année dernière, écart du budget de produit par entité juridique, et produit total de cette période et de la période passée                                                                                                                                                 |
| Analyse des dépenses            | Dépenses totales, dépenses totales budgétaires et réelles par entité juridique, dépenses réelles et budgétaires par trimestre, dépenses totales par catégorie de compte, et taux de frais d'exploitation                                                                                                                                                                 |
| Analyse de produit facturée     | Ventes totales, Ventes total par entité juridique, Ventes total par trimestre, et soldes des comptes de ventes ** note : ** Les états n'incluent pas les soldes d'ouverture des comptes généraux du module Ventes. Elles indiquent le total des transactions validées dans le module Ventes. |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données qui remplissent tableau de bord et états dans le contenu financier de performances se compriment sont Dynamics 365 pour les données d'opérations. Les entités suivantes ont été utilisée comme base du pack de contenu : ** Entités de données générales **

-   ** GeneralLedgerActivities ** – cette entité regroupe les soldes comptables par catégorie de compte.
-   ** BudgetActivities ** – cette entité regroupe les soldes budgétaires par catégorie de compte.

**Data entities**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Comptabilités
-   ChartofAccounts

Ces entités a été utilisée pour créer des mesures calculées dans le modèle de données. Les mesures calculées sont utilisées pour calculer les indicateurs de performance clé (KPIs) et les états utilisés dans l'établissement du pack de contenu. Par défaut, le pack de contenu fournit des données pour les trois dernières années et une année dans le futur. Pour inclure des calculs supplémentaires dans vos rapports et dans le tableau de bord, vous pouvez modifier le [classeur Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Ce classeur est le modèle de données par défaut utilisé pour créer le pack de contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](..\data-entities\data-entities.md)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](configure-power-bi-integration.md)



