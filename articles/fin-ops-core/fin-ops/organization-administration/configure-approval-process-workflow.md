---
title: Configurer des processus d'approbation dans un workflow
description: La procédure suivante permet de configurer les propriétés du processus d'approbation.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b09d09464eae932bf9caf4f2ea38cbbb3b4f0162
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190210"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="84941-103">Configurer des processus d'approbation dans un workflow</span><span class="sxs-lookup"><span data-stu-id="84941-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84941-104">La procédure suivante permet de configurer les propriétés du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="84941-105">Pour configurer un processus d'approbation, dans l'éditeur de workflow, cliquez avec le bouton droit sur l'élément d'approbation, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="84941-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="84941-106">Saisie d'un nom pour le processus d'approbation</span><span class="sxs-lookup"><span data-stu-id="84941-106">Name the approval process</span></span>

<span data-ttu-id="84941-107">Procédez comme suit pour entrer un nom pour le processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="84941-108">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="84941-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="84941-109">Dans le champ **Nom**, entrez un nom unique pour le processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="84941-110">Indication du moment où le système agit automatiquement sur le document</span><span class="sxs-lookup"><span data-stu-id="84941-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="84941-111">Vous pouvez configurer le système pour qu'il agisse automatiquement sur le document s'il répond à certaines conditions.</span><span class="sxs-lookup"><span data-stu-id="84941-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="84941-112">Par exemple, le système peut approuver les états de dépenses dont le montant total est inférieur à USD 100.</span><span class="sxs-lookup"><span data-stu-id="84941-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="84941-113">Procédez comme suit pour indiquer quand le système agit sur le document.</span><span class="sxs-lookup"><span data-stu-id="84941-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="84941-114">Dans le volet gauche, cliquez sur **Actions automatiques**.</span><span class="sxs-lookup"><span data-stu-id="84941-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="84941-115">Activez la case à cocher **Activer les actions automatiques**.</span><span class="sxs-lookup"><span data-stu-id="84941-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="84941-116">Cliquez sur **Ajouter une condition**.</span><span class="sxs-lookup"><span data-stu-id="84941-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="84941-117">Permet d'entrer une condition.</span><span class="sxs-lookup"><span data-stu-id="84941-117">Enter a condition.</span></span>
5. <span data-ttu-id="84941-118">Entrez d'autres conditions, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="84941-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="84941-119">Pour vérifier que les conditions que vous avez entrées sont correctement configurées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="84941-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="84941-120">Cliquez sur **Test** pour ouvrir l'écran **Condition de workflow de test**.</span><span class="sxs-lookup"><span data-stu-id="84941-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="84941-121">Sélectionnez un enregistrement dans la zone **Contrôler la condition** de l'écran.</span><span class="sxs-lookup"><span data-stu-id="84941-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="84941-122">Cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="84941-122">Click **Test**.</span></span> <span data-ttu-id="84941-123">Le système évalue l'enregistrement pour déterminer s'il répond aux conditions que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="84941-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="84941-124">Cliquez sur **OK** ou sur **Annuler** pour revenir à l'écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="84941-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="84941-125">Dans la liste **Action de saisie automatique**, sélectionnez l'action que le système doit appliquer au document.</span><span class="sxs-lookup"><span data-stu-id="84941-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="84941-126">Spécification du moment où les notifications sont envoyées</span><span class="sxs-lookup"><span data-stu-id="84941-126">Specify when notifications are sent</span></span>

<span data-ttu-id="84941-127">Vous pouvez envoyer des notifications aux personnes lorsqu'un document a été approuvé, rejeté, délégué ou réaffecté, ou encore lorsqu'une modification a été demandée.</span><span class="sxs-lookup"><span data-stu-id="84941-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="84941-128">Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.</span><span class="sxs-lookup"><span data-stu-id="84941-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="84941-129">Dans le volet gauche, cliquez sur **Notifications**.</span><span class="sxs-lookup"><span data-stu-id="84941-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="84941-130">Activez la case à cocher en regard des événements pour lesquels envoyer des notifications :</span><span class="sxs-lookup"><span data-stu-id="84941-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="84941-131">**Déléguer** – Lorsqu'un document a été affecté à un autre utilisateur pour approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="84941-132">**Réaffecter** – Lorsque l'utilisateur affecté n'a pas agi sur un document dans le délai imparti.</span><span class="sxs-lookup"><span data-stu-id="84941-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="84941-133">**Approuver** – Lorsqu'un document a été approuvé.</span><span class="sxs-lookup"><span data-stu-id="84941-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="84941-134">**Rejeter** – Lorsqu'un document a été rejeté.</span><span class="sxs-lookup"><span data-stu-id="84941-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="84941-135">**Demander une modification** – Lorsque l'utilisateur affecté a demandé une modification du document envoyé.</span><span class="sxs-lookup"><span data-stu-id="84941-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="84941-136">Sélectionnez la ligne pour un événement sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="84941-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="84941-137">Cliquez sur l'onglet **Texte de notification**.</span><span class="sxs-lookup"><span data-stu-id="84941-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="84941-138">Dans la zone de texte, entrez le texte de la notification.</span><span class="sxs-lookup"><span data-stu-id="84941-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="84941-139">Pour personnaliser le texte, vous pouvez insérer des espaces réservés qui seront remplacés par les données appropriées lorsqu'ils apparaissent aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="84941-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="84941-140">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="84941-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="84941-141">Cliquez dans la zone de texte à l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="84941-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="84941-142">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="84941-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="84941-143">Dans la liste affichée, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="84941-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="84941-144">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="84941-144">Click **Insert**.</span></span>

7. <span data-ttu-id="84941-145">Pour ajouter des traductions de la notification, cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="84941-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="84941-146">Dans l'écran affiché, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="84941-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="84941-147">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="84941-147">Click **Add**.</span></span>
    2. <span data-ttu-id="84941-148">Dans la liste affichée, sélectionnez la langue dans laquelle vous allez saisir le texte.</span><span class="sxs-lookup"><span data-stu-id="84941-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="84941-149">Entrez le texte dans la zone de texte **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="84941-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="84941-150">Pour personnaliser le texte, insérez des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="84941-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="84941-151">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="84941-151">Click **Close**.</span></span>

8. <span data-ttu-id="84941-152">Cliquez sur l'onglet **Destinataire**.</span><span class="sxs-lookup"><span data-stu-id="84941-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="84941-153">Spécifiez à qui les notifications sont envoyées.</span><span class="sxs-lookup"><span data-stu-id="84941-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="84941-154">Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 10.</span><span class="sxs-lookup"><span data-stu-id="84941-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="84941-155">Option</span><span class="sxs-lookup"><span data-stu-id="84941-155">Option</span></span></th>
    <th><span data-ttu-id="84941-156">Destinataires de la notification</span><span class="sxs-lookup"><span data-stu-id="84941-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="84941-157">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="84941-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="84941-158"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="84941-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="84941-159">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="84941-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="84941-160">Après avoir sélectionné <strong>Participant</strong>, cliquez sur l'onglet <strong>Basé sur les rôles</strong>.</span><span class="sxs-lookup"><span data-stu-id="84941-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="84941-161">Dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="84941-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="84941-162">Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="84941-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="84941-163"><strong>Utilisateur du workflow</strong></span><span class="sxs-lookup"><span data-stu-id="84941-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="84941-164">Utilisateurs participant au workflow actuel</span><span class="sxs-lookup"><span data-stu-id="84941-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="84941-165">Sélectionnez <strong>Utilisateur du workflow</strong>, puis cliquez sur l'onglet <strong>Utilisateur du workflow</strong>.</span><span class="sxs-lookup"><span data-stu-id="84941-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="84941-166">Dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="84941-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="84941-167"><strong>Utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="84941-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="84941-168">Utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="84941-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="84941-169">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="84941-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="84941-170">Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="84941-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="84941-171">Répétez les étapes 3 à 9 pour chaque événement que vous avez sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="84941-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="84941-172">Spécification d'un approbateur final</span><span class="sxs-lookup"><span data-stu-id="84941-172">Specify a final approver</span></span>

<span data-ttu-id="84941-173">Vous voudrez peut-être désigner un approbateur final pour les cas où l'approbateur est la seule personne à soumettre le document pour approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-173">You may want to designate a final approver for scenarios where the approver is the person who submitted the document for approval.</span></span> <span data-ttu-id="84941-174">Pour indiquer un approbateur final, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="84941-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="84941-175">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="84941-175">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="84941-176">Activez la case à cocher **Utiliser l'approbateur final**.</span><span class="sxs-lookup"><span data-stu-id="84941-176">Select the **Use final approver** check box.</span></span>
3. <span data-ttu-id="84941-177">Dans la liste, sélectionnez l'utilisateur qui sera l'approbateur final.</span><span class="sxs-lookup"><span data-stu-id="84941-177">In the list, select the user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="84941-178">Définition d'un délai limite</span><span class="sxs-lookup"><span data-stu-id="84941-178">Set a time limit</span></span>

<span data-ttu-id="84941-179">Si le processus d'approbation doit être exécuté dans un certain délai, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="84941-179">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="84941-180">Les options sélectionnées dans ces étapes remplacent celles sélectionnées dans les zones **Affectation** et **Escalade** de chaque étape d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-180">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="84941-181">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="84941-181">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="84941-182">Activez la case à cocher **Définir une limite de temps pour l'élément** **de workflow**.</span><span class="sxs-lookup"><span data-stu-id="84941-182">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="84941-183">Dans le champ **Durée**, spécifiez quand le processus d'approbation doit être exécuté.</span><span class="sxs-lookup"><span data-stu-id="84941-183">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="84941-184">Permet de sélectionner l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="84941-184">Select one of the following options:</span></span>

    - <span data-ttu-id="84941-185">**Heures** – Permet d'entrer le nombre d'heures accordé pour l'exécution du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-185">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="84941-186">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84941-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="84941-187">**Jours** – Permet d'entrer le nombre de jours accordé pour l'exécution du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-187">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="84941-188">Sélectionnez ensuite le calendrier utilisé par votre organisation, puis entrez les informations relatives à la semaine de travail de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84941-188">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="84941-189">**Semaines** – Permet d'entrer le nombre de semaines accordé pour l'exécution du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-189">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="84941-190">**Mois** – Permet de sélectionner le jour et la semaine limites d'exécution du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-190">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="84941-191">Par exemple, vous voudrez peut-être que le processus d'approbation soit exécuté d'ici le vendredi de la troisième semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="84941-191">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="84941-192">**Années** – Permet de sélectionner la semaine et le mois limites d'exécution du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-192">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="84941-193">Par exemple, vous voudrez peut-être que le processus d'approbation soit exécuté d'ici le vendredi de la troisième semaine de décembre.</span><span class="sxs-lookup"><span data-stu-id="84941-193">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="84941-194">Si le délai est dépassé, le système agit sur le document.</span><span class="sxs-lookup"><span data-stu-id="84941-194">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="84941-195">Dans la liste **Action**, sélectionnez l'action que le système doit exécuter.</span><span class="sxs-lookup"><span data-stu-id="84941-195">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="84941-196">Spécification des actions disponibles pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="84941-196">Specify which actions are available to the user</span></span>

<span data-ttu-id="84941-197">Lorsqu'un document est affecté à un utilisateur pour approbation, ce dernier doit agir sur le document.</span><span class="sxs-lookup"><span data-stu-id="84941-197">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="84941-198">Procédez comme suit pour indiquer les actions que l'utilisateur peut exécuter sur le document soumis.</span><span class="sxs-lookup"><span data-stu-id="84941-198">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="84941-199">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="84941-199">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="84941-200">Activez la case à cocher **Approuver** si l'utilisateur peut approuver le document.</span><span class="sxs-lookup"><span data-stu-id="84941-200">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="84941-201">Activez la case à cocher **Rejeter** si l'utilisateur peut rejeter le document.</span><span class="sxs-lookup"><span data-stu-id="84941-201">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="84941-202">Activez la case à cocher **Demander une modification** si l'utilisateur peut demander des modifications du document.</span><span class="sxs-lookup"><span data-stu-id="84941-202">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="84941-203">Activez la case à cocher **Déléguer** si l'utilisateur peut affecter le document à un autre utilisateur pour approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-203">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="84941-204">La case à cocher **Activer des actions à partir de la liste de travail dans Enterprise Portal** a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="84941-204">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="84941-205">Configuration des étapes d'approbation</span><span class="sxs-lookup"><span data-stu-id="84941-205">Configure the approval steps</span></span>

<span data-ttu-id="84941-206">Un processus d'approbation comprend plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="84941-206">An approval process consists of approval steps.</span></span> <span data-ttu-id="84941-207">Procédez comme suit pour ajouter des étapes au processus d'approbation et les configurer.</span><span class="sxs-lookup"><span data-stu-id="84941-207">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="84941-208">Dans l'éditeur de workflow, double-cliquez sur le processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-208">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="84941-209">L'éditeur de workflow affiche les étapes du processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="84941-209">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="84941-210">Pour ajouter une étape d'approbation, faites glisser l'étape de la zone **Éléments du workflow** sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="84941-210">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="84941-211">Pour configurer une étape d'approbation, voir [Configurer une étape d'approbation](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="84941-211">To configure an approval step, see [Configure an approval step](configure-approval-step-workflow.md).</span></span>
