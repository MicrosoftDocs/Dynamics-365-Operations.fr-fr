---
title: Prise en charge du tableau de transfert kanban pour les scanneurs de codes-barres
description: "La tableau de transfert kanban prend en charge l'entrée de scanneur à partir d'un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0696580dcf50139639dace641169d041021cf1b8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="df5be-103">Prise en charge du tableau de transfert kanban pour les scanneurs de codes-barres</span><span class="sxs-lookup"><span data-stu-id="df5be-103">Kanban transfer board support for barcode scanners</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="df5be-104">La tableau de transfert kanban prend en charge l'entrée de scanneur à partir d'un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="df5be-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="df5be-105">Modes d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="df5be-105">Registration modes</span></span>
------------------

<span data-ttu-id="df5be-106">Dans l'organisateur **Enregistrement du scanneur**, vous pouvez sélectionner le mode d'enregistrement, qui contrôle l'action lorsque vous numérisez un numéro de carte kanban ou entrez manuellement le numéro dans le champ Numéro de carte kanban.</span><span class="sxs-lookup"><span data-stu-id="df5be-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="df5be-107">Définir le mode d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="df5be-107">Set registration mode</span></span> | <span data-ttu-id="df5be-108">Description</span><span class="sxs-lookup"><span data-stu-id="df5be-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="df5be-109">Commencer</span><span class="sxs-lookup"><span data-stu-id="df5be-109">Start</span></span>                 | <span data-ttu-id="df5be-110">Enregistre une opération de transfert de kanban avec le statut « En cours ».</span><span class="sxs-lookup"><span data-stu-id="df5be-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="df5be-111">Terminée</span><span class="sxs-lookup"><span data-stu-id="df5be-111">Complete</span></span>              | <span data-ttu-id="df5be-112">Enregistre une opération de transfert de kanban avec le statut « Terminé ».</span><span class="sxs-lookup"><span data-stu-id="df5be-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="df5be-113">Vide</span><span class="sxs-lookup"><span data-stu-id="df5be-113">Empty</span></span>                 | <span data-ttu-id="df5be-114">Enregistre l'unité de manutention du matériel référencée par une carte kanban avec le statut « Vide ».</span><span class="sxs-lookup"><span data-stu-id="df5be-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="df5be-115">Sélectionner</span><span class="sxs-lookup"><span data-stu-id="df5be-115">Select</span></span>                | <span data-ttu-id="df5be-116">Enregistre un numéro de carte kanban et sélectionne automatiquement l'opération référencée dans la liste du kanban.</span><span class="sxs-lookup"><span data-stu-id="df5be-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="df5be-117">Sélection du mode d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="df5be-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="df5be-118">Lorsque vous utilisez un lecteur de codes-barres pour sélectionner une tâche, le mode d'affichage du tableau kanban change.</span><span class="sxs-lookup"><span data-stu-id="df5be-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="df5be-119">Dans ce mode, les conditions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="df5be-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="df5be-120">Seule la tâche de kanban numérisée s'affiche.</span><span class="sxs-lookup"><span data-stu-id="df5be-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="df5be-121">Les détails de la tâche sélectionnée s'affichent dans l'organisateur **Détails**.</span><span class="sxs-lookup"><span data-stu-id="df5be-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="df5be-122">L'organisateur **Messages** affiche les messages uniquement pour la tâche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="df5be-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="df5be-123">Vous pouvez modifier le statut de la tâche à l'aide des fonctions disponibles dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="df5be-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="df5be-124">Le tableau de transfert kanban continue à n'afficher qu'une seule tâche pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="df5be-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="df5be-125">Vous pouvez mettre à jour les informations de la liste de tâches manuellement en cliquant sur **Actualiser** (Maj+F5) dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="df5be-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="df5be-126">Après avoir actualisé les informations, les résultats complets pour le filtre de tâches s'affichent à nouveau.</span><span class="sxs-lookup"><span data-stu-id="df5be-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="df5be-127">Statut de tâche et actions possibles</span><span class="sxs-lookup"><span data-stu-id="df5be-127">Job status and possible actions</span></span>
<span data-ttu-id="df5be-128">Le statut de la tâche sélectionnée et le statut de toute tâche liée aux kanbans d'événement déterminent si vous pouvez poursuivre le traitement de la tâche.</span><span class="sxs-lookup"><span data-stu-id="df5be-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="df5be-129">Le tableau suivant affiche des informations sur ces statuts et tâches :</span><span class="sxs-lookup"><span data-stu-id="df5be-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="df5be-130">Statuts disponibles pour les tâches ou pour les unités de manutention référencées par les tâches.</span><span class="sxs-lookup"><span data-stu-id="df5be-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="df5be-131">Chaque tâche que vous pouvez exécuter pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="df5be-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df5be-132">Type de tâche</span><span class="sxs-lookup"><span data-stu-id="df5be-132">Job type</span></span></th>
<th><span data-ttu-id="df5be-133">Statut de la tâche ou statut de l'unité de manutention</span><span class="sxs-lookup"><span data-stu-id="df5be-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="df5be-134">Mettre à jour les prélèvements</span><span class="sxs-lookup"><span data-stu-id="df5be-134">Update picking list</span></span></th>
<th><span data-ttu-id="df5be-135">Commencer</span><span class="sxs-lookup"><span data-stu-id="df5be-135">Start</span></span></th>
<th><span data-ttu-id="df5be-136">Mettre à jour l'enregistrement</span><span class="sxs-lookup"><span data-stu-id="df5be-136">Update registration</span></span></th>
<th><span data-ttu-id="df5be-137">Terminée</span><span class="sxs-lookup"><span data-stu-id="df5be-137">Complete</span></span></th>
<th><span data-ttu-id="df5be-138">Vide</span><span class="sxs-lookup"><span data-stu-id="df5be-138">Empty</span></span></th>
<th><span data-ttu-id="df5be-139">Créer des kanbans d'événement</span><span class="sxs-lookup"><span data-stu-id="df5be-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="df5be-140">Transfert</span><span class="sxs-lookup"><span data-stu-id="df5be-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="df5be-141">Non planifié</span><span class="sxs-lookup"><span data-stu-id="df5be-141">Not planned</span></span></li>
<li><span data-ttu-id="df5be-142">Aucune tâche liée, ou les tâches liées sont terminées</span><span class="sxs-lookup"><span data-stu-id="df5be-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="df5be-143">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-143">Yes</span></span></td>
<td><span data-ttu-id="df5be-144">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-144">Yes</span></span></td>
<td><span data-ttu-id="df5be-145">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-145">Yes</span></span></td>
<td><span data-ttu-id="df5be-146">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-146">Yes</span></span></td>
<td><span data-ttu-id="df5be-147">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-147">No</span></span></td>
<td><span data-ttu-id="df5be-148">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="df5be-149">Transfert</span><span class="sxs-lookup"><span data-stu-id="df5be-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="df5be-150">Non planifié</span><span class="sxs-lookup"><span data-stu-id="df5be-150">Not planned</span></span></li>
<li><span data-ttu-id="df5be-151">La tâche liée n'est pas terminée</span><span class="sxs-lookup"><span data-stu-id="df5be-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="df5be-152">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-152">Yes</span></span></td>
<td><span data-ttu-id="df5be-153">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-153">No</span></span></td>
<td><span data-ttu-id="df5be-154">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-154">Yes</span></span></td>
<td><span data-ttu-id="df5be-155">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-155">No</span></span></td>
<td><span data-ttu-id="df5be-156">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-156">No</span></span></td>
<td><span data-ttu-id="df5be-157">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="df5be-158">Transfert</span><span class="sxs-lookup"><span data-stu-id="df5be-158">Transfer</span></span></td>
<td><span data-ttu-id="df5be-159">En cours</span><span class="sxs-lookup"><span data-stu-id="df5be-159">In progress</span></span></td>
<td><span data-ttu-id="df5be-160">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-160">Yes</span></span></td>
<td><span data-ttu-id="df5be-161">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-161">No</span></span></td>
<td><span data-ttu-id="df5be-162">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-162">Yes</span></span></td>
<td><span data-ttu-id="df5be-163">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-163">Yes</span></span></td>
<td><span data-ttu-id="df5be-164">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-164">No</span></span></td>
<td><span data-ttu-id="df5be-165">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="df5be-166">Transfert</span><span class="sxs-lookup"><span data-stu-id="df5be-166">Transfer</span></span></td>
<td><span data-ttu-id="df5be-167">Terminé</span><span class="sxs-lookup"><span data-stu-id="df5be-167">Completed</span></span></td>
<td><span data-ttu-id="df5be-168">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-168">No</span></span></td>
<td><span data-ttu-id="df5be-169">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-169">No</span></span></td>
<td><span data-ttu-id="df5be-170">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-170">No</span></span></td>
<td><span data-ttu-id="df5be-171">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-171">No</span></span></td>
<td><span data-ttu-id="df5be-172">Oui</span><span class="sxs-lookup"><span data-stu-id="df5be-172">Yes</span></span></td>
<td><span data-ttu-id="df5be-173">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="df5be-174">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="df5be-174">Transfer or process</span></span></td>
<td><span data-ttu-id="df5be-175">Vide</span><span class="sxs-lookup"><span data-stu-id="df5be-175">Empty</span></span></td>
<td><span data-ttu-id="df5be-176">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-176">No</span></span></td>
<td><span data-ttu-id="df5be-177">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-177">No</span></span></td>
<td><span data-ttu-id="df5be-178">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-178">No</span></span></td>
<td><span data-ttu-id="df5be-179">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-179">No</span></span></td>
<td><span data-ttu-id="df5be-180">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-180">No</span></span></td>
<td><span data-ttu-id="df5be-181">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="df5be-182">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="df5be-182">Transfer or process</span></span></td>
<td><span data-ttu-id="df5be-183">Carte kanban introuvable</span><span class="sxs-lookup"><span data-stu-id="df5be-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="df5be-184">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-184">No</span></span></td>
<td><span data-ttu-id="df5be-185">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-185">No</span></span></td>
<td><span data-ttu-id="df5be-186">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-186">No</span></span></td>
<td><span data-ttu-id="df5be-187">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-187">No</span></span></td>
<td><span data-ttu-id="df5be-188">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-188">No</span></span></td>
<td><span data-ttu-id="df5be-189">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="df5be-190">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="df5be-190">Transfer or process</span></span></td>
<td><span data-ttu-id="df5be-191">Une carte kanban est détectée, mais elle n'est pas affectée à un kanban</span><span class="sxs-lookup"><span data-stu-id="df5be-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="df5be-192">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-192">No</span></span></td>
<td><span data-ttu-id="df5be-193">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-193">No</span></span></td>
<td><span data-ttu-id="df5be-194">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-194">No</span></span></td>
<td><span data-ttu-id="df5be-195">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-195">No</span></span></td>
<td><span data-ttu-id="df5be-196">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-196">No</span></span></td>
<td><span data-ttu-id="df5be-197">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="df5be-198">Traiter</span><span class="sxs-lookup"><span data-stu-id="df5be-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="df5be-199">Non planifié</span><span class="sxs-lookup"><span data-stu-id="df5be-199">Not planned</span></span></li>
<li><span data-ttu-id="df5be-200">Préparé</span><span class="sxs-lookup"><span data-stu-id="df5be-200">Prepared</span></span></li>
<li><span data-ttu-id="df5be-201">En cours</span><span class="sxs-lookup"><span data-stu-id="df5be-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="df5be-202">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-202">No</span></span></td>
<td><span data-ttu-id="df5be-203">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-203">No</span></span></td>
<td><span data-ttu-id="df5be-204">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-204">No</span></span></td>
<td><span data-ttu-id="df5be-205">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-205">No</span></span></td>
<td><span data-ttu-id="df5be-206">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-206">No</span></span></td>
<td><span data-ttu-id="df5be-207">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="df5be-208">Traiter</span><span class="sxs-lookup"><span data-stu-id="df5be-208">Process</span></span></td>
<td><span data-ttu-id="df5be-209">Terminé</span><span class="sxs-lookup"><span data-stu-id="df5be-209">Completed</span></span></td>
<td><span data-ttu-id="df5be-210">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-210">No</span></span></td>
<td><span data-ttu-id="df5be-211">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-211">No</span></span></td>
<td><span data-ttu-id="df5be-212">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-212">No</span></span></td>
<td><span data-ttu-id="df5be-213">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-213">No</span></span></td>
<td><span data-ttu-id="df5be-214">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-214">No</span></span></td>
<td><span data-ttu-id="df5be-215">Non</span><span class="sxs-lookup"><span data-stu-id="df5be-215">No</span></span></td>
</tr>
</tbody>
</table>






