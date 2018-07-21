---
title: Project Service Automation
description: "Cette solution utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="d24a5-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d24a5-103">Project Service Automation</span></span>

<span data-ttu-id="d24a5-104">La solution d'intégration de Project Service Automation avec Finance and Operations utilise la fonction Intégration des données pour synchroniser les données entre les instances de Microsoft Dynamics 365 for Finance and Operations et de Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="d24a5-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="d24a5-105">Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de projets, de contrats de projet, de lignes de contrat de projet, de jalons de ligne de contrat de projet, de tâches de projet, de catégories de transaction de dépense, d'estimations des heures et d'estimations des dépenses entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="d24a5-106">Si vous utilisez Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, vous devez installer KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="d24a5-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="d24a5-107">Cela vous permet d'intégrer les projets à prix fixe.</span><span class="sxs-lookup"><span data-stu-id="d24a5-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="d24a5-108">Si vous utilisez la version 8.0 de Dynamics 365 for Finance and Operations, vous pourrez utiliser l'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d24a5-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="d24a5-109">Si vous utilisez la version 8.0.1 de Dynamics 365 for Finance and Operations, vous pourrez synchroniser des transactions réelles.</span><span class="sxs-lookup"><span data-stu-id="d24a5-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="d24a5-110">Si vous utilisez Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, après avoir installé KB 4132657 et KB 4132660, vous pourrez utiliser les modèles pour intégrer les tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et les transactions réelles, ainsi que pour configurer le verrouillage des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d24a5-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="d24a5-111">Si vous devez réinitialiser les répartitions comptables, nous vous recommandons d'installer également KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="d24a5-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="d24a5-112">Avant de pouvoir intégrer Project Service Automation avec Finance and Operations, vous devez configurer les paramètres d'intégration de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d24a5-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="d24a5-113">Pour plus d'informations, voir Paramètres d'intégration de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d24a5-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="d24a5-114">Cette solution d'intégration active la synchronisation directe dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="d24a5-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="d24a5-115">Gérez les contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-116">Créez des contrats dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-117">Gérez les lignes de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-118">Gérez les jalons de ligne de contrat de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-119">Gérez les tâches de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-120">Gérez les catégories de transaction de dépense dans Finance and Operations et synchronisez-les directement entre Finance and Operations et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d24a5-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="d24a5-121">Créez des estimations des heures du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="d24a5-122">Créez des estimations des dépenses du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="d24a5-123">Synchronisation des données</span><span class="sxs-lookup"><span data-stu-id="d24a5-123">Data synchronization</span></span>
<span data-ttu-id="d24a5-124">L'illustration suivante indique comment les données sont synchronisées dans le cadre de l'intégration entre Project Service Automation et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d24a5-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="d24a5-125">Tous les modèles ne sont pas disponibles actuellement.</span><span class="sxs-lookup"><span data-stu-id="d24a5-125">Not all templates are currently available.</span></span> <span data-ttu-id="d24a5-126">Les modèles seront disponibles dès qu'il seront terminés.</span><span class="sxs-lookup"><span data-stu-id="d24a5-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="d24a5-127">[![Intégration de Project Service Automation avec Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="d24a5-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="d24a5-128">Configuration requise pour Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d24a5-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="d24a5-129">Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 avec Platform Update 12 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d24a5-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="d24a5-130">Configuration requise pour Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d24a5-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="d24a5-131">Pour utiliser la solution d'intégration de Project Service Automation avec Finance and Operations, vous devez installer les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="d24a5-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="d24a5-132">Microsoft Dynamics 365 for Project Service Automation, version 9.0.0.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d24a5-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="d24a5-133">Prospect pour une solution de disponibilités pour Dynamics 365 for Sales, version 1.14.0.0 (v14) or ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d24a5-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="d24a5-134">Solution d'intégration de Project Service Automation avec Operations pour Dynamics 365 for Project Service Automation version 1.0.0.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d24a5-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="d24a5-135">Installer la solution d'intégration de Project Service Automation avec Finance and Operations dans votre instance de Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d24a5-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



