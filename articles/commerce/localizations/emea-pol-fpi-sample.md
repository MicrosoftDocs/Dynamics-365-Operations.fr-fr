---
title: Exemple d’intégration de l’imprimante fiscale pour la Pologne
description: Cet article fournit une présentation d’un exemple d’intégration fiscale pour la Pologne dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: e71d7b342789e4cf2e7644a46bc847087063fc78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876947"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Exemple d’intégration de l’imprimante fiscale pour la Pologne

[!include[banner](../includes/banner.md)]

Cet article fournit une présentation d’un exemple d’intégration fiscale pour la Pologne dans Microsoft Dynamics 365 Commerce.

La fonctionnalité Dynamics 365 Commerce pour la Pologne comprend un exemple d’intégration du point de vente (PDV) avec une imprimante fiscale. L’échantillon étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et prend en charge le protocole POSNET THERMAL HD 2.02 pour les imprimantes fiscales de [Posnet Polska S.A.](https://www.posnet.com.pl) L’exemple permet la communication avec une imprimante fiscale connectée via un port COM à l’aide d’un pilote logiciel natif. Il a été implémenté et testé à l’aide d’un émulateur logiciel fourni par Posnet pour l’imprimante fiscale Posnet Thermal HD FV EJ. L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) Retail.

Microsoft ne publie aucun matériel, logiciel ou documentation de Posnet. Pour plus d’informations sur la façon d’obtenir l’imprimante fiscale et de l’utiliser, contactez [Posnet Polska S.A.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Scénarios

Les scénarios suivants sont couverts par l’exemple d’intégration de l’imprimante fiscale pour la Pologne :

- Scénarios de vente :

    - Imprimez un reçu fiscal pour les ventes et les retours au comptant sans livraison.
    - Capturez une réponse de l’imprimante fiscale et stockez-la dans la base de données des canaux.
    - Taxes :

        - Mappage vers les codes fiscaux de l’imprimeur fiscal (départements).
        - Transférez les données fiscales mappées vers l’imprimante fiscale.

    - Paiements :

        - Mappage sur les modes de paiement de l’imprimeur fiscal.
        - Imprimez les paiements sur un reçu fiscal.
        - Imprimer les informations de modification.

    - Imprimer les remises en ligne.
    - Cartes cadeaux :

        - Exclure une ligne de carte-cadeau émise/rechargée d’un reçu fiscal pour une vente.
        - Imprimez un paiement qui utilise une carte-cadeau comme mode de paiement normal.

    - Imprimer les reçus fiscaux pour les opérations de commande client :

        - Un reçu fiscal n’est pas imprimé pour un acompte de commande client.
        - Imprimez un reçu fiscal pour les lignes de report d’une commande client hybride.
        - Imprimez un reçu fiscal pour l’opération de retrait d’une commande client.
        - Imprimez un reçu fiscal pour une commande de retour.

    - Imprimer les [Informations client](emea-pol-customer-information.md) qui est spécifié pour une transaction de vente sur un reçu fiscal. Un exemple de ces informations est le numéro de TVA du client.

- Relevés de fin de journée (rapports fiscal X et fiscal Z).
- Gestion des erreurs, telles que les options suivantes :

    - Réessayez l’enregistrement fiscal si une nouvelle tentative est possible, par exemple si l’imprimante fiscale n’est pas connectée, n’est pas prête ou ne répond pas, l’imprimante n’a plus de papier ou il y a un bourrage papier.
    - Reporter l’enregistrement fiscal.
    - Ignorez l’enregistrement fiscal ou marquez la transaction comme enregistrée et incluez des codes d’information pour capturer la raison de l’échec et des informations supplémentaires.
    - Vérifiez la disponibilité de l’imprimante fiscal avant l’ouverture d’une nouvelle opération de vente ou la finalisation d’une opération de vente.

### <a name="gift-cards"></a>Cartes cadeaux

L’exemple d’intégration de l’imprimante fiscale implémente les règles suivantes liées aux cartes-cadeaux :

- Exclure les lignes de vente liées aux opérations *Émettre une carte-cadeau* et *Ajouter à la carte-cadeau* à partir d’un reçu fiscal.
- N’imprimez pas un reçu fiscal s’il se compose uniquement de lignes de carte-cadeau.
- Déduisez le montant total des cartes-cadeaux émises ou rechargées lors d’une transaction des lignes de paiement du reçu fiscal.
- Enregistrez les ajustements calculés des lignes de paiement dans la base de données du canal avec une référence à une transaction fiscale correspondante.
- Le paiement par carte-cadeau est considéré comme un paiement régulier.

### <a name="customer-deposits-and-customer-order-deposits"></a>Acomptes client et acomptes commandes client

L’exemple d’intégration l’imprimante fiscale implémente les règles suivantes liées aux dépôts des clients et aux dépôts de commandes client :

- N’imprimez pas de reçu fiscal si une transaction est un dépôt client.
- N’imprimez pas de reçu fiscal si une transaction ne contient qu’un dépôt de commande client ou un remboursement de dépôt de commande client.
- Imprimez le montant de l’acompte préalablement versé sur un ticket fiscal pour une opération de retrait de commande client.
- Déduisez le montant du dépôt de commande client des lignes de paiement lorsqu’une commande client hybride est créée.
- Enregistrez les ajustements calculés des lignes de paiement dans la base de données du canal avec une référence à une transaction fiscale pour une commande client hybride.

### <a name="limitations-of-the-sample"></a>Limites de l’échantillon

- L’imprimante fiscale prend en charge uniquement les scénarios où la taxe de vente est incluse dans le prix. Par conséquent, l’option **Le prix comprend la taxe de vente** doit être définie sur **Oui** pour les magasins et les clients.
- Les rapports quotidiens (fiscal X et fiscal Z) sont imprimés en utilisant le format *Rapport d’équipe*.
- L’impression d’un code-barres sur les reçus fiscaux est considérée comme une personnalisation potentielle, car cette fonctionnalité n’est pas prise en charge dans les formats intégrés et ne peut être implémentée qu’en utilisant le rapport **Super format**.
- L’imprimante fiscale ne prend pas en charge les transactions mixtes. L’option **Interdire de mélanger les ventes et les retours dans un seul reçu** doit être définie sur **Oui** dans les profils de fonctionnalité PDV.

## <a name="set-up-fiscal-integration-for-poland"></a>Paramétrer l’intégration fiscale pour la Pologne

L’échantillon d’intégration de l’imprimante fiscale pour la Pologne est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Posnet** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour la Pologne (héritées)](emea-pol-fpi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

Suivez les étapes de configuration de l’intégration fiscale décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Notez également les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à cet échantillon d’intégration de l’imprimante fiscale](#set-up-the-registration-process).
1. [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configurer les états X/Z fiscaux depuis le PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Activer l’exécution manuelle d’un enregistrement fiscal reporté](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurer le processus d’inscription

Pour activer le processus d’enregistrement, procédez comme suit pour configurer Commerce Headquarters. Pour plus d’informations sur l’intégration fiscale, voir [Configuration de l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK)/application (par exemple, **[version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Ouvrez **src \> FiscalIntegration \> Posnet**.
    1. Téléchargez le fichier de configuration du fournisseur de document sur **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml** (par exemple, le [fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **HardwareStation \> ThermalDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml** (par exemple, [le fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichier de configuration du fournisseur de document :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml
    > 
    > La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez le fichier de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez un profil fonctionnel de connecteur. Sélectionnez le fournisseur de documents et le connecteur que vous avez chargés précédemment. Mettez à jour les [paramètres de mappage des données](#default-data-mapping) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur fiscal chargé précédemment. Mettez à jour les [paramètres du connecteur](#fiscal-connector-settings) si nécessaire.
6. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**. Créez un groupe de connecteurs fiscaux pour le profil fonctionnel de connecteur que vous avez créé précédemment.
7. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal et une étape du processus d’enregistrement fiscal et sélectionnez le groupe de connecteurs fiscaux créé précédemment.
8. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment.
9. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils du matériel**. Sélectionnez un profil de matériel lié à la station matérielle à laquelle l’imprimante fiscale sera connectée. Sur le raccourci **périphériques fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment.
10. Ouvrez le programme de distribution (**Commerce et vente au détail \> Informatique Retail et Commerce \> Programme de distribution**) et sélectionnez les projets **1070** et **1090** pour transférer les données vers la base de données du canal.

#### <a name="default-data-mapping"></a>Mappage des données par défaut

Le mappage de données par défaut suivant est inclus dans la configuration du fournisseur de documents fiscaux fournie dans le cadre de l’exemple d’intégration fiscale :

- **Mappagedes taux de taxe sur la valeur ajoutée (TVA)** – Le mappage des valeurs de pourcentage de taxe configurées pour les codes de taxe de vente aux taux de TVA spécifiques à l’imprimante fiscale. Voici le mappage par défaut :

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    Le premier composant de chaque paire représente un numéro de taux de TVA qui est configuré dans l’imprimante fiscale. Le deuxième composant représente le taux de TVA correspondant. Pour plus d’informations sur la configuration du taux de TVA de l’imprimante fiscale, consultez la documentation du pilote POSNET.

- **Mappage des types d’appel d’offres** – Le mappage des modes de paiement configurés pour le magasin avec les formats de paiement pris en charge par l’imprimante fiscale. Voici le mappage par défaut :

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    Le premier composant de chaque paire représente un mode de paiement configuré pour le magasin. Le second composant de chaque paire représente un formulaire de paiement correspondant pris en charge par l’imprimante fiscale. Pour plus d’informations sur les formulaires de paiement de l’imprimante fiscale prend en charge, consultez la documentation du pilote POSNET. Vous devez modifier l’exemple de mappage en fonction des modes de paiement configurés dans votre application.

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Chaîne de connexion** – Une chaîne qui décrit les détails de la connexion au périphérique dans un format pris en charge par le pilote. Pour plus d’informations, voir la documentation sur le pilote POSNET.
- **Synchronisation de la date et de l’heure** – Une valeur qui spécifie si la date et l’heure de l’imprimante doivent être synchronisées avec la station matérielle connectée.
- **Délai d’expiration de l’appareil** – La durée, en millisecondes, pendant laquelle le pilote attendra une réponse de l’appareil. Pour plus d’informations, voir la documentation sur le pilote POSNET.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour la Pologne (héritées)](emea-pol-fpi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

#### <a name="set-up-the-development-environment"></a>Configurer l’environnement de développement

Pour configurer un environnement de développement pour tester et étendre l’exemple, procédez comme suit.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information : [Télécharger les exemples et les packages de référence du SDK Retail depuis GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution d’intégration d’imprimante fiscale sur **Dynamics365Commerce.Solutions\\FiscalIntegration\\Posnet\\Posnet.sln**, et le générer.
1. Installer les extensions CRT :

    1. Recherchez le programme d’installation de l’extension CRT :

        - **Commerce Scale Unit :** Dans le dossier **Posnet\\ScaleUnit\\ScaleUnit.Posnet.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ScaleUnit.Posnet.Installer**.
        - **CRT local sur le PDV moderne :** Dans le dossier **Posnet\\ModernPOS\\ModernPOS.Posnet.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ModernPOS.Posnet.Installer**.

    1. Démarrez le programme d’installation de l’extension CRT à partir de la ligne de commande :

        - **Commerce Scale Unit :**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **CRT local sur le PDV moderne :**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Installez les extensions de station matérielle :

    1. Dans le dossier **Posnet\\HardwareStation\\HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **HardwareStation.PosnetThermalFVFiscalPrinter.Installer**.
    1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande :

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **Posnet build-pipeline.yml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration de l’imprimante fiscale pour la Pologne est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Posnet** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour la Pologne (héritées)](emea-pol-fpi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques à l’imprimante et de gérer les réponses de l’imprimante fiscale. Cette extension génère un ensemble de commandes spécifiques à l’imprimante au format JavaScript Object Notation (JSON) qui sont définies par la spécification POSNET 19-3678.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **DocumentProviderPosnetProtocol** est le point d’entrée de la demande de génération de documents à partir de l’imprimante fiscale.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre à l’imprimante qui doit être enregistré dans l’imprimante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : ventes, impression du rapport X et impression du rapport Z.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du fournisseur de document fiscal se trouve dans **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du fournisseur de documents fiscaux depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec l’imprimante fiscale. Cette extension appelle les fonctions du pilote POSNET pour soumettre des commandes que l’extension de CRT génère à l’imprimante fiscale. Il gère également les erreurs de périphérique.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **FiscalPrinterHandler** est le point d’entrée pour le traitement de demandes au périphériques fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents aux imprimantes et renvoie une réponse de l’imprimante fiscale.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé se l’appareil.
- **InitializeFiscalDeviceRequest** – Cette requête est utilisée pour l’initialisation de l’imprimante.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du connecteur fiscal se trouve dans **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
