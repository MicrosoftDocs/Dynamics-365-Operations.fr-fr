---
title: Configuration requise
description: "Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements dans le cloud et sur site."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: fr-fr
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Configuration requise

[!include[banner](../includes/banner.md)]


Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements dans le cloud et sur site. Avant d'installer Finance and Operations, si nécessaire, vérifiez que le système que vous utilisez répond ou excède la configuration minimale requise pour le réseau, le matériel et les logiciels.


## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge
Les applications suivantes Office sont prises en charge dans les déploiements dans le cloud et sur site de Finance and Operations.
-   Pour exécuter les compléments Microsoft Excel et Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus de détails sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Configuration système spécifique requise pour les déploiements dans le cloud
## <a name="network-requirements"></a>Exigences réseau
-   Finance and Operations est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins. C'est la latence entre un client de navigateur et le centre de données Microsoft Azure qui héberge Finance and Operations. Nous vous recommandons de tester la latence du réseau à l'adresse <http://www.azurespeed.com>.
-   Les besoins en bande passante pour Finance and Operations dépendent de votre scénario. La plupart des scénarios habituels nécessitent une bande passante de plus de 50 kilo-octets par seconde (KBps). Toutefois, pour les scénarios qui ont des exigences de charge utile élevées, tels que les espaces de travail ou les scénarios impliquant une personnalisation étendue, une bande passante plus conséquente est recommandée.

De manière générale, Finance and Operations est optimisé pour Internet. Le nombre d'allers-retours entre le client Web et le centre de données Azure est très faible et la charge utile entière est compressée. 

> [!WARNING]
> Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Pour les clients qui s'inquiètent des besoins de bande passante, utilisez une version d'aperçu de Finance and Operations.

## <a name="net-framework-requirements"></a>Exigences.NET Framework
Finance and Operations requiert la version .NET Framework 4.6.2 pour toutes les applications ClickOnce, telles que l'agent d'acheminement de document. Pour obtenir les instructions d'installation, voir [Installation de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Navigateurs Web pris en charge
L'application Web peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :


-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette
-   Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple

Pour trouver la dernière version pour chaque navigateur Web, accédez au site Internet du fournisseur logiciel. 

> [!NOTE]
> -   Une extension Chrome préliminaire doit être installée pour permettre à l'enregistreur de tâches de capturer des images de capture d'écran et de les inclure dans les documents Microsoft Word générés. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   L'éditeur de workflow démarre en tant qu'application ClickOnce. Seuls Microsoft Edge et Internet Explorer (dans une version prise en charge de Microsoft Windows) prennent en charge les applications ClickOnce. L'application ClickOnce d'éditeur de workflow nécessite un système d'exploitation compatible 64 bits.
> -   Le Concepteur de rapports pour les États financiers démarre en tant qu'application ClickOnce. Elle nécessite un système d'exploitation compatible 64 bits. Si vous utilisez Chrome, vous devez installer une extension ClickOnce pour télécharger le client Concepteur de rapports. Si vous utilisez Chrome en mode incognito, vérifiez que l'extension ClickOnce est également activée pour le mode incognito.
> -   Pour afficher un aperçu des fichiers PDF, nous vous recommandons d'utiliser des navigateurs tels que Microsoft Edge (dernière version disponible) sous Windows 10, ou Google Chrome (dernière version disponible) sous Windows 10, Windows 8,1, Windows 8, Windows 7, ou sur la tablette Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Navigateurs Web pris en charge pour Retail Cloud POS

Retail Cloud POS peut s'exécuter dans n'importe lequel des navigateurs Web suivants qui s'exécutent sur les systèmes d'exploitation spécifiés :

-   Microsoft Edge (dernière version publique disponible) sur Windows 10
-   Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
-   Chrome (dernière version publique disponible) sous Windows 10, Windows 8,1 ou Windows 7

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

-   Le connecteur pour Microsoft Dynamics AX a deux programmes d'installation distincts, le **Service Async Server Connector** et le **Service Real-time Service pour Dynamics AX 2012 R3**.
-   Les deux composants sont des applications 32 bits, mais elles fonctionnent aussi bien sur les architectures x86 ou x64.
-   Les deux composants sont pris en charge sur les systèmes d'exploitation suivants :
    -   Windows 7 éditions Professional, Enterprise et Ultimate
    -   Windows 8.1 Update 1 éditions Professional, Enterprise et Embedded
    -   Windows 10 éditions Pro, Enterprise et Enterprise LTSB
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Configuration système minimale

-   2 Go de RAM, 4 Go de RAM recommandés
-   Vitesse de pointe du processeur de 1,6 GHz par cœur (deux cœurs au minimum.)
-   Au moins 10 Go d'espace libre (la base de données des canaux peut nécessiter un espace volumineux.)

## <a name="requirements-for-development-on-local-vms"></a>Exigences pour le développement sur les ordinateurs virtuels locaux
Pour plus d'informations sur les exigences associées au développement sur les ordinateurs virtuels locaux, voir [Ordinateurs virtuels sur site](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Configuration requise pour les déploiements sur site

## <a name="network-requirements"></a>Exigences réseau
Finance and Operations (sur site) peut fonctionner sur les réseaux qui utilisent les protocoles Internet IPv4 ou IPv6. Tenez compte de l'environnement réseau lorsque vous planifiez votre système et utilisez des recommandations suivantes.

### <a name="network-response-time"></a>Temps de réponse réseau
Le tableau suivant répertorie la configuration réseau requise minimale pour la connexion entre le navigateur Web et le serveur d'objets d'application, ainsi que pour la connexion entre AOS et la base de données dans un système sur site.

| Valeur     | Du navigateur Web vers AOS | De la base de données vers AOS                                            |
|-----------|--------------------|------------------------------------------------------------|
| bande passante ; | 50 Ko/s par utilisateur   | 100 Mo/s                                                   |
| Latence   | < 250-300 ms       | < 1 ms (LAN uniquement). AOS et la base de données doivent être coïmplantés. |

- Finance and Operations (sur site) est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins. Cette latence est la latence entre un client de navigateur et le centre de données qui héberge Finance and Operations.
- Les besoins en bande passante pour Finance and Operations (sur site) dépendent de votre scénario. Les scénarios habituels nécessitent une bande passante de plus de 50 ko/s entre le navigateur et le serveur Finance and Operations. Toutefois, pour les scénarios qui ont des exigences de charge utile élevées, tels que les espaces de travail ou les scénarios impliquant une personnalisation étendue, une bande passante plus conséquente est recommandée et dépend de l'utilisation.
Les déploiements dans lesquels la base de données AOS et la base de données SQL Server sont dans des centres de données différents ne sont pas pris en charge. La base de données AOS et SQL Server doivent être coïmplantés. En général Finance and Operations est optimisé pour réduire les allers-retours entre le navigateur et le serveur. Le nombre d'allers-retours entre le client de navigateur et le centre de données est soit égal à zéro, soit égal à un pour chaque interaction utilisateur, et la charge utile entière est compressée.

> [!WARNING]
> Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Nous vous conseillons d'utiliser une simulation en temps réel par rapport à un environnement hors production Finance and Operations comme la meilleure mesure des performances pour votre dossier spécifique. 

### <a name="lan-environments"></a>Environnements LAN
Dans les environnements de réseau local (LAN), Bureau à distance Microsoft dans Microsoft Windows Server n'est pas nécessaire pour se connecter à Finance and Operations. Toutefois, il peut être demandé pour les opérations d'entretien sur les VM qui constituent les déploiements de serveur.

### <a name="wan-environments"></a>Environnements WAN
Dans les environnements de réseau étendu (WAN), Bureau à distance dans Windows Server n'est pas nécessaire pour se connecter à Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Configuration requise pour la connectivité Internet
Finance and Operations (sur site) ne nécessite pas de connectivité Internet de la part des stations de travail de l'utilisateur final. Toutefois, certaines fonctions ne sont pas disponibles sans connexion Internet.

| Client de navigateur | Un scénario Intranet sans connexion Internet est un point de conception pour l'option de déploiement sur site. Certains fonctions qui nécessitent des services dans le cloud ne seront pas disponibles, telles que les bibliothèques d'aide et de guide de tâche dans LCS. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Serveur         | Le niveau d'AOS ou de Service Fabric doit pouvoir communiquer avec LCS. Le client basé sur un navigateur sur site n'a pas besoin d'un accès Internet.                                                                                |
| Télémétrie      | Les données de télémétrie peuvent se perdre en cas de longues interruptions de la connectivité. Les interruptions de la connectivité à LCS n'affectent pas les fonctionnalités de l'application sur site.                                                |
| LCS            | La connectivité à LCS est requise pour les opérations de déploiement, de déploiement de code, et d'entretien.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Transfert des données de télémétrie vers le cloud
La majeure partie de la télémétrie est stockée localement et peut être consultée à l'aide de l'Observateur d'événements de Microsoft Windows. Un petit sous-ensemble d'événements de télémétrie est transféré dans les opportunités de télémétrie de Microsoft dans le cloud à des fins de diagnostic. Les données client et les données d'identification utilisateur final ne font pas partie de la télémétrie envoyée à Microsoft. Les noms des VM sont envoyés à Microsoft pour faciliter la gestion de l'environnement et les diagnostics du portail LCS.

## <a name="domain-requirements"></a>Configuration requise pour le domaine
Tenez compte des exigences suivantes de domaine lorsque vous installez Finance and Operations (sur site) :

- Les machines virtuelles qui hébergent les composants de Finance and Operations (sur site) doivent appartenir à un domaine Active Directory. Les services de domaine Active Directory (AD DS) doivent être configurés en mode natif.
- Les machines virtuelles qui exécutent des composants de Finance and Operations (sur site) doivent accéder les unes aux autres, configurées dans les services de domaine Active Directory. 
- Le contrôleur de domaine doit s'exécuter sous Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Configuration matérielle requise
Cette section décrit le matériel nécessaire à l'exécution de Finance and Operations (sur site).
Selon la configuration système, la composition des données, les applications et les fonctions que vous décidez d'utiliser, la configuration matérielle requise réelle varie. Voici quelques facteurs pouvant affecter le choix du matériel approprié pour Finance and Operations (sur site) :

- Le nombre de transactions par heure.
- Le nombre d'utilisateurs simultanés.

## <a name="minimum-infrastructure-requirements"></a>Configuration minimale de l'infrastructure requise
Finance and Operations (sur site) utilise Microsoft Azure Service Fabric pour héberger les services AOS, de traitement par lots, de gestion des données, Management reporter et d'orchestrateur d'environnement. Microsoft SQL Server Reporting Services (SSRS) n'est pas hébergé dans le cluster Service Fabric.
SQL Server doit être paramétré dans une configuration HADRON à haute disponibilité avec au moins deux nœuds pour l'utilisation de production.
La figure suivante indique le nombre minimal recommandé de nœuds dans le cluster Service Fabric.

[![Nombre recommandé de nœuds du cluster Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Configuration requise pour le processeur et la mémoire
Le tableau suivant répertorie le nombre de processeurs et la quantité de mémoire RAM nécessaires à chacun des rôles requis pour exécuter cette option de déploiement. Pour plus d'informations, lisez les recommandations relatives à la configuration minimale requise pour le cluster Service Fabric autonome, [Planifier et préparer votre cluster Service Fabric autonome](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Si d'autres logiciels Microsoft sont installés sur le même ordinateur, le système doit également être conforme aux exigences matérielles de ce logiciel. Nous vous recommandons de limiter les autres applications de serveur sur le même ordinateur que l'AOS à 1 Go de mémoire RAM.

**Dimensionnement par type de rôle et de topologie**

| Topologie   | Rôle (type de nœud)              | Cœurs de processeur recommandés | Mémoire recommandée (Go) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Production | AOS, gestion des données, traitement par lots   | 8                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |
| Bac à sable    | AOS, gestion des données, traitement par lots   | 4                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |

**Estimations de dimensionnement minimal pour les déploiements de production et de bac à sable**\*

| Topologie                                  | Rôle                          | Nombre d'instances |
|-------------------------------------------|-------------------------------|---------------------|
| Production                                | AOS (gestion des données, traitement par lots)  | 3                   |
|                                           | Management Reporter           | 2                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator\*\*                | 3                   |
| Bac à sable                                   | AOS, gestion des données, traitement par lots   | 2                   |
|                                           | Management Reporter           | 1                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator                  | 3                   |
| *Récapitulatif des topologies de production et de bac à sable* |                               | 16                  |

\*Ces chiffres sont en cours de validation par nos clients d'aperçu et peuvent être ajustés au besoin en fonction de ce commentaire.

\*\*Orchestrator est conçu comme type de nœud principal et sera utilisé pour exécuter les services Service Fabric également.

**Estimations initiales SQL Server et AD principales**

[![Estimations initiales SQL Server et AD principales](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Les tailles SQL Server dépendent grandement des charges de travail. Pour plus d'informations, voir la section [Calibrage de matériel pour les environnements sur site](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Stockage

- **AOS** : Finance and Operations (sur site) utilisera un partage SMB 3.0 pour stocker les données non structurées. Pour plus d'informations, voir [Direction des espaces de stockage direct dans Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** : Options durables :
    - Un paramétrage SSD à haute disponibilité.
    - Un réseau SAN optimisé pour les débits OLTP.
    - Un stockage en attachement direct haute performance 
- **Opérations d'entrée/sortie par seconde pour SQL et la gestion de données** : Le stockage pour la gestion des données et SQL Server doit avoir au moins 2 000 opérations d'entrée/sortie par seconde. Les opérations d'entrée/sortie par seconde de production dépendent de nombreux facteurs. Pour plus d'informations, voir la section « Calibrage de matériel pour les environnements sur site ». 
- **Opérations d'entrée/sortie par seconde de machine virtuelle** : Chaque machine virtuelle doit effectuer au moins 100 opérations d'entrée/sortie par seconde en écriture.

## <a name="virtual-host-requirements"></a>Configuration requise de l'hôte virtuel
Lorsque vous paramétrez les hôtes virtuels pour un environnement Finance and Operations (sur site), consultez les recommandations suivantes : [Planifier et préparer votre cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) et [Description d'un cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Chaque hôte virtuel doit disposer de suffisamment de cœurs pour l'infrastructure calibrée. Plusieurs configurations avancées sont possibles, où SQL Server réside sur le matériel physique mais le reste est virtualisé. Si SQL Server est virtualisé, le sous-système du disque doit être un SAN rapide ou équivalent. Dans tous les cas, assurez-vous que le paramétrage de base de l'hôte virtuel est hautement disponible et redondant. Dans tous les cas, lorsque la virtualisation est utilisée, aucun instantané de machine virtuelle ne doit être pris.

## <a name="software-requirements-for-all-server-computers"></a>La configuration logicielle requise pour tous les ordinateurs de serveur
Les logiciels suivants doivent être présents sur un ordinateur avant que des composants de Finance and Operations (sur site) puissent être installés :

- Microsoft .NET Framework 4.5.1 ou version ultérieure
- Service Fabric Pour plus d'informations, voir [Planifier et préparer votre cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Systèmes d'exploitation serveur pris en charge
Le tableau suivant répertorie les systèmes d'exploitation serveur pris en charge pour les composants Finance and Operations.

| Système d'exploitation                                     | Notes                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter ou Standard | Cette configuration requise concerne la base de données et le cluster Service Fabric qui héberge AOS. |

## <a name="software-requirements-for-database-servers"></a>Configuration logicielle requise pour les serveurs de base de données

- Seules les versions 64 bits de SQL Server 2016 sont prises en charge.
- Dans un environnement de production, nous vous recommandons d'installer la dernière mise à jour cumulative pour la version de SQL Server que vous utilisez.
- Finance and Operations (sur site) prend en charge des classements Unicode qui sont insensibles à la casse, sensibles aux accents, sensibles aux caractères Kana et insensibles à la largeur. Le classement doit correspondre aux paramètres régionaux Windows des ordinateurs qui exécutent des instances AOS. Si vous procédez à une nouvelle installation, nous vous recommandons de sélectionner un classement Windows plutôt que SQL Server. Pour plus d'informations sur la sélection d'un classement pour une base de données SQL Server, voir la [documentation SQL Server](/sql/sql-server/sql-server-technical-documentation).
Le tableau suivant répertorie les versions de SQL Server pris en charge pour les bases de données Finance and Operations. Pour plus d'informations, voir la configuration minimale requise pour [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Besoin                                                      | Notes                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition ou Enterprise Edition | Pour la configuration matérielle minimale de SQL Server 2016, voir [Configuration matérielle et logicielle pour l'installation de SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>La configuration logicielle requise pour tous les ordinateurs client
L'application web Finance and Operations peut être exécutée sur n'importe quel périphérique avec un navigateur web compatible HTML5.0. Les combinaisons de périphérique/navigateur spécifiques confirmées par Microsoft comprennent :

- Microsoft Edge (dernière version publique disponible) sur Windows 10
- Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
- Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette
- Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple

## <a name="software-requirements-for-active-directory-federation-services"></a>Configuration logicielle requise pour les Services ADFS (Active Directory Federation Services) 
Services ADFS (Active Directory Federation Services) sous Windows Server 2016

Le contrôleur de domaine doit être Windows Server 2012 R2 ou version ultérieure avec un niveau de domaine fonctionnel de 2012 R2 ou supérieur

Pour plus d'informations sur les niveaux de domaine fonctionnels, voir : 
- [Quels sont les niveaux fonctionnels d'Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Présentation des niveaux fonctionnels des services de domaine Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Configuration matérielle et logicielle requise pour les composants Retail
Finance and Operations (sur site) n'incluent pas les composants Retail à ce stade.

<a name="see-also"></a>Voir également :
--------

[Obtenir une copie d'évaluation de Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

