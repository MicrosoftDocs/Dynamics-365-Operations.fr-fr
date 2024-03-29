---
title: Directives de déploiement pour l’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque (héritées)
description: Cet article fournit des lignes directrices pour le déploiement de l’exemple d’intégration fiscale pour la République tchèque à partir du Kit de développement logiciel de vente au détail (SDK) Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 08/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7406a6443f851fcfa9757deed57c108ba7b6e069
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473902"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-the-czech-republic-legacy"></a>Directives de déploiement pour l’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque (héritées)

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Vous devez suivre les instructions de cet article uniquement si vous utilisez Microsoft Dynamics 365 Commerce version 10.0.28 ou antérieure. A partir de la version 10.0.29 de Commerce, l’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque est disponible dans le SDK de Commerce. Pour plus d’informations, voir [Configurer les composants du canal](./emea-cze-fi-sample.md#configure-channel-components).

Cet article fournit des instructions pour le déploiement de l’exemple d’intégration de service d’enregistrement fiscal pour la République tchèque à partir du (SDK) de Dynamics 365 Commerce Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations sur cet exemple d’intégration fiscale, voir [Exemples d’intégration du service d’enregistrement fiscal pour la République tchèque](emea-cze-fi-sample.md). 

L’échantillon d’intégration fiscale pour la République tchèque fait partie du Kit de développement logiciel (SDK) Retail. Pour en savoir plus sur la manière d’installer et d’utiliser le SDK, voir [Architecture du kit de développement logiciel de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Cet exemple se compose d’extensions pour l’environnement de Commerce Runtime (CRT) et la station matérielle. Pour exécuter cet exemple, vous devez modifier et générer les projets CRT et station matérielle. Nous vous recommandons d’utiliser un Kit de développement logiciel (SDK) Retail non modifié pour apporter les modifications décrites dans cet article. Nous vous recommandons également d’utiliser un système de contrôle de source, tel que Azure DevOps, où aucun fichier n’a encore été modifié.

## <a name="development-environment"></a>Environnement de développement

Suivez ces étapes pour configurer un environnement de développement afin de pouvoir tester et étendre l’exemple.

### <a name="enable-commerce-runtime-extensions"></a>Activer les extensions de Commerce Runtime

Les composants d’extension CRT sont inclus dans les échantillons CRT. Pour terminer les procédures suivantes, ouvrez la solution **CommerceRuntimeSamples.sln**, sous **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>Composant DocumentProvider.EFRSample

1. Trouvez le projet **Runtime.Extensions.DocumentProvider.EFRSample** et le construire.
2. Dans le dossier **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Commerce Scale Unit :** Copiez le fichier dans le dossier **\\bin\\ext** sous l’emplacement du site Commerce Scale Unit IIS (Internet Information Services).
    - **CRT local sur le PDV moderne :** Copiez le fichier dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>Composant DocumentProvider.DataModelEFR

1. Trouvez le projet **Runtime.Extensions.DocumentProvider.DataModelEFR** et le construire.
2. Dans le dossier **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Commerce Scale Unit :** Copiez le fichier dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Commerce Scale Unit.
    - **CRT local sur le PDV moderne :** Copiez le fichier dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Fichier de configuration d’extension

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

2. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Activer les extensions de connecteur fiscal

Vous pouvez activer les extensions de connecteur fiscal sur la [station matérielle](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) ou le [registre PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

### <a name="enable-hardware-station-extensions"></a>Activer les extensions de station matérielle

Les composants d’extension de station matérielle sont inclus dans les exemples de station matérielle. Pour terminer les procédures suivantes, ouvrez la solution **HardwareStationSamples.sln**, sous **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="efrsample-component"></a>Composant EFRSample

1. Trouvez le projet **HardwareStation.Extension.EFRSample** et le construire.
2. Dans le dossier **Extension.EFRSample\\bin\\Debug**, recherchez les fichiers d’assembly suivants :

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Copiez les fichiers d’assembly dans le dossier des extensions de la station matérielle :

    - **Station matérielle partagée :** Copiez les fichiers dans le dossier **bin** sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle dédiée sur le PDV moderne :** Copiez les fichiers dans l’emplacement du courtier client du PDV moderne.

4. Recherchez le fichier de configuration d’extension pour les extensions de la station matérielle. Le fichier s’appelle **HardwareStation.Extension.config**.

    - **Station matérielle partagée :** Les fichier est situé sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle dédiée sur le PDV moderne :** Le fichier est situé sous l’emplacement du courtier client du PDV moderne.

5. Ajoutez la ligne suivante à la section **composition** section du fichier de configuration.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>Activer les extensions PDV

L’échantillon d’extension PDV se trouve dans le dossier **src\\FiscalIntegration\\PosFiscalConnectorSample** du [référentiel de solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).

Pour utiliser l’exemple d’extension PDV dans l’ancien kit de développement logiciel, procédez comme suit.

1. Copiez le dossier **Pos.Extension** vers le dossier **Extensions** PDV de l’ancien kit de développement logiciel (par exemple, `C:\RetailSDK\src\POS\Extensions`).
1. Renommez la copie du dossier **Pos.Extension** **PosFiscalConnector**.
1. Supprimez les dossiers et fichiers suivants du dossier **PosFiscalConnector** :

    - bin
    - DataService
    - devDependencies
    - Bibliothèques
    - obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Ouvrez la solution **CloudPos.sln** ou **ModernPos.sln**.
1. Dans le projet **Pos.Extensions**, incluez le dossier **PosFiscalConnector**.
1. Ouvrez le fichier **extensions.json** et ajoutez l’extension **PosFiscalConnector**.
1. Générez le kit de développement logiciel.

### <a name="production-environment"></a>Environnement de production

La procédure précédente active les extensions qui sont des composants de l’exemple d’intégration du service d’enregistrement fiscal. De plus, suivez ces étapes pour créer des packages déployables qui contiennent des composants Commerce et pour appliquer ces packages dans un environnement de production.

1. Apportez les modifications suivantes dans les fichiers de configuration du package sous le dossier **RetailSdk\\Assets**.

    - Dans les fichiers de configuration **commerceruntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** ajoutez les lignes suivantes à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsCzechia" />
        ```

    - Dans le fichier de configuration **HardwareStation.Extension.config**, ajoutez la ligne suivante à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        ```

2. Apportez les modifications suivantes dans le fichier de configuration de personnalisation du package **Customization.settings**, sous le dossier **BuildTools**.

    - Ajoutez les lignes suivantes pour inclure les extensions CRT dans les packages déployables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Ajoutez la ligne suivante pour inclure l’extension de la station matérielle dans les packages déployables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample" />
        ```

3. Démarrez l’invite de commande MSBuild pour l’utilitaire Visual Studio et exécutez **msbuild** sous le dossier Kit de développement logiciel (SDK) Retail pour créer des packages déployables.
4. Appliquer les packages via Lifecycle Services (LCS) ou manuellement. Pour plus d’informations, voir [Créer des packages déployables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Effectuez toutes les tâches de configuration requises décrites dans [Configurer Commerce pour la République tchèque](emea-cze-fi-sample.md#set-up-commerce-for-the-czech-republic).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). Pour plus d’informations sur la conception de la solution d’intégration fiscale, voir [Vue d’ensemble de l’exemple de conception d’intégration fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses du service d’enregistrement fiscal.

L’extension CRT est **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Gestionnaire de demandes

Il y a un seul gestionnaire de demandes **DocumentProviderEFRFiscalCZE** pour le fournisseur de documents. Il est utilisé pour générer des documents fiscaux pour le service d’enregistrement fiscal.

Ce gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans le service d’enregistrement fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : les ventes, les dépôts sur compte client et les dépôts sur commande client.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Cette requête renvoie la réponse du service d’enregistrement fiscal. Cette réponse est sérialisée pour former une chaîne afin qu’elle soit prête à être enregistrée.

#### <a name="configuration"></a>Configuration

Le fichier de configuration **DocumentProviderFiscalEFRSampleCzech** se trouve dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage du fournisseur pour le fournisseur de documents depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- Mise en correspondance des taux de TVA
- Groupe TVA par défaut
- Groupe TVA de dépôt

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec le service d’enregistrement fiscal.

L’extension de la station matérielle est **HardwareStation.Extension.EFRSample**. Elle utilise le protocole HTTP ou HTTPS pour soumettre les documents que l’extension CRT génère au service d’enregistrement fiscal. Elle gère également les réponses reçues du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **EFRHandler** est le point d’entrée pour le traitement des demandes au service d’enregistrement fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents au service d’enregistrement fiscal et renvoie une réponse de celui-ci.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé du service d’enregistrement fiscal.
- **InitializeFiscalDeviceRequest** – Cette demande est utilisée pour initialiser le service d’enregistrement fiscal.

#### <a name="configuration"></a>Configuration

Le fichier de configuration se trouve dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage pour le connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- **Adresse du point de terminaison** – L’URL du service d’enregistrement fiscal.
- **Délai d’expiration** –  La durée, en millisecondes, pendant laquelle le connecteur attendra une réponse du service d’enregistrement fiscal.

### <a name="pos-fiscal-connector-extension-design"></a>Design des extensions de connecteur fiscal PDV

L’extension qui est un connecteur fiscal PDV a pour but de communiquer avec le service d’enregistrement fiscal depuis le PDV. Il utilise le protocole HTTPS pour la communication.

#### <a name="fiscal-connector-factory"></a>Paramètres d’usine du connecteur fiscal

La fabrique de connecteurs fiscaux mappe le nom du connecteur à l’implémentation du connecteur fiscal et se trouve dans le fichier **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. Le nom du connecteur doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

#### <a name="efr-fiscal-connector"></a>Connecteur fiscal EFR

Le connecteur fiscal EFR est situé dans le fichier **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Il met en œuvre l’interface **IFiscalConnector** qui prend en charge les requêtes suivantes :

- **FiscalRegisterSubmitDocumentClientRequest** –  Cette demande envoie des documents au service d’enregistrement fiscal et renvoie une réponse de celui-ci.
- **FiscalRegisterIsReadyClientRequest** –  Cette demande est utilisée pour un contrôle de santé du service d’enregistrement fiscal.
- **FiscalRegisterInitializeClientRequest** –  Cette demande est utilisée pour initialiser le service d’enregistrement fiscal.

#### <a name="configuration"></a>Configuration

Le fichier de configuration se trouve dans le dossier **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage pour le connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- **Adresse du point de terminaison** – L’URL du service d’enregistrement fiscal.
- **Délai d’expiration** –  La durée, en millisecondes, pendant laquelle le connecteur attendra une réponse du service d’enregistrement fiscal.
