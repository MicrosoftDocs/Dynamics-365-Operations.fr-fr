---
title: Application Human Resources de Teams
description: Cette rubrique vous présente l'application Microsoft Dynamics 365 Human Resources de Microsoft Teams.
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
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388114"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="786d5-103">Application Human Resources de Teams</span><span class="sxs-lookup"><span data-stu-id="786d5-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="786d5-104">L'application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d'afficher les informations sur leur solde de congés dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="786d5-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="786d5-105">Les employés peuvent interagir avec un bot pour demander des informations.</span><span class="sxs-lookup"><span data-stu-id="786d5-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="786d5-106">L'onglet **Congés** fournit des informations plus détaillées.</span><span class="sxs-lookup"><span data-stu-id="786d5-106">The **Time off** tab provides more detailed information.</span></span>

![Bot d'application de congé Human Resources de Teams](./media/hr-admin-teams-leave-app-bot.png)

![Onglet Congés de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="786d5-109">Installer et configurer</span><span class="sxs-lookup"><span data-stu-id="786d5-109">Install and setup</span></span>

<span data-ttu-id="786d5-110">Vous pouvez trouver l'application Human Resources dans la boutique Teams.</span><span class="sxs-lookup"><span data-stu-id="786d5-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="786d5-111">Pour plus d'informations sur l'installation de l'application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="786d5-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="786d5-112">Pour plus d'informations sur la gestion des autorisations d'application dans Teams, consultez [Gérer les stratégies d'autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="786d5-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="786d5-113">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="786d5-113">Known issues</span></span>

| <span data-ttu-id="786d5-114">Sortie</span><span class="sxs-lookup"><span data-stu-id="786d5-114">Issue</span></span> | <span data-ttu-id="786d5-115">État</span><span class="sxs-lookup"><span data-stu-id="786d5-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="786d5-116">Le solde est incorrect lors de la soumission de congés pour une date future.</span><span class="sxs-lookup"><span data-stu-id="786d5-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="786d5-117">Les prévisions ne sont pas encore disponibles.</span><span class="sxs-lookup"><span data-stu-id="786d5-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="786d5-118">Le solde affiche la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="786d5-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="786d5-119">Lors de la réduction du nombre d'heures prises dans une demande existante, le **Solde restant** diminue au lieu d'augmenter.</span><span class="sxs-lookup"><span data-stu-id="786d5-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="786d5-120">Nous aborderons ce problème connu à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="786d5-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="786d5-121">L'affichage est incorrect, mais les montants corrects sont ajustés lors de la soumission.</span><span class="sxs-lookup"><span data-stu-id="786d5-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="786d5-122">Deux fiches **Prochains jours de congé** s'affichent aux mêmes dates.</span><span class="sxs-lookup"><span data-stu-id="786d5-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="786d5-123">Les fiches représentent des soumissions individuelles.</span><span class="sxs-lookup"><span data-stu-id="786d5-123">The cards represent individual submissions.</span></span> <span data-ttu-id="786d5-124">Nous continuerons de recueillir vos commentaires et de faire des ajustements.</span><span class="sxs-lookup"><span data-stu-id="786d5-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="786d5-125">Impossible d'annuler une demande **En cours de révision**.</span><span class="sxs-lookup"><span data-stu-id="786d5-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="786d5-126">Cette fonctionnalité n'est actuellement pas prise en charge et sera ajoutée dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="786d5-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="786d5-127">Les informations sur le solde sont calculées à partir d'aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="786d5-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="786d5-128">Actuellement, le système n'affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences.</span><span class="sxs-lookup"><span data-stu-id="786d5-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="786d5-129">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="786d5-129">Privacy notice</span></span>

<span data-ttu-id="786d5-130">Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l'utilisateur sont analysées pour comprendre la requête/l'intention sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="786d5-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="786d5-131">L'entrée de l'utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l'un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="786d5-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="786d5-132">Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS.</span><span class="sxs-lookup"><span data-stu-id="786d5-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="786d5-133">Le service LUIS permet de lever l'ambiguïté ou de comprendre l'intention de la saisie utilisateur (dans ce cas, l'intention est de rechercher des informations) et l'entité cible (dans ce cas, l'entité souhaitée est un compte nommé Contoso).</span><span class="sxs-lookup"><span data-stu-id="786d5-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="786d5-134">Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="786d5-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="786d5-135">En installant et en autorisant l'accès à l'utilisation du bot, vous acceptez d'autoriser le service LUIS et l'infrastructure de bot Azure à traiter l'intention derrière l'entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée.</span><span class="sxs-lookup"><span data-stu-id="786d5-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="786d5-136">Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="786d5-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="786d5-137">Alors que le service LUIS n'a accès qu'aux requêtes de l'utilisateur et n'est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l'utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d'autres données et un tel contenu de requête peut être envoyé au service LUIS et à l'infrastructure de bot Azure.</span><span class="sxs-lookup"><span data-stu-id="786d5-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="786d5-138">Le contenu des requêtes et des messages de l'utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n'est pas utilisé pour la formation ou l'amélioration des services.</span><span class="sxs-lookup"><span data-stu-id="786d5-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="786d5-139">Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services.</span><span class="sxs-lookup"><span data-stu-id="786d5-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="786d5-140">Pour gérer les paramètres d'administration des applications dans Microsoft Teams, allez dans le [centre d'administration Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="786d5-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="786d5-141">Voir également :</span><span class="sxs-lookup"><span data-stu-id="786d5-141">See also</span></span> 

[<span data-ttu-id="786d5-142">Télécharger er installer Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="786d5-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="786d5-143">Centre d'aide Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="786d5-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="786d5-144">Gérer les demandes de congé dans Teams</span><span class="sxs-lookup"><span data-stu-id="786d5-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

