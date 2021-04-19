---
title: Options de mise en œuvre d’un réseau de diffusion de contenu
description: Cette rubrique passe en revue les différentes options d’implémentation d’un réseau de diffusion de contenu (CDN) pouvant être utilisées avec les environnements Microsoft Dynamics 365 Commerce. Ces options incluent des instances Azure Front Door natives fournies par Commerce et des instances Azure Front Door appartenant au client.
author: BrianShook
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9e98cf81f13b9181059bc96b95ac277a088311ea
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800709"
---
# <a name="content-delivery-network-implementation-options"></a>Options de mise en œuvre d’un réseau de diffusion de contenu

[!include [banner](includes/banner.md)]

Cette rubrique passe en revue les différentes options d’implémentation d’un réseau de diffusion de contenu (CDN) pouvant être utilisées avec les environnements Microsoft Dynamics 365 Commerce. Ces options incluent des instances Azure Front Door natives fournies par Commerce et des instances Azure Front Door appartenant au client.

Les clients Commerce ont plusieurs options lorsqu’ils doivent choisir quel service CDN utiliser avec leur environnement Commerce. Commerce est lancé avec la prise en charge Azure Front Door de base, qui couvre l’hébergement de base et les exigences de domaine personnalisé. Pour les entreprises qui souhaitent plus de contrôle et des capacités de sécurité plus spécifiques, par exemple un pare-feu d’application web (WAF), la meilleure option peut être d’utiliser une instance Azure Front Door appartenant au client ou un service CDN externe.

Les trois options d’implémentation CDN suivantes peuvent être utilisées avec les environnements Commerce :

- L’instance Azure Front Door fournie par Commerce
- Une instance Azure Front Door appartenant au client (pour un contrôle accru et des fonctionnalités de sécurité supplémentaires)
- Un service CDN externe

Les trois options d’implémentation CDN fournissent uniquement du contenu HTML dynamique de domaines personnalisés. Commerce gère automatiquement tous les contenus JavaScript, les feuilles de style en cascade (CSS), les images, les vidéos et d’autres contenus statiques via des CDN gérés par Microsoft. L’option que vous choisissez détermine les capacités opérationnelles, les capacités de contrôle et les capacités de sécurité supplémentaires disponibles.

L’illustration suivante présente une vue d’ensemble de l’architecture de Commerce.

![Présentation de l’architecture de Commerce](media/Commerce_CDN-Option_ComparisonModels.png)

Pour plus d’informations sur la configuration d’une instance Azure Front Door pour votre site Commerce, consultez [Ajouter la prise en charge d’un CDN](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Utiliser l’instance Azure Front Door fournie par Commerce

Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation de l’instance Azure Front Door fournie par Commerce pour gérer les points de terminaison de contenu.

| Avantages | Inconvénients |
|------|------|
| <ul><li>L’instance est incluse dans le coût de Commerce.</li><li>Étant donné que l’instance est gérée par l’équipe de Commerce, moins de maintenance est requise et des étapes de configuration sont partagées.</li><li>L’infrastructure hébergée par Azure est évolutive, sécurisée et fiable.</li><li>Le certificat SSL (Secure Sockets Layer) nécessite une configuration unique et est automatiquement renouvelé.</li><li>L’instance est surveillée par l’équipe Commerce qui recherche les erreurs et les anomalies.</li></ul> | <ul><li>Aucun WAF n’est pris en charge.</li><li>Il n’y a pas de personnalisations ou d’ajustements de paramètres spécifiques.</li><li>Les mises à jour ou les modifications de l’instance dépendent de l’équipe Commerce.</li><li>Une instance Azure Front Door distincte est requise pour les domaines apex, et un travail supplémentaire est requis pour intégrer les domaines apex avec Azure DNS.</li><li>Aucune télémétrie sur les réponses par seconde (RPS) ou le taux d’erreur n’est fournie au client.</li></ul> |

L’illustration suivante montre l’architecture de l’instance Azure Front Door fournie par Commerce.

![Instance Azure Front Door fournie par Commerce](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Utiliser une instance Azure Front Door appartenant au client

Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation d’une instance Azure Front Door appartenant au client pour gérer les points de terminaison de contenu.

| Avantages | Inconvénients |
|------|------|
| <ul><li>La configuration est sécurisée et facile à gérer.</li><li>L’infrastructure hébergée par Azure est évolutive, sécurisée et fiable.</li><li>L’instance permet une intégration WAF et des contrôles de règles précis pour une sécurité de meilleure qualité, spécialement adaptée à votre site.</li><li>L’instance permet un contrôle plus précis des certificats SSL (appartenant au client et gérés par Azure Front Door) et la liaison de domaine.</li><li>L’instance offre une solution de domaine apex si elle est directement associée à Azure DNS.</li><li>La télémétrie et les alertes sont fournies.</li><li>Le certificat SSL nécessite une configuration unique et est automatiquement renouvelé.</li></ul> | <ul><li>L’instance est autogérée.</li><li>Une période initiale d’acquisition des connaissances est requise.</li></ul> |

L’illustration suivante montre une infrastructure Commerce qui comprend une instance Azure Front Door appartenant au client.

![Infrastructure Commerce qui comprend une instance Azure Front Door appartenant au client](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Utiliser un service CDN externe

Le tableau suivant répertorie les avantages et les inconvénients de l’utilisation d’un service CDN externe pour gérer les points de terminaison de contenu.

| Avantages | Inconvénients |
|------|------|
| <ul><li>Cette option est utile lorsque le domaine existant est déjà hébergé sur un CDN externe.</li><li>Les CDN concurrents (par exemple, Akamai) peuvent avoir plus de capacités WAF.</li></ul> | <ul><li>Un contrat séparé est requis et des coûts supplémentaires s’appliquent.</li><li>SSL peut entraîner des coûts supplémentaires.</li><li>Étant donné que le service est distinct de la structure cloud Azure, une infrastructure supplémentaire doit être gérée.</li><li>Le service peut nécessiter des investissements en temps plus longs pour la configuration des points de terminaison et de la sécurité.</li><li>Les service est autogéré.</li><li>Les service est autocontrôlé.</li></ul> |

L’illustration suivante montre une infrastructure Commerce qui comprend un service CDN externe.

![Infrastructure Commerce qui comprend un service CDN externe](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter la prise en charge d’un réseau de distribution de contenu (CDN)](add-cdn-support.md)
