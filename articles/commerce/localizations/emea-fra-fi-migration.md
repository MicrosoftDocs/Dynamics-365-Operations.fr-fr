---
title: Effectuer une migration depuis l’ancienne fonctionnalité Commerce pour la France
description: Cet article explique comment effectuer la migration depuis la solution de signature numérique héritée dans la localisation de Microsoft Dynamics 365 Commerce pour la France vers la solution basée sur le cadre d’intégration fiscale du Commerce.
author: EvgenyPopovMBS
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: France
ms.author: josaw
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.18
ms.search.industry: Retail
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
manager: annbe
ms.openlocfilehash: 3a17317c246c108f6c81153e163360393c07717e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280284"
---
# <a name="migrate-from-legacy-commerce-functionality-for-france"></a>Effectuer une migration depuis l’ancienne fonctionnalité Commerce pour la France

[!include [banner](../includes/banner.md)]

Cet article explique comment effectuer la migration depuis la [solution de signature numérique héritée](emea-fra-deployment.md) dans la localisation de Microsoft Dynamics 365 Commerce pour la France vers la solution basée sur le [cadre d’intégration fiscale du Commerce](emea-fra-fi-deployment.md).

Si vous utilisez la [solution de signature numérique héritée pour la France](emea-fra-deployment.md), vous devez effectuer la migration vers la [solution d’intégration fiscale actuelle de Commerce](./emea-fra-fi-deployment.md) pour tenir compte des changements et recevoir les mises à jour en temps voulu pour les fonctionnalités propres à la France. Aucune modification majeure n’est requise dans la logique d’extension que vous avez créée. Cependant, étant donné que cette mise à jour est une mise à jour majeure, certaines de vos personnalisations cesseront de fonctionner à moins que des modifications ne soient apportées de votre côté. Par conséquent, vous devez planifier, préparer et terminer l’adoption de votre environnement.

## <a name="migration-process"></a>Processus de migration

Le processus de migration de l’ancienne solution de signature numérique vers la solution actuelle d’intégration fiscale repose sur le concept d’une mise à jour progressive. En d’autres termes, tous les composants de Commerce Headquarters et de Commerce Scale Unit doivent déjà être mis à jour avant que vous ne commenciez à mettre à jour le point de vente (POS).

Pour éviter les scénarios de double signature d’un événement ou d’une transaction (à la fois par l’extension héritée et l’extension actuelle), ou dans lesquels un événement ou une transaction ne peut pas être signé en raison d’une configuration incorrecte ou incomplète, nous vous recommandons de désactiver tous les appareils de PDV qui utilisent la solution héritée, puis de les mettre tous à jour simultanément. Par exemple, vous pouvez effectuer cette mise à jour simultanée magasin par magasin, en mettant à jour le profil de fonctionnalité de chaque magasin.

Procédez comme suit pour effectuer ce processus de migration :

1. Mettez à jour les composants de Commerce Headquarters.
1. Mettez à jour les composants Commerce Scale Unit et activez les extensions de la solution actuelle.
1. Mettez à jour les composants POS et activez les extensions de la solution actuelle.
1. Dans Commerce Headquarters, configurez la fonctionnalité d’intégration fiscale pour la France.
1. Assurez-vous que toutes les transactions hors ligne sont téléchargées depuis les appareils Modern POS compatibles hors ligne vers la base de données des canaux.
1. Fermez les équipes et déconnectez-vous de tous les appareils de point de vente.
1. Ajustez les formats de tickets de caisse afin qu’ils utilisent des champs personnalisés mis à jour.
1. Activez la fonctionnalité d’intégration fiscale.
1. Redémarrez le PDV.

> [!NOTE]
> Selon le type d’environnement, vous pouvez trouver plus de détails techniques sur le processus de migration dans la section [Migration dans un environnement de développement](#migration-in-a-development-environment) ou la section [Migration dans un environnement de production](#migration-in-a-production-environment) de cet article.

## <a name="configure-fiscal-integration"></a>Configurer l’intégration fiscale

Pour configurer la fonctionnalité d’intégration fiscale pour la France, suivez les étapes de la section [Configurer l’enregistrement fiscal](./emea-fra-cash-registers.md#set-up-fiscal-registration) et de la section [Configurer les paramètres de signature numérique](./emea-fra-cash-registers.md#configure-the-digital-signature-parameters).

> [!IMPORTANT]
> N’activez pas l’intégration fiscale sur la page **Paramètres partagés de Commerce** à ce stade.

## <a name="adjust-receipt-formats"></a>Ajuster les formats de tickets de caisse

Vous devez ajuster les formats de tickets de caisse afin qu’ils utilisent des champs personnalisés mis à jour. Pour des informations à jour sur les champs personnalisés pour la France, voir [Configurer des champs personnalisés afin qu’ils puissent être utilisés dans des formats de tickets de caisse pour les tickets de caisse de vente](./emea-fra-cash-registers.md#configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts).

## <a name="enable-fiscal-integration"></a>Activer l’intégration fiscale

Lorsque vous êtes prêt à activer la fonctionnalité d’intégration fiscale dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**.
1. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**.
1. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé.
1. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment.
1. Sur le raccourci **Services fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Ouvrez le planning de distribution et sélectionnez les tâches **1070** et **1090** pour transférer des données vers la base de données des canaux.

> [!WARNING]
> Une fois les étapes précédentes terminées, vos personnalisations précédentes de la fonctionnalité de signature numérique cesseront de fonctionner.

## <a name="migration-in-a-development-environment"></a>Migration dans un environnement de développement

### <a name="update-the-commerce-runtime-development"></a>Mettre à jour Commerce Runtime (développement)

Pour mettre à jour Commerce Runtime (CRT), suivez ces étapes.

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **CommerceRuntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit de Microsoft Internet Information Services (IIS).
    - **CRT local sur Modern POS :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du courtier client CRT.

    > [!WARNING]
    > Ne modifiez **pas** les fichiers CommerceRuntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

1. Dans le fichier de configuration de l’extension, recherchez et supprimez l’ancienne extension CRT, comme illustré dans l’exemple suivant.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsFrance" />
    ```

1. Dans le fichier de configuration de l’extension, ajoutez les lignes suivantes pour enregistrer l’échantillon actuel des extensions CRT.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsFrance" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventFrance" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsFrance" />
    ```

### <a name="update-modern-pos-development"></a>Mettre à jour Modern POS (développement)

Pour mettre à jour Modern POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\CloudPOS.sln**.
1. Dans le fichier **extensions.json**, ajoutez les lignes suivantes pour activer l’échantillon actuel de l’extension POS.

    ``` json
    {
        "baseUrl": "Microsoft/Receipts.FR"
    }, 
    {
        "baseUrl": "Microsoft/FifAuditEvent.FR"
    }
    ```

### <a name="update-cloud-pos-development"></a>Mettre à niveau Cloud POS (développement)

Pour mettre à jour Cloud POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**.
1. Dans le fichier **extensions.json**, ajoutez les lignes suivantes pour activer l’échantillon actuel de l’extension POS.

    ``` json
    {
        "baseUrl": "Microsoft/Receipts.FR"
    }, 
    {
        "baseUrl": "Microsoft/FifAuditEvent.FR"
    }
    ```

### <a name="remove-obsolete-customizations-from-the-development-environment-after-future-updates"></a>Supprimer les personnalisations obsolètes de l’environnement de développement après les futures mises à jour

Après une future mise à jour, vous pouvez supprimer les personnalisations obsolètes de Retail Server et de PDV de votre environnement de développement. Les procédures suivantes décrivent comment supprimer en toute sécurité des extensions.

#### <a name="remove-the-earlier-crt-extensions-development"></a>Supprimer les extensions CRT précédentes (développement)

Pour supprimer les précédentes extensions CRT, procédez comme suit.

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Commerce Scale Unit :** le fichier est intitulé **CommerceRuntime.ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du site Commerce Scale Unit.
    - **CRT local sur Modern POS :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible dans le dossier **bin\\ext** sous l’emplacement du courtier client CRT.

    > [!WARNING]
    > Ne modifiez **pas** les fichiers CommerceRuntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

1. Dans le fichier de configuration de l’extension, recherchez et supprimez les anciennes extensions CRT, comme illustré dans l’exemple suivant.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.CommonFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    <add source="assembly" value="Contoso.Commerce.Runtime.DataSignatureKeyVaultSample" />
    ```

#### <a name="remove-the-earlier-retail-server-extension-development"></a>Supprimer l’extension précédente de Retail Server (développement)

Pour supprimer l’extension précédente de Retail Server, procédez comme suit.

1. Recherchez le fichier de configuration pour Retail Server. Le fichier s’appelle **web.config** et se trouve dans le dossier racine sous l’emplacement du site IIS Retail Server.
1. Dans le fichier de configuration, recherchez l’ancienne extension de Retail Server dans la section **extensionComposition** et supprimez-la, comme illustré dans l’exemple suivant.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

#### <a name="disable-the-earlier-modern-pos-extension-development"></a>Désactiver l’ancienne extension Modern POS (développement)

Pour désactiver l’ancienne extension Modern POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**.
1. Dans le fichier **extensions.json**, supprimez les lignes suivantes pour désactiver l’extension POS précédente.

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.FR"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SequentialSignature"
    },
    {
        "baseUrl": "AuditEventSignatureSample"
    },
    {
        "baseUrl": "SalesTransBuildNumberSample"
    }
    ```

#### <a name="disable-the-earlier-cloud-pos-extension-development"></a>Désactiver l’ancienne extension Cloud POS (développement)

Pour désactiver l’ancienne extension Cloud POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**.
2. Dans le fichier **extensions.json**, supprimez les lignes suivantes pour désactiver l’extension POS précédente.

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.FR"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SequentialSignature"
    },
    {
        "baseUrl": "AuditEventSignatureSample"
    },
    {
        "baseUrl": "SalesTransBuildNumberSample"
    }
    ```

## <a name="migration-in-a-production-environment"></a>Migration dans un environnement de production

### <a name="update-crt-production"></a>Mettre à jour CRT (production)

Pour mettre à jour CRT, procédez comme suit.

1. Dans les fichiers de configuration **CommerceRuntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** sous le dossier **RetailSdk\\Assets**, supprimez l’extension CRT précédente, comme indiqué dans l’exemple suivant.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsFrance" />
    ```

1. Dans les fichiers de configuration **CommerceRuntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** sous le dossier **RetailSdk\\Assets**, apporter les modifications suivantes pour activer les extensions CRT actuelles.

    ``` xml 
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsFrance" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventFrance" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsFrance" />
    ```

### <a name="update-modern-pos-production"></a>Mettre à jour Modern POS (production)

Pour mettre à jour Modern POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\CloudPOS.sln**.
1. Dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**, ajoutez les lignes suivantes pour activer l’échantillon actuel de l’extension POS.

    ``` json
    {
        "baseUrl": "Microsoft/Receipts.FR"
    }, 
    {
        "baseUrl": "Microsoft/FifAuditEvent.FR"
    }
    ```

### <a name="update-cloud-pos-production"></a>Mettre à jour Cloud POS (production)

Pour mettre à jour Cloud POS, procédez comme suit.

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**.
1. Dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**, ajoutez les lignes suivantes pour activer l’échantillon actuel de l’extension POS.

    ``` json
    {
        "baseUrl": "Microsoft/Receipts.FR"
    }, 
    {
        "baseUrl": "Microsoft/FifAuditEvent.FR"
    }
    ```

### <a name="create-deployable-packages-production"></a>Créer des packages déployables (production)

Pour créer des packages déployables, procédez comme suit.

1. Exécutez **msbuild** pour l’intégralité du kit de développement logiciel (SDK) Retail afin de créer des packages déployables.
1. Appliquer les packages via Microsoft Dynamics Lifecycle Services (LCS) ou manuellement.

Pour plus d’informations, voir [Package du kit Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

### <a name="remove-obsolete-customizations-from-the-production-environment-after-future-updates"></a>Supprimer les personnalisations obsolètes de l’environnement de production après les futures mises à jour

Après une future mise à jour, vous pouvez supprimer les personnalisations obsolètes de Retail Server et de PDV de votre environnement de production. Les procédures suivantes décrivent comment supprimer en toute sécurité des extensions.

#### <a name="remove-the-earlier-crt-extension-production"></a>Supprimer l’extension CRT précédente (production)

1. Dans les fichiers de configuration **CommerceRuntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** sous le dossier **RetailSdk\\Assets**, supprimez l’extension CRT précédente.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.CommonFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureFrance" />
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    <add source="assembly" value="Contoso.Commerce.Runtime.DataSignatureKeyVaultSample" />
    ```

2. Dans le fichier de configuration de la personnalisation de packages **Customization.settings** sous le dossier **BuildTools**, supprimez les lignes suivantes pour exclure l’extension CRT précédente des packages déployables.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.CommonFrance.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsFrance.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtFrance.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureFrance.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsFrance.dll" />
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DataSignatureKeyVaultSample.dll" />
    ```

3. Dans la section **ItemGroup**, supprimez les lignes suivantes pour exclure l’extension Retail Server des packages déployables.

    ``` xml
    <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
    ```

4. Mettez à jour le fichier de configuration Retail Server. Dans le dossier **web.config** sous le dossier **RetailSDK\\Packages\\RetailServer\\Code**, supprimez les lignes suivantes de la section **extensionComposition**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

#### <a name="disable-the-earlier-modern-pos-extension-production"></a>Désactiver l’ancienne extension Modern POS (production)

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**.
2. Désactivez l’ancienne extension POS :

    - Dans le fichier **tsconfig.json**, ajoutez les dossiers suivants à la liste d’exclusion :

        - SalesTransactionSignatureSample
        - SequentialSignature
        - AuditEventSignatureSample
        - SalesTransBuildNumberSample

    - Dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**, supprimez les lignes suivantes.

        ``` json
        {
            "baseUrl": "Microsoft/AuditEvent.FR"
        },
        {
            "baseUrl": "SalesTransactionSignatureSample"
        },
        {
            "baseUrl": "SequentialSignature"
        },
        {
            "baseUrl": "AuditEventSignatureSample"
        },
        {
            "baseUrl": "SalesTransBuildNumberSample"
        }
        ```

#### <a name="disable-the-earlier-cloud-pos-extension-production"></a>Désactiver l’ancienne extension Cloud POS (production)

1. Ouvrez la solution sur **RetailSdk\\POS\\CloudPOS.sln**.
2. Désactivez l’ancienne extension POS :

    - Dans le fichier **tsconfig.json**, ajoutez les dossiers suivants à la liste d’exclusion :

        - SalesTransactionSignatureSample
        - SequentialSignature
        - AuditEventSignatureSample
        - SalesTransBuildNumberSample

    - Dans le fichier **extensions.json**, sous le dossier **RetailSDK\\POS\\Extensions**, supprimez les lignes suivantes.

        ``` json
        {
            "baseUrl": "Microsoft/AuditEvent.FR"
        },
        {
            "baseUrl": "SalesTransactionSignatureSample"
        },
        {
            "baseUrl": "SequentialSignature"
        },
        {
            "baseUrl": "AuditEventSignatureSample"
        },
        {
            "baseUrl": "SalesTransBuildNumberSample"
        }
        ```

#### <a name="create-deployable-packages-production"></a>Créer des packages déployables (production)

1. Exécutez **msbuild** pour l’intégralité du kit de développement logiciel (SDK) Retail afin de créer des packages déployables.
1. Appliquer les packages via Lifecycle Services (LCS) ou manuellement.

Pour plus d’informations, voir [Package du kit Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
