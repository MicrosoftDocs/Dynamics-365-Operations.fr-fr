---
title: "Synchroniser les tâches de projet à partir de Project Service Automation"
description: "Cette rubrique décrit le modèle et la tâche sous-jacente qui sont utilisés pour synchroniser les tâches de projet directement entre Microsoft Dynamics 365 for Project Service Automation et Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Synchroniser les tâches de projet dans Project Service Automation directement avec les activités de projet dans Finance and Operations

Cette rubrique décrit le modèle et la tâche sous-jacente qui sont utilisés pour synchroniser les tâches de projet directement entre Microsoft Dynamics 365 for Project Service Automation et Dynamics 365 for Finance and Operations.

> [!NOTE]
> L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flux de données pour Project Service Automation et Finance and Operations

La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations. Le modèle d'intégration disponible avec la fonction Intégration des données active le flux de données sur les tâches de projet entre Project Service Automation et Finance and Operations.

L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.

[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Modèle et tâche

Pour accéder au modèle, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.

Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les tâches de projet entre Project Service Automation et Finance and Operations :

-**Nom du modèle dans le module Intégration des données :** Tâches de projet (PSA vers Fin and Ops) -**Nom de la tâche dans le projet :** Tâches de projet

Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.

## <a name="entity-set"></a>Ensemble d'entités

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Tâches de projet                           | Entité d'intégration de la tâche de projet.   |

## <a name="entity-flow"></a>Flux d'entité

Les tâches de projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations en tant qu'activités de projet.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.

## <a name="power-query"></a>Power Query

Vous devez utiliser Microsoft Power Query pour filtrer les données si les conditions suivantes sont réunies :

- Des enregistrements spécifiques aux ressources sont disponibles dans une tâche de projet.

Si vous devez utiliser Power Query, suivez les instructions ci-après :

- Le modèle Tâches de projet (PSA vers Fin and Ops) a un filtre par défaut pour exclure les enregistrements spécifiques aux ressources d'une tâche de projet en définissant le filtre de **IsLineTask** sur **False**. Si vous créez votre propre modèle, vous devez ajouter ce filtre.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données. La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.

[![Mise en correspondance des modèles](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


