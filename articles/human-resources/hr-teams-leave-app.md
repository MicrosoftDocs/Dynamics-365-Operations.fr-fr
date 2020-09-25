---
title: Gérer les demandes de congé dans Teams
description: Cette rubrique montre comment demander des congés dans l’application Dynamics 365 Human Resources de Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 0fbf44fe35af3147fd5fb478b6cbfc5a5d0b109d
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766758"
---
# <a name="manage-leave-requests-in-teams"></a>Gérer les demandes de congé dans Teams

[!include [banner](includes/preview-feature.md)]

L’application Microsoft Dynamics 365 Human Resources de Microsoft Teams vous permet de demander rapidement des congés et d’afficher les informations sur votre solde de congés directement dans Microsoft Teams. Vous pouvez interagir avec un bot pour demander des informations. L’onglet **Congés** fournit des informations plus détaillées.

## <a name="install-the-app"></a>Installer l’application

Vous pouvez trouver l’application Human Resources dans la boutique Teams.

1. Sélectionnez les ellipses dans Microsoft Teams.

   ![Ellipses de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. Recherchez Dynamics 365 Human Resources, puis sélectionnez la vignette **Human Resources**.

   ![Vignette HR de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. Sélectionnez le bouton **Ajouter** pour installer l’application.

   ![Installation de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-in-store.png)

Si l’application ne vous connecte pas automatiquement, sélectionnez l’onglet **Paramètres** pour vous connecter.

![Onglet Paramètres de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles. 

Si vous avez accès à plusieurs instances de Human Resources, vous pouvez sélectionner l’environnement auquel vous souhaitez vous connecter dans l’onglet **Paramètres**.

> [!WARNING]
> L’application ne prend actuellement pas en charge le rôle de sécurité Administrateur système et affichera un message d’erreur si vous vous connectez avec un compte Administrateur système. Pour vous connecter avec un autre compte, sur l’onglet **Paramètres**, sélectionnez le bouton **Changer de compte**, puis connectez-vous avec un compte d’utilisateur qui ne dispose pas des privilèges d’administrateur système.
 
## <a name="use-the-bot"></a>Utiliser le bot

Après l’installation de l’application, un message de bienvenue apparaît, vous informant des types d’actions que le bot peut entreprendre en votre nom.

![Les équipes de Human Resources laissent un message de bienvenue au robot](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> Lors de la première interaction avec le bot, vous devrez peut-être vous connecter. Si vous ne voyez pas de boîte de dialogue de connexion, vérifiez les paramètres de votre navigateur pour autoriser les fenêtres contextuelles.

Vous pouvez demander au bot d’effectuer ce qui suit :

- Afficher les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier.

   ![L’application de congé Human Resources de Teams affiche les soldes](./media/hr-teams-leave-app-bot-balances.png)
 
- Afficher des détails supplémentaires sur un type de congé spécifique.

   ![L’application de congé Human Resources de Teams affiche les détails](./media/hr-teams-leave-app-bot-details.png)

- Lancer une demande de congé.

   ![L’application de congé Human Resources de Teams fait la demande de congé](./media/hr-teams-leave-app-bot-request.png)
 
Après avoir lancé une demande de congé, vous pouvez ajuster les jours directement dans la carte.

![L’application de congé Human Resources de Teams modifie la demande](./media/hr-teams-leave-app-bot-edit.png)
 
Lorsque vous avez terminé de saisir les informations, sélectionnez **Soumettre** pour soumettre la demande pour approbation. Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.

![L’application de congé Human Resources de Teams soumet la demande](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Gérer votre demandes dans Teams

L’onglet **Congés** vous permet de visualiser ce qui suit :

- Les informations sur le solde des congés pour chaque type de congé dont vous pouvez bénéficier

- Les demandes de congé à venir

- Les demandes de congés

- Les brouillons de demande de congé

![Onglet Congés de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Créer une demande

1. Pour créer une demande de congé, sélectionnez **Nouvelle demande**.

   ![Nouvelle demande de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Saisissez le ou les jours que vous souhaitez prendre, puis sélectionnez **Ajouter**.

   ![L’application de congé Human Resources de Teams ajoute les congés](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Le cas échéant, entrez un code motif. Saisissez également des commentaires et ajoutez des pièces jointes.

4. Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation. Vous pouvez également taper **Enregistrer comme brouillon** pour y revenir plus tard.

### <a name="manage-draft-requests"></a>Gérer les brouillons de demande

1. Sélectionnez l’onglet **Brouillons**.

   ![Onglet Brouillons de l’application de congé Human Resources de Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. Sélectionnez le crayon pour modifier la demande ou sélectionnez la corbeille pour supprimer la demande.

3. Apportez les modifications nécessaires. Lorsque vous avez terminé de saisir les informations, saisissez **Soumettre** pour soumettre la demande pour approbation. Vous pouvez également sélectionner **Enregistrer comme brouillon** pour y revenir plus tard.

   ![L’application de congé Human Resources de Teams modifie le brouillon](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="teams-notifications"></a>Notifications Teams

Lorsque vous ou un collaborateur dont vous êtes l’approbateur soumettez une demande de congé, vous recevez une notification dans l’application Human Resources dans Teams. Vous pouvez sélectionner la notification pour l’afficher. Les notifications apparaissent également dans la zone **Conversation instantanée**.

Si vous êtes un approbateur, vous pouvez sélectionner **Approuver** ou **Refuser** dans la notification. Vous pouvez également fournir un message facultatif.

![Laisser une notification de demande dans l’applications Teams Human Resources](./media/hr-teams-leave-app-notification.png)

## <a name="view-your-teams-leave-calendar"></a>Afficher votre calendrier de congés d’équipe

Si vous êtes un responsable avec des subordonnés directs, vous pouvez afficher les congés approuvés et en attente de votre équipe.

1. Dans l’application Human Resources dans Teams, sélectionnez **Congés**.

2. Sélectionnez **Calendrier d’équipe**.

   ![Afficher le calendrier de l’application Human Resources de Teams](./media/hr-teams-leave-app-view-calendar.png)

Le calendrier affiche les congés approuvés et en attente de vos subordonnés directs.

![Calendrier des congés de l’application Human Resources de Teams](./media/hr-teams-leave-app-calendar.png)

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
[Application Human Resources de Teams](hr-admin-teams-leave-app.md)
