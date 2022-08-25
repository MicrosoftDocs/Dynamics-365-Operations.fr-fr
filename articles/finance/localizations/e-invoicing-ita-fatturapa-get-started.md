---
title: Mettre en place l’intégration directe de FatturaPA italienne avec SDI
description: Cet article fournit des informations qui vous aideront à démarrer avec la facturation électronique pour l’Italie et à configurer l’intégration directe de FatturaPA italien avec le système Exchange (SDI).
author: gionoder
ms.date: 01/15/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: e050d3896b2ba10433e166995d6fc405996cf0b2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267154"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Mettre en place l’intégration directe de FatturaPA italienne avec SDI

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> La Facturation électronique pour l’Italie peut ne pas prendre actuellement en charge toutes les fonctions disponibles pour les factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.

Cet article donne des informations qui vous aideront à démarrer la Facturation électronique pour l’Italie dans Finance et Supply Chain Management. Elle vous guide tout au long des étapes de configuration spécifiques au pays/région dans Regulatory Configuration Services (RCS). Ces étapes complètent les étapes décrites dans [Démarrer la facturation électronique](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes décrites dans cet article, les conditions préalables suivantes doivent être respectées :

- Effectuez les étapes de [Démarrer l’administration du service de Facturation électronique](e-invoicing-get-started.md).
- Importer la fonctionnalité de facturation électronique **FatturaPA italienne (IT)** dans RCS à partir du référentiel mondial. Pour plus d’informations, consultez la section [Importer une fonctionnalité de facturation électronique depuis le fournisseur de configuration Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) de l’article "Commencer avec la facturation électronique" mentionnée précédemment.
- Ajoutez des liens à partir des certificats requis vers l’environnement de service. Les certificats requis incluent le certificat de signature numérique, le certificat de l’autorité de certification (CA) et le certificat des clients. Pour plus d’informations, voir la section [Créer un secret de certificat numérique](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret), de l’article « Prise en main de l’administration du service de Facturation électronique ».

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Configuration spécifique au pays pour la fonctionnalité de Facturation électronique FatturaPA (IT) italienne

Effectuez les procédures suivantes avant de déployer la configuration de l’application sur votre application Finance ou Supply Chain Management connectée.

Cette section complète la section [Configuration du paramétrage de l’application spécifique au pays](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) de l’article « Mise en route de la Facturation électronique ».

### <a name="create-a-new-feature"></a>Créer une nouvelle fonctionnalité

1. Connectez-vous à RCS.
2. Dans l’espace de travail **Déclaration électronique**, dans la section **Fournisseurs de configuration**, marquez le fournisseur de configuration de votre entreprise comme actif.
3. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
4. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez **Ajouter** \> **Basé sur la fonctionnalité existante**.
5. Sous **Fournisseur de configuration Microsoft**, sélectionnez **FatturaPA italienne (IT)** comme fonction de base, entrez un nom, puis sélectionnez **Créer une fonctionnalité**.

### <a name="set-up-application-specific-parameters"></a>Configurer des paramètres spécifiques à l’application

1. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité à modifier.
2. Sur l’onglet **Versions**, vérifiez que la version **Brouillon** est sélectionnée.
3. Sur l’onglet **Configurations**, sélectionnez une configuration, puis **Paramètres spécifiques à l’application**.
4. Dans la section **Recherches**, assurez-vous que la recherche **Liste des sous-catégories d’autoliquidation Natura** est sélectionnée.
5. Dans la section **Conditions**, sélectionnez **Ajouter**.
6. Ajoutez des conditions spécifiques pour chaque sous-catégorie définie dans le système, puis enregistrez vos modifications.

    > [!NOTE]
    > Dans la colonne **Nom**, vous pouvez sélectionner la valeur d’espace réservé **\*Vide\*** ou **\*Non vide\*** au lieu d’une valeur spécifique.

### <a name="configure-a-processing-pipeline-for-export"></a>Configurer un pipeline de traitement pour l’exportation

1. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité à modifier.
2. Dans l’onglet **Paramétrages**, sélectionnez **Factures vente**, puis sélectionnez **Modifier**.
3. Dans la section **Pipeline de traitement**, parcourez les actions et définissez tous les champs requis :

    - Pour l’action **Signer le document**, dans le champ **Nom du certificat**, spécifiez le certificat de signature numérique.
    - Pour l’action **Soumettre**, définissez les champs **Adresse URL** et **Certificats**. La valeur du champ **Certificats** est une chaîne de certificats, dont le premier est le certificat de l’autorité de certification racine (caentrate.cer), et le second est le certificat Clients.

4. Dans la section **Règles d’applicabilité**, parcourez les clauses et passez en revue ou définissez les champs obligatoires :
    - Examinez la clause **LegalEntityID** et mettez à jour avec la valeur correcte de votre entité juridique.

5. Sélectionnez **Valider** pour s’assurer que tous les champs obligatoires ont été définis.
6. Enregistrez vos modifications et fermez la page.
7. Dans l’onglet **Paramétrages**, sélectionnez **Factures projet**, puis sélectionnez **Modifier**.
8. Répétez les étapes 3 à 6 pour les factures de projet.

### <a name="configure-the-processing-pipeline-for-import"></a>Configurer le pipeline de traitement pour l’importation

1. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité à modifier.
2. Dans l’onglet **Paramétrages**, sélectionnez **Importer les factures**, puis sélectionnez **Modifier**.
3. Dans la section **Canal de données**, sur l’onglet **Paramètres**, dans le champ **Canal de données**, entrez une valeur de chaîne.
4. Sur l’onglet **Règles d’applicabilité**, définissez les champs pour la configuration. Vous pouvez utiliser la clause par défaut **Canal** en passant la valeur que vous avez définie pour le champ **Canal de données** à l’étape précédente vers le champ **Valeur**.

    ![Paramétrage des règles d’applicabilité.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Sélectionnez **Valider** pour s’assurer que tous les champs obligatoires ont été définis.

### <a name="deploy-the-feature"></a>Déployer la fonctionnalité

1. Terminez, publiez et déployez la fonctionnalité dans l’environnement de service. Pour plus d’informations, consultez la section [Déployer la fonctionnalité de facturation électronique dans l’environnement de service](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) de l’article « Commencer avec la facturation électronique » mentionnée précédemment.
2. Déployez la fonctionnalité sur l’application connectée. Pour plus d’informations, consultez la section [Déployer la fonctionnalité de facturation électronique dans l’application connectée](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) de l’article « Commencer avec la facturation électronique » mentionnée précédemment.

### <a name="set-up-finance"></a>Configurer Finance

1. Connectez-vous à votre environnement Finance.
2. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
3. Select **Référentiel** \> **Global** \> **Ouvrir**.
4. Sélectionnez et importez les configurations **Modèle de contexte de facture client** et **Importation de facture fournisseur (IT)**.
5. Allez dans **Administration de l’organisation** \> **Paramétrage** \> **Paramètres des documents électroniques**.
6. Sur l’onglet **Fonctionnalité**, recherchez et sélectionnez la fonctionnalité **Facture électronique italienne**, puis cochez la case **Activer**.
7. Sur l’onglet **Document électronique**, assurez-vous que les champs pour **Journal des factures clients** et **Facture de projet** sont définis en fonction des informations contenues dans [Configurer la configuration de l’application](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Paramétrer l’importation des factures fournisseur 

1. Dans Finance, dans l’espace de travail **Déclaration électronique**, dans la section **Fournisseurs de configuration**, marquez le fournisseur de configuration de votre entreprise comme actif.
2. Sélectionnez **Configurations des états**.
3. Sélectionnez **Modèle de contexte de facture client**, puis sélectionnez **Créez une configuration**.
4. Sélectionnez **Provenant du nom : Modèle de contexte de facture client, Microsoft** pour créez une configuration dérivée.
5. Dans la version **Brouillon**, sélectionnez **Concepteur**.
6. Dans l’arborescence **Modèle de données**, sélectionnez **Mapper le modèle à la source de données**.
7. Dans l’arborescence **Définitions**, sélectionnez **Canal de données**, puis sélectionnez **Concepteur**.
8. Dans l’arborescence **Source de données**, développez le conteneur **\$Contexte\_Canal**.
9. Dans le champ **Valeur**, sélectionnez **Modifier**. 
10. Entrez le nom du canal de données. Le nom doit avoir un maximum de 10 caractères. Il doit correspondre à la valeur du paramètre **Canal de données** du canal de données pour la fonctionnalité Facturation électronique dans RCS.
11. Enregistrez vos modifications, puis accédez à **Configurations de rapport** \> **Version de configuration complète**.
12. Dans l’onglet **Canaux externes**, dans la section **Canaux**, sélectionnez **Ajouter**.
13. Dans le champ **Canal**, entrez la valeur **\$Canal de contexte**.
14. Entrez des valeurs dans les champs **Description** et **Entreprise**.
15. Dans le champ **Contexte du document**, sélectionnez la nouvelle configuration que vous dérivez à partir du **Modèle de contexte de facture client**. La description du mappage doit être **Contexte du canal de données**.
16. Sous l’onglet **Importer les sources**, sélectionnez **Ajouter**, puis définissez les valeurs suivantes :

    - **Nom :** OutputFile
    - **Nom de l’entité de données :** En-tête de facture fournisseur (**Entité de données :** VendorInvoiceHeaderEntity)
    - **Mappage du modèle :** Importation de facture fournisseur (IT)

> [!NOTE]
> Si vous avez importé des factures fournisseurs de différentes sources, vous pouvez créer plusieurs canaux externes et plusieurs configurations dérivées qui ont des valeurs **\$Canal de contexte**. Par exemple, vous pouvez souhaiter importer des factures fournisseur pour différentes entités juridiques.

## <a name="proxy-server-setup"></a>Configuration du serveur proxy

Cette section fournit des informations qui vous aideront à installer et configurer le service proxy pour la communication entre le système Exchange (SDI) et le service de facturation électronique.

### <a name="create-an-app-registration"></a>Créez un enregistrement d’application

1. Utilisez le script Windows PowerShell suivant pour créer un certificat auto-signé pour l’authentification de service à service (S2S).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Enregistrez le fichier de certificat .pfx dans le coffre de clés, puis supprimez la copie locale.
3. Connectez-vous au [Portail Azure](https://portal.azure.com) en tant qu’administrateur.
4. Créez une inscription d’application pour le service proxy SDI.

    1. Aller à **Inscriptions d’application**, créez un enregistrement, puis définissez les valeurs suivantes :

        - **Nom :** Client proxy SDI
        - **Types de compte pris en charge :** Comptes dans cet annuaire d’organisation uniquement (locataire unique)

    2. Sélectionnez **S’inscrire**, puis sélectionnez l’enregistrement d’application que vous venez de créer.
    3. Aller à **Autorisations d’API**, et sélectionnez **Accorder le consentement de l’administrateur**.
    4. Aller à **Certificats et secrets**, sélectionnez **Charger le certificat**, et chargez le fichier de certificat .cer pour l’authentification S2S.
    5. Aller à **Applications de l’entreprise**, et sélectionnez l’application que vous avez créée.
    6. Enregistrer les valeurs **l’ID d’application** (ID client) et **ID objet** pour l’application.
    7. L’équipe du service de facturation doit accorder à l’application l’accès au service. Envoyez les valeurs des paramètres suivants à <D365EInvoiceSupport@microsoft.com> :

        - ID client AAD
        - ID d’environnement LCS
        - ID d’application
        - ID objet

5. Dans RCS, ajoutez l’application à la liste d’applications pour votre environnement de service.

    1. Aller à **Fonctionnalités de mondialisation** \> **Environnements** \> **Facturation électronique** \> **Environnements de services**, et sélectionnez votre environnement.
    2. Dans la section **Applications**, ajoutez une ligne à la grille et entrez le nom et l’ID d’objet de l’application.

        ![Ajout de l’application à l’environnement de service.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Sélectionnez **Enregistrer**, puis sélectionnez **Publier**.

### <a name="create-an-azure-virtual-machine"></a>Créer une machine virtuelle Azure

1. Dans le [portail Azure](https://portal.azure.com), accédez à **Machines Virtuelles**, puis sélectionnez **Créer**.
2. Sur l’onglet **Notions de base**, sélectionnez votre abonnement et votre groupe de ressources. Les valeurs doivent correspondre à l’abonnement et au groupe de ressources où se trouvent votre coffre de clés et votre stockage Blob.
3. Sélectionnez la région. Cette valeur doit être la région dans laquelle votre environnement Finance est déployé.
4. Ajoutez le nom d’utilisateur et le mot de passe de l’administrateur et enregistrez-les dans le coffre de clés.
5. Dans le champ **Sélectionnez les ports entrants**, sélectionnez **HTTPS (443)** et **RPD (3389)**.

    > [!NOTE]
    > Nous vous recommandons de désactiver le port **RDP (3389)** lorsque le système passe en production. Vous pouvez le réactiver si vous devez vous connecter à la machine virtuelle (MV) à des fins de dépannage.

    ![Définition des champs de l’onglet Général pour créer une MV Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. Sur l’onglet **Disques**, sur le raccourci **Avancé**, cochez la case **Utiliser des disques gérés**. Laissez la case **Disque de système d’exploitation éphémère** décochée.

    ![Définition des champs de l’onglet Disques pour créer une MV Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. Sur l’onglet **Mise en réseau**, sous le champ **IP publique**, sélectionnez **Créer**.

    ![Définition des champs de l’onglet Mise en réseau pour créer une MV Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. Dans la boîte de dialogue **Créer une adresse IP publique**, dans le groupe de champs **SKU**, sélectionnez l’option **Standard**. Dans le groupe de champs **Affectation**, sélectionnez l’option **Statique**.

    ![Création d’une adresse IP publique.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. Sur l’onglet **Gestion**, décochez la case **Arrêt automatique** pour désactiver l’arrêt automatique.
10. Définissez le champ **Mises à jour du SE invité** sur **Manuel**, puis définissez toute autre stratégie.
11. Réviser et créer la MV.
12. Dans la nouvelle MV, accédez à **Identité** \> **Système affecté**, et réglez l’option **Statut** sur **Activé**.
13. Accordez à la machine virtuelle l’accès au coffre de clés.

    1. Dans le coffre à clés, allez à **Contrôle d’accès (IAM)** \> **Attributions de rôles**.
    2. Sélectionnez **Ajouter une attribution de rôle**, puis définissez les champs suivants :

        1. Dans le champ **Rôle**, précisez **Utilisateur des clés secrètes du coffre-fort**.
        2. Dans le champ **Affecter l’accès à**, précisez **Machine virtuelle**.
        3. Dans le champ **Abonnement**, précisez votre abonnement.
        4. Dans le champ **Sélectionner**, précisez votre machine virtuelle.

    3. Allez dans **Stratégies d’accès**.
    4. Sélectionnez **Ajouter une stratégie d’accès**, puis définissez les champs suivants :

        1. Dans le champ **Principal sélectionné**, sélectionnez votre machine virtuelle.
        2. Dans la section **Certificat**, sélectionnez mes autorisations **Liste** et **Obtenir**.

14. Dans le [Portail Azure](https://portal.azure.com), aller à **Adresses IP publiques**, et sélectionnez l’adresse IP qui a été créée dans la machine virtuelle.
15. Aller à **Configuration**, et définissez le nom de domaine DNS (Domain Name System).

### <a name="prepare-the-proxy-service-environment"></a>Préparer l’environnement du service proxy

Suivez ces étapes sur la machine sur laquelle le service proxy est hébergé.

1. Connectez-vous à la machine virtuelle à l’aide de la connexion Bureau à distance.
2. Ouvrez le composant logiciel enfichable Certificat d’ordinateur local. Pour plus d’informations, voir [Comment : afficher les certificats avec le composant logiciel enfichable MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importer le certificat **caentrate.cer** de production et le **CAEntratetest.cer** à tester dans le [Magasin des autorités de certification racines de confiance](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** est le certificat d’autorité de certification racine qui a été fourni par l’autorité.)
4. Dans le Panneau de configuration, ouvrez **Activer ou désactiver des fonctionnalités Windows**, ou allez à **Gestionnaire de serveur** \> **Ajouter des rôles et des fonctionnalités** pour le système d’exploitation (SE) du serveur et activez les fonctionnalités Internet Information Services (IIS) :

    - Outils de gestion Web
        - Console de gestion IIS
    - Services World Wide Web
        - Fonctionnalités de développement d’applications
            - Extensibilité .NET 4.7 (ou 4.8)
            - ASP
            - ASP.NET 4.7 (ou 4.8)
            - CGI
            - Extensions ISAPI
            - Filtres ISAPI
        - Fonctionnalités HTTP courantes
            - Document par défaut
            - Navigation dans le répertoire
            - Erreurs HTTP
            - Contenu statique
        - Santé et diagnostics
            - Journalisation HTTP
            - Suivi
        - Fonctionnalités sur les performances
            - Compression de contenu statique
        - Sécurité
            - Filtrage des demandes

    ![Activation des fonctionnalités IIS.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Configurer le service proxy SDI dans IIS

1. Dans Microsoft Dynamics Lifecycle Services (LCS), allez à la bibliothèque d’actifs partagés, et sélectionnez **Package de données** comme type d’actif.
2. Trouver **Proxy Sdi de service de facturation électronique**, et téléchargez-le sur la machine virtuelle.
3. Configurez le service.

    1. Décompressez le dossier d’archive **Proxy Sdi du service de facturation électronique** que vous avez téléchargé.
    2. Dans le dossier **src\\FattureService**, ouvrez le fichier **appsettings.json** et définissez les paramètres suivants :

        - **KeyVaultUri** – Spécifiez l’adresse du coffre de clés qui stocke le certificat client pour le service de facturation.
        - **TenantId** – Spécifiez l’identificateur global unique (GUID) du locataire du client.
        - **EnvironmentId** – Spécifiez l’ID de l’environnement LCS.
        - **ClientId** – Spécifiez l’ID d’application de l’enregistrement de l’application des services intermédiaires dans le locataire du client.
        - **ClientCertificateName** – Spécifiez le nom du certificat S2S dans le Key Vault.
        - **SecurityServiceClientOptions.Endpoint** – Spécifiez l’URL du service de sécurité.
        - **SecurityServiceClientOptions.Resource** – Spécifiez la portée pour laquelle obtenir le jeton.
        - **InvoicingServiceClientOptions.Endpoint** – Spécifiez le point de terminaison du service de facturation. Cette valeur doit être le même point de terminaison que celui utilisé pour RCS et Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** – Spécifiez le nom de l’environnement de service. Cette valeur doit être le nom de votre environnement Finance.
        - **Dossier Notifications** – Spécifiez le dossier dans lequel enregistrer les fichiers de notification entrants.

    3. Dans le fichier **web.config**, recherchez la ligne suivante et ajoutez l’empreinte numérique du certificat du serveur proxy.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Lorsque le système passe en production, vous pouvez modifier certaines valeurs du fichier web.config pour réduire la quantité d’informations de journal collectées et économiser de l’espace disque. Dans le nœud **\<system.diagnostics\>\<source\>**, modifiez la valeur du **switchValue** à **Critical,Error**. Pour plus d’informations, voir [Visionneuse de trace de service MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Ouvrez le Gestionnaire IIS. Dans l’arborescence de gauche, restez dans le nœud racine. Sur la droite, sélectionnez **Certificats de serveur**.

    ![Sélection de certificats de service dans IIS Manager.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Ouvrez le menu et sélectionnez **Importer**.
6. Dans la boîte de dialogue **Certificat d’importation**, dans le **Fichier de certificat (.pfx)**, spécifiez le chemin du fichier .pfx pour le certificat du serveur proxy.

    ![Spécification du fichier de certificat du service proxy.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur **Sites**, puis sélectionnez **Ajouter un site web**.
8. Dans la boîte de dialogue **Ajouter un site web**, dans le champ **Nom du site**, entrez un nom pour le site.
9. Dans le champ **Chemin physique**, pointez sur le dossier **src\\FattureService**.
10. Sélectionnez **https** dans le champ **Type de liaison**.
11. Dans le champ **Nom d’hôte**, spécifiez le nom d’hôte.
12. Quitter les champs **adresse IP** et **Port** définis sur les valeurs par défaut.
13. Assurez-vous que la case **Exiger l’indication du nom du serveur** est décochée, car SDI ne prend pas en charge cette technologie.
14. Dans le champ **Certificat SSL**, sélectionnez le certificat de serveur proxy que vous avez importé.
15. Dans le champ **Pool d’applications**, spécifiez un pool pour le site et notez son nom (par exemple, **SdiAppPool**).

    ![Ajout d’un site Web.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Une fois que vous avez terminé de créer le site Web, ouvrez le menu de **Paramètres SSL**.

    ![Ouverture du menu des paramètres SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Cochez la case **Exiger SSL**, puis, dans le groupe de champs **Certificats clients**, sélectionnez l’option **Exiger**.

    ![Configuration des paramètres SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Ouvrez **Navigation dans le répertoire**, et sélectionnez **Activer**.
19. Dans n’importe quel navigateur Web, accédez à **serveurDNS/TrasmissioneFatture.svc**. Une page standard sur le service doit apparaître.

    ![Vérification du service dans un navigateur.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Créez les dossiers suivants pour stocker les journaux et les fichiers :

    - **C :\\Logs\\** – Stockez les fichiers journaux ici. Ces fichiers peuvent être consultés par la [visionneuse de trace de service MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C :\\Files\\** – Stockez tous les fichiers de réponse ici.

21. Dans l’explorateur de fichiers, accordez **SERVICE RÉSEAU** et **IIS AppPool\\SdiAppPool** (ou **IIS AppPool\\DefaultAppPool** si vous utilisez le pool par défaut) l’accès aux dossiers **Logs** et **Fichiers**.

    1. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur l’un des dossiers, puis sélectionnez **Propriétés**.
    2. Dans la boîte de dialogue **Propriétés**, sur l’onglet **Sécurité**, sélectionnez **Modifier**.
    3. Ajoutez les utilisateurs s’ils ne sont pas répertoriés.
    4. Répétez les étapes 1 à 3 pour l’autre dossier.

    ![Ajout d’autorisations à l’utilisateur du service.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Avis de confidentialité 

Activer la fonctionnalité **Facture électronique italienne** peut nécessiter l’envoi de données limitées. Ces données incluent le numéro d’identification fiscale de l’organisation. Un administrateur peut activer et désactiver la fonction de facture électronique italienne. Pour désactiver la fonctionnalité, procédez comme suit.

1. Allez dans **Administration de l’organisation** \> **Paramétrage** \> **Paramètres des documents électroniques**.
2. Sur l’onglet **Fonctionnalité**, sélectionnez les lignes contenant la fonctionnalité **Facture électronique italienne**, puis cochez la case **Désactiver maintenant**.

Les données qui sont importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez la section "Déclaration de confidentialité" dans la documentation de la fonctionnalité spécifique au pays/région.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la Facturation électronique](e-invoicing-service-overview.md)
- [Mise en route de l’administration du service de Facturation électronique](e-invoicing-get-started-service-administration.md)
- [Mise en route de la Facturation électronique](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
