---
title: Configurer des étapes d'approbation dans un workflow
description: Cette rubrique explique comment configurer les propriétés d'une étape d'approbation.
author: ChrisGarty
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69035be84d489d6ea2342c6974cfa9a31531f1c7
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698069"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="c757a-103">Configurer des étapes d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="c757a-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c757a-104">Cette rubrique explique comment configurer les propriétés d'une étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="c757a-105">Pour configurer une étape d'approbation, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'étape d'approbation, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c757a-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="c757a-106">Suivez ensuite les procédures suivantes permettent de configurer les propriétés de l'étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="c757a-107">Saisie d'un nom pour l'étape</span><span class="sxs-lookup"><span data-stu-id="c757a-107">Name the step</span></span>
<span data-ttu-id="c757a-108">Procédez comme suit pour entrer un nom pour l'étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="c757a-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="c757a-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c757a-110">Dans le champ **Nom**, entrez un nom unique pour l'étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="c757a-111">Saisie d'une ligne d'objet et des instructions</span><span class="sxs-lookup"><span data-stu-id="c757a-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="c757a-112">Vous devez fournir une ligne d'objet et des instructions aux utilisateurs affectés à l'étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="c757a-113">Par exemple, si vous configurez une étape d'approbation pour des demandes d'achat, l'utilisateur concerné par cette étape voit la ligne d'objet et les instructions sur la page **Demandes d'achat**.</span><span class="sxs-lookup"><span data-stu-id="c757a-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="c757a-114">La ligne d'objet figure dans une barre de message de la page.</span><span class="sxs-lookup"><span data-stu-id="c757a-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="c757a-115">L'utilisateur peut ensuite cliquer sur l'icône de la barre des messages pour afficher les instructions.</span><span class="sxs-lookup"><span data-stu-id="c757a-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="c757a-116">Procédez comme suit pour entrer une ligne d'objet et des instructions.</span><span class="sxs-lookup"><span data-stu-id="c757a-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="c757a-117">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="c757a-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c757a-118">Entrez la ligne d'objet dans le champ **Objet de l'article de travail**.</span><span class="sxs-lookup"><span data-stu-id="c757a-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="c757a-119">Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="c757a-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="c757a-120">Ils sont remplacés par les données appropriées lorsque la ligne d'objet s'affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c757a-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="c757a-121">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c757a-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="c757a-122">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="c757a-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="c757a-123">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="c757a-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="c757a-124">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="c757a-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="c757a-125">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="c757a-125">Click **Insert**.</span></span>

4. <span data-ttu-id="c757a-126">Suivez les étapes suivantes pour ajouter une traduction de la ligne d'objet.</span><span class="sxs-lookup"><span data-stu-id="c757a-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="c757a-127">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="c757a-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="c757a-128">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c757a-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="c757a-129">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="c757a-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="c757a-130">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="c757a-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="c757a-131">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="c757a-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="c757a-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c757a-132">Click **Close**.</span></span>

5. <span data-ttu-id="c757a-133">Entrez les instructions dans le champ **Instructions de l'élément de travail**.</span><span class="sxs-lookup"><span data-stu-id="c757a-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="c757a-134">Pour personnaliser les instructions, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="c757a-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="c757a-135">Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c757a-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="c757a-136">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c757a-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="c757a-137">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="c757a-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="c757a-138">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="c757a-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="c757a-139">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="c757a-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="c757a-140">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="c757a-140">Click **Insert**.</span></span>

7. <span data-ttu-id="c757a-141">Suivez les étapes suivantes pour ajouter une traduction des instructions.</span><span class="sxs-lookup"><span data-stu-id="c757a-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="c757a-142">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="c757a-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="c757a-143">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c757a-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="c757a-144">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="c757a-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="c757a-145">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="c757a-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="c757a-146">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 6.</span><span class="sxs-lookup"><span data-stu-id="c757a-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="c757a-147">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c757a-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="c757a-148">Affectation de l'étape d'approbation</span><span class="sxs-lookup"><span data-stu-id="c757a-148">Assign the approval step</span></span>

<span data-ttu-id="c757a-149">Procédez comme suit pour indiquer à qui affecter la tâche d'approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="c757a-150">Dans le volet gauche, cliquez sur **Affectation**.</span><span class="sxs-lookup"><span data-stu-id="c757a-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="c757a-151">Sous l'onglet **Type d'affectation**, sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="c757a-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="c757a-152">Option</span><span class="sxs-lookup"><span data-stu-id="c757a-152">Option</span></span></th>
    <th><span data-ttu-id="c757a-153">Utilisateurs à qui l'étape d'approbation est affectée</span><span class="sxs-lookup"><span data-stu-id="c757a-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="c757a-154">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c757a-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="c757a-155">Participant</span><span class="sxs-lookup"><span data-stu-id="c757a-155">Participant</span></span></td>
    <td><span data-ttu-id="c757a-156">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="c757a-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c757a-157">Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter l'étape.</span><span class="sxs-lookup"><span data-stu-id="c757a-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="c757a-158">Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel vous souhaitez affecter l'étape.</span><span class="sxs-lookup"><span data-stu-id="c757a-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c757a-159">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="c757a-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="c757a-160">Utilisateurs d'une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="c757a-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c757a-161">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter l'étape.</span><span class="sxs-lookup"><span data-stu-id="c757a-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="c757a-162">Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="c757a-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="c757a-163">Ces noms représentent les utilisateurs à qui l'étape peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="c757a-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="c757a-164">Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c757a-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="c757a-165">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="c757a-166">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="c757a-167">Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="c757a-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="c757a-168">Sous l'onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter l'étape :</span><span class="sxs-lookup"><span data-stu-id="c757a-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="c757a-169"><strong>Affecter à tous les utilisateurs récupérés</strong> – L'étape est affectée à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="c757a-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="c757a-170"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – L'étape est affectée uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="c757a-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="c757a-171"><strong>Exclure les utilisateurs à la condition suivante</strong> – L'étape n'est affectée à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="c757a-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="c757a-172">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="c757a-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c757a-173">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="c757a-173">Workflow user</span></span></td>
    <td><span data-ttu-id="c757a-174">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="c757a-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="c757a-175">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="c757a-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c757a-176">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="c757a-176">User</span></span></td>
    <td><span data-ttu-id="c757a-177">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="c757a-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c757a-178">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="c757a-179">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs système.</span><span class="sxs-lookup"><span data-stu-id="c757a-179">The <strong>Available users</strong> list includes all system users.</span></span> <span data-ttu-id="c757a-180">Sélectionnez les utilisateurs à qui vous souhaitez affecter l'étape, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="c757a-181">Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour traiter les documents qui atteignent cette étape d'approbation ou pour y répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="c757a-182">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c757a-182">Select one of the following options:</span></span>

    - <span data-ttu-id="c757a-183">**Heures** – Entrez le nombre d'heures accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="c757a-184">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c757a-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="c757a-185">**Jours** – Entrez le nombre de jours accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="c757a-186">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c757a-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="c757a-187">**Semaines** – Entrez le nombre de semaines accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="c757a-188">**Mois** – Sélectionnez le jour et la semaine où l'utilisateur doit répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="c757a-189">Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="c757a-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="c757a-190">**Années** – Sélectionnez le jour et le mois limites où l'utilisateur doit répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="c757a-191">Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois de décembre.</span><span class="sxs-lookup"><span data-stu-id="c757a-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="c757a-192">Si l'utilisateur ne traite pas le document dans le délai imparti, le document est en retard.</span><span class="sxs-lookup"><span data-stu-id="c757a-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="c757a-193">Un document en retard est réaffecté, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.</span><span class="sxs-lookup"><span data-stu-id="c757a-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="c757a-194">Si vous avez affecté l'étape d'approbation à plusieurs utilisateurs ou à un groupe d'utilisateurs, cliquez sur l'onglet **Stratégie d'achèvement**, puis sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c757a-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="c757a-195">**Un seul approbateur** – L'action appliquée au document est déterminée par la première personne qui répond.</span><span class="sxs-lookup"><span data-stu-id="c757a-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="c757a-196">Par exemple, Sam a soumis un état de dépenses de USD 15 000.</span><span class="sxs-lookup"><span data-stu-id="c757a-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="c757a-197">L'état de dépenses est actuellement affecté à Sue, Jo et Bill.</span><span class="sxs-lookup"><span data-stu-id="c757a-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="c757a-198">Si Sue est la première à répondre au document, l'action qu'elle effectue est appliquée au document.</span><span class="sxs-lookup"><span data-stu-id="c757a-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="c757a-199">Si Sue rejette le document, il est rejeté et renvoyé à Sam.</span><span class="sxs-lookup"><span data-stu-id="c757a-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="c757a-200">Si Sue approuve le document, il est envoyé à Ann pour approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Workflow avec un processus d'approbation](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="c757a-202">**La majorité des approbateurs** – L'action appliquée au document est déterminée lorsque la majorité des approbateurs ont répondu.</span><span class="sxs-lookup"><span data-stu-id="c757a-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="c757a-203">Par exemple, Sam a soumis un état de dépenses de USD 15 000.</span><span class="sxs-lookup"><span data-stu-id="c757a-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="c757a-204">L'état de dépenses est actuellement affecté à Sue, Jo et Bill.</span><span class="sxs-lookup"><span data-stu-id="c757a-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="c757a-205">Si Sue et Jo sont les deux premiers approbateurs à répondre, l'action qu'ils effectuent est appliquée au document.</span><span class="sxs-lookup"><span data-stu-id="c757a-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="c757a-206">Si Sue approuve le document, mais que Jo le rejette, le document est rejeté et renvoyé à Sam.</span><span class="sxs-lookup"><span data-stu-id="c757a-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="c757a-207">Si Sue et Jo approuvent le document, il est envoyé à Ann pour approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="c757a-208">**Pourcentage d'approbateurs** – L'action appliquée au document est déterminée lorsqu'un pourcentage spécifique d'approbateurs a répondu.</span><span class="sxs-lookup"><span data-stu-id="c757a-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="c757a-209">Par exemple, Sam a soumis un état de dépenses de USD 15 000.</span><span class="sxs-lookup"><span data-stu-id="c757a-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="c757a-210">L'état de dépenses est actuellement affecté à Sue, Jo et Bill, et vous avez entré le pourcentage **50**.</span><span class="sxs-lookup"><span data-stu-id="c757a-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="c757a-211">Si Sue et Jo sont les deux premiers approbateurs à répondre, l'action qu'ils effectuent est appliquée au document, car ils répondent à la condition qui stipule 50 % d'approbateurs.</span><span class="sxs-lookup"><span data-stu-id="c757a-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="c757a-212">Si Sue approuve le document, mais que Jo le rejette, le document est rejeté et renvoyé à Sam.</span><span class="sxs-lookup"><span data-stu-id="c757a-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="c757a-213">Si Sue et Jo approuvent le document, il est envoyé à Ann pour approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="c757a-214">**Tous les approbateurs** – Tous les approbateurs doivent approuver le document.</span><span class="sxs-lookup"><span data-stu-id="c757a-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="c757a-215">Sinon, le workflow ne peut pas continuer.</span><span class="sxs-lookup"><span data-stu-id="c757a-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="c757a-216">Par exemple, Sam a soumis un état de dépenses de 15 000 EUR.</span><span class="sxs-lookup"><span data-stu-id="c757a-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="c757a-217">L'état de dépenses est actuellement affecté à Sue, Jo et Bill.</span><span class="sxs-lookup"><span data-stu-id="c757a-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="c757a-218">Si Sue et Jo approuvent le document, mais que Bill le rejette, le document est rejeté et renvoyé à Sam.</span><span class="sxs-lookup"><span data-stu-id="c757a-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="c757a-219">Si Sue, Jo et Bill approuvent le document, il est envoyé à Ann pour approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="c757a-220">Indication du moment où l'étape d'approbation est requise</span><span class="sxs-lookup"><span data-stu-id="c757a-220">Specify when the approval step is required</span></span>

<span data-ttu-id="c757a-221">Vous pouvez indiquer quand l'étape d'approbation est requise.</span><span class="sxs-lookup"><span data-stu-id="c757a-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="c757a-222">L'étape d'approbation peut être requise tout le temps ou uniquement sous certaines conditions.</span><span class="sxs-lookup"><span data-stu-id="c757a-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="c757a-223">L'étape d'approbation est toujours requise</span><span class="sxs-lookup"><span data-stu-id="c757a-223">The approval step is always required</span></span>

<span data-ttu-id="c757a-224">Si l'étape d'approbation est toujours requise, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c757a-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="c757a-225">Dans le volet gauche, cliquez sur **Condition**.</span><span class="sxs-lookup"><span data-stu-id="c757a-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="c757a-226">Sélectionnez l'option **Toujours exécuter cette étape**.</span><span class="sxs-lookup"><span data-stu-id="c757a-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="c757a-227">L'étape d'approbation est requise sous certaines conditions</span><span class="sxs-lookup"><span data-stu-id="c757a-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="c757a-228">L'étape d'approbation que vous configurez peut être requise uniquement sous certaines conditions.</span><span class="sxs-lookup"><span data-stu-id="c757a-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="c757a-229">Par exemple, si vous configurez une étape d'approbation pour un workflow de demande d'achat, vous voudrez peut-être que cette étape ne soit réalisée que si le montant de la demande d'achat est supérieur à 10 000 EUR.</span><span class="sxs-lookup"><span data-stu-id="c757a-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="c757a-230">Procédez comme suit pour indiquer quand l'étape d'approbation est requise.</span><span class="sxs-lookup"><span data-stu-id="c757a-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="c757a-231">Dans le volet gauche, cliquez sur **Condition**.</span><span class="sxs-lookup"><span data-stu-id="c757a-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="c757a-232">Sélectionnez l'option **Exécuter cette étape uniquement si la condition suivante est remplie**.</span><span class="sxs-lookup"><span data-stu-id="c757a-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="c757a-233">Permet d'entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="c757a-233">Enter a condition.</span></span>
4. <span data-ttu-id="c757a-234">Entrez des conditions supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c757a-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="c757a-235">Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c757a-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="c757a-236">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="c757a-236">Click **Test**.</span></span>
    2. <span data-ttu-id="c757a-237">Sur la page **Condition de workflow de test**, sélectionnez un enregistrement dans la zone **Contrôler la condition**.</span><span class="sxs-lookup"><span data-stu-id="c757a-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="c757a-238">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="c757a-238">Click **Test**.</span></span> <span data-ttu-id="c757a-239">Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="c757a-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="c757a-240">Cliquez sur **OK** ou sur **Annuler** pour revenir à la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c757a-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="c757a-241">Spécification des conséquences du retard du document</span><span class="sxs-lookup"><span data-stu-id="c757a-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="c757a-242">Si un utilisateur ne traite pas un document dans le délai imparti, le document est en retard.</span><span class="sxs-lookup"><span data-stu-id="c757a-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="c757a-243">Un document en retard peut être réaffecté ou affecté automatiquement à un autre utilisateur pour approbation.</span><span class="sxs-lookup"><span data-stu-id="c757a-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="c757a-244">Procédez comme suit pour réaffecter le document en retard.</span><span class="sxs-lookup"><span data-stu-id="c757a-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="c757a-245">Dans le volet gauche, cliquez sur **Escalade**.</span><span class="sxs-lookup"><span data-stu-id="c757a-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="c757a-246">Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="c757a-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="c757a-247">Le système affecte automatiquement le document aux utilisateurs répertoriés dans le chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="c757a-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="c757a-248">Le tableau suivant présente un exemple de chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="c757a-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="c757a-249">Séquence</span><span class="sxs-lookup"><span data-stu-id="c757a-249">Sequence</span></span> | <span data-ttu-id="c757a-250">Chemin de réaffectation</span><span class="sxs-lookup"><span data-stu-id="c757a-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="c757a-251">1</span><span class="sxs-lookup"><span data-stu-id="c757a-251">1</span></span>        | <span data-ttu-id="c757a-252">Affecter à : Donna</span><span class="sxs-lookup"><span data-stu-id="c757a-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="c757a-253">2</span><span class="sxs-lookup"><span data-stu-id="c757a-253">2</span></span>        | <span data-ttu-id="c757a-254">Affecter à : Erin</span><span class="sxs-lookup"><span data-stu-id="c757a-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="c757a-255">3</span><span class="sxs-lookup"><span data-stu-id="c757a-255">3</span></span>        | <span data-ttu-id="c757a-256">Action finale : Rejeter</span><span class="sxs-lookup"><span data-stu-id="c757a-256">Final action: Reject</span></span> |

    <span data-ttu-id="c757a-257">Dans cet exemple, le système affecte le document en retard à Donna.</span><span class="sxs-lookup"><span data-stu-id="c757a-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="c757a-258">Si celle-ci ne répond pas dans le délai imparti, le système affecte le document à Erin.</span><span class="sxs-lookup"><span data-stu-id="c757a-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="c757a-259">Si celle-ci ne répond pas dans le délai imparti, le système rejette le document.</span><span class="sxs-lookup"><span data-stu-id="c757a-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="c757a-260">Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**.</span><span class="sxs-lookup"><span data-stu-id="c757a-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="c757a-261">Sous l'onglet **Type d'affectation**, sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="c757a-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="c757a-262">Option</span><span class="sxs-lookup"><span data-stu-id="c757a-262">Option</span></span></th>
    <th><span data-ttu-id="c757a-263">Utilisateurs à qui le document est affecté</span><span class="sxs-lookup"><span data-stu-id="c757a-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="c757a-264">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c757a-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="c757a-265">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="c757a-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="c757a-266">Utilisateurs d'une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="c757a-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c757a-267">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie à laquelle réaffecter le document.</span><span class="sxs-lookup"><span data-stu-id="c757a-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="c757a-268">Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="c757a-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="c757a-269">Ces noms représentent les utilisateurs à qui le document peut être réaffecté.</span><span class="sxs-lookup"><span data-stu-id="c757a-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="c757a-270">Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c757a-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="c757a-271">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="c757a-272">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="c757a-273">Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="c757a-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="c757a-274">Sous l'onglet <strong>Options de la hiérarchie</strong>, indiquez les utilisateurs de la sélection à qui le document est réaffecté :</span><span class="sxs-lookup"><span data-stu-id="c757a-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="c757a-275"><strong>Affecter à tous les utilisateurs récupérés</strong> – Le document est réaffecté à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="c757a-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="c757a-276"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – Le document est réaffecté uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="c757a-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="c757a-277"><strong>Exclure les utilisateurs à la condition suivante</strong> – Le document n'est affecté à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="c757a-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="c757a-278">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="c757a-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c757a-279">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="c757a-279">Workflow user</span></span></td>
    <td><span data-ttu-id="c757a-280">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="c757a-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="c757a-281">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="c757a-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="c757a-282">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="c757a-282">User</span></span></td>
    <td><span data-ttu-id="c757a-283">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="c757a-283">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="c757a-284">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="c757a-285">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c757a-285">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="c757a-286">Sélectionnez les utilisateurs à qui réaffecter le document, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="c757a-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="c757a-287">Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour traiter les documents qui atteignent cette étape d'approbation ou pour y répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="c757a-288">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c757a-288">Select one of the following options:</span></span>

    - <span data-ttu-id="c757a-289">**Heures** – Entrez le nombre d'heures accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="c757a-290">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c757a-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="c757a-291">**Jours** – Entrez le nombre de jours accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="c757a-292">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c757a-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="c757a-293">**Semaines** – Entrez le nombre de semaines accordé à l'utilisateur pour répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="c757a-294">**Mois** – Sélectionnez le jour et la semaine où l'utilisateur doit répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="c757a-295">Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="c757a-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="c757a-296">**Années** – Sélectionnez le jour et le mois limites où l'utilisateur doit répondre.</span><span class="sxs-lookup"><span data-stu-id="c757a-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="c757a-297">Par exemple, vous pouvez souhaiter que l'utilisateur réponde avant le vendredi de la troisième semaine du mois de décembre.</span><span class="sxs-lookup"><span data-stu-id="c757a-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="c757a-298">Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="c757a-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="c757a-299">Vous pouvez modifier l'ordre des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c757a-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="c757a-300">Si les utilisateurs du chemin de réaffectation ne répondent pas dans le délai imparti, le système traite automatiquement le document.</span><span class="sxs-lookup"><span data-stu-id="c757a-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="c757a-301">Pour indiquer l'action exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une action sous l'onglet **Terminer l'action**.</span><span class="sxs-lookup"><span data-stu-id="c757a-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
