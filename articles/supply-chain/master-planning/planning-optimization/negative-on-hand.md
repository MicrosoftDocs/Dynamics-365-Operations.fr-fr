---
title: Planification avec des quantités disponibles négatives
description: Cette rubrique explique comment une quantité disponible négative est gérée lorsque vous utilisez la fonctionnalité d'optimisation de la planification.
author: ChristianRytt
manager: AnnBe
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ca12d13f7318f649cb1dbc0f7c3cf56502c9d3ea
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3077482"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="de07f-103">Planification avec des quantités disponibles négatives</span><span class="sxs-lookup"><span data-stu-id="de07f-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de07f-104">Si le système affiche une quantité globale disponible négative, le moteur de planification traite la quantité comme étant égale à 0 (zéro) pour éviter tout approvisionnement excessif.</span><span class="sxs-lookup"><span data-stu-id="de07f-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="de07f-105">Voici comment fonctionne cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="de07f-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="de07f-106">La fonctionnalité d'optimisation de la planification regroupe les quantités disponibles au niveau le plus bas des dimensions de couverture.</span><span class="sxs-lookup"><span data-stu-id="de07f-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="de07f-107">(Par exemple, si *emplacement* n'est pas une dimension de couverture, la fonctionnalité d'optimisation de la planification regroupe les quantités disponibles au niveau *entrepôt*.)</span><span class="sxs-lookup"><span data-stu-id="de07f-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="de07f-108">Si la quantité globale disponible au niveau le plus bas des dimensions de couverture est négative, le système suppose que la quantité disponible est vraiment égale à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="de07f-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de07f-109">Le système de planification peut seulement être aussi précis que les données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="de07f-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="de07f-110">Si les données d'entrée sont inexactes, les enregistrements de la quantité disponible négative indiqueront que les informations de stock dans Microsoft Dynamics 365 Supply Chain Management ne sont pas synchronisées avec le monde réel.</span><span class="sxs-lookup"><span data-stu-id="de07f-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="de07f-111">Par conséquent, le résultat de la planification sera erroné.</span><span class="sxs-lookup"><span data-stu-id="de07f-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="de07f-112">Pour obtenir un résultat de planification précis, vous devez réduire le nombre d'enregistrements affichant une quantité disponible négative.</span><span class="sxs-lookup"><span data-stu-id="de07f-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="de07f-113">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="de07f-113">Example 1</span></span>

<span data-ttu-id="de07f-114">L'entrepôt 13 est configuré de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="de07f-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="de07f-115">**Code couverture** : Min./Max.</span><span class="sxs-lookup"><span data-stu-id="de07f-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="de07f-116">**Minimum** : 15 pièces (pcs)</span><span class="sxs-lookup"><span data-stu-id="de07f-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="de07f-117">**Maximum** : 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="de07f-118">Le niveau le plus bas des dimensions de couverture est *entrepôt*, et les quantités disponibles suivantes sont enregistrées au niveau *emplacement* :</span><span class="sxs-lookup"><span data-stu-id="de07f-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="de07f-119">**Site 1, entrepôt 13, emplacement 1** : 20 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="de07f-120">**Site 1, entrepôt 13, emplacement 2** : &minus;8 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="de07f-121">Par conséquent, la quantité globale disponible pour l'entrepôt 13 est 12 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="de07f-122">(= 20 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-122">(= 20 pcs.</span></span> <span data-ttu-id="de07f-123">&minus; 8 pcs).</span><span class="sxs-lookup"><span data-stu-id="de07f-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="de07f-124">Dans ce cas, le moteur de planification utilise une quantité globale disponible de 12 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="de07f-125">pour l'entrepôt 13.</span><span class="sxs-lookup"><span data-stu-id="de07f-125">for warehouse 13.</span></span>

<span data-ttu-id="de07f-126">Le résultat est une commande planifiée de 13 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="de07f-127">(= 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-127">(= 25 pcs.</span></span> <span data-ttu-id="de07f-128">&minus; 12 pcs) pour remplir l'entrepôt 13 de 12 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="de07f-129">à 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="de07f-130">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="de07f-130">Example 2</span></span>

<span data-ttu-id="de07f-131">L'entrepôt 13 est configuré de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="de07f-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="de07f-132">**Code couverture** : Min./Max.</span><span class="sxs-lookup"><span data-stu-id="de07f-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="de07f-133">**Minimum** : 15 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="de07f-134">**Maximum** : 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="de07f-135">Le niveau le plus bas des dimensions de couverture est *entrepôt*, et les quantités disponibles suivantes sont enregistrées au niveau *emplacement* :</span><span class="sxs-lookup"><span data-stu-id="de07f-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="de07f-136">**Site 1, entrepôt 13, emplacement 1** : 4 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="de07f-137">**Site 1, entrepôt 13, emplacement 2** : &minus;8 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="de07f-138">Par conséquent, la quantité globale disponible pour l'entrepôt 13 est &minus;4 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="de07f-139">(= 4 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-139">(= 4 pcs.</span></span> <span data-ttu-id="de07f-140">&minus; 8 pcs).</span><span class="sxs-lookup"><span data-stu-id="de07f-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="de07f-141">Autrement dit, elle est inférieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="de07f-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="de07f-142">Dans ce cas, le moteur de planification suppose que la quantité disponible pour l'entrepôt 13 est 0 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="de07f-143">au lieu de &minus;4 pcs.</span><span class="sxs-lookup"><span data-stu-id="de07f-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="de07f-144">Le résultat est une commande planifiée de 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="de07f-145">(= 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-145">(= 25 pcs.</span></span> <span data-ttu-id="de07f-146">&minus; 0 pcs) pour remplir l'entrepôt 13 de 0 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="de07f-147">à 25 pcs</span><span class="sxs-lookup"><span data-stu-id="de07f-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="de07f-148">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="de07f-148">Related resources</span></span>

[<span data-ttu-id="de07f-149">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="de07f-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="de07f-150">Mise en route de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="de07f-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="de07f-151">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="de07f-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="de07f-152">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="de07f-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="de07f-153">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="de07f-153">Cancel a planning job</span></span>](cancel-planning-job.md)
