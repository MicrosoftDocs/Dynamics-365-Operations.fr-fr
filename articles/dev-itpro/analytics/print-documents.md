---
title: Impression dans les applications Finance and Operations
description: "Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez imprimer des documents à l'aide d'une imprimante locale ou d'un périphérique réseau connecté. Cet article fournit une vue d'ensemble de la manière dont les documents sont imprimés."
author: TJVass
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: IT Pro, Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 30a418e6c49849369f0a0e3ffa28f31b9b88b7e7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="printing-in-finance-and-operations-applications"></a>Impression dans les applications Finance and Operations

[!INCLUDE [banner](../includes/banner.md)]

Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez imprimer des documents à l'aide d'une imprimante locale ou d'un périphérique réseau connecté. Cet article fournit une vue d'ensemble de la manière dont les documents sont imprimés.

<a name="printing-overview"></a>Vue d'ensemble de l'impression
-----------------

Microsoft Dynamics 365 for Finance and Operations fournit des services et des applications client intégrés qui facilitent la génération, l'enregistrement, et la distribution des documents qui prennent en charge les activités commerciales. Dans Finance and Operations, vous pouvez imprimer des documents à l'aide d'une imprimante locale ou d'un périphérique réseau connecté. En outre, vous pouvez exporter les pages et états Finance and Operations directement vers le client, comme les fichiers PDF ou les documents Microsoft Office. Enfin, la charge de travail distribuée vous permet d'imprimer des documents commerciaux directement depuis un appareil mobile à l'aide des ressources réseau. Bien que les besoins d'impression puissent varier, tous les secteurs doivent généralement créer des copies papier des documents commerciaux à l'aide de Finance and Operations. L'impression de documents sur des périphériques réseau à partir d'applications hébergées présente un ensemble unique de défis. Voici quelques exemples :

-   Les pilotes d'impression peuvent ne pas être disponibles sur l'appareil de l'utilisateur.
-   L'appareil de l'utilisateur peut ne pas être connecté au réseau d'entreprise.

L'utilisation d'un hôte dédié et après quelques étapes faciles, les administrateurs système peuvent configurer des déploiements afin que les utilisateurs puissent imprimer directement depuis les applications de l'entreprise sur les périphériques réseau.

### <a name="printing-scenarios-in-finance-and-operations-applications"></a>Scénarios d'impression dans les applications Finance and Operations

Le tableau suivant décrit les trois principaux scénarios d'impression dans les applications Finance and Operations.

| Scénario                        | Objectif                                                      | Solution                                                                                                            |
|---------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| 1. Impression de ce que vous voyez        | Imprimez ce qui est affiché dans le navigateur.             | Une version « imprimable » de la page Web est générée pour le navigateur.                                             |
| 2. Impression interactive         | Imprimez un document de précision sur un périphérique connecté localement. | Vous pouvez exporter une version PDF de l'état et la télécharger dans le navigateur.                                          |
| 3. Impression sur un périphérique réseau | Envoyez un document de précision sur un périphérique d'impression de domaine.     | Un document de précision est envoyé à une application client qui s'exécute sur un serveur hébergé dans le domaine du client. |

Comme la solution varie, selon le scénario, les applications Finance and Operations fournissent des services et des outils intégrés pour aider les utilisateurs à atteindre leurs objectifs :

-   Le **Scénario 1** est pris en charge par le rendu du client HTML5 du navigateur.
-   Le **Scénario 2** utilise des applications client et des services Microsoft Office 365.
-   Le **Scénario 3** requiert la prise en charge des applications client et des services hébergés dans Microsoft Azure.

Outre la plateforme déployée dans l'abonnement Azure, les applications Finances and Operations fournissent aux clients une application Azuré intégrée qui les aide à utiliser plus facilement les périphériques hébergés dans le domaine pour l'impression de documents.

## <a name="service-overview"></a>Vue d'ensemble du service
Pendant que les documents qui sont produits par les applications hébergées attendent d'être imprimés sur un périphérique réseau connecté, ils sont stockés dans le stockage des objets blobs Azure. L'[Agent d'acheminement de document](install-document-routing-agent.md) utilise l'authentification Azure pour établir un canal sécurisé vers les services Azure. **Séquence d'exécution**

1.  L'état est généré par Microsoft SQL Server Reporting Services (SSRS) et stocké dans le stockage des objets blobs Azure. Les paramètres d'imprimante associée sont enregistrés avec le document.
2.  L'agent d'acheminement de document interroge la file d'attente d'Azure Service Bus pour les tâches actives.
3.  Le document est téléchargé par l'agent d'acheminement de document et mis en attente dans l'imprimante réseau.

La solution basée sur le client permet aux clients de gérer l'échelle de leurs besoins d'impression. Les clients qui ont des charges de travail d'impression volumineuses peuvent installer plusieurs agents d'acheminement de document pour augmenter le nombre d'opérations d'impression simultanées. Sinon, certains clients nécessitent très peu d'installations de l'agent d'acheminement de document pour gérer leurs besoins d'impression prévus.

### <a name="service-components-for-network-printing"></a>Composants de service pour l'impression réseau

Les diagramme suivant présente les composants de base permettant la prise en charge d'opérations d'impression réseau. [![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png) Notez qu'une seule imprimante peut être enregistrée avec plusieurs agents d'acheminement de document. Pour résoudre les préférences d'imprimante, le service hébergé utilise le chemin réseau identifiant de manière unique chaque imprimante réseau. Par conséquent, même si une imprimante est enregistrée par plusieurs clients, elle apparaît comme sélection unique dans la liste des imprimantes disponibles dans les applications Finance and Operations.



