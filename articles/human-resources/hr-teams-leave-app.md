---
title: Gérer les demandes de congé dans Teams
description: Cette rubrique montre comment demander des congés dans l'application Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 67501a1fa65493a1a23eb6176ece5be98d6e4659
ms.sourcegitcommit: 7fc0726c0a93ce6f4dafaad3232b4687f61cdc88
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3393006"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="206d7-103">Gérer les demandes de congé dans Teams</span><span class="sxs-lookup"><span data-stu-id="206d7-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="206d7-104">L'application Microsoft Dynamics 365 Human Resources de Microsoft Teams vous permet de demander rapidement des congés et d'afficher les informations sur votre solde de congés directement dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="206d7-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="206d7-105">Vous pouvez interagir avec un bot pour demander des informations.</span><span class="sxs-lookup"><span data-stu-id="206d7-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="206d7-106">L'onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="206d7-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="206d7-107">Installer l'application</span><span class="sxs-lookup"><span data-stu-id="206d7-107">Install the app</span></span>

<span data-ttu-id="206d7-108">Vous pouvez trouver l'application Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="206d7-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="206d7-109">Sélectionnez les ellipses dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="206d7-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Ellipses de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="206d7-111">Recherchez Dynamics 365 Human Resources, puis sélectionnez la vignette **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="206d7-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Vignette HR de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="206d7-113">Sélectionnez le bouton **Ajouter** pour installer l'application.</span><span class="sxs-lookup"><span data-stu-id="206d7-113">Select the **Add** button to install the app.</span></span>

   ![Installation de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="206d7-115">Si l'application ne vous connecte pas automatiquement, sélectionnez l'onglet **Paramètres** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="206d7-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Onglet Paramètres de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="206d7-117">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="206d7-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="206d7-118">Si vous avez accès à plusieurs instances de Human Resources, vous pouvez sélectionner l'environnement auquel vous souhaitez vous connecter dans l'onglet **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="206d7-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="206d7-119">L'application ne prend actuellement pas en charge le rôle de sécurité Administrateur système et affichera un message d'erreur si vous vous connectez avec un compte Administrateur système.</span><span class="sxs-lookup"><span data-stu-id="206d7-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="206d7-120">Pour vous connecter avec un autre compte, sur l'onglet **Paramètres**, sélectionnez le bouton **Changer de compte**, puis connectez-vous avec un compte d'utilisateur qui ne dispose pas des privilèges d'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="206d7-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="206d7-121">Utiliser le bot</span><span class="sxs-lookup"><span data-stu-id="206d7-121">Use the bot</span></span>

<span data-ttu-id="206d7-122">Après l'installation de l'application, un message de bienvenue apparaît, vous informant des types d'actions que le bot peut entreprendre en votre nom.</span><span class="sxs-lookup"><span data-stu-id="206d7-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Les équipes de Human Resources laissent un message de bienvenue au robot](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="206d7-124">Lors de la première interaction avec le bot, vous devrez peut-être vous connecter.</span><span class="sxs-lookup"><span data-stu-id="206d7-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="206d7-125">Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.</span><span class="sxs-lookup"><span data-stu-id="206d7-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="206d7-126">Vous pouvez demander au bot d'effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="206d7-126">You can ask the bot to:</span></span>

- <span data-ttu-id="206d7-127">Afficher les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier.</span><span class="sxs-lookup"><span data-stu-id="206d7-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![L'application de congé Human Resources de Teams affiche les soldes](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="206d7-129">Afficher des détails supplémentaires sur un type de congé spécifique.</span><span class="sxs-lookup"><span data-stu-id="206d7-129">Show additional details about a specific leave type.</span></span>

   ![L'application de congé Human Resources de Teams affiche les détails](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="206d7-131">Lancer une demande de congé.</span><span class="sxs-lookup"><span data-stu-id="206d7-131">Start a leave request for you.</span></span>

   ![L'application de congé Human Resources de Teams fait la demande de congé](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="206d7-133">Après avoir lancé une demande de congé, vous pouvez ajuster les jours directement sur la fiche ou sélectionner **Modifier les détails** pour ajouter des informations supplémentaires à votre demande.</span><span class="sxs-lookup"><span data-stu-id="206d7-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![L'application de congé Human Resources de Teams modifie la demande](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="206d7-135">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="206d7-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="206d7-136">Vous pouvez également taper **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="206d7-136">You can also type **Save as draft** to come back to it later.</span></span>

![L'application de congé Human Resources de Teams soumet la demande](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="206d7-138">Gérer votre demandes dans Teams</span><span class="sxs-lookup"><span data-stu-id="206d7-138">Manage your leave in Teams</span></span>

<span data-ttu-id="206d7-139">L'onglet **Congés** vous permet de visualiser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="206d7-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="206d7-140">Les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier</span><span class="sxs-lookup"><span data-stu-id="206d7-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="206d7-141">Les demandes de congé à venir</span><span class="sxs-lookup"><span data-stu-id="206d7-141">Upcoming leave requests</span></span>

- <span data-ttu-id="206d7-142">Les demandes de congés</span><span class="sxs-lookup"><span data-stu-id="206d7-142">Time-off requests</span></span>

- <span data-ttu-id="206d7-143">Les brouillons de demande de congé</span><span class="sxs-lookup"><span data-stu-id="206d7-143">Draft leave requests</span></span>

![Onglet Congés de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="206d7-145">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="206d7-145">Create a new request</span></span>

1. <span data-ttu-id="206d7-146">Pour créer une demande de congé, sélectionnez **Nouvelle demande**.</span><span class="sxs-lookup"><span data-stu-id="206d7-146">To create a new leave request, select **New request**.</span></span>

   ![Nouvelle demande de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="206d7-148">Saisissez le ou les jours que vous souhaitez prendre, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="206d7-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![L'application de congé Human Resources de Teams ajoute les congés](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="206d7-150">Le cas échéant, entrez un code motif.</span><span class="sxs-lookup"><span data-stu-id="206d7-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="206d7-151">Saisissez également des commentaires et ajoutez des pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="206d7-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="206d7-152">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="206d7-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="206d7-153">Vous pouvez également taper **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="206d7-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="206d7-154">Gérer les brouillons de demande</span><span class="sxs-lookup"><span data-stu-id="206d7-154">Manage draft requests</span></span>

1. <span data-ttu-id="206d7-155">Sélectionnez l'onglet **Brouillons**.</span><span class="sxs-lookup"><span data-stu-id="206d7-155">Select the **Drafts** tab.</span></span>

   ![Onglet Brouillons de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="206d7-157">Sélectionnez le crayon pour modifier la demande ou sélectionnez la corbeille pour supprimer la demande.</span><span class="sxs-lookup"><span data-stu-id="206d7-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="206d7-158">Apportez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="206d7-158">Make any necessary changes.</span></span> <span data-ttu-id="206d7-159">Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation.</span><span class="sxs-lookup"><span data-stu-id="206d7-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="206d7-160">Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.</span><span class="sxs-lookup"><span data-stu-id="206d7-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![L'application de congé Human Resources de Teams modifie le brouillon](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="206d7-162">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="206d7-162">Privacy notice</span></span>

<span data-ttu-id="206d7-163">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l'utilisateur sont analysées pour comprendre la requête/l'intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="206d7-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="206d7-164">L'entrée de l'utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l'un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="206d7-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="206d7-165">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="206d7-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="206d7-166">Le service LUIS permet de lever l'ambiguïté ou de comprendre l'intention de la saisie utilisateur (dans ce cas, l'intention est de rechercher des informations) et l'entité cible (dans ce cas, l'entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="206d7-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="206d7-167">Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="206d7-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="206d7-168">En installant et en autorisant l'accès à l'utilisation du bot, vous acceptez d'autoriser le service LUIS et l'infrastructure de bot Azure à traiter l'intention derrière l'entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="206d7-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="206d7-169">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="206d7-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="206d7-170">Alors que le service LUIS n'a accès qu'aux requêtes de l'utilisateur et n'est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l'utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d'autres données et un tel contenu de requête peut être envoyé au service LUIS et à l'infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="206d7-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="206d7-171">Le contenu des requêtes et des messages de l'utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n'est pas utilisé pour la formation ou l'amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="206d7-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="206d7-172">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="206d7-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="206d7-173">Pour gérer les paramètres d'administration des applications dans Microsoft Teams, allez dans le [centre d'administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="206d7-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="206d7-174">Voir également :</span><span class="sxs-lookup"><span data-stu-id="206d7-174">See also</span></span>

[<span data-ttu-id="206d7-175">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="206d7-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="206d7-176">Centre d'aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="206d7-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="206d7-177">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="206d7-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
