---
title: Application Human Resources de Teams
description: Cette rubrique vous présente l’application Microsoft Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 33322b9b553076125695f257b201463e9d8275c6
ms.sourcegitcommit: e27510ba52623c801353eed4853f8c0aeea3bb2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3828912"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="66e95-103">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="66e95-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="66e95-104">L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66e95-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="66e95-105">Les employés peuvent interagir avec un bot pour demander des informations.</span><span class="sxs-lookup"><span data-stu-id="66e95-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="66e95-106">L'onglet **Congés** fournit des informations plus détaillées. De plus, ils peuvent envoyer aux gens des informations sur les congés à venir dans les équipes et les chats en dehors de l'application Human Resources.</span><span class="sxs-lookup"><span data-stu-id="66e95-106">The **Time off** tab provides more detailed information.In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot d’application de congé Human Resources de Teams](./media/hr-admin-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="66e95-110">Installer et configurer</span><span class="sxs-lookup"><span data-stu-id="66e95-110">Install and setup</span></span>

<span data-ttu-id="66e95-111">Vous pouvez trouver l’application Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="66e95-111">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="66e95-112">Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="66e95-112">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="66e95-113">Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="66e95-113">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="66e95-114">Activer les notifications pour l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="66e95-114">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="66e95-115">Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="66e95-115">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="66e95-116">Seuls les utilisateurs connectés à Teams et utilisant l’application Human Resources Teams recevront des notifications.</span><span class="sxs-lookup"><span data-stu-id="66e95-116">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="66e95-117">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="66e95-117">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="66e95-118">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="66e95-118">Select **Links**.</span></span>

3. <span data-ttu-id="66e95-119">Sous **Configurer**, sélectionnez **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="66e95-119">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="66e95-120">Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="66e95-120">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Activer les notifications de l’application Teams dans les paramètres système](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="66e95-122">Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.</span><span class="sxs-lookup"><span data-stu-id="66e95-122">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Activer les notifications Teams pour tous les utilisateurs](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="66e95-124">Activer ou désactiver les notifications Teams pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="66e95-124">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="66e95-125">Une fois que vous avez activé les notifications pour l’application Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="66e95-125">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="66e95-126">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="66e95-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="66e95-127">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="66e95-127">Select **Links**.</span></span>

3. <span data-ttu-id="66e95-128">Sous **Utilisateurs**, sélectionnez **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="66e95-128">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="66e95-129">Sélectionnez l’onglet **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="66e95-129">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="66e95-130">Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66e95-130">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="66e95-132">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="66e95-132">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="66e95-133">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="66e95-133">Known issues</span></span>

| <span data-ttu-id="66e95-134">Sortie</span><span class="sxs-lookup"><span data-stu-id="66e95-134">Issue</span></span> | <span data-ttu-id="66e95-135">Statut</span><span class="sxs-lookup"><span data-stu-id="66e95-135">Status</span></span> |
| --- | --- |
| <span data-ttu-id="66e95-136">Le défilement horizontal ne fonctionne pas sur les téléphones Android</span><span class="sxs-lookup"><span data-stu-id="66e95-136">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="66e95-137">Le défilement horizontal n’est pas un problème sur les appareils iOS ou de bureau.</span><span class="sxs-lookup"><span data-stu-id="66e95-137">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="66e95-138">Nous travaillons sur un correctif pour Android.</span><span class="sxs-lookup"><span data-stu-id="66e95-138">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="66e95-139">Le solde est incorrect lors de la soumission de congés pour une date future.</span><span class="sxs-lookup"><span data-stu-id="66e95-139">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="66e95-140">Les prévisions ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="66e95-140">Forecasting isn't yet available.</span></span> <span data-ttu-id="66e95-141">Le solde affiche la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="66e95-141">The balance displays for the current date.</span></span> |
| <span data-ttu-id="66e95-142">Impossible d’annuler une demande **En cours de révision**.</span><span class="sxs-lookup"><span data-stu-id="66e95-142">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="66e95-143">Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="66e95-143">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="66e95-144">Les informations sur le solde sont calculées à partir d’aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="66e95-144">Balance information is calculated as of today.</span></span> | <span data-ttu-id="66e95-145">Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences.</span><span class="sxs-lookup"><span data-stu-id="66e95-145">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="66e95-146">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="66e95-146">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="66e95-147">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="66e95-147">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="66e95-148">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="66e95-148">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="66e95-149">L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="66e95-149">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="66e95-150">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="66e95-150">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="66e95-151">Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="66e95-151">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="66e95-152">Ces informations sont ensuite transmises à  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="66e95-152">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="66e95-153">En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="66e95-153">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="66e95-154">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="66e95-154">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="66e95-155">Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="66e95-155">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="66e95-156">Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="66e95-156">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="66e95-157">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="66e95-157">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="66e95-158">Pour gérer les paramètres d’administration des applications dans Microsoft Teams, allez dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="66e95-158">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="66e95-159">Microsoft Teams, Azure Event Grid et Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="66e95-159">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="66e95-160">Lorsque vous utilisez l'application Dynamics 365 Human Resources dans Microsoft Teams, certaines données client peuvent circuler en dehors de la zone géographique où le service Human Resources de votre client est déployé.</span><span class="sxs-lookup"><span data-stu-id="66e95-160">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="66e95-161">Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de workflow à la Grille d’événements Microsoft Azure et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66e95-161">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="66e95-162">Ces données peuvent être stockées dans Microsoft Azure Event Grid jusqu’à 24 heures et seront traitées aux États-Unis, elles sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="66e95-162">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="66e95-163">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="66e95-163">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="66e95-164">Lors d'une conversation avec le chat bot dans l'application Human Resources, le contenu de la conversation peut être stocké dans Azure Cosmos DB et transmis à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66e95-164">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="66e95-165">Ces données peuvent être stockées dans Azure Cosmos DB jusqu'à 24 heures et peuvent être traitées en dehors de la région géographique où le service Human Resources de votre client est déployé, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour amélioration de la formation ou du service.</span><span class="sxs-lookup"><span data-stu-id="66e95-165">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="66e95-166">Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="66e95-166">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="66e95-167">Pour limiter l'accès à l'application Human Resources dans Microsoft Teams pour votre organisation ou les utilisateurs au sein de votre organisation, consultez [Gérer les stratégies d'autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="66e95-167">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="66e95-168">Voir également :</span><span class="sxs-lookup"><span data-stu-id="66e95-168">See also</span></span> 

[<span data-ttu-id="66e95-169">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66e95-169">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="66e95-170">Centre d’aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66e95-170">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="66e95-171">Gérer les demandes de congés dans Teams</span><span class="sxs-lookup"><span data-stu-id="66e95-171">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

