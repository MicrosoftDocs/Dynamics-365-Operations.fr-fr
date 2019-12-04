---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773960"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="5c412-103">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="5c412-103">Cancel a planning job</span></span>

<span data-ttu-id="5c412-104">Dans Microsoft Dynamics 365 Supply Chain Management, vous pouvez annuler une tâche active de planification qui utilise la fonctionnalité Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="5c412-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="5c412-105">Pour annuler une tâche active de planification, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5c412-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5c412-106">Seules les tâches actives peuvent être annulées.</span><span class="sxs-lookup"><span data-stu-id="5c412-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="5c412-107">Accédez à **Planification \> Paramétrage \> Plans**.</span><span class="sxs-lookup"><span data-stu-id="5c412-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="5c412-108">Permet de sélectionner un plan approprié pour l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="5c412-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="5c412-109">Sélectionnez **Historique**.</span><span class="sxs-lookup"><span data-stu-id="5c412-109">Select **History**.</span></span>
4. <span data-ttu-id="5c412-110">Sélectionnez la tâche de planification à annuler.</span><span class="sxs-lookup"><span data-stu-id="5c412-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="5c412-111">Sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="5c412-111">Select **Cancel**.</span></span>

<span data-ttu-id="5c412-112">Le statut de tâche sera **Annulation en cours** jusqu'à ce que le service Optimisation de la planification confirme que la tâche a été annulée.</span><span class="sxs-lookup"><span data-stu-id="5c412-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="5c412-113">Le statut est alors modifié et passe sur **Annulé**.</span><span class="sxs-lookup"><span data-stu-id="5c412-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="5c412-114">Pour voir les modifications du statut, vous devez actualiser la page en sélectionnant le bouton **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="5c412-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5c412-115">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="5c412-115">Related resources</span></span>

[<span data-ttu-id="5c412-116">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="5c412-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="5c412-117">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="5c412-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="5c412-118">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="5c412-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="5c412-119">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="5c412-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="5c412-120">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="5c412-120">Apply filters to a plan</span></span>](plan-filters.md)
