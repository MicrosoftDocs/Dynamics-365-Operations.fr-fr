---
title: Directives de déploiement pour l’échantillon d’intégration d’imprimante fiscale pour la Pologne (héritées)
description: Cette rubrique fournit des lignes directrices pour le déploiement de l’exemple d’intégration de l’imprimante fiscale pour la Pologne à partir du Kit de développement logiciel de vente au détail (SDK) Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: bff3a6ad74d50e7b706d4df92b17a4a3af36521b
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944813"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Directives de déploiement pour l’échantillon d’intégration d’imprimante fiscale pour la Pologne (héritées)

[!include[banner](../includes/banner.md)]

Cette rubrique fournit des instructions pour le déploiement de l’exemple d’intégration d’imprimante fiscale pour la Pologne à partir du Kit de développement logiciel (SDK) Microsoft Dynamics 365 Commerce Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations sur cet exemple d’intégration fiscale, voir [Exemples d’intégration d’imprimante fiscale pour la Pologne](emea-pol-fpi-sample.md). 

L’échantillon d’intégration fiscale pour la Pologne fait partie du Kit de développement logiciel (SDK) Retail. Pour en savoir plus sur la manière d’installer et d’utiliser le SDK, voir [Architecture du kit de développement logiciel de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Cet exemple se compose d’extensions pour l’environnement de Commerce Runtime (CRT) et la station matérielle. Pour exécuter cet exemple, vous devez modifier et générer les projets CRT et station matérielle. Nous vous recommandons d’utiliser un Kit de développement logiciel (SDK) Retail non modifié pour apporter les modifications décrites dans cette rubrique. Nous vous recommandons également d’utiliser un système de contrôle de source, tel que Azure DevOps, où aucun fichier n’a encore été modifié.

## <a name="development-environment"></a>Environnement de développement

Suivez ces étapes pour configurer un environnement de développement afin de pouvoir tester et étendre l’exemple.

### <a name="commerce-runtime-extension-components"></a>Composants d’extension Commerce Runtime

Les composants d’extension CRT sont inclus dans le Kit de développement logiciel (SDK) Retail. Pour terminer les procédures suivantes, ouvrez la solution **CommerceRuntimeSamples.sln**, sous **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Trouvez le projet **Runtime.Extensions.DocumentProvider.PosnetSample** et le construire.
2. Dans le dossier **Extensions.DocumentProvider.PosnetSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Copiez le fichier d’assembly dans le dossier d’extension CRT :

    - **Commerce Scale Unit :** Copiez le fichier dans le dossier **\\bin\\ext** sous l’emplacement du site Commerce Scale Unit IIS (Internet Information Services).
    - **CRT local sur le PDV moderne :** Copiez le fichier dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Redémarrez le service Commerce :

    - **Commerce Scale Unit :** Redémarrez le site de service Commerce à partir du Gestionnaire IIS.
    - **Courtier client :** Terminer le processus **dllhost.exe** dans le Gestionnaire des tâches, puis redémarrez PDV moderne.

### <a name="hardware-station-extension-components"></a>Composants d’extensions de station matérielle

Les composants d’extension de station matérielle sont inclus dans le Kit de développement logiciel (SDK) Retail. Pour terminer les procédures suivantes, ouvrez la solution **HardwareStationSamples.sln**, sous **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Trouvez le projet **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** et le construire.
2. Dans le dossier **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Copiez le fichier d’assembly sur une machine de station matérielle déployée :

    - **Station matérielle distante :** Copiez le fichier dans le dossier **bin** sous l’emplacement du site de la station matérielle IIS. Copiez les bibliothèques du pilote d’imprimante (**libposcmbth.dll**, **libcmbth\_serial.dll**, et **cmbth\_pl.lng**).

4. Recherchez le fichier de configuration pour les extensions de la station matérielle. Le fichier s’appelle **HardwareStation.Extension.config** :

    - **Station matérielle distante :** Le fichier est situé sous l’emplacement du site de la station matérielle IIS.

5. Ajoutez la ligne suivante à la section **composition** section du fichier de configuration.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Redémarrez le service Station matérielle :

    - **Station matérielle distante :** Redémarrez le site de la station matérielle à partir du Gestionnaire IIS.

## <a name="production-environment"></a>Environnement de production

Dans la procédure précédente, vous avez activé les extensions qui sont des composants de l’exemple d’intégration du service d’enregistrement fiscal. De plus, suivez ces étapes pour créer des packages déployables qui contiennent des composants Commerce et pour appliquer ces packages dans un environnement de production.

1. Apportez les modifications suivantes dans les fichiers de configuration du package sous le dossier **RetailSdk\\Assets** :

    - Dans les fichiers de configuration **commerceruntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** ajoutez la ligne suivante à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - Dans le fichier de configuration **HardwareStation.Extension.config**, ajoutez la ligne suivante à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Apportez les modifications suivantes dans le fichier de configuration de personnalisation du package **Customization.settings**, sous le dossier **BuildTools** :

    - Ajoutez la ligne suivante pour inclure l’extension CRT dans les packages déployables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Ajoutez la ligne suivante pour inclure l’extension de la station matérielle dans les packages déployables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Démarrez l’invite de commande MSBuild pour l’utilitaire Visual Studio et exécutez **msbuild** sous le dossier Kit de développement logiciel (SDK) Retail pour créer des packages déployables.
1. Appliquer les packages via Lifecycle Services (LCS) ou manuellement. Pour plus d’informations, voir [Créer des packages déployables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration d’imprimante fiscale pour la Pologne est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). Pour plus d’informations sur la conception de la solution d’intégration fiscale, voir [Vue d’ensemble de l’exemple de conception d’intégration fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques à l’imprimante et de gérer les réponses de l’imprimante fiscale.

L’extension CRT est **Runtime.Extensions.DocumentProvider.PosnetSample**. Cette extension génère un ensemble de commandes spécifiques à l’imprimante au format JavaScript Object Notation (JSON) qui sont définies par la spécification POSNET 19-3678.

Pour plus d’informations sur la conception de la solution d’intégration fiscale, voir [Processus d’enregistrement fiscal et exemples d’intégration fiscale pour les périphériques fiscaux](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **DocumentProviderPosnetProtocol** est le point d’entrée de la demande de génération de documents à partir de l’imprimante fiscale.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre à l’imprimante qui doit être enregistré dans l’imprimante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : ventes, impression du rapport X et impression du rapport Z.

#### <a name="configuration"></a>Configuration

Le fichier de configuration est situé dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage du fournisseur pour le fournisseur de documents depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- Mise en correspondance des taux de TVA
- Mise en correspondance des types de mode de paiement
- Type de paiement pour les dépôts

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec l’imprimante fiscale.

L’extension de la station matérielle est **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Cette extension appelle les fonctions du pilote POSNET pour soumettre des commandes que l’extension de CRT génère à l’imprimante fiscale. Il gère également les erreurs de périphérique.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **FiscalPrinterHandler** est le point d’entrée pour le traitement de demandes au périphériques fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents aux imprimantes et renvoie une réponse de l’imprimante fiscale.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé se l’appareil.
- **InitializeFiscalDeviceRequest** – Cette requête est utilisée pour l’initialisation de l’imprimante.

#### <a name="configuration"></a>Configuration

Le fichier de configuration se trouve dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage pour le connecteur depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- **Chaîne de connexion** – Une chaîne qui décrit les détails de la connexion au périphérique dans un format pris en charge par le pilote. Pour plus d’informations, voir la documentation sur le pilote POSNET.
- **Synchronisation de la date et de l’heure** – Une valeur qui spécifie si la date et l’heure de l’imprimante doivent être synchronisées avec la station matérielle connectée.
- **Délai d’expiration de l’appareil** – La durée, en millisecondes, pendant laquelle le pilote attendra une réponse de l’appareil. Pour plus d’informations, voir la documentation sur le pilote POSNET.
