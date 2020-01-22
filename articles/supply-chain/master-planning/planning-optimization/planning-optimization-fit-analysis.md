---
title: Analyse de concordance d'optimisation de la planification
description: Cette rubrique explique comment vérifier votre configuration et vos données par rapport aux fonctionnalités de la fonction d'optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
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
ms.openlocfilehash: a61529da63bc20fdd591afc94db960b05c284bb9
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935873"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="a9c22-103">Analyse de concordance d'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="a9c22-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="a9c22-104">Pour voir la compatibilité de votre configuration actuelle et des données avec la fonction d'optimisation de la planification, accédez à **Planification** \> **Configuration** \> **Analyse de concordance de l'optimisation de la planification**, puis sélectionnez **Exécuter l'analyse**.</span><span class="sxs-lookup"><span data-stu-id="a9c22-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="a9c22-105">Si l'analyse permet de trouver des incohérences, elles sont répertoriées sur la même page.</span><span class="sxs-lookup"><span data-stu-id="a9c22-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="a9c22-106">(L'exécution de l'analyse peut prendre quelques minutes.)</span><span class="sxs-lookup"><span data-stu-id="a9c22-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="a9c22-107">Si des incohérences sont détectées, vous pouvez utiliser l'optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="a9c22-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="a9c22-108">Les résultats de l'analyse de concordance indiquent simplement les endroits où le service de planification n'honorera pas votre configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="a9c22-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="a9c22-109">En d'autres termes, ils affichent les endroits où certains processus pourraient être ignorés ou ne pourraient pas être pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a9c22-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="a9c22-110">Résultats d'analyse : Exemple 1</span><span class="sxs-lookup"><span data-stu-id="a9c22-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="a9c22-111">**Fonctionnalité :** Production</span><span class="sxs-lookup"><span data-stu-id="a9c22-111">**Feature:** Production</span></span>
- <span data-ttu-id="a9c22-112">**Problème :** les articles au niveau de la nomenclature supérieure à zéro : 56</span><span class="sxs-lookup"><span data-stu-id="a9c22-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="a9c22-113">**Explication :** l'analyse de concordance a trouvé 56 articles avec une configuration de nomenclature pour la production.</span><span class="sxs-lookup"><span data-stu-id="a9c22-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="a9c22-114">Puisque la version actuelle de l'optimisation de la planification en prend pas en charge la production, l'optimisation de la planification génèrera les commandes fournisseur planifiées plutôt que les ordres de production planifiés.</span><span class="sxs-lookup"><span data-stu-id="a9c22-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="a9c22-115">Elle affichera également un avertissement qui répertorie les articles concernés.</span><span class="sxs-lookup"><span data-stu-id="a9c22-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="a9c22-116">Résultats d'analyse : Exemple 2</span><span class="sxs-lookup"><span data-stu-id="a9c22-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="a9c22-117">**Fonctionnalité :** Actions</span><span class="sxs-lookup"><span data-stu-id="a9c22-117">**Feature:** Actions</span></span>
- <span data-ttu-id="a9c22-118">**Problème :** Groupes de couverture avec calcul des actions activé : 6</span><span class="sxs-lookup"><span data-stu-id="a9c22-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="a9c22-119">**Explication :** l'analyse de concordance a trouvé six groupes de couverture où le calcul des actions est activé.</span><span class="sxs-lookup"><span data-stu-id="a9c22-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="a9c22-120">Puisque la version actuelle de l'optimisation de la planification ne prend pas en charge les actions, aucune action ne sera générée pendant la planification.</span><span class="sxs-lookup"><span data-stu-id="a9c22-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="a9c22-121">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="a9c22-121">Related resources</span></span>

[<span data-ttu-id="a9c22-122">Vue d'ensemble de l'optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="a9c22-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="a9c22-123">Prise en main de l'Optimisation de la planification</span><span class="sxs-lookup"><span data-stu-id="a9c22-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="a9c22-124">Afficher l'historique du plan et les journaux de planification</span><span class="sxs-lookup"><span data-stu-id="a9c22-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="a9c22-125">Appliquer les filtres à un plan</span><span class="sxs-lookup"><span data-stu-id="a9c22-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="a9c22-126">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="a9c22-126">Cancel a planning job</span></span>](cancel-planning-job.md)
