---
title: Module de conversation instantanée avec le module Power Virtual Agents
description: Cet article décrit la Commerce Chat avec le module Power Virtual Agents qui intègre Microsoft Power Virtual Agents aux sites web Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691059"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Module de conversation instantanée avec le module Power Virtual Agents

[!include [banner](includes/banner.md)]

Cet article décrit la Commerce Chat avec le module Power Virtual Agents qui intègre Microsoft Power Virtual Agents aux sites web Dynamics 365 Commerce.

La fonctionnalité Commerce Chat avec Power Virtual Agents permet aux clients d’e-commerce Dynamics 365 d’utiliser des capacités de chatbot Power Virtual Agents pour gérer leurs requêtes. Dès la version 10.0.30 de Dynamics 365 Commerce, cette fonctionnalité peut être intégrée aux sites Web d’e-commerce en utilisant la Commerce Chat avec le module Power Virtual Agents qui fait partie de la bibliothèque de modules Commerce.

La fonctionnalité Commerce Chat avec Power Virtual Agents aide les entreprises à atteindre les objectifs suivants :

- Accroître l’engagement personnalisé avec les clients pour aider à améliorer la fidélisation de la clientèle.
- Améliorer le service client grâce à l’intégration de chatbots en libre-service.
- Améliorer la satisfaction globale des clients pour aider à augmenter les ventes.

> [!NOTE]
> Pour en savoir plus sur les différences entre les applications Dynamics 365 Omnicanal pour Customer Service et Power Virtual Agents, voir [Présentation des modules Commerce Chat](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Prérequis pour utiliser Power Virtual Agents

Pour utiliser la fonctionnalité Commerce Chat avec Power Virtual Agents, vous devez d’abord créer un chatbot Power Virtual Agents pour votre site e-commerce. Pour obtenir des instructions, consultez [Créer un bot d’agent virtuel puissant](/power-virtual-agents/authoring-first-bot).

Après avoir configuré le chatbot, vous devez copier les valeurs de paramètres de chatbot **ID de bot** et **ID client** pour configurer l’expérience Commerce Chat. Pour plus d’informations sur la copie de ces valeurs, voir [Récupérer vos paramètres de bot Power Virtual Agents](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Configurer votre site d’e-commerce 

Une méthode recommandée pour implémenter l’expérience de chat pour votre site de commerce électronique consiste à ajouter le module Commerce Chat with Power Virtual Agents au fragment d’en-tête partagé utilisé sur les pages de votre site.

Pour ajouter le module de chat au fragment d'en-tête de votre site dans le générateur de site de Commerce, procédez comme suit.

1. Dans le générateur de site Commerce de votre site, allez à **Fragments**.
1. Cliquez sur **Nouveau**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le module **Commerce Chat avec Power Virtual Agents**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Dans la vue en plan, sélectionnez **Msdyn365 pva chat connector**.
1. Dans le volet propriétés à droite, procédez comme suit :

    1. Sous **Paramètres de bot**, dans le champ **URL CDN Chat Webchat Bot Framework**, laissez la valeur par défaut (par exemple, `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. Dans le champ **URL d’authentification Bot Framework Direct Line**, laissez la valeur par défaut (par exemple, `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. Dans le champ **ID de bot**, saisissez la valeur Power Virtual Agents **ID de bot** que vous avez copiée dans la section [Prérequis pour utiliser Power Virtual Agents](#prereq).
    1. Dans le champ **ID client**, saisissez la valeur **ID client** que vous avez copiée.

1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Aller à **Fragments**, et ouvrez le fragment d’en-tête de votre site.
1. Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton de suspension (**...**), puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le fragment de chat que vous avez créé au préalable, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.

## <a name="proactive-chat-parameters"></a>Paramètres de conversation instantanée proactive

Pour une liste complète des paramètres de configuration de conversation instantanée proactive, voir [Paramètres de conversation instantanée proactive du module Commerce Chat](chat-proactive-chat-parameters.md).

> [!NOTE]
> Actuellement, Power Virtual Agents ne prend pas en charge l’authentification Azure Active Directory B2C (Azure AD B2C). Seuls les appels anonymes Retail Cloud Scale Unit (RCSU) sont pris en charge pour obtenir la disponibilité des produits ou interagir avec d’autres API anonymes. Les appels aux API authentifiées via les chatbots Power Virtual Agents nécessitent une connexion client explicite.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des fonctionnalités de conversation instantanée Commerce](commerce-chat-overview.md)

[Commerce Chat avec le module Omnicanal pour Customer Service](commerce-chat-module.md)

[Paramètres de conversation instantanée proactive du module Commerce Chat](chat-proactive-chat-parameters.md)
