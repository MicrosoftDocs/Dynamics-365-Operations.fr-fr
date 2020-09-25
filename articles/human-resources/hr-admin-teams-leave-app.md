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
# <a name="human-resources-app-in-teams"></a>Application Human Resources de Teams

[!include [banner](includes/preview-feature.md)]

L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d’afficher les informations sur leur solde de congés dans Microsoft Teams. Les employés peuvent interagir avec un bot pour demander des informations. L’onglet **Congés** fournit des informations plus détaillées.

![Bot d’application de congé Human Resources de Teams](./media/hr-admin-teams-leave-app-bot.png)

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Installer et configurer

Vous pouvez trouver l’application Human Resources dans la boutique Teams. Pour plus d’informations sur l’installation de l’application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).

Pour plus d’informations sur la gestion des autorisations d’application dans Teams, consultez [Gérer les stratégies d’autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Activer les notifications pour l’application Human Resources dans Teams

Si vous souhaitez que les utilisateurs reçoivent des notifications de demande de congé dans l’application Teams, vous devez activer les notifications dans Human Resources.

>[!NOTE]
>Seuls les utilisateurs connectés à Teams et utilisant l’application Human Resources Teams recevront des notifications.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Configurer**, sélectionnez **Paramètres système**.

4. Sur l’onglet **Général**, définissez **Activer les notifications pour l’application Teams** sur **Oui**.

   ![Activer les notifications de l’application Teams dans les paramètres système](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Pour activer les notifications Teams pour tous les utilisateurs, sélectionnez **Oui** à l’invite.

   ![Activer les notifications Teams pour tous les utilisateurs](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Activer ou désactiver les notifications Teams pour les utilisateurs individuels

Une fois que vous avez activé les notifications pour l’application Human Resources de Teams, vous pouvez activer ou désactiver les notifications pour des utilisateurs individuels.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez **Liens**.

3. Sous **Utilisateurs**, sélectionnez **Options utilisateur**.

4. Sélectionnez l’onglet **Workflow**.

5. Définissez **Activer les notifications pour l’application Teams** sur **Oui** pour activer les notifications pour l’utilisateur ou **Non** pour désactiver les notifications pour l’utilisateur.

   ![Activer les notifications de l’application Teams dans l’onglet Workflow des options utilisateur](./media/hr-admin-teams-leave-app-notifications.png)

6. Sélectionnez **Enregistrer**.

## <a name="known-issues"></a>Problèmes connus

| Sortie | Statut |
| --- | --- |
| Le défilement horizontal ne fonctionne pas sur les téléphones Android | Le défilement horizontal n’est pas un problème sur les appareils iOS ou de bureau. Nous travaillons sur un correctif pour Android. |
| Erreur : il y a un problème pour trouver un environnement auquel se connecter. | Vous pouvez recevoir cette erreur même si vous avez vérifié que l’utilisateur peut accéder à un ou plusieurs environnements Human Resources. De plus, vous pouvez ne pas voir tous les environnements que vous attendez. En attendant que nous résolvions ce problème, supprimez l’utilisateur, puis réimportez-le pour résoudre le problème. |
| Le solde est incorrect lors de la soumission de congés pour une date future. | Les prévisions ne sont pas encore disponibles. Le solde affiche la date actuelle. |
| Impossible d’annuler une demande **En cours de révision**. | Cette fonctionnalité n’est actuellement pas prise en charge et sera ajoutée dans une prochaine version. |
| Les informations sur le solde sont calculées à partir d’aujourd’hui. | Actuellement, le système n’affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences. |

## <a name="privacy-notice"></a>Avis de confidentialité

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l’utilisateur sont analysées pour comprendre la requête/l’intention sous-jacente. L’entrée de l’utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l’un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS). Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS. Le service LUIS permet de lever l’ambiguïté ou de comprendre l’intention de la saisie utilisateur (dans ce cas, l’intention est de rechercher des informations) et l’entité cible (dans ce cas, l’entité souhaitée est un compte nommé Contoso). Ces informations sont ensuite transmises à  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l’utilisateur. 

En installant et en autorisant l’accès à l’utilisation du bot, vous acceptez d’autoriser le service LUIS et l’infrastructure de bot Azure à traiter l’intention derrière l’entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée. Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources. Alors que le service LUIS n’a accès qu’aux requêtes de l’utilisateur et n’est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l’utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d’autres données et un tel contenu de requête peut être envoyé au service LUIS et à l’infrastructure de bot Azure. 

Le contenu des requêtes et des messages de l’utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n’est pas utilisé pour la formation ou l’amélioration des services. Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services. 

Pour gérer les paramètres d’administration des applications dans Microsoft Teams, allez dans le [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a>Grille d’événements Microsoft Azure et Microsoft Teams

Lorsque vous utilisez la fonction de notifications pour Dynamics 365 Human Resources dans Teams, certaines données client circuleront en dehors de la zone géographique où le service Human Resources de votre client est déployé. Dynamics 365 Human Resources transmet la demande de congé de l’employé et les détails de la tâche de workflow à la Grille d’événements Microsoft Azure et Microsoft Teams. Ces données peuvent être stockées jusqu’à 24 heures et traitées aux États-Unis, sont chiffrées en transit et au repos, et ne sont pas utilisées par Microsoft ou ses sous-traitants pour la formation ou l’amélioration des services.

## <a name="see-also"></a>Voir également : 

[Télécharger er installer Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centre d’aide Microsoft Teams](https://support.office.com/teams)</br>
[Gérer les demandes de congés dans Teams](hr-teams-leave-app.md)

