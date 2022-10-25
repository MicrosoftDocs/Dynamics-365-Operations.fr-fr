---
title: Commerce Chat avec le module Omnicanal pour Customer Service
description: Cet article décrit Commerce Chat avec le module Omnicanal pour Customer Service dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: 99e8b9d66a04390ab70fd1deff9f95fe28bdfae3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690314"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Commerce Chat avec le module Omnicanal pour Customer Service

[!include [banner](includes/banner.md)]

Cet article décrit Commerce Chat avec le module *Omnicanal pour Customer Service* dans Microsoft Dynamics 365 Commerce.

Dans la version 10.0.29 de Commerce, un nouveau Commerce Chat avec le module Omnicanal pour Customer Service a été ajouté à la bibliothèque de modules Commerce. La fonctionnalité de chat de Commerce offre aux clients du commerce électronique les fonctionnalités de chat de Dynamics 365 Omnicanal pour Customer Service, qui inclut une assistance en direct pour aider à répondre aux requêtes des clients, fournir un service client et faciliter les ventes pour les clients de Commerce.

La fonctionnalité de chat de Commerce permet aux détaillants d’atteindre ces objectifs :

- Accroître l’engagement personnalisé avec les clients pour aider à améliorer la fidélisation de la clientèle.
- Améliorer le service client grâce à l’intégration d’agents humains et de chatbots en libre-service.
- Aider les agents à acquérir de l’expérience grâce au profil client, aux commandes et aux données d’achat en temps réel qui stimulent les améliorations opérationnelles et l’engagement.
- Améliorer la satisfaction globale des clients pour aider à augmenter les ventes.

Les actions suivantes sont disponibles en tant que fonctionnalité de Commerce chat :

- Commerce Chat avec Omnicanal pour Customer Service
- L’ajout de **Commerce Call Center** sous forme d’onglet d’application dans l’expérience de l’agent dans Dynamics 365 Omnicanal pour Customer Service

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Prérequis pour Omnicanal pour Customer Service

Comme condition préalable, vous devez configurer le chat dans le widget d’administration de Omnicanal pour Customer Service et obtenir certains des paramètres pour configurer l’expérience de Commerce chat. Pour obtenir des instructions, voir [Configurer un canal de chat](/dynamics365/customer-service/set-up-chat-widget).

Après avoir configuré le chat dans le widget d’administration de Omnicanal pour Customer Service, vous obtiendrez un script qui ressemble à l’exemple suivant.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Copiez ce script, car vous aurez besoin des valeurs qu’il contient pour configurer le module de chat.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Champs obligatoires de Commerce Chat avec Omnicanal pour Customer Service

Le tableau suivant présente les valeurs du script du widget d’administration de Omnicanal pour Customer Service qui sont requises pour configurer le module Commerce Chat avec Omnicanal pour Customer Service.

| Propriété du widget | Description |
| ------------- |--------------|
| Source du script | La valeur de **src** dans le script du widget de chat. |
| Identifiant de application | La valeur de **data-app-id** dans le script du widget de chat. |
| Identifiant de l'organisation | La valeur de **data-org-id** dans le script du widget de chat. |
| URL de l'organisation | La valeur de **data-org-url** dans le script du widget de chat. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Configurez l’expérience de Commerce chat pour votre site de commerce électronique

Une méthode recommandée pour implémenter l’expérience de chat pour votre site de commerce électronique consiste à ajouter le module Commerce Chat with Omnicanal pour Customer Service au fragment d’en-tête partagé utilisé sur les pages de votre site de commerce électronique.

Pour ajouter le module de chat au fragment d'en-tête de votre site dans le générateur de site de Commerce, procédez comme suit.

1. Dans le générateur de site de votre site, allez à **Fragments**.
1. Cliquez sur **Nouveau**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le module **Commerce Chat avec Omnicanal pour Customer Service**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Dans la vue en plan, sélectionnez **Msdyn365 cs chat connector**.
1. Dans le volet **propriétés de Chat** à droite, procédez comme suit :

    1. Dans le champ **Source des scripts**, saisissez la valeur **src** que vous avez obtenue à partir du script Omnicanal pour Customer Service.
    1. Dans le champ **identifiant de l'application**, saisissez la valeur **data-app-id** que vous avez obtenue à partir du script Omnicanal pour Customer Service.
    1. Dans le champ **identifiant de l'organisation**, la valeur **data-org-id** que vous avez obtenue à partir du script Omnicanal pour Customer Service.
    1. Dans le champ **URL de l'organisation**, saisissez la valeur de **data-org-url** que vous avez obtenue à partir du script Omnicanal pour Customer Service.

    ![Création d’un fragment de module Commerce Chat dans le générateur de site de Commerce.](media/Commerce-chat-creating-new-fragment.png)

1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Aller à **Fragments**, et ouvrez le fragment d’en-tête de votre site.
1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le fragment de chat que vous avez créé au préalable, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

> [!NOTE]
> Pour une liste complète des paramètres de configuration, voir [Paramètres de conversation instantanée proactive du module Commerce Chat](chat-proactive-chat-parameters.md).

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Ajouter Commerce headquarters en tant qu’onglet d’application de Omnicanal pour Customer Service

Vous pouvez ajouter Commerce headquarters en tant qu’onglet d’application de Omnicanal pour Customer Service Les conseillers peuvent ensuite utiliser l’interface utilisateur de l’expérience d’agent de Omnicanal pour Customer Service pour accéder facilement au module Customer Service de Dynamics 365 Commerce qui contient des informations contextuelles sur le client ainsi que les informations sur leurs commandes. En outre, les agents du Customer Service peuvent passer de nouvelles commandes, initier des retours et vérifier les informations sur l’état des commandes.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Créer un nouvel onglet d’application qui charge Commerce headquarters dans un module iFrame 

Pour créer un nouvel onglet d’application qui charge Commerce headquarters dans un module iFrame, suivez les étapes suivantes.

1. Ouvrez [Power Apps Maker Portal](https://make.powerapps.com).
1. Dans le volet de navigation sur la gauche, sélectionnez **Apps**.
1. Sélectionnez **Centre d’administration du Customer Service**.
1. Allez à **Expérience d’agent**.
1. Pour les **Modèles d’onglets d’application**, sélectionnez **Gérer**.
1. Créer un nouvel onglet d’application du type **Site Web tiers**. Pour les instructions, voir [Gestion des modèles des onglets d'application](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. Dans **Paramètres**, dans le champ **Valeur** domaine du paramètre **url**, entrez l’URL suivante, où `<YourOrganizationHeadquartersURL>` et`<LegalEntityname>` sont remplacés par les valeurs appropriées. Omnicanal pour Customer Service lit **{AccountNumber}** depuis le contexte de chat. Par conséquent, laissez **{AccountNumber}** comme tel.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Laissez vide le champ **Value** du paramètre **data**.

![Création d’une application dans Dynamics 365 Omnicanal pour Customer Service.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Activer un nouvel onglet d’application pour les agents dans Dynamics 365 Omnicanal pour Customer Service

Pour activer un nouvel onglet d’application pour les agents dans Dynamics 365 Omnicanal pour Customer Service, suivez les étapes suivantes.
    
1. Ouvrez [Power Apps Maker Portal](https://make.powerapps.com).
1. Dans le volet de navigation sur la gauche, sélectionnez **Apps**.
1. Sélectionnez **Centre d’administration du Customer Service**.
1. Allez à **Service client\> Workstreams**.
1. Ouvrez le flux de travail que vous avez créé pour vos agents, puis, dans **Réglages avancés**, sélectionnez **Sessions par défaut**.
1. Dans **Onglets d’application**, sélectionnez **Ajouter un onglet d’application existant**, puis ajoutez le nouvel onglet d’application que vous avez créé précédemment. Cette étape garantit qu’un onglet d’application qui charge Commerce headquarters dans un module iFrame apparaîtra lorsqu’un agent reçoit un appel de chat entrant depuis votre site Web d'e-commerce.

> [!NOTE]
> Vous ne pouvez pas modifier le modèle de session de conversation instantanée par défaut dans le flux de travail. Par conséquent, vous souhaiterez peut-être créer un nouveau modèle ou dupliquer le modèle existant pour le mettre à jour. Pour plus d’informations, voir [Modèles associés avec flux de travail](/dynamics365/app-profile-manager/associate-templates).

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Ajouter des variables de contexte dans Dynamics 365 Omnicanal pour Customer Service

Pour ajouter des variables de contexte dans Dynamics 365 Omnicanal pour Customer Service, suivez les étapes suivantes.

1. Ouvrez [Power Apps Maker Portal](https://make.powerapps.com).
1. Dans le volet de navigation sur la gauche, sélectionnez **Apps**.
1. Sélectionnez **Centre d’administration du Customer Service**.
1. Allez à **Service client\> Workstreams**.
1. Ouvrez le flux de travail que vous avez créé pour vos agents, puis, dans **Réglages avancés**, allez à la section **Variable de contexte**.
1. Sélectionnez **Éditer**, puis ajoutez **AccountNumber** comme variable de contexte du type **texte**. Cette variable aidera Commerce headquarters à charger les informations client avec les numéros de compte correspondants.

> [!NOTE]
> Si vous souhaitez lire les adresses e-mail et les noms des utilisateurs connectés à partir d’un canal d'e-commerce, vous pouvez ajouter **Email** et **Nom** en tant que variables de contexte du type **texte**, en plus du variable de contexte **AccountNumber**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des fonctionnalités de conversation instantanée Commerce](commerce-chat-overview.md)

[Module de conversation instantanée avec le module Power Virtual Agents](chat-module-pva.md)

[Paramètres de conversation instantanée proactive du module Commerce Chat](chat-proactive-chat-parameters.md)
