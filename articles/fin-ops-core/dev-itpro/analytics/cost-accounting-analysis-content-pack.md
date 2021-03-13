---
title: Contenu Power BI Analyse de contrôle de gestion
description: Cette rubrique décrit les données incluses dans le contenu Power BI d’analyse du contrôle de gestion.
author: AndersGirke
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c9a4741c1b09b8e68a9fe95d6f4effa328615d5
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093384"
---
# <a name="cost-accounting-analysis-power-bi-content"></a>Contenu Power BI Analyse de contrôle de gestion

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les données incluses dans le contenu Power BI **Analyse du contrôle de gestion**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Analyse du contrôle de gestion** est destiné aux contrôleurs de coûts ou à toute personne chargée de contrôler les coûts d’une organisation. Il inclut les mesures clés, telles que le coût, la magnitude et le taux de coût par coût réel, coût budgétaire et coût budgétaire flexible. Il utilise les données de transaction du module **Contrôle de gestion** et fournit une vue globale des coûts pour l’ensemble de l’organisation dans une devise de déclaration. Les responsables peuvent filtrer les données par objet de coût pour contrôler les coûts de leurs unités d’organisation, même si l’organisation peut avoir plusieurs entités juridiques.

Comme le contenu **Analyse du contrôle de gestion** présente les écarts entre les coûts réels et les coûts budgétés, les responsables peuvent être informés des tendances positives et négatives pour leurs unités opérationnelles. Les responsables peuvent détailler les hiérarchies de l’élément de coût ou chaque élément de coût. Ainsi, les responsables peuvent obtenir une analyse détaillée de la manière dont les écarts de coûts sont survenus, puis agir en conséquence.

Le contenu **Analyse du contrôle de gestion** permet aux contrôleurs de gestion d’analyser la manière dont le coût se répercute sur les objets de coût de l’ensemble de l’organisation.

Pour en savoir plus sur le contrôle de gestion, voir [Page d’accueil du contrôle de gestion](../../../finance/cost-accounting/cost-accounting-home-page.md).

En définissant la sécurité au niveau de l’accès dans le module Contrôle de gestion et en la combinant à la sécurité au niveau de la ligne dans Power BI, vous pouvez autoriser l’accès au contenu Power BI **Analyse du contrôle de gestion** à tous les propriétaires d’objet de coût. Toutes les données des visualisations seront ensuite filtrées selon le niveau d’accès contrôlé dans le contrôle de gestion. Pour en savoir plus sur la sécurité au niveau de l’accès et la sécurité au niveau de la ligne, voir [Paramétrer la sécurité du contenu Power BI d’analyse du contrôle de gestion](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Vous trouverez le contenu Power BI **Analyse du contrôle de gestion** dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le contenu et l’implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).

Veillez à télécharger le contenu **Analyse du contrôle de gestion** qui s’applique à la version de Microsoft Dynamics 365 que vous utilisez.

> [!NOTE]
> Le KB 4011327 doit être consulté pour ce contenu Power BI. Une fois que vous êtes connecté à LCS, vous pouvez accéder à la Base de connaissances à l’adresse <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le contenu comprend un ensemble de pages d’état. Chaque page contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables. Le tableau suivant donne une vue d’ensemble des visualisations dans le contenu Power BI **Analyse du contrôle de gestion**.

| Page d’état                      | Graphique                                                                                                                         | Vignette                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Contrôle des coûts par période fiscale    | Coût réel et coût budgétaire par niveau de hiérarchie d’éléments de coût                                                                   | Coût réel et coût budgétaire                    |
|                                  | Écart budgétaire par niveau de hiérarchie d’éléments de coût                                                                               | Taux de coût réel et taux de coût budgétaire          |
|                                  | 10 premiers écarts budgétaires en pourcentage par élément de coût                                                                          | Magnitude réelle et magnitude budgétaire          |
| Contrôle des coûts par année en cours     | Coût réel et coût budgétaire par période d’année civile                                                                           | Coût réel et coût budgétaire                    |
|                                  | Écart budgétaire par période d’année civile                                                                                       | Taux de coût réel et taux de coût budgétaire          |
|                                  | 10 premiers écarts budgétaires en pourcentage par élément de coût                                                                          | Magnitude réelle et magnitude budgétaire          |
| Taux de coût par exercice         | Taux de coût réel par comportement de coût                                                                                             | Taux de coût réel et taux de coût budgétaire          |
|                                  | Taux de coût réel, écart de taux de coût budgétaire, pourcentage du taux de coût budgétaire et taux de coût budgétaire par niveau de hiérarchie d’éléments de coût | Magnitude réelle et magnitude budgétaire          |
|                                  | Écart budgétaire par niveau de hiérarchie d’éléments de coût                                                                               |                                               |
|                                  | 10 premiers écarts budgétaires en pourcentage par élément de coût                                                                          |                                               |
| Budget flexible par exercice | Coût réel, coût budgétaire et coût budgétaire flexible par niveau de hiérarchie d’éléments de coût                                             | Magnitude réelle et magnitude budgétaire          |
|                                  | Écart budgétaire et écart budgétaire flexible par niveau de hiérarchie d’éléments de coût                                                  | Coût réel et coût budgétaire flexible           |
|                                  | Coût réel, coût budgétaire et coût flexible par comportement de coût et par niveau de hiérarchie d’éléments de coût                                  | Taux de coût réel et taux de coût budgétaire flexible |
| Relevé des coûts par période fiscale  | Coût réel par niveau de hiérarchie d’éléments de coût et nom du membre de la dimension d’objet de coût                                             |                                               |
|                                  | Coût réel par nom du membre de la dimension d’objet de coût et nom du membre de la dimension d’élément de coût                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données suivantes sont utilisées pour remplir les pages d’état dans le contenu Power BI **Analyse du contrôle de gestion**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).

Les mesures globales clés suivantes sont utilisées comme base du contenu.

| Entité                  | Mesure globale clé | Source de données pour Dynamics 365      | Champ     | Description                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| Écritures de contrôle de gestion | SUM(Amount)               | CAMDATAAggregatedCostEntry        | Montant    | Montant dans la devise comptable du contrôle de gestion. |
| Entrées statistiques     | SUM(Magnitude)            | CAMDATAAggregatedStatisctialEntry | Ampleur |                                                    |

Le tableau suivant indique comment les mesures globales clés sont utilisées pour créer plusieurs mesures calculées dans l’ensemble de données du contenu.

| Mesure                                       | Méthode de calcul de la mesure                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Coût réel                                   | CALCULATE(’Écritures de contrôle de gestion’\[Mesure\], ’Versions de transaction’\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)            |
| Coût budgétaire                                   | CALCULATE(’Écritures de contrôle de gestion’\[Mesure\], ’Versions de transaction’\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)            |
| Écart de coût budgétaire                          | \[Coût budgétaire\] - \[Coût réel\]                                                                                      |
| Pourcentage d’écart budgétaire                    | IF(\[Coût budgétaire\] = 0, blank(), \[Écart budgétaire\] / \[Coût budgétaire\])                                                |
| Magnitude réelle                              | CALCULATE(’Écritures statistiques’\[FullMagnitude\], ’Versions de transaction’\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)          |
| Magnitude budgétaire                              | CALCULATE(\[FullMagnitude\], ’Versions de transaction’\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)                               |
| Écart budgétaire statistique                   | \[Magnitude budgétaire\] - \[Magnitude réelle\]                                                                            |
| Pourcentage d’écart budgétaire statistique        | IF(\[Magnitude budgétaire\] = 0, blank(), \[Écart budgétaire statistique\] / \[Écart budgétaire\])                          |
| Taux de coût réel                              | IF(\[Magnitude réelle\] = 0, BLANK(), \[Coût réel\] / \[Magnitude réelle\])                                          |
| Taux de coût du budget                              | IF(\[Magnitude budgétaire\] = 0, BLANK(), \[Coût budgétaire\] / \[Magnitude budgétaire\])                                          |
| Écart de taux de coût budgétaire                     | \[Taux de coût budgétaire\] - \[Taux de coût réel\]                                                                            |
| Pourcentage d’écart de taux de coût budgétaire          | IF(\[Coût budgétaire\] = 0, blank(), \[Écart de taux de coût budgétaire\] / \[Taux de coût budgétaire\])                                 |
| Coût budgétaire fixe                             | CALCULATE(\[Coût budgétaire\], ’Écritures de contrôle de gestion’\[COSTBEHAVIOR\] = 1)                                              |
| Coût budgétaire variable                          | CALCULATE(\[Coût budgétaire\], ’Écritures de contrôle de gestion’\[COSTBEHAVIOR\] = 2)                                              |
| Coût budgétaire flexible fixe                    | \[Coût budgétaire fixe\]                                                                                                  |
| Coût budgétaire flexible variable                 | IF(\[Magnitude budgétaire\] = 0, BLANK(), (\[Coût budgétaire variable\] / \[Magnitude budgétaire\]) \* \[Magnitude réelle\])       |
| Coût budgétaire flexible                          | \[Coût budgétaire flexible fixe\] + \[Coût budgétaire flexible variable\]                                                     |
| Écart budgétaire flexible                      | \[Coût budgétaire flexible\] - \[Coût réel\]                                                                             |
| Pourcentage d’écart budgétaire flexible           | IF(\[Coût budgétaire flexible\] = 0, BLANK(), \[Écart budgétaire flexible\] / \[Coût budgétaire flexible\])                     |
| Taux de coût budgétaire flexible                     | IF(\[Magnitude réelle\] = 0, BLANK(), \[Coût budgétaire flexible\] / \[Magnitude réelle\])                                 |
| Écart de taux de coût budgétaire flexible            | \[Taux de coût budgétaire flexible\] - \[Taux de coût réel\]                                                                   |
| Pourcentage d’écart de taux de coût budgétaire flexible | IF(\[Taux de coût budgétaire flexible\] = 0, BLANK(), \[Écart de taux de coût budgétaire flexible\] / \[Taux de coût budgétaire flexible\]) |

Les dimensions clés suivantes sont utilisées comme filtres pour diviser les mesures globales afin d’obtenir une plus grande granularité et de fournir des données d’analyse plus approfondies.

| Entité                             | Exemples d’attributs                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Comptabilités de contrôle de gestion            | Comptabilité de contrôle de gestion                                                                                               |
| Unités de contrôle des coûts                 | Nom de l’unité de contrôle des coûts                                                                                               |
| Dimensions d’éléments de coût            | Nom de la dimension d’éléments de coût, nom du membre de la dimension d’élément de coût, description du membre de la dimension d’élément de coût          |
| Dimensions d’objets de coût             | Nom de la dimension d’objet de coût, nom du membre de la dimension d’objet de coût, description du membre de la dimension d’objet de coût              |
| Dimensions statistiques             | Nom de la dimension statistique, nom du membre de la dimension statistique, description du membre de la dimension statistique              |
| Hiérarchies de dimensions d’objet de coût  | Nom de la hiérarchie de dimensions d’objet de coût, niveau de la hiérarchie de dimensions d’objet de coût, arborescence de la hiérarchie de dimensions d’objet de coût    |
| Hiérarchies de dimensions d’élément de coût | Nom de la hiérarchie de dimensions d’élément de coût, niveau de la hiérarchie de dimensions d’élément de coût, arborescence de la hiérarchie de dimensions d’élément de coût |
| Hiérarchies de dimensions statistiques  | Nom de la hiérarchie de dimensions statistiques, niveau de la hiérarchie de dimensions statistiques, arborescence de la hiérarchie de dimensions statistiques    |
| Versions de transaction               | Nom de la version                                                                                                         |
| Calendriers fiscaux                   | Calendrier, description du calendrier                                                                                       |
| Exercices                       | Année civile                                                                                                        |
| Périodes fiscales                     | Période de l’année civile                                                                                                 |
