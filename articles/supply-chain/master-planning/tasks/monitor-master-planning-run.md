---
title: Surveiller l'exécution d'une planification générale
description: Cette rubrique explique comment le responsable de production peut vérifier si une exécution de la planification est en cours.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 045b82af6f65b22e1c683f8de47a6df282711e6a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427664"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="473a0-103">Surveiller l'exécution d'une planification générale</span><span class="sxs-lookup"><span data-stu-id="473a0-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="473a0-104">Utiliser un diagramme de Gantt pour visualiser la progression de la planification</span><span class="sxs-lookup"><span data-stu-id="473a0-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="473a0-105">Depuis la page **Afficher la progression de la planification**, vous pouvez afficher les détails des exécutions de planification historiques en tant que diagramme de Gantt.</span><span class="sxs-lookup"><span data-stu-id="473a0-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="473a0-106">Cette fonctionnalité peut vous aider à comprendre le temps passé aux différentes phases de la planification.</span><span class="sxs-lookup"><span data-stu-id="473a0-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="473a0-107">Pour une tâche de planification active actuelle, la page **Afficher la progression de la planification** peut être utilisée pour suivre la progression et afficher le temps restant estimé.</span><span class="sxs-lookup"><span data-stu-id="473a0-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="473a0-108">Activer et utiliser la fonction de visualisation de la progression du plan</span><span class="sxs-lookup"><span data-stu-id="473a0-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="473a0-109">Pour utiliser cette fonctionnalité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="473a0-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="473a0-110">Dans l'espace de travail **Gestion des fonctionnalités**, sous l'onglet **Nouveau**, sélectionnez **Visualisation de la progression de la planification** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="473a0-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="473a0-111">Si la fonctionnalité ne s'affiche pas sur l'onglet **Nouveau**, examinez les onglets **Non activé** et **Tous**.</span><span class="sxs-lookup"><span data-stu-id="473a0-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="473a0-112">Sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="473a0-112">Select **Enable now**.</span></span> <span data-ttu-id="473a0-113">Sinon, sélectionnez **Programme**, puis sélectionnez l'heure à laquelle vous souhaitez activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="473a0-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="473a0-114">La page **Afficher la progression de la planification** peut afficher les tâches historiques de planification et les tâches actives de planification.</span><span class="sxs-lookup"><span data-stu-id="473a0-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="473a0-115">Pour afficher les tâches historiques de planification, il existe deux options.</span><span class="sxs-lookup"><span data-stu-id="473a0-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="473a0-116">Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**, puis, dans le volet Actions, sélectionnez **Historique**.</span><span class="sxs-lookup"><span data-stu-id="473a0-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="473a0-117">Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**</span><span class="sxs-lookup"><span data-stu-id="473a0-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="473a0-118">Accédez à **Planification \> Espaces de travail \> Planification**, sur la vignette de planification cliquez sur **Historique**.</span><span class="sxs-lookup"><span data-stu-id="473a0-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="473a0-119">Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**</span><span class="sxs-lookup"><span data-stu-id="473a0-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="473a0-120">Pour afficher les tâches actives de planification, il existe deux options.</span><span class="sxs-lookup"><span data-stu-id="473a0-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="473a0-121">Accédez à **Planification \> Espaces de travail \> Planification**, dans le volet Actions, sélectionnez **Processus de planification non terminés**.</span><span class="sxs-lookup"><span data-stu-id="473a0-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="473a0-122">Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**.</span><span class="sxs-lookup"><span data-stu-id="473a0-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="473a0-123">Accédez à **Planification \> Espaces de travail \> Planification**, sur la vignette de planification cliquez sur **Afficher la progression**.</span><span class="sxs-lookup"><span data-stu-id="473a0-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="473a0-124">Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**</span><span class="sxs-lookup"><span data-stu-id="473a0-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="473a0-125">Remarque : vous pouvez afficher les tâches actives uniquement lorsqu'une tâche de planification est en cours.</span><span class="sxs-lookup"><span data-stu-id="473a0-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="473a0-126">Analyser une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="473a0-126">Analyze a master planning job</span></span>

<span data-ttu-id="473a0-127">Dans le diagramme de Gantt, vous pouvez développer chacun des processus de planification suivants pour afficher des informations supplémentaires sur le temps passé :</span><span class="sxs-lookup"><span data-stu-id="473a0-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="473a0-128">Initialisation</span><span class="sxs-lookup"><span data-stu-id="473a0-128">Initializing</span></span>
- <span data-ttu-id="473a0-129">Suppression et insertion de données</span><span class="sxs-lookup"><span data-stu-id="473a0-129">Deleting and inserting data</span></span>
- <span data-ttu-id="473a0-130">Planification de la couverture</span><span class="sxs-lookup"><span data-stu-id="473a0-130">Coverage planning</span></span>
- <span data-ttu-id="473a0-131">Retards</span><span class="sxs-lookup"><span data-stu-id="473a0-131">Delays</span></span>
- <span data-ttu-id="473a0-132">Messages d’action</span><span class="sxs-lookup"><span data-stu-id="473a0-132">Action messages</span></span>
- <span data-ttu-id="473a0-133">Finalisation</span><span class="sxs-lookup"><span data-stu-id="473a0-133">Finalization</span></span>
- <span data-ttu-id="473a0-134">Confirmation automatique</span><span class="sxs-lookup"><span data-stu-id="473a0-134">Auto-firming</span></span>

<span data-ttu-id="473a0-135">Le diagramme de Gantt est un outil utile si vous souhaitez afficher l'impact de l'utilisation des messages d'action.</span><span class="sxs-lookup"><span data-stu-id="473a0-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="473a0-136">Navigation dans le diagramme de Gantt</span><span class="sxs-lookup"><span data-stu-id="473a0-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="473a0-137">Pour développer le groupe sélectionné et afficher les détails, sélectionnez le signe (**+**) dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="473a0-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="473a0-138">Pour réduire le groupe sélectionné, sélectionnez le signe (**-**) dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="473a0-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="473a0-139">Vous pouvez utiliser le clavier pour la navigation.</span><span class="sxs-lookup"><span data-stu-id="473a0-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="473a0-140">Utilisez les touches **Flèche vers le haut** et **Flèche vers le bas** pour passer d'une ligne à l'autre.</span><span class="sxs-lookup"><span data-stu-id="473a0-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="473a0-141">Utilisez les touches **Flèche droite** et **Flèche gauche** pour développer et réduire les groupes.</span><span class="sxs-lookup"><span data-stu-id="473a0-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="473a0-142">Pour ouvrir ou fermer tous les niveaux dans le diagramme de Gantt, sélectionnez **Développer tout** ou **Réduire tout**.</span><span class="sxs-lookup"><span data-stu-id="473a0-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="473a0-143">Pour afficher le temps de traitement associé, survolez une tâche avec la souris.</span><span class="sxs-lookup"><span data-stu-id="473a0-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="473a0-144">(Les tâches sont le niveau le plus bas dans le diagramme de Gantt.)</span><span class="sxs-lookup"><span data-stu-id="473a0-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="473a0-145">Afficher une exécution supplémentaire de planification pour comparer des tâches</span><span class="sxs-lookup"><span data-stu-id="473a0-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="473a0-146">En sélectionnant une tâche de planification dans le champ **Afficher une exécution de planification supplémentaire**, vous pouvez afficher une exécution supplémentaire de planification dans le diagramme de Gantt et comparer les deux tâches.</span><span class="sxs-lookup"><span data-stu-id="473a0-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="473a0-147">Affichage au niveau de la nomenclature</span><span class="sxs-lookup"><span data-stu-id="473a0-147">BOM-level display</span></span>

<span data-ttu-id="473a0-148">Les niveaux de nomenclature sont affichés différemment pour la planification de couverture, les retards, les actions et la confirmation.</span><span class="sxs-lookup"><span data-stu-id="473a0-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="473a0-149">**Planification de la couverture** : les niveaux de nomenclature sont affichés comme prévu.</span><span class="sxs-lookup"><span data-stu-id="473a0-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="473a0-150">Ils sont calculés de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="473a0-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="473a0-151">**Exemple :** niveau de nomenclature 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="473a0-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="473a0-152">**Retards** : les niveaux de nomenclature sont affichés comme niveaux de nomenclature de planification de la couverture multipliés par – 1.</span><span class="sxs-lookup"><span data-stu-id="473a0-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="473a0-153">(Autrement dit, ils ont un signe négatif.)</span><span class="sxs-lookup"><span data-stu-id="473a0-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="473a0-154">**Exemple :** niveau de nomenclature –2, –1, 0</span><span class="sxs-lookup"><span data-stu-id="473a0-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="473a0-155">**Message d'action** : les niveaux de nomenclature sont affichés comme prévu.</span><span class="sxs-lookup"><span data-stu-id="473a0-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="473a0-156">Ils sont calculés de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="473a0-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="473a0-157">**Exemple :** niveau de nomenclature 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="473a0-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="473a0-158">**Confirmation automatique** : les niveaux de nomenclature sont affichés comme 999 moins le niveau de nomenclature de la planification de couverture.</span><span class="sxs-lookup"><span data-stu-id="473a0-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="473a0-159">**Exemple :** niveau de nomenclature 999, 998, 997</span><span class="sxs-lookup"><span data-stu-id="473a0-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="473a0-160">Le tableau suivant résume le comportement.</span><span class="sxs-lookup"><span data-stu-id="473a0-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="473a0-161">Niveau de nomenclature qui s'affiche</span><span class="sxs-lookup"><span data-stu-id="473a0-161">BOM level that is shown</span></span> | <span data-ttu-id="473a0-162">Article final</span><span class="sxs-lookup"><span data-stu-id="473a0-162">End item</span></span> | <span data-ttu-id="473a0-163">Sous-composant</span><span class="sxs-lookup"><span data-stu-id="473a0-163">Subcomponent</span></span> | <span data-ttu-id="473a0-164">Matière première</span><span class="sxs-lookup"><span data-stu-id="473a0-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="473a0-165">Planification de la couverture</span><span class="sxs-lookup"><span data-stu-id="473a0-165">Coverage planning</span></span> | <span data-ttu-id="473a0-166">0</span><span class="sxs-lookup"><span data-stu-id="473a0-166">0</span></span> | <span data-ttu-id="473a0-167">1</span><span class="sxs-lookup"><span data-stu-id="473a0-167">1</span></span> | <span data-ttu-id="473a0-168">2</span><span class="sxs-lookup"><span data-stu-id="473a0-168">2</span></span> |
| <span data-ttu-id="473a0-169">Retards</span><span class="sxs-lookup"><span data-stu-id="473a0-169">Delays</span></span> | <span data-ttu-id="473a0-170">0</span><span class="sxs-lookup"><span data-stu-id="473a0-170">0</span></span> | <span data-ttu-id="473a0-171">–1</span><span class="sxs-lookup"><span data-stu-id="473a0-171">–1</span></span> | <span data-ttu-id="473a0-172">–2</span><span class="sxs-lookup"><span data-stu-id="473a0-172">–2</span></span> |
| <span data-ttu-id="473a0-173">Message d'action</span><span class="sxs-lookup"><span data-stu-id="473a0-173">Action message</span></span> | <span data-ttu-id="473a0-174">0</span><span class="sxs-lookup"><span data-stu-id="473a0-174">0</span></span> | <span data-ttu-id="473a0-175">1</span><span class="sxs-lookup"><span data-stu-id="473a0-175">1</span></span> | <span data-ttu-id="473a0-176">2</span><span class="sxs-lookup"><span data-stu-id="473a0-176">2</span></span> |
| <span data-ttu-id="473a0-177">Confirmation automatique</span><span class="sxs-lookup"><span data-stu-id="473a0-177">Auto-firming</span></span> | <span data-ttu-id="473a0-178">999</span><span class="sxs-lookup"><span data-stu-id="473a0-178">999</span></span> | <span data-ttu-id="473a0-179">998</span><span class="sxs-lookup"><span data-stu-id="473a0-179">998</span></span> | <span data-ttu-id="473a0-180">997</span><span class="sxs-lookup"><span data-stu-id="473a0-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="473a0-181">Visualiser la progression</span><span class="sxs-lookup"><span data-stu-id="473a0-181">Visualize progress</span></span>

<span data-ttu-id="473a0-182">Si vous affichez une tâche de planification en cours d'exécution, la progression est affichée en couleurs dans le diagramme de Gantt.</span><span class="sxs-lookup"><span data-stu-id="473a0-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="473a0-183">Les couleurs suivantes s'appliquent au thème bleu.</span><span class="sxs-lookup"><span data-stu-id="473a0-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="473a0-184">Pour d'autres thèmes de couleur, les couleurs différeront.</span><span class="sxs-lookup"><span data-stu-id="473a0-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="473a0-185">**Bleu foncé** : Tâches de planification terminées.</span><span class="sxs-lookup"><span data-stu-id="473a0-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="473a0-186">**Orange** : la tâche qui est actuellement ouverte.</span><span class="sxs-lookup"><span data-stu-id="473a0-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="473a0-187">**Bleu clair** : l'estimation pour les tâches restantes.</span><span class="sxs-lookup"><span data-stu-id="473a0-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="473a0-188">La couleur est affichée uniquement sur le niveau le plus bas dans le diagramme de Gantt.</span><span class="sxs-lookup"><span data-stu-id="473a0-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="473a0-189">Sélectionnez **Développer tout** pour afficher toutes les tâches dans la tâche de planification.</span><span class="sxs-lookup"><span data-stu-id="473a0-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="473a0-190">L'estimation des tâches restantes est basée sur des tâches historiques de planification.</span><span class="sxs-lookup"><span data-stu-id="473a0-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="473a0-191">Exécuter la planification et suivre le temps de traitement</span><span class="sxs-lookup"><span data-stu-id="473a0-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="473a0-192">Dans le tableau de bord par défaut, sélectionnez **Planification**.</span><span class="sxs-lookup"><span data-stu-id="473a0-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="473a0-193">Dans le champ **Plan**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="473a0-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="473a0-194">Sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="473a0-194">Select **Run**.</span></span>
1. <span data-ttu-id="473a0-195">Définissez l'option **Suivre le temps de traitement** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="473a0-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="473a0-196">Entrez un nombre dans le champ **Nombre de threads**.</span><span class="sxs-lookup"><span data-stu-id="473a0-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="473a0-197">Dans l'organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="473a0-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="473a0-198">Dans la grille, sélectionnez la ligne où le champ **Champ** est défini sur **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="473a0-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="473a0-199">Dans le champ **Critère**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="473a0-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="473a0-200">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="473a0-200">Select **OK**.</span></span>
