---
title: Distribuer et planifier des questionnaires
description: "Cette rubrique décrit comment distribuer les questionnaires que vous créez pour qu'ils soient à la disposition de la personne ou du groupe de personnes qui les complèteront."
author: kherr75
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: eafcb047117eab73fddbd93c4c1d0aafb0023ebd
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="92102-103">Distribuer et planifier des questionnaires</span><span class="sxs-lookup"><span data-stu-id="92102-103">Distribute and schedule questionnaires</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="92102-104">Cette rubrique décrit comment distribuer les questionnaires que vous créez pour qu'ils soient à la disposition de la personne ou du groupe de personnes qui les complèteront.</span><span class="sxs-lookup"><span data-stu-id="92102-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="92102-105">Il existe plusieurs méthodes pour distribuer un questionnaire :</span><span class="sxs-lookup"><span data-stu-id="92102-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="92102-106">Marquer le questionnaire comme actif.</span><span class="sxs-lookup"><span data-stu-id="92102-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="92102-107">Le questionnaire est alors mis à la disposition de tous les employés, sauf si son accès est restreint par un groupe de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="92102-108">Affecter des droits à un groupe de questionnaires.</span><span class="sxs-lookup"><span data-stu-id="92102-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="92102-109">Le questionnaire est alors à la disposition de tous les membres du groupe sélectionné.</span><span class="sxs-lookup"><span data-stu-id="92102-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="92102-110">Créer des sessions de réponse prévues.</span><span class="sxs-lookup"><span data-stu-id="92102-110">Create planned answer sessions.</span></span> <span data-ttu-id="92102-111">Le questionnaire est alors accessible à une seule personne.</span><span class="sxs-lookup"><span data-stu-id="92102-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="92102-112">Créer un programme.</span><span class="sxs-lookup"><span data-stu-id="92102-112">Create a schedule.</span></span> <span data-ttu-id="92102-113">Le questionnaire peut alors être accessibles à plusieurs personnes.</span><span class="sxs-lookup"><span data-stu-id="92102-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="92102-114">Marquer un questionnaire comme actif</span><span class="sxs-lookup"><span data-stu-id="92102-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="92102-115">En définissant le champ **Actif** sur **Oui** dans la page **Questionnaires**, le questionnaire est mis à disposition de tous les employés pour qu'ils le remplissent.</span><span class="sxs-lookup"><span data-stu-id="92102-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="92102-116">Les personnes interrogées peuvent remplir le questionnaire à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="92102-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="92102-117">Cette fonctionnalité est utile si vous souhaitez collecter des commentaires continuels au cours de l'année.</span><span class="sxs-lookup"><span data-stu-id="92102-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="92102-118">Par exemple, vous pouvez confectionner un questionnaire pour que les employés donnent leurs commentaires sur le service de déjeuner de la cafétéria.</span><span class="sxs-lookup"><span data-stu-id="92102-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="92102-119">Groupes de questionnaires</span><span class="sxs-lookup"><span data-stu-id="92102-119">Questionnaire groups</span></span>
<span data-ttu-id="92102-120">Vous pouvez paramétrer des groupes de questionnaires puis y inclure les personnes interrogées auxquelles un questionnaire doit être distribué.</span><span class="sxs-lookup"><span data-stu-id="92102-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="92102-121">Vous pouvez créer des groupes de questionnaires dans les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="92102-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="92102-122">**Groupes de questionnaire**– Seules les personnes d'un groupe de questionnaires peuvent remplir un questionnaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="92102-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="92102-123">Par exemple, si le public visé est constitué de fournisseurs, vous pouvez créer un groupe de questionnaires spécifiques à ces personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="92102-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="92102-124">**Membres du groupe de questionnaire** – Vous pouvez ajouter des personnes aux groupes de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="92102-125">Pour affecter un groupe de questionnaires à un questionnaire, dans la page **Questionnaires**, cliquez sur **Droits de l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="92102-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="92102-126">Une fois que le questionnaire est enregistré comme actif, les membres du groupe de questionnaires peuvent remplir le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="92102-127">Cette fonctionnalité est utile si vous souhaitez tester un questionnaire sur une sélection de personnes avant de distribuer à un plus grand groupe, ou si vous souhaitez cibler un questionnaire sur une audience très spécifique.</span><span class="sxs-lookup"><span data-stu-id="92102-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="92102-128">Sessions de réponse prévues dans un questionnaire</span><span class="sxs-lookup"><span data-stu-id="92102-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="92102-129">Les sessions de réponse prévues sont des questionnaires que vous avez créés et pour lequel vous avez sélectionné les personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="92102-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="92102-130">**Remarque :** avant de paramétrer des sessions de réponse prévues, vous devez créer un questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="92102-131">Dans la page **Session de réponse prévue**, vous pouvez créer une session de réponse prévue pour un employé individuel.</span><span class="sxs-lookup"><span data-stu-id="92102-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="92102-132">La liste de la page affiche tous les questionnaires planifiés.</span><span class="sxs-lookup"><span data-stu-id="92102-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="92102-133">Les sessions de réponse planifiées sont également utilisées dans la page **Programmes de questionnaire**, où vous pouvez planifier des questionnaires pour plusieurs personnes :</span><span class="sxs-lookup"><span data-stu-id="92102-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="92102-134">Employés</span><span class="sxs-lookup"><span data-stu-id="92102-134">Employees</span></span>
-   <span data-ttu-id="92102-135">Participants du cours</span><span class="sxs-lookup"><span data-stu-id="92102-135">Course participants</span></span>
-   <span data-ttu-id="92102-136">Unités organisationnelles</span><span class="sxs-lookup"><span data-stu-id="92102-136">Organizational units</span></span>

<span data-ttu-id="92102-137">Chaque personne peut répondre au questionnaire une seule fois.</span><span class="sxs-lookup"><span data-stu-id="92102-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="92102-138">Programmer un questionnaire</span><span class="sxs-lookup"><span data-stu-id="92102-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="92102-139">De manière facultative, vous pouvez planifier un questionnaire pour plusieurs personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="92102-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="92102-140">Types de planification</span><span class="sxs-lookup"><span data-stu-id="92102-140">Planning types</span></span>

<span data-ttu-id="92102-141">Les types de planification sont nécessaires si vous souhaitez programmer des sessions de réponse prévues pour plusieurs personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="92102-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="92102-142">Les types de planification permettent de classer les programmes de questionnaires.</span><span class="sxs-lookup"><span data-stu-id="92102-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="92102-143">Par exemple, vous pouvez planifier des questionnaires aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="92102-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="92102-144">Évaluation</span><span class="sxs-lookup"><span data-stu-id="92102-144">Evaluation</span></span>
-   <span data-ttu-id="92102-145">Étude</span><span class="sxs-lookup"><span data-stu-id="92102-145">Survey</span></span>
-   <span data-ttu-id="92102-146">Test</span><span class="sxs-lookup"><span data-stu-id="92102-146">Testing</span></span>

<span data-ttu-id="92102-147">Vous pouvez spécifier les types de planification pour un programme de questionnaires dans la page **Programmes de questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="92102-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="92102-148">Types de référence pour le questionnaire</span><span class="sxs-lookup"><span data-stu-id="92102-148">Reference types for questionnaire</span></span>

<span data-ttu-id="92102-149">Les types de référence aident à entrer les critères de sélection des personnes interrogées lorsque vous planifiez un questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="92102-150">Utilisez la page **Types de référence** pour paramétrer les types de référence pour un questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="92102-151">Chaque type de référence correspond à une table dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="92102-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="92102-152">Lorsque vous créez des programmes de questionnaires, vous pouvez spécifier des enregistrements individuels dans la table ou une plage d'enregistrements qui seront associés au questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="92102-153">Par exemple, si vous sélectionnez la table Cours, vous pouvez décider à quel cours spécifique le questionnaire se rapporte.</span><span class="sxs-lookup"><span data-stu-id="92102-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="92102-154">Lorsque vous paramétrez un type de référence pour la table Cours, certains champs et boutons de la page **Cours** deviennent disponibles.</span><span class="sxs-lookup"><span data-stu-id="92102-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="92102-155">Programmes de questionnaire</span><span class="sxs-lookup"><span data-stu-id="92102-155">Questionnaire schedules</span></span>

<span data-ttu-id="92102-156">Vous pouvez utiliser des programmes de questionnaire pour générer plusieurs sessions de réponse prévues pour un groupe d'utilisateurs, selon le type de référence.</span><span class="sxs-lookup"><span data-stu-id="92102-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="92102-157">Créez un programme dans la page **Programmes de questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="92102-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="92102-158">Sélectionnez le type d'organisation pour classer le programme, et pour sélectionner le type de référence qui doit être utilisé pour interroger le système pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="92102-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="92102-159">Par exemple, si vous définissez le type de référence sur la table Cours, vous pouvez sélectionner un cours spécifique dans le champ **Référence**.</span><span class="sxs-lookup"><span data-stu-id="92102-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="92102-160">Cliquez sur **Détails de la configuration** pour sélectionner le questionnaire et d'autres critères.</span><span class="sxs-lookup"><span data-stu-id="92102-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="92102-161">Par exemple, spécifiez le nom de l'instructeur comme critère si le questionnaire est une évaluation de l'instructeur.</span><span class="sxs-lookup"><span data-stu-id="92102-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="92102-162">Après avoir terminé d'entrer les détails de configuration, le système génère des sessions de réponse prévues pour les utilisateurs qui sont inclus dans la requête.</span><span class="sxs-lookup"><span data-stu-id="92102-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="92102-163">Cliquez sur **Sessions de réponse prévues** pour afficher les sessions de réponse pour le programme.</span><span class="sxs-lookup"><span data-stu-id="92102-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="92102-164">Vous pouvez ensuite créer manuellement des sessions de réponse prévues supplémentaires ou supprimer des sessions de réponse prévues qui n'ont pas reçu de réponse.</span><span class="sxs-lookup"><span data-stu-id="92102-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="92102-165">Cliquez sur **Fonctions** &gt; **Démarrer** pour que le questionnaire soit disponible aux utilisateurs des sessions de réponse prévues associées.</span><span class="sxs-lookup"><span data-stu-id="92102-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="92102-166">Cliquez sur **Réponses** pour afficher les réponses apportées au questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="92102-167">Vous pouvez également copier les paramètres de planification des questionnaires, les sessions de réponse prévues, et les réponses à un nouveau programme de questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="92102-168">Notifier les personnes interrogées sur les questionnaires à leur disposition</span><span class="sxs-lookup"><span data-stu-id="92102-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="92102-169">Lorsque vous distribuez un questionnaire, vous devez informer les personnes interrogées que des questionnaires sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="92102-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="92102-170">Notifier les personnes interrogées d'une session de réponse prévue</span><span class="sxs-lookup"><span data-stu-id="92102-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="92102-171">Si vous utilisez une session de réponse prévue, vous devez informer la personne directement, par téléphone ou par e-mail.</span><span class="sxs-lookup"><span data-stu-id="92102-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="92102-172">Notifier les personnes interrogées d'un programme</span><span class="sxs-lookup"><span data-stu-id="92102-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="92102-173">Utilisez la page **Programmes de questionnaire** pour préparer et envoyer un e-mail à toutes les personnes interrogées affectées au questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="92102-174">Entrez le texte de l'e-mail sous l'onglet **E-mail pour le libre-service pour employés**. Une fois le programme démarré, cliquez sur **Fonctions** &gt; **Envoyer un e-mail** pour générer et envoyer un e-mail aux personnes interrogées.</span><span class="sxs-lookup"><span data-stu-id="92102-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="92102-175">Les personnes interrogées peuvent alors se connecter au site Web et remplir le questionnaire.</span><span class="sxs-lookup"><span data-stu-id="92102-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="92102-176">**Remarque :** avant d'utiliser la fonctionnalité d'e-mail, votre administrateur informatique doit entrer les paramètres d'e-mail dans la page **Paramètres d'e-mail**.</span><span class="sxs-lookup"><span data-stu-id="92102-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="92102-177">Terminer un questionnaire planifié</span><span class="sxs-lookup"><span data-stu-id="92102-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="92102-178">Vous pouvez mettre fin à un questionnaire planifié une fois que toutes les personnes interrogées ont répondu aux sessions de réponses qui leur étaient attribuées.</span><span class="sxs-lookup"><span data-stu-id="92102-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="92102-179">Une fois qu'un questionnaire planifié est terminé, vous ne pouvez pas copier ses paramètres dans un nouveau programme.</span><span class="sxs-lookup"><span data-stu-id="92102-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="92102-180">**Remarque :** si une ou plusieurs personnes interrogées n'ont pas complété le questionnaire mais que vous souhaitez mettre fin au programme, vous devez commencez par supprimer ces personnes interrogées appropriées de la liste dans la page **Session de réponse prévue**.</span><span class="sxs-lookup"><span data-stu-id="92102-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="92102-181">Vous pouvez ensuite mettre fin au programme.</span><span class="sxs-lookup"><span data-stu-id="92102-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="92102-182">Remplissage de questionnaires</span><span class="sxs-lookup"><span data-stu-id="92102-182">Completing questionnaires</span></span>
<span data-ttu-id="92102-183">Une fois le questionnaire conçu et distribué, il peut être rempli par les personnes interrogées sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="92102-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="92102-184">Vous pouvez remplir les questionnaires disponibles à partir de deux emplacements :</span><span class="sxs-lookup"><span data-stu-id="92102-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="92102-185">Dans le volet de navigation, cliquez sur **Questionnaires** &gt; **Distribuer** &gt; **Remplir un questionnaire**.</span><span class="sxs-lookup"><span data-stu-id="92102-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="92102-186">Dans le libre service employé, cliquez sur **Questionnaires à remplir**.</span><span class="sxs-lookup"><span data-stu-id="92102-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="92102-187">Les questionnaires peuvent être accessibles à des utilisateurs ou groupes d'utilisateurs spécifiques, ou à tous les utilisateurs d'un réseau.</span><span class="sxs-lookup"><span data-stu-id="92102-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="additional-resources"></a><span data-ttu-id="92102-188">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="92102-188">Additional resources</span></span>
--------

[<span data-ttu-id="92102-189">Conception de questionnaires</span><span class="sxs-lookup"><span data-stu-id="92102-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="92102-190">Utilisation de questionnaires</span><span class="sxs-lookup"><span data-stu-id="92102-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="92102-191">Affichage et évaluation des résultats des questionnaire</span><span class="sxs-lookup"><span data-stu-id="92102-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)



