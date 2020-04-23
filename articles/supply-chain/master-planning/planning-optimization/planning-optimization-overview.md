---
title: Vue d'ensemble d'Optimisation de la planification
description: Cette rubrique fournit une vue d'ensemble de la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: f88ee8067fdd816ba6890ee28bafe8fa4d3b3ac5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208729"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="fbcc1-103">Vue d'ensemble d'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="fbcc1-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="fbcc1-104">Le complément d'Optimisation de la planification pour Microsoft Dynamics 365 Supply Chain Management permet le calcul de planification en dehors de Dynamics 365 Supply Chain Management et de la base de données SQL associée.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="fbcc1-105">Les avantages associés à la fonctionnalité Optimisation de la planification incluent des performances améliorées et un impact minimum sur la base de données SQL pendant l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="fbcc1-106">De rapides exécutions de la planification peuvent être effectuées même pendant les heures de bureau, afin que les planificateurs puissent réagir immédiatement aux modifications de la demande ou des paramètres.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="fbcc1-107">Pour utiliser Optimisation de a planification, vous devez installer le complément d'Optimisation de la planification depuis votre projet dans Microsoft Dynamics Lifecycle Services (LCS) et activer la fonctionnalité Optimisation de la planification dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="fbcc1-108">Pour plus d'informations, voir [Prise en main d'Optimisation de la planification](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="fbcc1-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="fbcc1-109">L'illustration suivante présente l'avantage d'exécuter Optimisation de la planification pendant les heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Avantage d'exécuter Optimisation de la planification pendant les heures de bureau](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="fbcc1-111">Performances améliorées</span><span class="sxs-lookup"><span data-stu-id="fbcc1-111">Improved performance</span></span>

<span data-ttu-id="fbcc1-112">Optimisation de la planification peut être utilisée dans des scénarios impliquant des plans généraux à long terme.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="fbcc1-113">Elle est spécialement conçue pour les calculs très rapides impliquant des volumes de données très importants.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="fbcc1-114">Puisqu'elle est intégrée comme service à plusieurs locataires ultra-évolutif, plusieurs instances peuvent travailler ensemble en simultané pour calculer le plan.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="fbcc1-115">En outre, le service de planification supprime la charge de la planification de votre système et fonctionne avec un flux de données qui réduit la charge du serveur.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="fbcc1-116">Optimisation de la planification peut vous aider à atteindre les objectifs suivants :</span><span class="sxs-lookup"><span data-stu-id="fbcc1-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="fbcc1-117">Améliorer les performances de planification via une exécution à plus court terme.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="fbcc1-118">Réduire l'impact sur d'autres processus pendant l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="fbcc1-119">Effectuer des exécutions de planification plus fréquentes.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-119">Do more frequent planning runs.</span></span> <span data-ttu-id="fbcc1-120">(Vous n'êtes pas limité aux exécutions quotidiennes.)</span><span class="sxs-lookup"><span data-stu-id="fbcc1-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="fbcc1-121">S'assurer que la future croissance de l'entreprise ne surcharge pas le système de planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="fbcc1-122">Architecture et flux de données</span><span class="sxs-lookup"><span data-stu-id="fbcc1-122">Architecture and data flow</span></span>

<span data-ttu-id="fbcc1-123">Lorsque le complément de l'optimisation de la planification est installé depuis LCS, une connexion sûre au service Optimisation de la planification est établie.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="fbcc1-124">Le service se situe dans le même pays ou la même région du centre de données que l'instance Supply Chain Management associée.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="fbcc1-125">Une fois l'optimisation de la planification configurée, lorsque la planification est exécutée, les données principales et de transaction sont envoyées de Supply Chain Management vers le service Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="fbcc1-126">Si le complément d'Optimisation de la planification est désinstallé, toutes les données associées au service d'Optimisation de la planification sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="fbcc1-127">Flux de données de haut niveau pour les exécutions de régénération</span><span class="sxs-lookup"><span data-stu-id="fbcc1-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="fbcc1-128">Le client Supply Chain Management envoie un signal pour demander l'exécution d'une planification depuis l'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="fbcc1-129">L'Optimisation de la planification demande les données nécessaires via le connecteur intégré.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="fbcc1-130">La base de données SQL envoie les informations requises concernant les données de configuration, générales et de transaction à l'Optimisation de la planification via le connecteur.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="fbcc1-131">Le connecteur traduit les informations entre Supply Chain Management et le service d'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="fbcc1-132">Le service d'Optimisation de la planification mémorise les données relatives à la planification et effectue les calculs requis.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="fbcc1-133">Le résultat de la planification est envoyé à la base de données Supply Chain Management via le connecteur.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="fbcc1-134">Les résultats incluent des informations telles que les ordres prévisionnels et les informations sur l'origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="fbcc1-135">L'Optimisation de la planification envoie un signal à Supply Chain Management pour indiquer que l'exécution de la planification est terminée.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="fbcc1-136">Elle envoie également des messages et avertissements appropriés.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="fbcc1-137">L'illustration suivante présente le flux de données.</span><span class="sxs-lookup"><span data-stu-id="fbcc1-137">The following illustration shows the data flow.</span></span>

![Flux de données pour les exécutions de régénération](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="fbcc1-139">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="fbcc1-139">Related resources</span></span>

[<span data-ttu-id="fbcc1-140">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="fbcc1-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="fbcc1-141">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="fbcc1-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="fbcc1-142">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="fbcc1-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="fbcc1-143">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="fbcc1-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="fbcc1-144">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="fbcc1-144">Cancel a planning job</span></span>](cancel-planning-job.md)
