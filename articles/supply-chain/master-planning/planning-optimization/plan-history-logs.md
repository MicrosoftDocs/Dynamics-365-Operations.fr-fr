---
title: Afficher l’historique du plan et les journaux de planification
description: Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187245"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="c6624-103">Afficher l’historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="c6624-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c6624-104">Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c6624-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c6624-105">Pour afficher l’historique d’un plan, ouvrez le plan en accédant à **Planification** \> **Paramétrage** \> **Plans** \> **Plans généraux** et en sélectionnant **Historique**.</span><span class="sxs-lookup"><span data-stu-id="c6624-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="c6624-106">L’historique répertorie toutes les tâches du plan sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c6624-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="c6624-107">La liste inclut les tâches terminées et actives.</span><span class="sxs-lookup"><span data-stu-id="c6624-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="c6624-108">L’historique des exécutions de la planification générale de l’optimisation de la planification ne conserve que 60 enregistrements maximum par plan général.</span><span class="sxs-lookup"><span data-stu-id="c6624-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="c6624-109">Chaque fois que vous exécutez un nouveau calcul de planification générale, le premier enregistrement de l’historique de ce plan est supprimé.</span><span class="sxs-lookup"><span data-stu-id="c6624-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="c6624-110">Outre le fait de voir l’heure de début et le statut des tâches, vous pouvez afficher le journal pour une tâche spécifique.</span><span class="sxs-lookup"><span data-stu-id="c6624-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="c6624-111">Le journal inclut des informations supplémentaires et des avertissements.</span><span class="sxs-lookup"><span data-stu-id="c6624-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="c6624-112">Toutes les tâches n’ont pas un journal.</span><span class="sxs-lookup"><span data-stu-id="c6624-112">Not all jobs have a log.</span></span> <span data-ttu-id="c6624-113">Pour afficher le journal pour une tâche, sélectionnez **Journal**.</span><span class="sxs-lookup"><span data-stu-id="c6624-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="c6624-114">Les entrées de journal ne sont stockées que pendant 30 jours après la date de fin de la tâche, après quoi elles sont automatiquement supprimées.</span><span class="sxs-lookup"><span data-stu-id="c6624-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c6624-115">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="c6624-115">Related resources</span></span>

- [<span data-ttu-id="c6624-116">Vue d’ensemble de l’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="c6624-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="c6624-117">Mise en route de l’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="c6624-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="c6624-118">Analyse de concordance d’optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="c6624-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="c6624-119">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="c6624-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="c6624-120">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="c6624-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]