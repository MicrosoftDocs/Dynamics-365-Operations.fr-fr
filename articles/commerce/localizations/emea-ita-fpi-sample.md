---
title: Exemple d’intégration de l’imprimante fiscale pour l’Italie
description: Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour l’Italie dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 02226fd9f2c92db2518ca48baefb680a3d2f0ac1
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076901"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Exemple d’intégration de l’imprimante fiscale pour l’Italie

[!include[banner](../includes/banner.md)]

Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour l’Italie dans Microsoft Dynamics 365 Commerce.

La fonctionnalité Commerce pour l’Italie comprend un exemple d’intégration du point de vente (PDV) avec une imprimante fiscale. L’échantillon étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) pour qu’elle fonctionne avec les imprimantes [Série Epson FP-90III](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) d’Epson et permet la communication avec une imprimante fiscale en mode serveur Web via le service Web EpsonFPMate à l’aide de l’API Fiscal ePOS-Print. L’exemple prend uniquement en charge le mode Registratore Telematico (RT). L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) Retail.

Microsoft ne publie aucun matériel, logiciel ou documentation d’Epson. Pour plus d’informations sur la façon d’obtenir l’imprimante fiscale et de l’utiliser, contactez [Epson Italia S.p.A](https://www.epson.it).

## <a name="scenarios"></a>Scénarios

Les scénarios suivants sont couverts par l’exemple d’intégration de l’imprimante fiscale pour l’Italie :

- Scénarios de vente :

    - Imprimez un reçu fiscal pour les ventes et les retours au comptant sans livraison.
    - Capturez une réponse de l’imprimante fiscale et stockez-la dans la base de données des canaux.
    - Taxes :

        - Mappage vers les codes fiscaux de l’imprimeur fiscal (départements).
        - Transférez les données fiscales mappées vers l’imprimante fiscale.
        - Imprimez les taxes sur un reçu fiscal.

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

    - Imprimez un code à barres pour le numéro de reçu sur un reçu fiscal.
    - Imprimer les [Informations client](emea-ita-customer-information.md) qui est spécifié pour une transaction de vente sur un reçu fiscal. Un exemple de ces informations est le code de loterie du client. 

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
- Les rapports quotidiens (fiscal X et fiscal Z) sont imprimés en utilisant le format intégré au micrologiciel de l’imprimante fiscale.
- L’imprimante fiscale ne prend pas en charge les transactions mixtes. L’option **Interdire de mélanger les ventes et les retours dans un seul reçu** doit être définie sur **Oui** dans les profils de fonctionnalité PDV.
- L’exemple prend en charge l’intégration uniquement avec une imprimante fiscale qui fonctionne en mode Registratore Telematico (RT)).

## <a name="set-up-fiscal-integration-for-italy"></a>Paramétrer l’intégration fiscale pour l’Italie

L’échantillon d’intégration de l’imprimante fiscale pour l’Italie est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\EpsonFP90IIISample** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour l’Italie (héritées)](emea-ita-fpi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

Suivez les étapes de configuration de l’intégration fiscale décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Notez également les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à cet échantillon d’intégration de l’imprimante fiscale](#set-up-the-registration-process).
1. [Configurer les textes fiscaux pour les remises](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configurer les états X/Z fiscaux depuis le PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Activer l’exécution manuelle d’un enregistrement fiscal reporté](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurer la fonctionnalité de gestion des informations client dans PDV](emea-ita-customer-information.md#setup).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurer le processus d’inscription

Pour activer le processus d’enregistrement, procédez comme suit pour configurer Commerce Headquarters. Pour plus d’informations sur l’intégration fiscale, voir [Configuration de l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK)/application (par exemple, **[version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Ouvrez **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Téléchargez le fichier de configuration du fournisseur de document sur **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (par exemple, le [fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml** (par exemple, [le fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichier de configuration du fournisseur de document :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
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

- **Mappage des types d’appel d’offres** – Le mappage des modes de paiement configurés pour le magasin avec les types de paiement pris en charge par l’imprimante fiscale. L’exemple suivant montre le mappage par défaut.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Voici une explication des attributs dans ce mappage :

    - **StorePaymentMethod** est un mode de paiement qui est mis en place pour le magasin à **Retail et Commerce \> Configuration des canaux \> Modes de paiement \> Modes de paiement**.
    - **PrinterPaymentType** and **PrinterPaymentIndex** correspondent au type de paiement et à l’indice correspondants définis dans la documentation de l’imprimante fiscale Epson.
    - **DepositPaymentMethod** est utilisé pour spécifier le type de paiement et l’index d’une imprimante pour la partie du montant de la collecte de la commande client qui est réglée avec le dépôt de la commande client.

    La table suivante montre comment le mappage des modes de paiement correspond au stockage des modes de paiement configurés dans les données de démonstration standard.

    | Mode de règlement | Nom du mode de paiement |
    |----------------|---------------------|
    | 1              | Monétaire                |
    | 3              | Carte                |
    | 4              | Compte client    |
    | 6              | Devise            |
    | 8              | Carte cadeau           |

    Vous devez modifier l’exemple de mappage en fonction des modes de paiement configurés dans votre application.

- **Type de code-barres pour le numéro de reçu** – Le type de code à barres utilisé pour afficher un numéro de reçu sur un reçu fiscal. Le mappage par défaut est **CODE128**.
- **Imprimer les données fiscales dans l’en-tête du reçu** – Si ce paramètre est activé, les informations du magasin seront imprimées sur le reçu fiscal. Ces informations comprennent le nom, l’adresse et le numéro d’identification fiscale du magasin, ainsi que le nom du caissier.
- **Mappage du service d’impression fiscale** – Le mappage des services de l’imprimante fiscale avec les taux de taxe sur la valeur ajoutée (TVA), les natures exonérées de TVA et les types de produits. L’exemple suivant montre le mappage par défaut.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Voici une explication des attributs dans ce mappage :

    - **VATRate** est un taux de TVA pris en charge qui est configuré en tant que code de taxe de vente. La valeur dans le mappage a deux décimales mais pas de séparateur décimal. Par example, **2200** représente 22 pour cent, et **1000** représente 10 pour cent.
    - **VATExemptNature** n’est applicable que dans les cas où le taux de TVA est de 0 (zéro), y compris les cas où il n’y a pas de taxe. Actuellement, **VATExemptNature** est pris en charge uniquement pour les cartes-cadeaux, et la valeur dans le mappage doit correspondre à la valeur de la propriété **VATExemptNatureForGiftCard** dans le fichier de configuration XML.
    - **ProductType** est le type de produit. Une valeur de **0** représente les marchandises et une valeur de **1** représente les services.
    - **DepartmentNumber** est le numéro du département qui est configuré dans l’imprimante et qui correspond aux trois attributs précédents.

    Vous devez modifier l’exemple de mappage en fonction des taux de TVA qui sont configurés dans votre application et des services correspondants qui sont configurés dans votre imprimante fiscale.

- **Nature de l’exonération de TVA pour carte cadeau** – Le caractère exonéré de TVA qui doit être appliqué lors de l’émission ou du rechargement d’une carte cadeau. La valeur doit correspondre à une entrée dans le mappage du service d’impression fiscale. Le mappage par défaut est **NS**.
- **Activer les articles gratuits** – Si ce paramètre est activé, le type d’ajustement de remise *omaggio* pour les articles bénéficiant d’une remise de 100 % est activé.
- **Code d’information pour l’origine du retour** – Le code d’information utilisé pour saisir l’origine d’une transaction de retour si aucun reçu de vente original n’est fourni. Ce paramètre est utilisé avec les paramètres **Code d’information pour la date de vente d’origine** et **Mappage d’origine de retour** pour générer un message correct dans le reçu fiscal sur l’origine d’une transaction de retour si aucune transaction de vente d’origine n’existe. 

    Ce code info doit être paramétré pour permettre à l’utilisateur de sélectionner ou de saisir l’une des origines possibles des retours dans vos magasins. Par exemple, il peut être configuré comme une liste de sous-codes (tels que **Retour du site** ou **Retour du kiosque**). Le paramètre **Mappage d’origine de retour** est ensuite utilisé pour traduire la valeur de le code info en une commande pour l’imprimante fiscale.

    Le code info sélectionné pour **Code info pour l’origine du retour** doit être configuré comme un code info obligatoire qui est déclenché une fois par transaction de vente. Il doit être attribué comme code info **Retourner le produit** dans le profil de fonctionnalité PDV, afin qu’il soit déclenché lorsque l’opération **Retourner le produit** est exécutée.

    Aucune valeur par défaut n’est spécifiée pour ce mappage. Vous devez sélectionner un code info configuré dans votre application.

- **Code info pour la date de vente d’origine** – Le code info utilisé pour saisir la date de vente d’origine d’une transaction de retour si aucun reçu de vente original n’est fourni. Ce paramètre est utilisé avec les paramètres **Code d’information pour l’origine du retour** et **Mappage d’origine de retour** pour générer un message correct dans le reçu fiscal sur l’origine d’une transaction de retour si aucune transaction de vente d’origine n’existe.

    Le code info doit être configuré de manière à ce que le champ **Type d’entrée** soit défini sur **Date**. Il doit être configuré comme un code info obligatoire qui est déclenché une fois par transaction de vente. Il devrait également être attribué comme **Code info lié** pour le code info qui est sélectionné pour le paramètre **Code info pour l’origine du retour**, de sorte que les deux codes info soient déclenchés l’un après l’autre.

    Aucune valeur par défaut n’est spécifiée pour ce mappage. Vous devez sélectionner un code info configuré dans votre application.

- **Mappage de l’origine du retour** – Le mappage des origines du retour utilisé pour imprimer l’origine d’une transaction de retour si aucun reçu de vente original n’est fourni. Ce paramètre est utilisé avec les paramètres **Code info pour l’origine du retour** et **Code info pour la date de vente d’origine** pour générer un message correct dans le reçu fiscal sur l’origine d’une transaction de retour si aucune transaction de vente d’origine n’existe. L’exemple suivant montre le mappage par défaut.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Voici une explication des attributs dans ce mappage :

    - **ReturnOrigin** est l’une des origines possibles des retours dans vos magasins. La valeur doit correspondre à une valeur du paramètre **Code info pour l’origine du retour**.
    - **PrinterReturnOrigin** est l’une des origines de retour acceptées par l’imprimeur fiscal (**PDV**, **RV**, ou **ND**).
    - **PrinterReturnOriginWithoutFiscalData** est l’origine de retour acceptée par l’imprimante fiscale et qui correspond à une transaction de retour liée à une transaction de vente d’origine qui n’a pas de données fiscales liées, car elle n’a pas été enregistrée via une imprimante fiscale. Dans ce cas, la date de vente d’origine est identifiée comme la date de la transaction de vente d’origine.

Les mappages de données par défaut suivants sont obsolètes et ne sont conservés qu’à des fins de compatibilité descendante :

- Cartographie des codes de taxe sur la valeur ajoutée (TVA)
- Type de paiement pour les dépôts

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Adresse du point de terminaison** – L’URL de l’imprimante.
- **Synchronisation de la date et de l’heure** – Une valeur qui spécifie si la date et l’heure de l’imprimante doivent être synchronisées avec la station matérielle connectée.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour l’Italie (héritées)](emea-ita-fpi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

#### <a name="set-up-the-development-environment"></a>Configurer l’environnement de développement

Pour configurer un environnement de développement pour tester et étendre l’exemple, procédez comme suit.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information : [Télécharger les exemples et les packages de référence du SDK Retail depuis GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution d’intégration d’imprimante fiscale sur **Dynamics365Commerce.Solutions\\Intégration Fiscale\\EpsonFP90IIISample\\EpsonFP90IIISample.sln**, et le générer.
1. Installer les extensions CRT :

    1. Recherchez le programme d’installation de l’extension CRT :

        - **Commerce Scale Unit :** Dans le dossier **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ScaleUnit.EpsonFP90III.Installer**.
        - **CRT local sur le PDV moderne :** Dans le dossier **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ModernPOS.EpsonFP90III.Installer**.

    1. Démarrez le programme d’installation de l’extension CRT à partir de la ligne de commande :

        - **Commerce Scale Unit :**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **CRT local sur le PDV moderne :**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Installez les extensions de station matérielle :

    1. Dans le dossier **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **HardwareStation.EpsonFP90III.Installer**.
    1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande :

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **EpsonFP90III build-pipeline.yml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration de l’imprimante fiscale pour l’Italie est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\EpsonFP90IIISample** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration de l’imprimante fiscale pour l’Italie (héritées)](emea-ita-fpi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques à l’imprimante et de gérer les réponses de l’imprimante fiscale.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **DocumentProviderEpsonFP90III** est le point d’entrée de la demande de génération de documents à partir de l’imprimante fiscale.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre à l’imprimante qui doit être enregistré dans l’imprimante fiscale.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : ventes, impression du rapport X et impression du rapport Z.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du fournisseur de document fiscal se trouve dans **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du fournisseur pour le fournisseur de documents depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec l’imprimante fiscale. Cette extension utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère à l’imprimante fiscale. Elle gère également les réponses reçues de l’imprimante fiscale.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **EpsonFP90IIISample** est le point d’entrée pour le traitement de demandes au périphériques fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents aux imprimantes et renvoie une réponse de l’imprimante fiscale.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé se l’appareil.
- **InitializeFiscalDeviceRequest** – Cette requête est utilisée pour l’initialisation de l’imprimante.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du connecteur fiscal se trouve dans **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage pour le connecteur depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
