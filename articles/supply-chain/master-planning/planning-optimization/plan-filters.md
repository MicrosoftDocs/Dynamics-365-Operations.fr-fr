---
title: Appliquer les filtres à un plan
description: Cette rubrique explique comment utiliser des filtres sur un plan lorsque la fonctionnalité Optimisation de la planification est utilisée.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
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
ms.openlocfilehash: 73e4a045ff5a9912b898a7115d3d8f530846ebdd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209787"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="f0cf4-103">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="f0cf4-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f0cf4-104">Lorsque la fonctionnalité d'Optimisation de la planification est utilisée, vous pouvez appliquer un filtre à un plan.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="f0cf4-105">Le **filtre de plan** est toujours appliqué lors d'une exécution de planification.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="f0cf4-106">Un **filtre de plan** est utile si vous souhaitez limiter un plan à un groupe d'articles spécifique et veiller à ce qu'aucun autre article ne soit inclus dans le cadre de la planification obtenue.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="f0cf4-107">Si un **filtre de plan** est appliqué et si un filtre de runtime est également appliqué pendant l'exécution de la planification, seule l'intersection des deux filtres est comprise dans l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="f0cf4-108">Le **Filtre de plan** peut être accessible depuis **Plans généraux** lorsque l'Optimisation de la planification est utilisée.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f0cf4-109">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="f0cf4-109">Example scenario</span></span>

<span data-ttu-id="f0cf4-110">Un filtre de plan est configuré. Il inclut des éléments A, B et C. Les exécutions de la planification ont ensuite lieu pour le même plan, mais différents filtres de runtime s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="f0cf4-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="f0cf4-111">**Filtre de runtime qui inclut l'article D :** aucun article n'est planifié, car il n'existe aucune intersection entre le filtre de plan et le filtre de runtime.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="f0cf4-112">**Filtre de runtime qui inclut l'article A et D :** seul l'article A est inclus dans l'exécution de la planification, car l'article D ne fait pas partie du filtre de plan.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="f0cf4-113">**Filtre de runtime qui inclut l'article B :** seul l'article B est inclus dans l'exécution de la planification et le résultat de planification précédent pour l'article A est conservé.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="f0cf4-114">**Filtre de runtime qui inclut tous les articles (filtre vierge) :** les articles A, B et C sont inclus dans l'exécution de la planification et le résultat de la planification précédente pour les articles A et B est remplacé.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="f0cf4-115">Vous devez éviter de définir un filtre de plan sur le plan sélectionné comme **Plan général dynamique actuel** sur la page **Paramètres de planification**.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="f0cf4-116">Sinon, la fonctionnalité dynamique de plan général est limitée aux articles filtrés.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="f0cf4-117">Par exemple, si les exigences nettes sont mises à jour pour un article qui ne fait pas partie du filtre de plan, aucun résultat ne sera généré.</span><span class="sxs-lookup"><span data-stu-id="f0cf4-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="f0cf4-118">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="f0cf4-118">Related resources</span></span>

[<span data-ttu-id="f0cf4-119">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="f0cf4-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="f0cf4-120">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="f0cf4-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="f0cf4-121">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="f0cf4-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="f0cf4-122">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="f0cf4-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="f0cf4-123">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="f0cf4-123">Cancel a planning job</span></span>](cancel-planning-job.md)
