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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c1cceb15d64215cb8d5c996df792e863d466f87d
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053561"
---
# <a name="human-resources-app-in-teams"></a>Application Human Resources de Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams. Les employés peuvent interagir avec un bot pour demander des informations. L’onglet **Congés** fournit des informations plus détaillées. En outre, il permet d’envoyer des informations aux personnes sur le prochain congé dans les équipes et dans les chats en dehors de l’application Human Resources.

![Bot d’application de congé Human Resources de Teams](./media/hr-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Carte de demande de congé de Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Installer et configurer

Vous pouvez trouver l’application Dynamics 365 Human Resources dans la boutique Teams. Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).

Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

Si vous souhaitez que vos utilisateurs voient le calendrier des congés et absences dans l’application, vous devez activer le **Calendrier des congés et absences dans Teams** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Activer les notifications pour l’application Human Resources dans Teams

Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Dynamics 365 Human Resources.

>[!NOTE]
>Seuls les utilisateurs connectés à Teams et utilisant l’application Dynamics 365 Human Resources Teams recevront des notifications.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Configurer**, sélectionnez **Paramètres système**.

4. Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.

   ![Activer les notifications de l’application Teams dans les paramètres système](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.

   ![Activer les notifications Teams pour tous les utilisateurs](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Activer ou désactiver les notifications Teams pour les utilisateurs individuels

Une fois que vous avez activé les notifications pour l’application Dynamics 365 Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Utilisateurs**, sélectionnez **Options utilisateur**.

4. Sélectionnez l’onglet **Workflow**.

5. Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur](./media/hr-admin-teams-leave-app-notifications.png)

6. Sélectionnez **Enregistrer**.

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

## <a name="notes"></a>Notes

Les éléments de travail suivants sont prévus pour les prochaines versions :

| Élément de travail | Statut |
| --- | --- |
| Le solde est incorrect lors de la soumission de congés pour une date future. | Les prévisions ne sont pas encore disponibles. Le solde affiche la date actuelle. |
| Impossible d’annuler une demande **En cours de révision**. | Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version. |
| Les informations sur le solde sont calculées à partir d’aujourd’hui. | Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences. |

## <a name="troubleshooting"></a>Dépannage

Si un utilisateur rencontre des problèmes pour se connecter ou utiliser l’application Teams de Human Resources, essayez de suivre ces instructions de dépannage. Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l’assistance. Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Impossible de se connecter à l’application Human Resources dans Teams

Si un utilisateur vous contacte car il ne peut pas se connecter à l’application, vérifiez qu’il dispose d’un enregistrement d’employé associé dans Human Resources.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erreur lors de l’approbation des demandes de congé dans l’application Human Resources dans Teams

Si un utilisateur reçoit une erreur lors de la tentative d’approbation des demandes de congé dans l’application Teams, essayez les étapes de résolution des problèmes suivantes :

1. Vérifiez que leur compte Teams est le même que celui utilisé pour accéder à Human Resources.

2. Vérifiez qu’il s’agit d’un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l’approbation de congé. Pour plus d’informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Les approbateurs de congé ne reçoivent pas les messages de discussion de Teams pour approuver les demandes de congé

1. Assurez-vous que les notifications sont activées pour l'environnement et l'utilisateur. Pour plus d’informations, consultez [Activer les notifications pour l’application Human Resources dans Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) et [Activer ou désactiver les notifications Teams pour les utilisateurs individuels](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Assurez-vous que les utilisateurs sont connectés à l'onglet **Chats** avec les mêmes informations d'identification utilisées pour approuver les demandes de congé. Utilisez les messages « déconnexion », puis « connexion » pour vous connecter avec les informations d'identification correctes.

3. Si le problème persiste, vérifiez l'état du traitement par lots du système Événements commerciaux en tant qu'administrateur système. S'il est en attente ou en cours d'exécution, revenez dans quelques minutes. Si le statut reste inchangé, enregistrez un ticket de support afin que notre équipe puisse vous aider à résoudre le problème.

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

[Télécharger er installer Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centre d’aide Microsoft Teams](https://support.office.com/teams)</br>
[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]