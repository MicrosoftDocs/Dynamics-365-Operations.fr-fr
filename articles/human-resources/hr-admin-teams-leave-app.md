---
title: Application Human Resources de Teams
description: Cette rubrique vous présente l’application Microsoft Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3926acd07a68f59682c18f4f7bc290dc1e21d0b6
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889738"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="0d7dc-103">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-103">Human Resources app in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0d7dc-104">L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="0d7dc-105">Les employés peuvent interagir avec un bot pour demander des informations.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="0d7dc-106">L’onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="0d7dc-107">En outre, il permet d’envoyer des informations aux personnes sur le prochain congé dans les équipes et dans les chats en dehors de l’application Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot d’application de congé Human Resources de Teams](./media/hr-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="0d7dc-111">Installer et configurer</span><span class="sxs-lookup"><span data-stu-id="0d7dc-111">Install and setup</span></span>

<span data-ttu-id="0d7dc-112">Vous pouvez trouver l’application Dynamics 365 Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-112">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span> <span data-ttu-id="0d7dc-113">Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="0d7dc-114">Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

<span data-ttu-id="0d7dc-115">Si vous souhaitez que vos utilisateurs voient le calendrier des congés et absences dans l’application, vous devez activer le **Calendrier des congés et absences dans Teams** dans la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-115">If you want your users to view the Leave and absence calendar in the app, you'll need to enable the **Leave and absence calendar in Teams** in Feature management.</span></span> <span data-ttu-id="0d7dc-116">Pour plus d’informations sur l’activation des fonctionnalités, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-116">For more information about enabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="0d7dc-117">Activer les notifications pour l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-117">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="0d7dc-118">Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-118">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Dynamics 365 Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="0d7dc-119">Seuls les utilisateurs connectés à Teams et utilisant l’application Dynamics 365 Human Resources Teams recevront des notifications.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-119">Only users who are signed into Teams and using the Dynamics 365 Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="0d7dc-120">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-120">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="0d7dc-121">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-121">Select **Links**.</span></span>

3. <span data-ttu-id="0d7dc-122">Sous **Configurer**, sélectionnez **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-122">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="0d7dc-123">Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-123">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Activer les notifications de l’application Teams dans les paramètres système](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="0d7dc-125">Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-125">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Activer les notifications Teams pour tous les utilisateurs](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="0d7dc-127">Activer ou désactiver les notifications Teams pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="0d7dc-127">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="0d7dc-128">Une fois que vous avez activé les notifications pour l’application Dynamics 365 Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-128">After you've enabled notifications for the Dynamics 365 Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="0d7dc-129">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="0d7dc-130">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-130">Select **Links**.</span></span>

3. <span data-ttu-id="0d7dc-131">Sous **Utilisateurs**, sélectionnez **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-131">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="0d7dc-132">Sélectionnez l’onglet **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-132">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="0d7dc-133">Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-133">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="0d7dc-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-135">Select **Save**.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="0d7dc-136">Langues prises en charge</span><span class="sxs-lookup"><span data-stu-id="0d7dc-136">Supported languages</span></span>

<span data-ttu-id="0d7dc-137">L’application Dynamics 365 Human Resources dans Teams prend en charge les langues suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d7dc-137">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="0d7dc-138">ID de paramètres régionaux</span><span class="sxs-lookup"><span data-stu-id="0d7dc-138">Locale ID</span></span> | <span data-ttu-id="0d7dc-139">Langue</span><span class="sxs-lookup"><span data-stu-id="0d7dc-139">Language</span></span> |
| --- | --- |
| <span data-ttu-id="0d7dc-140">de-DE</span><span class="sxs-lookup"><span data-stu-id="0d7dc-140">de-DE</span></span> | <span data-ttu-id="0d7dc-141">Allemand (Allemagne)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-141">German (Germany)</span></span> |
| <span data-ttu-id="0d7dc-142">es-ES</span><span class="sxs-lookup"><span data-stu-id="0d7dc-142">es-ES</span></span> | <span data-ttu-id="0d7dc-143">Espagnol (Espagne)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-143">Spanish (Spain)</span></span> |
| <span data-ttu-id="0d7dc-144">es-MX</span><span class="sxs-lookup"><span data-stu-id="0d7dc-144">es-MX</span></span> | <span data-ttu-id="0d7dc-145">Espagnol (Mexique)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-145">Spanish (Mexico)</span></span> |
| <span data-ttu-id="0d7dc-146">fr-CA</span><span class="sxs-lookup"><span data-stu-id="0d7dc-146">fr-CA</span></span> | <span data-ttu-id="0d7dc-147">Français (Canada)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-147">French (Canada)</span></span> |
| <span data-ttu-id="0d7dc-148">fr-FR</span><span class="sxs-lookup"><span data-stu-id="0d7dc-148">fr-FR</span></span> | <span data-ttu-id="0d7dc-149">Français (France)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-149">French (France)</span></span> |
| <span data-ttu-id="0d7dc-150">it-IT</span><span class="sxs-lookup"><span data-stu-id="0d7dc-150">it-IT</span></span> | <span data-ttu-id="0d7dc-151">Italien (Italie)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-151">Italian (Italy)</span></span> |
| <span data-ttu-id="0d7dc-152">nl-NL</span><span class="sxs-lookup"><span data-stu-id="0d7dc-152">nl-NL</span></span> | <span data-ttu-id="0d7dc-153">Néerlandais (Pays-Bas)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-153">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="0d7dc-154">pt-BR</span><span class="sxs-lookup"><span data-stu-id="0d7dc-154">pt-BR</span></span> | <span data-ttu-id="0d7dc-155">Portugais (Brésil)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-155">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="0d7dc-156">tr-TR</span><span class="sxs-lookup"><span data-stu-id="0d7dc-156">tr-TR</span></span> | <span data-ttu-id="0d7dc-157">Turc (Turquie)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-157">Turkish (Turkey)</span></span> |
| <span data-ttu-id="0d7dc-158">zh-CN</span><span class="sxs-lookup"><span data-stu-id="0d7dc-158">zh-CN</span></span> | <span data-ttu-id="0d7dc-159">Chinois (simplifié)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-159">Chinese (Simplified)</span></span> |

## <a name="notes"></a><span data-ttu-id="0d7dc-160">Notes</span><span class="sxs-lookup"><span data-stu-id="0d7dc-160">Notes</span></span>

<span data-ttu-id="0d7dc-161">Les éléments de travail suivants sont prévus pour les prochaines versions :</span><span class="sxs-lookup"><span data-stu-id="0d7dc-161">The following work items are slated for future releases:</span></span>

| <span data-ttu-id="0d7dc-162">Élément de travail</span><span class="sxs-lookup"><span data-stu-id="0d7dc-162">Work item</span></span> | <span data-ttu-id="0d7dc-163">Statut</span><span class="sxs-lookup"><span data-stu-id="0d7dc-163">Status</span></span> |
| --- | --- |
| <span data-ttu-id="0d7dc-164">Le solde est incorrect lors de la soumission de congés pour une date future.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-164">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="0d7dc-165">Les prévisions ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-165">Forecasting isn't yet available.</span></span> <span data-ttu-id="0d7dc-166">Le solde affiche la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-166">The balance displays for the current date.</span></span> |
| <span data-ttu-id="0d7dc-167">Impossible d’annuler une demande **En cours de révision**.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-167">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="0d7dc-168">Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-168">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="0d7dc-169">Les informations sur le solde sont calculées à partir d’aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-169">Balance information is calculated as of today.</span></span> | <span data-ttu-id="0d7dc-170">Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-170">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="0d7dc-171">Dépannage</span><span class="sxs-lookup"><span data-stu-id="0d7dc-171">Troubleshooting</span></span>

<span data-ttu-id="0d7dc-172">Si un utilisateur rencontre des problèmes pour se connecter ou utiliser l’application Teams de Human Resources, essayez de suivre ces instructions de dépannage.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-172">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="0d7dc-173">Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l’assistance.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-173">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="0d7dc-174">Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-174">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="0d7dc-175">Impossible de se connecter à l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-175">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="0d7dc-176">Si un utilisateur vous contacte car il ne peut pas se connecter à l’application, vérifiez qu’il dispose d’un enregistrement d’employé associé dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-176">If a user contacts you because they can't sign into the app, verify that they have an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="0d7dc-177">Erreur lors de l’approbation des demandes de congé dans l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-177">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="0d7dc-178">Si un utilisateur reçoit une erreur lors de la tentative d’approbation des demandes de congé dans l’application Teams, essayez les étapes de résolution des problèmes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d7dc-178">If a user receives an error while trying to approve,  leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="0d7dc-179">Vérifiez que leur compte Teams est le même que celui utilisé pour accéder à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-179">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="0d7dc-180">Vérifiez qu’il s’agit d’un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l’approbation de congé.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-180">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="0d7dc-181">Pour plus d’informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-181">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="0d7dc-182">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="0d7dc-182">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="0d7dc-183">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="0d7dc-183">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="0d7dc-184">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-184">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="0d7dc-185">L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-185">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="0d7dc-186">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-186">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="0d7dc-187">Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-187">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="0d7dc-188">Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-188">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="0d7dc-189">En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-189">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="0d7dc-190">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-190">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="0d7dc-191">Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-191">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="0d7dc-192">Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-192">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="0d7dc-193">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-193">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="0d7dc-194">Pour gérer les paramètres d’administration des applications dans Microsoft Teams, accédez au [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-194">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="0d7dc-195">Microsoft Teams, Azure Event Grid et Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="0d7dc-195">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="0d7dc-196">Lorsque vous utilisez l’application Dynamics 365 Human Resources dans Microsoft Teams, certaines données client peuvent circuler en dehors de la zone géographique où le service Human Resources de votre client est déployé.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-196">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="0d7dc-197">Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de flux de travail à Microsoft Azure Event Grid et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-197">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="0d7dc-198">Ces données peuvent être stockées dans Microsoft Azure Event Grid jusqu’à 24 heures et seront traitées aux États-Unis, elles sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-198">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="0d7dc-199">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-199">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="0d7dc-200">Lors d’une conversation avec le chat bot dans l’application Human Resources, le contenu de la conversation peut être stocké dans Azure Cosmos DB et transmis à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-200">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="0d7dc-201">Ces données peuvent être stockées dans Azure Cosmos DB jusqu’à 24 heures et peuvent être traitées en dehors de la région géographique où le service Human Resources de votre client est déployé, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour amélioration de la formation ou du service.</span><span class="sxs-lookup"><span data-stu-id="0d7dc-201">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="0d7dc-202">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-202">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="0d7dc-203">Pour limiter l’accès à l’application Human Resources dans Microsoft Teams pour votre organisation ou les utilisateurs au sein de votre organisation, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="0d7dc-203">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d7dc-204">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0d7dc-204">See also</span></span> 

[<span data-ttu-id="0d7dc-205">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-205">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="0d7dc-206">Centre d’aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-206">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="0d7dc-207">Gérer les demandes de congés dans Teams</span><span class="sxs-lookup"><span data-stu-id="0d7dc-207">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]