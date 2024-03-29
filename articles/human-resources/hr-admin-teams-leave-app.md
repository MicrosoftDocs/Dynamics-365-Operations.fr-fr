---
title: Application Human Resources de Teams
description: Cet article vous présente l’application Microsoft Dynamics 365 Human Resources de Microsoft Teams.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d29802bdf3411c93f20d710e1f26e541e5022d57
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812184"
---
# <a name="human-resources-app-in-teams"></a>Application Human Resources de Teams


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams. Les employés peuvent interagir avec un bot pour demander des informations. L’onglet **Congés** fournit des informations plus détaillées. En outre, il permet d’envoyer des informations aux personnes sur le prochain congé dans les équipes et dans les chats en dehors de l’application Human Resources.

![Bot d’application de congé Human Resources de Teams.](./media/hr-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams.](./media/hr-teams-leave-app-timeoff-tab.png)

![Carte de demande de congé de Human Resources.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Installer et configurer

Vous pouvez trouver l’application Dynamics 365 Human Resources dans la boutique Teams. Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).

Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

Si vous souhaitez que vos utilisateurs voient le calendrier des congés et absences dans l’application, vous devez activer le **Calendrier des congés et absences dans Teams** dans la gestion des fonctionnalités. Pour plus d’informations sur l’activation des fonctionnalités, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="update-app"></a>Mettre à jour l’application
>[!NOTE]
> À compter du 20 décembre 2021, les services de bot de l’application Human Resources hébergés dans l’abonné Microsoft seront mis hors service. Il n’y aura aucun impact pour une extension à jour (version 1.1.5) qui est disponible pour l’installation. L’impact principal sera sur l’extension obsolète (version 1.1.4). Le bot de discussion instantanée dans cette version cessera de fonctionner. L’onglet **Congés** continuera à fonctionner dans les deux extensions.

Pour la version 1.1.4, le bot de conversation instantanée cessera de répondre à tout message. Par example, **Connexion**, **Voir les soldes**, et **Voir congés**. L’application doit être mise à jour manuellement vers la dernière version. Pour plus d’informations, voir la rubrique [Mettre à jour les applications dans Microsoft Teams](/MicrosoftTeams/apps-update-experience).

Pour mettre à jour vers la version 1.1.5, procédez comme suit :
1. Dans Microsoft Teams, aller à **Applications**.
2. Recherchez l’application **Human Resources**.
3. Sélectionnez **Mettre à niveau**.

Vous pouvez vérifier la version de l’application Human Resources soit en allant sur l’onglet **À propos** ou à la section **Application personnelle**. 

![Onglet **À propos** de Human Resources.](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Activer les notifications pour l’application Human Resources dans Teams

Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Dynamics 365 Human Resources.

>[!NOTE]
>Seuls les utilisateurs connectés à Teams et utilisant l’application Dynamics 365 Human Resources Teams recevront des notifications.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Configurer**, sélectionnez **Paramètres système**.

4. Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.

   ![Activer les notifications de l’application Teams dans les paramètres système.](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.

   ![Activer les notifications Teams pour tous les utilisateurs.](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Activer ou désactiver les notifications Teams pour les utilisateurs individuels

Une fois que vous avez activé les notifications pour l’application Dynamics 365 Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Utilisateurs**, sélectionnez **Options utilisateur**.

4. Sélectionnez l’onglet **Workflow**.

5. Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur.](./media/hr-admin-teams-leave-app-notifications.png)

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
| tr-TR | Turc (Türkiye) |
| zh-CN | Chinois (simplifié) |

## <a name="notes"></a>Notes

Les éléments de travail suivants sont prévus pour les prochaines versions :

| Élément de travail | Statut |
| --- | --- |
| Le solde est incorrect lors de la soumission de congés pour une date future. | Les prévisions ne sont pas encore disponibles. Le solde affiche la date actuelle. |
| Impossible d’annuler une demande **En cours de révision**. | Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version. |
| Les informations sur le solde sont calculées à partir d’aujourd’hui. | Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée sur la page **Paramètres des congés et absences**. |

## <a name="troubleshooting"></a>Résolution des problèmes

Si un utilisateur rencontre des problèmes pour se connecter ou utiliser l’application Teams de Human Resources, essayez de suivre ces instructions de dépannage. Si vous rencontrez toujours des problèmes après la résolution des problèmes, contactez l’assistance. Pour plus d’informations, voir [Obtenir de l’aide](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>S’assurer que l’application Teams Human Resources est à jour
Si vous rencontrez des problèmes avec l’application Teams Human Resources, vous devez vérifier que vous exécutez bien la dernière version. La version minimale prise en charge est la 1.1.5. Pour obtenir des instructions sur la mise à jour d’une application Teams, consultez la [documentation Teams](/MicrosoftTeams/apps-update-experience).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Impossible de se connecter à l’application Human Resources dans Teams

Si un utilisateur vous contacte car il ne peut pas se connecter à l’application, vérifiez qu’il dispose d’un enregistrement d’employé associé dans Human Resources.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erreur lors de l’approbation des demandes de congé dans l’application Human Resources dans Teams

Si un utilisateur reçoit une erreur au moment de la tentative d’approbation des demandes de congé dans l’application Teams, essayez les étapes de résolution des problèmes suivantes :

1. Vérifiez que leur compte Teams est le même que celui utilisé pour accéder à Human Resources.

2. Vérifiez qu’il s’agit d’un approbateur valide pour la demande en vérifiant les paramètres de flux de travail pour l’approbation de congé. Pour plus d’informations sur les workflows de demande de congé, voir [Créer un workflow de demande de congé](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Les approbateurs de congé ne reçoivent pas les messages de discussion de Teams pour approuver les demandes de congé

1. Assurez-vous que les notifications sont activées pour l’environnement et l’utilisateur. Pour plus d’informations, consultez [Activer les notifications pour l’application Human Resources dans Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) et [Activer ou désactiver les notifications Teams pour les utilisateurs individuels](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Assurez-vous que les utilisateurs sont connectés à l’onglet **Chats** avec les mêmes informations d’identification utilisées pour approuver les demandes de congé. Utilisez les messages « déconnexion », puis « connexion » pour vous connecter avec les informations d’identification correctes.

3. Si le problème persiste, vérifiez l’état du traitement par lots du **système Événements commerciaux** en tant qu’administrateur système. S’il est **en attente** ou **en cours d’exécution**, revenez dans quelques minutes. Si le statut reste inchangé, enregistrez un ticket de support afin que notre équipe puisse résoudre le problème.

## <a name="privacy-notice"></a>Avis de confidentialité

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente. L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS). Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS. Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso). Ces informations sont ensuite transmises à la  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur.

En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée. Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources. Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à Azure Bot Framework. 

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
