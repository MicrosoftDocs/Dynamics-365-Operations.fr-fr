---
title: Prise en charge du tableau de transfert kanban pour les scanneurs de codes-barres
description: La tableau de transfert kanban prend en charge l'entrée de scanneur à partir d'un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "319452"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="62d4f-103">Prise en charge du tableau de transfert kanban pour les scanneurs de codes-barres</span><span class="sxs-lookup"><span data-stu-id="62d4f-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62d4f-104">La tableau de transfert kanban prend en charge l'entrée de scanneur à partir d'un lecteur de codes-barres de widget pour Sélectionner, Démarrer, Terminer et Vider une tâche de kanban.</span><span class="sxs-lookup"><span data-stu-id="62d4f-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="62d4f-105">Modes d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="62d4f-105">Registration modes</span></span>
------------------

<span data-ttu-id="62d4f-106">Dans l'organisateur **Enregistrement du scanneur**, vous pouvez sélectionner le mode d'enregistrement, qui contrôle l'action lorsque vous numérisez un numéro de carte kanban ou entrez manuellement le numéro dans le champ Numéro de carte kanban.</span><span class="sxs-lookup"><span data-stu-id="62d4f-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="62d4f-107">Définir le mode d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="62d4f-107">Set registration mode</span></span> | <span data-ttu-id="62d4f-108">Description</span><span class="sxs-lookup"><span data-stu-id="62d4f-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="62d4f-109">Commencer</span><span class="sxs-lookup"><span data-stu-id="62d4f-109">Start</span></span>                 | <span data-ttu-id="62d4f-110">Enregistre une opération de transfert de kanban avec le statut « En cours ».</span><span class="sxs-lookup"><span data-stu-id="62d4f-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="62d4f-111">Terminée</span><span class="sxs-lookup"><span data-stu-id="62d4f-111">Complete</span></span>              | <span data-ttu-id="62d4f-112">Enregistre une opération de transfert de kanban avec le statut « Terminé ».</span><span class="sxs-lookup"><span data-stu-id="62d4f-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="62d4f-113">Vide</span><span class="sxs-lookup"><span data-stu-id="62d4f-113">Empty</span></span>                 | <span data-ttu-id="62d4f-114">Enregistre l'unité de manutention du matériel référencée par une carte kanban avec le statut « Vide ».</span><span class="sxs-lookup"><span data-stu-id="62d4f-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="62d4f-115">Sélectionner</span><span class="sxs-lookup"><span data-stu-id="62d4f-115">Select</span></span>                | <span data-ttu-id="62d4f-116">Enregistre un numéro de carte kanban et sélectionne automatiquement l'opération référencée dans la liste du kanban.</span><span class="sxs-lookup"><span data-stu-id="62d4f-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="62d4f-117">Sélection du mode d'enregistrement</span><span class="sxs-lookup"><span data-stu-id="62d4f-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="62d4f-118">Lorsque vous utilisez un lecteur de codes-barres pour sélectionner une tâche, le mode d'affichage du tableau kanban change.</span><span class="sxs-lookup"><span data-stu-id="62d4f-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="62d4f-119"> Dans ce mode, les conditions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="62d4f-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="62d4f-120">Seule la tâche de kanban numérisée s'affiche.</span><span class="sxs-lookup"><span data-stu-id="62d4f-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="62d4f-121">Les détails de la tâche sélectionnée s'affichent dans l'organisateur **Détails**.</span><span class="sxs-lookup"><span data-stu-id="62d4f-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="62d4f-122">L'organisateur **Messages** affiche les messages uniquement pour la tâche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="62d4f-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="62d4f-123">Vous pouvez modifier le statut de la tâche à l'aide des fonctions disponibles dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="62d4f-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="62d4f-124">Le tableau de transfert kanban continue à n'afficher qu'une seule tâche pendant ce temps.</span><span class="sxs-lookup"><span data-stu-id="62d4f-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="62d4f-125">Vous pouvez mettre à jour les informations de la liste de tâches manuellement en cliquant sur **Actualiser** (Maj+F5) dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="62d4f-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="62d4f-126">Après avoir actualisé les informations, les résultats complets pour le filtre de tâches s'affichent à nouveau.</span><span class="sxs-lookup"><span data-stu-id="62d4f-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="62d4f-127">Statut de tâche et actions possibles</span><span class="sxs-lookup"><span data-stu-id="62d4f-127">Job status and possible actions</span></span>
<span data-ttu-id="62d4f-128">Le statut de la tâche sélectionnée et le statut de toute tâche liée aux kanbans d'événement déterminent si vous pouvez poursuivre le traitement de la tâche.</span><span class="sxs-lookup"><span data-stu-id="62d4f-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="62d4f-129">Le tableau suivant affiche des informations sur ces statuts et tâches :</span><span class="sxs-lookup"><span data-stu-id="62d4f-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="62d4f-130">Statuts disponibles pour les tâches ou pour les unités de manutention référencées par les tâches.</span><span class="sxs-lookup"><span data-stu-id="62d4f-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="62d4f-131">Chaque tâche que vous pouvez exécuter pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="62d4f-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="62d4f-132">Type de tâche</span><span class="sxs-lookup"><span data-stu-id="62d4f-132">Job type</span></span></th>
<th><span data-ttu-id="62d4f-133">Statut de la tâche ou statut de l'unité de manutention</span><span class="sxs-lookup"><span data-stu-id="62d4f-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="62d4f-134">Mettre à jour les prélèvements</span><span class="sxs-lookup"><span data-stu-id="62d4f-134">Update picking list</span></span></th>
<th><span data-ttu-id="62d4f-135">Commencer</span><span class="sxs-lookup"><span data-stu-id="62d4f-135">Start</span></span></th>
<th><span data-ttu-id="62d4f-136">Mettre à jour l'enregistrement</span><span class="sxs-lookup"><span data-stu-id="62d4f-136">Update registration</span></span></th>
<th><span data-ttu-id="62d4f-137">Terminée</span><span class="sxs-lookup"><span data-stu-id="62d4f-137">Complete</span></span></th>
<th><span data-ttu-id="62d4f-138">Vide</span><span class="sxs-lookup"><span data-stu-id="62d4f-138">Empty</span></span></th>
<th><span data-ttu-id="62d4f-139">Créer des kanbans d'événement</span><span class="sxs-lookup"><span data-stu-id="62d4f-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="62d4f-140">Transfert</span><span class="sxs-lookup"><span data-stu-id="62d4f-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="62d4f-141">Non planifié</span><span class="sxs-lookup"><span data-stu-id="62d4f-141">Not planned</span></span></li>
<li><span data-ttu-id="62d4f-142">Aucune tâche liée, ou les tâches liées sont terminées</span><span class="sxs-lookup"><span data-stu-id="62d4f-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="62d4f-143">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-143">Yes</span></span></td>
<td><span data-ttu-id="62d4f-144">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-144">Yes</span></span></td>
<td><span data-ttu-id="62d4f-145">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-145">Yes</span></span></td>
<td><span data-ttu-id="62d4f-146">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-146">Yes</span></span></td>
<td><span data-ttu-id="62d4f-147">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-147">No</span></span></td>
<td><span data-ttu-id="62d4f-148">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="62d4f-149">Transfert</span><span class="sxs-lookup"><span data-stu-id="62d4f-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="62d4f-150">Non planifié</span><span class="sxs-lookup"><span data-stu-id="62d4f-150">Not planned</span></span></li>
<li><span data-ttu-id="62d4f-151">La tâche liée n'est pas terminée</span><span class="sxs-lookup"><span data-stu-id="62d4f-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="62d4f-152">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-152">Yes</span></span></td>
<td><span data-ttu-id="62d4f-153">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-153">No</span></span></td>
<td><span data-ttu-id="62d4f-154">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-154">Yes</span></span></td>
<td><span data-ttu-id="62d4f-155">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-155">No</span></span></td>
<td><span data-ttu-id="62d4f-156">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-156">No</span></span></td>
<td><span data-ttu-id="62d4f-157">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="62d4f-158">Transfert</span><span class="sxs-lookup"><span data-stu-id="62d4f-158">Transfer</span></span></td>
<td><span data-ttu-id="62d4f-159">En cours</span><span class="sxs-lookup"><span data-stu-id="62d4f-159">In progress</span></span></td>
<td><span data-ttu-id="62d4f-160">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-160">Yes</span></span></td>
<td><span data-ttu-id="62d4f-161">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-161">No</span></span></td>
<td><span data-ttu-id="62d4f-162">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-162">Yes</span></span></td>
<td><span data-ttu-id="62d4f-163">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-163">Yes</span></span></td>
<td><span data-ttu-id="62d4f-164">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-164">No</span></span></td>
<td><span data-ttu-id="62d4f-165">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="62d4f-166">Transfert</span><span class="sxs-lookup"><span data-stu-id="62d4f-166">Transfer</span></span></td>
<td><span data-ttu-id="62d4f-167">Terminé</span><span class="sxs-lookup"><span data-stu-id="62d4f-167">Completed</span></span></td>
<td><span data-ttu-id="62d4f-168">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-168">No</span></span></td>
<td><span data-ttu-id="62d4f-169">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-169">No</span></span></td>
<td><span data-ttu-id="62d4f-170">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-170">No</span></span></td>
<td><span data-ttu-id="62d4f-171">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-171">No</span></span></td>
<td><span data-ttu-id="62d4f-172">Oui</span><span class="sxs-lookup"><span data-stu-id="62d4f-172">Yes</span></span></td>
<td><span data-ttu-id="62d4f-173">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="62d4f-174">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="62d4f-174">Transfer or process</span></span></td>
<td><span data-ttu-id="62d4f-175">Vide</span><span class="sxs-lookup"><span data-stu-id="62d4f-175">Empty</span></span></td>
<td><span data-ttu-id="62d4f-176">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-176">No</span></span></td>
<td><span data-ttu-id="62d4f-177">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-177">No</span></span></td>
<td><span data-ttu-id="62d4f-178">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-178">No</span></span></td>
<td><span data-ttu-id="62d4f-179">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-179">No</span></span></td>
<td><span data-ttu-id="62d4f-180">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-180">No</span></span></td>
<td><span data-ttu-id="62d4f-181">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="62d4f-182">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="62d4f-182">Transfer or process</span></span></td>
<td><span data-ttu-id="62d4f-183">Carte kanban introuvable</span><span class="sxs-lookup"><span data-stu-id="62d4f-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="62d4f-184">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-184">No</span></span></td>
<td><span data-ttu-id="62d4f-185">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-185">No</span></span></td>
<td><span data-ttu-id="62d4f-186">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-186">No</span></span></td>
<td><span data-ttu-id="62d4f-187">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-187">No</span></span></td>
<td><span data-ttu-id="62d4f-188">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-188">No</span></span></td>
<td><span data-ttu-id="62d4f-189">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="62d4f-190">Transfert ou processus</span><span class="sxs-lookup"><span data-stu-id="62d4f-190">Transfer or process</span></span></td>
<td><span data-ttu-id="62d4f-191">Une carte kanban est détectée, mais elle n'est pas affectée à un kanban</span><span class="sxs-lookup"><span data-stu-id="62d4f-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="62d4f-192">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-192">No</span></span></td>
<td><span data-ttu-id="62d4f-193">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-193">No</span></span></td>
<td><span data-ttu-id="62d4f-194">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-194">No</span></span></td>
<td><span data-ttu-id="62d4f-195">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-195">No</span></span></td>
<td><span data-ttu-id="62d4f-196">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-196">No</span></span></td>
<td><span data-ttu-id="62d4f-197">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="62d4f-198">Traiter</span><span class="sxs-lookup"><span data-stu-id="62d4f-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="62d4f-199">Non planifié</span><span class="sxs-lookup"><span data-stu-id="62d4f-199">Not planned</span></span></li>
<li><span data-ttu-id="62d4f-200">Préparé</span><span class="sxs-lookup"><span data-stu-id="62d4f-200">Prepared</span></span></li>
<li><span data-ttu-id="62d4f-201">En cours</span><span class="sxs-lookup"><span data-stu-id="62d4f-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="62d4f-202">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-202">No</span></span></td>
<td><span data-ttu-id="62d4f-203">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-203">No</span></span></td>
<td><span data-ttu-id="62d4f-204">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-204">No</span></span></td>
<td><span data-ttu-id="62d4f-205">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-205">No</span></span></td>
<td><span data-ttu-id="62d4f-206">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-206">No</span></span></td>
<td><span data-ttu-id="62d4f-207">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="62d4f-208">Traiter</span><span class="sxs-lookup"><span data-stu-id="62d4f-208">Process</span></span></td>
<td><span data-ttu-id="62d4f-209">Terminé</span><span class="sxs-lookup"><span data-stu-id="62d4f-209">Completed</span></span></td>
<td><span data-ttu-id="62d4f-210">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-210">No</span></span></td>
<td><span data-ttu-id="62d4f-211">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-211">No</span></span></td>
<td><span data-ttu-id="62d4f-212">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-212">No</span></span></td>
<td><span data-ttu-id="62d4f-213">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-213">No</span></span></td>
<td><span data-ttu-id="62d4f-214">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-214">No</span></span></td>
<td><span data-ttu-id="62d4f-215">Non</span><span class="sxs-lookup"><span data-stu-id="62d4f-215">No</span></span></td>
</tr>
</tbody>
</table>





