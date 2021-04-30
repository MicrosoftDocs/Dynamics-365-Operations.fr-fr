---
title: Gérer les demandes de congé dans Teams
description: Cette rubrique montre comment demander des congés dans l’application Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 48bf6f7997d6159077419bcd05d27fd711c8fb4b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891028"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="5331b-103">Gérer les demandes de congés dans Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5331b-104">L’application Dynamics 365 Human Resources de Microsoft Teams vous permet de demander rapidement des congés et d’afficher les informations sur votre solde de congés directement dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="5331b-105">Vous pouvez interagir avec un robot pour demander des informations et lancer une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="5331b-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="5331b-106">L’onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="5331b-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="5331b-107">Vous pouvez également envoyer des informations aux personnes sur votre prochain congé dans Teams et dans les chats en dehors de l’application Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5331b-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="5331b-108">Installer l’application</span><span class="sxs-lookup"><span data-stu-id="5331b-108">Install the app</span></span>

<span data-ttu-id="5331b-109">Vous pouvez trouver l’application Dynamics 365 Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="5331b-110">Sélectionnez les ellipses dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Ellipses de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="5331b-112">Recherchez Dynamics 365 Human Resources, puis sélectionnez la vignette **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="5331b-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Vignette HR de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="5331b-114">Sélectionnez le bouton **Ajouter** pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="5331b-114">Select the **Add** button to install the app.</span></span>

   ![Installation de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="5331b-116">Si l’application ne vous connecte pas automatiquement, sélectionnez l’onglet **Paramètres** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="5331b-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Onglet Paramètres de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="5331b-118">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="5331b-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="5331b-119">Si vous avez accès à plusieurs instances de Human Resources, vous pouvez sélectionner l’environnement auquel vous souhaitez vous connecter dans l’onglet **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5331b-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="5331b-120">L’application prend désormais en charge le rôle de sécurité Administrateur système.</span><span class="sxs-lookup"><span data-stu-id="5331b-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="5331b-121">Utiliser le bot</span><span class="sxs-lookup"><span data-stu-id="5331b-121">Use the bot</span></span>

<span data-ttu-id="5331b-122">Après l’installation de l’application, un message de bienvenue apparaît, vous informant des types d’actions que le bot peut entreprendre en votre nom.</span><span class="sxs-lookup"><span data-stu-id="5331b-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Les équipes de Human Resources laissent un message de bienvenue au robot](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="5331b-124">Lors de la première interaction avec le bot, vous devrez peut-être vous connecter.</span><span class="sxs-lookup"><span data-stu-id="5331b-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="5331b-125">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="5331b-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="5331b-126">Vous pouvez demander au bot d’effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="5331b-126">You can ask the bot to:</span></span>

- <span data-ttu-id="5331b-127">Lancer une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="5331b-127">Start a leave request for you.</span></span>

  ![Démarrer une demande de congé dans le chat Teams](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="5331b-129">Le bot conversationnel remplira une demande de congé pour vous.</span><span class="sxs-lookup"><span data-stu-id="5331b-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="5331b-130">Sélectionner **Demander un congé** et modifiez les détails de votre demande.</span><span class="sxs-lookup"><span data-stu-id="5331b-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Modifier les détails de la demande de congés](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="5331b-132">Lorsque vous avez terminé de modifier les détails de votre demande de congé, sélectionnez **Envoyer** pour la soumettre pour approbation.</span><span class="sxs-lookup"><span data-stu-id="5331b-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Soumettre une demande de congé](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="5331b-134">Gérer votre demandes dans Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-134">Manage your leave in Teams</span></span>

<span data-ttu-id="5331b-135">L’onglet **Congés** vous permet de visualiser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="5331b-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="5331b-136">Les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier</span><span class="sxs-lookup"><span data-stu-id="5331b-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="5331b-137">Les demandes de congé à venir</span><span class="sxs-lookup"><span data-stu-id="5331b-137">Upcoming leave requests</span></span>

- <span data-ttu-id="5331b-138">Les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="5331b-138">Time-off requests</span></span>

- <span data-ttu-id="5331b-139">Les brouillons de demande de congé</span><span class="sxs-lookup"><span data-stu-id="5331b-139">Draft leave requests</span></span>

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="5331b-141">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="5331b-141">Create a new request</span></span>

1. <span data-ttu-id="5331b-142">Pour créer une demande de congé, sélectionnez **Nouvelle demande**.</span><span class="sxs-lookup"><span data-stu-id="5331b-142">To create a new leave request, select **New request**.</span></span>

   ![Nouvelle demande de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="5331b-144">Saisissez le ou les jours que vous souhaitez prendre, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5331b-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![L’application de congé Human Resources de Teams ajoute les congés](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="5331b-146">Le cas échéant, entrez un code motif.</span><span class="sxs-lookup"><span data-stu-id="5331b-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="5331b-147">Saisissez également des commentaires et ajoutez des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="5331b-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="5331b-148">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="5331b-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5331b-149">Vous pouvez également taper **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="5331b-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="5331b-150">Gérer les brouillons de demande</span><span class="sxs-lookup"><span data-stu-id="5331b-150">Manage draft requests</span></span>

1. <span data-ttu-id="5331b-151">Sélectionnez l’onglet **Brouillons**.</span><span class="sxs-lookup"><span data-stu-id="5331b-151">Select the **Drafts** tab.</span></span>

   ![Onglet Brouillons de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="5331b-153">Sélectionnez le crayon pour modifier la demande ou sélectionnez la corbeille pour supprimer la demande.</span><span class="sxs-lookup"><span data-stu-id="5331b-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="5331b-154">Apportez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="5331b-154">Make any necessary changes.</span></span> <span data-ttu-id="5331b-155">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="5331b-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5331b-156">Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="5331b-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![L’application de congé Human Resources de Teams modifie le brouillon](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="5331b-158">Répondre aux notifications Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-158">Respond to Teams notifications</span></span>

<span data-ttu-id="5331b-159">Lorsque vous ou un collaborateur dont vous êtes l’approbateur soumettez une demande de congé, vous recevez une notification dans l’application Human Resources dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="5331b-160">Vous pouvez sélectionner la notification pour l’afficher.</span><span class="sxs-lookup"><span data-stu-id="5331b-160">You can select the notification to view it.</span></span> <span data-ttu-id="5331b-161">Les notifications apparaissent également dans la zone **Conversation instantanée**.</span><span class="sxs-lookup"><span data-stu-id="5331b-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="5331b-162">Si vous êtes un approbateur, vous pouvez sélectionner **Approuver** ou **Refuser** dans la notification.</span><span class="sxs-lookup"><span data-stu-id="5331b-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="5331b-163">Vous pouvez également fournir un message facultatif.</span><span class="sxs-lookup"><span data-stu-id="5331b-163">You can also provide an optional message.</span></span>

![Laisser une notification de demande dans l’applications Teams Human Resources](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="5331b-165">Envoyer des informations sur les congés à venir à vos collègues</span><span class="sxs-lookup"><span data-stu-id="5331b-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="5331b-166">Après avoir installé l’application Human Resources pour Teams, vous pouvez facilement envoyer des informations sur votre prochain congé à vos collègues dans les équipes ou les chats.</span><span class="sxs-lookup"><span data-stu-id="5331b-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="5331b-167">Dans une équipe ou dans une discussion dans Teams, sélectionnez le bouton Ressources humaines sous la fenêtre de discussion.</span><span class="sxs-lookup"><span data-stu-id="5331b-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Bouton Ressources humaines sous la fenêtre de discussion](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="5331b-169">Sélectionnez la demande de congé que vous souhaitez partager.</span><span class="sxs-lookup"><span data-stu-id="5331b-169">Select the leave request you want to share.</span></span> <span data-ttu-id="5331b-170">Si vous souhaitez partager un brouillon de demande de congé, sélectionnez **Brouillons** en premier.</span><span class="sxs-lookup"><span data-stu-id="5331b-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Sélectionner une demande de congé à venir à partager](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="5331b-172">Votre demande de congé s’affichera dans le chat.</span><span class="sxs-lookup"><span data-stu-id="5331b-172">Your leave request will display in the chat.</span></span>

![Carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="5331b-174">Si vous avez partagé une demande de brouillon, elle s’affichera comme brouillon :</span><span class="sxs-lookup"><span data-stu-id="5331b-174">If you shared a draft request, it will display as a draft:</span></span>

![Brouillon de carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="5331b-176">Afficher votre calendrier de congés d’équipe</span><span class="sxs-lookup"><span data-stu-id="5331b-176">View your team's leave calendar</span></span>

<span data-ttu-id="5331b-177">Si vous êtes un responsable avec des subordonnés directs, vous pouvez afficher les congés approuvés et en attente de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="5331b-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="5331b-178">Dans l’application Human Resources dans Teams, sélectionnez **Congés**.</span><span class="sxs-lookup"><span data-stu-id="5331b-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="5331b-179">Sélectionnez **Calendrier d’équipe**.</span><span class="sxs-lookup"><span data-stu-id="5331b-179">Select **Team calendar**.</span></span> <span data-ttu-id="5331b-180">Le calendrier affiche les congés approuvés et en attente de vos subordonnés directs.</span><span class="sxs-lookup"><span data-stu-id="5331b-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Afficher le calendrier de l’application Human Resources de Teams](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="5331b-182">Si vous ne pouvez pas voir le calendrier de l’équipe, demandez à votre administrateur de l’activer.</span><span class="sxs-lookup"><span data-stu-id="5331b-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="5331b-183">Pour plus d’informations, voir [Installation et configuration](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="5331b-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="5331b-184">Langues prises en charge</span><span class="sxs-lookup"><span data-stu-id="5331b-184">Supported languages</span></span>

<span data-ttu-id="5331b-185">L’application Dynamics 365 Human Resources dans Teams prend en charge les langues suivantes :</span><span class="sxs-lookup"><span data-stu-id="5331b-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="5331b-186">ID de paramètres régionaux</span><span class="sxs-lookup"><span data-stu-id="5331b-186">Locale ID</span></span> | <span data-ttu-id="5331b-187">Langue</span><span class="sxs-lookup"><span data-stu-id="5331b-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="5331b-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="5331b-188">de-DE</span></span> | <span data-ttu-id="5331b-189">Allemand (Allemagne)</span><span class="sxs-lookup"><span data-stu-id="5331b-189">German (Germany)</span></span> |
| <span data-ttu-id="5331b-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="5331b-190">es-ES</span></span> | <span data-ttu-id="5331b-191">Espagnol (Espagne)</span><span class="sxs-lookup"><span data-stu-id="5331b-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="5331b-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="5331b-192">es-MX</span></span> | <span data-ttu-id="5331b-193">Espagnol (Mexique)</span><span class="sxs-lookup"><span data-stu-id="5331b-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="5331b-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="5331b-194">fr-CA</span></span> | <span data-ttu-id="5331b-195">Français (Canada)</span><span class="sxs-lookup"><span data-stu-id="5331b-195">French (Canada)</span></span> |
| <span data-ttu-id="5331b-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="5331b-196">fr-FR</span></span> | <span data-ttu-id="5331b-197">Français (France)</span><span class="sxs-lookup"><span data-stu-id="5331b-197">French (France)</span></span> |
| <span data-ttu-id="5331b-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="5331b-198">it-IT</span></span> | <span data-ttu-id="5331b-199">Italien (Italie)</span><span class="sxs-lookup"><span data-stu-id="5331b-199">Italian (Italy)</span></span> |
| <span data-ttu-id="5331b-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="5331b-200">nl-NL</span></span> | <span data-ttu-id="5331b-201">Néerlandais (Pays-Bas)</span><span class="sxs-lookup"><span data-stu-id="5331b-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="5331b-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="5331b-202">pt-BR</span></span> | <span data-ttu-id="5331b-203">Portugais (Brésil)</span><span class="sxs-lookup"><span data-stu-id="5331b-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="5331b-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="5331b-204">tr-TR</span></span> | <span data-ttu-id="5331b-205">Turc (Turquie)</span><span class="sxs-lookup"><span data-stu-id="5331b-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="5331b-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="5331b-206">zh-CN</span></span> | <span data-ttu-id="5331b-207">Chinois (simplifié)</span><span class="sxs-lookup"><span data-stu-id="5331b-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="5331b-208">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="5331b-208">Troubleshooting</span></span>

<span data-ttu-id="5331b-209">Si vous rencontrez des problèmes pour vous connecter ou utiliser l’application Teams de Dynamics 365 Human Resources, essayez de suivre ces instructions de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="5331b-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="5331b-210">Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l’assistance.</span><span class="sxs-lookup"><span data-stu-id="5331b-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="5331b-211">Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="5331b-211">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="5331b-212">Impossible de se connecter à l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="5331b-213">Si vous ne pouvez pas vous connecter à l’application, il est possible que le compte que vous utilisez pour vous connecterà Microsoft Teams ne soit pas associé à un enregistrement d’employé dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5331b-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5331b-214">Contactez votre administrateur système pour vous assurer que votre enregistrement d’employé est correctement associé.</span><span class="sxs-lookup"><span data-stu-id="5331b-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="5331b-215">Les traductions ne s’affichent pas correctement</span><span class="sxs-lookup"><span data-stu-id="5331b-215">Translations don't display correctly</span></span>

<span data-ttu-id="5331b-216">Si les traductions ne s’affichent pas comme prévu, assurez-vous que la langue que vous sélectionnez dans Teams correspond à la langue sélectionnée dans Human Resources **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="5331b-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="5331b-217">Dans Teams, regardez **Langue de l’application** dans **Réglages**.</span><span class="sxs-lookup"><span data-stu-id="5331b-217">In Teams, look at **App language** in **Settings**.</span></span>

![Paramètres Teams](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="5331b-219">Dans Human Resources, sélectionnez **Réglages** puis **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="5331b-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="5331b-220">Vérifiez que le champ **Langue** correspond au champ **Langue de l’application** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Options utilisateur Human Resources](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="5331b-222">Si vous rencontrez toujours des problèmes de traduction, faites-le nous savoir.</span><span class="sxs-lookup"><span data-stu-id="5331b-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="5331b-223">Pour plus d’informations, voir [Obtenir de l’aide sur les applications Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="5331b-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="5331b-224">Erreur lors de l’approbation des demandes de congé dans l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="5331b-225">Si vous recevez une erreur lors de la tentative d’approbation des demandes de congé dans l’application Teams, essayez les étapes de dépannage suivantes :</span><span class="sxs-lookup"><span data-stu-id="5331b-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="5331b-226">Vérifiez que le compte que vous utilisez pour vous connecter à Microsoft Teams est le même que celui que vous utilisez pour accéder à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5331b-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="5331b-227">Vérifiez que vous êtes un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l’approbation de congé.</span><span class="sxs-lookup"><span data-stu-id="5331b-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="5331b-228">Pour plus d’informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="5331b-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="5331b-229">Problèmes d’accessibilité connus</span><span class="sxs-lookup"><span data-stu-id="5331b-229">Known accessibility issues</span></span>

<span data-ttu-id="5331b-230">L’application Ressources humaines dans Teams présente les problèmes d’accessibilité suivants que nous travaillons à résoudre dans les versions futures.</span><span class="sxs-lookup"><span data-stu-id="5331b-230">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="5331b-231">Sortie</span><span class="sxs-lookup"><span data-stu-id="5331b-231">Issue</span></span> | <span data-ttu-id="5331b-232">Solution ou explication</span><span class="sxs-lookup"><span data-stu-id="5331b-232">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="5331b-233">Le zoom à 400 %% sur le bureau masque certains des boutons d’action de la vue.</span><span class="sxs-lookup"><span data-stu-id="5331b-233">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="5331b-234">Nous vous recommandons d’utiliser une loupe à la place jusqu’à ce que nous puissions prendre en charge ce niveau de zoom.</span><span class="sxs-lookup"><span data-stu-id="5331b-234">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="5331b-235">Sur l’onglet **Congé**, la voix off annonce une action sur un bouton lors de la lecture de l’en-tête de la grille des congés.</span><span class="sxs-lookup"><span data-stu-id="5331b-235">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="5331b-236">L’en-tête et les éléments de la grille sont regroupés par année et sont réductibles.</span><span class="sxs-lookup"><span data-stu-id="5331b-236">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="5331b-237">La voix off interprète cela comme un élément exploitable, mais ce n’est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="5331b-237">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="5331b-238">Sur l’onglet **Congé**, il y a un geste de balayage supplémentaire lors de la navigation vers **Code motif** dans une nouvelle demande.</span><span class="sxs-lookup"><span data-stu-id="5331b-238">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="5331b-239">Il n’y a aucun contrôle caché auquel la navigation par balayage tente d’accéder.</span><span class="sxs-lookup"><span data-stu-id="5331b-239">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="5331b-240">Sur l’onglet **Congé**, si vous faites glisser votre doigt pendant que le calendrier est ouvert, vous vous retrouvez hors du contrôle au lieu d’être en haut dans une nouvelle demande ou lors de la modification d’une demande.</span><span class="sxs-lookup"><span data-stu-id="5331b-240">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="5331b-241">Quand vous atteignez **Aller à aujourd’hui**, considérez que c’est la fin du contrôle et faites glisser votre doigt dans la direction inverse pour revenir en haut.</span><span class="sxs-lookup"><span data-stu-id="5331b-241">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="5331b-242">Sur l’onglet **Conversation instantanée**, le focus revient en haut lorsque vous entrez une date lors de l’utilisation de l’outil d’assistance ou de la navigation au clavier.</span><span class="sxs-lookup"><span data-stu-id="5331b-242">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="5331b-243">Appuyez Tabulation jusqu’à ce que vous atteigniez à nouveau votre zone de saisie.</span><span class="sxs-lookup"><span data-stu-id="5331b-243">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="5331b-244">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5331b-244">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="5331b-245">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="5331b-245">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="5331b-246">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="5331b-246">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="5331b-247">L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="5331b-247">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="5331b-248">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="5331b-248">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="5331b-249">Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="5331b-249">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="5331b-250">Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5331b-250">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="5331b-251">En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="5331b-251">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="5331b-252">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5331b-252">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5331b-253">Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="5331b-253">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="5331b-254">Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="5331b-254">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="5331b-255">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="5331b-255">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="5331b-256">Pour gérer les paramètres d’administration des applications dans Microsoft Teams, accédez au [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5331b-256">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="5331b-257">Microsoft Teams, Azure Event Grid et Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="5331b-257">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="5331b-258">Lorsque vous utilisez l’application Dynamics 365 Human Resources dans Microsoft Teams, certaines données client peuvent circuler en dehors de la zone géographique où le service Human Resources de votre client est déployé.</span><span class="sxs-lookup"><span data-stu-id="5331b-258">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="5331b-259">Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de flux de travail à Microsoft Azure Event Grid et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-259">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="5331b-260">Ces données peuvent être stockées dans Microsoft Azure Event Grid jusqu’à 24 heures et seront traitées aux États-Unis, elles sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="5331b-260">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="5331b-261">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="5331b-261">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="5331b-262">Lors d’une conversation avec le chat bot dans l’application Human Resources, le contenu de la conversation peut être stocké dans Azure Cosmos DB et transmis à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5331b-262">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="5331b-263">Ces données peuvent être stockées dans Azure Cosmos DB jusqu’à 24 heures et peuvent être traitées en dehors de la région géographique où le service Human Resources de votre client est déployé, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour amélioration de la formation ou du service.</span><span class="sxs-lookup"><span data-stu-id="5331b-263">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="5331b-264">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="5331b-264">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="5331b-265">Pour limiter l’accès à l’application Human Resources dans Microsoft Teams pour votre organisation ou les utilisateurs au sein de votre organisation, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="5331b-265">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="5331b-266">Voir également :</span><span class="sxs-lookup"><span data-stu-id="5331b-266">See also</span></span>

[<span data-ttu-id="5331b-267">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-267">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="5331b-268">Centre d’aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-268">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="5331b-269">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="5331b-269">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]