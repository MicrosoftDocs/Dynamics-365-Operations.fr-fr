---
title: Configuration requise
description: "Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Operations."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 86053196a3aad6b7b5d7830860e1af347dd969d8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="system-requirements"></a>Configuration requise

[!include[banner](../includes/banner.md)]


Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Operations.

<a name="supported-web-browsers"></a>Navigateurs Web pris en charge
----------------------

L'application Web Microsoft Dynamics 365 for Operations peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette
-   Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. **Remarques :**

-   Pour capturer des images générées à partir de l'enregistreur de tâches et les inclure dans les documents Microsoft Word, vous devez avoir une extension Chrome installée. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   L'éditeur de workflow démarre en tant qu'application ClickOnce. Seuls Microsoft Edge et Internet Explorer (dans une version prise en charge de Microsoft Windows) prennent en charge les applications ClickOnce. L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.
-   Le Concepteur de rapports pour les États financiers démarre en tant qu'application ClickOnce. Elle nécessite un système d'exploitation compatible 64 bits. Si vous utilisez Chrome, vous devez installer une extension ClickOnce afin de télécharger le client Concepteur de rapports. Si vous utilisez Chrome en mode incognito, vérifiez que l'extension ClickOnce est également activée pour le mode incognito.
-   Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navigateurs Web pris en charge pour Retail Cloud POS

L'application Retail Cloud POS pour Dynamics 365 for Operations peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Chrome (dernière version publique disponible) sous Windows 10, Windows 8,1 ou Windows 7

## <a name="network-requirements"></a>Exigences réseau
-   Dynamics 365 for Operations est conçu pour les réseaux ayant une latence inférieure à 150 millisecondes (ms). C'est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Dynamics 365 for Operations. Nous vous recommandons de tester la latence du réseau à l'adresse <http://www.azurespeed.com>.
-   Les besoins en bande passante pour Dynamics 365 for Operations dépendent de votre scénario. La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps). Toutefois, pour les scénarios qui ont des exigences de charge utile élevées, tels que les espaces de travail ou les scénarios impliquant une personnalisation étendue, une bande passante plus conséquente est recommandée.

De manière générale, Dynamics 365 for Operations est optimisé pour Internet. Le nombre d'allers-retours entre le client Web et le centre de données Azure est très faible et la charge utile entière est compressée. **Attention :** ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Pour les clients qui s'inquiètent des besoins de bande passante, utilisez une version d'aperçu de Dynamics 365 for Operations.

## <a name="net-framework-requirements"></a>Exigences.NET Framework
Dynamics 365 for Operations requiert la version .NET Framework 4.6.2 pour toutes les applications ClickOnce, telles que l'agent d'acheminement de document. Pour obtenir les instructions d'installation, voir [Installation de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge
-   Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus de détails sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.

## <a name="retail-modern-pos-requirements"></a>Exigences de Retail Modern POS
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   Retail Modern POS est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.
-   Retail Modern POS est pris en charge uniquement sous les éditions Windows 10 Pro, Enterprise et Enterprise LTSB (Long Term Servicing Branch).

### <a name="minimum-system-requirements"></a>Configuration système minimale

-   La résolution minimale prise en charge est 1280 × 1024.
-   L'ordinateur sur lequel est exécuté Retail Modern POS doit avoir la configuration minimale suivante :
    -   Il doit disposer au moins d'un processeur double-cœur fonctionnant à une fréquence d'au moins 2 GHz.
    -   Il doit disposer d'au moins 3 Go de mémoire vive (RAM).
    -   Il doit avoir accès à Internet.

## <a name="retail-hardware-station-requirements"></a>Exigences de la station matérielle Retail
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   La station matérielle Retail est une application 32 bits, mais elle fonctionne aussi bien sur les architectures x86 ou x64.
-   La station matérielle Retail est prise en charge sur les systèmes d'exploitation suivants :
    -   Windows 7 éditions Professional, Enterprise et Ultimate. **Remarque :** Windows 7 est pris en charge uniquement si Internet Explorer 11 est installé manuellement sur le système.
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

## <a name="requirements-for-development-on-local-vms"></a>Exigences pour le développement sur les ordinateurs virtuels locaux
Pour plus d'informations sur les exigences associées au développement sur les ordinateurs virtuels locaux, voir [Ordinateurs virtuels sur site](../dev-tools/access-instances.md).

<a name="see-also"></a>Voir également :
--------

[Obtenir une version d'évaluation de Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)




