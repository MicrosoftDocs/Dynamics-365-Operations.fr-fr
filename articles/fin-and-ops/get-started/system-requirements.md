---
title: "Configuration requise pour les déploiements Cloud"
description: "Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements cloud."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: 7fe11966b27eb0793a47835e05e465d809bf3407
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="system-requirements-for-cloud-deployments"></a>Configuration requise pour les déploiements Cloud

[!include[banner](../includes/banner.md)]

Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements cloud. Avant d'installer Finance and Operations, si nécessaire, vérifiez que le système que vous utilisez répond ou excède la configuration minimale requise pour le réseau, le matériel et les logiciels.

## <a name="supported-web-browsers"></a>Navigateurs Web pris en charge
L'application Web peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette
-   Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. 

> [!NOTE]
> -   Vous devez installer une extension Chrome préliminaire pour permettre à l'enregistreur de tâches d'effectuer des captures d'écran et de les inclure dans les documents Microsoft Word générés. <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   L'éditeur de workflow démarre en tant qu'application ClickOnce. Seuls Microsoft Edge et Internet Explorer (dans une version prise en charge de Microsoft Windows) prennent en charge les applications ClickOnce. L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.
> -   Le Concepteur de rapports pour les États financiers démarre en tant qu'application ClickOnce. Il nécessite un système d'exploitation compatible 64 bits. Si vous utilisez Chrome, vous devez installer une extension ClickOnce pour télécharger le client Concepteur de rapports. Si vous utilisez Chrome en mode incognito, vérifiez que l'extension ClickOnce est également activée pour le mode incognito.
> -   Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navigateurs Web pris en charge pour Retail Cloud POS

Retail Cloud POS peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Chrome (dernière version publique disponible) sous Windows 10, Windows 8,1 ou Windows 7

## <a name="network-requirements"></a>Exigences réseau
-   Finance and Operations est conçu pour les réseaux ayant une latence de 250 à 300 millisecondes (ms) ou moins. C'est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Finance and Operations. Nous vous recommandons de tester la latence du réseau à l'adresse <http://www.azurespeed.com>.
-   Les besoins en bande passante pour Finance and Operations dépendent de votre scénario. La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps). Toutefois, une bande passante plus conséquente est recommandée pour les scénarios qui ont des exigences de charge utile élevées, tels que les scénarios impliquant des espaces de travail ou une personnalisation étendue.

De manière générale, Finance and Operations est optimisé pour Internet. Le nombre d'allers-retours entre le client Web et le centre de données Azure est très faible et la charge utile entière est compressée. 

> [!WARNING]
> Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Les clients qui s'inquiètent des besoins de bande passante doivent utiliser une version d'aperçu de Finance and Operations.

## <a name="net-framework-requirements"></a>Exigences.NET Framework
Finance and Operations requiert la version Microsoft .NET Framework 4.6.2 pour toutes les applications ClickOnce, telles que l'agent d'acheminement de document. Pour obtenir les instructions d'installation, voir [Installation de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge
Les applications suivantes Microsoft Office sont prises en charge dans les déploiements dans le cloud et sur site de Finance and Operations :

-   Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus d'informations sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.

## <a name="retail-modern-pos-requirements"></a>Exigences de Retail Modern POS

> [!NOTE]
> Si Retail Modern POS utilise une base de données hors connexion, l'ordinateur doit respecter toutes les configurations requises pour Microsoft SQL Server. Une base de données hors connexion Retail Modern POS fonctionnera sur Microsoft SQL Server 2012 avec Service Pack 3 ou une version ultérieure, Microsoft SQL Server 2014 avec Service Pack 2 ou une version ultérieure et Microsoft SQL Server 2016. Il est recommandé d'utiliser systématiquement la dernière version disponible, et d'installer tous les Service Packs les plus récents.

### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   Retail Modern POS est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.
-   Retail Modern POS est pris en charge uniquement sous les éditions Windows 10 Pro, Enterprise et Enterprise LTSB (Long Term Servicing Branch).

### <a name="minimum-system-requirements"></a>Configuration système minimale

-   La résolution minimale prise en charge est 1280 × 1024.
-   L'ordinateur sur lequel est exécuté Retail Modern POS doit avoir la configuration minimale suivante :

    -   Il doit disposer au moins d'un processeur double-cœur fonctionnant à une fréquence d'au moins 2 GHz.
    -   Il doit avoir au minimum 3 giga-octets (Go) de mémoire RAM.
    -   Il doit avoir accès à Internet.

## <a name="retail-hardware-station-requirements"></a>Exigences de la station matérielle Retail
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   La station matérielle Retail est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.
-   La station matérielle Retail est prise en charge sur les systèmes d'exploitation suivants :

    -   Windows 7 éditions Professional, Enterprise et Ultimate 
    
        > [!NOTE]
        > Windows 7 est pris en charge uniquement si Internet Explorer 11 est manuellement installé sur le système.

    -   Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded
    -   Windows 10 éditions Pro, Enterprise et Enterprise LTSB

### <a name="minimum-system-requirements"></a>Configuration système minimale

L'ordinateur doit répondre à tous exigences système pour installer et utiliser les éléments suivants :

-   Services Internet (IIS)
-   matériel tiers

## <a name="retail-store-scale-unit-requirements"></a>Exigences de l'unité d'échelle de magasin de vente au détail
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   L'unité d'échelle Retail Store est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.
-   L'unité d'échelle Retail Store est prise en charge sur les systèmes d'exploitation suivants :

    -   Windows 7 éditions Professional, Enterprise et Ultimate
    -   Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded
    -   Windows 10 éditions Pro, Enterprise et Enterprise LTSB

### <a name="minimum-system-requirements"></a>Configuration système minimale

-   4 Go de mémoire vive (RAM)
-   Vitesse de pointe du processeur de 1,6 GHz par cœur (deux cœurs au minimum.)
-   Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)

### <a name="recommended-system-requirements"></a>Configuration système recommandée

-   6 Go de mémoire vive (RAM)
-   Vitesse de pointe du processeur de 2,4 GHz i7 (ou équivalent) par cœur (quatre cœurs recommandés.)
-   Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)

## <a name="connector-requirements"></a>Connecteur requis
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   Le connecteur pour Microsoft Dynamics AX a deux programmes d'installation distincts, un pour le service Async Server Connector et un pour le service Real-time Service pour Dynamics AX 2012 R3.
-   Les deux composants sont des applications 32 bits, mais ils fonctionnent aussi bien sur les architectures x86 ou x64.
-   Les deux composants sont pris en charge sur les systèmes d'exploitation suivants :

    -   Windows 7 éditions Professional, Enterprise et Ultimate
    -   Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded
    -   Windows 10 éditions Pro, Enterprise et Enterprise LTSB
    -   Microsoft Windows Server 2012 R2 et Microsoft Windows Server 2016

### <a name="minimum-system-requirements"></a>Configuration système minimale
-   2 Go de RAM (4 Go de RAM sont recommandés)
-   Vitesse de pointe du processeur de 1,6 GHz par cœur (deux cœurs au minimum.)
-   Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)

## <a name="requirements-for-development-on-local-vms"></a>Exigences pour le développement sur les ordinateurs virtuels locaux
Pour plus d'informations sur les exigences associées au développement sur les ordinateurs virtuels locaux, voir [Ordinateurs virtuels sur site](../../dev-itpro/dev-tools/access-instances.md).


## <a name="see-also"></a>Voir également :

[Obtenir une copie d'évaluation de Dynamics 365 for Finance and Operations, Enterprise Edition](../../dev-itpro/dev-tools/get-evaluation-copy.md)

