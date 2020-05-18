---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
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
ms.openlocfilehash: 4b65d344cd764740cc1485969c2fc4c2052e55e2
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323460"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="b9828-103">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="b9828-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9828-104">Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b9828-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="b9828-105">Lorsque vous cliquez sur **Annuler** dans la boîte de dialogue lorsqu'une tâche d'optimisation de la planification est déclenchée directement à partir de l'interface utilisateur (pas en arrière-plan), cette dernière ne sera pas annulée.</span><span class="sxs-lookup"><span data-stu-id="b9828-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="b9828-106">Même si vous recevez un avertissement tel que « Opération annulée », vous devez tout de même effectuer les étapes suivantes pour annuler une tâche de planification à l'aide de la fonctionnalité Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="b9828-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="b9828-107">Pour annuler une tâche active de planification, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b9828-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9828-108">Seules les tâches actives peuvent être annulées.</span><span class="sxs-lookup"><span data-stu-id="b9828-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="b9828-109">Accédez à **Planification \> Paramétrage \> Plans**.</span><span class="sxs-lookup"><span data-stu-id="b9828-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="b9828-110">Permet de sélectionner un plan approprié pour l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="b9828-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="b9828-111">Sélectionnez **Historique**.</span><span class="sxs-lookup"><span data-stu-id="b9828-111">Select **History**.</span></span>
4. <span data-ttu-id="b9828-112">Sélectionnez la tâche de planification à annuler.</span><span class="sxs-lookup"><span data-stu-id="b9828-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="b9828-113">Sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="b9828-113">Select **Cancel**.</span></span>

<span data-ttu-id="b9828-114">Le statut de tâche sera **Annulation en cours** jusqu'à ce que le service Optimisation de la planification confirme que la tâche a été annulée.</span><span class="sxs-lookup"><span data-stu-id="b9828-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="b9828-115">Le statut est alors modifié et passe sur **Annulé**.</span><span class="sxs-lookup"><span data-stu-id="b9828-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="b9828-116">Pour voir les modifications du statut, vous devez actualiser la page en sélectionnant le bouton **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="b9828-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9828-117">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b9828-117">Additional resources</span></span>

[<span data-ttu-id="b9828-118">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b9828-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="b9828-119">Mise en route de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b9828-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="b9828-120">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="b9828-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="b9828-121">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="b9828-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="b9828-122">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="b9828-122">Apply filters to a plan</span></span>](plan-filters.md)
