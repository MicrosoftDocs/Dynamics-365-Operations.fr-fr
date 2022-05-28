---
title: Déploiement en masse de composants en libre-service Commerce hérités
description: Cette rubrique explique comment utiliser l'infrastructure des programmes d'installation de composants en libre-service pour installer et entretenir en mode silencieux des déploiements.
author: jashanno
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: 5cb27fd0ea366d12c8bd6ee1cdb0c6d584375862
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741561"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Déploiement en masse de composants en libre-service Commerce hérités

[!include [banner](../includes/banner.md)]

Cette rubrique s'applique à l'infrastructure scellée, aux programmes d'installation de composants qui sont publiés chaque mois, à partir de la version 10.0.18, et qui sont mis à disposition dans la bibliothèque de ressources partagées dans Microsoft Dynamics Lifecycle Services (LCS). Notez que les premières versions de ces nouveaux programmes d'installation sont désignées comme **(Version préliminaire)**. Cependant, le seul but de cette désignation est de différencier les nouveaux programmes d'installation tandis que Microsoft détermine s'il existe des exigences fonctionnelles supplémentaires pour les utiliser. Cela ne signifie pas que les programmes d'installation ne sont pas valides pour la production. Sur la base de la publication de ces nouveaux programmes d'installation, Microsoft prévoit de déconseiller les anciens programmes d'installation (hérités) en octobre 2023 ou vers cette date. 

Cette rubrique explique comment utiliser les nouveaux programmes d'installation pour effectuer une installation silencieuse et des mises à jour de maintenance via des arguments de ligne de commande. Ces arguments vous permettent d'effectuer un déploiement de masse de plusieurs manières différentes.

> [!NOTE]
> Les nouveaux programmes d'installation scellés en libre-service ne seront pas disponibles au siège et ne peuvent être téléchargés que via LCS.

## <a name="delimiters-for-mass-deployment"></a>Délimiteurs pour un déploiement en masse

Le tableau suivant montre les délimiteurs qui peuvent être utilisés dans l'exécution de la ligne de commande.


| Séparateur                 | Description |
|---------------------------|-------------|
| --AadTokenIssuerPrefix | Le préfixe de l'émetteur de jetons Microsoft Azure Active Directory (Azure AD). |
| --AsyncClientAadClientId | L'ID client Azure AD que le client asynchrone doit utiliser lors des communications avec Headquarters. |
| --AsyncClientAppInsightsInstrumentationKey | Clé d'instrumentation AppInsights client Async. |
| --AsyncClientCertFullPath | Le chemin d'accès URN entièrement formaté qui utilise l'empreinte numérique comme métrique de recherche de l'emplacement du certificat Async Client Identity qui doit être utilisé pour s'authentifier auprès d'Azure AD pour les communications avec Headquarters. Par exemple, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` est un URN correctement formaté. La valeur **\<MyThumbprint\>** sera remplacé par l'empreinte numérique du certificat qui doit être utilisée. N'utilisez pas ce paramètre conjointement avec le paramètre **-AsyncClientCertThumbprint**. |
| --AsyncClientCertThumbprint | L'empreinte numérique du certificat Async Client Identity qui doit être utilisé pour s'authentifier auprès d'Azure AD pour les communications avec Headquarters. Cette empreinte sera utilisée pour rechercher l'emplacement **LocalMachine/Ma boutique** et le nom pour trouver le bon certificat à utiliser. N'utilisez pas ce paramètre conjointement avec le paramètre **-AsyncClientCertFullPath**. |
| --ClientAppInsightsInstrumentationKey | Clé d'instrumentation AppInsights client Async. |
| --CloudPosAppInsightsInstrumentationKey | Clé d'instrumentation AppInsights client Async. |
| --Config | Le fichier de configuration qui doit être utilisé lors de l'installation. Un exemple de nom de fichier est **Contoso.CommerceScaleUnit.xml**. |
| --CposAadClientId | L'ID client Azure AD que le PDV Cloud doit utiliser lors de l'activation de l'appareil. Ce paramètre n'est pas requis pour les déploiements sur site. |
| --Device | L'ID de l'appareil, tel qu'indiqué sur la page **Périphériques** dans Headquarters. |
| --EnvironmentId | ID d’environnement. |
| --HardwareStationAppInsightsInstrumentationKey | La clé d'instrumentation AppInsights de la station matérielle. |
| --Install | Paramètre qui spécifie si le composant fourni par ce programme d'installation doit être installé. Ce paramètre n’est pas obligatoire. |
| --InstallOffline | Pour Modern POS, ce paramètre spécifie que la base de données hors ligne doit également être installée et configurée. Utilisez le paramètre **-SQLServerName** aussi. Sinon, le programme d'installation essaiera de trouver une instance par défaut qui répond aux prérequis. |
| --Port | Le port qui doit être associé et utilisé par le répertoire virtuel Retail Server. Si aucun port n'est défini, le port par défaut, 443 est utilisé. |
| --Register | L'ID de registre tel qu'indiqué sur la page **Registres** dans Headquarters. |
| --RetailServerAadClientId | L'ID client Azure AD que Retail Server doit utiliser lors des communications avec Headquarters. |
| --RetailServerAadResourceId | L'ID de la ressource d'application Retail Server Azure AD doit être utilisée lors de l'activation de l'appareil. Ce paramètre n'est pas requis pour les déploiements sur site. |
| --RetailServerCertFullPath | Le chemin d'accès URN entièrement formaté qui utilise l'empreinte numérique comme métrique de recherche de l'emplacement du certificat Retail Server Identity qui doit être utilisé pour s'authentifier auprès d'Azure AD pour les communications avec Headquarters. Par example, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` est un URN correctement formaté où la valeur **\<MyThumbprint\>** sera remplacée par l'empreinte numérique du certificat qui doit être utilisée. N'utilisez pas ce paramètre conjointement avec le paramètre **-RetailServerCertThumbprint**. |
| --RetailServerCertThumbprint | L'empreinte numérique du certificat Retail Server Identity qui doit être utilisé pour s'authentifier auprès d'Azure AD pour les communications avec Headquarters. Cette empreinte sera utilisée pour rechercher l'emplacement **LocalMachine/Ma boutique** et le nom pour trouver le bon certificat à utiliser. N'utilisez pas ce paramètre conjointement avec le paramètre **-RetailServerCertFullPath**. |
| --RetailServerURL | L'URL Retail Server que le programme d'installation doit utiliser. (Cette URL est également connue sous le nom de Commerce Scale Unit \[CSU\] URL.) Pour Modern POS, cette valeur sera utilisée lors de l'activation de l'appareil. |
| --SkipAadCredentialsCheck| Un commutateur qui indique si les vérifications préalables des informations d'identification Azure AD doivent être ignorées. La valeur par défaut est **false**. |
| --SkipCertCheck | Un commutateur qui indique si les vérifications préalables du certificat doivent être ignorées. La valeur par défaut est **false**. |
| --SkipIisCheck | Un commutateur qui indique si les vérifications préalables des Services Internet (IIS) doivent être ignorées. La valeur par défaut est **false**. |
| --SkipNetFrameworkCheck | Un commutateur qui indique si les vérifications préalables de .NET Framework doivent être ignorées. La valeur par défaut est **false**. |
| --SkipScaleUnitHealthcheck | Un commutateur qui indique si la vérification de l'état des composants installés doit être ignorée. La valeur par défaut est **false**. |
| --SkipSChannelCheck | Un commutateur qui indique si les vérifications préalables du canal sécurisé doivent être ignorées. La valeur par défaut est **false**. |
| --SkipSqlFullTextCheck | Un commutateur qui indique si la validation du prérequis SQL Server qui nécessite la recherche en texte intégral doit être ignorée. La valeur par défaut est **false**. |
| --SkipSqlServerCheck | Un commutateur qui indique si les vérifications préalables SQL Server doivent être ignorées. La valeur par défaut est **false**. |
| --SqlServerName | Nom du serveur SQL Server. Si le nom n'est pas spécifié, le programme d'installation essaiera de trouver l'instance par défaut. |
| --SslcertFullPath | Le chemin URN entièrement formaté qui utilise l'empreinte comme métrique de recherche de l'emplacement du certificat qui doit être utilisé pour chiffrer le trafic HTTP vers l'unité d'échelle. Par example, `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` est un URN correctement formaté où la valeur **\<MyThumbprint\>** sera remplacée par l'empreinte numérique du certificat qui doit être utilisée. N'utilisez pas ce paramètre conjointement avec le paramètre **-SslCertThumbprint**. |
| --SslCertThumbprint | Empreinte numérique du certificat à utiliser pour chiffrer le trafic HTTP vers l'unité d'échelle. Cette empreinte sera utilisée pour rechercher l'emplacement **LocalMachine/Ma boutique** et le nom pour trouver le bon certificat à utiliser. N'utilisez pas ce paramètre conjointement avec le paramètre **-SslCertFullPath**. |
| --StoreSystemAosUrl | URL Headquarters (AOS). |
| --StoreSystemChannelDatabaseId | ID de base de données du canal (nom). |
| --TenantId | ID de client Azure AD. |
| --TransactionServiceAzureAuthority | L'autorité Azure AD du service des transactions. |
| --TransactionServiceAzureResource | La ressource Azure AD du service des transactions. |
| --TrustSqlServerCertificate | Un commutateur qui indique si le certificat du serveur doit être approuvé lors de l'établissement d'une connexion à SQL Server. Pour éviter les risques de sécurité, les déploiements de production ne doivent jamais fournir une valeur **true** ici. La valeur par défaut est **false**. |
| --Verbosity | Niveau de journalisation demandé lors de l'installation. En règle générale, cette valeur ne doit pas être utilisée. |
| --WindowsPhoneAppInsightsInstrumentationKey | La clé d'instrumentation AppInsights de la station matérielle. |

## <a name="general-overview"></a>Présentation générale

Le nouveau cadre pour les installateurs en libre-service comporte diverses fonctionnalités et améliorations. Le nouveau cadre génère actuellement des programmes d'installation uniquement pour Modern POS, la station matérielle et le CSU (auto-hébergé). Il est important de comprendre l'utilisation de base de la ligne de commande des programmes d'installation scellés, qui devrait ressembler à celle utilisée dans l'exemple suivant. 
 
```Console
<Component Installer Name>.exe install --<Parameter Name> "<Parameter Information>"
```

Le programme d'installation requiert le paramètre **install** (ou alors **uninstall** pour supprimer l'installation) et tous les paramètres spécifiques à cette installation. **Le nom du paramètre** doit inclure tous les paramètres nécessaires tels que le registre, l'URL CSU ou les informations de certificat. **Informations sur les paramètres** doit inclure toute information supplémentaire sur les paramètres.

Le cadre scellé a été créé pour permettre les modifications suivantes :
- **Scellé** – Le nouveau cadre d'installation sépare complètement les installateurs de composants de base distribués par Microsoft des personnalisations basées sur l'extensibilité. Les personnalisations seront installées par la suite mais seront alors non liées aux mises à jour (de sorte que les mises à jour ne seront autorisées que pour le composant de base Microsoft, uniquement pour les personnalisations, ou pour les deux).
- **Sans interface graphique** – Il n'y a plus d'interface utilisateur (UI). Au lieu de cela, il existe un exécutable entièrement piloté par ligne de commande pour chaque programme d'installation de composant. Ce changement est l'un des nombreux changements ou fonctionnalités clés qui sont utilisés pour cibler le nouveau cadre d'installation pour une utilisation avec un déploiement de masse.
- **Journalisation plus approfondie** – Les journaux d'installation améliorés permettent une meilleure validation de l'achèvement ou de l'échec de l'installation, des étapes qui ont été effectuées et des avertissements ou des erreurs qui ont été générés.
- **Nettoyer** - Dans le nouveau cadre, les installateurs de composants travaillent plus dur pour maintenir la propreté des répertoires d'installation, en effaçant tout le contenu du dossier de composants avant d'installer les nouveaux composants. Ce nettoyage garantit qu'il n'y a pas de fichiers restants qui pourraient causer des problèmes et empêcher une installation réussie.

Trois composants n'ont pas été migrés vers le nouveau framework : le simulateur de périphérique virtuel, Async Server Connector Service (utilisé pour Dynamics AX 2012 R3) et le remplacement du service en temps réel (utilisé pour la prise en charge de Dynamics AX 2012 R3).

> [!NOTE]
> Les programmes d'installation sont stockés localement et conservés.  Il est important, au fil du temps, de gérer ou de supprimer les installeurs retenus pour ne pas gaspiller d'espace disque. Il est recommandé de conserver le programme d'installation actuel pour les composants de base et tout programme d'installation d'extension pour les dernières versions à des fins de récupération après des situations extrêmes.

## <a name="migration"></a>Migration

La migration des anciens programmes d'installation de composants de structure en libre-service vers les nouveaux programmes d'installation de composants de structure nécessite la désinstallation des anciens composants.

- **Modern POS** – Le nouveau cadre d'installation a entraîné la réception par l'application d'un nouvel ID de signature d'application. Par conséquent, la désinstallation complète des anciens composants est requise avant l'installation du nouveau composant Framework Modern POS. En raison de l'exigence d'une désinstallation complète, l'activation de l'appareil sera à nouveau requise. (Cette réactivation de l'appareil est une exigence unique, à condition que la désinstallation ne se reproduise pas.)
- **Station matérielle** – En tant que site Web IIS, le nouveau cadre d'installation nécessite que la structure du dossier de base soit retravaillée. Par conséquent, la désinstallation complète des anciens composants est requise avant l'installation du nouveau composant de station matérielle.
- **Commerce Scale Unit (CSU, auto-hébergé)** – En tant que série de sites Web IIS, le nouveau cadre d'installation nécessite que la structure du dossier de base soit retravaillée.  Par conséquent, la désinstallation complète des anciens composants est requise avant l'installation du nouveau composant (auto-hébergé) Framework CSU.

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Avant de commencer

Il est essentiel que vous supprimiez l'ancien composant Modern POS en libre-service. Pour plus d’informations, voir les étapes de migration plus haut dans cette rubrique.

### <a name="examples-of-silent-deployment"></a>Exemples de déploiement silencieux

Cette section montre des exemples de commandes utilisées pour installer Modern POS.

#### <a name="silently-install-modern-pos"></a>Installation de Modern POS en mode silencieux

La commande suivante installe (ou met à jour) en mode silencieux Modern POS. Il possède la structure de commande standard utilisée pour la maintenance silencieuse des composants actuellement installés. La structure utilise les valeurs de base de **&lt;InstallerName&gt;.exe**.

La commande de base suivante présente les options disponibles si une installation est demandée. Il est fortement recommandé d'utiliser cette commande lors du premier test ou de l'utilisation du programme d'installation.

```Console
CommerceModernPOS.exe --help install
```

> [!NOTE]
> Un fichier de configuration n'est pas requis pour Modern POS. Le programme d'installation dispose désormais de paramètres (affichés plus haut dans cette rubrique) pour les différentes valeurs utilisées lors de l'activation de l'appareil.

La commande suivante spécifie tous les paramètres qui doivent être utilisés lors de l'activation de l'appareil après l'installation de l'application Modern POS. Cet exemple utilise le registre **Houston-3**, qui est une valeur couramment utilisée dans les données de démonstration Dynamics 365 Commerce.

```Console
CommerceModernPOS.exe install --Register "Houston-3" --Device "Houston-3" --RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

La commande suivante spécifie les paramètres à utiliser pour installer et configurer la base de données hors ligne. Le serveur SQL est spécifié avec le fichier de configuration qui doit être utilisé.

```Console
CommerceModernPOS.exe install --InstallOffline --SQLServerName "SQLExpress" --Config "ModernPOS.Houston-3.xml"
```

Vous pouvez mélanger et assortir ces concepts pour obtenir les résultats d'installation que vous souhaitez.

## <a name="hardware-station"></a>Station matérielle

### <a name="before-you-begin"></a>Avant de commencer

Il est essentiel que vous supprimiez l'ancien composant de station matérielle en libre-service. Pour plus d’informations, voir les étapes de migration plus haut dans cette rubrique. Il n'y a plus d'outil d'information sur le compte marchand. Au lieu de cela, les informations de compte marchand sont installées lorsqu'un terminal de PDV est couplé avec la station matérielle. Il est fortement recommandé d'utiliser cette commande lors du premier test ou de l'utilisation du programme d'installation.

```Console
CommerceHardwareStation.exe --help install
```

### <a name="examples-of-silent-deployment"></a>Exemples de déploiement silencieux

Cette section montre des exemples de commandes utilisées pour installer la station matérielle.

#### <a name="silently-install-hardware-station"></a>Installation de la station matérielle en mode silencieux

La commande suivante installe (ou met à jour) en mode silencieux la station matérielle. Il a la structure de commande standard qui est utilisée pour entretenir les composants qui sont actuellement installés. La structure utilise les valeurs de base de **&lt;InstallerName&gt;.exe**.

La commande de base suivante exécute le programme d'installation du fichier exécutable.

```Console
HardwareStation.exe install --Port 443 --StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" --StoreSystemChannelDatabaseID "Houston" --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> Un fichier de configuration n'est pas requis pour la station matérielle. Le programme d'installation dispose désormais de paramètres (affichés plus haut dans cette rubrique) pour les différentes valeurs requises.

La commande suivante spécifie tous les paramètres requis pour ignorer les vérifications préalables lors d'une installation standard. 

> [!NOTE]
> Ignorer les vérifications n'est pas recommandé sans des tests approfondis à l'avance ou dans des situations de développement.

```Console
HardwareStation.exe install --SkipFirewallUpdate --SkipOPOSCheck --SkipVersionCheck --SkipURLCheck --Config "HardwareStation.Houston.xml"
```

Comme il est d'usage, il est courant de mélanger et d'assortir ces concepts pour obtenir les résultats d'installation que vous souhaitez.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (auto-hébergé)

Il est fortement recommandé d'utiliser cette commande lors du premier test ou de l'utilisation du programme d'installation.

```Console
CommerceStoreScaleUnitSetup.exe --help install
```

### <a name="before-you-begin"></a>Avant de commencer

Il est essentiel que vous supprimiez l'ancien composant CSU en libre-service (auto-hébergé). Pour plus d’informations, voir les étapes de migration plus haut dans cette rubrique.

### <a name="examples-of-silent-deployment"></a>Exemples de déploiement silencieux

Cette section montre des exemples de commandes utilisées pour installe CSU (auto-hébergé).

#### <a name="silently-install-csu-self-hosted"></a>Installer CSU (auto-hébergé) en mode silencieux

La commande suivante installe (ou met à jour) en mode silencieux CSU (auto-hébergé). Il possède la structure de commande standard utilisée pour la maintenance silencieuse des composants actuellement installés. La structure utilise les valeurs de base de **&lt;InstallerName&gt;.exe**.

Par rapport aux autres installateurs en libre-service, Commerce Scale Unit (CSU) est plus complexe et nécessite une quantité assez importante d'informations supplémentaires. La commande suivante est la commande minimale (avec paramètres) nécessaire pour exécuter le programme d'installation du fichier exécutable lorsqu'aucun fichier de configuration n'est présent.

```Console
CommerceScaleUnit.exe install --port 446 --SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> Un fichier de configuration est toujours requis pour CSU (auto-hébergé).

La commande suivante est une commande plus approfondie qui exécute le programme d'installation du fichier exécutable avec quelques paramètres alternatifs.

```Console
CommerceScaleUnit.exe install --Port 446 --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate --Verbosity 0 --Config "Contoso.StoreSystemSetup.xml"
```

La commande suivante spécifie tous les paramètres requis pour ignorer les vérifications préalables lors d'une installation standard. 

> [!NOTE]
> Ignorer les vérifications n'est pas recommandé sans des tests approfondis à l'avance ou dans des situations de développement.


```Console
CommerceScaleUnit.exe installer --skipscaleunithealthcheck --skipcertcheck --skipaadcredentialscheck --skipschannelcheck --skipiischeck --skipnetcorebundlecheck --skipsqlservercheck --skipnetframeworkcheck --skipversioncheck --skipurlcheck --Config "Contoso.StoreSystemSetup.xml" --SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" --RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" --AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" --RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" --CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" --RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" --TrustSqlServerCertificate
```

Vous pouvez mélanger et assortir ces concepts pour obtenir les résultats d'installation que vous souhaitez.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
