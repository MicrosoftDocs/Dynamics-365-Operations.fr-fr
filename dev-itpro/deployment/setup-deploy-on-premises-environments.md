---
title: "Paramétrer et déployer les environnements sur site"
description: "Cette rubrique fournit des informations sur la planification, paramétrer, et déployer un environnement des environnements sur site."
author: kfend
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d100f6dbcbdf8f4c12ab04670fb598a88d48d84b
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: fr-fr
ms.lasthandoff: 08/10/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Paramétrer et déployer les environnements sur site

Ce document décrit comment organiser votre déploiement, paramétrez l'infrastructure, et déploiement Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (sur site).

## <a name="finance-and-operations-components"></a>Composants Finance et Operations

L'application Finance and Operations comporte trois composants principaux :

- Serveur d'objets d'application (AOS)
- Business Intelligence (BI)
- Génération d'états financiers/Management Reporter

Ces composants dépendent du logiciel système suivant :

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 SP1, avec les fonctions suivantes :

    - La recherche d'index de recherche en texte intégral est activée.
    - SQL Server Reporting Services(SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > L'application ne fonctionnera pas si la recherche en texte intégral n'est pas activée.

- SQL Server Management Studio
- Microsoft Azure Service Fabric autonome
- Windows PowerShell 5.0 ou version ultérieure
- Services ADFS (Active Directory Federation Services) sous Windows Server 2016

  Le contrôleur de domaine doit être Windows Server 2012 R2 ou version ultérieure avec un niveau de domaine fonctionnel de 2012 R2, ou supérieur

  Pour plus d'informations sur les niveaux de domaine fonctionnels, voir : 
  - [Quels sont les niveaux fonctionnels d'Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Présentation des niveaux fonctionnels des services de domaine Active Directory](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

Les bits Finance et Operations sont distribués via Microsoft Dynamics Lifecycle Services (LCS). Avant de déployer, vous devez acheter des clés de licence via le canal [Accords d'entreprise](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) et paramétrer un projet sur site dans LCS. Les déploiements peuvent être initiés via LCS uniquement. Pour plus d'informations sur le paramétrage des projets sur site dans LCS, voir [Créer un projet sur site dans Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Authentification

L'application sur site utilise AD FS. Pour interagir avec LCS, vous devez également configurer Azure Active Directory (Azure AD).

## <a name="standalone-service-fabric"></a>Service Fabric autonome

Finance and Operations utilise Service Fabric autonome. Pour plus d'informations, voir la [documentation Service Fabric](/azure/service-fabric/).

## <a name="infrastructure"></a>Infrastructure

Finance and Operations est conçue pour utiliser l'architecture hyper-convergée. La configuration matérielle inclut les composants suivants :

- Le cluster Service Fabric autonome est basé sur des machines virtuelles Windows Server 2016 (VM)
- SQL Server (SQL en cluster et Always-On sont pris en charge)
- AD FS pour l'authentification
- Partage de fichier Server Message Block (SMB) version 3 pour le stockage
- Facultatif : Microsoft Office Server 2017

Pour plus d'informations, voir [Configuration requise](../get-started/system-requirements.md) et directive de calibrage.

### <a name="hardware-layout"></a>Mise en page matérielle

Planifier votre infrastructure et votre cluster Service Fabric, selon le dimensionnement recommandé dans [Calibrage de matériel pour les environnements sur site](../get-started/hardware-sizing-on-premises-environments.md). Pour plus d'informations sur la planification du cluster Service Fabric, voir [Planification et préparez du déploiement de votre cluster Service Fabric autonome](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

Le tableau suivant présente un exemple de mise en page matérielle. Cet exemple est utilisé dans toute cette rubrique pour illustrer le paramétrage.

> [!NOTE]
> Le nœud principal du cluster Service Fabric doit avoir au moins trois nœuds. Dans cet exemple, **OrchestratorType** est désigné comme type de nœud principal.

| Objectif de la machine                                 | Nom de la machine    | Adresse IP    |
|-------------------------------------------------|-----------------|---------------|
| Contrôleur de domaine                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Serveur de fichiers                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| Cluster SQL Always-On                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Client                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Cluster Service Fabric /AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Cluster Service Fabric /AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Cluster Service Fabric /AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Cluster Service Fabric /Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Cluster Service Fabric /Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Cluster Service Fabric /Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Cluster Service Fabric/nœud de Management Reporter | SQLAOSMR1       | 10.179.108.18 |
| Cluster Service Fabric /nœud SSRS 1                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Configuration

### <a name="prerequisites"></a>Conditions préalables

Avant de commencer à configurer, les conditions requises suivantes doivent être remplies. Le paramétrage de ces conditions préalables n'est pas traité dans ce document.

- Les services de domaine Active Directory (AD DS) sont installés et configurés dans votre réseau.
- AD FS est déployé.
- SQL Server, SSRS, et Management Studio sont installés.

### <a name="overview"></a>Vue d'ensemble

Les étapes suivantes doivent être effectuées pour paramétrer l'infrastructure pour Finances et Operations.

1. Planifier votre nom de domaine et zones de DNS
2. Planification et acquisition des certificats
3. Planifier vos utilisateurs et comptes de service
4. Créer des zones DNS et ajouter des enregistrements A
5. Associer des VM au domaine
6. Ajouter des logiciels indispensables aux VM
7. Télécharger les scripts de paramétrage de LCS
8. Décrire votre configuration
9. Installer les certificats
10. Paramétrer un cluster Service Fabric autonome
11. Configurer la connectivité de LCS pour le locataire
12. Paramétrer le stockage de fichiers
13. Paramétrer SQL Server
14. Configurer les bases de données
15. Chiffrer des informations d'identification
16. Paramétrage SSRS
17. Configurer AD FS

### <a name="plan-your-domain-name-and-dns-zones"></a>Planifier votre nom de domaine et zones de DNS

Nous vous recommandons d'utiliser un nom de domaine enregistré publiquement pour l'installation de production d'AOS. Ainsi, il est accessible en dehors du réseau, si l'accès extérieur est requis.

Par exemple, si le domaine de votre société est contoso.com, votre région pour Finances et Operations (sur site) peut être d365ffo.onprem.contoso.com, et les noms d'hôte comme suit :

- ax.d365ffo.onprem.contoso.com pour des machines AOS
- sf.d365ffo.onprem.contoso.com pour le cluster Service Fabric

### <a name="plan-and-acquire-your-certificates"></a>Planification et acquisition des certificats

Les certificats SSL (Secure Sockets Layer) sont requis pour sécuriser un cluster Service Fabric et tous les applications qui sont déployées. Pour vos charges de travail de production et de bac à sable, nous vous recommandons d'acquérir les certificats auprès d'une autorité de certification (CA), par exemple [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate) ou [GlobalSign](https://www.globalsign.com/en/ssl/). Si votre domaine est paramétré avec [Services de certificat Active Directory](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (AD CS), vous pouvez créer des certificats via AD CS. Chaque certificat doit contenir une clé privée créée pour l'échange de clés, et il doit être exportable vers un fichier d'échange d'informations personnelles (.pfx).

Les certificats auto-signés ne peuvent être utilisés qu'à des fins de test. Pour plus de commodité, les scripts de paramétrage incluent des scripts qui génèrent et exportent des certificats auto-signés. Comme indiqué, ces certificats doivent être utilisés à des fins de test uniquement.

| Objectif                                      | Explication | Conditions supplémentaires |
|----------------------------------------------|-------------|-------------------------|
| Certificat SSL SQL Server                   | Ce certificat permet de chiffrer les données qui sont transmises sur un réseau entre une instance de SQL Server et une application client. | <p>Le nom de domaine du certificat doit correspondre au nom de domaine complet (FQDN) de l'instance ou du service d'écoute de SQL Server.</p><p>Par exemple, si le service d'écoute SQL est hébergé sur la machine DAX7SQLAOSQLA, le nom DNS du certificat est DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Certificat de serveur Service Fabric            | Ce certificat est utilisé pour aider à sécuriser la communication de nœud-à-nœud entre les nœuds de Service Fabric. Ce certificat est également utilisé comme certificat de serveur présenté au client qui se connecte au cluster. | <p>Le nom de domaine du certificat doit correspondre à la zone de DNS dans laquelle AOS et Service Fabric sont hébergées.</p><p>Par exemple, le nom de domaine du certificat peut être \*.onprem.contoso.com ou \*.contoso.com.</p><p>Si vous utilisez un certificat de caractère générique, le caractère générique s'applique à un seul niveau. Un sous-domaine, autre nom de l'objet (SAN) doit être appliqué au certificat si c'est plusieurs niveaux, par exemple \*.contoso.com dans l'exemple précédent.</p> |
| Certificat de client Service Fabric            | Ce certificat est utilisé par les clients pour afficher et gérer le cluster de Service Fabric. | |
| Certificat de chiffrement                     | Ce certificat permet de chiffrer des informations importantes telles que le mots de passe SQL Server et le mot de passe du compte d'utilisateur. | <p>L'utilisation de clé de certificat doit inclure le chiffrement de données (10) et ne doit pas contenir l'authentification de serveur ou l'authentification client.</p><p>Pour plus d'informations, voir [Gestion des secrets dans les application Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| Certificat SSL Microsoft Dynamics AX Application Object Server (AOS)                          | <p>Ce certificat est utilisé comme certificat de serveur présenté au client pour le site web Microsoft Dynamics AX Application Object Server (AOS). Il est également utilisé pour activer des Windows Communication Foundation (WCF)/SOAP (Simple Object Access Protocol).</p><p>Le certificat du serveur Service Fabric peut être utilisé ici s'il s'agit d'un certificat de caractère générique.</p> | <p>Le nom de domaine du certificat doit correspondre à la zone de DNS dans laquelle AOS et Service Fabric sont hébergées.</p><p>Par exemple, le nom de domaine du certificat peut être \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com, or \*.contoso.com.</p><p>Si vous utilisez un certificat de caractère générique, le caractère générique s'applique à un seul niveau. Un sous-domaine, SAN, doit être appliqué au certificat si c'est plusieurs niveaux, par exemple \*.contoso.com dans l'exemple précédent.</p> |
| Certificat d'authentification de session           | Ce certificat est utilisé par Microsoft Dynamics AX Application Object Server (AOS) pour aider sécurisé des informations de session utilisateur. | C'est également le certificat **Partage de fichier** qui sera utilisé au moment du déploiement de LCS. |
| Certificat de chiffrement de données et de signature de données | Ces certificats sont utilisés par Microsoft Dynamics AX Application Object Server (AOS) pour chiffrer les informations confidentielles. | |
| Certificat de client d'états financiers       | Ce certificat est utilisé pour aider à sécuriser la communication entre les services d'états financiers et Microsoft Dynamics AX Application Object Server (AOS). | |
| Certificat d'état                        | Ce certificat est utilisé pour aider à sécuriser la communication entre SSRS et Microsoft Dynamics AX Application Object Server (AOS). | |
| Certificat d'agent local sur site           | <p>Ce certificat est utilisé pour aider à sécuriser les communications entre un agent local basé sur site et LCS.</p><p>Ce certificat permet à l'agent local d'agir pour le compte de votre locataire Azure AD et pour communiquer avec LCS pour orchestrer et surveiller les déploiements.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Planifier vos utilisateurs et comptes de service

Vous devez créer plusieurs comptes d'utilisateur ou de service pour que Finance et Operations (sur site) fonctionnent. Vous devez créer une combinaison de comptes de service gérés en groupe (gMSAs), de comptes de domaine et de comptes SQL. Le tableau suivant indique les comptes d'utilisateur, leurs objets, et les noms des exemples qui seront utilisés dans cette rubrique.

| Compte utilisateur                                            | Type           | Objectif | Nom d'utilisateur |
|---------------------------------------------------------|----------------|---------|-----------|
| Compte de service d'application d'états financiers         | gMSA           |         | Contoso\\svc-FRAS$ |
| Compte de service de traitement d'états financiers             | gMSA           |         | Contoso\\svc-FRPS$ |
| Compte de service de concepteur en un clic pour les états financiers | gMSA           |         | Contoso\\svc-FRCO$ |
| Compte de service Microsoft Dynamics AX Application Object Server (AOS)                                     | gMSA           | Cet utilisateur doit être créé pour de futures corrections. Nous prévoyons de permettre à Microsoft Dynamics AX Application Object Server (AOS) d'utiliser le gMSA dans les futures versions. En créant cet utilisateur au moment du paramétrage, vous aiderez à garantir une transition transparente vers le gMSA. | Contoso\\svc-AXSF$ |
| Compte de service Microsoft Dynamics AX Application Object Server (AOS)                                     | Compte de domaine | Microsoft Dynamics AX Application Object Server (AOS) utilise cet utilisateur dans la version GA. | Contoso\\AXServiceUser |
| Utilisateur administrateur de base de données SQL Microsoft Dynamics AX Application Object Server (AOS)                                   | Utilisateur SQL       | Finance et Operations utilisent cet utilisateur pour s'authentifier avec SQL\*. Cet utilisateur sera également remplacé par l'utilisateur gMSA dans les futures versions. | AXDBAdmin |
| Compte de service d'agent de déploiement local                  | gMSA           | Ce compte est utilisé par l'agent local pour orchestrer le déploiement sur divers nœuds. | Contoso\\Svc-LocalAgent$ |

\* Le nom d'utilisateur et le mot de passe SQL pour l'authentification SQL sont sécurisés, car ils sont chiffrés et stockés dans le partage de fichiers.

### <a name="create-dns-zones-and-add-a-records"></a>Créer des zones DNS et ajouter des enregistrements A

DNS est intégré à AD DS, et vous permet de planifier, gérer, et rechercher des ressources dans un réseau. Créez une zone de recherche directe DNS et des enregistrements A pour le nom de l'hôte Microsoft Dynamics AX Application Object Server (AOS) et le cluster Service Fabric. Dans cet exemple de paramétrage, le nom de la zone DNS est d365ffo.onprem.contoso.com, et les enregistrements A/noms d'hôte sont les suivants :

- **ax**.d365ffo.onprem.contoso.com pour des machines Microsoft Dynamics AX Application Object Server (AOS)
- **sf**.d365ffo.onprem.contoso.com pour le cluster Service Fabric

#### <a name="add-a-dns-zone"></a>Ajouter une zone DNS

Pour ce faire, procédez comme suit.

1. Connectez-vous à la machine du contrôleur de domaine, cliquez sur **Démarrer**, et démarrez le gestionnaire DNS en saisissant **dnsmgmt.msc**.
2. Cliquez avec le bouton droit sur le nom du contrôleur de domaine, cliquez sur **Nouvelle zone** \> **Suivant**.
3. sélectionner **Zone principale**.
4. Laissez la case à cocher **Stocker la zone dans Active Directory (disponible uniquement si le serveur DNS est un contrôleur de domaine ouvert en écriture** activée, puis cliquez sur **Suivant**.
5. Sélectionnez **Dans tous les serveurs DNS s'exécutant sur les contrôleurs de domaine dans ce domaine : Contoso.com**, puis cliquez sur **Suivant**.
6. Sélectionnez **Zone de recherche directe**, puis cliquez sur **Suivant**.
7. Entrez le nom de la zone de votre paramétrage, puis cliquez sur **Suivant**. Par exemple, entrez **d365ffo.onprem.contoso.com**.
8. Sélectionnez **Ne pas activer les mises à jour dynamiques**, puis cliquez sur **Suivant**.

#### <a name="set-up-an-a-record-for-aos"></a>Paramétree un enregistrement A pour Microsoft Dynamics AX Application Object Server (AOS)

Dans la nouvelle zone DNS, créez un enregistrement A nommé **ax.d365ffo.onprem.contoso.com** pour **chaque** nœud du cluster Service Fabric de type **AOSNodeType**. Ne créez pas d'enregistrements A pour les autres types de nœuds.

1. Cliquez avec le bouton droit sur la nouvelle zone, puis cliquez sur **Nouvel hôte**.
2. Entrez le nom et l'adresse IP du nœud Service Fabric (par exemple 10.179.108.12), puis cliquez sur **Ajouter l'hôte**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Paramétrer un enregistrement A pour Orchestrator

Dans la nouvelle zone DNS, créez un enregistrement A nommé **sf.d365ffo.onprem.contoso.com** pour **chaque** nœud du cluster Service Fabric de type **OrchestratorType**. Ne créez pas d'enregistrements A pour les autres types de nœuds.

1. Cliquez avec le bouton droit sur la nouvelle zone, puis cliquez sur **Nouvel hôte**.
2. Entrez le nom et l'adresse IP du nœud Service Fabric (par exemple 10.179.108.15), puis cliquez sur **Ajouter l'hôte**.

#### <a name="join-vms-to-the-domain"></a>Associer des VM au domaine

Joignez chacune des VM au domaine en suivant les étapes de la [Procédure pour joindre Windows Server 2016 à un domaine Active Directory](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). Sinon, utilisez le script Windows PowerShell.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Une fois que les VM sont associées au domaine, ajoutez les comptes de service Microsoft Dynamics AX Application Object Server (AOS) (Contoso\svc-AXSF$, Contoso\svc-AXSF$) au groupe d'administrateurs locaux. Pour cela, consultez l'article [Ajouter un membre à un groupe local](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx).

#### <a name="disable-user-access-control"></a>Désactiver le contrôle d'accès utilisateur 

Exécutez le script suivant pour désactiver le contrôle d'accès utilisateur sur **chaque** le nœud Service Fabric.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> Vous devez redémarrer le nœud après l'exécution complète du script.

#### <a name="add-prerequisite-software-to-vms"></a>Ajouter des logiciels indispensables aux VM

Le tableau suivant répertorie les logiciels nécessaires à appliquer aux machines de chaque type de nœud.

> [!NOTE]
> Vous devez redémarrer votre ordinateur après avoir installé les composants.

| Type de nœud | Composant | Commande |
|-----------|-----------|---------|
| AOS       | Pilote SNAC – ODBC | Voir [Pilote Microsoft ODBC 13,1 pour SQL Server - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | La version 2.0-3.5 de Microsoft .NET Framework (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | La version 4.0-4.6 de Microsoft .NET Framework (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Services Internet (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Packages redistribuables Microsoft Visual C++ pour Microsoft Visual Studio 2013 | Voir [Packages redistribuables Microsoft Visual C++ pour Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560) |
| AOS       | Composant redistribuable Moteur de base de données Microsoft Access 2010 | Voir [Composant redistribuable Moteur de base de données Microsoft Access 2010](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| BI        | La version 2.0-3.5 de .NET Framework (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| BI        | La version 4.0-4.6 de .NET Framework (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| BI        | Microsoft SQL Server 2016 SP1 | |
| BI        | Management Studio 2016 | |
| BI        | Services de génération d'états financiers SQL Server 2016 en mode **natif** | |
| MR        | La version 2.0-3.5 de .NET Framework (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | La version 4.0-4.6 de .NET Framework (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Packages redistribuables Microsoft Visual C++ pour Visual Studio 2013 | Voir [Packages redistribuables Microsoft Visual C++ pour Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560) |

#### <a name="download-setup-scripts-from-lcs"></a>Télécharger les scripts de paramétrage de LCS

Nous avons fourni plusieurs scripts pour améliorer l'expérience du paramétrage. Procédez comme suit pour télécharger les scripts de paramétrage LCS.

1. Connectez-vous à LCS (<https://lcs.dynamics.com/v2>).
2. Dans le tableau de bord, cliquez sur la vignette **Bibliothèque d'actifs partagés**.
3. Cliquez sur l'onglet **Modèle**.
4. Dans la grille, sélectionnez la ligne **Dynamics 365 for Operations - scripts de déploiement sur site**.
5. Cliquez sur **Versions**, puis téléchargez la dernière version des scripts.

### <a name="describe-your-configuration"></a>Décrire votre configuration

Cette section fournit des informations sur les scripts que vous devez exécuter. Les scripts sont traités dans l'ordre dans lequel vous devez les exécuter. Pour exécuter les scripts, complétez le modèle de fichier à $(downloadPath)\\ConfigTemplate.xml. Le fichier ConfigTemplate.xml décrit les clusters Service Fabric, les certificats utilisés pour les configurer, et les comptes qui doivent bénéficier de l'accès aux certificats pertinents. Dans l'exemple fourni, les valeurs sont renseignées dans l'infrastructure d'exemple décrite dans cette rubrique. Le modèle de fichier sera utilisé dans la section suivante.

#### <a name="create-the-domain-account-for-a-service-user"></a>Créez le compte de domaine d'un utilisateur de service

Exécutez la commande suivante pour créer le compte d'utilisateur de domaine, contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Création de gMSA

1. Modifiez le répertoire avec **$(DownloadPath)**, puis exécutez la commande suivante de Windows PowerShell.

    > [!NOTE]
    > Ce script ne crée pas d'utilisateurs. Au lieu de cela, il imprime les commandes qui doivent être exécutées manuellement sur la machine du contrôleur de domaine.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Copiez la sortie de la commande dans une fenêtre Windows PowerShell. Assurez-vous que les sauts de ligne sont supprimés, puis exécutez les lignes sur la machine du contrôleur de domaine Active Directory à l'aide de privilèges élevés (cliquez avec le bouton droit, puis cliquez sur **Exécuter en tant qu'administrateur**).
3. Exécutez le script suivant sur la machine du contrôleur de domaine Active Directory pour valider les comptes ayant été correctement créés. Assurez-vous que vous exécutez le script après avoir remplacé le modèle qui correspond à la convention d'appellation des comptes de service.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Exécutez le script Export-AddGMSAsONVMScript.ps1 sur la machine client. Ce script génère des scripts qui sont exécutés sur chaque VM Service Fabric et les ajoute à un dossier correspondant à chaque nom de VM.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Arrêter IIS

Utilisez le protocole RDP (Remote Desktop Protocol) pour vous connecter à chaque VM Service Fabric, puis exécutez les étapes manuelles dans [Démarrer ou arrêter le serveur Web (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). Sinon, utilisez le script suivant de Windows PowerShell à l'aide de RDP pour vous connecter à chaque VM Service Fabric.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_La fonction IIS doit être installée mais désactivée, car il existe des dépendances aux dll IIS dans le produit._

### <a name="install-certificates"></a>Installer les certificats

1. Si vous avez acquis des certificats qui étaient répertoriés plus haut dans cette rubrique par une CA valide, entrez le nom et l'empreinte .pfx des certificats dans le fichier ConfigTemplate.xml. Définissez l'attribut **generateSelfSignedCert** sur **Faux** et l'attribut **exportable** sur **Faux**. Copiez les fichiers .pfx dans le dossier $(DownloadPath)\\InfrastructureScripts\\Certs.
2. Si vous utilisez les certificats auto-signés (à des fins de test uniquement), exécutez le script suivant. Pour créer certificats auto-signés, dans le fichier ConfigTemplate.xml, vérifiez que **generateSelfSignedCert** est défini sur **Vrai** et **exportable** sur **Vrai**. Le script mettra le fichier XML à jour avec l'empreinte pour les certificats.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Exportez les nouveaux certificats avec la clé privée (le fichier .pfx). Utilisez le script suivant pour générer et exécuter des commandes d'exportation dans Windows PowerShell. Les fichiers .pfx seront ajoutées dans le dossier Certs.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Les certificats doivent avoir été installés et doivent figurer dans cert:\\CurrentUser\\My. Les certificats doivent également être exportables.

    Si vous utilisez des certificats auto-signés, ignorez la section suivante. Vous n'avez pas besoin d'exécuter cette procédure.

4. Après avoir exporté ou copié les fichiers .pfx dans le dossier $(DownloadPath)\\InfrastructureScripts\\Certs, exécutez les commandes suivantes pour générer les scripts qui seront placés dans les dossiers qui correspondent aux VM.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Copiez les scripts dans chaque dossier des VM qui correspondent au nom de dossier.
6. Sur chaque VM, exécutez les scripts suivants dans l'ordre dans lequel ils s'affichent.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Paramétrer un cluster Service Fabric autonome

1. Exécutez la commande suivante pour générer le fichier ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Pour plus d'informations, voir [Étape 1B : Créer un cluster à plusieurs machines](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [Sécuriser un cluster autonome sur Windows à l'aide de certificats X.509](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security) et [Créer un cluster autonome s'exécutant sous Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Téléchargez le [package d'installation autonome de Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) vers un de vos nœuds Service Fabric. Une fois le fichier zip téléchargé, débloquez-le en cliquant avec le bouton droit sur le fichier zip puis en cliquant sur **Propriétés**. Dans la boîte de dialogue, activez la case à cocher **Débloquer** en bas à droite.
3. Copiez le fichier zip sur l'un des nœuds du cluster Service Fabric, puis décompressez-le.
4. Exécutez les commandes suivantes pour créer une règle de pare-feu entrante sur les ports 443 et 445 dans tous les nœuds.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Exécutez les commandes suivantes pour créer une règle de pare-feu entrante sur le port 80 pour le nœud SSRS uniquement.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Copiez votre fichier ClusterConfig.json à l'emplacement d'installation décompressé de Service Fabric autonome.
7. Accédez à l'emplacement d'installation décompressé dans Windows PowerShell à l'aide de privilèges élevés, puis exécutez la commande suivante pour tester ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Si le test réussit, exécutez la commande suivante pour déployer le cluster.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Une fois le cluster créé, ouvrez l'Explorateur Service Fabric sur n'importe quelle machine client pour valider l'installation :

    1. Installez le certificat client Service Fabric dans CurrentUser\\My, s'il n'est pas déjà installé.
    2. Accédez à **Paramètres IE** \> **Mode de compatibilité**, puis désactivez la case à cocher **Afficher les sites Intranet en mode de compatibilité**.
    3. Accédez à `https://sf.d365ffo.onprem.contoso.com:19080`, où sf.d365ffo.onprem.contoso.com est le nom de l'hôte du cluster Service Fabric spécifié dans la zone. Si la résolution du nom DNS n'est pas configurée, utilisez l'adresse IP de la machine.
    4. Sélectionnez le certificat client. La page **Explorateur Service Fabric** s'affiche.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Configurer la connectivité de LCS pour le locataire

Le déploiement et la tenue à jour de Finance et Operations sont orchestrés via LCS à l'aide d'un agent locale sur site. Pour établir la connectivité entre LCS et le locataire de Finance et Operations, vous devez configurer un certificat qui permet à l'agent local d'agir pour le compte à votre locataire Azure AD (par exemple, Contoso.Onmicrosoft.com).

Utilisez le certificat d'agent sur site acquis auprès d'une CA ou le certificat auto-signé que vous avez généré à l'aide des scripts.

Seuls les comptes utilisateur qui disposent du rôle du répertoire Administrateur global peuvent ajouter des certificats pour autoriser LCS. Par défaut, la personne qui s'inscrit à Microsoft Office 365 pour votre organisation sera l'administrateur global du répertoire.

> [!NOTE]
> Vous devez configurer le certificat précisément une fois par un locataire. Tous les environnements locaux peuvent utiliser le même certificat pour se connecter à LCS.

1. Téléchargez et installez la dernière version d'Azure PowerShell sur une machine client. Pour plus d'informations, voir [Installer et configurer Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Connexion au [portail Azure du client](https://portal.azure.com) pour vérifier que vous disposez du rôle de répertoire Administrateur global.
3. Exécutez le script suivant dans $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Paramétrez le stockage de fichiers

Vous devez paramétrer deux partages de fichiers SMB 3.0 hautement disponibles. Pour plus d'informations sur l'activation de SMB 3.0, voir[Améliorations de la sécurité de SMB](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
La négociation de dialecte sécurisée ne peut pas détecter ou empêcher les rétrogradations de SMB 2.0 ou 3.0 vers SMB 1.0. Pour cette raison, et pour tirer parti des capacités complètes du chiffrement SMB, nous vous recommandons vivement de désactiver le serveur SMB 1.0

> [!NOTE]
> Pour vous assurer que vos données sont protégées lorsqu'elles sont au repos dans votre environnement, BitLocker Drive Encryption doit être activé sur chaque machine. Pour plus d'informations sur l'activation de BitLocker, voir [BitLocker : procédure de déploiement sur Windows Server 2012 et versions ultérieures](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Un partage de fichiers qui stocke les documents utilisateur qui sont téléchargés dans Microsoft Dynamics AX Application Object Server (AOS) (par exemple, \\\\DAX7SQLAOFILE1\\aos-storage).
- Un partage de fichiers qui stocke le build et les fichiers de configuration les plus récents pour orchestrer le déploiement (par exemple, \\\\DAX7SQLAOFILE1\\agent))

    > [!NOTE]
    > Conservez ce chemin d'accès au partage de fichiers aussi court que possible pour éviter de dépasser la longueur de chemin d'accès maximale sur les fichiers qui seront mis dans le partage.

1. Sur la machine du partage de fichiers, exécutez la commande suivante.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Paramétrez le partage de fichiers \\\\DAX7SQLAOFILE1\\aos-storage

2. Dans le Gestionnaire de serveur, sélectionnez **Fichier et services de stockage** \> **Partages**.
3. Cliquez sur **Tâches** \> **Nouveau partage** pour créer un partage avec le nom **aos-storage**.
4. Accordez les autorisations **Modifier** pour chaque machine du cluster Service Fabric excepté **OrchestratorNodeType**.
5. Accordez les autorisations **Modifier** pour l'utilisateur du domaine Microsoft Dynamics AX Application Object Server (AOS) (contoso\\AXServiceUser) et l'utilisateur de gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Paramétrez le partage de fichiers de l'agent \\\\DAX7SQLAOFILE1\\

6. Revenez au Gestionnaire de serveur, sélectionnez **Fichier et services de stockage** \> **Partages**.
7. Cliquez sur **Tâches** \> **Nouveau partage** pour créer un partage avec le nom **agent**.
8. Accordez les autorisations **Contrôle total** à l'utilisateur de gMSA pour l'agent de déploiement local (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Paramétrer SQL Server

1. Installez le serveur SQL Server 2016 SP1 avec haute disponible, comme des clusters SQL qui incluent un réseau (SAN) ou dans une configuration Always-On.  Vérifiez que **Moteur de base de données, services de génération d'états, recherche de texte intégral** et **Outils de gestion** sont déjà installés.
> [!NOTE]
> Assurez-vous que SQL Always-On est paramétré conformément à la [page Sélectionner la synchronisation de données initiale (Assistants de groupe de disponibilité Always-On)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) et suivez [Pour préparer des bases de données secondaires manuellement](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Exécutez le service SQL en tant qu'utilisateur de domaine.
3. Obtenez un certificat SSL d'une CA pour configurer Finance et Operations. A des fins de test, vous pouvez créer et utiliser un certificat auto-signé.

**Certificat auto-signé pour l'instance SQL mise en cluster**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Certificat auto-signé pour l'instance SQL Always-On**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. A l'aide du certificat, effectuez les étapes de [Procédure d'activation du chiffrement SSL pour une instance de SQL Server à l'aide de la console Microsoft Management](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) pour configurer SSL sur SQL Server.
5. Pour chaque nœud du cluster, procédez comme suit. Assurez-vous que vous apportez les modifications sous le nœud inactif et que vous basculez vers celui-ci une fois les modifications apportées.

    1. Importez le certificat dans LocalMachine\\My.
    2. Accordez des autorisations de certificat au compte de service utilisé pour exécuter le service SQL. Dans la console Microsoft Management (MMC), cliquez avec le bouton droit sur le certificat (certlm.msc), puis cliquez sur **Tâches** \> **Gérer les clés privées**.
    3. Ajoutez l'empreinte de certificat à HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate.
    4. Dans le gestionnaire de configuration Microsoft SQL Server, définissez **ForceEncryption** sur **Oui**.

6. Exportez la clé publique du certificat (le fichier .cer), et installez-la dans la racine de confiance de chaque nœud Service Fabric.

### <a name="configure-the-orchestratordata-database"></a>Configurer la base de données OrchestratorData

1.  Créez une base de données vide et nommez-la **OrchestratorData**. Cette base de données est utilisée par l'agent local sur site pour orchestrer des déploiements.
2.  Accordez les autorisations (svc-LocalAgent$) **DB\_owner** gMSA de l'agent local dans la base de données :

    1. Dans l'arborescence, développez le nom du serveur, développez **Sécurité** \> **Connexions**, puis cliquez avec le bouton droit et cliquez sur **Nouvelle connexion**.

        ![Commande Nouvelle connexion](./media/OPSetup_01_NewLogin.png)


    2. Recherchez le compte de service **svc-LocalAgent$**. Cliquez sur **Emplacements**, sélectionnez **Répertoire entier**, puis cliquez sur **Types d'objet** et sélectionnez **Compte de service**.

        ![Sélectionnez la boîte de dialogue Utilisateur, Compte de service ou Groupe](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Définissez **Affecter ServerRole** sur **Public**.
    4. Affectez l'autorisation de rôle de base de données **db\_owner** à la base de données OrchestratorData.

### <a name="configure-the-finance-and-operations-database"></a>Configurer la base de données Finance and Operations

1. Connectez-vous à LCS (<https://lcs.dynamics.com/v2>).
2. Dans le tableau de bord, cliquez sur la vignette **Bibliothèque d'actifs partagés**.
3. Cliquez sur l'onglet **Modèle** 
4. Dans la grille, cliquez sur la ligne **Dynamics 365 for Finance and Operations, édition Enterprise (sur site) - données de démonstration** pour télécharger le zip.
5. Le zip contient des fichiers .bak de données vides et de démonstration. Selon vos besoins, sélectionnez le fichier .bak approprié. Par exemple, si vous avez besoin de données de démonstration, restaurez le fichier AxBootstrapDB_Demodata.bak. 
6. Restaurez la base de données AxBootstrapDB_DemoData.bak.
7. Renommez la base de données **AXDBRAIN**.
8. Exécutez les requêtes suivantes dans la base de données restaurée.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Mettez à jour les fichiers de la base de données :

    1. Cliquez avec le bouton droit sur la base de données, puis sur **Propriétés**.
    2. Cliquez sur **Fichiers** pour modifier les propriétés du fichier de base de données.
    3. Dans le champ **Taille initiale (Mo)**, entrez une valeur supérieure à 5 120.

        ![Boîte de dialogue Propriétés de la base de données](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. Pour **AXDBBuild\_Data**, définissez le champ **Croissance automatique/optimisation** sur **200** méga-octets (Mo).
    5. Pour **AXDBBuild\_Log**, définissez le champ **Croissance automatique/optimisation** sur **500** Mo.

        ![Modifiez la boîte de dialogue Croissance automatique](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Créez un utilisateur qui dispose de l'authentification SQL activée (axdbadmin).
6. Utilisez les informations du tableau suivant pour mettre en correspondance les utilisateurs et les rôles de la base de données.

    | Utilisateur             | Type    | Rôle de la base de données |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Octroyez à l'utilisateur svc-AXSF$ et à l'utilisateurs SQL axdbadmin un accès aux rôles de la base de données tempdb :

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. Dans Management Studio, exécutez les commandes T-SQL (Transact SQL) suivantes :

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Exécutez la commande suivante :
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Configurez la base de données de génération d'états financiers

1.  Créez une base de données vide et nommez-la **FinancialReporting**.
2.  Utilisez les informations du tableau suivant pour mettre en correspondance les utilisateurs et les rôles de la base de données.

    | Utilisateur             | Type | Rôle de la base de données |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Chiffrer des informations d'identification

1. Dans toute machine client, installez le certificat de chiffrement dans le magasin de certificats LocalMachine\\My.
2. Accordez à l'utilisateur actuel un accès en lecture à la clé privée de ce certificat.
3. Créez un fichier Credentials.json comme indiqué ici.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** est le mot de passe utilisateur du domaine chiffré pour l'utilisateur de domaine Microsoft Dynamics AX Application Object Server (AOS) (contoso\\axserviceuser).
    - **SqlUser** est l'utilisateur SQL chiffré (axdbadmin) ayant accès à la base de données Finances et Operations (AXDBRAIN), et **SqlPassword** est le mot de passe SQL chiffré.

4. Copiez le fichier .json dans le partage de fichiers SMB, \\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json.
5. Metez à jour le fichier Credentials.json avec des valeurs chiffrées.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. Dans Credentials.json, remplacez **\<encryptedDomainUserPassword\>** par le mot de passe de domaine chiffré.
    2. Remplacez **\<encryptedSqlUser\>** par l'utilisateur SQL Finance et Operations chiffré.
    3. Remplacez **\<encryptedSqlPassword\>** par le mot de passe SQL Finance et Operations.
    
### <a name="set-up-ssrs"></a>Paramétrage SSRS

1.  Avant de commencer, vérifiez que les conditions préalables répertoriés au début de cette rubrique sont installées.
2.  Procédez comme suit pour [Configurer SQL Server Reporting Services pour un déploiement sur site](../analytics/configure-ssrs-on-premises.md).

### <a name="configure-ad-fs"></a>Configurer AD FS

Avant d'exécuter cette procédure, AS FS doit être déployé sous Windows Server 2016. Pour plus d'informations sur le déploiement d'AD FS, voir [le guide de déploiement Windows Server 2016 et 2012 R2, et le guide de déploiement d'AD FS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

Finance et Operations requiert une configuration supplémentaire en plus de la configuration prête à l'emploi par défaut d'AD FS. Pour les étapes suivantes, Windows PowerShell s'exécute sur une machine sur laquelle le service de rôle AD FS est installé. Le compte utilisateur doit disposer d'autorisations suffisantes pour administrer AD FS. Par exemple, l'utilisateur doit disposer d'un compte d'administrateur de domaine.

1. Configurez l'identificateur AD FS afin qu'il corresponde à l'émetteur de jeton d'AD FS.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Vous devez désactiver l'authentification intégrée Windows pour les connexions d'authentification Intranet à moins que vous ayez configuré AD FS pour les environnements mixtes. Pour plus d'informations sur la configuration de l'authentification intégrée Windows afin qu'elle puisse être utilisée avec l'AD FS, voir [Configurer des navigateurs pour utiliser l'authentification intégrée Windows avec AD FS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. Pour se connecter, l'adresse e-mail de l'utilisateur doit être une entrée d'authentification acceptable.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Pour qu'AD FS approuve Finance et Operations pour l'échange d'authentification, différentes entrées d'application doivent être enregistrées dans AD FS sous un groupe d'applications AD FS. Pour accélérer le processus de paramétrage et minimiser les erreurs, vous pouvez utiliser le script suivant pour l'enregistrement. Copiez le script Publish-ADFSApplicationGroup.ps1 et le répertoire D365FO-OP sur une machine ayant le rôle de service AD FS installé. Exécutez ensuite le script à l'aide d'un compte utilisateur, tel qu'un compte d'administrateur, qui dispose de suffisamment d'autorisations pour administrer AD FS. Pour plus d'informations sur l'utilisation du script, voir la documentation répertoriée dans le script. Notez les ID client spécifiés dans la sortie, car vous devrez confirmer ces informations dans LCS dans une étape ultérieure.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

La console de gestion AD FS doit ressembler à ce qui suit. Pour ouvrir le Gestionnaire de serveur, cliquez sur **Outils** \> **Gestion d'AD FS**, puis, au bas de la vue arborescente de gauche, cliquez sur **Groupes d'applications**. Double-cliquez sur le groupe d'applications pour afficher plus de détails.

![Propriétés du groupe d'applications](./media/OPSetup_05_ApplicatioGroupProperties.png)

Enfin, pour une vérification de la validité, assurez-vous que vous pouvez accéder à l'URL de configuration OpenID d'AD FS sur un nœud Service Fabric du type **AOSNodeType** en accédant à `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` dans un navigateur web. Si vous recevez un message indiquant que le site n'est pas sécurisé, vous n'avez pas encore ajouté votre certificat SSL AD FS au magasin des autorités de certification racines de confiance. Cette étape est décrite dans le Guide de déploiement d'AD FS. Si vous accédez à l'URL, un fichier JSON (JavaScript Object Notation) est retourné qui contient la configuration de votre AD FS et vous voyez que votre URL AD FS est approuvée.

Ainsi, le paramétrage de l'infrastructure est terminé. Les sections suivantes décrivent comment explorer [LCS](https://lcs.dynamics.com) pour configurer votre connecteur et déployer votre environnement Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Configurez le connecteur et installez l'agent locale sur site

1. Connectez-vous à [LCS](https://lcs.dynamics.com/) et ouvrez le projet de mise en œuvre sur site.
2. Dans le menu Hamburger, cliquez sur **Paramètres du projet**.

    ![Commande des paramètres du projet](./media/OPSetup_06_ProjectSettings.png)

3. Cliquez sur **Connecteurs sur site**.
4. Cliquez sur **Ajouter** pour créer un connecteur.
5. Dans l'onglet **Configurer l'infrastructure de l'hôte**, téléchargez le programme d'installation de l'agent.

    ![Téléchargez le bouton du programme d'installation de l'agent dans l'onglet Configurer l'infrastructure de l'hôte.](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Vérifiez si que le fichier zip est déverrouillé. Cliquez avec le bouton droit sur le fichier, cliquez sur **Propriétés**, puis sur **Déverrouiller**.
7. Décompressez le programme d'installation de l'agent sur l'un des nœuds Service Fabric de type **OrchestratorType**.
8. Dans l'onglet **Configurer l'agent**, entrez les paramètres de configuration.
9. Enregistrez la configuration, puis cliquez sur **Télécharger les configurations** pour télécharger le fichier de configuration localagent-config.json.

    ![Téléchargez le bouton des configurations sous l'onglet Configurer l'agent](./media/OPSetup_08_DownloadConfigurations.png)

10. Copiez le fichier localagent-config.json sur la machine sur laquelle se situe le module du programme d'installation de l'agent.
11. Dans une fenêtre d'invite de commande, exécutez la commande suivante en accédant au dossier qui contient le programme d'installation de l'agent.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > L'utilisateur qui exécute cette commande doit disposer des autorisations **db\_owner** sur la base de données OrchestratorData.
    
12. Une fois l'agent local installé, revenez à connecteur sur site dans LCS.
13. Sous l'onglet **Valider le paramétrage**, cliquez sur le bouton **Agent de message**. Cela testera la connectivité entre LCS et votre agent local. Lorsque la connexion est établie, la page ressemble au graphique ci-dessous.

     ![Valider l'agent](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Déployer votre environnement Dynamics 365 for Finance and Operations (sur site)

1. Accédez à votre projet sur site dans LCS, accédez à **Environnement**, **Bac à sable** et cliquez sur **Configurer**
2. Sélectionnez votre **Topologie de l'environnement** et exécutez l'Assistant pour initier votre déploiement.
3. L'agent local collectera la demande de déploiement, lancera celui-ci et communiquera à nouveau avec LCS une fois prêt.

