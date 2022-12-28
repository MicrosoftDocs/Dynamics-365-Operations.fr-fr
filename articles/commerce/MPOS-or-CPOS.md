---
title: Choisir entre Store Commerce et Cloud POS
description: Cet article explique les principales différences entre Store Commerce et Cloud POS, et décrit divers facteurs que les détaillants qui implémentent Dynamics 365 Commerce devraient envisager pour les aider à faire le meilleur choix en fonction de leurs besoins.
author: josaw1
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 0e1092c0c5c49c6a99dd441c75f545fc831c0b03
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831555"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>Choisir entre Store Commerce et Cloud POS

[!include [banner](includes/banner.md)]

Cet article explique les principales différences entre Store Commerce et Cloud POS, et décrit divers facteurs que les détaillants qui implémentent Dynamics 365 Commerce devraient envisager pour les aider à faire le meilleur choix en fonction de leurs besoins. Il fournit aussi aux responsables de l’implémentation un contexte, des conseils et des instructions supplémentaires sur les facteurs qu’ils doivent prendre en considération quand ils déploient Dynamics 365 Commerce. En passant en revue et en suivant ce guide dans le cadre du processus de déploiement, les responsables de l’implémentation peuvent éviter les problèmes susceptibles d’affecter la satisfaction ou les performances de l’utilisateur.

## <a name="insights"></a>Aperçus

Commerce offre un large éventail d’options de déploiement et de topologie. Par conséquent, les détaillants peuvent choisir les composants et la configuration qui correspondent le mieux à leurs exigences métier et technologiques. Un aspect de l’implémentation qui nécessite une attention particulière est le choix d’une plateforme et d’un facteur de forme pour le composant de point de vente (PDV).

### <a name="pos-platform-and-form-factor-considerations"></a>Éléments à prendre en compte pour la plate-forme et le facteur de forme du PDV

Commerce prend en charge les options PDV suivantes :

- Store Commerce pour Microsoft Windows
- Store Commerce pour iOS et Android
- Cloud POS (CPOS), qui prend en charge Microsoft Edge et les navigateurs Google Chrome
- Modern POS (MPOS) pour Microsoft Windows (MPOS sera déconseillé en octobre 2023.) 

Dans tous les cas, le PDV (Store Commerce et CPOS) partage le même code d’application principal. Ce point est important pour les raisons suivantes :

- L’interface utilisateur (UI) est cohérente, quel que soit la plateforme ou le facteur de forme.
- La plupart des capacités fonctionnelles sont identiques, quel que soit la plateforme ou le facteur de forme. Toutefois, il existe des différences importantes. Ces différences sont décrites dans cet article.
- Dans chaque magasin, les écarts de PDV peuvent être combinés et s’exécuter simultanément. Par exemple, pour ses principales caisses enregistreuses, un détaillant peut utiliser Store Commerce sur les ordinateurs exécutant Windows. Toutefois, le détaillant peut remplacer ces caisses enregistreuses par des terminaux basés sur un navigateur ou des appareils mobiles.
- Les personnalisations et les extensions peuvent facilement être utilisées dans les plateformes et les facteurs de forme. Comme le code d’application principal est partagé, la plupart des personnalisations peuvent être implémentées une fois au lieu de plusieurs fois.

### <a name="store-commerce-vs-cpos"></a>Store Commerce vs. CPOS

Bien que Store Commerce et CPOS soient identiques en grande partie, il existe des différences importantes que vous devez comprendre.

#### <a name="store-commerce"></a>Store Commerce

Store Commerce est une application de bureau qui est installée et entretenue sur un appareil.

- **Windows** – L’application Store Commerce pour Windows contient l’intégralité du code d’application, Commerce Runtime (CRT) et la station matérielle (HWS).
- **iOS/Android** – Sur ces plateformes, l’application agit comme un hôte pour le code d’application CPOS. Autrement dit, le code d’application provient du serveur CPOS hébergé sur Commerce Scale Unit. Pour plus d’informations, voir [Vue d’ensemble de Commerce Scale Unit](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>CPOS

Comme CPOS s’exécute dans un navigateur, l’application n’est pas installée sur l’appareil. Au lieu de cela, le navigateur accède au code d’application à partir du serveur CPOS. Par conséquent, CPOS ne peut pas accéder directement au matériel POS ou travailler dans un état hors connexion.

### <a name="store-deployment-considerations"></a>Éléments à prendre en compte pour le déploiement dans le magasin

Outre une plateforme et un facteur de forme, les détaillants doivent également choisir une option de déploiement dans le magasin. Le tableau suivant affiche les configurations disponibles pour chaque option POS.

| Application PDV            | Commerce Scale Unit | Disponible hors connexion | Support local HWS |
|----------------------------|---------------------|-------------------|-------------------|
| Store Commerce pour Windows | Cloud ou RSSU       | Oui               | Oui               |
| Store Commerce pour Android | Cloud ou RSSU       | N°                | Oui               |
| Store Commerce pour iOS     | Cloud ou RSSU       | N°                | Oui               |
| PDV Cloud                  | Cloud ou RSSU       | N°                | N°                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

Le Commerce Scale Unit est un composant qui héberge le CRT. Le CRT contient toute la logique métier utilisée par le PDV, et il permet d’accéder à la base de données du canal. Quand ils sont en ligne, tous les clients PDV du magasin utilisent le Commerce Scale Unit. Le Commerce Scale Unit peut être déployée dans le cloud ou dans le magasin.

#### <a name="offline-mode"></a>Mode hors connexion

Store Commerce pour Windows prend en charge le mode hors connexion. En mode hors connexion, le PDV peut continuer à traiter les ventes même s’il est déconnecté du Commerce Scale Unit. Il peut ensuite être synchronisé avec la base de données du canal quand la connectivité est restaurée. Store Commerce utilise sa propre instance incorporée du CRT et utilise temporairement sa propre source de données locale (base de données SQL Server hors connexion). Pour plus d’informations sur la fonctionnalité hors connexion, voir [Fonctionnalité PDV hors connexion](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>Considérations relatives au périphérique/matériel PDV

Les détaillants doivent également prendre en compte la manière dont le PDV accède aux appareils et périphériques tels que les imprimantes, les tiroirs-caisse et les terminaux de paiement. Les stations matérielles peuvent être dédiées à une caisse enregistreuse PDV ou partagées entre les caisses enregistreuses d’un magasin.

| Application PDV            | OPOS HWS local | Périphériques réseau | Support HWS partagé |
|----------------------------|----------------|---------------------|--------------------|
| Store Commerce pour Windows | Oui            | Oui                 | Oui                |
| Store Commerce pour Android | N°             | Oui                 | Oui                |
| Store Commerce pour iOS     | N°             | Oui                 | Oui                |
| PDV Cloud                  | N°             | N°                  | Oui                |

Pour plus d’informations sur les stations matérielles, voir [Configurer et installer la station matérielle de vente au détail](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>Considérations d’implémentation

Tenez compte des informations suivantes quand vous planifiez la mise en œuvre de votre PDV dans vos magasins :

- **Besoins fonctionnels** – Les principaux processus et fonctionnalités d’entreprise sont identiques, quel que soit la plateforme, le facteur de forme ou la topologie de déploiement. Par conséquent, la plupart des détaillants ne doivent pas prendre en compte les besoins fonctionnels quand ils planifient leur implémentation.
- **Connectivité** – La disponibilité du réseau (réseau étendu \[WAN\] et réseau local \[LAN\]) est un facteur important qui nécessite une attention particulière. Tous les avantages qu’offre une solution sans empreinte hébergée dans le cloud en termes de coût et de simplicité sont perdus si le système n’est pas disponible pour les processus critiques pour l’entreprise.

    À moins que la connectivité d’un appareil donné soit très dépendante et résiliente, ou qu’un certain temps d’interruption soit acceptable pour le détaillant, nous vous recommandons l’une des options suivantes :

    - Utilisez Store Commerce dans Windows et activez le mode hors connexion.
    - Déployez un Commerce Scale Unit local.

    Ces deux options ne sont pas mutuellement exclusives. Pour la topologie la plus fiable, les détaillants peuvent déployer un RSSU local pour réduire la dépendance sur la connexion Internet ou de la disponibilité d’Azure, et ils peuvent également déployer des caisses enregistreuses PDV quand le mode hors connexion est activé si le serveur ou réseau local rencontre un problème.

- **Appareils matériels/Périphériques** – Un aspect important d’un système de détail PDV est la possibilité d’utiliser des périphériques PDV tels que des imprimantes, des tiroirs-caisse et des terminaux de paiement. Même si toutes les options PDV disponibles peuvent utiliser des appareils périphériques, seul Store Commerce pour Windows les prend en charge directement. Pour toutes les autres applications, une ou plusieurs stations matérielles sont requises. Bien que cette approche soit plus flexible, des composants supplémentaires doivent être déployés, configurés et mis en service.
- **Configuration requise** – La configuration requise pour l’application PDV varie. Veillez à vérifier les dernières informations disponibles avant de faire votre choix. Par exemple, comme CPOS s’exécute dans un navigateur, il prend en charge un plus grand nombre de systèmes d’exploitation. Pour plus d’informations sur la configuration requise, voir [Configuration requise pour les déploiements Cloud](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **Déploiement et maintenance** – La complexité des exigences de déploiement et de maintenance peut varier, selon l’application et le déploiement choisis. Par exemple, pour un déploiement CPOS hébergé dans le cloud, il n’est pas nécessaire d’installer et de mettre à jour chaque appareil. Par conséquent, cette approche réduit considérablement la complexité et le coût. Toutefois, si vous déployez Store Commerce sur chaque caisse enregistreuse et activez le mode hors connexion, et si vous déployez également les stations matérielles partagées, vous augmentez considérablement le nombre de points de terminaison à gérer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
