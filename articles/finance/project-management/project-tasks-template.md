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
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="698ea-103">Synchroniser les tâches de projet directement de Project Service Automation vers Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="698ea-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="698ea-104">Cette rubrique décrit le modèle et la tâche sous-jacente utilisés pour synchroniser les tâches de projet directement depuis Dynamics 365 Project Service Automation vers Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="698ea-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="698ea-105">L'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités sont disponibles dans la version 8.0.</span><span class="sxs-lookup"><span data-stu-id="698ea-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="698ea-106">Si vous utilisez Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="698ea-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="698ea-107">Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="698ea-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="698ea-108">L'intégration des chiffres réels est disponible dans version 8.0.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="698ea-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="698ea-109">Flux de données pour Project Service Automation et Finance</span><span class="sxs-lookup"><span data-stu-id="698ea-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="698ea-110">La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Project Service Automation et de Finance.</span><span class="sxs-lookup"><span data-stu-id="698ea-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="698ea-111">Le modèle d'intégration disponible avec la fonction Intégration des données active le flux de données sur les tâches du projet entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="698ea-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="698ea-112">L'illustration suivante indique comment les données sont synchronisées entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="698ea-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="698ea-113">[![Flux de données pour l'intégration de Project Service Automation avec Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="698ea-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="698ea-114">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="698ea-114">Template and task</span></span>

<span data-ttu-id="698ea-115">Pour accéder au modèle, dans le centre d'administrateur de Microsoft PowerApps, sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner des modèles publics.</span><span class="sxs-lookup"><span data-stu-id="698ea-115">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="698ea-116">Le modèle suivant et la tâche sous-jacente sont utilisés pour synchroniser les tâches du projet entre Project Service Automation et Finance :</span><span class="sxs-lookup"><span data-stu-id="698ea-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="698ea-117">**Nom du modèle dans le module Intégration des données :** Tâches du projet (PSA vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="698ea-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="698ea-118">**Nom de la tâche dans le projet :** Tâches du projet</span><span class="sxs-lookup"><span data-stu-id="698ea-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="698ea-119">Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.</span><span class="sxs-lookup"><span data-stu-id="698ea-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="698ea-120">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="698ea-120">Entity set</span></span>

| <span data-ttu-id="698ea-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="698ea-121">Project Service Automation</span></span> | <span data-ttu-id="698ea-122">Finances</span><span class="sxs-lookup"><span data-stu-id="698ea-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="698ea-123">Tâches de projet</span><span class="sxs-lookup"><span data-stu-id="698ea-123">Project Tasks</span></span>              | <span data-ttu-id="698ea-124">Entité d'intégration de la tâche de projet</span><span class="sxs-lookup"><span data-stu-id="698ea-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="698ea-125">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="698ea-125">Entity flow</span></span>

<span data-ttu-id="698ea-126">Les tâches de projet sont gérées dans Project Service Automation, et elles sont synchronisées avec Finance en tant qu'activités de projet.</span><span class="sxs-lookup"><span data-stu-id="698ea-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="698ea-127">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="698ea-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="698ea-128">Avant toute synchronisation des tâches de projet, vous devez synchroniser les contrats de projet et les projets.</span><span class="sxs-lookup"><span data-stu-id="698ea-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="698ea-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="698ea-129">Power Query</span></span>

<span data-ttu-id="698ea-130">Vous devez utiliser Microsoft Power Query pour Excel pour filtrer les données si la condition suivante est satisfaite :</span><span class="sxs-lookup"><span data-stu-id="698ea-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="698ea-131">Des enregistrements spécifiques aux ressources sont disponibles dans une tâche de projet.</span><span class="sxs-lookup"><span data-stu-id="698ea-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="698ea-132">Si vous devez utiliser Power Query, suivez l'instruction ci-après :</span><span class="sxs-lookup"><span data-stu-id="698ea-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="698ea-133">Le modèle Tâches de projet (PSA vers Fin and Ops) a un filtre par défaut qui exclut les enregistrements spécifiques aux ressources d'une tâche de projet en définissant le filtre de **IsLineTask** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="698ea-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="698ea-134">Si vous créez votre propre modèle, vous devez ajouter ce filtre.</span><span class="sxs-lookup"><span data-stu-id="698ea-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="698ea-135">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="698ea-135">Template mapping in Data integration</span></span>

<span data-ttu-id="698ea-136">L'illustration suivante présente un exemple de mise en correspondance des tâches du modèle dans le module Intégration des données.</span><span class="sxs-lookup"><span data-stu-id="698ea-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="698ea-137">La mise en correspondance indique les informations de champ qui sont synchronisées entre Finance et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="698ea-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="698ea-138">[![Mise en correspondance des modèles](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="698ea-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
