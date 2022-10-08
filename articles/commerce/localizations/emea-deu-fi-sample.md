---
title: Exemple d’intégration du service d’enregistrement fiscal pour l’Allemagne
description: Cet article fournit une présentation d’un exemple d’intégration fiscale pour l’Allemagne dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-05-29
ms.openlocfilehash: a725badbce498e4e7b35aecb2500e273586c7b77
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631451"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Exemple d’intégration du service d’enregistrement fiscal pour l’Allemagne

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cet article fournit une présentation d’un exemple d’intégration fiscale pour l’Allemagne dans Microsoft Dynamics 365 Commerce.

Pour répondre aux exigences fiscales locales pour les caisses enregistreuses en Allemagne, la fonctionnalité Dynamics 365 Commerce pour l’Allemagne comprend un exemple d’intégration du point de vente (PDV) avec un service d’enregistrement fiscal externe. L’exemple étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). Elle est basée sur la solution [EFR (Registre fiscal électronique)](https://www.efsta.eu/de/fiskalloesungen/deutschland) de [l’EFSTA](https://www.efsta.eu/de/) et permet la communication avec le service EFR via le protocole HTTPS. Le service EFR doit être hébergé sur Retail Hardware Station ou sur un ordinateur distinct pouvant être connectée à partir de la station matérielle. L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) de Commerce.

Microsoft ne publie aucun matériel, logiciel ou documentation de l’EFSTA. Pour savoir comment obtenir la solution EFR et l’exploiter, contactez [l’EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Scénarios

Les scénarios suivants sont couverts par l’exemple d’intégration du service d’enregistrement fiscal pour l’Allemagne.

### <a name="sales-operations"></a>Opérations de vente

- **Enregistrement des ventes au comptant et des retours dans le service d’enregistrement fiscal :**

    L’enregistrement des opérations de vente comprend les étapes suivantes :

    1. Enregistrement de la date de début

        Le début de chaque transaction est enregistré dans un élément technique de sécurité (TSE) connecté au service EFR. À la suite de l’enregistrement, un TSE attribue un ID de transaction (TID).

    2. Enregistrement de la date de fin

        Quand une transaction est conclue au point de vente, elle est enregistrée en utilisant le même TID qui a été attribué au moment de l’enregistrement du début de la transaction. À ce moment, les données détaillées de la transaction sont envoyées au service d’enregistrement fiscal. Ces données incluent des informations sur la ligne de vente et des informations sur les remises, les paiements et les taxes.

    3. Capture d’une réponse du service d’enregistrement fiscal

        Les données de sécurité sont reçues d’un TSE dans le cadre d’une réponse et sont enregistrées dans la transaction dans la base de données du canal. Les données de sécurité sont constituées des informations suivantes :

        - TID
        - Date et heure de début de la transaction
        - Date et heure de fin de la transaction
        - Compteur de signatures
        - Vérifier la valeur
        - Numéro de série du TSE

- **Enregistrement des commandes client dans le service d’enregistrement fiscal :** Le processus d’enregistrement est le même que le processus pour les ventes et les retours au comptant sans livraison.
- **Enregistrement des opérations comprenant des cartes-cadeaux et des acomptes :** Le processus d’enregistrement est le même que le processus pour les ventes et les retours au comptant sans livraison.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>Notifier les utilisateurs des échecs d’enregistrement fiscal

Le service d’enregistrement fiscal peut notifier les utilisateurs des échecs survenus au moment de l’enregistrement fiscal de deux manières :

- Imprimer les informations supplémentaires de la réponse dans le champ **Message d’information** sur les reçus.
- Afficher les notifications du service fiscal sous forme de messages d’utilisateur au PDV.

    > [!NOTE]
    > Ce mécanisme de notification exige que le paramètre **Afficher les notifications d’enregistrement fiscal** sur la page **Profils techniques des connecteurs** soit activé.

#### <a name="printing-receipts"></a>Impression des tickets de caisse

L’impression des reçus est obligatoire en Allemagne. Tous les reçus doivent contenir au moins les informations suivantes :

- Nom et adresse de la société
- Informations sur les marchandises, y compris leurs prix et quantités
- Informations sur les paiements reçus
- Informations sur les taxes, y compris les montants totaux par taux d’imposition
- Sécurité des données :

    - TID
    - Date et heure de début de la transaction
    - Date et heure de fin de la transaction
    - Compteur de signatures
    - Vérifier la valeur
    - Numéro de série du TSE

- Message d’information

> [!NOTE]
> Un code QR peut également être imprimé sur les reçus. Bien que le code QR soit facultatif, il est fortement recommandé. Pour plus d’informations sur la façon d’obtenir un code QR dans le cadre d’une réponse du service d’enregistrement fiscal, consultez le document "Guide EFR \[DE\]" publié sur le site Internet [Documentation EFSTA](https://public.efsta.net/efr/).
>
> Le champ **Message d’information** sur les reçus affiche une notification du service d’enregistrement fiscal. Par exemple, si un dispositif de signature est interrompu, un texte spécial peut être imprimé sur un reçu.

#### <a name="voided-suspended-and-recalled-transactions"></a>Transactions nulles, en suspens et rappelées

- Une transaction annulée est enregistrée en tant que demande de terminaison d’une transaction dans le service d’enregistrement fiscal.
- Une transaction en suspens est enregistrée en tant que demande de terminaison d’une transaction dans le service d’enregistrement fiscal.
- Le rappel d’une transaction est enregistré en tant que début de la nouvelle transaction dans le service d’enregistrement fiscal.

### <a name="non-sales-transactions-and-shift-closing"></a>Transactions non commerciales et clôture des équipes

Les opérations non commerciales suivantes sont enregistrées en tant qu’opérations non fiscales dans le service d’enregistrement fiscal en utilisant le mot-clé **NFS** :

- Déclarer le montant de départ
- Entrée de fond de caisse
- Vider la caisse
- Mise en coffre-fort
- Remise en banque
- Comptes de revenus
- Comptes de dépenses

L’opération **Fermer l’équipe** est également enregistrée en tant qu’opération non fiscale dans le service d’enregistrement fiscal en utilisant le mot-clé **NFS**.

### <a name="data-export-and-audit"></a>Exportation de données et audit

Toutes les transactions doivent être signées par un TSE pour garantir leur intégrité, leur authenticité et leur exhaustivité, et pour aider à empêcher la manipulation des données enregistrées.

> [!WARNING]
> Seul un TSE certifié peut être utilisé. Pour plus d’informations sur les types et les modèles d’EST pris en charge dans la solution EFR, consultez le document "Guide EFR \[DE\]" qui est publié sur le site web [Documentation EFSTA](https://public.efsta.net/efr/). Pour savoir comment choisir et obtenir un TSE, contactez [l’EFSTA](https://www.efsta.eu/at/kontakt).

Les réglementations en Allemagne nécessitent une prise en charge de l’exportation DSFinV-K. L’export DSFinV-K peut être déclenché dans la solution EFR. Pour plus d’informations sur l’export DSFinV-K, consultez le document "Guide EFR \[DE\]" publié sur le site web [Documentation EFSTA](https://public.efsta.net/efr/).

### <a name="limitations-of-the-sample"></a>Limites de l’échantillon

Le service d’enregistrement fiscal prend en charge uniquement les scénarios où la taxe de vente est incluse dans les prix. Par conséquent, l’option **Les prix comprennent la taxe de vente** doit être définie sur **Oui** pour les magasins et les clients.

Le service fiscal ne prend pas en charge les situations dans lesquelles plusieurs codes de taxe de vente sont appliqués à la même ligne de transaction.

Le cadre d’intégration fiscale ne prend pas en charge les devis de vente. Ces opérations ne sont donc pas enregistrées au service fiscal.

## <a name="set-up-commerce-for-germany"></a>Configurer Commerce pour l’Allemagne

Cette section décrit les paramètres Commerce spécifiques et recommandés pour l’Allemagne. Pour plus d’informations sur la configuration, voir [Page d’accueil de Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique à l’Allemagne, vous devez spécifier les paramètres suivants.

- Dans l’adresse principale de l’entité juridique, définissez le champ **Pays/région** sur **DEU** (Allemagne).
- Dans le profil de fonctionnalité du PDV de chaque magasin situé en Allemagne, définissez le champ **Code ISO** sur **DE** (Allemagne).

Vous devez également spécifier les paramètres suivants pour l’Allemagne. Vérifiez que vous exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

### <a name="set-up-vat-per-german-requirements"></a>Paramétrer la TVA selon les exigences de l’Allemagne

Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation des fonctionnalités sur les taxes, voir [Vue d’ensemble des taxes](../../finance/general-ledger/indirect-taxes-overview.md).

Sur les reçus de vente, vous pouvez imprimer un code abrégé pour un code de taxe de vente (par exemple, "A" ou "B"). Pour rendre cette fonctionnalité disponible, définissez le champ **Code pour l’impression** sur la page **Codes de taxe de vente**.

### <a name="set-up-stores"></a>Paramétrage des magasins

Sur la page **Tous les magasins**, mettez à jour les détails du magasin. Spécifiquement, définissez les paramètres suivants :

- Dans le champ **Groupe de taxe de vente**, spécifiez le groupe de taxe de vente à utiliser pour les ventes au client par défaut.
- Définissez l’option **Les prix incluent la taxe** sur **Oui**.
- Définissez le champ **Nom** au nom de l’entreprise. Ce changement permet de s’assurer que le nom de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le nom de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.
- Définissez le champ **Numéro d’identification de taxe (TIN)** sur numéro d’identification de l’entreprise. Ce changement permet de s’assurer que le numéro d’identification de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le numéro d’identification de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.

### <a name="set-up-functionality-profiles"></a>Paramétrage des profils de fonctionnalité

Paramétrage des profils de fonctionnalité de PDV. Sur l raccourci **Numérotation des reçus**, configurez la numérotation des reçus en créant ou en mettant à jour des enregistrements pour les types de transactions de réception **Vente**, **Commande client** et **Retour**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse du PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900 001.

Ajoutez les étiquettes de point de vente suivantes à la section **PDV** de la page **Texte en langue étrangère**.

| ID langue | ID texte | Texte                                  |
|-------------|---------|---------------------------------------|
| fr-FR       | 900001  | Code QR                               |
| fr-FR       | 900002  | ID transaction                        |
| fr-FR       | 900003  | Code d’impression de la taxe de vente au détail                 |
| fr-FR       | 900004  | Montant de la taxe (ventes)                    |
| fr-FR       | 900005  | Base de la taxe (ventes)                     |
| fr-FR       | 900006  | Heure de début de la transaction           |
| fr-FR       | 900007  | Heure de fin de transaction             |
| fr-FR       | 900008  | Numéro de série de l’élément de sécurité |
| fr-FR       | 900009  | Compteur de signatures                     |
| fr-FR       | 900010  | Vérifier la valeur                           |
| fr-FR       | 900011  | Message d’info                          |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** spécifiées dans la page **Texte en langue étrangère**.

| Name                            | Type    | ID texte de la légende |
|---------------------------------|---------|-----------------|
| QRCODE\_DE                      | Récépissé | 900001          |
| TRANSACTIONID\_DE               | Récépissé | 900002          |
| RETAILPRINTCODE\_DE             | Récépissé | 900003          |
| SALESTAXAMOUNT\_DE              | Récépissé | 900004          |
| SALESTAXBASIS\_DE               | Récépissé | 900005          |
| TRANSACTIONSTARTDATETIME\_DE    | Récépissé | 900006          |
| TRANSACTIONENDDATETIME\_DE      | Récépissé | 900007          |
| SECURITYELEMENTSERIALNUMBER\_DE | Récépissé | 900008          |
| SIGNCOUNTER\_DE                 | Récépissé | 900009          |
| SIGN\_DE                        | Récépissé | 900010          |
| INFOMESSAGE\_DE                 | Récépissé | 900011          |

> [!NOTE]
> Il est important que vous spécifiiez des noms de champs personnalisés corrects, comme indiqué dans le tableau précédent. Un nom de champ personnalisé incorrect entraînera des données manquantes dans les reçus.

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse requis, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

- **En-tête :** Ajoutez les champs suivants :

    - Les champs **Nom du magasin** et **Numéro d’identification fiscale**, qui sont utilisés pour imprimer le nom de l’entreprise et le numéro d’identification sur les reçus. Vous pouvez également ajouter le nom de l’entreprise et le numéro d’identification à la disposition du ticket de caisse sous forme de texte libre.
    - Les champs **Adresse du magasin**, **Date**, **Heure 24H**, **Numéro de reçu**, et **Numéro d’enregistrement**.

- **Lignes :** Ajoutez les champs suivants :

    - Champ **Nom de l’article**
    - Champ **Qté**
    - Champ **Prix total avec taxe**
    - Champ **Code d’impression de la taxe de vente au détail**, qui est utilisé pour imprimer le code abrégé qui correspond au code de taxe de vente qui s’applique à l’article

- **Pied de page :** Ajoutez les champs suivants :

    - Champs de paiement, afin que les montants de paiement pour chaque mode de paiement soient imprimés. Par exemple, ajoutez les champs **Nom de l’offre** et **Montant de l’offre** à une ligne de la disposition.
    - Champs dans le groupe de champs **Ventilation fiscale**. Tous les champs de ce groupe de champs doivent être imprimés sur une ligne distincte.

        - Le champ **ID taxe** standard qui active une synthèse de taxe à imprimer pour chaque code taxe. Le champ doit être ajouté sur une nouvelle ligne.
        - Le champ **Pourcentage d’impôt**, qui est un champ standard utilisé pour imprimer le taux de taxe effectif pour le code de taxe de vente.
        - Le champ **Base de la taxe (ventes)** qui permet d’imprimer le montant total des disponibilités pour le code de taxe de vente. Les acomptes et les opérations de carte cadeau sont exclues.
        - Le champ **Montant de la taxe (ventes)** qui permet d’imprimer le montant de la taxe du reçu pour les ventes en espèces pour le code de taxe de vente.
        - Le champ **Code d’impression de la taxe de vente au détail**, qui est utilisé pour imprimer le code abrégé qui correspond au code de taxe de vente.

    - Champs contenant des données de transaction sécurisées renvoyées par le service d’enregistrement fiscal :

        - Champ **ID transaction** qui identifie le numéro de la transaction en espèces dans le service d’enregistrement fiscal
        - Champ **DateHeure de début de la transaction**
        - Champ **DateHeure de fin de la transaction**
        - Champ **Numéro de série de l’élément de sécurité**
        - Champ **Compteur de signatures**
        - Champ **Vérifier la valeur**
        - Champ **Code QR**, utilisé pour imprimer la référence à la transaction en espèces enregistrée sous forme de code QR

        > [!NOTE]
        > La valeur **Code QR** est extraite de la réponse du registre fiscal. EFR renvoie un code QR dans sa réponse uniquement si la valeur du champ **Attributs** dans la configuration EFR est décrit dans la documentation EFSTA. Le format de code QR dans le champ **Attributs** dans la configuration EFR doit être défini sur **BMP**.

    - Champ **Message d’information** afin que des messages de notification du service d’enregistrement fiscal s’affichent sur les reçus. Par exemple, si un dispositif de signature est interrompu, un texte spécial peut être imprimé sur un reçu.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Paramétrer l’intégration fiscale pour l’Allemagne

L’échantillon d’intégration du service d’enregistrement fiscal pour l’Allemagne est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du SDK de Commerce. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du SDK de Commerce, consultez [Télécharger des exemples et des packages de référence du SDK de Commerce à partir de GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md) et [Configurer un pipeline de build pour le SDK de packaging indépendant](../dev-itpro/build-pipeline.md).

> [!NOTE]
> L’échantillon d’intégration du service d’enregistrement fiscal pour l’Allemagne est disponible dans le SDK de Commerce à partir de la version 10.0.29 de Commerce. Dans la version de 10.0.28 ou antérieure de Commerce, vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Allemagne (héritées)](emea-deu-fi-sample-sdk.md).

Suivez les étapes de configuration de l’intégration fiscale décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md) :

1. [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Notez également les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à cet échantillon d’intégration du service d’enregistrement fiscal](#set-up-the-registration-process).
1. [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Les capacités de gestion des erreurs du cadre d’intégration fiscale pourraient ne pas être entièrement alignées sur les réglementations fiscales locales.
    >
    > - Nous vous recommandons de laisser l’option **Continuer en cas d’erreur** sur la page **Processus d’enregistrement fiscal** désactivée, car toutes les transactions doivent être correctement enregistrées, même si la première tentative d’enregistrement fiscal n’a pas réussi.
    > - Avant d’activer l’option **Ignorer** ou **Marquer comme enregistré** sur la page **Processus d’enregistrement fiscal**, vous devez discuter de ces modifications du processus d’enregistrement fiscal avec votre conseiller fiscal ou le bureau des impôts local.

1. [Activer l’exécution manuelle d’un enregistrement fiscal différé](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurer le processus d’inscription

Pour activer le processus d’enregistrement, procédez comme suit pour configurer Commerce Headquarters. Pour plus d’informations sur l’intégration fiscale, voir [Configuration de l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK).
    1. Ouvrez **src \> FiscalIntegration \> Efr**.
    1. Téléchargez le fichier de configuration du fournisseur de document fiscal sur **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml**.
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **Configurations \> Connectors \> ConnectorEFRSample.xml**.

    > [!NOTE]
    > Dans la version de 10.0.28 ou antérieure de Commerce, vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Lifecycle Services (LCS). Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichier de configuration du fournisseur de document :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleGermany.xml
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez le fichier de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez un profil fonctionnel de connecteur. Sélectionnez le fournisseur de documents et le connecteur que vous avez chargés précédemment. Mettez à jour les [paramètres de mappage des données](#default-data-mapping) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur fiscal chargé précédemment. Mettez à jour les [paramètres du connecteur](#fiscal-connector-settings) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**. Créez un groupe de connecteurs fiscaux pour le profil fonctionnel de connecteur que vous avez créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal et une étape du processus d’enregistrement fiscal et sélectionnez le groupe de connecteurs fiscaux créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils du matériel**. Sélectionnez un profil de matériel lié à la station matérielle auquel le service d'enregistrement fiscal sera connecté. Sur le raccourci **périphériques fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment.
1. Ouvrez le programme de distribution (**Commerce et vente au détail \> Informatique Retail et Commerce \> Programme de distribution**) et sélectionnez les projets **1070** et **1090** pour transférer les données vers la base de données du canal.

#### <a name="default-data-mapping"></a>Mappage des données par défaut

Le mappage de données par défaut suivant est inclus dans la configuration du fournisseur de documents fiscaux fournie dans le cadre de l’exemple d’intégration fiscale :

- **Mappage des types d’appel d’offres** – La mise en correspondance des modes de paiement avec les valeurs de l’attribut **PayG** (groupe de paiement) dans les demandes envoyées au service fiscal. Voici le mappage par défaut :

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    Le premier composant de chaque paire représente un mode de paiement configuré pour le magasin. Le second composant de chaque paire représente un groupe de paiement correspondant pris en charge par le service d’enregistrement fiscal EFR. Pour plus d’informations sur les groupes de paiements pris en charge par EFR pour l’Allemagne, consultez la [Référence EFR](https://public.efsta.net/efr/).

    L’exemple de mappage des modes de paiement correspond au stockage des modes de paiement configurés dans les données de démonstration standard.

    | Mode de règlement | Nom du mode de paiement |
    |----------------|---------------------|
    | 1              | Monétaire                |
    | 2              | Cocher               |
    | 3              | Carte                |
    | 4              | Compte client    |
    | 5              | Autre               |
    | 6              | Devise            |
    | 7              | N° document             |
    | 8              | Carte cadeau           |
    | 9              | Vider la caisse/transférer |
    | 10             | Cartes de fidélité       |
    | 11             | Chèques non locaux    |

    Par conséquent, vous devez modifier l’exemple de mappage en fonction des modes de paiement configurés dans votre application.

- **Inclure les données client** – Si ce paramètre est activé, les demandes adressées au service fiscal contiendront des informations sur le client, telles que les noms et les adresses, dans les cas où un client est ajouté à une transaction.
- **Mappage des taux de taxe sur la valeur ajoutée (TVA)** – Le mappage des valeurs de pourcentage de taxe configurées pour les codes de taxe de vente avec les valeurs de l’attribut **TaxG** (groupe de taxes) dans les demandes envoyées au service fiscal. Voici le mappage par défaut :

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    Le premier composant de chaque paire représente un groupe de taxe TVA pris en charge par le service d’enregistrement fiscal EFR. Le deuxième composant représente le taux de TVA correspondant. Pour plus d’informations sur les groupes de TVA pris en charge par EFR pour l’Allemagne, consultez la [Référence EFR](https://public.efsta.net/efr/).

- **Groupe fiscal pour les cartes-cadeaux et les acomptes** – La valeur de l’attribut **TaxG** dans les demandes qui sont envoyées au service fiscal, en fonction des opérations qui impliquent des cartes-cadeaux ou des acomptes. Voici le mappage par défaut :

    ```
    G
    ```

- **Groupe fiscal pour exonération de TVA** – La valeur de l’attribut **TaxG** dans les demandes qui sont adressées au service fiscal, en fonction des opérations exonérées d’obligations fiscales. Voici le mappage par défaut :

    ```
    F
    ```

> [!NOTE]
> Les paramètres de taxe dans le mappage de données par défaut sont responsables de la mise en correspondance des paramètres de taxe dans le système et des groupes de taxe dans le service EFR. Les groupes de taxes ne peuvent être imprimés sur les reçus que si le champ **Code pour l’impression** est défini sur la page **Codes de taxe de vente**.

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Adresse du point de terminaison** – L’URL du service d’enregistrement fiscal.
- **Délai d’expiration** – La durée, en millisecondes, pendant laquelle le connecteur fiscal attendra une réponse du service d’enregistrement fiscal.
- **Afficher les notifications d’enregistrement fiscal** – Cet indicateur contrôle si les notifications que le service d’enregistrement fiscal renvoie doivent être présentées à l’opérateur.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!NOTE]
> - L’échantillon d’intégration du service d’enregistrement fiscal pour l’Allemagne est disponible dans le SDK de Commerce à partir de la version 10.0.29 de Commerce. Dans la version de 10.0.28 ou antérieure de Commerce, vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Allemagne (héritées)](emea-deu-fi-sample-sdk.md).
> - Les exemples de Commerce déployés dans votre environnement ne sont pas automatiquement mis à jour lorsque vous appliquez des mises à jour de service ou de qualité aux composants de Commerce. Vous devez mettre à jour manuellement les exemples requis.

#### <a name="set-up-the-development-environment"></a>Configurer l’environnement de développement

Pour configurer un environnement de développement pour tester et étendre l’exemple, procédez comme suit.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information, voir [Télécharger les exemples et les packages de référence du SDK de Commerce sur GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution EFR sur **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln**, et générez-la.
1. Installer les extensions de Commerce Runtime :

    1. Recherchez le programme d’installation de l’extension CRT :

        - **Commerce Scale Unit :** Dans le dossier **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ScaleUnit.EFR.Installer**.
        - **CRT local sur le PDV moderne :** Dans le dossier **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ModernPOS.EFR.Installer**.

    1. Démarrez le programme d’installation de l’extension CRT à partir de la ligne de commande :

        - **Commerce Scale Unit :**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **CRT local sur le PDV moderne :**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Installer les extensions de connecteur fiscal :

    Vous pouvez installer les extensions de connecteur fiscal sur la [station matérielle](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) ou le [registre PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Installez les extensions de station matérielle :

        1. Dans le dossier **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **HardwareStation.EFR.Installer**.
        1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande en exécutant la commande suivante.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Installer les extensions PDV :

        1. Ouvrez l’exemple de solution de connecteur fiscal PDV à l’adresse **Dynamics365Commerce.Solutions\\FiscalIntegration\\ PosFiscalConnectorSample\\ Contoso.PosFiscalConnectorSample.sln**, et générez-le.
        1. Dans le dossier **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande en exécutant la commande suivante.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **EFR build-pipeline.yml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration du service d’enregistrement fiscal pour l’Allemagne est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du SDK de Commerce. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de CRT, et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du SDK de Commerce, consultez [Téléchargez des exemples et des packages de référence du SDK de Commerce à partir de GitHub et NuGet](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurez un pipeline de build pour le SDK de packaging indépendant](../dev-itpro/build-pipeline.md).

> [!NOTE]
> L’échantillon d’intégration du service d’enregistrement fiscal pour l’Allemagne est disponible dans le SDK de Commerce à partir de la version 10.0.29 de Commerce. Dans la version de 10.0.28 ou antérieure de Commerce, vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Allemagne (héritées)](emea-deu-fi-sample-sdk.md).

### <a name="crt-extension-design"></a>Conception des extensions CRT

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Il y a un gestionnaire de demandes pour le fournisseur de documents, **DocumentProviderEFRFiscalDEU**. Il est utilisé pour générer des documents fiscaux pour le service d’enregistrement fiscal. Il est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans le service d’enregistrement fiscal.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Cette demande renvoie la réponse avec les données étendues.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du fournisseur de document fiscal se trouve dans **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleGermany.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du fournisseur de documents fiscaux depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec le service d’enregistrement fiscal.

L’extension de la station matérielle est **HardwareStation.Extension.EFRSample**. Elle utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère au service d’enregistrement fiscal. Elle gère également les réponses reçues du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **EFRHandler** est le point d’entrée pour le traitement des demandes au service d’enregistrement fiscal. Ce gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents au service d’enregistrement fiscal et renvoie une réponse de celui-ci.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé du service d’enregistrement fiscal.
- **InitializeFiscalDeviceRequest** – Cette demande est utilisée pour initialiser le service d’enregistrement fiscal.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du connecteur fiscal se trouve dans **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
