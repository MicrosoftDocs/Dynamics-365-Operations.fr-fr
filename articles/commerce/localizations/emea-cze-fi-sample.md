---
title: Exemple d’intégration du service d’enregistrement fiscal pour la République tchèque
description: Cet article fournit une présentation d’un exemple d’intégration fiscale pour la République tchèque dans Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: dc7ef27954de2bb10bbaf91fc5a3aa14d6ee6ffd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280331"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Exemple d’intégration du service d’enregistrement fiscal pour la République tchèque

[!include[banner](../includes/banner.md)]

Cet article fournit une présentation d’un exemple d’intégration fiscale pour la République tchèque dans Microsoft Dynamics 365 Commerce.

Pour répondre aux exigences fiscales locales pour les caisses enregistreuses en République tchèque, la fonctionnalité Dynamics 365 Commerce pour la République tchèque comprend un exemple d’intégration du point de vente (PDV) avec un service d’enregistrement fiscal externe. L’exemple étend la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md). Elle est basée sur la solution [EFR (Registre fiscal électronique)](https://efsta.org/sicherheitsloesungen/) de [l’EFSTA](https://efsta.org/) et permet la communication avec le service EFR via le protocole HTTPS. Le service EFR assure l’enregistrement électronique des ventes (EET – Elektronická evidence tržeb), c’est-à-dire la transmission en ligne des données de vente à un service web fiscal des autorités fiscales.

Le service EFR doit être hébergé sur la station matérielle Commerce ou sur une machine distincte pouvant être connectée à partir de la station matérielle. L’exemple est fourni sous forme de code source et fait partie du kit de développement logiciel (SDK) Retail.

Microsoft ne publie aucun matériel, logiciel ou documentation de l’EFSTA. Pour savoir comment obtenir la solution EFR et l’exploiter, contactez [l’EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Scénarios

Les scénarios suivants sont couverts par l’exemple d’intégration du service d’enregistrement fiscal pour la République tchèque.

- Enregistrement des opérations en espèces dans le service d’enregistrement fiscal.

    - Envoyez les données détaillées de la transaction au service d’enregistrement fiscal. Ces données incluent des informations sur la ligne de vente et des informations sur les remises, les paiements et les taxes. Le service d’enregistrement fiscal envoie en outre les données au service Web des autorités fiscales et reçoit une confirmation de sa part qui comprend le code d’identification fiscale de la transaction.
    - Capturez une réponse du service d’enregistrement fiscal. Cette réponse comprend des données fiscales telles que le code d’identification fiscale et le code de sécurité de la transaction, etc.
    - Imprimez les données fiscales d’une transaction enregistrée sur le reçu.

- Enregistrement des opérations de cartes-cadeaux et des dépôts des clients dans le service d’enregistrement fiscal.

    - Émettre ou ajouter de l’argent à une carte cadeau.
    - Enregistrer un dépôt sur compte client.
    - Créez une commande client et enregistrez un acompte pour la commande.
    - Modifiez une commande client et remplacez l’acompte pour la commande.
    - Annulez une commande client et remboursez l’acompte pour la commande.

- Gestion des erreurs, telles que les options suivantes.

    - Réessayez l’enregistrement fiscal si une nouvelle tentative est possible, par exemple si le service d’enregistrement fiscal n’est pas disponible, n’est pas prêt ou ne répond pas.
    - Reporter l’enregistrement fiscal.
    - Ignorez l’enregistrement fiscal ou marquez la transaction comme enregistrée et incluez des codes d’information pour capturer la raison de l’échec et des informations supplémentaires.
    - Vérifiez la disponibilité du service d’enregistrement fiscal avant l’ouverture d’une nouvelle opération de vente ou la finalisation d’une opération de vente.

### <a name="gift-cards"></a>Cartes cadeaux

L’exemple d’intégration du service d’enregistrement fiscal implémente les règles suivantes liées aux cartes-cadeaux.

- Les lignes de vente liées aux opérations *Émettre une carte-cadeau* ou *Ajouter à la carte-cadeau* dans une transaction de vente sont marquées d’un attribut spécial quand la transaction est enregistrée dans le service d’enregistrement fiscal.
- Un paiement par carte cadeau est considéré comme un paiement régulier et marqué d’un attribut spécial au moment de l’enregistrement de la transaction dans le service d’enregistrement fiscal.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Dépôts sur comptes client et acomptes commandes client

L’exemple d’intégration du service d’enregistrement fiscal implémente les règles suivantes liées aux dépôts comptes clients et aux compte de commandes client.

- Une transaction liée à un dépôt compte client ou à un dépôt de commande client est enregistrée dans le service d’enregistrement fiscal en tant que transaction sur une seule ligne et est marquée par un attribut spécial. Le groupe TVA d’acompte est précisé dans cette ligne.
- Quand une commande client hybride est créée, c’est-à-dire une commande client qui contient des produits pouvant être effectués hors du magasin par le client, ainsi que des produits qui seront récupérés ou expédiés ultérieurement, la transaction enregistrée dans le service d’enregistrement fiscal contient des lignes pour les produits qui sont exécutés, ainsi qu’une ligne pour le dépôt de commande.
- Un paiement par compte client est considéré comme un paiement régulier et marqué d’un attribut spécial au moment de l’enregistrement de la transaction dans le service d’enregistrement fiscal.
- Le montant de l’acompte de commande client qui est appliqué à une opération Retrait de commande client est considérée comme un paiement régulier et marquée d’un attribut spécial quand la transaction est enregistrée dans le service d’enregistrement fiscal.

### <a name="offline-registration"></a>Inscription hors ligne

Si le service d’enregistrement fiscal ne parvient pas à transmettre les données de transaction au service Web fiscal des autorités fiscales (par exemple, en raison du délai de réponse) et à recevoir une confirmation du service Web (c’est-à-dire le code d’identification fiscale de la transaction), il génère une signature locale pour la transaction et l’inclut ainsi qu’un code d’erreur spécial dans la réponse. Le service d’enregistrement fiscal renvoie les transactions dans l’ordre d’origine en arrière-plan dès que la connexion réseau est rétablie.

### <a name="limitations-of-the-sample"></a>Limites de l’échantillon

Le service d’enregistrement fiscal prend en charge uniquement les scénarios où la taxe de vente est incluse dans le prix. Par conséquent, l’option **Le prix comprend la taxe de vente** doit être définie sur **Oui** pour les magasins et les clients.

## <a name="set-up-commerce-for-the-czech-republic"></a>Configurer Commerce pour la République tchèque

Cette section décrit les paramètres Commerce spécifiques et recommandés pour la République tchèque. Pour plus d’informations, voir [Page d’accueil de Commerce](../index.md).

Pour utiliser la fonctionnalité spécifique au tchèque, vous devez spécifier les paramètres suivants.

- Dans l’adresse principale de l’entité juridique, définissez le champ **Pays/région** sur **CZE** (République tchèque).
- Dans le profil de fonctionnalité du PDV de chaque magasin situé en République tchèque, définissez le champ **Code ISO** sur **CZ** (République tchèque).

Vous devez également spécifier les paramètres suivants pour la République tchèque. Notez que vous devez exécuter des tâches de distribution appropriées après que vous avez terminé le paramétrage.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Paramétrer la TVA selon les exigences de la République tchèque


Vous devez créer des codes de taxe, des groupes de taxe et des groupes de taxe d’article. Vous devez également paramétrer les informations de taxe pour les produits et services. Pour plus d’informations sur le paramétrage et l’utilisation des fonctionnalités sur les taxes, voir [Vue d’ensemble des taxes](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Paramétrage des magasins

Sur la page **Tous les magasins**, mettez à jour les détails du magasin. Spécifiquement, définissez les paramètres suivants.

- Dans le champ **Groupe de taxe de vente**, spécifiez le groupe de taxe de vente à utiliser pour les ventes au client par défaut.
- Définissez l’option **Les prix incluent la taxe** sur **Oui**.
- Définissez le champ **Nom** au nom de l’entreprise. Ce changement permet de garantir que le nom de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le nom de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.
- Définissez le champ **Numéro d’identification de taxe (TIN)** sur numéro d’identification de l’entreprise. Ce changement permet de garantir que le numéro d’identification de l’entreprise apparaît sur un reçu de vente. Vous pouvez également ajouter le numéro d’identification de l’entreprise à la présentation du ticket de caisse sous forme de texte libre.

### <a name="set-up-functionality-profiles"></a>Paramétrage des profils de fonctionnalité

Paramétrage des profils de fonctionnalité de PDV.

- Sur l raccourci **Numérotation des reçus**, configurez la numérotation des reçus en créant ou en mettant à jour des enregistrements pour les types de transactions de réception **Vente**, **Commande client** et **Retour**.

### <a name="set-up-registration-numbers"></a>Paramétrer les numéros d’enregistrement

1. Accédez à **Administration d’organisation \> Carnet d’adresse global \> Types d’enregistrement \> Types d’enregistrement**. Créer un type d’inscription. Spécifie le champ **Pays/région** sur **CZE** (République tchèque) et la restreindre à l’Organisation.
2. Accédez à **Administration d’organisation \> Carnet d’adresse global \> Types d’enregistrement \> Catégories d’enregistrement**. Créer une catégorie d’inscription. Sélectionnez le type d’enregistrement de l’étape précédente et définissez **Catégorie d’inscription** sur **ID du local commercial**.
3. Accédez à **Administration d’organisation \> Organisations \> Unités opérationnelles**. Pour chaque magasin situé en République tchèque, sélectionnez l’unité liée au magasin. Sur le raccourci **Adresse**, développez la liste déroulante **Plus d’options**, puis sélectionnez **Avancé**. 
4. Sur la page **Gérer les adresses** ouverte, vous devez spécifier le paramètre suivant.

    - Sur le raccourci **Adresse** définissez le champ **Pays/région** sur **CZE**.
    - Sur le raccourci **ID inscription** créez un enregistrement. Sélectionnez le type d’inscription créé précédemment et définissez le numéro d’inscription.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurez des champs personnalisés afin qu’ils puissent être utilisés dans les formats de ticket de caisse des tickets de caisse

Vous pouvez configurer les champs de texte en langue étrangère et personnalisés utilisés dans les formats de ticket de caisse du PDV. La société par défaut de l’utilisateur qui crée le paramétrage de ticket de caisse doit être la même entité juridique que celle dans laquelle le paramétrage du texte en langue étrangère est créé. Sinon, les mêmes textes en langue étrangère doivent être créés dans la société par défaut et l’entité juridique de l’utilisateur du magasin pour lequel le paramétrage est créé.

Dans la page **Texte en langue étrangère**, ajoutez les enregistrements suivants pour les étiquettes des champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID langue**, **ID texte** et **Texte** qui sont affichées dans la table sont uniquement des exemples. Vous pouvez les modifier pour répondre à vos besoins. Toutefois, les valeurs **ID texte** que vous utilisez doivent être uniques, elles doivent être égales ou supérieures à 900 001.

Ajoutez les étiquettes de point de vente suivantes à la section **PDV** du **Texte en langue étrangère** de la table :

| ID langue | ID texte | Texte                   |
|-------------|---------|------------------------|
| fr-FR       | 900001  | ID provozovny/pokladny |
| fr-FR       | 900002  | BKP                    |
| fr-FR       | 900003  | PKP                    |
| fr-FR       | 900004  | FIK                    |
| fr-FR       | 900005  | Infos                   |
| fr-FR       | 900006  | Souche de N°        |

Dans la page **Champs personnalisés**, ajoutez les enregistrements suivants pour les champs personnalisés des mises en page de ticket de caisse. Notez que les valeurs **ID texte de la légende** doivent correspondre aux valeurs **ID texte** que vous avez spécifiées dans la page **Texte en langue étrangère** :

| Name                 | Type    | ID texte de la légende |
|----------------------|---------|-----------------|
| TLT                  | Récépissé | 900001          |
| SEC                  | Récépissé | 900002          |
| SIGN                 | Récépissé | 900003          |
| FISCAL               | Récépissé | 900004          |
| INFO                 | Récépissé | 900005          |
| CONTINUOUSNUMBER     | Récépissé | 900006          |

> [!NOTE]
> Il est important que vous spécifiiez des noms de champs personnalisés corrects, comme indiqué dans le tableau précédent. Un nom de champ personnalisé incorrect entraînera des données manquantes dans les reçus.

### <a name="configure-receipt-formats"></a>Configurer les formats de tickets de caisse

Pour chaque format de ticket de caisse nécessaire, modifiez la valeur du champ **Comportement d’impression** sur **Toujours imprimer**.

Dans le Concepteur de format de ticket de caisse, ajoutez des champs personnalisés suivants dans les sections du ticket de caisse approprié. Notez que les noms de champs correspondent aux textes en langue étrangère que vous avez définis dans la section précédente.

- **En-tête :** Ajoutez les champs suivants.

    - Les champs **Nom du magasin** et **Numéro d’identification fiscale** : ils sont utilisés pour imprimer le nom de l’entreprise et le numéro d’identification sur les reçus. Vous pouvez également ajouter le nom de l’entreprise et le numéro d’identification à la disposition du ticket de caisse sous forme de texte libre.
    - **Adresse du magasin**, **Date**, **Heure 24H**, **Numéro de reçu**, et **Numéro d’enregistrement**.
    - **Numéro e séquence** : ce champ identifie le numéro de la transaction en espèces dans le service d’enregistrement fiscal.

- **Lignes :** Ajoutez les champs suivants.

    - **Nom article**
    - **Qté**
    - **Prix total avec taxe**

- **Pied de page :** Ajoutez les champs suivants.

    - Champs de paiement, afin que les montants de paiement pour chaque mode de paiement soient imprimés. Par exemple, ajoutez les champs **Nom de l’offre** et **Montant de l’offre** à une ligne de la disposition.
    - **ID provozovny/pokladny** : ce champ imprime les identificateurs du local commercial et de la caisse enregistreuse.
    - **BKP** : ce champ imprime le code de sécurité du contribuable qui lui est attribué par le service d’enregistrement fiscal.
    - **FIK** : ce champ imprime le code d’identification fiscale de la transaction qui est attribué par le service web de l’administration fiscale en cas d’inscription en ligne réussie.
    - **PKP** : ce champ imprime le code de signature du contribuable qui est généré par le service d’enregistrement fiscal en cas d’enregistrement hors ligne.
    - **Info** : ce champ imprime les informations complémentaires du service d’enregistrement fiscal.

Pour plus d’informations sur l’utilisation des formats de tickets de caisse, voir [Configurer et concevoir les formats de tickets de caisse](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Paramétrer l’intégration fiscale pour la République tchèque

L’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour la République tchèque (héritées)](emea-cze-fi-sample-sdk.md).
>
> La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

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
    1. Téléchargez le fichier de configuration du fournisseur de document sur **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml** (par exemple, le [dossier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **Configurations \> Connecteurs \> ConnectorEFRSample.xml**, (par exemple, [le fichier pour version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Les fichiers de configuration de cet exemple d’intégration fiscale se trouvent dans les dossiers suivants du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS :
    >
    > - **Fichier de configuration du fournisseur de document :** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **Fichier de configuration du connecteur fiscal :** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

1. Accédez à **Commerce et vente au détail \> Configuration du Siège \> Paramètres \> Paramètres commerciaux partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez le fichier de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez un profil fonctionnel de connecteur. Sélectionnez le fournisseur de documents et le connecteur que vous avez chargés précédemment. Mettez à jour les [paramètres de mappage des données](#default-data-mapping) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur fiscal chargé précédemment. Mettez à jour les [paramètres du connecteur](#fiscal-connector-settings) si nécessaire.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**. Créez un groupe de connecteurs fiscaux pour le profil fonctionnel de connecteur que vous avez créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal et une étape du processus d’enregistrement fiscal et sélectionnez le groupe de connecteurs fiscaux créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils du matériel**. Sélectionnez un profil de matériel lié à la station matérielle à laquelle l’imprimante fiscale sera connectée. Sur le raccourci **périphériques fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment.
1. Ouvrez le programme de distribution (**Commerce et vente au détail \> Informatique Retail et Commerce \> Programme de distribution**) et sélectionnez les projets **1070** et **1090** pour transférer les données vers la base de données du canal.

#### <a name="default-data-mapping"></a>Mappage des données par défaut

Le mappage de données par défaut suivant est inclus dans la configuration du fournisseur de documents fiscaux fournie dans le cadre de l’exemple d’intégration fiscale :

- **Mappage des taux de taxe sur la valeur ajoutée (TVA)** – Le mappage des valeurs de pourcentage de taxe configurées pour les codes de taxe de vente avec les valeurs de l’attribut **TaxG** (groupe de taxes) dans les demandes envoyées au service fiscal. Voici le mappage par défaut :

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    Le premier composant de chaque paire représente un groupe de taxe TVA pris en charge par le service d’enregistrement fiscal EFR. Le deuxième composant représente le taux de TVA correspondant. Pour plus d’informations sur les groupes de TVA pris en charge par EFR pour la République tchèque, consultez la [Référence EFR](https://public.efsta.net/efr/).

- **Mappage du groupe TVA par défaut** – Tous les montants de TVA qui ne peuvent pas être mappés à l’un des groupes de TVA prédéterminés seront attribués au groupe de TVA par défaut (de base). Voici le mappage par défaut :

    ```
    A
    ```

- **Mappage de l’acompte du groupe TVA** – Les montants des acomptes clients et les acomptes des commandes clients seront imputés au groupe TVA des acomptes. Voici le mappage par défaut :

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Paramètres du connecteur fiscal

Les paramètres suivants sont inclus dans la configuration du connecteur fiscal fournie dans le cadre de l’exemple d’intégration fiscale :

- **Adresse du point de terminaison** – L’URL du service d’enregistrement fiscal.
- **Délai d’expiration** – La durée, en millisecondes, pendant laquelle le connecteur fiscal attendra une réponse du service d’enregistrement fiscal.

### <a name="configure-channel-components"></a>Configurer des composants de canal

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour la République tchèque (héritées)](emea-cze-fi-sample-sdk.md).
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

L’échantillon d’intégration du service d’enregistrement fiscal pour la République tchèque est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) Retail. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\Efr** dossier du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (par exemple, [l’échantillon dans la version/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). L’exemple [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux, qui est une extension de Commerce Runtime (CRT), et un connecteur fiscal, qui est une extension de Commerce Hardware Station. Pour plus d’informations sur l’utilisation du Kit de développement logiciel (SDK) Retail, consultez [Architecture du Kit de développement logiciel (SDK) Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) et [Configurer un pipeline de build pour le Kit de développement logiciel (SDK) de package indépendant](../dev-itpro/build-pipeline.md).

> [!WARNING]
> En raison des limites du [nouveau modèle de package et d’extension indépendant](../dev-itpro/build-pipeline.md), il ne peut actuellement pas être utilisé pour cet échantillon d’intégration fiscale. Vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une VM de développeur dans LCS. Pour plus d’informations, voir [Directives de déploiement pour l’échantillon d’intégration fiscale pour la République tchèque (héritées)](emea-cze-fi-sample-sdk.md). La prise en charge du nouveau modèle d’emballage et d’extension indépendant pour les exemples d’intégration fiscale est prévue pour les versions ultérieures.

### <a name="commerce-runtime-extension-design"></a>Conception d’extension Commerce Runtime

Le but de l’extension qui est un fournisseur de documents fiscaux est de générer des documents spécifiques au service et de gérer les réponses du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Il y a un seul gestionnaire de demandes **DocumentProviderEFRFiscalCZE** pour le fournisseur de documents, qui est utilisé pour générer des documents fiscaux pour le service d’enregistrement fiscal.

Ce gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du fournisseur de documents du connecteur spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes.

- **GetFiscalDocumentDocumentProviderRequest** – Cette demande contient des informations sur le document qui doit être généré. Il renvoie un document propre au service qui doit être enregistré dans le service d’enregistrement fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Cette requête renvoie la liste des événements auxquels s’abonner. Actuellement, les événements suivants sont pris en charge : les ventes, les acomptes sur compte client et les dépôts sur commande client.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Cette requête renvoie la réponse du service d’enregistrement fiscal. Cette réponse est sérialisée pour former une chaîne afin qu’elle soit prête à être enregistrée.

#### <a name="configuration"></a>Configuration

Le fichier de configuration du fournisseur de document fiscal se trouve dans **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** dans le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Ce fichier a pour but de permettre le paramétrage du fournisseur de documents fiscaux depuis le siège de Commerce. Le format de fichier est aligné sur les exigences de configuration de l’intégration fiscale.

### <a name="hardware-station-extension-design"></a>Conception de l’extension de station matérielle

L’extension qui est un connecteur fiscal a pour but de communiquer avec le service d’enregistrement fiscal. L’extension de la station matérielle utilise le protocole HTTP pour soumettre les documents que l’extension CRT génère au service d’enregistrement fiscal. Elle gère également les réponses reçues du service d’enregistrement fiscal.

#### <a name="request-handler"></a>Gestionnaire de demandes

Le gestionnaire de demandes **EFRHandler** est le point d’entrée pour le traitement des demandes au service d’enregistrement fiscal.

Le gestionnaire est hérité de l’interface **INamedRequestHandler**. La méthode **HandlerName** est chargée de renvoyer le nom du gestionnaire. Le nom du gestionnaire doit correspondre au nom du connecteur fiscal spécifié dans le siège de Commerce.

Le connecteur prend en charge les demandes suivantes.

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
