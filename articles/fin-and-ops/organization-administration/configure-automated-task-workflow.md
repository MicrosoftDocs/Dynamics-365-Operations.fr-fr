---
title: Configurer des tâches automatiques dans un workflow
description: Cette rubrique explique comment configurer les propriétés d'une tâche automatique.
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
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a9f37228beedafa085987668d5c89b06c6c9d61
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "365107"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="8e88c-103">Configurer des tâches automatiques dans un workflow</span><span class="sxs-lookup"><span data-stu-id="8e88c-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e88c-104">Cette rubrique explique comment configurer les propriétés d'une tâche automatique.</span><span class="sxs-lookup"><span data-stu-id="8e88c-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="8e88c-105">Pour configurer une tâche automatique, dans l'éditeur de workflow, cliquez avec le bouton droit sur la tâche, puis cliquez sur **Propriétés** pour ouvrir la page **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="8e88c-106">Suivez ensuite les procédures suivantes pour configurer les propriétés de la tâche automatique.</span><span class="sxs-lookup"><span data-stu-id="8e88c-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="8e88c-107">Saisie d'un nom pour la tâche</span><span class="sxs-lookup"><span data-stu-id="8e88c-107">Name the task</span></span>

<span data-ttu-id="8e88c-108">Procédez comme suit pour entrer un nom pour la tâche automatique.</span><span class="sxs-lookup"><span data-stu-id="8e88c-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="8e88c-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="8e88c-110">Entrez un nom unique pour la tâche dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="8e88c-111">Spécification du moment où les notifications sont envoyées</span><span class="sxs-lookup"><span data-stu-id="8e88c-111">Specify when notifications are sent</span></span>

<span data-ttu-id="8e88c-112">Vous pouvez envoyer des notifications aux personnes lorsqu'une tâche automatique a été effectuée ou annulée.</span><span class="sxs-lookup"><span data-stu-id="8e88c-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="8e88c-113">Procédez comme suit pour indiquer quand les notifications sont envoyées, et à qui.</span><span class="sxs-lookup"><span data-stu-id="8e88c-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="8e88c-114">Dans le volet gauche, cliquez sur **Notifications**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="8e88c-115">Activez la case à cocher en regard des événements pour lesquels envoyer des notifications :</span><span class="sxs-lookup"><span data-stu-id="8e88c-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="8e88c-116">**Exécution** – Des notifications sont envoyées lorsque la tâche a été exécutée.</span><span class="sxs-lookup"><span data-stu-id="8e88c-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="8e88c-117">**Annulé** – Des notifications sont envoyées lorsque la tâche a été annulée.</span><span class="sxs-lookup"><span data-stu-id="8e88c-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="8e88c-118">Sélectionnez la ligne pour un événement sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="8e88c-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="8e88c-119">Entrez le texte de la notification dans la zone de texte de l'onglet **Texte de notification**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="8e88c-120">Pour personnaliser la notification, vous pouvez insérer des espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="8e88c-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="8e88c-121">Ils sont remplacés par les données appropriées lorsque la notification s'affiche pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8e88c-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="8e88c-122">Pour insérer un espace réservé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8e88c-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="8e88c-123">Dans la zone de texte, cliquez pour spécifier l'endroit où l'espace réservé doit figurer.</span><span class="sxs-lookup"><span data-stu-id="8e88c-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="8e88c-124">Cliquez sur **Insérer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="8e88c-125">Dans la liste qui s'affiche, sélectionnez l'espace réservé que vous souhaitez insérer.</span><span class="sxs-lookup"><span data-stu-id="8e88c-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="8e88c-126">Cliquez sur **Insérer**</span><span class="sxs-lookup"><span data-stu-id="8e88c-126">Click **Insert**.</span></span>

6. <span data-ttu-id="8e88c-127">Suivez les étapes suivantes pour ajouter une traduction de la notification.</span><span class="sxs-lookup"><span data-stu-id="8e88c-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="8e88c-128">Cliquez sur **Traductions**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="8e88c-129">Dans la page qui s'affiche, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="8e88c-130">Dans la liste qui apparaît, sélectionnez la langue de saisie du texte.</span><span class="sxs-lookup"><span data-stu-id="8e88c-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="8e88c-131">Entrez le texte dans le champ **Texte traduit**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="8e88c-132">Pour personnaliser le texte, vous pouvez insérer des espaces réservés tel que décrit à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="8e88c-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="8e88c-133">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-133">Click **Close**.</span></span>

7. <span data-ttu-id="8e88c-134">Spécifiez à qui les notifications sont envoyées sous l'onglet **Destinataire**.</span><span class="sxs-lookup"><span data-stu-id="8e88c-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="8e88c-135">Sélectionnez l'une des options du tableau suivant et suivez les étapes supplémentaires concernant l'option avant de passer à l'étape 8.</span><span class="sxs-lookup"><span data-stu-id="8e88c-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="8e88c-136">Option</span><span class="sxs-lookup"><span data-stu-id="8e88c-136">Option</span></span></th>
    <th><span data-ttu-id="8e88c-137">Destinataires de la notification</span><span class="sxs-lookup"><span data-stu-id="8e88c-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="8e88c-138">Étapes supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8e88c-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="8e88c-139">Participant</span><span class="sxs-lookup"><span data-stu-id="8e88c-139">Participant</span></span></td>
    <td><span data-ttu-id="8e88c-140">Utilisateurs affectés à un groupe ou à un rôle spécifique</span><span class="sxs-lookup"><span data-stu-id="8e88c-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="8e88c-141">Après avoir sélectionné <strong>Participant</strong>, sous l'onglet <strong>Basé sur le rôle</strong>, dans la liste <strong>Type de participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="8e88c-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="8e88c-142">Dans la liste <strong>Participant</strong>, sélectionnez le type de groupe ou de rôle auquel envoyer les notifications.</span><span class="sxs-lookup"><span data-stu-id="8e88c-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="8e88c-143">Utilisateur du workflow</span><span class="sxs-lookup"><span data-stu-id="8e88c-143">Workflow user</span></span></td>
    <td><span data-ttu-id="8e88c-144">Utilisateurs participant au workflow actuel</span><span class="sxs-lookup"><span data-stu-id="8e88c-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="8e88c-145">Après avoir sélectionné <strong>Utilisateur du workflow</strong>, sous l'onglet <strong>Utilisateur du workflow</strong>, dans la liste <strong>Utilisateur du workflow</strong>, sélectionnez un utilisateur qui participe au workflow.</span><span class="sxs-lookup"><span data-stu-id="8e88c-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="8e88c-146">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="8e88c-146">User</span></span></td>
    <td><span data-ttu-id="8e88c-147">Utilisateurs Microsoft Dynamics 365 for Finance and Operations spécifiques</span><span class="sxs-lookup"><span data-stu-id="8e88c-147">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="8e88c-148">Sélectionnez <strong>Utilisateur</strong>, puis cliquez sur l'onglet <strong>Utilisateur</strong>.</span><span class="sxs-lookup"><span data-stu-id="8e88c-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="8e88c-149">La liste <strong>Utilisateurs disponibles</strong> inclut tous les utilisateurs Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8e88c-149">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="8e88c-150">Sélectionnez les utilisateurs à qui envoyer les notifications, puis déplacez-les dans la liste <strong>Utilisateurs sélectionnés</strong>.</span><span class="sxs-lookup"><span data-stu-id="8e88c-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="8e88c-151">Répétez les étapes 3 à 7 pour chaque événement que vous avez sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="8e88c-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>
