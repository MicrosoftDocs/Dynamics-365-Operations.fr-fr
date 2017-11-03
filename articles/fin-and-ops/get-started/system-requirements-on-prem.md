---
title: "Configuration requise pour les déploiements sur site"
description: "Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements sur site."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 25a6f326c57e84d6a7c356ac5407be7ed3095f83
ms.openlocfilehash: 5edc6f0b2240e9dd2d3b72a13f35e96f016aa013
ms.contentlocale: fr-fr
ms.lasthandoff: 10/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Configuration requise pour les déploiements sur site

[!include[banner](../includes/banner.md)]

Cette rubrique indique la configuration requise pour la version actuelle de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition pour des déploiements sur site. Avant d'installer Finance and Operations, si nécessaire, vérifiez que le système que vous utilisez répond ou excède la configuration minimale requise pour le réseau, le matériel et les logiciels.

## <a name="network-requirements"></a>Exigences réseau
Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (local) peut fonctionner sur les réseaux qui utilisent les protocoles Internet IPv4 ou IPv6. Tenez compte de l'environnement réseau lorsque vous planifiez votre système et utilisez des recommandations suivantes.

### <a name="network-response-time"></a>Temps de réponse réseau
Le tableau suivant répertorie la configuration réseau requise minimale pour la connexion entre le navigateur Web et le serveur d'objets d'application, ainsi que pour la connexion entre AOS et la base de données dans un système sur site.

| Valeur     | Du navigateur Web vers AOS                      | De la base de données vers AOS |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| bande passante ; | 50 kilo-octets par seconde (Ko/s) par utilisateur | 100 mégaoctets par seconde (Mo/s) |
| Latence   | Moins de 250-300 millisecondes (ms)     | Moins de 1 ms (réseau local (LAN) uniquement). AOS et la base de données doivent être coïmplantés. |

- Finance and Operations (sur site) est conçu pour les réseaux ayant une latence inférieure à 250 à 300 millisecondes (ms) ou moins. Cette latence est la latence entre un client de navigateur et le centre de données qui héberge Finance and Operations.
- Les besoins en bande passante pour Finance and Operations (sur site) dépendent de votre scénario. Les scénarios habituels nécessitent une bande passante de plus de 50 ko/s entre le navigateur et le serveur Finance and Operations. Toutefois, une bande passante plus conséquente est recommandée pour les scénarios qui ont des exigences de charge utile élevées, tels que les scénarios impliquant des espaces de travail ou une personnalisation étendue. Le montant spécifique de la bande passante dépend de l'utilisation.

Les déploiements dans lesquels la base de données AOS et la base de données Microsoft SQL Server sont dans des centres de données différents ne sont pas pris en charge. AOS et la base de données SQL Server doivent être coïmplantés. 

En général Finance and Operations est optimisé pour réduire les allers-retours entre le navigateur et le serveur. Le nombre d'allers-retours entre le client de navigateur et le centre de données est soit égal à zéro, soit égal à un pour chaque interaction utilisateur, et la charge utile entière est compressée.

> [!WARNING]
> Ne calculez pas la bande passante d'un emplacement client nécessaire en multipliant le nombre d'utilisateurs par la bande passante minimale requise. Il est très difficile de calculer l'utilisation simultanée d'un emplacement donné. Nous vous recommandons d'utiliser une simulation en temps réel par rapport à un environnement hors production Finance and Operations comme la meilleure mesure des performances pour votre dossier spécifique. 

### <a name="lan-environments"></a>Environnements LAN
Dans les environnements LAN, Bureau à distance Microsoft dans Microsoft Windows Server n'est pas nécessaire pour se connecter à Finance and Operations. Toutefois, Bureau à distance peut être demandé pour les opérations d'entretien sur les machine virtuelles (VM) qui constituent les déploiements de serveur.

### <a name="wan-environments"></a>Environnements WAN
Dans les environnements de réseau étendu (WAN), Bureau à distance dans Windows Server n'est pas nécessaire pour se connecter à Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Configuration requise pour la connectivité Internet
Finance and Operations (sur site) ne nécessite pas de connectivité Internet de la part des stations de travail de l'utilisateur. Toutefois, certaines fonctions ne sont pas disponibles sans connexion Internet.

|                    |   |
|--------------------|---|
| **Client de navigateur** | Un scénario Intranet sans connexion Internet est un point de conception pour l'option de déploiement sur site. Certains fonctions qui nécessitent des services dans le cloud ne seront pas disponibles, telles que les bibliothèques d'aide et de guide de tâche dans Microsoft Dynamics Lifecycle Services (LCS). |
| **Serveur**         | Le niveau d'AOS ou de Microsoft Azure Service Fabric doit pouvoir communiquer avec LCS. Le client basé sur un navigateur sur site n'a pas besoin d'un accès Internet. |
| **Télémétrie**      | Les données de télémétrie peuvent se perdre en cas de longues interruptions de la connectivité. Les interruptions de la connectivité à LCS n'affectent pas les fonctionnalités de l'application sur site. |
| **LCS**            | La connectivité à LCS est requise pour les opérations de déploiement, de déploiement de code, et d'entretien. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Transfert des données de télémétrie vers le cloud
La majeure partie des données télémétriques est stockée localement et peut être consultée à l'aide de l'Observateur d'événements de Microsoft Windows. Un petit sous-ensemble d'événements de télémétrie est transféré dans les opportunités de télémétrie de Microsoft dans le cloud à des fins de diagnostic. Les données client et les données d'identification utilisateur ne font pas partie des données télémétriques envoyées à Microsoft. Les noms des VM sont envoyés à Microsoft pour faciliter la gestion de l'environnement et les diagnostics du portail LCS.

## <a name="domain-requirements"></a>Configuration requise pour le domaine
Tenez compte des exigences suivantes de domaine lorsque vous installez Finance and Operations (sur site) :

- Les VM qui hébergent les composants de Finance and Operations (sur site) doivent appartenir à un domaine Active Directory. Les services de domaine Active Directory (AD DS) doivent être configurés en mode natif.
- Les VM qui exécutent des composants Finance and Operations (local) doivent avoir accès entre eux. Cet accès est configuré dans AD DS. 
- Le contrôleur de domaine doit être Microsoft Windows Server 2012 R2 ou version ultérieure, et le niveau de domaine fonctionnel doit être 2012 R2 ou supérieur

## <a name="hardware-requirements"></a>Configuration matérielle requise
Cette section décrit le matériel nécessaire à l'exécution de Finance and Operations (sur site).

La configuration matérielle requise réelle varie, selon la configuration système, la composition des données, les applications et les fonctions que vous décidez d'utiliser. Voici quelques facteurs pouvant affecter le choix du matériel approprié pour Finance and Operations (sur site) :

- Le nombre de transactions par heure
- Le nombre d'utilisateurs simultanés

## <a name="minimum-infrastructure-requirements"></a>Configuration minimale de l'infrastructure requise
Finance and Operations (sur site) utilise Service Fabric pour héberger les services AOS, de traitement par lots, de gestion des données, Management reporter et d'orchestrateur d'environnement. 

SQL Server doit avoir une configuration HADRON à haute disponibilité avec au moins deux nœuds pour l'utilisation de production.

L'illustration suivante indique le nombre minimal de nœuds recommandé dans le cluster Service Fabric.

[![Nombre recommandé de nœuds du cluster Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Configuration requise pour le processeur et la mémoire
Les tableaux suivants répertorient le nombre de processeurs et la quantité de mémoire RAM nécessaires à chacun des rôles requis pour exécuter cette option de déploiement. Pour plus d'informations, consultez les recommandations relatives à la configuration minimale requise pour le cluster Service Fabric autonome dans [Planifier et préparer votre cluster Service Fabric autonome](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Si d'autres logiciels Microsoft sont installés sur le même ordinateur, le système doit également être conforme aux exigences matérielles de ce logiciel. Si d'autres applications de serveur sont installée sur le même ordinateur que l'AOS, nous vous recommandons de limiter ces applications de serveur à 1 Go de mémoire RAM.

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

**Estimations de dimensionnement minimal pour les déploiements de production et de bac à sable\***

| Topologie                                        | Rôle                          | Nombre d'instances |
|-------------------------------------------------|-------------------------------|---------------------|
| Production                                      | AOS (gestion des données, traitement par lots)  | 3                   |
|                                                 | Management Reporter           | 2                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator\*\*              | 3                   |
| Bac à sable                                         | AOS, gestion des données, traitement par lots   | 2                   |
|                                                 | Management Reporter           | 1                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator                  | 3                   |
| *Récapitulatif des topologies de production et de bac à sable* |                               | *16*                |

\* Ces chiffres sont en cours de validation par nos clients d'aperçu et peuvent être ajustés au besoin en fonction de ce commentaire.

\*\* Orchestrator est conçu comme type de nœud principal et sera utilisé pour exécuter les services Service Fabric également.

**Estimations initiales pour le SQL Server principal et AD DS**

<table>
<thead>
<tr>
<th></th>
<th>Rôle</th>
<th>VM/instances</th>
<th>Noyaux</th>
<th>Nombre total de noyaux</th>
<th>Mémoire par instance (Go)</th>
<th>Mémoire totale (Go)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Infrastructure partagée</strong></td>
<td>SQL Server*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Serveur de fichiers/réseau SAN/stockage hautement disponible</td>
<td colspan="5"><p>Le stockage principal doit être basé sur les SSD sur un réseau SAN d'exécution.</p>
<p>Le débit des opérations de taille et d'entrée-sortie par seconde sont basée sur la taille de la charge de travail.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Synthèse de l'infrastructure partagée</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\*Les tailles SQL Server dépendent grandement des charges de travail. Pour plus d'informations, voir [Calibrage de matériel pour les environnements sur site](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Stockage

- **AOS** : Finance and Operations (sur site) utilise un partage SMB 3.0 pour stocker les données non structurées. Pour plus d'informations, voir [Direction des espaces de stockage direct dans Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** : Les options suivantes sont viables :

    - Un paramétrage SSD hautement disponible
    - Un réseau SAN qui est amélioré pour les débits de traitement des transactions en ligne (OLTP)
    - Un stockage en attachement direct haute performance 

- **Opérations d'entrée/sortie par seconde pour SQL Server et la gestion de données** : Le stockage pour la gestion des données et SQL Server doit avoir au moins 2 000 opérations d'entrée/sortie par seconde. Les opérations d'entrée/sortie par seconde de production dépendent de nombreux facteurs. Pour plus d'informations, voir [Calibrage de matériel pour les environnements sur site](hardware-sizing-on-premises-environments.md).
- **Opérations d'entrée/sortie par seconde de VM** : Chaque VM doit effectuer au moins 100 écritures d'opérations d'entrée/sortie par seconde.

## <a name="virtual-host-requirements"></a>Configuration requise de l'hôte virtuel
Lorsque vous paramétrez les hôtes virtuels pour un environnement Finance and Operations (sur site), voir les recommandations dans [Planifier et préparer votre cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) et [Description d'un cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Chaque hôte virtuel doit disposer de suffisamment de cœurs pour l'infrastructure calibrée. Plusieurs configurations avancées sont possibles, où SQL Server réside sur le matériel physique mais le reste est virtualisé. Si SQL Server est virtualisé, le sous-système du disque doit être un SAN rapide ou équivalent. Dans tous les cas, assurez-vous que le paramétrage de base de l'hôte virtuel est hautement disponible et redondant. Dans tous les cas, lorsque la virtualisation est utilisée, aucun instantané de machine virtuelle ne doit être pris.

## <a name="software-requirements-for-all-server-computers"></a>La configuration logicielle requise pour tous les ordinateurs de serveur
Les logiciels suivants doivent être présents sur un ordinateur avant que des composants de Finance and Operations (sur site) puissent être installés :

- Microsoft .NET Framework 4.5.1 ou version ultérieure
- Service Fabric

Pour plus d'informations, voir [Planifier et préparer votre cluster Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Systèmes d'exploitation serveur pris en charge
Le tableau suivant répertorie les systèmes d'exploitation serveur pris en charge pour les composants Finance and Operations.

| Système d'exploitation                                     | Notes |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter ou Standard | Cette configuration requise concerne la base de données et le cluster Service Fabric qui héberge AOS. |

## <a name="software-requirements-for-database-servers"></a>Configuration logicielle requise pour les serveurs de base de données

- Seules les versions 64 bits de SQL Server 2016 sont prises en charge.
- Dans un environnement de production, nous vous recommandons d'installer la dernière mise à jour cumulative pour la version de SQL Server que vous utilisez.
- Finance and Operations (sur site) prend en charge des classements Unicode qui sont insensibles à la casse, sensibles aux accents, sensibles aux caractères Kana et insensibles à la largeur. Le classement doit correspondre aux paramètres régionaux Windows des ordinateurs qui exécutent des instances AOS. Si vous procédez à une nouvelle installation, nous vous recommandons de sélectionner un classement Windows plutôt que SQL Server. Pour plus d'informations sur la sélection d'un classement pour une base de données SQL Server, voir la [documentation SQL Server](/sql/sql-server/sql-server-technical-documentation).

Le tableau suivant répertorie les versions de SQL Server pris en charge pour les bases de données Finance and Operations. Pour plus d'informations, voir la configuration minimale requise pour [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Besoin                                                      | Notes |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition ou Enterprise Edition | Pour la configuration matérielle minimale de SQL Server 2016, voir [Configuration matérielle et logicielle pour l'installation de SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-application-object-server-aos"></a>Configuration logicielle du Serveur d'objets d'application 
- SQL Server Integration Services (SSIS)

## <a name="software-requirements-for-reporting-server-bi"></a>Configuration logicielle pour le Serveur de génération d'états (BI)
- SQL Server Reporting Services (SSRS)

## <a name="software-requirements-for-client-computers"></a>La configuration logicielle requise pour tous les ordinateurs client
L'application web Finance and Operations peut être exécutée sur n'importe quel périphérique avec un navigateur web compatible HTML 5.0. Voici certaines combinaisons de périphérique/navigateur spécifiques confirmées par Microsoft :

- Microsoft Edge (dernière version publique disponible) sur Windows 10
- Internet Explorer 11 sur Windows 10, Windows 8.1, ou Windows 7
- Google Chrome (dernière version publique disponible) sur Windows 10, Windows 8.1, Windows 8, Windows 7, ou Google Nexus 10 tablette
- Apple Safari (dernière version publique disponible) sur Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra), ou iPad Apple

## <a name="software-requirements-for-active-directory-federation-services"></a>Configuration logicielle requise pour les Services ADFS (Active Directory Federation Services) 
Services ADFS (Active Directory Federation Services) sous Windows Server 2016 est requis.

Le contrôleur de domaine doit être Windows Server 2012 R2 ou version ultérieure, et le niveau de domaine fonctionnel doit être 2012 R2 ou supérieur Pour plus d'informations sur les niveaux de domaine fonctionnels, consultez les pages suivantes :

- [Quels sont les niveaux fonctionnels d'Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Présentation des niveaux fonctionnels des services de domaine Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Applications Microsoft Office prises en charge
Les applications suivantes Microsoft Office sont prises en charge dans les déploiements dans le cloud et sur site de Finance and Operations :

-   Pour exécuter les compléments Microsoft Excel et Microsoft Word, vous devez disposer de Microsoft Office 2016 pour Windows ou Mac. Pour plus d'informations sur les exigences en matière de versions, voir [Dépannage de l'intégration d'Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).
-   Pour afficher les documents qui sont générés par la fonctionnalité Exporter vers Excel ou Exporter vers Word, vous devez disposer de Microsoft Office 2007 ou version ultérieure.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Configuration matérielle et logicielle requise pour les composants Retail
Actuellement, Finance and Operations (sur site) n'inclue pas les composants Retail.

