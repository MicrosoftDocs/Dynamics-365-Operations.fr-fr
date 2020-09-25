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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776306"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="b8245-103">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="b8245-104">L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b8245-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="b8245-105">Les employés peuvent interagir avec un bot pour demander des informations.</span><span class="sxs-lookup"><span data-stu-id="b8245-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="b8245-106">L’onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="b8245-106">The **Time off** tab provides more detailed information.</span></span>

![Bot d’application de congé Human Resources de Teams](./media/hr-admin-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="b8245-109">Installer et configurer</span><span class="sxs-lookup"><span data-stu-id="b8245-109">Install and setup</span></span>

<span data-ttu-id="b8245-110">Vous pouvez trouver l’application Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="b8245-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="b8245-111">Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="b8245-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="b8245-112">Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="b8245-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="b8245-113">Activer les notifications pour l’application Human Resources dans Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="b8245-114">Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8245-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="b8245-115">Seuls les utilisateurs connectés à Teams et utilisant l’application Human Resources Teams recevront des notifications.</span><span class="sxs-lookup"><span data-stu-id="b8245-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="b8245-116">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="b8245-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b8245-117">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="b8245-117">Select **Links**.</span></span>

3. <span data-ttu-id="b8245-118">Sous **Configurer**, sélectionnez **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="b8245-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="b8245-119">Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b8245-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Activer les notifications de l’application Teams dans les paramètres système](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="b8245-121">Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.</span><span class="sxs-lookup"><span data-stu-id="b8245-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Activer les notifications Teams pour tous les utilisateurs](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="b8245-123">Activer ou désactiver les notifications Teams pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="b8245-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="b8245-124">Une fois que vous avez activé les notifications pour l’application Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="b8245-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="b8245-125">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="b8245-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b8245-126">Sélectionnez **Liens**.</span><span class="sxs-lookup"><span data-stu-id="b8245-126">Select **Links**.</span></span>

3. <span data-ttu-id="b8245-127">Sous **Utilisateurs**, sélectionnez **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="b8245-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="b8245-128">Sélectionnez l’onglet **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="b8245-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="b8245-129">Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b8245-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="b8245-131">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b8245-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b8245-132">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="b8245-132">Known issues</span></span>

| <span data-ttu-id="b8245-133">Sortie</span><span class="sxs-lookup"><span data-stu-id="b8245-133">Issue</span></span> | <span data-ttu-id="b8245-134">Statut</span><span class="sxs-lookup"><span data-stu-id="b8245-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="b8245-135">Le défilement horizontal ne fonctionne pas sur les téléphones Android</span><span class="sxs-lookup"><span data-stu-id="b8245-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="b8245-136">Le défilement horizontal n’est pas un problème sur les appareils iOS ou de bureau.</span><span class="sxs-lookup"><span data-stu-id="b8245-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="b8245-137">Nous travaillons sur un correctif pour Android.</span><span class="sxs-lookup"><span data-stu-id="b8245-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="b8245-138">Erreur : il y a un problème pour trouver un environnement auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="b8245-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="b8245-139">Vous pouvez recevoir cette erreur même si vous avez vérifié que l’utilisateur peut accéder à un ou plusieurs environnements Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8245-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="b8245-140">De plus, vous pouvez ne pas voir tous les environnements que vous attendez.</span><span class="sxs-lookup"><span data-stu-id="b8245-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="b8245-141">En attendant que nous résolvions ce problème, supprimez l’utilisateur, puis réimportez-le pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="b8245-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="b8245-142">Le solde est incorrect lors de la soumission de congés pour une date future.</span><span class="sxs-lookup"><span data-stu-id="b8245-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="b8245-143">Les prévisions ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="b8245-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="b8245-144">Le solde affiche la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="b8245-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="b8245-145">Impossible d’annuler une demande **En cours de révision**.</span><span class="sxs-lookup"><span data-stu-id="b8245-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="b8245-146">Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="b8245-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="b8245-147">Les informations sur le solde sont calculées à partir d’aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="b8245-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="b8245-148">Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences.</span><span class="sxs-lookup"><span data-stu-id="b8245-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="b8245-149">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="b8245-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="b8245-150">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="b8245-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="b8245-151">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="b8245-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="b8245-152">L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="b8245-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="b8245-153">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="b8245-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="b8245-154">Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="b8245-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="b8245-155">Ces informations sont ensuite transmises à  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b8245-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="b8245-156">En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="b8245-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="b8245-157">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b8245-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b8245-158">Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="b8245-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="b8245-159">Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="b8245-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="b8245-160">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="b8245-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="b8245-161">Pour gérer les paramètres d’administration des applications dans Microsoft Teams, allez dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b8245-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="b8245-162">Grille d’événements Microsoft Azure et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="b8245-163">Lorsque vous utilisez la fonction de notifications pour Dynamics 365 Human Resources dans Teams, certaines données client circuleront en dehors de la zone géographique où le service Human Resources de votre client est déployé.</span><span class="sxs-lookup"><span data-stu-id="b8245-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="b8245-164">Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de workflow à la Grille d’événements Microsoft Azure et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b8245-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="b8245-165">Ces données peuvent être stockées jusqu’à 24 heures et traitées aux États-Unis, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="b8245-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8245-166">Voir également :</span><span class="sxs-lookup"><span data-stu-id="b8245-166">See also</span></span> 

[<span data-ttu-id="b8245-167">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="b8245-168">Centre d’aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="b8245-169">Gérer les demandes de congés dans Teams</span><span class="sxs-lookup"><span data-stu-id="b8245-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

