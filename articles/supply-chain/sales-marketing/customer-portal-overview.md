---
title: Présentation du portail client pour Dynamics 365 Supply Chain Management
description: Cette rubrique présente le portail client et explique qui doit l’utiliser et comment il fonctionne.
author: dasani-madipalli
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: fc0f8187c10bfc95f94e59b62be8e89d4556dbfc373294aa17579d8c69caed18
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764009"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Présentation du portail client pour Dynamics 365 Supply Chain Management

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="what-is-the-customer-portal"></a>Qu’est-ce que le portail client ?

Les systèmes de chaîne d’approvisionnement modernes reposent sur l’intégration. Ils exigent que les stocks, la demande des clients et les services commerciaux soient intégrés au lieu de résider dans des silos séparés. Le portail client aide les organisations qui exécutent Microsoft Dynamics 365 Supply Chain Management à améliorer cette intégration et à mieux informer leurs clients.

Le portail client est un modèle de [portails Power Apps](/powerapps/maker/portals/overview) qui permet aux entreprises de créer un site web interentreprises (B2B) ouvert sur l’extérieur pour les scénarios liés au traitement des commandes client. Ce modèle utilise la [double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management et les portails Power Apps pour permettre aux clients externes de l’entreprise de visualiser et de créer des données à partir de l’environnement Dynamics 365 de l’entreprise.

Le modèle de portail client possède toutes les fonctionnalités de personnalisation que proposent les portails Power Apps. Le modèle peut facilement être modifié pour représenter la marque de l’entreprise, ajouter d’autres fonctionnalités et changer l’expérience utilisateur. Toutes les fonctionnalités prêtes à l’emploi du modèle peuvent être modifiées à votre guise.

> [!IMPORTANT]
> En soi, le modèle n’est pas censé être complètement fonctionnel. Il sert simplement de base pour les clients qui souhaitent créer un site web ouvert sur l’extérieur afin que les clients de l’entreprise puissent interagir avec les données issues de Supply Chain Management.

> [!NOTE]
> La documentation du portail client s’adresse aux administrateurs, aux personnalisateurs et aux intégrateurs système qui configureront le portail client pour une installation de Supply Chain Management. Il utilise les termes _client_ et _utilisateur_ pour décrire les personnes qui sont des clients de l’organisation qui exécute Supply Chain Management qui utiliseront le portail final lui-même.

## <a name="video"></a>Vidéo

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

La vidéo [Présentation du modèle de portail client dans Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) (illustrée ci-dessus) est incluse dans la [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.

## <a name="who-should-use-it"></a>Qui doit l’utiliser ?

Le portail client est conçu pour les entreprises qui exécutent Supply Chain Management et présentent les caractéristiques suivantes :

- Ils souhaitent créer un site Web ouvert sur l’extérieur qui communique les informations de traitement des commandes (telles que le statut des commandes ou les informations de compte) directement depuis leur système Supply Chain Management jusqu’aux clients de l’entreprise.
- Ils passent de Dynamics AX 2012 à Supply Chain Management et utilisaient auparavant le [Portail client en libre service AX 2012](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

Les types d’organisations suivants **ne sont pas** de bons candidats pour la mise en place du portail client :

- Les entreprises qui souhaitent créer un site web pour des clients non professionnels. Ces entreprises doivent envisager de créer un [Site web de commerce électronique Dynamics 365 Commerce](../../commerce/create-ecommerce-site.md).
- Les entreprises qui utilisent déjà un site web de portail Power Apps dans un but similaire. Ces entreprises ne bénéficieront d’aucun avantage supplémentaire à utiliser le portail client. Le portail client est fourni sous la forme d’un modèle qui sert de guide et de point de départ pour les clients qui souhaitent « relier les points » entre la double écriture, Supply Chain Management et les portails Power Apps. Si vous avez déjà configuré un site web à cette fin, il est possible qu’il ne vous soit pas très utile d’utiliser le modèle de portail client pour reconfigurer ce site web.

## <a name="how-does-it-work"></a>Comment ça fonctionne ?

Le portail client est fourni en tant que modèle de portails Power Apps. Il repose sur les portails Power Apps et sur la double écriture.

Les [portails Power Apps](/powerapps/maker/portals/overview) sont une fonctionnalité qui permet aux utilisateurs de créer un site web ouvert sur l’extérieur auquel des personnes extérieures à l’organisation peuvent se connecter. La création de portails requiert peu ou pas de code. Le portail client est l’un des nombreux [Modèles de portail Dynamics 365](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) disponibles auprès de Microsoft.

La [double écriture](/powerapps/maker/portals/overview) est un produit d’infrastructure prêt à l’emploi qui fournit une interaction en temps quasi réel entre les applications Customer Engagement et les applications Finance and Operations. La double écriture offre une intégration bidirectionnelle entre les applications Finance and Operations et Microsoft Dataverse. Par conséquent, elle offre une expérience utilisateur intégrée entre les différentes applications. Le portail client dépend des tables synchronisées par la double écriture. Avant que les données issues de Supply Chain Management puissent apparaître dans le portail client, la double écriture doit être activée pour toutes les tables appropriées.

![Dépendances du portail client.](media/customer-portal-elements.png "Dépendances du portail client")

Le portail client sert de point de départ pour les organisations qui souhaitent utiliser les portails Power Apps pour créer un site Web ouvert sur l’extérieur qui utilise les données de leur installation Supply Chain Management. Il aide les organisations à connecter la double écriture, Supply Chain Management et les portails Power Apps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]