---
title: Synchroniser les tâches de projet directement de Project Service Automation vers Finance and Operations
description: Cette rubrique décrit le modèle et la tâche sous-jacente utilisés pour synchroniser les tâches de projet directement depuis Microsoft Dynamics 365 Project Service Automation vers Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250390"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Synchroniser les tâches de projet directement de Project Service Automation vers Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le modèle et la tâche sous-jacente utilisés pour synchroniser les tâches de projet directement depuis Dynamics 365 Project Service Automation vers Dynamics 365 Finance.

> [!NOTE]
> - L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0.
> - Si vous utilisez Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités. Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.
> - L'intégration des chiffres réels est disponible dans version 8.0.1 ou version ultérieure.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flux de données pour Project Service Automation et Finance

La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance. Le modèle d'intégration disponible avec la fonction Intégration des données active le flux de données sur les tâches du projet entre Project Service Automation et Finance.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance.

[![Flux de données pour l'intégration de Project Service Automation avec Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Modèle et tâche

Pour accéder au modèle, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle suivant et la tâche sous-jacente sont utilisés pour synchroniser les tâches du projet entre Project Service Automation et Finance :

- **Nom du modèle dans le module Intégration des données :** Tâches du projet (PSA vers Fin and Ops)
- **Nom de la tâche dans le projet :** Tâches du projet

Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.

## <a name="entity-set"></a>Ensemble d'entités

| Project Service Automation | Finances                             |
|----------------------------|-------------------------------------|
| Tâches de projet              | Entité d'intégration de la tâche de projet |

## <a name="entity-flow"></a>Flux d'entité

Les tâches de projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance en tant qu'activités de projet.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query pour Excel pour filtrer les données si la condition suivante est satisfaite :

- Des enregistrements spécifiques aux ressources sont disponibles dans une tâche de projet.

Si vous devez utiliser Power Query, suivez l'instruction ci-après :

- Le modèle Tâches de projet (PSA vers Fin and Ops) a un filtre par défaut qui exclut les enregistrements spécifiques aux ressources d'une tâche de projet en définissant le filtre de **IsLineTask** sur **False**. Si vous créez votre propre modèle, vous devez ajouter ce filtre.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.

[![Mise en correspondance des modèles](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
