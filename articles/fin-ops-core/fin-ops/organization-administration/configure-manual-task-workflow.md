---
title: Configurer des tâches manuelles dans un workflow
description: Cette rubrique explique comment configurer les propriétés d’une tâche manuelle.
author: ChrisGarty
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f61e0f7ee16519767192fb379f20c1ed20b69caa
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798803"
---
# <a name="configure-manual-tasks-in-a-workflow"></a><span data-ttu-id="5eef7-103">Configurer des tâches manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="5eef7-103">Configure manual tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5eef7-104">Cette rubrique explique comment configurer les propriétés d’une tâche manuelle.</span><span class="sxs-lookup"><span data-stu-id="5eef7-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="5eef7-105">Pour configurer une tâche manuelle, dans l’éditeur de workflow, cliquez avec le bouton droit sur la tâche, puis cliquez sur **Propriétés** pour ouvrir l’écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="5eef7-106">Suivez ensuite les procédures suivantes pour configurer les propriétés de la tâche manuelle.</span><span class="sxs-lookup"><span data-stu-id="5eef7-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="5eef7-107">Saisie d’un nom pour la tâche</span><span class="sxs-lookup"><span data-stu-id="5eef7-107">Name the task</span></span>

<span data-ttu-id="5eef7-108">Procédez comme suit pour entrer un nom pour la tâche manuelle.</span><span class="sxs-lookup"><span data-stu-id="5eef7-108">Follow these steps to enter a name for the manual task.</span></span>

1. <span data-ttu-id="5eef7-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="5eef7-110">Entrez un nom unique pour la tâche dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="5eef7-111">Saisie d’une ligne d’objet et des instructions</span><span class="sxs-lookup"><span data-stu-id="5eef7-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="5eef7-112">Vous devez fournir une ligne d’objet et des instructions aux utilisateurs affectés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="5eef7-113">Par exemple, si vous configurez une tâche pour des demandes d’achat, l’utilisateur concerné par cette tâche voit la ligne d’objet et les instructions dans la page **Demandes d’achat**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="5eef7-114">La ligne d’objet figure dans une barre de message de la page.</span><span class="sxs-lookup"><span data-stu-id="5eef7-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="5eef7-115">L’utilisateur peut ensuite cliquer sur l’icône de la barre des messages pour afficher les instructions.</span><span class="sxs-lookup"><span data-stu-id="5eef7-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="5eef7-116">Procédez comme suit pour entrer une ligne d’objet et des instructions.</span><span class="sxs-lookup"><span data-stu-id="5eef7-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="5eef7-117">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="5eef7-118">Entrez la ligne d’objet dans le champ **Objet de l’article de travail**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="5eef7-119">Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="5eef7-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="5eef7-120">Ils sont remplacés par les données appropriées lorsque la ligne d’objet s’affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="5eef7-121">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="5eef7-122">Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="5eef7-123">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="5eef7-124">Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="5eef7-125">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="5eef7-125">Click **Insert**.</span></span>

4. <span data-ttu-id="5eef7-126">Suivez les étapes suivantes pour ajouter une traduction de la ligne d’objet.</span><span class="sxs-lookup"><span data-stu-id="5eef7-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="5eef7-127">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="5eef7-128">Dans la page qui s’affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="5eef7-129">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="5eef7-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="5eef7-130">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="5eef7-131">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="5eef7-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="5eef7-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-132">Click **Close**.</span></span>

5. <span data-ttu-id="5eef7-133">Entrez les instructions dans le champ **Instructions de l’élément de travail**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="5eef7-134">Pour personnaliser les instructions, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="5eef7-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="5eef7-135">Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="5eef7-136">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="5eef7-137">Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="5eef7-138">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="5eef7-139">Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="5eef7-140">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="5eef7-140">Click **Insert**.</span></span>

7. <span data-ttu-id="5eef7-141">Suivez les étapes suivantes pour ajouter une traduction des instructions.</span><span class="sxs-lookup"><span data-stu-id="5eef7-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="5eef7-142">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="5eef7-143">Dans la page qui s’affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="5eef7-144">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="5eef7-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="5eef7-145">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="5eef7-146">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="5eef7-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="5eef7-147">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="5eef7-148">Affectation de la tâche</span><span class="sxs-lookup"><span data-stu-id="5eef7-148">Assign the task</span></span>

<span data-ttu-id="5eef7-149">Procédez comme suit pour indiquer à qui affecter la tâche manuelle.</span><span class="sxs-lookup"><span data-stu-id="5eef7-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1. <span data-ttu-id="5eef7-150">Dans le volet gauche, cliquez sur **Affectation**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="5eef7-151">Sous l’onglet **Type d’affectation**, sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="5eef7-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="5eef7-152">Option</span><span class="sxs-lookup"><span data-stu-id="5eef7-152">Option</span></span></th>
    <th><span data-ttu-id="5eef7-153">Utilisateurs à qui la tâche est affectée</span><span class="sxs-lookup"><span data-stu-id="5eef7-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="5eef7-154">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5eef7-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="5eef7-155">Participant</span><span class="sxs-lookup"><span data-stu-id="5eef7-155">Participant</span></span></td>
    <td><span data-ttu-id="5eef7-156">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="5eef7-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-157">Après avoir sélectionné <strong>Participant</strong>, sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="5eef7-158">Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel affecter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-159">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="5eef7-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="5eef7-160">Utilisateurs d’une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="5eef7-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-161">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="5eef7-162">Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5eef7-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="5eef7-163">Ces noms représentent les utilisateurs à qui la tâche peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="5eef7-164">Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="5eef7-165">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="5eef7-166">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="5eef7-167">Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5eef7-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="5eef7-168">Sous l’onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter la tâche :</span><span class="sxs-lookup"><span data-stu-id="5eef7-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="5eef7-169"><strong>Affecter à tous les utilisateurs récupérés</strong> – La tâche est affectée à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="5eef7-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="5eef7-170"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La tâche est affectée uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="5eef7-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="5eef7-171"><strong>Exclure les utilisateurs à la condition suivante</strong> – La tâche n’est affectée à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="5eef7-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="5eef7-172">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="5eef7-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-173">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="5eef7-173">Workflow user</span></span></td>
    <td><span data-ttu-id="5eef7-174">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="5eef7-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="5eef7-175">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="5eef7-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-176">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="5eef7-176">User</span></span></td>
    <td><span data-ttu-id="5eef7-177">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="5eef7-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-178">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="5eef7-179">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-179">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="5eef7-180">Sélectionnez les utilisateurs à qui vous souhaitez affecter la tâche, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-181">File d’attente</span><span class="sxs-lookup"><span data-stu-id="5eef7-181">Queue</span></span></td>
    <td><span data-ttu-id="5eef7-182">File d’attente des éléments de travail</span><span class="sxs-lookup"><span data-stu-id="5eef7-182">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-183">Après avoir sélectionné <strong>File d’attente</strong>, cliquez sur l’onglet <strong>Basé sur la file d’attente</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="5eef7-184">Pour affecter la tâche à une file d’attente donnée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="5eef7-185">Dans la liste <strong>Type de file d’attente</strong>, sélectionnez <strong>Files d’attente des éléments de travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="5eef7-186">Sélectionnez la file d’attente dans la liste <strong>Nom de file d’attente</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="5eef7-187">Si une condition détermine la file d’attente à laquelle la tâche est affectée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="5eef7-188">Dans la liste <strong>Type de file d’attente</strong>, sélectionnez <strong>Files d’attente conditionnelles des éléments de travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="5eef7-189">Dans la liste <strong>Nom de file d’attente</strong>, sélectionnez <strong>File d’attente conditionnelle</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="5eef7-190">Cette option est utilisée uniquement pour certains workflows, tels que Gestion des dossiers.</span><span class="sxs-lookup"><span data-stu-id="5eef7-190">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="5eef7-191">Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour réaliser la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="5eef7-192">Permet de sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5eef7-192">Select one of the following options:</span></span>

    - <span data-ttu-id="5eef7-193">**Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="5eef7-194">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-195">**Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="5eef7-196">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-197">**Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="5eef7-198">**Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="5eef7-199">Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="5eef7-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="5eef7-200">**Années** – Permet de sélectionner le jour et le mois où l’utilisateur doit terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="5eef7-201">Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine de décembre.</span><span class="sxs-lookup"><span data-stu-id="5eef7-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="5eef7-202">Si l’utilisateur ne termine pas la tâche dans le délai imparti, la tâche est en retard.</span><span class="sxs-lookup"><span data-stu-id="5eef7-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="5eef7-203">Une tâche en retard peut être réaffectée, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.</span><span class="sxs-lookup"><span data-stu-id="5eef7-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="5eef7-204">Spécification des conséquences du retard de la tâche</span><span class="sxs-lookup"><span data-stu-id="5eef7-204">Specify what happens when the task is overdue</span></span>

<span data-ttu-id="5eef7-205">Si un utilisateur ne termine pas la tâche manuelle dans le délai imparti, la tâche est en retard.</span><span class="sxs-lookup"><span data-stu-id="5eef7-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="5eef7-206">Une tâche en retard peut être affectée à un échelon supérieur ou affectée automatiquement à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5eef7-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="5eef7-207">Procédez comme suit pour réaffecter la tâche en retard.</span><span class="sxs-lookup"><span data-stu-id="5eef7-207">Follow these steps to escalate the task if it's overdue.</span></span>

1. <span data-ttu-id="5eef7-208">Dans le volet gauche, cliquez sur **Escalade**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-208">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="5eef7-209">Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="5eef7-210">Le système affecte automatiquement la tâche aux utilisateurs répertoriés dans le chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="5eef7-211">Le tableau suivant présente un exemple de chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="5eef7-212">Séquence</span><span class="sxs-lookup"><span data-stu-id="5eef7-212">Sequence</span></span> | <span data-ttu-id="5eef7-213">Chemin de réaffectation</span><span class="sxs-lookup"><span data-stu-id="5eef7-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="5eef7-214">1</span><span class="sxs-lookup"><span data-stu-id="5eef7-214">1</span></span>        | <span data-ttu-id="5eef7-215">Affecter à : Donna</span><span class="sxs-lookup"><span data-stu-id="5eef7-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="5eef7-216">2</span><span class="sxs-lookup"><span data-stu-id="5eef7-216">2</span></span>        | <span data-ttu-id="5eef7-217">Affecter à : Erin</span><span class="sxs-lookup"><span data-stu-id="5eef7-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="5eef7-218">3</span><span class="sxs-lookup"><span data-stu-id="5eef7-218">3</span></span>        | <span data-ttu-id="5eef7-219">Action finale : Rejeter</span><span class="sxs-lookup"><span data-stu-id="5eef7-219">Final action: Reject</span></span> |

    <span data-ttu-id="5eef7-220">Dans cet exemple, le système affecte la tâche en retard à Donna.</span><span class="sxs-lookup"><span data-stu-id="5eef7-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="5eef7-221">Si celle-ci ne termine pas la tâche dans le délai imparti, le système affecte la tâche à Erin.</span><span class="sxs-lookup"><span data-stu-id="5eef7-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="5eef7-222">Si celle-ci ne termine pas la tâche dans le délai imparti, le système rejette le document qui était soumis pour traitement.</span><span class="sxs-lookup"><span data-stu-id="5eef7-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>

3. <span data-ttu-id="5eef7-223">Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="5eef7-224">Sous l’onglet **Type d’affectation**, sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="5eef7-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="5eef7-225">Option</span><span class="sxs-lookup"><span data-stu-id="5eef7-225">Option</span></span></th>
    <th><span data-ttu-id="5eef7-226">Utilisateurs à qui la tâche est affectée</span><span class="sxs-lookup"><span data-stu-id="5eef7-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="5eef7-227">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5eef7-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="5eef7-228">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="5eef7-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="5eef7-229">Utilisateurs d’une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="5eef7-229">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-230">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l’onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel réaffecter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="5eef7-231">Le système doit extraire un ensemble de noms d’utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5eef7-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="5eef7-232">Ces noms représentent les utilisateurs à qui la tâche peut être réaffectée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="5eef7-233">Pour indiquer le point de départ et le point final de l’ensemble de noms d’utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="5eef7-234">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="5eef7-235">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="5eef7-236">Entrez ensuite une condition pour indiquer où le système arrête l’extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5eef7-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="5eef7-237">Sous l’onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels réaffecter la tâche :</span><span class="sxs-lookup"><span data-stu-id="5eef7-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="5eef7-238"><strong>Affecter à tous les utilisateurs récupérés</strong> – La tâche est réaffectée à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="5eef7-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="5eef7-239"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La tâche est réaffectée uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="5eef7-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="5eef7-240"><strong>Exclure les utilisateurs à la condition suivante</strong> – La tâche n’est réaffectée à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="5eef7-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="5eef7-241">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="5eef7-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-242">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="5eef7-242">Workflow user</span></span></td>
    <td><span data-ttu-id="5eef7-243">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="5eef7-243">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="5eef7-244">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="5eef7-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-245">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="5eef7-245">User</span></span></td>
    <td><span data-ttu-id="5eef7-246">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="5eef7-246">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-247">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="5eef7-248">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-248">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="5eef7-249">Sélectionnez les utilisateurs à qui vous souhaitez réaffecter la tâche, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="5eef7-250">Sous l’onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l’utilisateur pour réaliser la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="5eef7-251">Permet de sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5eef7-251">Select one of the following options:</span></span>

    - <span data-ttu-id="5eef7-252">**Heures** – Permet d’entrer le nombre d’heures accordées à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="5eef7-253">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-254">**Jours** – Permet d’entrer le nombre de jours accordés à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="5eef7-255">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-256">**Semaines** – Permet d’entrer le nombre de semaines accordées à l’utilisateur pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="5eef7-257">**Mois** – Permet de sélectionner le jour et la semaine où l’utilisateur doit terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="5eef7-258">Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="5eef7-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="5eef7-259">**Années** – Permet de sélectionner le jour et le mois où l’utilisateur doit terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="5eef7-260">Vous voudrez peut-être que l’utilisateur ait effectué la tâche d’ici le vendredi de la troisième semaine de décembre.</span><span class="sxs-lookup"><span data-stu-id="5eef7-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5. <span data-ttu-id="5eef7-261">Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="5eef7-262">Vous pouvez modifier l’ordre des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-262">You can change the order of the users.</span></span>
6. <span data-ttu-id="5eef7-263">Si les utilisateurs du chemin de réaffectation ne terminent pas la tâche dans le délai imparti, le système agit sur la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="5eef7-264">Pour indiquer l’action exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une action sous l’onglet **Terminer l’action**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="5eef7-265">Indication du moment où le système agit automatiquement sur la tâche</span><span class="sxs-lookup"><span data-stu-id="5eef7-265">Specify when the system automatically acts on the task</span></span>

<span data-ttu-id="5eef7-266">Vous pouvez configurer le système pour qu’il agisse sur la tâche manuelle si elle répond à certaines conditions.</span><span class="sxs-lookup"><span data-stu-id="5eef7-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="5eef7-267">Supposons qu’une tâche nécessite qu’un membre du département États de dépenses passe en revue les reçus soumis avec un état de dépenses.</span><span class="sxs-lookup"><span data-stu-id="5eef7-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="5eef7-268">Selon la stratégie de l’entreprise, cette tâche doit être exécutée si le montant total de l’état de dépense est supérieur à 100 EUR.</span><span class="sxs-lookup"><span data-stu-id="5eef7-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="5eef7-269">Dans ce cas, vous pouvez configurer le système de sorte qu’il marque automatiquement la tâche comme **Terminé** lorsque le montant total est inférieur à 100.</span><span class="sxs-lookup"><span data-stu-id="5eef7-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="5eef7-270">Procédez comme suit pour indiquer quand le système agit sur la tâche manuelle.</span><span class="sxs-lookup"><span data-stu-id="5eef7-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1. <span data-ttu-id="5eef7-271">Dans le volet gauche, cliquez sur **Actions automatiques**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-271">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="5eef7-272">Activez la case à cocher **Activer les actions automatiques**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-272">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="5eef7-273">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-273">Click **Add condition**.</span></span>
4. <span data-ttu-id="5eef7-274">Permet d’entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="5eef7-274">Enter a condition.</span></span>
5. <span data-ttu-id="5eef7-275">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5eef7-275">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="5eef7-276">Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="5eef7-277">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-277">Click **Test**.</span></span>
    2. <span data-ttu-id="5eef7-278">Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="5eef7-279">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-279">Click **Test**.</span></span> <span data-ttu-id="5eef7-280">Le système évalue l’enregistrement pour déterminer s’il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="5eef7-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="5eef7-281">Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7. <span data-ttu-id="5eef7-282">Dans la liste **Action de saisie automatique**, sélectionnez l’action que le système doit appliquer à la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="5eef7-283">Spécification du moment où les notifications sont envoyées</span><span class="sxs-lookup"><span data-stu-id="5eef7-283">Specify when notifications are sent</span></span>

<span data-ttu-id="5eef7-284">Vous pouvez envoyer des notifications aux personnes lorsqu’une tâche manuelle a été déléguée, réaffectée, terminée ou rejetée, ou encore lorsqu’une modification a été demandée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="5eef7-285">Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.</span><span class="sxs-lookup"><span data-stu-id="5eef7-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="5eef7-286">Dans le volet gauche, cliquez sur **Notifications**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-286">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="5eef7-287">Activez la case à cocher en regard des événements pour lesquels les notifications doivent être envoyées.</span><span class="sxs-lookup"><span data-stu-id="5eef7-287">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="5eef7-288">**Déléguer** – La tâche a été affectée à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5eef7-288">**Delegate** – The task has been assigned to another user.</span></span>
    - <span data-ttu-id="5eef7-289">**Réaffecter** – L’utilisateur affecté n’a pas terminé la tâche dans le délai imparti.</span><span class="sxs-lookup"><span data-stu-id="5eef7-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    - <span data-ttu-id="5eef7-290">**Terminé** – L’utilisateur affecté a terminé la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-290">**Complete** – The assigned user has completed the task.</span></span>
    - <span data-ttu-id="5eef7-291">**Rejeter** – L’utilisateur affecté a rejeté le document soumis.</span><span class="sxs-lookup"><span data-stu-id="5eef7-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    - <span data-ttu-id="5eef7-292">**Demander une modification** – L’utilisateur affecté a demandé une modification du document soumis.</span><span class="sxs-lookup"><span data-stu-id="5eef7-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3. <span data-ttu-id="5eef7-293">Sélectionnez la ligne pour un événement sélectionné à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="5eef7-293">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="5eef7-294">Entrez le texte de la notification dans la zone de texte de l’onglet **Texte de notification**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="5eef7-295">Pour personnaliser la notification, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="5eef7-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="5eef7-296">Ils sont remplacés par les informations appropriées lorsque la notification s’affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="5eef7-297">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5eef7-297">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="5eef7-298">Dans la zone de texte, cliquez pour spécifier l’endroit où l’espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-298">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="5eef7-299">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-299">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="5eef7-300">Dans la liste qui s’affiche, sélectionnez l’espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="5eef7-300">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="5eef7-301">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="5eef7-301">Click **Insert**.</span></span>

6. <span data-ttu-id="5eef7-302">Suivez les étapes suivantes pour ajouter une traduction de la notification.</span><span class="sxs-lookup"><span data-stu-id="5eef7-302">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="5eef7-303">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-303">Click **Translations**.</span></span>
    2. <span data-ttu-id="5eef7-304">Dans la page qui s’affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-304">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="5eef7-305">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="5eef7-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="5eef7-306">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-306">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="5eef7-307">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="5eef7-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="5eef7-308">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-308">Click **Close**.</span></span>

7. <span data-ttu-id="5eef7-309">Spécifiez à qui les notifications sont envoyées sous l’onglet **Destinataire**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="5eef7-310">Sélectionnez l’une des options du tableau suivant et suivez les étapes supplémentaires concernant l’option avant de passer à l’étape 8.</span><span class="sxs-lookup"><span data-stu-id="5eef7-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="5eef7-311">Option</span><span class="sxs-lookup"><span data-stu-id="5eef7-311">Option</span></span></th>
    <th><span data-ttu-id="5eef7-312">Destinataires de la notification</span><span class="sxs-lookup"><span data-stu-id="5eef7-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="5eef7-313">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5eef7-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="5eef7-314">Participant</span><span class="sxs-lookup"><span data-stu-id="5eef7-314">Participant</span></span></td>
    <td><span data-ttu-id="5eef7-315">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="5eef7-315">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-316">Après avoir sélectionné <strong>Participant</strong>, sous l’onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="5eef7-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="5eef7-317">Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="5eef7-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-318">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="5eef7-318">Workflow user</span></span></td>
    <td><span data-ttu-id="5eef7-319">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="5eef7-319">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="5eef7-320">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l’onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="5eef7-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="5eef7-321">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="5eef7-321">User</span></span></td>
    <td><span data-ttu-id="5eef7-322">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="5eef7-322">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="5eef7-323">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l’onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="5eef7-324">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5eef7-324">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="5eef7-325">Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="5eef7-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="5eef7-326">Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="5eef7-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="5eef7-327">Définition d’un délai limite</span><span class="sxs-lookup"><span data-stu-id="5eef7-327">Set a time limit</span></span>

<span data-ttu-id="5eef7-328">Si la tâche manuelle doit être exécutée dans un certain délai, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5eef7-328">Follow these steps if the manual task must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="5eef7-329">Les options sélectionnées dans cette procédure remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de la page.</span><span class="sxs-lookup"><span data-stu-id="5eef7-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="5eef7-330">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="5eef7-331">Activez la case à cocher **Définir une limite de temps pour l’élément de workflow**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="5eef7-332">Dans le champ **Durée**, spécifiez quand la tâche doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="5eef7-333">Permet de sélectionner l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="5eef7-333">Select one of the following options:</span></span>

    - <span data-ttu-id="5eef7-334">**Heures** – Permet d’entrer le nombre d’heures pendant lesquelles cette tâche doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="5eef7-335">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-336">**Jours** – Permet d’entrer le nombre de jours pendant lesquels cette tâche doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="5eef7-337">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5eef7-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="5eef7-338">**Semaines** – Permet d’entrer le nombre de semaines accordé pour l’exécution de la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    - <span data-ttu-id="5eef7-339">**Mois** – Permet de sélectionner le jour et la semaine et le mois limites où la tâche doit être terminée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="5eef7-340">Par exemple, vous voudrez peut-être que la tâche soit exécutée d’ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="5eef7-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="5eef7-341">**Années** – Permet de sélectionner le jour, la semaine et le mois limites où la tâche doit être terminée.</span><span class="sxs-lookup"><span data-stu-id="5eef7-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="5eef7-342">Vous voudrez peut-être que la tâche soit exécutée d’ici le vendredi de la troisième semaine de décembre.</span><span class="sxs-lookup"><span data-stu-id="5eef7-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="5eef7-343">Si le délai est dépassé, le système agit sur la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="5eef7-344">Dans la liste **Action**, sélectionnez l’action que le système doit exécuter.</span><span class="sxs-lookup"><span data-stu-id="5eef7-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="5eef7-345">Spécification des actions disponibles pour l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5eef7-345">Specify which actions are available to the user</span></span>

<span data-ttu-id="5eef7-346">Lorsque la tâche manuelle est affectée à un utilisateur, l’utilisateur doit agir sur la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="5eef7-347">Procédez comme suit pour indiquer les actions que l’utilisateur peut exécuter sur la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-347">Follow these steps to specify which actions the user can take on the task.</span></span>

> [!NOTE]
> <span data-ttu-id="5eef7-348">Les actions disponibles peuvent varier selon la conception de la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-348">The actions that are available vary, depending on the design of the task.</span></span>

1. <span data-ttu-id="5eef7-349">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-349">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="5eef7-350">Activez la case à cocher **Terminé** si vous voulez que l’utilisateur puisse marquer la tâche comme **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="5eef7-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3. <span data-ttu-id="5eef7-351">Activez la case à cocher **Rejeter** si vous voulez que l’utilisateur puisse rejeter le document envoyé.</span><span class="sxs-lookup"><span data-stu-id="5eef7-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4. <span data-ttu-id="5eef7-352">Activez la case à cocher **Demander une modification** si vous voulez que l’utilisateur puisse demander des modifications du document envoyé.</span><span class="sxs-lookup"><span data-stu-id="5eef7-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5. <span data-ttu-id="5eef7-353">Activez la case à cocher **Déléguer** si vous voulez que l’utilisateur puisse affecter la tâche à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5eef7-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6. <span data-ttu-id="5eef7-354">Activez la case à cocher **Réaffecter** si vous voulez que l’utilisateur puisse réaffecter la tâche à un autre utilisateur de la file d’attente des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="5eef7-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7. <span data-ttu-id="5eef7-355">Activez la case à cocher **Lancer** si vous voulez que l’utilisateur puisse réaffecter la tâche à la file d’attente des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="5eef7-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="5eef7-356">Un autre utilisateur peut effectuer la tâche.</span><span class="sxs-lookup"><span data-stu-id="5eef7-356">Another user can then complete the task.</span></span>
