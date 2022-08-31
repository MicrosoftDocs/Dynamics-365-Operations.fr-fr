---
title: Directives de déploiement pour l’échantillon d’intégration d’unité de contrôle pour la Suède (héritées)
description: Cet article fournit des lignes directrices pour le déploiement de l’exemple d’intégration d’unité de contrôle pour la Suède à partir du Kit de développement logiciel Retail (SDK)
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: fcc35a2203641b24fe4edd2ab34f2e4d5db9bb53
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324295"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Directives de déploiement pour l’échantillon d’intégration d’unité de contrôle pour la Suède (héritées)

[!include [banner](../includes/banner.md)]

Cet article fournit des instructions pour le déploiement de l’exemple d’intégration d’unité de contrôle pour la Suède à partir du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations sur cet exemple d’intégration fiscale, voir [Exemples d’intégration d’unité de contrôle pour la Suède](emea-swe-fi-sample.md). 

L’échantillon d’intégration fiscale pour la Suède fait partie du Kit de développement logiciel (SDK) Retail. Pour en savoir plus sur la manière d’installer et d’utiliser le SDK, voir [Architecture du kit de développement logiciel de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Cet exemple se compose d’extensions pour l’environnement de Commerce Runtime (CRT) , la station matérielle et le point de vente (PDV). Pour exécuter cet exemple, vous devez modifier et générer les projets CRT, station matérielle et PDV. Nous vous recommandons d’utiliser un Kit de développement logiciel (SDK) Retail non modifié pour apporter les modifications décrites dans cet article. Nous vous recommandons également d’utiliser un système de contrôle de source, tel que Azure DevOps, où aucun fichier n’a encore été modifié.

## <a name="development-environment"></a>Environnement de développement

Suivez ces étapes pour configurer un environnement de développement afin de pouvoir tester et étendre l’exemple.

### <a name="enable-crt-extensions"></a>Activer les extensions CRT

Les composants d’extension CRT sont inclus dans les échantillons CRT. Pour terminer les procédures suivantes, ouvrez la solution **CommerceRuntimeSamples.sln**, sous **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>Composant DocumentProvider.CleanCashSample

1. Trouvez le projet **Runtime.Extensions.DocumentProvider.CleanCashSample** et le construire.
2. Dans le dossier **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Commerce Scale Unit :** Copiez le fichier dans le dossier **\\bin\\ext** sous l’emplacement du site Commerce Scale Unit IIS (Internet Information Services).
    - **CRT local sur le PDV moderne :** Copiez le fichier dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Fichier de configuration d’extension

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **commerceruntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

2. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Activer les extensions de station matérielle

Les composants d’extension de station matérielle sont inclus dans les exemples de station matérielle. Pour terminer les procédures suivantes, ouvrez la solution **HardwareStationSamples.sln**, sous **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>Composant CleanCash

1. Trouvez le projet **HardwareStation.Extension.CleanCashSample** et le construire.
2. Dans le dossier **Extension.CleanCashSample\\bin\\Debug**, recherchez les fichiers d’assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** et **Interop.CleanCash\_1\_1.dll**.
3. Copiez les fichiers d’assembly dans le dossier des extensions de la station matérielle :

    - **Station matérielle partagée :** Copiez les fichiers dans le dossier **bin** sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle dédiée sur le PDV moderne :** Copiez les fichiers dans l’emplacement du courtier client du PDV moderne.

4. Recherchez le fichier de configuration d’extension pour les extensions de la station matérielle. Le fichier s’appelle **HardwareStation.Extension.config**.

    - **Station matérielle partagée :** Les fichier est sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle dédiée sur le PDV moderne :** Le fichier est sous l’emplacement du courtier client du PDV moderne.

5. Ajoutez la ligne suivante à la section **composition** section du fichier de configuration.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Activer les composants d’extension PDV moderne

1. Ouvrez la solution **ModernPOS.sln** sous **RetailSdk\\POS** et assurez-vous qu’il peut être compilé sans erreur. De plus, assurez-vous que vous pouvez exécuter le PDV moderne de Visual Studio en utilisant la commande **Exécuter**.

    > [!NOTE]
    > Le ODV moderne ne doit pas être personnalisé. Vous devez activer le contrôle de compte d’utilisateur (UAC) et vous devez désinstaller les instances précédemment installées du PDV moderne si nécessaire.

2. Activer le chargement des extensions en ajoutant les lignes suivantes au fichier **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Pour plus d’informations et pour des exemples montrant comment inclure des dossiers de code source et permettre le chargement d’extensions, consultez les instructions du fichier readme.md dans le projet **Pos.Extensions**.

3. Recréez la solution.
4. Exécutez le PDV moderne dans le débogueur et testez la fonctionnalité.

### <a name="enable-cloud-pos-extension-components"></a>Activer les composants d’extension PDV de cloud

1. Ouvrez la solution **CloudPOS.sln** sous **RetailSdk\\POS** et assurez-vous qu’il peut être compilé sans erreur.
2. Activer le chargement des extensions en ajoutant les lignes suivantes au fichier **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Pour plus d’informations et pour des exemples montrant comment inclure des dossiers de code source et permettre le chargement d’extensions, consultez les instructions du fichier readme.md dans le projet **Pos.Extensions**.

3. Recréez la solution.
4. Exécutez la solution en utilisant la commande **Exécuter** et en suivant les étapes du manuel Kit de développement logiciel (SDK) Retail.

## <a name="production-environment"></a>Environnement de production

La procédure précédente active les extensions qui sont des composants de l’exemple d’intégration d’unité de contrôle. De plus, suivez ces étapes pour créer des packages déployables qui contiennent des composants Commerce et pour appliquer ces packages dans un environnement de production.

1. Apportez les modifications suivantes dans les fichiers de configuration du package sous le dossier **RetailSdk\\Assets** :

    - Dans les fichiers de configuration **commerceruntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** ajoutez les lignes suivantes à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - Dans le fichier de configuration **HardwareStation.Extension.config**, ajoutez la ligne suivante à la section **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Apportez les modifications suivantes dans le fichier de configuration de personnalisation du package **Customization.settings**, sous le dossier **BuildTools** :

    - Ajoutez la ligne suivante pour inclure les extensions CRT dans les packages déployables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Ajoutez les lignes suivantes pour inclure l’extension de la station matérielle dans les packages déployables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Activez l’extension PDV en ajoutant les lignes suivantes dans le dossier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Démarrez l’invite de commande MSBuild pour l’utilitaire Visual Studio et exécutez **msbuild** sous le dossier Kit de développement logiciel (SDK) Retail pour créer des packages déployables.
5. Appliquer les packages via Lifecycle Services (LCS) ou manuellement. Pour plus d’informations, voir [Créer des packages déployables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Effectuez toutes les tâches de configuration requises décrites dans [Configuration l’intégration avec les unités de contrôle](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Conception les extensions

### <a name="crt-extension-design"></a>Conception des extensions CRT

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses de l’unité de contrôle.

L’extension CRT est **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Pour plus d’informations sur la conception de la solution d’intégration fiscale, voir [Processus d’enregistrement fiscal et exemples d’intégration fiscale pour les périphériques et les services fiscaux](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Gestionnaire de demandes

Il y a un seul gestionnaire de demandes **DocumentProviderCleanCash** pour le fournisseur de documents. Il est utilisé pour générer des documents fiscaux pour l’unité de contrôle.

Ce gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans l’unité de contrôle.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements de vente et les événements d’audit sont pris en charge.

#### <a name="configuration"></a>Configuration

Le fichier de configuration **DocumentProviderFiscalCleanCashSample** se situe dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage du fournisseur pour le fournisseur de documents depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- Mise en correspondance des codes de TVA

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec l’unité de contrôle.

L’extension de la station matérielle est **HardwareStation.Extension.CleanCashSample**. Elle utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère à l’unité de contrôle. Elle gère également les réponses reçues de l’unité de contrôle.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **CleanCashHandler** est le point d’entrée pour le traitement des demandes à l’unité de contrôle.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents à l’unité de contrôle et renvoie une réponse de celui-ci.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé de l’unité de contrôle.
- **InitializeFiscalDeviceRequest** – Cette requête est utilisée pour l’initialisation de l’unité de contrôle.

#### <a name="configuration"></a>Configuration

Le fichier de configuration se situe dans le dossier **Configuration** du projet d’extension. Ce fichier a pour but de permettre le paramétrage pour le connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale. Les paramètres suivants sont ajoutés :

- **Chaîne de connexions** – Les paramètres de connexion de l’unité de contrôle.
- **Délai d’expiration** – La durée, en millisecondes, pendant laquelle le pilote attendra une réponse de l’unité de contrôle.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrer à partir de l’exemple d’intégration précédent

Si vous utilisez [l’échantillon précédent pour l’intégration POS avec des unités de contrôle pour la Suède](retail-sdk-control-unit-sample.md), vous devrez peut-être migrer de celui-ci vers l’exemple d’intégration actuel. Pour adopter le changement et recevoir des mises à jour en temps opportun pour les fonctionnalités pour la Suède à l’avenir, vous devrez peut-être effectuer une mise à niveau, effectuer des ajustements mineurs de code et de configuration dans les extensions que vous avez créées et reconstruire vos solutions. Aucune modification majeure n’est requise dans la logique d’extension que vous avez créée. L’exemple d’intégration précédent et vos personnalisations continueront de fonctionner si aucune modification n’est apportée de votre part. Par conséquent, vous pouvez planifier, préparer et effectuer l’adoption de votre environnement.

### <a name="migration-process"></a>Processus de migration

La migration de l’échantillon d’intégration antérieur vers l’échantillon d’intégration de l’unité de contrôle actuel devrait être basée sur le concept d’une mise à jour progressive. En d’autres termes, tous les composants de Commerce Headquarters et de Commerce Scale Unit doivent déjà être mis à jour avant que vous ne commenciez à mettre à jour le point de vente (PDV) et les composants de la station matérielle.

Pour éviter une situation de double signature d’un événement ou d’une transaction (c’est-à-dire signé à la fois par l’extension précédente et l’extension actuelle), ou dans lesquels un événement ou une transaction ne peut pas être signé en raison d’une configuration manquante, nous vous recommandons de désactiver tous les appareils de PDV et de station matérielle qui utilisent l’échantillon précédent, puis de les mettre tous à jour simultanément. Cette mise à jour simultanée peut être effectuée, par exemple, magasin par magasin, en mettant à jour le profil de fonctionnalité de chaque magasin et le profil matériel de la station matérielle.

Le processus de migration doit inclure les étapes suivantes.

1. Mettez à jour les composants de Commerce Headquarters.
1. Mettez à jour les composants Commerce Scale Unit et activez les extensions de l’exemple actuel.
1. Assurez-vous que toutes les transactions hors ligne sont synchronisés depuis les appareils MPOS compatibles hors ligne.
1. Désactivez tous les appareils qui utilisent les composants de l’exemple précédent.
1. Effectuez toutes les tâches de configuration requises décrites dans [Configuration l’intégration avec les unités de contrôle](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Mettez à jour les composants PDV et de la station matérielle, désactivez les extensions qui font partie de l’exemple précédent et activez les extensions de l’exemple actuel.

    > [!NOTE]
    > Selon le type d’environnement, vous pouvez trouver plus de détails techniques sur le processus de migration dans la section [Migration dans un environnement de développement](#migration-in-a-development-environment) ou la section [Migration dans un environnement de production](#migration-in-a-production-environment) de cet article.

### <a name="migration-in-a-development-environment"></a>Migration dans un environnement de développement

#### <a name="update-crt"></a>Mise à jour de CRT.

1. Trouvez le projet **Runtime.Extensions.DocumentProvider.CleanCashSample** et le construire.
2. Dans le dossier **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Commerce Scale Unit :** Copiez le fichier dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Commerce Scale Unit.
    - **CRT local sur le PDV moderne :** Copiez le fichier dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **CommerceRuntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur Modern POS :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et il se trouve dans le dossier **bin\\ext** sous l’emplacement du courtier client CRT.

    > [!WARNING]
    > Ne modifiez **pas** les fichiers CommerceRuntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

5. Recherchez et supprimez l’ancienne extension CRT dans le fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ne terminez pas cette étape tant que vous n’avez pas mis à jour tous les appareils de point de vente qui fonctionnent avec cet instance de CRT.

6. Enregistrez l’échantillon actuel des extensions CRT dans le fichier de configuration de l’extension en ajoutant les lignes suivantes.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Mettre à jour la station matérielle

1. Trouvez le projet **HardwareStation.Extension.CleanCashSample** et le construire.
2. Dans le dossier **Extension.CleanCashSample\\bin\\Debug**, recherchez les fichiers d’assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** et **Interop.CleanCash\_1\_1.dll**.
3. Copiez les fichiers d’assembly dans le dossier des extensions de la station matérielle :

    - **Station matérielle partagée :** Copiez les fichiers dans le dossier **bin** sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle dédiée sur le PDV moderne :** Copiez les fichiers dans l’emplacement du courtier client du PDV moderne.

4. Recherchez le fichier de configuration d’extension **HardwareStation.Extension.config** :

    - **Station matérielle distante :** Les fichier est sous l’emplacement du site de la station matérielle IIS.
    - **Station matérielle locale sur le PDV moderne :** Le fichier est sous l’emplacement du courtier client du PDV moderne.

    > [!WARNING]
    > Ne modifiez **pas** les fichiers CommerceRuntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

5. Recherchez et supprimez l’ancienne extension de la station matérielle dans le fichier de configuration de l’extension.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 et versions antérieures](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 et versions ultérieures](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 et versions ultérieures](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Ajoutez la ligne suivante à la section **composition** section du fichier de configuration d’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Mettre à jour Modern POS

1. Ouvrez la solution **CloudPOS.sln** sous **RetailSdk\\POS**.
2. Désactivez l’extension PDV précédente en supprimant les lignes suivantes du fichier **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Activez l’échantillon actuel de l’extension PDV en ajoutant les lignes suivantes dans le fichier **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Mettre à jour le point de vente cloud

1. Ouvrez la solution **ModernPOS.sln** sous **RetailSdk\\POS**.
2. Désactivez l’extension PDV précédente en supprimant les lignes suivantes du fichier **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Activez l’échantillon actuel de l’extension PDV en ajoutant les lignes suivantes dans le fichier **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migration dans un environnement de production

#### <a name="update-crt"></a>Mise à jour de CRT.

1. supprimez l’extension CRT précédente des fichiers de configuration **CommerceRuntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** sous le dossier **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Ne terminez pas cette étape tant que vous n’avez pas mis à jour tous les appareils de point de vente qui fonctionnent avec cet instance de CRT.

2. Activez les extensions CRT de l’exemple actuel en apportant les modifications suivantes dans les fichiers de configuration **CommerceRuntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** sous le dossier **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. Dans le fichier de configuration de la personnalisation de packages **Customization.settings** sous le dossier **BuildTools**, ajoutez la ligne suivante pour inclure l’extension CRT de l’exemple précédent dans les packages déployables.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Mettre à jour la station matérielle

1. Supprimez l’ancienne extension de la station matérielle en modifiant le fichier de configuration **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 et versions antérieures](#tab/retail-7-3)

    Supprimez la section suivante des fichier de configuration **HardwareStation.Shared.config** et **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 et versions ultérieures](#tab/retail-7-3-1)

    Supprimez la section suivante du fichier de configuration **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 et versions ultérieures](#tab/retail-10-0)

    Supprimez la section suivante du fichier de configuration **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Activez l’exemple d’extension de station matérielle actuelle en ajoutant la ligne suivante à la section **composition** dans le fichier de configuration **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Apportez les modifications suivantes dans le fichier de configuration de personnalisation du package **Customization.settings**, sous le dossier **BuildTools** :

    - Supprimez la ligne suivante pour exclure l’extension de la station matérielle précédente des packages déployables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Ajoutez les lignes suivantes pour inclure l’exemple d’extensions de la station matérielle suivant dans les packages déployables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Mettre à jour Modern POS

1. Ouvrez la solution **CloudPOS.sln** dans **RetailSdk\\POS**.
2. Désactivez l’ancienne extension POS :

    - Dans le fichier **tsconfig.json**, ajoutez le dossier **FiscalRegisterSample** à la liste d’exclusion.
    - Supprimez les lignes suivantes du fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Activez l’échantillon actuel de l’extension PDV en ajoutant les lignes suivantes dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Mettre à jour le point de vente cloud

1. Ouvrez la solution **ModernPOS.sln** sous **RetailSdk\\POS**.
2. Désactivez l’ancienne extension POS :

    - Dans le fichier **tsconfig.json**, ajoutez le dossier **FiscalRegisterSample** à la liste d’exclusion.
    - Supprimez les lignes suivantes du fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Activez l’échantillon actuel de l’extension PDV en ajoutant les lignes suivantes dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Créer des packages déployables

Exécutez **msbuild** pour l’intégralité du kit de développement logiciel (SDK) Retail afin de créer des packages déployables. Appliquer les packages via Lifecycle Services (LCS) ou manuellement. Pour plus d’informations, voir [Package du kit Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
