---
title: Exemple d’intégration du service d’enregistrement fiscal pour l’Autriche
description: Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour l’Autriche dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: f03eab49f0abfc8a279ea43f69fa2ac0100bd34a
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7945037"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Exemple d’intégration du service d’enregistrement fiscal pour l’Autriche

[!include[banner](../includes/banner.md)]

Cette rubrique fournit une présentation d’un exemple d’intégration fiscale pour l’Autriche dans Microsoft Dynamics 365 Commerce.

Pour répondre aux exigences fiscales locales pour les caisses enregistreuses en Autriche, la fonctionnalité Dynamics 365 Retail pour l’Autriche comprend un exemple d’intégration du point de vente (PDV) avec un service d’enregistrement fiscal externe. L’exemple étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). Elle est basée sur la solution [EFR (Registre fiscal électronique)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) de [l’EFSTA](https://www.efsta.eu/at/) et permet la communication avec le service EFR via le protocole HTTPS. Le service EFR doit être hébergé sur Retail Hardware Station ou sur une machine distincte pouvant être connectée à partir de la station matérielle. L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) Retail.

Microsoft ne publie aucun matériel, logiciel ou documentation de l’EFSTA. Pour savoir comment obtenir la solution EFR et l’exploiter, contactez [l’EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Scénarios

Les scénarios suivants sont couverts par l’exemple d’intégration du service d’enregistrement fiscal pour l’Autriche :

- Enregistrement des opérations en espèces dans le service d’enregistrement fiscal :

    - Envoyez les données détaillées de la transaction au service d’enregistrement fiscal. Ces données incluent des informations sur la ligne de vente et des informations sur les remises, les paiements et les taxes.
    - Capturez une réponse du service d’enregistrement fiscal. Cette réponse comprend une signature numérique et un lien vers la transaction enregistrée.
    - Enregistrez les taxes et associez-les aux codes fiscaux du service d’enregistrement fiscal.
    - Imprimez le code QR d’une transaction enregistrée sur le reçu.

- Enregistrement des opérations de cartes-cadeaux et des dépôts des clients en tant qu’opérations sans espèces dans le service d’enregistrement fiscal :

    - Émettre ou ajouter de l’argent à une carte cadeau.
    - Enregistrer un dépôt sur compte client.
    - Enregistrer un dépôt sur commande client.

- Enregistrement des transactions hors ventes et des événements en tant qu’opérations sans espèces dans le service d’enregistrement fiscal :

    - Ouvrir l’équipe et fermer l’équipe
    - Montant de départ, entrée flottante et retrait de l’offre
    - Remplacement de prix
    - Remplacement de taxe
    - Impression de l’accusé de réception
    - Ouvrir tiroir-caisse
    - Imprimer un X de caisse
    - Imprimer un Z de caisse

- Impression des relevés de fin de journée (rapports X/Z) comportant des champs spécifiques à l’Autriche :

    - Nombre total de produits ou de services qui ont été livrés aux clients
    - Répartition des ventes par taux d’imposition
    - Répartition des paiements par caissier/opérateur de caisse
    - Remises de prix et retours qui réduisent les ventes quotidiennes
    - Zéro vente (cadeaux)

- Gestion des erreurs, telles que les options suivantes :

    - Réessayez l’enregistrement fiscal si une nouvelle tentative est possible, par exemple si le service d’enregistrement fiscal n’est pas disponible, n’est pas prêt ou ne répond pas.
    - Reporter l’enregistrement fiscal.
    - Ignorez l’enregistrement fiscal ou marquez la transaction comme enregistrée et incluez des codes d’information pour capturer la raison de l’échec et des informations supplémentaires.
    - Vérifiez la disponibilité du service d’enregistrement fiscal avant l’ouverture d’une nouvelle opération de vente ou la finalisation d’une opération de vente.

### <a name="gift-cards"></a>Cartes cadeaux

L’exemple d’intégration du service d’enregistrement fiscal implémente les règles suivantes liées aux cartes-cadeaux :

- Exclure les lignes de vente liées aux opérations *Émettre une carte-cadeau* et *Ajouter à la carte-cadeau* à partir d’une opération en espèces. Au lieu d’enregistrer ces lignes dans le cadre d’une transaction en espèces, enregistrez-les en tant que transaction distincte sans espèces dans le service d’enregistrement fiscal.
- N’imprimez pas de ventilation par groupe fiscal et de code QR sur un reçu si celui-ci se compose uniquement de lignes de carte-cadeau.
- Imprimez le montant total des cartes-cadeaux émises ou rechargées lors d’une transaction séparément du montant de la transaction en espèces sur le reçu.
- Enregistrez les ajustements calculés des lignes de paiement dans la base de données du canal avec une référence à une transaction fiscale correspondante.
- Le paiement par carte-cadeau est considéré comme un paiement régulier.

### <a name="customer-deposits-and-customer-order-deposits"></a>Acomptes client et acomptes commandes client

L’exemple d’intégration du service d’enregistrement fiscal implémente les règles suivantes liées aux dépôts des clients et aux dépôts de commandes client :

- Enregistrez une transaction autre qu’en espèces si une transaction est un dépôt client.
- Enregistrez une transaction autre qu’en espèces si une transaction ne contient qu’un dépôt de commande client ou un remboursement de dépôt de commande client.
- Déduisez le montant du dépôt de commande client des lignes de paiement lorsqu’une commande client hybride est créée.
- Enregistrez les ajustements calculés des lignes de paiement dans la base de données du canal avec une référence à une transaction fiscale pour une commande client hybride.

### <a name="limitations-of-the-sample"></a>Limites de l’échantillon

Le service d’enregistrement fiscal prend en charge uniquement les scénarios où la taxe de vente est incluse dans le prix. Par conséquent, l’option **Le prix comprend la taxe de vente** doit être définie sur **Oui** pour les magasins et les clients.

## <a name="set-up-commerce-for-austria"></a>Configurer Commerce pour l’Autriche

Cette section décrit les paramètres Commerce spécifiques et recommandés pour l’Autriche. Pour plus d’informations sur les informations de configuration, voir [Page d’accueil Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique à l’Autriche, vous devez spécifier les paramètres suivants :

- Dans l’adresse principale de l’entité juridique, définissez le champ **Pays/région** sur **AUT** (Autriche).
- Dans le profil de fonctionnalité du PDV de chaque magasin situé en Autriche, définissez le champ **Code ISO** sur **AT** (Autriche).

Vous devez également spécifier les paramètres suivants pour l’Autriche. Notez que vous devez exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

### <a name="set-up-vat-per-austrian-requirements"></a>Paramétrer la TVA selon les exigences de l’Autriche

Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation des fonctionnalités sur les taxes, voir [Vue d’ensemble des taxes](../../finance/general-ledger/indirect-taxes-overview.md).

Sur les reçus de vente, vous pouvez imprimer un code abrégé pour un code de taxe de vente (par exemple, "A" ou "B"). Pour rendre cette fonctionnalité disponible, définissez le champ **Imprimer le code** sur la page **Codes de taxe de vente**.

### <a name="set-up-stores"></a>Paramétrage des magasins

Sur la page **Tous les magasins**, mettez à jour les détails du magasin. Spécifiquement, définissez les paramètres suivants :

- Dans le champ **Groupe de taxe de vente**, spécifiez le groupe de taxe de vente à utiliser pour les ventes au client par défaut.
- Définissez l’option **Les prix incluent la taxe** sur **Oui**.
- Définissez le champ **Nom** au nom de l’entreprise. Ce changement permet de garantir que le nom de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le nom de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.
- Définissez le champ **Numéro d’identification de taxe (TIN)** sur numéro d’identification de l’entreprise. Ce changement permet de garantir que le numéro d’identification de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le numéro d’identification de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.

### <a name="set-up-functionality-profiles"></a>Paramétrage des profils de fonctionnalité

Paramétrage des profils de fonctionnalité de PDV :

- Sur l raccourci **Numérotation des reçus**, configurez la numérotation des reçus en créant ou en mettant à jour des enregistrements pour les types de transactions de réception **Vente**, **Commande client** et **Retour**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse du PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900 001.

Ajoutez les étiquettes de point de vente suivantes à la section **PDV** du **Texte en langue étrangère** de la table :

| ID langue | ID texte | Texte                      |
|-------------|---------|---------------------------|
| fr-FR       | 900001  | Code QR                   |
| fr-FR       | 900002  | Numéro continu         |
| fr-FR       | 900003  | Code d’impression de la taxe de vente au détail     |
| fr-FR       | 900004  | Total (ventes)             |
| fr-FR       | 900005  | Total de la taxe (ventes)         |
| fr-FR       | 900006  | Total TTC (ventes) |
| fr-FR       | 900007  | Montant de la taxe (ventes)        |
| fr-FR       | 900008  | Base de la taxe (ventes)         |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère** :

| Name                 | Type    | ID texte de la légende |
|----------------------|---------|-----------------|
| QRCODE               | Récépissé | 900001          |
| CONTINUOUSNUMBER     | Récépissé | 900002          |
| RETAILPRINTCODE      | Récépissé | 900003          |
| SALESTOTAL           | Récépissé | 900004          |
| SALESTOTALTAX        | Récépissé | 900005          |
| SALESTOTALINCLUDETAX | Récépissé | 900006          |
| SALESTAXAMOUNT       | Récépissé | 900007          |
| SALESTAXBASIS        | Récépissé | 900008          |

> [!NOTE]
> Il est important que vous spécifiiez des noms de champs personnalisés corrects, comme indiqué dans le tableau précédent. Un nom de champ personnalisé incorrect entraînera des données manquantes dans les reçus.

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse nécessaire, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

- **En-tête :** Ajoutez les champs suivants :

    - Les champs **Nom du magasin** et **Numéro d’identification fiscale**, qui sont utilisés pour imprimer le nom de l’entreprise et le numéro d’identification sur les reçus. Vous pouvez également ajouter le nom de l’entreprise et le numéro d’identification à la disposition du ticket de caisse sous forme de texte libre.
    - Les champs **Adresse du magasin**, **Date**, **Heure 24H**, **Numéro de reçu**, et **Numéro d’enregistrement**.
    - Les champs **Numéro continu**, pour identifier le numéro de la transaction en espèces dans le service d’enregistrement fiscal.

- **Lignes :** Ajoutez les champs suivants :

    - **Nom article**.
    - **Qté**.
    - **Prix total TTC**.
    - **Code d’impression de la taxe de vente au détail**, qui est utilisé pour imprimer le code abrégé qui correspond au code de taxe de vente qui s’applique à l’article.

- **Pied de page :** Ajoutez les champs suivants :

    - Champs de paiement, afin que les montants de paiement pour chaque mode de paiement soient imprimés. Par exemple, ajoutez les champs **Nom de l’offre** et **Montant de l’offre** à une ligne de la disposition.
    - Le groupe de champs **Total des ventes** :

        - Le champ **Total des ventes** qui permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant est hors taxe. Les acomptes et les opérations de carte cadeau sont exclues.
        - Le champ **Total TTC (ventes)** qui permet d’imprimer le montant total des ventes de disponibilités du ticket de caisse. Le montant inclue la taxe. Les acomptes et les opérations de carte cadeau sont exclues.
        - Le champ **Taxe totale (ventes)** qui permet d’imprimer le montant total des taxes des ventes de disponibilités. Les acomptes et les opérations de carte cadeau sont exclues.

    - Le groupe de champs **Ventilation fiscale**. Tous les champs de ce groupe de champs doivent être imprimés sur une ligne distincte.

        - Le champ **ID taxe** standard qui active une synthèse de taxe à imprimer pour chaque code taxe. Le champ doit être ajouté sur une nouvelle ligne.
        - Le champ **Pourcentage d’impôt**, qui est un champ standard utilisé pour imprimer le taux de taxe effectif pour le code de taxe de vente.
        - Le champ **Base de la taxe (ventes)** qui permet d’imprimer le montant total des disponibilités pour le code de taxe de vente. Les acomptes et les opérations de carte cadeau sont exclues.
        - Le champ **Montant de la taxe (ventes)** qui permet d’imprimer le montant de la taxe du reçu pour les ventes en espèces pour le code de taxe de vente.
        - Le champ **Code d’impression de la taxe de vente au détail**, qui est utilisé pour imprimer le code abrégé qui correspond au code de taxe de vente.

    - Le champ **Code QR**, qui est utilisé pour imprimer la référence à la transaction en espèces enregistrée sous forme de code QR.

        > [!NOTE]
        > La valeur **Code QR** est extraite de la réponse du registre fiscal. EFR renvoie un code QR dans sa réponse uniquement si la valeur du champ **Attributs** dans la configuration EFR est décrit dans la documentation EFSTA. Le format de code QR dans le champ **Attributs** dans la configuration EFR doit être défini sur **BMP**.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Paramétrer l’intégration fiscale pour l’Autriche

L’échantillon d’intégration du service d’enregistrement fiscal pour l’Autriche est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Autriche (héritées)](emea-aut-fi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

Suivez les étapes de configuration de l’intégration fiscale décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md) :

1. [Configurer un processus d’enregistrement fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Notez également les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à cet échantillon d’intégration du service d’enregistrement fiscal](#set-up-the-registration-process).
1. [Définir les paramètres de traitement des erreurs](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Activer l’exécution manuelle d’un enregistrement fiscal reporté](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurer le processus d’inscription

Pour activer le processus d’enregistrement, procédez comme suit pour configurer Commerce Headquarters. Pour plus d’informations sur l’intégration fiscale, voir [Configuration de l’intégration fiscale pour les canaux Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK)/application (par exemple, **[version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Ouvrez **src \> FiscalIntegration \> Efr**.
    1. Ouvrez **Configurations \> DocumentProviders**, et téléchargez les fichiers de configuration du fournisseur de documents fiscaux : **DocumentProviderFiscalEFRSampleAustria.xml** et **DocumentProviderNonFiscalEFRSampleAustria.xml** (par example, [l’emplacement des fichiers pour la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **Configurations \> Connecteurs \> ConnectorEFRSample.xml**, (par exemple, [le fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichiers de configuration du fournisseur de documents fiscaux :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez les fichiers de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez deux profils fonctionnels de connecteur, un pour chaque fournisseur de document fiscal que vous avez chargé précédemment, et sélectionnez le connecteur fiscal que vous avez chargé précédemment. Mettez à jour les [paramètres de mappage des données](#default-data-mapping) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur fiscal chargé précédemment. Mettez à jour les [paramètres du connecteur](#fiscal-connector-settings) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**. Créez deux groupes de connecteurs fiscaux, un pour chaque profil fonctionnel de connecteur que vous avez créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal et deux étapes du processus d’enregistrement fiscal et sélectionnez les groupes de connecteurs fiscaux créés précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment. Pour permettre l’inscription des événements non fiscaux sur le PDV, sur le raccourci **Fonctions**, sous **PDV**, définissez l’option **Audit** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils du matériel**. Sélectionnez un profil de matériel lié à la station matérielle à laquelle l’imprimante fiscale sera connectée. Sur le raccourci **périphériques fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment.
1. Ouvrez le programme de distribution (**Commerce et vente au détail \> Informatique Retail et Commerce \> Programme de distribution**) et sélectionnez les projets **1070** et **1090** pour transférer les données vers la base de données du canal.

#### <a name="default-data-mapping"></a>Mappage des données par défaut

Le mappage de données par défaut suivant est inclus dans la configuration du fournisseur de documents fiscaux fournie dans le cadre de l’exemple d’intégration fiscale :

- **Mappage des taux de taxe sur la valeur ajoutée (TVA)** – Le mappage des valeurs de pourcentage de taxe configurées pour les codes de taxe de vente avec les valeurs de l’attribut **TaxG** (groupe de taxes) dans les demandes envoyées au service fiscal. Voici le mappage par défaut :

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    Le premier composant de chaque paire représente un groupe de taxe TVA pris en charge par le service d’enregistrement fiscal EFR. Le deuxième composant représente le taux de TVA correspondant. Pour plus d’informations sur les groupes de TVA pris en charge par EFR pour l’Autriche, consultez la [Référence EFR](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Adresse du point de terminaison** – L’URL du service d’enregistrement fiscal.
- **Délai d’expiration de l’appareil** – La durée, en millisecondes, pendant laquelle le connecteur fiscal attendra une réponse du service d’enregistrement fiscal.
- **Afficher les notifications d’enregistrement fiscal** – Cet indicateur contrôle si les notifications que le service d’enregistrement fiscal renvoie doivent être présentées à l’opérateur.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Autriche (héritées)](emea-aut-fi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

#### <a name="set-up-the-development-environment"></a>Configurer l’environnement de développement

Pour configurer un environnement de développement pour tester et étendre l’exemple, procédez comme suit.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information : [Télécharger les exemples et les packages de référence du SDK Retail depuis GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution EFR sur **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln**, et générez-la.
1. Installer les extensions CRT :

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

1. Installez les extensions de station matérielle :

    1. Dans le dossier **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **HardwareStation.EFR.Installer**.
    1. Démarrez le programme d’installation de l’extension à partir de la ligne de commande.

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **EFR build-pipeline.yml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Conception des extensions

L’échantillon d’intégration du service d’enregistrement fiscal pour l’Autriche est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour l’Autriche (héritées)](emea-aut-fi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Il existe deux gestionnaires de demandes pour les fournisseurs de documents :

- **DocumentProviderEFRFiscalAUT** – Ce gestionnaire permet de générer des documents fiscaux pour le service d’enregistrement fiscal.
- **DocumentProviderEFRNonFiscalAUT** – Ce gestionnaire permet de générer des documents non fiscaux pour le service d’enregistrement fiscal.

Ces gestionnaires sont hérités de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes :

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans le service d’enregistrement fiscal.
- **GetNonFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document non fiscal qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans le service d’enregistrement fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : ventes, impression du rapport X, impression du rapport Z, dépôts sur compte client, dépôts de commande client, événements d’audit et transactions non commerciales.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Cette requête renvoie la réponse du service d’enregistrement fiscal. Cette réponse est sérialisée pour former une chaîne afin qu’elle soit prête à être enregistrée.

#### <a name="configuration"></a>Configuration

Les fichiers de configuration du fournisseur de documents fiscaux se trouvent dans le dossier **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) :

- **DocumentProviderFiscalEFRSampleAustria** – Le fichier de configuration du fournisseur de documents fiscaux pour les documents fiscaux.
- **DocumentProviderNonFiscalEFRSampleAustria** – Le fichier de configuration du fournisseur de documents fiscaux pour les documents non fiscaux.

Ces fichiers ont pour but de permettre le paramétrage du fournisseur de documents fiscaux depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec le service d’enregistrement fiscal. L’extension de la station matérielle utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère au service d’enregistrement fiscal. Elle gère également les réponses reçues du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **EFRHandler** est le point d’entrée pour le traitement des demandes au service d’enregistrement fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur fiscal prend en charge les demandes suivantes :

- **SubmitDocumentFiscalDeviceRequest** – Cette demande envoie des documents au service d’enregistrement fiscal et renvoie une réponse de celui-ci.
- **IsReadyFiscalDeviceRequest** – Cette demande est utilisée pour un contrôle de santé du service d’enregistrement fiscal.
- **InitializeFiscalDeviceRequest** – Cette demande est utilisée pour initialiser le service d’enregistrement fiscal.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du connecteur fiscal se trouve dans **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du connecteur fiscal depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
