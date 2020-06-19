---
title: Paramétrer les cours de formation
description: Les administrateurs des ressources humaines et les responsables peuvent utiliser les fonctionnalités du cours pour tenir à jour des informations sur la formation qui est offerte aux employés.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 253f0d07679b6327a0ed1e3cc20ede66249750b8
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429334"
---
# <a name="set-up-training-courses"></a><span data-ttu-id="231f6-103">Paramétrer les cours de formation</span><span class="sxs-lookup"><span data-stu-id="231f6-103">Set up training courses</span></span>

<span data-ttu-id="231f6-104">Les administrateurs des ressources humaines et les responsables peuvent utiliser les fonctionnalités du cours pour tenir à jour des informations sur la formation qui est offerte aux employés.</span><span class="sxs-lookup"><span data-stu-id="231f6-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="231f6-105">Paramétrage des conditions préalables</span><span class="sxs-lookup"><span data-stu-id="231f6-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="231f6-106">Les informations suivantes sont requises et doivent être définies avant de créer des cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="231f6-107">**Types de cours**</span><span class="sxs-lookup"><span data-stu-id="231f6-107">**Course types**</span></span>

<span data-ttu-id="231f6-108">Les informations suivantes sont des informations facultatives que vous pouvez spécifier pour les cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="231f6-109">Si vous savez que vous allez entrer ces informations pour les cours, vous devez paramétrer ces informations avant de créer des enregistrements de cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="231f6-110">**Groupes de classes**</span><span class="sxs-lookup"><span data-stu-id="231f6-110">**Classroom groups**</span></span>
-   <span data-ttu-id="231f6-111">**Groupes de cours**</span><span class="sxs-lookup"><span data-stu-id="231f6-111">**Course groups**</span></span>
-   <span data-ttu-id="231f6-112">**Lieux de cours**</span><span class="sxs-lookup"><span data-stu-id="231f6-112">**Course locations**</span></span>
-   <span data-ttu-id="231f6-113">**Classes**</span><span class="sxs-lookup"><span data-stu-id="231f6-113">**Classrooms**</span></span>
-   <span data-ttu-id="231f6-114">**Instructeurs**</span><span class="sxs-lookup"><span data-stu-id="231f6-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="231f6-115">Types de cours</span><span class="sxs-lookup"><span data-stu-id="231f6-115">Course types</span></span>
<span data-ttu-id="231f6-116">Ceux-ci servent à classer les cours en fonction de leur structure ou de leur contenu.</span><span class="sxs-lookup"><span data-stu-id="231f6-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="231f6-117">Vous pouvez créer des types de cours dans la page **Types de cours**.</span><span class="sxs-lookup"><span data-stu-id="231f6-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="231f6-118">Vous devez sélectionner un type de cours lorsque vous créez un enregistrement de cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="231f6-119">Type de paramétrage de cours</span><span class="sxs-lookup"><span data-stu-id="231f6-119">Course setup type</span></span>
<span data-ttu-id="231f6-120">Le tableau suivant répertorie les trois types de paramétrage pour les cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="231f6-121">Les types de paramétrage déterminent la structure du cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="231f6-122">Type de paramétrage</span><span class="sxs-lookup"><span data-stu-id="231f6-122">Setup type</span></span></th>
<th><span data-ttu-id="231f6-123">Description</span><span class="sxs-lookup"><span data-stu-id="231f6-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="231f6-124"><strong>Standard</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="231f6-125">Sélectionnez ce type pour les cours qui n'ont pas un emploi du temps quotidien.</span><span class="sxs-lookup"><span data-stu-id="231f6-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="231f6-126">Il s'agit du type de paramétrage par défaut lors de la création d'un cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="231f6-127"><strong>Emploi du temps</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="231f6-128">Sélectionnez ce type pour organiser les détails de chaque journée de cours qui se déroule sur plusieurs jours.</span><span class="sxs-lookup"><span data-stu-id="231f6-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="231f6-129"><strong>Emploi du temps + session</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="231f6-130">Sélectionnez ce type pour les cours plus complexes.</span><span class="sxs-lookup"><span data-stu-id="231f6-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="231f6-131">Par exemple, vous pouvez diviser l'emploi du temps du cours en suivis et sessions.</span><span class="sxs-lookup"><span data-stu-id="231f6-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="231f6-132"><strong>Suivi</strong> : Les suivis sont les domaines d'intérêt spécifiques d'un cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="231f6-133"><strong>Sessions</strong> : Les sessions permettent de diviser les suivis et aident à identifier les processus ou les techniques spécifiques adaptés au suivi concerné.</span><span class="sxs-lookup"><span data-stu-id="231f6-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="231f6-134">Tâches de cours</span><span class="sxs-lookup"><span data-stu-id="231f6-134">Course tasks</span></span>
<span data-ttu-id="231f6-135">Pour chaque cours, vous pouvez effectuer les tâches suivantes.</span><span class="sxs-lookup"><span data-stu-id="231f6-135">For each course, you can complete the following tasks.</span></span>
- <span data-ttu-id="231f6-136">Enregistrer les participants</span><span class="sxs-lookup"><span data-stu-id="231f6-136">Register participants</span></span>
- <span data-ttu-id="231f6-137">Spécifier une date limite d'inscription</span><span class="sxs-lookup"><span data-stu-id="231f6-137">Specify a registration deadline</span></span>
- <span data-ttu-id="231f6-138">Définir le nombre minimal et le nombre maximal de participants</span><span class="sxs-lookup"><span data-stu-id="231f6-138">Define the minimum and maximum number of participants</span></span>
- <span data-ttu-id="231f6-139">Affecter un lieu de cours et une classe</span><span class="sxs-lookup"><span data-stu-id="231f6-139">Assign a course location and classroom</span></span>
- <span data-ttu-id="231f6-140">Recommander des hôtels aux participants</span><span class="sxs-lookup"><span data-stu-id="231f6-140">Recommend hotels to course participants</span></span>
- <span data-ttu-id="231f6-141">Créer une description du cours, que vous pouvez ensuite annoncer sur le libre-service pour employés</span><span class="sxs-lookup"><span data-stu-id="231f6-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="231f6-142">**Remarque** : vous pouvez supprimer un cours uniquement si personne n'y est inscrit.</span><span class="sxs-lookup"><span data-stu-id="231f6-142">**Note** You can delete a course only if no one has registered for it.</span></span> 

## <a name="course-statuses"></a><span data-ttu-id="231f6-143">Statuts de cours</span><span class="sxs-lookup"><span data-stu-id="231f6-143">Course statuses</span></span>
<span data-ttu-id="231f6-144">Le tableau suivant répertorie les statuts de cours possibles et les actions que vous pouvez effectuer lorsque le cours a un statut spécifique.</span><span class="sxs-lookup"><span data-stu-id="231f6-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="231f6-145">Statut</span><span class="sxs-lookup"><span data-stu-id="231f6-145">Status</span></span></th>
<th><span data-ttu-id="231f6-146">Actions</span><span class="sxs-lookup"><span data-stu-id="231f6-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="231f6-147"><strong>Créé</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="231f6-148">Permet d'entrer et de modifier les informations sur le cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="231f6-149">Permet d'attribuer le statut <strong>Ouvert</strong> au cours afin que les employés puissent s'inscrire.</span><span class="sxs-lookup"><span data-stu-id="231f6-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="231f6-150"><strong>Ouverte</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="231f6-151">Permet d'inscrire les participants au cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="231f6-152">Permet de supprimer des participants d'un cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="231f6-153">Permet de confirmer l'inscription des participants au cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="231f6-154">Remplacez le statut de cours par<strong> Clôturé</strong> ou <strong>Annulé</strong>.</span><span class="sxs-lookup"><span data-stu-id="231f6-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="231f6-155">Prévoyez des questionnaires pour les participants dont le statut est <strong>Confirmé</strong>.</span><span class="sxs-lookup"><span data-stu-id="231f6-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="231f6-156"><strong>Clôturé(e)</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="231f6-157">Vous pouvez rouvrir le cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="231f6-158"><strong>Annulé</strong></span><span class="sxs-lookup"><span data-stu-id="231f6-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="231f6-159">Vous pouvez rouvrir le cours.</span><span class="sxs-lookup"><span data-stu-id="231f6-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="231f6-160">Participants du cours</span><span class="sxs-lookup"><span data-stu-id="231f6-160">Course participants</span></span>
<span data-ttu-id="231f6-161">Les participants du cours sont des employés qui prennent part à un cours de formation ou un événement.</span><span class="sxs-lookup"><span data-stu-id="231f6-161">Course participants are workers who participate in a training course or event.</span></span> <span data-ttu-id="231f6-162">Vous pouvez inscrire des participants aux cours actifs.</span><span class="sxs-lookup"><span data-stu-id="231f6-162">You can only register participants for open courses.</span></span> <span data-ttu-id="231f6-163">Le nombre minimal et maximal de participants que vous pouvez inscrire à un cours est défini dans l'organisateur **General** de la page **Cours**.</span><span class="sxs-lookup"><span data-stu-id="231f6-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="231f6-164">Workflow</span><span class="sxs-lookup"><span data-stu-id="231f6-164">Workflow</span></span>
--------

<span data-ttu-id="231f6-165">Les employés qui s'inscrivent à un cours via la page **Libre service employé** peuvent faire suivre leur inscription via le workflow pour approbation.</span><span class="sxs-lookup"><span data-stu-id="231f6-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span> <span data-ttu-id="231f6-166">Vous pouvez affecter un workflow à un cours dans l'organisateur **Général** de la page **Cours**.</span><span class="sxs-lookup"><span data-stu-id="231f6-166">You can assign a workflow to a course on the **General** FastTab on the **Courses** page.</span></span>





