---
title: Choix entre Modern POS et Cloud POS
description: "Cette rubrique explique les principales différences entre Retail Modern POS et Cloud POS. Elle décrit également les différents facteurs qui doivent être pris en considération par les détaillants qui implémentent Microsoft Dynamics 365 for Retail pour les aider à faire le meilleur choix pour leurs besoins."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: 
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7efda507ad826b7765431e6cbdd78c3c9246bc7c
ms.openlocfilehash: 03b7b4d468e35c7b77cf2a2e52c038c0995c7f53
ms.contentlocale: fr-fr
ms.lasthandoff: 12/08/2017

---

# <a name="choose-between-modern-pos-and-cloud-pos"></a>Choix entre Modern POS et Cloud POS

[!include[banner](includes/banner.md)]

Cette rubrique fournit aux responsables de l'implémentation un contexte, des conseils et des instructions supplémentaires sur les facteurs qu'ils doivent prendre en considération lorsqu'ils déploient Microsoft Dynamics 365 for Retail. En passant en revue et en suivant ces instructions dans le cadre du processus de déploiement, les responsables de l'implémentation peuvent éviter les problèmes susceptibles d'affecter la satisfaction ou les performances de l'utilisateur.

## <a name="insights"></a>Analyse
Retail offre un large éventail d'options de déploiement et de topologie. Par conséquent, les détaillants peuvent choisir les composants et la configuration qui correspondent le mieux à leurs exigences métier et technologiques. Un aspect de l'implémentation qui nécessite une attention particulière est le choix d'une plateforme et d'un facteur de forme pour le composant de point de vente (POS).

### <a name="pos-platform-and-form-factor-considerations"></a>Éléments à prendre en compte pour la plate-forme et le facteur de forme du POS
Retail prend en charge les options POS suivantes :

- Retail Modern POS (MPOS) pour Microsoft Windows
- MPOS pour Microsoft Windows Phone
- MPOS pour tablette iPad Apple ou Android Google
- Cloud POS (CPOS), qui prend en charge les navigateurs Microsoft Edge, Internet Explorer et Google Chrome

Dans tous les cas, le POS (MPOS et CPOS) partage le même code d'application principal. Ce point est important pour les raisons suivantes :

- L'interface utilisateur est cohérente, quel que soit la plateforme ou le facteur de forme.
- La plupart des capacités fonctionnelles sont identiques, quel que soit la plateforme ou le facteur de forme. Toutefois, il existe des différences importantes. Ces différences sont décrites dans cette rubrique.
- Dans un magasin donné, les écarts POS peuvent être combinés et s'exécuter simultanément. Par exemple, pour ses principales caisses enregistreuses, un détaillant peut utiliser MPOS sur les ordinateurs exécutant Windows. Toutefois, le détaillant peut remplacer ces caisses enregistreuses par des terminaux basés sur un navigateur ou des appareils mobiles.
- Les personnalisations et les extensions peuvent facilement être utilisées dans les plateformes et les facteurs de forme. Comme le code d'application principal est partagé, la plupart des personnalisations peuvent être implémentées une fois au lieu de plusieurs fois.

### <a name="mpos-vs-cpos"></a>MPOS et CPOS
Bien que MPOS et CPOS soient identiques en grande partie, il existe des différences importantes que vous devez comprendre.

#### <a name="mpos"></a>MPOS

MPOS sur un appareil Windows, iOS ou Android est une application mises en package, installée, et mise en service sur cet appareil.

- **Windows** – L'application MPOS pour Windows contient l'intégralité du code d'application et le Commerce Runtime (CRT) incorporé. 
- **iOS/Android** – Sur ces plateformes, l'application agit comme un hôte pour le code d'application CPOS. Autrement dit, le code d'application provient du serveur CPOS sur Microsoft Azure ou de l'Unité d'échelle de magasin de vente au détail (RSSU). Pour plus d'informations, voir [Vue d'ensemble Unité d'échelle de magasin de vente au détail](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>CPOS

Comme CPOS s'exécute dans un navigateur, l'application n'est pas installée sur l'appareil. Le navigateur accède au code d'application à partir du serveur CPOS. Par conséquent, CPOS ne peut pas accéder directement au matériel POS en étant hors connexion.

### <a name="store-deployment-considerations"></a>Éléments à prendre en compte pour le déploiement dans le magasin
Outre une plateforme et un facteur de forme, les détaillants doivent également choisir une option de déploiement dans le magasin. Le tableau suivant affiche les configurations disponibles pour chaque option POS.

| Application POS         | Serveur de vente au détail | Disponible hors connexion |
|-------------------------|---------------|-------------------|
| MPOS pour Windows        | Cloud ou RSSU | Oui               |
| MPOS pour iOS ou Android | Cloud ou RSSU | N°                |
| Cloud POS               | Cloud ou RSSU | N°                |

#### <a name="retail-server"></a>Serveur de vente au détail

Le serveur Retail est un composant qui héberge le CRT. Le CRT contient la logique métier utilisée par le POS, et il permet d'accéder à la base de données des canaux. Lorsqu'ils sont en ligne, tous les clients POS du magasin utilisent le serveur Retail. Le serveur Retail peut être déployé dans le cloud ou dans le magasin (RSSU).

#### <a name="offline-mode"></a>Mode hors connexion

MPOS pour Windows prend en charge le mode hors connexion. En mode hors connexion, le POS peut continuer à traiter les ventes même s'il est déconnecté du serveur Retail. Il peut ensuite être synchronisé avec la base de données des canaux lorsque la connectivité est restaurée. MPOS utilise sa propre instance incorporée du CRT et utilise temporairement sa propre source de données locale (base de données SQL Server hors connexion). Pour plus d'informations sur la fonctionnalité hors connexion, voir [Fonctionnalité de POS hors connexion](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>Éléments à prendre en compte pour les périphériques/le matériel POS
Les détaillants doivent également prendre en compte la manière dont le POS accède aux appareils et périphériques tels que les imprimantes, les tiroirs-caisse et les terminaux de paiement. Seul MPOS pour Windows prend en charge la communication directe avec ces appareils. MPOS pour Windows Phone, iOS ou Android, et Cloud POS nécessitent une station matérielle pour pouvoir accéder à ces appareils. Les stations matérielles peuvent être dédiées à une caisse enregistreuse POS ou partagées entre les caisses enregistreuses d'un magasin. Pour plus d'informations sur les stations matérielles, voir [Configurer et installer la station matérielle Retail](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>Considérations d'implémentation
Tenez compte des informations suivantes lorsque vous planifiez votre implémentation POS dans vos magasins de vente au détail :

- **Besoins fonctionnels** – Les principaux processus et fonctionnalités d'entreprise sont identiques, quel que soit la plateforme, le facteur de forme ou la topologie de déploiement. Par conséquent, la plupart des détaillants ne doivent pas prendre en compte les besoins fonctionnels lorsqu'ils planifient leur implémentation.
- **Connectivité** - La disponibilité du réseau (réseau étendu \[WAN\] et réseau local \[LAN\]) est un facteur important qui nécessite une attention particulière. Tous les avantages qu'offre une solution hébergée dans le cloud à encombrement nul en termes de coût et de simplicité sont perdus si le système n'est pas disponible pour les processus d'entreprise importants.

    À moins que la connectivité d'un appareil donné soit très dépendante et résiliente, ou qu'un certain temps d'interruption soit acceptable pour le revendeur, nous vous recommandons l'une des options suivantes :

    - Utilisez MPOS dans Windows et activez le mode hors connexion.
    - Déployez un RSSU sur site.

    Ces deux options ne sont pas mutuellement exclusives. Pour la topologie la plus fiable, les détaillants peuvent déployer un RSSU local pour réduire la dépendance vis-à-vis de la connexion Internet ou de la disponibilité d'Azure, et ils peuvent également déployer des caisses enregistreuses POS lorsque le mode hors connexion est activé si le serveur ou réseau local rencontre un problème.

- **Périphériques matériels/Périphériques** – Un aspect important d'un système Retail POS est la possibilité d'utiliser des périphériques POS tels que des imprimantes, des tiroirs-caisse et des terminaux de paiement. Même si toutes les options POS disponibles peuvent utiliser les périphériques, seul MPOS pour Windows les prend en charge directement. Pour toutes les autres applications, une ou plusieurs stations matérielles sont requises. Bien que cette approche soit plus flexible, des composants supplémentaires doivent être déployés, configurés et mis en service.
- **Configuration requise** – La configuration requise pour l'application POS varie. Veillez à vérifier les dernières informations disponibles avant de faire votre choix. Par exemple, comme CPOS s'exécute dans un navigateur, il prend en charge un plus grand nombre de systèmes d'exploitation. Pour plus d'informations sur la configuration requise, voir [Configuration requise pour les déploiements Cloud](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **Déploiement et mise en service** – La complexité des exigences de déploiement et de mise en service peut varier, selon l'application et le déploiement choisis. Par exemple, pour un déploiement CPOS hébergé dans le cloud, il n'est pas nécessaire d'installer et de mettre à jour chaque appareil. Par conséquent, cette approche réduit considérablement la complexité et le coût. Toutefois, si vous déployez MPOS sur chaque caisse enregistreuse et activez le mode hors connexion, et si vous déployez également les stations matérielles partagées, vous augmentez considérablement le nombre de points de terminaison à gérer.

