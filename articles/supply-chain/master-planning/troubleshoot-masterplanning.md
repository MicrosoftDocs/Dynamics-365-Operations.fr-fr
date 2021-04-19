---
title: Résoudre des problèmes de planification
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation de la planification.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8e78634c0efb1c401297559ce40b2ca30519f3bf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809468"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="f7dff-103">Résoudre des problèmes de planification</span><span class="sxs-lookup"><span data-stu-id="f7dff-103">Troubleshoot master planning</span></span>

<span data-ttu-id="f7dff-104">Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="f7dff-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="f7dff-105">La distribution de nomenclatures se comporte différemment pour les ordres de fabrication confirmés et pour les ordres de fabrication estimés pour le travail créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="f7dff-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f7dff-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-106">Issue description</span></span>

<span data-ttu-id="f7dff-107">Lorsqu’un ordre de fabrication est confirmé, les articles ne sont pas distribués lorsque vous distribuez la nomenclature (BOM).</span><span class="sxs-lookup"><span data-stu-id="f7dff-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="f7dff-108">Cependant, lorsque vous créez manuellement un ordre de travail et que vous estimez ensuite l’ordre de fabrication, les postes sont répartis.</span><span class="sxs-lookup"><span data-stu-id="f7dff-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f7dff-109">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-109">Issue resolution</span></span>

<span data-ttu-id="f7dff-110">Le système fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="f7dff-110">The system is working as expected.</span></span> <span data-ttu-id="f7dff-111">La distribution qui se produit lorsque l’ordre de fabrication est confirmé pointera vers l’ordre planifié, mais il ne semble pas que l’ordre planifié soit actuellement confirmé dans ce cas.</span><span class="sxs-lookup"><span data-stu-id="f7dff-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="f7dff-112">Cependant, si l’ordre de fabrication a été estimé, l’explosion est déclenchée à partir de l’ordre de fabrication lancé lorsqu’il n’existe aucun ordre planifié.</span><span class="sxs-lookup"><span data-stu-id="f7dff-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="f7dff-113">La valeur Délai n’est pas mise à jour lorsque je replanifie un ordre planifié.</span><span class="sxs-lookup"><span data-stu-id="f7dff-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="f7dff-114">Pour mettre à jour le délai des ordres planifiés, ouvrez la boîte de dialogue **Replanification** pour l’ordre planifié.</span><span class="sxs-lookup"><span data-stu-id="f7dff-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="f7dff-115">Dans l’organisateur **Répartition**, assurez-vous que l’option **Traiter la vague au lancement dans l’entrepôt** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="f7dff-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="f7dff-116">La planification de la production ne prend pas en compte les marges de sécurité définies sur la couverture des articles pour l’approvisionnement indexé.</span><span class="sxs-lookup"><span data-stu-id="f7dff-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f7dff-117">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-117">Issue description</span></span>

<span data-ttu-id="f7dff-118">La planification tient compte des marges de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f7dff-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="f7dff-119">Cependant, les marges de sécurité sont ignorées lors de la planification des ordres de fabrication planifiés.</span><span class="sxs-lookup"><span data-stu-id="f7dff-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f7dff-120">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-120">Issue resolution</span></span>

<span data-ttu-id="f7dff-121">Les marges ne sont prises en compte que lors de la planification, pas lors de la planification manuelle.</span><span class="sxs-lookup"><span data-stu-id="f7dff-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="f7dff-122">Les marges sont conçues pour agir comme un tampon pendant la phase de planification, pour donner une certaine "marge" pour le processus réel.</span><span class="sxs-lookup"><span data-stu-id="f7dff-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="f7dff-123">Pour obtenir le résultat souhaité, vous pouvez supprimer la marge.</span><span class="sxs-lookup"><span data-stu-id="f7dff-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="f7dff-124">L’itinéraire doit ensuite être mis à jour pour inclure l’heure souhaitée (par exemple, en tant que durée de la file d’attente).</span><span class="sxs-lookup"><span data-stu-id="f7dff-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="f7dff-125">La planification et la planification manuelle devraient alors produire le même résultat.</span><span class="sxs-lookup"><span data-stu-id="f7dff-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="f7dff-126">Les commandes planifiées sont générées même si nous avons des articles en stock et que des ordres de fabrication existent déjà pour eux.</span><span class="sxs-lookup"><span data-stu-id="f7dff-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="f7dff-127">Vous pourrez peut-être résoudre ce problème en augmentant la valeur **Jours positifs** pour les groupes concernés sur la page **Groupe de couverture**.</span><span class="sxs-lookup"><span data-stu-id="f7dff-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="f7dff-128">Ce changement amènera le système à déterminer si le stock disponible peut être utilisé pour la demande.</span><span class="sxs-lookup"><span data-stu-id="f7dff-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="f7dff-129">Ensuite, un nouvel ordre planifié ne sera pas généré pour les articles en stock.</span><span class="sxs-lookup"><span data-stu-id="f7dff-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="f7dff-130">La planification générale ne semble pas respecter les limites de capacité et prévoit plus que la capacité disponible.</span><span class="sxs-lookup"><span data-stu-id="f7dff-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f7dff-131">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-131">Issue description</span></span>

<span data-ttu-id="f7dff-132">Lorsque vous utilisez la planification des opérations là où il y a une capacité limitée et où l’itinéraire spécifie un mélange d’exigences pour un groupe de ressources et des ressources individuelles, il existe un faible risque de surréservation en raison de la façon dont l’algorithme valide les conflits de capacité.</span><span class="sxs-lookup"><span data-stu-id="f7dff-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="f7dff-133">Cette surréservation peut se produire lorsque vous utilisez des assistants pour exécuter la planification générale.</span><span class="sxs-lookup"><span data-stu-id="f7dff-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="f7dff-134">Il est plus probable que cela se produise s’il existe de nombreux travaux dont la durée d’exécution est relativement courte.</span><span class="sxs-lookup"><span data-stu-id="f7dff-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f7dff-135">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-135">Issue resolution</span></span>

<span data-ttu-id="f7dff-136">S’il est essentiel qu’aucune surréservation ne se produise pour la planification des opérations, vous pouvez faire de la planification une partie de la planification mono-thread en activant l’option **Capacité finie précise pour la planification des opérations** sur la page **Paramètres de planification**.</span><span class="sxs-lookup"><span data-stu-id="f7dff-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="f7dff-137">Cette option n’est pas disponible par défaut.</span><span class="sxs-lookup"><span data-stu-id="f7dff-137">This option isn't available by default.</span></span> <span data-ttu-id="f7dff-138">Vous devez l’ajouter manuellement à la page à l’aide des fonctionnalités de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="f7dff-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="f7dff-139">Lorsque vous utilisez cette option, la planification s’exécute plus lentement en raison du manque de traitement parallèle.</span><span class="sxs-lookup"><span data-stu-id="f7dff-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="f7dff-140">Les commandes planifiées prennent du temps à se mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f7dff-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f7dff-141">Description du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-141">Issue description</span></span>

<span data-ttu-id="f7dff-142">Lors de la mise à jour de la quantité requise et/ou de la date de livraison d’un ordre planifié, il faut généralement au moins 30 secondes par commande pour enregistrer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f7dff-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f7dff-143">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="f7dff-143">Issue resolution</span></span>

<span data-ttu-id="f7dff-144">Il s’agit d’un problème connu avec le moteur de planification intégré.</span><span class="sxs-lookup"><span data-stu-id="f7dff-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="f7dff-145">Cela est dû à la distribution automatique sous-jacente à travers la structure de la nomenclature lors des modifications.</span><span class="sxs-lookup"><span data-stu-id="f7dff-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="f7dff-146">Ce problème est résolu dans l’Optimisation de la planification, où un planificateur peut mettre à jour et approuver les commandes pertinentes et, s’il le souhaite, déclencher un cycle de planification pour mettre à jour les ordres planifiés pour la structure de nomenclature sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="f7dff-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="f7dff-147">Une façon d’améliorer les performances avec le moteur de planification intégré consiste à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7dff-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="f7dff-148">Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.</span><span class="sxs-lookup"><span data-stu-id="f7dff-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="f7dff-149">Sélectionnez un plan.</span><span class="sxs-lookup"><span data-stu-id="f7dff-149">Select a plan.</span></span>
1. <span data-ttu-id="f7dff-150">Développez le raccourci **Plage de gestion en jours**.</span><span class="sxs-lookup"><span data-stu-id="f7dff-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="f7dff-151">Définissez **Répartition** sur *Oui* et définissez le champ sous ce paramètre sur 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="f7dff-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="f7dff-152">Cela limitera la période des distributions effectuées pour ce plan à une seule journée.</span><span class="sxs-lookup"><span data-stu-id="f7dff-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]