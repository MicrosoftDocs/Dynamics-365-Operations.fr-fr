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

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="bdb21-103">Synchroniser les tâches de projet dans Project Service Automation directement avec les activités de projet dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bdb21-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="bdb21-104">Cette rubrique décrit le modèle et la tâche sous-jacente qui sont utilisés pour synchroniser les tâches de projet directement entre Microsoft Dynamics 365 for Project Service Automation et Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="bdb21-105">L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0 de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="bdb21-106">Flux de données pour Project Service Automation et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bdb21-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="bdb21-107">La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="bdb21-108">Le modèle d'intégration disponible avec la fonction Intégration des données active le flux de données sur les tâches de projet entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="bdb21-109">L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="bdb21-110">[![Flux de données pour l'intégration de Project Service Automation avec Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="bdb21-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="bdb21-111">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="bdb21-111">Template and task</span></span>

<span data-ttu-id="bdb21-112">Pour accéder au modèle, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.</span><span class="sxs-lookup"><span data-stu-id="bdb21-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="bdb21-113">Le modèle et la tâche sous-jacente ci-après sont utilisés pour synchroniser les tâches de projet entre Project Service Automation et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="bdb21-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="bdb21-114">-**Nom du modèle dans le module Intégration des données :** Tâches de projet (PSA vers Fin and Ops) -**Nom de la tâche dans le projet :** Tâches de projet</span><span class="sxs-lookup"><span data-stu-id="bdb21-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="bdb21-115">Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.</span><span class="sxs-lookup"><span data-stu-id="bdb21-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="bdb21-116">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="bdb21-116">Entity set</span></span>

|<span data-ttu-id="bdb21-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="bdb21-117">Project Service Automation</span></span>               | <span data-ttu-id="bdb21-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bdb21-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="bdb21-119">Tâches de projet</span><span class="sxs-lookup"><span data-stu-id="bdb21-119">Project Tasks</span></span>                           | <span data-ttu-id="bdb21-120">Entité d'intégration de la tâche de projet.</span><span class="sxs-lookup"><span data-stu-id="bdb21-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="bdb21-121">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="bdb21-121">Entity flow</span></span>

<span data-ttu-id="bdb21-122">Les tâches de projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance and Operations en tant qu'activités de projet.</span><span class="sxs-lookup"><span data-stu-id="bdb21-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="bdb21-123">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="bdb21-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="bdb21-124">Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.</span><span class="sxs-lookup"><span data-stu-id="bdb21-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="bdb21-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="bdb21-125">Power Query</span></span>

<span data-ttu-id="bdb21-126">Vous devez utiliser Microsoft Power Query pour filtrer les données si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="bdb21-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="bdb21-127">Des enregistrements spécifiques aux ressources sont disponibles dans une tâche de projet.</span><span class="sxs-lookup"><span data-stu-id="bdb21-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="bdb21-128">Si vous devez utiliser Power Query, suivez les instructions ci-après :</span><span class="sxs-lookup"><span data-stu-id="bdb21-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="bdb21-129">Le modèle Tâches de projet (PSA vers Fin and Ops) a un filtre par défaut pour exclure les enregistrements spécifiques aux ressources d'une tâche de projet en définissant le filtre de **IsLineTask** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="bdb21-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="bdb21-130">Si vous créez votre propre modèle, vous devez ajouter ce filtre.</span><span class="sxs-lookup"><span data-stu-id="bdb21-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bdb21-131">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="bdb21-131">Template mapping in Data integration</span></span>

<span data-ttu-id="bdb21-132">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="bdb21-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="bdb21-133">La mise en correspondance indique les informations de champ qui sont synchronisées entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bdb21-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="bdb21-134">[![Mise en correspondance des modèles](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="bdb21-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


