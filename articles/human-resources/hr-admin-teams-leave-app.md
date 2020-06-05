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
# <a name="human-resources-app-in-teams"></a>Application Human Resources de Teams

[!include [banner](includes/preview-feature.md)]

L'application Microsoft Dynamics 365 Human Resources de Microsoft Teams permet aux employés de demander rapidement des congés et d'afficher les informations sur leur solde de congés dans Microsoft Teams. Les employés peuvent interagir avec un bot pour demander des informations. L'onglet **Congés** fournit des informations plus détaillées.

![Bot d'application de congé Human Resources de Teams](./media/hr-admin-teams-leave-app-bot.png)

![Onglet Congés de l'application de congé Human Resources de Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Installer et configurer

Vous pouvez trouver l'application Human Resources dans la boutique Teams. Pour plus d'informations sur l'installation de l'application Teams, voir [Gérer les demandes de congé dans Teams](hr-teams-leave-app.md).

Pour plus d'informations sur la gestion des autorisations d'application dans Teams, consultez [Gérer les stratégies d'autorisation des applications dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="known-issues"></a>Problèmes connus

| Sortie | État |
| --- | --- |
| Le solde est incorrect lors de la soumission de congés pour une date future. | Les prévisions ne sont pas encore disponibles. Le solde affiche la date actuelle. |
| Lors de la réduction du nombre d'heures prises dans une demande existante, le **Solde restant** diminue au lieu d'augmenter. | Nous aborderons ce problème connu à l'avenir. L'affichage est incorrect, mais les montants corrects sont ajustés lors de la soumission. |
| Deux fiches **Prochains jours de congé** s'affichent aux mêmes dates. | Les fiches représentent des soumissions individuelles. Nous continuerons de recueillir vos commentaires et de faire des ajustements. |
| Impossible d'annuler une demande **En cours de révision**. | Cette fonctionnalité n'est actuellement pas prise en charge et sera ajoutée dans une prochaine version. |
| Les informations sur le solde sont calculées à partir d'aujourd'hui. | Actuellement, le système n'affiche pas les soldes à partir de la période de régularisation, même si elle est configurée dans les paramètres des congés et absences. |

## <a name="privacy-notice"></a>Avis de confidentialité

Avec le bot Dynamics 365 Human Resources de Microsoft Teams, les entrées de texte de l'utilisateur sont analysées pour comprendre la requête/l'intention sous-jacente. L'entrée de l'utilisateur telle que « Rechercher le compte Contoso » est acheminée vers l'un des services cognitifs de Microsoft appelé Language Understanding Intelligent Service (LUIS). Cliquez  [ici](https://www.luis.ai/) pour en savoir plus sur LUIS. Le service LUIS permet de lever l'ambiguïté ou de comprendre l'intention de la saisie utilisateur (dans ce cas, l'intention est de rechercher des informations) et l'entité cible (dans ce cas, l'entité souhaitée est un compte nommé Contoso). Ces informations sont ensuite transmises à la  [structure de bot Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft qui interagit avec les données de Dynamics 365 Human Resources et récupère les informations souhaitées pour la requête de l'utilisateur. 

En installant et en autorisant l'accès à l'utilisation du bot, vous acceptez d'autoriser le service LUIS et l'infrastructure de bot Azure à traiter l'intention derrière l'entrée, ce qui se traduit par une expérience utilisateur conversationnelle améliorée. Le service LUIS et la structure de bot Azure peuvent avoir des niveaux de conformité différents par rapport à Dynamics 365 Human Resources. Alors que le service LUIS n'a accès qu'aux requêtes de l'utilisateur et n'est pas conçu pour être connecté aux données ou au compte Dynamics 365 Human Resources de l'utilisateur, un utilisateur du bot Dynamics 365 Human Resources peut entrer volontairement une requête contenant des données client, des données personnelles ou d'autres données et un tel contenu de requête peut être envoyé au service LUIS et à l'infrastructure de bot Azure. 

Le contenu des requêtes et des messages de l'utilisateur est conservé dans le système LUIS pendant 30 jours maximum, il est chiffré au repos et n'est pas utilisé pour la formation ou l'amélioration des services. Cliquez  [ici](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) pour en savoir plus sur Cognitive Services. 

Pour gérer les paramètres d'administration des applications dans Microsoft Teams, allez dans le [centre d'administration Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Voir également : 

[Télécharger er installer Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centre d'aide Microsoft Teams](https://support.office.com/teams)</br>
[Gérer les demandes de congé dans Teams](hr-teams-leave-app.md)

