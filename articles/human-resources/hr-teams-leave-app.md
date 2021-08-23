---
title: Gérer les demandes de congé dans Teams
description: Cette rubrique montre comment demander des congés dans l’application Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 94fa4dca7ff8372d4cf1aeee225e821574f4104048db5ad8a816be2bce496de8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725864"
---
# <a name="manage-leave-requests-in-teams"></a>Gérer les demandes de congés dans Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L’application Dynamics 365 Human Resources de Microsoft Teams vous permet de demander rapidement des congés et d’afficher les informations sur votre solde de congés directement dans Microsoft Teams. Vous pouvez interagir avec un robot pour demander des informations et lancer une demande de congé. L’onglet **Congés** fournit des informations plus détaillées. Vous pouvez également envoyer des informations aux personnes sur votre prochain congé dans Teams et dans les chats en dehors de l’application Human Resources.

## <a name="install-the-app"></a>Installer l’application

Vous pouvez trouver l’application Dynamics 365 Human Resources dans la boutique Teams.

1. Dans Microsoft Teams, accédez à la liste des applications.
 
2. Recherchez Dynamics 365 Human Resources, puis sélectionnez la vignette **Human Resources**.

3. Sélectionnez le bouton **Ajouter** pour installer l’application.

Si l’application ne vous connecte pas automatiquement, sélectionnez l’onglet **Paramètres** pour vous connecter.

> [!NOTE]
> Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles. 

Si vous avez accès à plusieurs instances de Human Resources, vous pouvez sélectionner l’environnement auquel vous souhaitez vous connecter dans l’onglet **Paramètres**.

> [!NOTE]
> L’application prend désormais en charge le rôle de sécurité Administrateur système.
 
## <a name="use-the-bot"></a>Utiliser le bot

Après l’installation de l’application, un message de bienvenue apparaît, vous informant des types d’actions que le bot peut entreprendre en votre nom.

> [!NOTE]
> Lors de la première interaction avec le bot, vous devrez peut-être vous connecter. Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.

Vous pouvez demander au bot d’effectuer ce qui suit :

- Afficher vos soldes de congés actuels. Par exemple, envoyez un message indiquant : « Afficher les soldes de congés ».

- Lancer une demande de congé. Par exemple, envoyez un message indiquant : « Prendre des congés » ou « Je souhaite prendre des congés les jeudi et vendredi prochains » pour être plus précis dans votre demande de congé pour le type de congé. 

  ![Démarrer une demande de congé dans le chat Teams.](./media/hr-teams-leave-app-initiate.png)

- Le bot conversationnel remplira une demande de congé pour vous. Sélectionner **Demander un congé** et modifiez les détails de votre demande.

   Si vous souhaitez envoyer des demandes de congé pour plusieurs types de congés pour la même date, sélectionnez l’option **Fractionner la journée avec** dans le menu **Plus d’options**. 

   Si vous sélectionnez un congé d’une demi-journée lorsque l’unité de demande de congé est exprimée en jours, vous pouvez spécifier si vous souhaitez demander un congé la matinée ou l’après-midi en sélectionnant l’option **Définition de la demi-journée** dans le menu **Plus d’options**.
   
   ![Définitions de la demi-journée.](./media/HalfDayDefinitions.png)

- Lorsque vous avez terminé de modifier les détails de votre demande de congé, sélectionnez **Envoyer** pour la soumettre pour approbation.

  ![Soumettre une demande de congé.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Gérer votre demandes dans Teams

L’onglet **Congés** vous permet de visualiser ce qui suit : 

- Les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier

- Les demandes de congé à venir

- Les demandes de congés

- Les brouillons de demande de congé
 
### <a name="create-a-new-request"></a>Créer une demande

1. Pour créer une demande de congé, sélectionnez **Nouvelle demande**.

2. Saisissez le ou les jours que vous souhaitez prendre, puis sélectionnez **Ajouter**.

   ![L’application de congé Human Resources de Teams ajoute les congés.](./media/TimeOffHours.png)

3. Le cas échéant, entrez un code motif. Saisissez également des commentaires et ajoutez des pièces jointes.

4. Sélectionnez l’option **Fractionner la journée avec** dans le menu **Plus d’options** si vous souhaitez envoyer plusieurs entrées de demande de congé pour la même date pour différents types de congés.

5. Sélectionnez l’option **Définition de la demi-journée** pour spécifier si vous souhaitez demander la matinée ou l’après-midi. Cette option est disponible lorsque l’unité de demande de congé est exprimée en jours et que le montant demandé est de 0,5 jour.

6. Lorsque vous avez terminé de saisir les informations, cliquez sur **Envoyer** pour envoyer la demande pour approbation. Vous pouvez également cliquer sur **Enregistrer comme brouillon** pour y revenir plus tard.

### <a name="manage-draft-requests"></a>Gérer les brouillons de demande

1. Sélectionnez l’onglet **Brouillons**.

2. Sélectionnez le crayon pour modifier la demande ou sélectionnez la corbeille pour supprimer la demande.

3. Apportez les modifications nécessaires. Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation. Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.
   
### <a name="respond-to-teams-notifications"></a>Répondre aux notifications Teams

Lorsque vous ou un collaborateur dont vous êtes l’approbateur soumettez une demande de congé, vous recevez une notification dans l’application Human Resources dans Teams. Vous pouvez sélectionner la notification pour l’afficher. Les notifications apparaissent également dans la zone **Conversation instantanée**.

Si vous êtes un approbateur, vous pouvez sélectionner **Approuver** ou **Refuser** dans la notification. Vous pouvez également fournir un message facultatif.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Envoyer des informations sur les congés à venir à vos collègues

Après avoir installé l’application Human Resources pour Teams, vous pouvez facilement envoyer des informations sur votre prochain congé à vos collègues dans les équipes ou les chats.

1. Dans une équipe ou dans une discussion dans Teams, sélectionnez le bouton Ressources humaines sous la fenêtre de discussion.

   ![Bouton Ressources humaines sous la fenêtre de discussion.](./media/hr-teams-leave-app-chat-button.png)

2. Sélectionnez la demande de congé que vous souhaitez partager. Si vous souhaitez partager un brouillon de demande de congé, sélectionnez **Brouillons** en premier.

Votre demande de congé s’affichera dans le chat.

Si vous avez partagé une demande provisoire, elle s’affichera comme brouillon.

## <a name="view-your-teams-leave-calendar"></a>Afficher le calendrier des congés de votre équipe

Si vous êtes un responsable avec des subordonnés directs, vous pouvez afficher les congés approuvés et en attente de votre équipe.

1. Dans l’application Human Resources dans Teams, sélectionnez **Congés**.

2. Sélectionnez **Calendrier d’équipe**. Le calendrier affiche les congés approuvés et en attente de vos subordonnés directs.

   > [!NOTE]
   > Si vous ne pouvez pas voir le calendrier de l’équipe, demandez à votre administrateur de l’activer. Pour plus d’informations, voir [Installation et configuration](hr-admin-teams-leave-app.md#install-and-setup).

## <a name="supported-languages"></a>Langues prises en charge

L’application Dynamics 365 Human Resources dans Teams prend en charge les langues suivantes :

| ID de paramètres régionaux | Langue |
| --- | --- |
| de-DE | Allemand (Allemagne) |
| es-ES | Espagnol (Espagne) |
| es-MX | Espagnol (Mexique) |
| fr-CA | Français (Canada) |
| fr-FR | Français (France) |
| it-IT | Italien (Italie) |
| nl-NL | Néerlandais (Pays-Bas) |
| pt-BR | Portugais (Brésil) |
| tr-TR | Turc (Turquie) |
| zh-CN | Chinois (simplifié) |

## <a name="troubleshooting"></a>Résolution des problèmes

Si vous rencontrez des problèmes pour vous connecter ou utiliser l’application Teams de Dynamics 365 Human Resources, essayez de suivre ces instructions de résolution des problèmes. Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l’assistance. Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Impossible de se connecter à l’application Human Resources dans Teams

Si vous ne pouvez pas vous connecter à l’application, il est possible que le compte que vous utilisez pour vous connecterà Microsoft Teams ne soit pas associé à un enregistrement d’employé dans Dynamics 365 Human Resources. Contactez votre administrateur système pour vous assurer que votre enregistrement d’employé est correctement associé.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>Impossible de trouver l'environnement Dynamics 365 Human Resources dans les paramètres

Si vous ne pouvez pas sélectionner le bon environnement Dynamics 365, l'enregistrement d'utilisateur n'a peut-être pas été correctement synchronisé. Contactez votre administrateur système pour recréer l'enregistrement d'utilisateur et l'associer aux informations d'identification de l'utilisateur. Essayez ensuite de vous connecter à l'application Human Resources pour Microsoft Teams après quelques minutes.

### <a name="translations-dont-display-correctly"></a>Les traductions ne s’affichent pas correctement

Si les traductions ne s’affichent pas comme prévu, assurez-vous que la langue que vous sélectionnez dans Teams correspond à la langue sélectionnée dans Human Resources **Options utilisateur**.

Dans Teams, regardez **Langue de l’application** dans **Réglages**.

![Paramètres Teams.](./media/hr-teams-leave-app-settings.png)

Dans Human Resources, sélectionnez **Réglages** puis **Options utilisateur**. Vérifiez que le champ **Langue** correspond au champ **Langue de l’application** dans Teams.

![Options utilisateur Human Resources.](./media/hr-teams-leave-app-user-options.png)

Si vous rencontrez toujours des problèmes de traduction, faites-le nous savoir. Pour plus d’informations, voir [Obtenir de l’aide sur les applications Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erreur lors de l’approbation des demandes de congé dans l’application Human Resources dans Teams

Si vous recevez une erreur lors de la tentative d’approbation des demandes de congé dans l’application Teams, essayez les étapes de dépannage suivantes :

1. Vérifiez que le compte que vous utilisez pour vous connecter à Microsoft Teams est le même que celui que vous utilisez pour accéder à Dynamics 365 Human Resources.

2. Vérifiez que vous êtes un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l’approbation de congé. Pour plus d’informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Les approbateurs de congé ne reçoivent pas les messages de discussion de Teams pour approuver les demandes de congé

1. Assurez-vous que les notifications sont activées pour l’environnement et l’utilisateur. Pour plus d’informations, consultez [Activer les notifications pour l’application Human Resources dans Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) et [Activer ou désactiver les notifications Teams pour les utilisateurs individuels](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Assurez-vous que les utilisateurs sont connectés à l’onglet **Chats** avec les mêmes informations d’identification utilisées pour approuver les demandes de congé. Utilisez les messages « déconnexion », puis « connexion » pour vous connecter avec les informations d’identification correctes.

3. Si le problème persiste, vérifiez l’état du traitement par lots du système Événements commerciaux en tant qu’administrateur système. S’il est en attente ou en cours d’exécution, revenez dans quelques minutes. Si le statut reste inchangé, enregistrez un ticket de support afin que notre équipe puisse vous aider à résoudre le problème.

## <a name="known-accessibility-issues"></a>Problèmes d’accessibilité connus

L’application Ressources humaines dans Teams présente les problèmes d’accessibilité suivants que nous travaillons à résoudre dans les versions futures.

| Sortie | Solution ou explication |
| --- | --- |
| Le zoom à 400 %% sur le bureau masque certains des boutons d’action de la vue. | Nous vous recommandons d’utiliser une loupe à la place jusqu’à ce que nous puissions prendre en charge ce niveau de zoom. |
| Sur l’onglet **Congé**, la voix off annonce une action sur un bouton lors de la lecture de l’en-tête de la grille des congés. | L’en-tête et les éléments de la grille sont regroupés par année et sont réductibles. La voix off interprète cela comme un élément exploitable, mais ce n’est pas le cas. |
| Sur l’onglet **Congé**, il y a un geste de balayage supplémentaire lors de la navigation vers **Code motif** dans une nouvelle demande. | Il n’y a aucun contrôle caché auquel la navigation par balayage tente d’accéder. |
| Sur l’onglet **Congé**, si vous faites glisser votre doigt pendant que le calendrier est ouvert, vous vous retrouvez hors du contrôle au lieu d’être en haut dans une nouvelle demande ou lors de la modification d’une demande. | Quand vous atteignez **Aller à aujourd’hui**, considérez que c’est la fin du contrôle et faites glisser votre doigt dans la direction inverse pour revenir en haut. |
| Sur l’onglet **Conversation instantanée**, le focus revient en haut lorsque vous entrez une date lors de l’utilisation de l’outil d’assistance ou de la navigation au clavier. | Appuyez Tabulation jusqu’à ce que vous atteigniez à nouveau votre zone de saisie. |

## <a name="privacy-notice"></a>Avis de confidentialité

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente. L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS). Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS. Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso). Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur. 

En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée. Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources. Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure. 

Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services. Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services. 

Pour gérer les paramètres d’administration des applications dans Microsoft Teams, accédez au [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid et Azure Cosmos DB

Lorsque vous utilisez l’application Dynamics 365 Human Resources dans Microsoft Teams, certaines données client peuvent circuler en dehors de la zone géographique où le service Human Resources de votre client est déployé.

Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de flux de travail à Microsoft Azure Event Grid et Microsoft Teams. Ces données peuvent être stockées dans Microsoft Azure Event Grid jusqu’à 24 heures et seront traitées aux États-Unis, elles sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services. Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Lors d’une conversation avec le chat bot dans l’application Human Resources, le contenu de la conversation peut être stocké dans Azure Cosmos DB et transmis à Microsoft Teams. Ces données peuvent être stockées dans Azure Cosmos DB jusqu’à 24 heures et peuvent être traitées en dehors de la région géographique où le service Human Resources de votre client est déployé, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour amélioration de la formation ou du service. Pour comprendre où vos données sont stockées dans Teams, veuillez consulter : [Emplacement des données dans Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Pour limiter l’accès à l’application Human Resources dans Microsoft Teams pour votre organisation ou les utilisateurs au sein de votre organisation, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Voir également :

[Télécharger et installer Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centre d’aide Microsoft Teams](https://support.office.com/teams)</br>
[Application Human Resources de Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
