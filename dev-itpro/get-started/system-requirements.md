---
title: Configuration requise
description: "Cette rubrique répertorie les requise pour la version actuelle de Microsoft Dynamics 365 pour les opérations."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Configuration requise

Cette rubrique répertorie les requise pour la version actuelle de Microsoft Dynamics 365 pour les opérations.

<a name="supported-web-browsers"></a>Navigateurs Web pris en charge
----------------------

Microsoft Dynamics 365 pour l'application Web Opérations peut être exécuté dans les navigateurs Web qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Bord Microsoft (le plus tard publiquement - version disponible) sous Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (le plus tard publiquement - version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou la tablettes la connexion 10 de Google
-   Safari d'Apple (le plus tard publiquement - version disponible) sur Mac SE x 10,10 (Yosemite), 10,11 (EL Capitan) ou 10,12 (sierra), ou iPad d'Apple

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. **Remarques :**

-   Pour entrer des images générées à partir de l'enregistreur de tâches et les inclure dans les documents Microsoft Word, vous devez avoir une extension du chrome installé. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   L'éditeur de workflow démarre comme application de ClickOnce. Seul le bord et Internet Explorer Microsoft (sur une version prise en charge de Microsoft Windows) prennent en charge les applications de ClickOnce. L'application de ClickOnce d'éditeur de workflow nécessite un système d'exploitation 64 bits compatible.
-   Le Concepteur de rapports pour les états financiers est commencé comme application de ClickOnce. Il requiert un système d'exploitation 64 bits compatible. Si vous utilisez chrome, vous devez installer une extension de ClickOnce afin de télécharger le client du Concepteur de rapports. Si vous utilisez chrome avec le mode incognito, vérifiez que l'extension de ClickOnce est également activée pour le mode incognito.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navigateurs Web pris en charge pour Retail Cloud POS

Le PDV au détail de cloud pour Dynamics 365 pour les opérations peut être exécuté dans les navigateurs Web qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Bord Microsoft (le plus tard publiquement - version disponible) sous Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Chrome (le plus tard publiquement - version disponible) sous Windows 10, Windows 8,1, ou Windows 7

## <a name="network-requirements"></a>Les besoins de réseaux
-   Dynamics 365 pour les opérations est conçu pour les réseaux avec le temps d'attente de inférieur à 150 millisecondes de (ms). Il s'agit du temps d'attente d'un client du navigateur au centre de calculs azuré Microsoft qui héberge Dynamics 365 pour les opérations. Nous vous recommandons de tester le temps de latence du réseau à<> l'adresse http://www.azurespeed.com.
-   Les besoins de bande passante pour Dynamics 365 pour les opérations dépendent de votre scénario. La plupart des scénarios habituelles nécessitent une bande passante de plus de 50 kilo-octets par {{seconde:per}} (Kbps). Toutefois, pour les scénarios qui ont des exigences élevés de charge utile, tels que des espaces de travail ou des scénarios impliquant la personnalisation étendue, plus de bande passante est recommandée.

En général Dynamics 365 pour les opérations est amélioré pour Internet. Numéro de allers-retours des appels client d'un du navigateur au centre de calculs azuré est très importante, et la charge utile totale est compressée. ** Prévenant : ** Ne calculent pas les besoins de bande passante d'un emplacement client en multipliant le nombre d'utilisateurs par les exigences minimales de bande passante. Il est très difficile calculer l'utilisation simultanée d'un emplacement donné. Pour les clients qui sont préoccupés {{par:about}} les besoins de bande passante, utilisez une version d'aperçu de Dynamics 365 pour les opérations.

## <a name="net-framework-requirements"></a>Les besoins de .NET Framework
Dynamics 365 pour les opérations requiert la version 4.6.2 .NET Framework pour tous clic- une fois les candidatures, telles que l'agent d'acheminement de document. Pour obtenir des instructions d'installation, voir [installant le .NET Framework] (https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Applications prises en charge Microsoft Office
-   Pour exécuter les compléments Microsoft Excel et de Word, Microsoft Office 2016 pour Windows ou le Mac installé. Pour plus de détails sur les besoins de version, voir [problèmes d'intégration Office] (/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Pour afficher les documents qui sont générés par l'exportation vers Excel ou exportent à la fonctionnalité de Word, Microsoft Office 2007 ou une version ultérieure doit être installé.

## <a name="retail-modern-pos-requirements"></a>Les besoins de Retail Modern POS
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   Le Retail Modern POS est une application de 32 bits, mais il est exécuté sur les architectures x86 ou x64.
-   Le Retail Modern POS est pris en charge uniquement sous Windows 10 les éditions de service à long terme de pro, d'entreprise, et entreprise de branche (LTSB).

### <a name="minimum-system-requirements"></a>Les exigences minimales du système

-   La résolution prise en charge par minimal est le × 1280 1024.
-   L'ordinateur que le Retail Modern POS s'exécute doit répondre à ces conditions :
    -   Il doit avoir, au moins, un processeur de double- noyau exécuté à aucun inférieur à 2 GHz (GHz).
    -   Il doit avoir, au moins, 3 gigas de (GB) de mémoire vive (RAM).
    -   Il doit avoir accès Internet.

## <a name="retail-hardware-station-requirements"></a>Les exigences du détail de station matérielle
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   La station matérielle au détail est une application de 32 bits, mais elle sera exécuté sur les architectures x86 ou x64.
-   La station matérielle au détail est prise en charge des systèmes d'exploitation suivants :
    -   Professionnel de Windows 7, activités, et éditions finales ** note : ** Windows 7 est pris en charge uniquement si Internet Explorer 11 est manuellement installé sur le système.
    -   Professionnel de la mise à jour 1 Windows 8,1, activités, et éditions intégrées
    -   Windows 10 éditions pro, d'entreprise, et d'entreprise LTSB

### <a name="minimum-system-requirements"></a>Les exigences minimales du système

L'ordinateur doit répondre à tous les requise pour installer et d'utilisation des options suivantes :

-   Services Internet (IIS)
-   Tiers matériel

## <a name="retail-store-scale-unit-requirements"></a>Les besoins d'unités d'échelle de magasin de vente au détail
### <a name="supported-operating-systems"></a>Systèmes d'exploitation pris en charge

-   Unité d'échelle de Retail est une application de 32 bits, mais elle sera exécuté sur les architectures x86 ou x64.
-   Unité d'échelle de magasin de vente au détail est prise en charge des systèmes d'exploitation suivants :
    -   Professionnel de Windows 7, activités, et éditions finales
    -   Professionnel de la mise à jour 1 Windows 8,1, activités, et éditions intégrées
    -   Windows 10 éditions pro, d'entreprise, et d'entreprise LTSB

### <a name="minimum-system-requirements"></a>Les exigences minimales du système

-   4 Go de mémoire vive (RAM)
-   1,6 GHz de vitesse du centrales effectués de crête par noyau (deux noyaux sont au minimum.)
-   Au moins 10 gigaoctets de l'espace libre (la base de données des canaux peut nécessiter un grand nombre d'espace.)

### <a name="recommended-system-requirements"></a>Les exigences du système recommandée

-   6 Go de mémoire vive (RAM)
-   2,4 GHz d'i7 (ou équivalent) de vitesse du centrales effectués de crête par noyau (quatre noyaux sont recommandées.)
-   Au moins 10 gigaoctets de l'espace libre (la base de données des canaux peut nécessiter un grand nombre d'espace.)

## <a name="requirements-for-development-on-local-vms"></a>Les exigences pour le développement sur les VMs locales
Pour plus d'informations sur les besoins pour le développement sur les ordinateurs virtuels locaux (VMs), voir [MV exécutant excédentaire locaux] (/dynamics365/operations/dev-itpro/dev-tools/access-instances #vm-that-is-running-in-premises).

<a name="see-also"></a>Voir également :
--------

[Obtenir une copie d'évaluation de Dynamics 365 pour les opérations] (/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


