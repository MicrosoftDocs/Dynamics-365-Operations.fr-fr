---
title: Vue d'ensemble de Project Service Automation
description: Cette rubrique fournit des informations relatives à Dynamics 365 Project Service Automation dans la solution d'intégration Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250551"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="551d0-103">Vue d'ensemble de Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="551d0-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="551d0-104">La solution d'intégration de Project Service Automation avec Finance utilise la fonction Intégration des données pour synchroniser les données entre les instances de Dynamics 365 Finance et Dynamics 365 Project Service Automation via Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="551d0-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="551d0-105">Les modèles d'intégration disponibles avec la fonction Intégration des données activent le flux de projets, de contrats de projet, de lignes de contrat de projet, de jalons de ligne de contrat de projet, de tâches de projet, de catégories de transaction de dépense, d'estimations des heures et d'estimations des dépenses entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="551d0-106">Si vous utilisez la version 7.3.0, vous devez installer KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="551d0-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="551d0-107">Cela vous permet ensuite d'intégrer les projets à prix fixe.</span><span class="sxs-lookup"><span data-stu-id="551d0-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="551d0-108">Si vous utilisez la version 7.3.0, et que vous apportez des transactions de frais de Project Service Automation, vous devez installer KB 4345320 pour inclure ces frais de la facture de projet.</span><span class="sxs-lookup"><span data-stu-id="551d0-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="551d0-109">Si vous utilisez la version 8.0, vous serez en mesure d'utiliser l'intégration des tâches de projet, les catégories de transaction de dépense, les estimations des heures, les estimations des dépenses et le verrouillage des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="551d0-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="551d0-110">Si vous utilisez la version 8.0.1 ou ultérieure, vous pourrez synchroniser les chiffres réels.</span><span class="sxs-lookup"><span data-stu-id="551d0-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="551d0-111">Avant de pouvoir intégrer Project Service Automation avec Finance, vous devez configurer les paramètres d'intégration de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="551d0-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="551d0-112">Pour plus d'informations, voir [Paramètres d'intégration de Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="551d0-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="551d0-113">Cette solution d'intégration active la synchronisation directe dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="551d0-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="551d0-114">Gérez les contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-115">Créez des contrats dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-116">Gérez les lignes de contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-117">Gérez les jalons des lignes de contrats de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-118">Gérez les tâches de projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-119">Gérez les catégories de transaction de dépense dans Finance et synchronisez-les directement entre Finance et Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="551d0-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="551d0-120">Créez des estimations des heures du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-121">Créez des estimations des dépenses du projet dans Project Service Automation et synchronisez-les directement entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="551d0-122">Créez du temps de projet, des dépenses et des transactions réelles de frais dans Project Service Automation, puis créez des transactions de projet dans le journal d'intégration Project Service Automation afin qu'elles puissent être validées dans Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="551d0-123">Synchronisation des données</span><span class="sxs-lookup"><span data-stu-id="551d0-123">Data synchronization</span></span>

<span data-ttu-id="551d0-124">L'illustration suivante indique comment les données sont synchronisées dans le cadre de l'intégration entre Project Service Automation et Finance.</span><span class="sxs-lookup"><span data-stu-id="551d0-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="551d0-125">Tous les modèles ne sont pas disponibles actuellement.</span><span class="sxs-lookup"><span data-stu-id="551d0-125">Not all templates are currently available.</span></span> <span data-ttu-id="551d0-126">Les modèles seront disponibles dès qu'il seront terminés.</span><span class="sxs-lookup"><span data-stu-id="551d0-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="551d0-127">[![Intégration de Project Service Automation avec Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="551d0-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="551d0-128">Configuration requise pour Finance</span><span class="sxs-lookup"><span data-stu-id="551d0-128">System requirements for Finance</span></span>

<span data-ttu-id="551d0-129">Pour utiliser la solution d'intégration de Project Service Automation avec Finance, vous devez installer Enterprise Edition 7.3 avec Platform Update 12 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="551d0-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="551d0-130">Configuration requise pour Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="551d0-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="551d0-131">Pour utiliser la solution d'intégration de Project Service Automation avec Finance, vous devez installer les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="551d0-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="551d0-132">Dynamics 365 Project Service Automation version 9.0.0.0 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="551d0-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="551d0-133">Prospect pour une solution de disponibilités pour Dynamics 365 Sales, version 1.14.0.0 (v14) or ultérieure.</span><span class="sxs-lookup"><span data-stu-id="551d0-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="551d0-134">Solution Project Service Automation avec Finance pour Dynamics 365 Project Service Automation version 1.0.0.0 ou ultérieure</span><span class="sxs-lookup"><span data-stu-id="551d0-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="551d0-135">Installer la solution d'intégration de Project Service Automation avec Finance dans votre instance de Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="551d0-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="551d0-136">Téléchargez la solution d'intégration de Project Service Automation dans Finance depuis le [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=57016), et suivez les instructions fournies dans la solution.</span><span class="sxs-lookup"><span data-stu-id="551d0-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
