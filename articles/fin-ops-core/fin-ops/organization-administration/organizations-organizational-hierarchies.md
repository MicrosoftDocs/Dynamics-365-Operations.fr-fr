---
title: Vue d’ensemble des organisations et des hiérarchies d’organisation
description: Les hiérarchies organisationnelles représentent les relations entre les organisations qui composent votre entreprise.
author: sericks007
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom:
- "17291"
- intro-internal
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74aa2736b4cfb11039ea1cee3f62e74cf4928a1b27cea16e7e0e86f66bdddd59
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715987"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>Vue d’ensemble des organisations et des hiérarchies d’organisation

[!include [banner](../includes/banner.md)]

Une organisation est un groupe de personnes qui travaillent ensemble pour réaliser un processus entreprise ou atteindre un objectif. Les hiérarchies organisationnelles représentent les relations entre les organisations qui composent votre entreprise.

## <a name="organizations"></a>Organisations

Vous pouvez définir les types suivants d’organisations internes : entités juridiques, sections et équipes.

Toutes les organisations internes sont des types de l’entité **Partie**. C’est pourquoi, ces organisations utilisent le carnet d’adresses pour stocker les informations d’adresse et de contact. Une partie (personne ou organisation) peut appartenir à un ou plusieurs carnets d’adresses.

### <a name="legal-entities"></a>Entités juridiques

Une entité juridique est une organisation qui dispose d’une structure juridique enregistrée ou légalement déclarée. Les entités juridiques peuvent passer des contrats juridiques et sont tenues de préparer des relevés faisant état de leurs performances.

Une société est un type d’entité juridique. Actuellement, les entreprises sont les seuls types d’entité juridique que vous pouvez créer et chaque entité juridique est associée à un ID société. Cette association existe car certaines zones fonctionnelles du programme utilisent un ID société, ou DataAreaId, dans leurs modèles de données. Dans ces zones fonctionnelles, les sociétés sont utilisées en tant que limite pour la sécurité des données. Les utilisateurs peuvent accéder aux données uniquement pour la société à laquelle ils sont actuellement connectés.

### <a name="operating-units"></a>Sections

Une section est une organisation utilisée pour partager le contrôle des ressources économiques et des processus opérationnels dans une société. Dans une section, les personnes ont la responsabilité d’optimiser l’utilisation des ressources rares, d’améliorer les processus et de justifier leurs performances.

Les types d’unités opérationnelles incluent les centres de coût, les unités commerciales, les chaînes de valeur, les services et les chaînes de commerce. Le tableau suivant fournit d’autres informations sur chaque type de section.

| Type de section | description ; | Objectif |
|---------------------|-------------|---------|
| Centre de coût         | Section dans laquelle les gestionnaires sont responsables des dépenses budgétées et réelles. | Utilisé pour la gestion et le contrôle opérationnel des processus entreprise qui englobent les entités juridiques. |
| Unité commerciale       | Section semi-autonome créée pour répondre aux objectifs commerciaux stratégiques. | Utilisé pour les états financiers basés sur les secteurs ou les lignes de produits que l’organisation gère indépendamment des entités juridiques. |
| Chaîne de valeur        | Section qui contrôle un ou plusieurs flux de production. | Utilisée couramment dans la production au plus juste pour contrôler les activités et les flux requis pour offrir un produit ou un service aux consommateurs. |
| Département          | Section représentant une catégorie ou une portion fonctionnelle d’une organisation qui exécute une tâche spécifique, par exemple les ventes ou la comptabilité. | Utilisé pour créer des états sur les zones fonctionnelles. Un département peut être responsable des résultats et peut être composé d’un groupe de centres de coût. |
| Canal de commerce      | Unité opérationnelle représentent un magasin physique, un magasin en ligne ou une place de marché en ligne. | Utilisé pour la gestion et le contrôle opérationnel d’un ou plusieurs magasins au sein d’une entité juridique ou entre plusieurs entités juridiques. |

### <a name="teams"></a>Équipes

Une équipe est une organisation dont les membres partagent des responsabilités, des intérêts et des objectifs communs. Les équipes ne peuvent pas être utilisées dans les hiérarchies organisationnelles.

## <a name="organizational-hierarchies"></a>Hiérarchies organisationnelles

Paramétrez des hiérarchies organisationnelles pour afficher et créer des états relatifs à votre entreprise à partir de perspectives différentes. Par exemple, vous pouvez paramétrer une hiérarchie d’entités juridiques pour les déclarations légales ou fiscales. Paramétrez une hiérarchie basée sur des sections pour déclarer des informations financières qui ne sont pas requises par la loi, mais qui sont utilisées à des fins de contrôle interne. Par exemple, vous pouvez créer une stratégie d’achat pour contrôler les politiques d’achat, les règles et les processus entreprise.

Un objet est affecté à chaque hiérarchie. L’objet d’une hiérarchie détermine les types d’organisations pouvant être inclus dans la hiérarchie. L’objet définit également dans quels scénarios d’application la hiérarchie peut être utilisée.

Les organisations d’une hiérarchie peuvent partager des paramètres, des stratégies et des transactions. Une organisation peut hériter des paramètres de son organisation parent ou les remplacer. Cependant, les données principales partagées, telle que les produits et les carnets d’adresses, s’appliquent à l’ensemble de l’organisation et ne peuvent pas être remplacées pour les organisations individuelles. La création d’organisations et de hiérarchies nécessite une planification soignée. Pour plus d’informations voir [Planifier votre hiérarchie d’organisation](plan-organizational-hierarchy.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]