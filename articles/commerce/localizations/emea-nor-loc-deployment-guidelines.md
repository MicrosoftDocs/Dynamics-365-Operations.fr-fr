---
ms.openlocfilehash: b17bd56f9f3e4def341658626915adbd7f5aada6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281536"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Instructions de déploiement de caisses enregistreuses pour la Norvège (héritées)
---

titre : Instructions de déploiement de caisses enregistreuses pour la Norvège (héritées) [!include [banner](../includes/banner.md)]
description : Cet article est un guide de déploiement qui montre comment activer la localisation Microsoft Dynamics 365 Commerce pour la Norvège.

auteur : EvgenyPopovMBS Cet article est un guide de déploiement qui montre comment activer la localisation Microsoft Dynamics 365 Commerce pour la Norvège. La localisation consiste en plusieurs extensions des composants Commerce. Par exemple, les extensions vous permettent d’imprimer des champs personnalisés sur les reçus, d’enregistrer des événements d’audit supplémentaires, des transactions de vente et des transactions de paiement dans le point de vente (PDV), de signer numériquement les transactions de vente et d’imprimer des rapports X et Z dans des formats locaux. Pour plus d’informations sur la localisation pour la Norvège, voir [Fonctionnalité de caisse enregistreuse pour la Norvège](./emea-nor-cash-registers.md).
ms.date : 20/12/2021

ms.topic : article Cet exemple fait partie du kit de développement logiciel (SDK) Retail. Pour en savoir plus le Kit de développement logiciel (SDK), voir [Architecture du kit de développement logiciel de Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).
public : Utilisateur de l’application, Développeur, Pro de l’informatique

ms.reviewer : v-chgriffin Cet exemple se compose d’extensions pour l’environnement de Commerce Runtime (CRT), Retail Server et PDV. Pour exécuter cet exemple, vous devez modifier et générer les projets CRT, Retail Server et PDV. Nous vous recommandons d’utiliser un Kit de développement logiciel (SDK) Retail non modifié pour apporter les modifications décrites dans cet article. Nous vous recommandons également d’utiliser un système de contrôle de source, tel que Microsoft Visual Studio Online (VSO), où aucun fichier n’a encore été modifié.
ms.search.region : global

ms.author : josaw
> [!NOTE]
ms.search.validFrom : 2018-02-28 Dans Commerce 10.0.8 et versions ultérieures, Retail Server est appelé Commerce Scale Unit. Étant donné que ce sujet s’applique à plusieurs versions précédentes de l’application, *Retail Server* est utilisé tout au long du sujet.
>
---
> Certaines étapes des procédures décrites dans cet article diffèrent selon la version de Commerce que vous utilisez. Pour plus d’informations, voir [Nouveautés ou changements dans Dynamics 365 Retail](../get-started/whats-new.md).


6. Mettez à jour le fichier de configuration Retail Server. Dans le fichier **RetailSDK\\Packages\\RetailServer\\Code\\web.config**, ajoutez les lignes suivantes à la section composition **extensionComposition**.
### <a name="using-certificate-profiles-in-commerce-channels"></a>Utilisation des profils de certificat dans les canaux Commerce


    ``` xml
Dans Commerce versions 10.0.15 et ultérieures, vous pouvez utiliser la fonctionnalité [Profils de certificats définis par l’utilisateur pour les magasins de détail](./certificate-profiles-for-retail-stores.md) qui prend en charge le basculement hors connexion lorsque Key Vault ou le siège de Commerce ne sont pas disponibles. La fonctionnalité étend la fonction [Gérer les clés secrètes pour les canaux de vente au détail](../dev-itpro/manage-secrets.md).
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />

    ```
Pour appliquer cette fonctionnalité dans l’extension CRT, suivez les étapes ci-après.


7. Exécutez **msbuild** pour l’intégralité du kit de développement logiciel (SDK) Retail afin de créer des packages déployables.
1. Créer un projet d’extension CRT (type de projet de bibliothèque de classes C#). Utilisez les exemples de modèles du kit de développement logiciel (SDK) Retail (RetailSDK\SampleExtensions\CommerceRuntime).
8. Appliquer les packages via Microsoft Dynamics Lifecycle Services (LCS) ou manuellement. Pour plus d’informations, voir [Créer des packages déployables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).


2. Ajoutez un gestionnaire personnalisé pour CertificateSignatureServiceRequest dans le projet SequentialSignatureRegister.
### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Activer la signature numérique en mode hors connexion pour le PDV moderne


3. Pour lire un appel secret, `GetUserDefinedSecretCertificateServiceRequest` en utilisant un constructeur avec le paramètre profileId. Cela démarrera la fonctionnalité fonctionnant avec les paramètres des profils de certificat. En fonction des paramètres, le certificat sera récupéré à partir d’Azure Key Vault ou du stockage de la machine locale.
Pour activer la signature numérique en mode hors connexion pour le PDV moderne, vous devez suivre ces étapes après avoir activé le PDV moderne sur un nouvel appareil.


    ```csharp
1. Sign in to POS.
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
2. On the **Database connection status** page, make sure that the offline database is fully synchronized. When the value of the **Pending downloads** field is **0** (zero), the database is fully synchronized.
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);
3. Sign out of POS.

4. Wait a while for the offline database to be fully synchronized.
    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
5. Sign in to POS.
    ```
6. Sur la page **Statut de la connexion à la base de données**, assurez-vous que la base de données hors connexion est entièrement synchronisée. Lorsque la valeur du champ **Transactions en attente dans la base de données hors connexion** est **0** (zéro), la base de données est entièrement synchronisée.

7. Redémarrez le PDV moderne.
4. Une fois le certificat récupéré, procédez à la signature des données.



5. Construisez le projet d’extension CRT.
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

6. Copiez la bibliothèque de classes de sortie et collez-la dans ...\RetailServer\webroot\bin\Ext pour un test manuel.

7. Dans le fichier CommerceRuntime.Ext.config, mettez à jour la section de composition d’extension avec les informations de bibliothèque personnalisées.

## <a name="development-environment"></a>Environnement de développement

Suivez ces procédures pour configurer un environnement de développement afin de pouvoir tester et étendre l’exemple.

### <a name="the-crt-extension-components"></a>Composants d’extension CRT

Les composants d’extension CRT sont inclus dans les échantillons CRT. Pour terminer les procédures suivantes, ouvrez la solution CRT, **CommerceRuntimeSamples.sln**, sous **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>Composant ReceiptsNorway

1. Trouvez le projet **Runtime.Extensions.ReceiptsNorway** et le construire.
2. Dans le dossier **Extensions.ReceiptsNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.ReceiptsNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site Microsoft Internet Information Services (IIS) Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salespaymenttransext-component"></a>Composant SalesPaymentTransExt

1. Trouvez le projet **Runtime.Extensions.SalesPaymentTransExt** et le construire.
2. Dans le dossier **Extensions.SalesPaymentTransExt\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="xzreportsnorway-component"></a>Composant XZReportsNorway

1. Trouvez le projet **Runtime.Extensions.XZReportsNorway** et le construire.
2. Dans le dossier **Extensions.XZReportsNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.XZReportsNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

# <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>Exemple de composant RegisterAuditEvent

1. Trouvez le projet **Runtime.Extensions.RegisterAuditEventSample** et le construire.
2. Dans le dossier **Extensions.RegisterAuditEventSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignature-sample-component"></a>Composant SalesTransactionSignature

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

# <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>Exemple de composant RegisterAuditEvent

1. Trouvez le projet **Runtime.Extensions.RegisterAuditEventSample** et le construire.
2. Dans le dossier **Extensions.RegisterAuditEventSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignature-sample-component"></a>Composant SalesTransactionSignature

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignaturesamplemessages-component"></a>Composant SalesTransactionSignatureSample.Messages

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureSample.Messages**.
2. Dans le dossier **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>Exemple de composant RegisterAuditEvent

1. Trouvez le projet **Runtime.Extensions.RegisterAuditEventSample** et le construire.
2. Dans le dossier **Extensions.RegisterAuditEventSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignature-sample-component"></a>Composant SalesTransactionSignature

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregistercontracts-component"></a>Composant SequentialSignatureRegister.Contracts

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Dans le dossier **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>Exemple de composant RegisterAuditEvent

1. Trouvez le projet **Runtime.Extensions.RegisterAuditEventSample** et le construire.
2. Dans le dossier **Extensions.RegisterAuditEventSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregister-component"></a>Composant SequentialSignatureRegister

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SequentialSignatureRegister\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignaturenorway-component"></a>Composant SalesTransactionSignatureNorway

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Dans le dossier **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregistercontracts-component"></a>Composant SequentialSignatureRegister.Contracts

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Dans le dossier **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Composant SalesPaymentTransExtNorway

1. Trouvez le projet **Runtime.Extensions.SalesPaymentTransExtNorway** et le construire.
2. Dans le dossier **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>Composant RegisterAuditEventNorway

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

2. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregister-component"></a>Composant SequentialSignatureRegister

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SequentialSignatureRegister\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignaturenorway-component"></a>Composant SalesTransactionSignatureNorway

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Dans le dossier **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregistercontracts-component"></a>Composant SequentialSignatureRegister.Contracts

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Dans le dossier **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Composant SalesPaymentTransExtNorway

1. Trouvez le projet **Runtime.Extensions.SalesPaymentTransExtNorway** et le construire.
2. Dans le dossier **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>Composant RegisterAuditEventNorway

1. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

2. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregister-component"></a>Composant SequentialSignatureRegister

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifier le fichier **App.config** en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente.
3. Créez le projet.
4. Dans le dossier **Extensions.SequentialSignatureRegister\\bin\\Debug**, recherchez les fichiers suivants :

    - Le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Le fichier de configuration **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copiez les fichiers dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

6. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

7. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="salestransactionsignaturenorway-component"></a>Composant SalesTransactionSignatureNorway

1. Trouvez le projet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. Dans le dossier **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

#### <a name="sequentialsignatureregistercontracts-component"></a>Composant SequentialSignatureRegister.Contracts

1. Trouvez le projet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. Dans le dossier **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Composant SalesPaymentTransExtNorway

1. Trouvez le projet **Runtime.Extensions.SalesPaymentTransExtNorway** et le construire.
2. Dans le dossier **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions CRT :

    - **Retail Server :** Copiez l’assembly dans le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur le PDV moderne :** Copiez l’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.

4. Recherchez le fichier de configuration de l’extension pour CRT :

    - **Retail Server :** Le fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin\\ext** sous l’emplacement du site IIS Retail Server.
    - **CRT local sur PDV moderne :** le fichier est intitulé **CommerceRuntime.MPOSOffline.Ext.config** et est disponible à l’emplacement du courtier client CRT local.

5. Enregistrez la modification CRT du fichier de configuration de l’extension.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Ne modifiez **pas** les fichiers commerceruntime.config et CommerceRuntime.MPOSOffline.config. Ces fichiers ne sont pas destinés à des personnalisations.

---

### <a name="the-retail-server-extension-components"></a>Les composants de l’extension Retail Server

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Exemple de composant Retail Server SalesTransactionSignature

1. Dans le dossier **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample**, recherchez le projet **RetailServer.Extensions.SalesTransactionSignatureSample** et le construire.
2. Dans le dossier **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Copiez le fichier d’assembly dans le dossier des extensions Retail Server.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    Le dossier est le dossier **\\bin** sous l’emplacement du site IIS Retail Server.

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    Le dossier est le dossier **\\bin** sous l’emplacement du site IIS Retail Server.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Le dossier est le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    Le dossier est le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    Le dossier est le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    Le dossier est le dossier **\\bin\\ext** sous l’emplacement du site IIS Retail Server.

    ---

4. Recherchez le fichier de configuration pour Retail Server. Le fichier s’appelle **web.config** et se trouve dans le dossier racine sous l’emplacement du site IIS Retail Server.
5. Enregistrez les extensions Retail Server dans la section **extensionComposition** du fichier de configuration.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Enregistrez les dépendances des extensions Retail Server.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4/)

    1. Dans le dossier **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez les fichiers suivants :

        - Le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - Le fichier de configuration **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Copiez les fichiers dans le dossier **\\bin** sous l’emplacement du site IIS Retail Server.
    3. Enregistrez la modification CRT du fichier de configuration de l’extension pour CRT. Ce fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin** sous l’emplacement du site IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later/)

    1. Dans le dossier **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
    2. Copiez le fichier dans le dossier **\\bin** sous l’emplacement du site IIS Retail Server.
    3. Enregistrez la modification CRT du fichier de configuration de l’extension pour CRT. Ce fichier s’appelle **commerceruntime.ext.config** et se trouve dans le dossier **bin** sous l’emplacement du site IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Aucune action n’est nécessaire.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    > [!NOTE]
    > Aucune action n’est nécessaire.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    > [!NOTE]
    > Aucune action n’est nécessaire.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    > [!NOTE]
    > Aucune action n’est nécessaire.

    ---

### <a name="the-modern-pos-extension-components"></a>Composants d’extension PDV moderne

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implémenter le code proxy pour le mode hors connexion

Cette partie est équivalente au contrôleur Retail Server, mais elle étend le CRT local qui est utilisé lorsque le client n’est pas connecté.

1. Dans le fichier **customization.settings**, modifiez la section **@(RetailServerLibraryPathForProxyGeneration)** afin qu’il utilise le nouvel assembly Retail Server pour la génération de proxy.
2. Implémentez les méthodes d’interface suivantes dans le dossier **StoreOperationsManager**. Pour la première itération, ajoutez le code suivant :

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    ---

3. Pour régénérer le code proxy, générez le dossier **Proxies** à partir de la ligne de commande en utilisant la commande **msbuild /t:Rebuild**.
4. Résoudre les dépendances du projet **Proxy.RetailProxy** :

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    Ouvrez **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, ajoutez le projet **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** à la solution et ajoutez une référence de projet au projet **RetailProxy** de la référence **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    Ouvrez **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, ajoutez le projet **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** à la solution et ajoutez une référence de projet au projet **RetailProxy** de la référence **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    ---

5. Ajustez les méthodes d’interface dans la classe **StoreOperationsManager** :

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    > [!NOTE]
    > Cette étape ne s’applique pas à cette version.

    ---

6. Mettre à jour le fichier **dllhost.exe.config** afin que le courtier client charge le nouvel assembly RetailProxy.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Composant d’extension de proxy Retail (Retail 7.3.1 et versions ultérieures)

Effectuez la procédure suivante uniquement si vous utilisez Retail 7.3.1 et versions ultérieures.

1. Dans le dossier **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample**, recherchez le projet **RetailServer.Extensions.SalesTransactionSignatureSample** et le construire.
2. Dans le dossier **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug**, recherchez le fichier d’assembly **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Copiez les fichiers d’assembly dans le dossier **\\ext** sous l’emplacement du courtier client CRT local.
4. Enregistrez la modification de proxy Retail du fichier de configuration de l’extension. Le fichier s’appelle **RetailProxy.MPOSOffline.ext.config**, et c’est sous l’emplacement du courtier client CRT local.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Composants d’extension PDV moderne

1. Ouvrez la solution sur **RetailSdk\\POS\\ModernPOS.sln**, et assurez-vous qu’il peut être compilé sans erreur. De plus, assurez-vous que vous pouvez exécuter le PDV moderne de Microsoft Visual Studio en utilisant la commande **Run**.

    > [!NOTE]
    > Le ODV moderne ne doit pas être personnalisé. Vous devez activer le contrôle de compte d’utilisateur (UAC) et vous devez désinstaller les instances précédemment installées du PDV moderne si nécessaire.

2. Incluez les dossiers de code source existants suivants dans le projet **Pos.Extensions**.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Activer les extensions à compiler dans **tsconfig.json** en supprimant les dossiers suivants de la liste d’exclusion.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Activer le chargement des extensions dans **extensions.json** en ajoutant les lignes suivantes à l’endroit approprié.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Pour plus d’informations et pour des exemples montrant comment inclure des dossiers de code source et permettre le chargement d’extensions, consultez les instructions du fichier readme.md dans le projet **Pos.Extensions**.

5. Recréez la solution.
6. Exécutez le PDV moderne dans le débogueur et testez la fonctionnalité.

### <a name="cloud-pos-extension-components"></a>Composants d’extension PDV de cloud

1. Ouvrez la solution sur **RetailSdk\\POS\\CloudPOS.sln**, et assurez-vous qu’il peut être compilé sans erreur.
2. Incluez les dossiers de code source existants suivants dans le projet **Pos.Extensions**.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Activer les extensions à compiler dans **tsconfig.json** en supprimant les dossiers suivants de la liste d’exclusion.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Activer le chargement des extensions dans **extensions.json** en ajoutant les lignes suivantes à l’endroit approprié.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Pour plus d’informations et pour des exemples montrant comment inclure des dossiers de code source et permettre le chargement d’extensions, consultez les instructions du fichier readme.md dans le projet **Pos.Extensions**.

5. Recréez la solution.
6. Exécutez la solution en utilisant la commande **Exécuter** et en suivant les étapes du manuel Kit de développement logiciel (SDK) Retail.
7. Testez la fonctionnalité.

### <a name="set-up-required-parameters-in-headquarters"></a>Configurer les paramètres requis au siège

Pour plus d’informations, voir [Fonctionnalité de caisse enregistreuse pour la Norvège](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Environnement de production

Suivez ces étapes pour créer des packages déployables qui contiennent des composants Commerce et pour appliquer ces packages dans un environnement de production.

1. Complétez les étapes de la section [Composants d’extension du PDV Cloud](#cloud-pos-extension-components) ou [Composants d’extension de PDV moderne](#modern-pos-extension-components) plus haut dans cet article.
2. Apportez les modifications suivantes dans les fichiers de configuration du package sous le dossier **RetailSdk\\Assets** :

    1. Dans les fichiers de configuration **commerceruntime.ext.config** et **CommerceRuntime.MPOSOffline.Ext.config** ajoutez les lignes suivantes à la section **composition** :

        # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Activer la personnalisation du proxy de Commerce :

        # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

        Dans le fichier de configuration **dllhost.exe.config**, ajoutez les lignes suivantes à la sous-section **appSettings** de la section **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

        Dans le fichier de configuration **dllhost.exe.config**, ajoutez les lignes suivantes à la sous-section **appSettings** de la section **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Dans le fichier de configuration **RetailProxy.MPOSOffline.ext.config**, ajoutez les lignes suivantes à la section **composition** :

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

        Dans le fichier de configuration **RetailProxy.MPOSOffline.ext.config**, ajoutez les lignes suivantes à la section **composition** :

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

        Dans le fichier de configuration **RetailProxy.MPOSOffline.ext.config**, ajoutez les lignes suivantes à la section **composition** :

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

        Dans le fichier de configuration **RetailProxy.MPOSOffline.ext.config**, ajoutez les lignes suivantes à la section **composition** :

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Apportez les modifications suivantes dans le fichier de configuration de personnalisation du package **Customization.settings** :

    1. Activer la personnalisation du proxy de Retail.

        # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

        Ajoutez les lignes suivantes à la section **&lt;ItemGroup Condition="’@(RetailServerLibraryPathForProxyGeneration)’ == ’’"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

        Ajoutez les lignes suivantes à la section **&lt;ItemGroup Condition="’@(RetailServerLibraryPathForProxyGeneration)’ == ’’"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure l’extension de proxy Retail dans les packages déployables :

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

        Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure l’extension de proxy Retail dans les packages déployables :

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

        Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure l’extension de proxy Retail dans les packages déployables :

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

        Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure l’extension de proxy Retail dans les packages déployables :

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure les extensions CRT dans les packages déployables :

        # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Ajoutez les lignes suivantes à la section **ItemGroup** pour inclure l’extension Retail Server dans les packages déployables :

        # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Modifiez les fichiers suivants pour inclure les fichiers de ressources pour la Norvège dans les packages déployables :
    - Packages\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Packages\RetailServer\Sdk.RetailServerSetup.proj
  
  - Pour le fichier **Sdk.ModernPos.Shared.csproj** 
    - Ajouter une ligne à la section **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > Au lieu de <File_name>, spécifiez un nom du fichier de ressources. Il en va de même pour les autres exemples donnés ci-dessous.
 
    - Ajoutez une ligne à la section **Target Name="CopyPackageFiles"**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - Pour le fichier **Sdk.RetailServerSetup.proj** 
    - Ajouter une ligne à la section **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Ajoutez une ligne à la section **Target Name="CopyPackageFiles"**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Modifier le fichier de configuration du certificat en spécifiant l’empreinte, l’emplacement du magasin et le nom du magasin pour le certificat qui doit être utilisé pour signer les transactions de vente. Copiez ensuite le fichier de configuration dans le dossier **Références**.

    # <a name="application-update-4"></a>[Mise à jour d’application 4](#tab/app-update-4)

    Le fichier est nommé **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, et se trouve sous **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[Mise à jour 5 de l’application et versions ultérieures](#tab/app-update-5-and-later)

    Le fichier est nommé **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, et se trouve sous **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Le fichier est nommé **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, et se trouve sous **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 et versions ultérieures](#tab/retail-7-3-2)

    Le fichier est nommé **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, et se trouve sous **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 et versions ultérieures](#tab/retail-7-3-5)

    Le fichier est nommé **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, et se trouve sous **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 et versions ultérieures](#tab/retail-8-1-1)

    Le fichier est nommé **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, et se trouve sous **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---
