---
title: Exemple d’intégration de l’unité de contrôle pour la Suède
description: Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour la Suède dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 32c2cf31d82d17d3391536e7a9f1722e1462c336
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944764"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Exemple d’intégration de l’unité de contrôle pour la Suède

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour la Suède dans Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Cet exemple de fonctionnalité d’intégration fiscale remplace [l’échantillon précédent pour l’intégration POS avec des unités de contrôle pour la Suède](retail-sdk-control-unit-sample.md). L’échantillon précédent ne tire pas parti du [cadre d’intégration fiscale](./fiscal-integration-for-retail-channel.md) et deviendra obsolète dans les mises à jour ultérieures. Pour plus d’informations sur la migration de l’exemple précédent vers l’exemple qui correspond à Dynamics 365 Commerce version **10.0.22 et versions antérieures**, voir [Migration à partir de l’exemple d’intégration précédent](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

La fonctionnalité Commerce pour la Suède comprend un exemple d’intégration du point de vente (PDV) avec des dispositifs fiscaux spécifiques à la Suède connus sous le nom *d’unités de contrôle*. Cet exemple étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). On suppose qu’une unité de contrôle est physiquement connectée à une station matérielle avec laquelle le PDV est couplé. À titre d’exemple, cet exemple utilise l’interface de programmation d’applications (API) de l’unité de contrôle [CleanCash Type A](https://www.retailinnovation.se/produkter) par Retail Innovation HTT AB. La version 1.1.4 de l’API CleanCash est utilisée.

L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) Retail.

Microsoft ne publie aucun matériel, logiciel ou documentation de Retail Innovation HTT AB. Pour plus d’informations sur la façon d’obtenir l’unité de contrôle et de l’utiliser, contactez [Retail Innovation HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Scénarios

L’exemple d’intégration d’unité de contrôle pour la Suède comprend les fonctionnalités suivantes :

- Les ventes, les retours et les copies de reçus sont automatiquement enregistrés dans une unité de contrôle connectée à la station matérielle associée au point de vente.
- Le code de contrôle et le numéro de fabrication de l’unité de contrôle pour une transaction enregistrée sont capturés à partir de l’unité de contrôle et enregistrés dans la transaction. Ces données sont également appelées *réponse fiscale*. La réponse fiscale peut être consultée sur la page **Opérations en magasin**.
- Des champs personnalisés pour le code de contrôle et le numéro de fabrication de l’unité de contrôle peuvent être ajoutés à une disposition de reçu. De cette façon, vous pouvez imprimer la réponse fiscale d’une transaction sur un reçu.
- La réponse fiscale pour une transaction est indiquée sur l’état de canal **Journal électronique (Suède)**.
- Plusieurs options de gestion des erreurs sont disponibles. Voici quelques exemples :

    - Réessayez l’enregistrement fiscal, si une nouvelle tentative est possible. Vous pouvez réessayer l’enregistrement fiscal si, par exemple, l’unité de contrôle n’est pas connectée, n’est pas prête ou ne répond pas.
    - Reporter l’enregistrement fiscal.
    - Ignorez l’enregistrement fiscal ou marquez la transaction comme enregistrée et incluez des codes d’information pour capturer la raison de l’échec et des informations supplémentaires.
    - Vérifiez la disponibilité de l’unité de contrôle avant l’ouverture d’une nouvelle opération de vente ou la finalisation d’une opération de vente.

### <a name="limitations-of-the-sample"></a>Limites de l’échantillon

L’exemple d’intégration d’unité de contrôle pour la Suède ne prend actuellement pas en charge les scénarios de commande client.

## <a name="setting-up-the-integration-with-control-units"></a>Configuration de l’intégration avec des unités de contrôle

Pour plus d’informations sur la configuration requise pour la Suède, voir [Configuration de Commerce pour la Suède](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Configurer des reçus spécifiques à la Suède

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900001.

Ajoutez les étiquettes de point de vente suivantes dans la section **PDV** de la page **Texte en langue étrangère**.

| ID langue | ID texte | Texte                  |
|-------------|---------|-----------------------|
| fr-FR       | 900001  | Enregistrer le code de contrôle |
| fr-FR       | 900002  | Enregistrer le périphérique       |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère**.

| Name                         | Type    | ID texte de la légende |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Récépissé | 900001          |
| SE_FISCALREGISTERID          | Récépissé | 900002          |

> [!NOTE]
> Il est important que vous spécifiiez des noms de champs personnalisés corrects, comme indiqué dans le tableau ci-dessus. Un nom de champ personnalisé incorrect entraînera des données manquantes dans les reçus.

#### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse requis, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans la section **Pied de page**. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente de cette rubrique.

- **Enregistrer le code de contrôle** – Ce champ imprime le code de contrôle.
- **Enregistrer l’appareil** – Ce champ imprime le numéro de fabrication de l’unité de contrôle.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Modèles de tickets de caisse et impression](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Paramétrer l’intégration fiscale pour la Suède

L’échantillon d’intégration de l’unité de contrôle pour la Suède est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\CleanCash** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’unité de contrôle pour la Suède (héritées)](emea-swe-fi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

Suivez les étapes de configuration de l’intégration fiscale décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Notez également les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à cet échantillon d’intégration de l’unité de contrôle](#set-up-the-registration-process).
1. [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Activer l’exécution manuelle d’un enregistrement fiscal reporté](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurer le processus d’inscription

Pour activer le processus d’enregistrement, procédez comme suit pour configurer Commerce Headquarters. Pour plus d’informations sur l’intégration fiscale, voir [Configuration de l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK)/application (par exemple, **[version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Ouvrez **src \> FiscalIntegration \> CleanCash**.
    1. Téléchargez le fichier de configuration du fournisseur de document sur **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (par exemple, le [fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (par exemple, [le fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichier de configuration du fournisseur de document :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
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

- **Mappage du code de la taxe sur la valeur ajoutée (TVA)** – Ce mappage définit les codes de taxe sur la valeur ajoutée (TVA) spécifiques à l’appareil aux codes de taxe de vente correspondants. Le mappage du code TVA doit avoir le format suivant :

    ```
    1 : code1 ; 2 : code2
    ```

    Voici une explication de ce format :

    - *1* et *2* sont des codes TVA spécifiques à l’appareil.
    - Un point-virgule (;) est utilisé comme séparateur.
    - *code1* et *code2* sont des codes de taxe de vente configurés au siège de Commerce. Vous devez modifier l’exemple de mappage en fonction des codes taxes configurés dans votre application.

    Les unités de contrôle prennent en charge jusqu’à quatre codes TVA différents. Par conséquent, le mappage du code TVA peut être configuré de la manière suivante :

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Plusieurs codes de taxe de vente peuvent être mappés sur le même code TVA spécifique à l’appareil.

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Chaîne de connexions** – Les paramètres de connexion de l’unité de contrôle.
- **Délai d’expiration** – La durée, en millisecondes, pendant laquelle le pilote attendra une réponse de l’unité de contrôle.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’unité de contrôle pour la Suède (héritées)](emea-swe-fi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

#### <a name="set-up-the-development-environment"></a>Configurer l’environnement de développement

Pour configurer un environnement de développement pour tester et étendre l’exemple, procédez comme suit.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information : [Télécharger les exemples et les packages de référence du SDK Retail depuis GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution d’intégration d’unité de contrôle sur **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln**, et le générer.
1. Installer les extensions CRT :

    1. Recherchez le programme d’installation de l’extension CRT :

        - **Commerce Scale Unit :** Dans le dossier **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ScaleUnit.CleanCash.Installer**.
        - **CRT local sur le PDV moderne :** Dans le dossier **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ModernPOS.CleanCash.Installer**.

    2. Démarrez le programme d’installation de l’extension CRT à partir de la ligne de commande :

        - **Commerce Scale Unit :**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **CRT local sur le PDV moderne :**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Installez les extensions de station matérielle :

    1. Dans le dossier **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **HardwareStation.CleanCash.Installer**.
    1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande :

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **CleanCash build-pipeline.yml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Conception les extensions

L’échantillon d’intégration de l’unité de contrôle pour la Suède est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\CleanCash** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’unité de contrôle pour la Suède (héritées)](emea-swe-fi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

### <a name="crt-extension-design"></a>Conception des extensions CRT

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses de l’unité de contrôle.

#### <a name="request-handler"></a>Gestionnaire de demandes

Il y a un seul gestionnaire de demandes **DocumentProviderCleanCash** pour le fournisseur de documents. Il est utilisé pour générer des documents fiscaux pour l’unité de contrôle.

Ce gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans l’unité de contrôle.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements de vente et les événements d’audit sont pris en charge.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du fournisseur de document fiscal se trouve dans **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du fournisseur pour le fournisseur de documents depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec l’unité de contrôle. Elle utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère à l’unité de contrôle. Elle gère également les réponses reçues de l’unité de contrôle.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **CleanCashHandler** est le point d’entrée pour le traitement des demandes à l’unité de contrôle.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents à l’unité de contrôle et renvoie une réponse de celui-ci.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé de l’unité de contrôle.
- **InitializeFiscalDeviceRequest** – Cette requête est utilisée pour l’initialisation de l’unité de contrôle.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du connecteur fiscal se trouve dans **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage pour le connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
