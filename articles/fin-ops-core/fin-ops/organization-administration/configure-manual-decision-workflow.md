---
title: Configurer des décisions manuelles dans un workflow
description: Cette rubrique explique comment configurer les différentes propriétés d'une décision manuelle.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 859e74b869fcf9b8a886f27f67f51bdf28819979
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698241"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="57ca0-103">Configurer des décisions manuelles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="57ca0-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57ca0-104">Cette rubrique explique comment configurer les différentes propriétés d'une décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="57ca0-105">Pour configurer une décision manuelle, dans l'éditeur de workflow, cliquez avec le bouton droit sur la décision manuelle, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="57ca0-106">Suivez ensuite les procédures suivantes pour configurer les propriétés de la décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="57ca0-107">Saisie d'un nom pour la décision</span><span class="sxs-lookup"><span data-stu-id="57ca0-107">Name the decision</span></span>

<span data-ttu-id="57ca0-108">Procédez comme suit pour entrer un nom pour la décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="57ca0-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57ca0-110">Entrez un nom unique pour la décision manuelle dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="57ca0-111">Saisie d'une ligne d'objet et des instructions</span><span class="sxs-lookup"><span data-stu-id="57ca0-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="57ca0-112">Vous devez fournir une ligne d'objet et des instructions aux utilisateurs affectés à la décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="57ca0-113">Par exemple, si vous configurez une décision pour des demandes d'achat, l'utilisateur concerné par cette décision voit la ligne d'objet et les instructions dans la page **Demandes d'achat**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="57ca0-114">La ligne d'objet figure dans une barre de message de la page.</span><span class="sxs-lookup"><span data-stu-id="57ca0-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="57ca0-115">L'utilisateur peut ensuite cliquer sur l'icône de la barre des messages pour afficher les instructions.</span><span class="sxs-lookup"><span data-stu-id="57ca0-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="57ca0-116">Procédez comme suit pour entrer une ligne d'objet et des instructions.</span><span class="sxs-lookup"><span data-stu-id="57ca0-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="57ca0-117">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57ca0-118">Entrez la ligne d'objet dans l'onglet **Instructions**, dans le champ **Objet de l'article de travail**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="57ca0-119">Si vous souhaitez personnaliser la ligne, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="57ca0-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="57ca0-120">Ils sont remplacés par les données appropriées lorsque la ligne d'objet s'affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="57ca0-121">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57ca0-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="57ca0-122">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="57ca0-123">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="57ca0-124">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="57ca0-125">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="57ca0-125">Click **Insert**.</span></span>

4. <span data-ttu-id="57ca0-126">Suivez les étapes suivantes pour ajouter une traduction de la ligne d'objet.</span><span class="sxs-lookup"><span data-stu-id="57ca0-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="57ca0-127">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="57ca0-128">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57ca0-129">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="57ca0-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="57ca0-130">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57ca0-131">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="57ca0-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="57ca0-132">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-132">Click **Close**.</span></span>

5. <span data-ttu-id="57ca0-133">Entrez les instructions dans le champ **Instructions de l'élément de travail**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="57ca0-134">Pour personnaliser les instructions, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="57ca0-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="57ca0-135">Ils sont remplacés par les données appropriées lorsque les instructions apparaissent aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="57ca0-136">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57ca0-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="57ca0-137">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="57ca0-138">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="57ca0-139">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="57ca0-140">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="57ca0-140">Click **Insert**.</span></span>

7. <span data-ttu-id="57ca0-141">Suivez les étapes suivantes pour ajouter une traduction des instructions.</span><span class="sxs-lookup"><span data-stu-id="57ca0-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="57ca0-142">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="57ca0-143">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57ca0-144">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="57ca0-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="57ca0-145">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57ca0-146">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 6.</span><span class="sxs-lookup"><span data-stu-id="57ca0-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="57ca0-147">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="57ca0-148">Indication des résultats possibles d'une décision</span><span class="sxs-lookup"><span data-stu-id="57ca0-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="57ca0-149">En général, quand un document est affecté à un décideur lorsque ce dernier doit répondre à une question.</span><span class="sxs-lookup"><span data-stu-id="57ca0-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="57ca0-150">Le plus souvent, la réponse à la question est **Oui** ou **Non** ou **Vrai** ou **Faux**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="57ca0-151">Procédez comme suit pour indiquer les résultats possibles de la décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="57ca0-152">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57ca0-153">Entrez le nom du résultat ou de l'option dans l'onglet **Résultats**, dans le champ **Résultat 1**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="57ca0-154">Suivez les étapes suivantes pour ajouter une traduction du résultat.</span><span class="sxs-lookup"><span data-stu-id="57ca0-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="57ca0-155">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="57ca0-156">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57ca0-157">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="57ca0-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="57ca0-158">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57ca0-159">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-159">Click **Close**.</span></span>

4. <span data-ttu-id="57ca0-160">Dans le champ **Résultat 2**, entrez le nom du résultat ou de l'option.</span><span class="sxs-lookup"><span data-stu-id="57ca0-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="57ca0-161">Suivez les étapes suivantes pour ajouter une traduction du résultat.</span><span class="sxs-lookup"><span data-stu-id="57ca0-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="57ca0-162">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="57ca0-163">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57ca0-164">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="57ca0-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="57ca0-165">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57ca0-166">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="57ca0-167">Spécification du moment où les notifications sont envoyées</span><span class="sxs-lookup"><span data-stu-id="57ca0-167">Specify when notifications are sent</span></span>

<span data-ttu-id="57ca0-168">Vous pouvez envoyer des notifications aux personnes lorsqu'une décision doit être prise, déléguée ou réaffectée.</span><span class="sxs-lookup"><span data-stu-id="57ca0-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="57ca0-169">Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.</span><span class="sxs-lookup"><span data-stu-id="57ca0-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="57ca0-170">Dans le volet gauche, cliquez sur **Notifications**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="57ca0-171">Activez la case à cocher en regard des événements pour lesquels les notifications doivent être envoyées.</span><span class="sxs-lookup"><span data-stu-id="57ca0-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="57ca0-172">**\[Choix 1\]** – L'utilisateur affecté a choisi **\[Choix 1\]**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="57ca0-173">**\[Choix 2\]** – L'utilisateur affecté a choisi **\[Choix 2\]**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="57ca0-174">**Déléguer** – L'utilisateur affecté a affecté la décision à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="57ca0-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="57ca0-175">**Réaffecter** – L'utilisateur affecté n'a pas pris la décision dans le délai imparti.</span><span class="sxs-lookup"><span data-stu-id="57ca0-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="57ca0-176">Sélectionnez la ligne pour un événement sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="57ca0-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="57ca0-177">Entrez le texte de la notification dans la zone de texte de l'onglet **Texte de notification**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="57ca0-178">Pour personnaliser la notification, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="57ca0-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="57ca0-179">Ils sont remplacés par les données appropriées lorsque la notification s'affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="57ca0-180">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57ca0-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="57ca0-181">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="57ca0-182">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="57ca0-183">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="57ca0-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="57ca0-184">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="57ca0-184">Click **Insert**.</span></span>

6. <span data-ttu-id="57ca0-185">Suivez les étapes suivantes pour ajouter une traduction de la notification.</span><span class="sxs-lookup"><span data-stu-id="57ca0-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="57ca0-186">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="57ca0-187">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57ca0-188">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="57ca0-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="57ca0-189">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57ca0-190">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="57ca0-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="57ca0-191">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-191">Click **Close**.</span></span>

7. <span data-ttu-id="57ca0-192">Spécifiez à qui les notifications sont envoyées sous l'onglet **Destinataire**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="57ca0-193">Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 8.</span><span class="sxs-lookup"><span data-stu-id="57ca0-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="57ca0-194">Option</span><span class="sxs-lookup"><span data-stu-id="57ca0-194">Option</span></span></th>
    <th><span data-ttu-id="57ca0-195">Destinataires de la notification</span><span class="sxs-lookup"><span data-stu-id="57ca0-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="57ca0-196">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="57ca0-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="57ca0-197">Participant</span><span class="sxs-lookup"><span data-stu-id="57ca0-197">Participant</span></span></td>
    <td><span data-ttu-id="57ca0-198">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="57ca0-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-199">Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="57ca0-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="57ca0-200">Dans la liste <strong>Participant</strong>, sélectionnez le groupe ou le rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="57ca0-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-201">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="57ca0-201">Workflow user</span></span></td>
    <td><span data-ttu-id="57ca0-202">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="57ca0-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="57ca0-203">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="57ca0-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-204">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="57ca0-204">User</span></span></td>
    <td><span data-ttu-id="57ca0-205">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="57ca0-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-206">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="57ca0-207">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="57ca0-208">Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="57ca0-209">Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="57ca0-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="57ca0-210">Affectation d'une décision</span><span class="sxs-lookup"><span data-stu-id="57ca0-210">Assign a decision</span></span>

<span data-ttu-id="57ca0-211">Procédez comme suit pour indiquer à qui affecter une décision manuelle.</span><span class="sxs-lookup"><span data-stu-id="57ca0-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="57ca0-212">Dans le volet gauche, cliquez sur **Affectation**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="57ca0-213">Sous l'onglet **Type d'affectation**, sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="57ca0-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="57ca0-214">Option</span><span class="sxs-lookup"><span data-stu-id="57ca0-214">Option</span></span></th>
    <th><span data-ttu-id="57ca0-215">Utilisateurs à qui la décision est affectée</span><span class="sxs-lookup"><span data-stu-id="57ca0-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="57ca0-216">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="57ca0-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="57ca0-217">Participant</span><span class="sxs-lookup"><span data-stu-id="57ca0-217">Participant</span></span></td>
    <td><span data-ttu-id="57ca0-218">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="57ca0-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-219">Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="57ca0-220">Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel affecter la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-221">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="57ca0-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="57ca0-222">Utilisateurs d'une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="57ca0-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-223">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie auquel affecter la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="57ca0-224">Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="57ca0-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="57ca0-225">Ces noms représentent les utilisateurs à qui la décision peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="57ca0-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="57ca0-226">Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57ca0-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="57ca0-227">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="57ca0-228">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="57ca0-229">Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="57ca0-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="57ca0-230">Sous l'onglet <strong>Options de la hiérarchie</strong>, spécifiez les utilisateurs de la sélection auxquels affecter la décision :</span><span class="sxs-lookup"><span data-stu-id="57ca0-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="57ca0-231"><strong>Affecter à tous les utilisateurs récupérés</strong> – La décision est affectée à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="57ca0-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="57ca0-232"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La décision est affectée uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="57ca0-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="57ca0-233"><strong>Exclure les utilisateurs à la condition suivante</strong> – La décision n'est affectée à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="57ca0-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="57ca0-234">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="57ca0-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-235">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="57ca0-235">Workflow user</span></span></td>
    <td><span data-ttu-id="57ca0-236">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="57ca0-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="57ca0-237">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="57ca0-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-238">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="57ca0-238">User</span></span></td>
    <td><span data-ttu-id="57ca0-239">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="57ca0-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-240">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="57ca0-241">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="57ca0-242">Sélectionnez les utilisateurs à qui vous souhaitez affecter la décision, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="57ca0-243">Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="57ca0-244">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="57ca0-244">Select one of the following options:</span></span>

    - <span data-ttu-id="57ca0-245">**Heures** – Permet d'entrer le nombre d'heures accordées à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="57ca0-246">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-247">**Jours** – Permet d'entrer le nombre de jours accordés à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="57ca0-248">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-249">**Semaines** – Permet d'entrer le nombre de semaines accordées à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="57ca0-250">**Mois** – Permet de sélectionner le jour et la semaine où l'utilisateur doit prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="57ca0-251">Vous voudrez peut-être que l'utilisateur prenne la décision d'ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="57ca0-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="57ca0-252">**Années** – Permet de sélectionner le jour, la semaine et le mois où l'utilisateur doit prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="57ca0-253">Vous voudrez peut-être que l'utilisateur prenne la décision d'ici le vendredi de la troisième semaine du mois de décembre.</span><span class="sxs-lookup"><span data-stu-id="57ca0-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="57ca0-254">Si l'utilisateur ne prend pas la décision dans le délai imparti, la décision est en retard.</span><span class="sxs-lookup"><span data-stu-id="57ca0-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="57ca0-255">Une décision en retard est réaffectée, conformément aux options que vous sélectionnez dans la zone **Escalade** de cette page.</span><span class="sxs-lookup"><span data-stu-id="57ca0-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="57ca0-256">Spécification des conséquences du retard d'une décision</span><span class="sxs-lookup"><span data-stu-id="57ca0-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="57ca0-257">Si un utilisateur ne prend pas la décision dans le délai imparti, la décision est en retard.</span><span class="sxs-lookup"><span data-stu-id="57ca0-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="57ca0-258">Une décision en retard peut être affectée à un échelon supérieur ou affectée automatiquement à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="57ca0-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="57ca0-259">Procédez comme suit pour réaffecter la décision en retard.</span><span class="sxs-lookup"><span data-stu-id="57ca0-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="57ca0-260">Dans le volet gauche, cliquez sur **Escalade**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="57ca0-261">Activez la case à cocher **Utiliser le chemin de réaffectation** pour créer un chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="57ca0-262">Le système affecte automatiquement la décision aux utilisateurs répertoriés dans le chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="57ca0-263">Le tableau suivant présente un exemple de chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="57ca0-264">Séquence</span><span class="sxs-lookup"><span data-stu-id="57ca0-264">Sequence</span></span> | <span data-ttu-id="57ca0-265">Chemin de réaffectation</span><span class="sxs-lookup"><span data-stu-id="57ca0-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="57ca0-266">1</span><span class="sxs-lookup"><span data-stu-id="57ca0-266">1</span></span>        | <span data-ttu-id="57ca0-267">Affecter à : Donna</span><span class="sxs-lookup"><span data-stu-id="57ca0-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="57ca0-268">2</span><span class="sxs-lookup"><span data-stu-id="57ca0-268">2</span></span>        | <span data-ttu-id="57ca0-269">Affecter à : Erin</span><span class="sxs-lookup"><span data-stu-id="57ca0-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="57ca0-270">3</span><span class="sxs-lookup"><span data-stu-id="57ca0-270">3</span></span>        | <span data-ttu-id="57ca0-271">Action finale : \[Choix 1\]</span><span class="sxs-lookup"><span data-stu-id="57ca0-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="57ca0-272">Dans cet exemple, le système affecte la décision en retard à Donna.</span><span class="sxs-lookup"><span data-stu-id="57ca0-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="57ca0-273">Si celle-ci ne prend pas la décision dans le délai imparti, le système affecte la décision à Erin.</span><span class="sxs-lookup"><span data-stu-id="57ca0-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="57ca0-274">Si celle-ci ne prend pas la décision dans le délai imparti, le système sélectionne le **\[Choix 1\]** comme décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="57ca0-275">Pour ajouter un utilisateur dans le chemin de réaffectation, cliquez sur **Ajouter une réaffectation**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="57ca0-276">Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 4.</span><span class="sxs-lookup"><span data-stu-id="57ca0-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="57ca0-277">Option</span><span class="sxs-lookup"><span data-stu-id="57ca0-277">Option</span></span></th>
    <th><span data-ttu-id="57ca0-278">Utilisateurs à qui la décision est affectée</span><span class="sxs-lookup"><span data-stu-id="57ca0-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="57ca0-279">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="57ca0-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="57ca0-280">Hiérarchie</span><span class="sxs-lookup"><span data-stu-id="57ca0-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="57ca0-281">Utilisateurs d'une hiérarchie organisationnelle spécifique</span><span class="sxs-lookup"><span data-stu-id="57ca0-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-282">Après avoir sélectionné <strong>Hiérarchie</strong>, sous l'onglet <strong>Sélection de hiérarchie</strong>, dans la liste <strong>Type de hiérarchie</strong>, sélectionnez le type de hiérarchie à laquelle réaffecter la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="57ca0-283">Le système doit extraire un ensemble de noms d'utilisateurs de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="57ca0-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="57ca0-284">Ces noms représentent les utilisateurs à qui la décision peut être réaffectée.</span><span class="sxs-lookup"><span data-stu-id="57ca0-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="57ca0-285">Pour indiquer le point de départ et le point final de l'ensemble de noms d'utilisateurs extraits par le système, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="57ca0-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="57ca0-286">Pour spécifier le point de départ, sélectionnez une personne dans la liste <strong>Commencer à</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="57ca0-287">pour indiquer le point final, cliquez sur <strong>Ajouter une condition</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="57ca0-288">Entrez ensuite une condition pour indiquer où le système arrête l'extraction de noms dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="57ca0-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="57ca0-289">Sous l'onglet <strong>Options de la hiérarchie</strong>, indiquez les utilisateurs de la sélection à qui la décision est réaffecté :</span><span class="sxs-lookup"><span data-stu-id="57ca0-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="57ca0-290"><strong>Affecter à tous les utilisateurs récupérés</strong> – La décision est réaffecté à tous les utilisateurs de la sélection.</span><span class="sxs-lookup"><span data-stu-id="57ca0-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="57ca0-291"><strong>Affecter uniquement au dernier utilisateur récupéré</strong> – La décision est réaffecté uniquement au dernier utilisateur de la sélection.</span><span class="sxs-lookup"><span data-stu-id="57ca0-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="57ca0-292"><strong>Exclure les utilisateurs à la condition suivante</strong> – La décision n'est réaffectée à aucun des utilisateurs de la sélection qui remplissent une condition.</span><span class="sxs-lookup"><span data-stu-id="57ca0-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="57ca0-293">Cliquez sur <strong>Ajouter une condition</strong> pour spécifier la condition.</span><span class="sxs-lookup"><span data-stu-id="57ca0-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-294">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="57ca0-294">Workflow user</span></span></td>
    <td><span data-ttu-id="57ca0-295">Utilisateurs du workflow actuel</span><span class="sxs-lookup"><span data-stu-id="57ca0-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="57ca0-296">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="57ca0-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57ca0-297">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="57ca0-297">User</span></span></td>
    <td><span data-ttu-id="57ca0-298">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="57ca0-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57ca0-299">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="57ca0-300">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="57ca0-301">Sélectionnez les utilisateurs à qui réaffecter la décision, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="57ca0-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="57ca0-302">Sous l'onglet **Limite de temps**, dans le champ **Durée**, indiquez le délai accordé à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="57ca0-303">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="57ca0-303">Select one of the following options:</span></span>

    - <span data-ttu-id="57ca0-304">**Heures** – Permet d'entrer le nombre d'heures accordées à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="57ca0-305">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-306">**Jours** – Permet d'entrer le nombre de jours accordés à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="57ca0-307">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-308">**Semaines** – Permet d'entrer le nombre de semaines accordées à l'utilisateur pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="57ca0-309">**Mois** – Permet de sélectionner le jour et la semaine où l'utilisateur doit prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="57ca0-310">Vous voudrez peut-être que l'utilisateur prenne la décision d'ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="57ca0-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="57ca0-311">**Années** – Permet de sélectionner le jour, la semaine et le mois où l'utilisateur doit prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="57ca0-312">Vous voudrez peut-être que l'utilisateur prenne la décision d'ici le vendredi de la troisième semaine du mois de décembre.</span><span class="sxs-lookup"><span data-stu-id="57ca0-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="57ca0-313">Répétez les étapes 3 à 4 pour chaque utilisateur à ajouter au chemin de réaffectation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="57ca0-314">Vous pouvez modifier l'ordre des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="57ca0-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="57ca0-315">Si les utilisateurs du chemin de réaffectation ne prennent pas la décision dans le délai imparti, le système prend la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="57ca0-316">Pour indiquer l'option exécutée par le système, sélectionnez la ligne **Action**, puis sélectionnez une option sous l'onglet **Terminer l'action**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="57ca0-317">Définition d'un délai limite</span><span class="sxs-lookup"><span data-stu-id="57ca0-317">Set a time limit</span></span>

<span data-ttu-id="57ca0-318">Si la décision doit être prise dans un certain délai, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="57ca0-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="57ca0-319">Les options sélectionnées dans cette procédure remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de la page.</span><span class="sxs-lookup"><span data-stu-id="57ca0-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="57ca0-320">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="57ca0-321">Activez la case à cocher **Définir une limite de temps pour l'élément de workflow**.</span><span class="sxs-lookup"><span data-stu-id="57ca0-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="57ca0-322">Dans le champ **Durée**, spécifiez quand la décision doit être prise.</span><span class="sxs-lookup"><span data-stu-id="57ca0-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="57ca0-323">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="57ca0-323">Select one of the following options:</span></span>

    - <span data-ttu-id="57ca0-324">**Heures** – Permet d'entrer le nombre d'heures.</span><span class="sxs-lookup"><span data-stu-id="57ca0-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="57ca0-325">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-326">**Jours** – Permet d'entrer le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="57ca0-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="57ca0-327">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="57ca0-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="57ca0-328">**Semaines** – Permet d'entrer le nombre de semaines.</span><span class="sxs-lookup"><span data-stu-id="57ca0-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="57ca0-329">**Mois** – Permet de sélectionner le jour et la semaine où prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="57ca0-330">Par exemple, vous pouvez décider que la décision soit prise d'ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="57ca0-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="57ca0-331">**Années** – Permet de sélectionner le jour, la semaine et le mois limites pour prendre la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="57ca0-332">Par exemple, vous pouvez décider que la décision soit prise d'ici le vendredi de la troisième semaine de décembre.</span><span class="sxs-lookup"><span data-stu-id="57ca0-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="57ca0-333">Si le délai est dépassé, le système prend la décision.</span><span class="sxs-lookup"><span data-stu-id="57ca0-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="57ca0-334">Dans la liste **Action**, sélectionnez l'option que le système doit sélectionner.</span><span class="sxs-lookup"><span data-stu-id="57ca0-334">In the **Action** list, select the option that the system should select.</span></span>
