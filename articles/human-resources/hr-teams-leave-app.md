---
title: Gérer les demandes de congé dans Teams
description: Cette rubrique montre comment demander des congés dans l’application Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6856e417ee47f8f582f797c5bcedcff23a1432f
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3929991"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="f417d-103">Gérer les demandes de congé dans Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f417d-104">L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams vous permet de demander rapidement des congés et d’afficher les informations sur votre solde de congés directement dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="f417d-105">Vous pouvez interagir avec un robot pour demander des informations et lancer une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="f417d-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="f417d-106">L’onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="f417d-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="f417d-107">En outre, vous pouvez envoyer des informations aux personnes sur votre prochain congé dans les équipes et dans les chats en dehors de l'application Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f417d-107">In addition, you can send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="f417d-108">Installer l’application</span><span class="sxs-lookup"><span data-stu-id="f417d-108">Install the app</span></span>

<span data-ttu-id="f417d-109">Vous pouvez trouver l’application Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="f417d-110">Sélectionnez les ellipses dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Ellipses de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="f417d-112">Recherchez Dynamics 365 Human Resources, puis sélectionnez la vignette **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="f417d-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Vignette HR de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="f417d-114">Sélectionnez le bouton **Ajouter** pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="f417d-114">Select the **Add** button to install the app.</span></span>

   ![Installation de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="f417d-116">Si l’application ne vous connecte pas automatiquement, sélectionnez l’onglet **Paramètres** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f417d-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Onglet Paramètres de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="f417d-118">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="f417d-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="f417d-119">Si vous avez accès à plusieurs instances de Human Resources, vous pouvez sélectionner l’environnement auquel vous souhaitez vous connecter dans l’onglet **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="f417d-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="f417d-120">L'application prend désormais en charge le rôle de sécurité Administrateur système.</span><span class="sxs-lookup"><span data-stu-id="f417d-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="f417d-121">Utiliser le bot</span><span class="sxs-lookup"><span data-stu-id="f417d-121">Use the bot</span></span>

<span data-ttu-id="f417d-122">Après l’installation de l’application, un message de bienvenue apparaît, vous informant des types d’actions que le bot peut entreprendre en votre nom.</span><span class="sxs-lookup"><span data-stu-id="f417d-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Les équipes de Human Resources laissent un message de bienvenue au robot](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="f417d-124">Lors de la première interaction avec le bot, vous devrez peut-être vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f417d-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="f417d-125">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="f417d-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="f417d-126">Vous pouvez demander au bot d’effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f417d-126">You can ask the bot to:</span></span>

- <span data-ttu-id="f417d-127">Afficher les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier.</span><span class="sxs-lookup"><span data-stu-id="f417d-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![L’application de congé Human Resources de Teams affiche les soldes](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="f417d-129">Afficher des détails supplémentaires sur un type de congé spécifique.</span><span class="sxs-lookup"><span data-stu-id="f417d-129">Show additional details about a specific leave type.</span></span>

   ![L’application de congé Human Resources de Teams affiche les détails](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="f417d-131">Lancer une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="f417d-131">Start a leave request for you.</span></span>

   ![L’application de congé Human Resources de Teams fait la demande de congé](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="f417d-133">Après avoir lancé une demande de congé, vous pouvez ajuster les jours directement dans la carte.</span><span class="sxs-lookup"><span data-stu-id="f417d-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![L’application de congé Human Resources de Teams modifie la demande](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="f417d-135">Lorsque vous avez terminé de saisir les informations, sélectionnez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="f417d-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="f417d-136">Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="f417d-136">You can also select **Save as draft** to come back to it later.</span></span>

![L’application de congé Human Resources de Teams soumet la demande](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="f417d-138">Gérer votre demandes dans Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-138">Manage your leave in Teams</span></span>

<span data-ttu-id="f417d-139">L’onglet **Congés** vous permet de visualiser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f417d-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="f417d-140">Les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier</span><span class="sxs-lookup"><span data-stu-id="f417d-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="f417d-141">Les demandes de congé à venir</span><span class="sxs-lookup"><span data-stu-id="f417d-141">Upcoming leave requests</span></span>

- <span data-ttu-id="f417d-142">Les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="f417d-142">Time-off requests</span></span>

- <span data-ttu-id="f417d-143">Les brouillons de demande de congé</span><span class="sxs-lookup"><span data-stu-id="f417d-143">Draft leave requests</span></span>

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="f417d-145">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="f417d-145">Create a new request</span></span>

1. <span data-ttu-id="f417d-146">Pour créer une demande de congé, sélectionnez **Nouvelle demande**.</span><span class="sxs-lookup"><span data-stu-id="f417d-146">To create a new leave request, select **New request**.</span></span>

   ![Nouvelle demande de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="f417d-148">Saisissez le ou les jours que vous souhaitez prendre, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f417d-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![L’application de congé Human Resources de Teams ajoute les congés](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="f417d-150">Le cas échéant, entrez un code motif.</span><span class="sxs-lookup"><span data-stu-id="f417d-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="f417d-151">Saisissez également des commentaires et ajoutez des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="f417d-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="f417d-152">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="f417d-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f417d-153">Vous pouvez également taper **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="f417d-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="f417d-154">Gérer les brouillons de demande</span><span class="sxs-lookup"><span data-stu-id="f417d-154">Manage draft requests</span></span>

1. <span data-ttu-id="f417d-155">Sélectionnez l’onglet **Brouillons**.</span><span class="sxs-lookup"><span data-stu-id="f417d-155">Select the **Drafts** tab.</span></span>

   ![Onglet Brouillons de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="f417d-157">Sélectionnez le crayon pour modifier la demande ou sélectionnez la corbeille pour supprimer la demande.</span><span class="sxs-lookup"><span data-stu-id="f417d-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="f417d-158">Apportez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="f417d-158">Make any necessary changes.</span></span> <span data-ttu-id="f417d-159">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="f417d-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f417d-160">Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="f417d-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![L’application de congé Human Resources de Teams modifie le brouillon](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="f417d-162">Répondre aux notifications Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-162">Respond to Teams notifications</span></span>

<span data-ttu-id="f417d-163">Lorsque vous ou un collaborateur dont vous êtes l’approbateur soumettez une demande de congé, vous recevez une notification dans l’application Human Resources dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="f417d-164">Vous pouvez sélectionner la notification pour l’afficher.</span><span class="sxs-lookup"><span data-stu-id="f417d-164">You can select the notification to view it.</span></span> <span data-ttu-id="f417d-165">Les notifications apparaissent également dans la zone **Conversation instantanée**.</span><span class="sxs-lookup"><span data-stu-id="f417d-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="f417d-166">Si vous êtes un approbateur, vous pouvez sélectionner **Approuver** ou **Refuser** dans la notification.</span><span class="sxs-lookup"><span data-stu-id="f417d-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="f417d-167">Vous pouvez également fournir un message facultatif.</span><span class="sxs-lookup"><span data-stu-id="f417d-167">You can also provide an optional message.</span></span>

![Laisser une notification de demande dans l’applications Teams Human Resources](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="f417d-169">Envoyer des informations sur les congés à venir à vos collègues</span><span class="sxs-lookup"><span data-stu-id="f417d-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="f417d-170">Après avoir installé l'application Human Resources pour Teams, vous pouvez facilement envoyer des informations sur votre prochain congé à vos collègues dans les équipes ou les chats.</span><span class="sxs-lookup"><span data-stu-id="f417d-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="f417d-171">Dans une équipe ou dans une discussion dans Teams, sélectionnez le bouton Ressources humaines sous la fenêtre de discussion.</span><span class="sxs-lookup"><span data-stu-id="f417d-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Bouton Ressources humaines sous la fenêtre de discussion](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="f417d-173">Sélectionnez la demande de congé que vous souhaitez partager.</span><span class="sxs-lookup"><span data-stu-id="f417d-173">Select the leave request you want to share.</span></span> <span data-ttu-id="f417d-174">Si vous souhaitez partager un brouillon de demande de congé, sélectionnez **Brouillons** en premier.</span><span class="sxs-lookup"><span data-stu-id="f417d-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Sélectionner une demande de congé à venir à partager](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="f417d-176">Votre demande de congé s'affichera dans le chat.</span><span class="sxs-lookup"><span data-stu-id="f417d-176">Your leave request will display in the chat.</span></span>

![Carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="f417d-178">Si vous avez partagé une demande de brouillon, elle s'affichera comme brouillon :</span><span class="sxs-lookup"><span data-stu-id="f417d-178">If you shared a draft request, it will display as a draft:</span></span>

![Brouillon de carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="f417d-180">Afficher votre calendrier de congés d’équipe</span><span class="sxs-lookup"><span data-stu-id="f417d-180">View your team's leave calendar</span></span>

<span data-ttu-id="f417d-181">Si vous êtes un responsable avec des subordonnés directs, vous pouvez afficher les congés approuvés et en attente de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="f417d-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="f417d-182">Dans l’application Human Resources dans Teams, sélectionnez **Congés**.</span><span class="sxs-lookup"><span data-stu-id="f417d-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="f417d-183">Sélectionnez **Calendrier d’équipe**.</span><span class="sxs-lookup"><span data-stu-id="f417d-183">Select **Team calendar**.</span></span>

   ![Afficher le calendrier de l’application Human Resources de Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="f417d-185">Le calendrier affiche les congés approuvés et en attente de vos subordonnés directs.</span><span class="sxs-lookup"><span data-stu-id="f417d-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Calendrier des congés de l’application Human Resources de Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="f417d-187">Dépannage</span><span class="sxs-lookup"><span data-stu-id="f417d-187">Troubleshooting</span></span>

<span data-ttu-id="f417d-188">Si vous rencontrez des problèmes pour vous connecter ou utiliser l'application Teams de Human Resources, essayez de suivre ces instructions de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="f417d-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="f417d-189">Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l'assistance.</span><span class="sxs-lookup"><span data-stu-id="f417d-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="f417d-190">Pour plus d’informations, voir [Obtenir de l’aide](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="f417d-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="f417d-191">Impossible de se connecter à l'application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="f417d-192">Si vous ne pouvez pas vous connecter à l'application, il est possible que le compte que vous utilisez pour vous connecterà Microsoft Teams ne soit pas associé à un enregistrement d'employé dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f417d-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f417d-193">Contactez votre administrateur système pour vous assurer que votre enregistrement d'employé est correctement associé.</span><span class="sxs-lookup"><span data-stu-id="f417d-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="f417d-194">Erreur lors de l'approbation des demandes de congé dans l'application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="f417d-195">Si vous recevez une erreur lors de la tentative d'approbation des demandes de congé dans l'application Teams, effectuez les étapes de dépannage suivantes :</span><span class="sxs-lookup"><span data-stu-id="f417d-195">If you receive an error when you're trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="f417d-196">Vérifiez que le compte que vous utilisez pour vous connecter à Microsoft Teams est le même que celui que vous utilisez pour accéder à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f417d-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="f417d-197">Vérifiez que vous êtes un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l'approbation de congé.</span><span class="sxs-lookup"><span data-stu-id="f417d-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="f417d-198">Pour plus d'informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f417d-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="f417d-199">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="f417d-199">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="f417d-200">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="f417d-200">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="f417d-201">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="f417d-201">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="f417d-202">L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="f417d-202">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="f417d-203">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="f417d-203">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="f417d-204">Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="f417d-204">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="f417d-205">Ces informations sont ensuite transmises à  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f417d-205">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="f417d-206">En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="f417d-206">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="f417d-207">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f417d-207">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f417d-208">Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="f417d-208">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="f417d-209">Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="f417d-209">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="f417d-210">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="f417d-210">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="f417d-211">Pour gérer les paramètres d’administration des applications dans Microsoft Teams, accédez au [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f417d-211">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="f417d-212">Microsoft Teams, Azure Event Grid et Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="f417d-212">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="f417d-213">Lorsque vous utilisez l'application Dynamics 365 Human Resources dans Microsoft Teams, certaines données client peuvent circuler en dehors de la zone géographique où le service Human Resources de votre client est déployé.</span><span class="sxs-lookup"><span data-stu-id="f417d-213">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="f417d-214">Dynamics 365 Human Resources transmet la demande de congé de l'employé et les détails de la tâche de flux de travail à Microsoft Azure Event Grid et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-214">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="f417d-215">Ces données peuvent être stockées dans Microsoft Azure Event Grid jusqu’à 24 heures et seront traitées aux États-Unis, elles sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="f417d-215">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f417d-216">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f417d-216">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="f417d-217">Lors d'une conversation avec le chat bot dans l'application Human Resources, le contenu de la conversation peut être stocké dans Azure Cosmos DB et transmis à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f417d-217">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="f417d-218">Ces données peuvent être stockées dans Azure Cosmos DB jusqu'à 24 heures et peuvent être traitées en dehors de la région géographique où le service Human Resources de votre client est déployé, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour amélioration de la formation ou du service.</span><span class="sxs-lookup"><span data-stu-id="f417d-218">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f417d-219">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="f417d-219">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="f417d-220">Pour limiter l'accès à l'application Human Resources dans Microsoft Teams pour votre organisation ou les utilisateurs au sein de votre organisation, consultez [Gérer les stratégies d'autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="f417d-220">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="f417d-221">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f417d-221">See also</span></span>

[<span data-ttu-id="f417d-222">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-222">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="f417d-223">Centre d’aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-223">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="f417d-224">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="f417d-224">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
