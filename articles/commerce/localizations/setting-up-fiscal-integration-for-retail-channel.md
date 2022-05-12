---
title: Configurer l’intégration fiscale pour les canaux de commerce
description: Cette rubrique donne des instructions pour configurer la fonctionnalité d’intégration fiscale pour les canaux de commerce.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 51a75ce03b0ae6b744ec56df35bd3fdb1f40cf3a
ms.sourcegitcommit: 5f7177b9ab192b5a6554bfc2f285f7cf0b046264
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661747"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Configurer l’intégration fiscale pour les canaux de commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Cette rubrique donne des instructions pour configurer la fonctionnalité d’intégration fiscale pour les canaux de commerce. Pour plus d’informations sur l’intégration fiscale, voir [Vue d’ensemble de l’intégration fiscale pour les canaux de commerce](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>Activer les fonctionnalités dans Commerce Headquarters

Pour activer les fonctionnalités associées à la fonctionnalité d’intégration fiscale pour les canaux Commerce, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Recherchez et activez les fonctions suivantes :

    - **Intégration fiscale directe à partir des registres PDV** – Cette fonctionnalité étend le cadre d’intégration fiscale en ajoutant la possibilité de créer des connecteurs fiscaux qui seront exécutés en point de vente (PDV). Ce type de connecteur communique avec un appareil ou un service fiscal qui fournit une interface de programmation d’application (API) HTTP et ne nécessite pas de machine physique dédiée dans le magasin. Par exemple, cette fonctionnalité permet une intégration fiscale pour les appareils mobiles sans nécessiter de station matérielle partagée.
    - **Remplacements du profil technique d’intégration fiscale** – Cette fonctionnalité permet d’étendre la configuration de l’intégration fiscale et ajoute la possibilité de vérifier les paramètres de connexion sur la page des paramètres d’une Caisse enregistreuse de PDV. Quand cette fonctionnalité est activée, vous pouvez remplacer les paramètres d’un profil technique.
    - **État d’enregistrement fiscal des Caisse enregistreuse de PDV** – Quand cette fonctionnalité est activée, vous pouvez désactiver le processus d’enregistrement fiscal pour des Caisse enregistreuse de PDV spécifiques. Si l’enregistrement fiscal est désactivé pour une Caisse enregistreuse de PDV, les transactions de vente ne peuvent pas être effectuées sur cette Caisse enregistreuse.
    - **Sauvegarde du stockage local d’intégration fiscale** – Cette fonctionnalité étend les capacités de traitement des erreurs du cadre d’intégration fiscale. Elle permet également la sauvegarde automatique des données d’enregistrement fiscal en cas de perte de données, de sorte que les données du stockage local soient restaurées pendant l’activation d’un appareil.

## <a name="set-up-commerce-parameters"></a>Configurer les paramètres de commerce

Pour définir des paramètres Commerce, procédez comme suit.

1. Dans la page **Paramètres partagés de commerce**, dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Sous l’onglet **Souches de numéros**, définissez les souches de numéros pour les références suivantes :

    - Numéro du profil technique fiscal
    - Numéro du groupe de connecteurs fiscaux
    - Numéro du processus d’enregistrement

1. Dans la page **Paramètres de commerce**, définissez la souche de numéros pour le numéro de profil fonctionnel fiscal.

> [!NOTE]
> Les souches de numéros sont facultatives. Les numéros pour toutes les entités d’intégration fiscale peuvent être générés depuis les souches de numéros ou manuellement.

## <a name="set-up-a-fiscal-registration-process"></a>Configurer un processus d’enregistrement fiscal

Le processus de paramétrage de l’intégration fiscale inclut les tâches générales suivantes :

- configuration des connecteurs fiscaux qui représentent les périphériques ou les services fiscaux utilisés à des fins d’enregistrement fiscal, comme les imprimantes fiscales par exemple ;
- configuration des fournisseurs de documents fiscaux qui seront enregistrés dans les périphériques ou services fiscaux par les connecteurs fiscaux ;
- configuration du processus d’enregistrement fiscal qui définit une séquence des étapes d’enregistrement fiscal ainsi que les connecteurs fiscaux et les fournisseurs de documents fiscaux utilisés pour chaque étape ;
- affectation du processus d’enregistrement fiscal aux profils de fonctionnalité du PDV ;
- affectation des profils techniques de connecteur aux profils matériels.
- Affectez les profils techniques de connecteur aux profils matériels ou fonctionnalités PDV.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Télécharger les configurations des fournisseurs de documents fiscaux

Un fournisseur de documents fiscaux est responsable de la génération des documents fiscaux qui représentent les transactions et les événements enregistrés sur le PDV dans un format également compatible avec un périphérique ou un service fiscal. Par exemple, un fournisseur de documents fiscaux peut générer une représentation de reçu fiscal au format XML.

Pour télécharger les configurations des fournisseurs de documents fiscaux, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Fournisseurs de documents fiscaux** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux**).
1. Importez une configuration XML pour chaque périphérique ou service que vous prévoyez d’utiliser.

> [!TIP]
> En sélectionnant **Affichage**, vous pouvez afficher tous les profils fonctionnels et techniques liés au fournisseur de documents fiscaux actuel.

> [!NOTE]
> La mise en correspondance des données est considérée comme faisant partie du fournisseur de documents fiscaux. Pour paramétrer différentes mises en correspondance de données pour le même connecteur (par exemple, les réglementations spécifiques à chaque état), vous devez créer différents fournisseurs de documents fiscaux.

### <a name="upload-configurations-of-fiscal-connectors"></a>Importer les configurations des connecteurs fiscaux

Un connecteur fiscal est responsable de la communication avec un périphérique ou un service fiscal. Par exemple, un connecteur fiscal peut envoyer un reçu fiscal qu’un fournisseur de documents fiscaux a créé au format XML vers une imprimante fiscale. Pour en savoir plus sur les composants de l’intégration fiscale, voir [Processus d’enregistrement fiscal et exemples d’intégration fiscale pour les périphériques et les services fiscaux](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Pour télécharger les configurations des connecteurs, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Connecteurs fiscaux** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**).
1. Importez une configuration XML pour chaque périphérique ou service que vous prévoyez d’utiliser à des fins d’intégration fiscale.

> [!TIP]
> En sélectionnant **Affichage**, vous pouvez afficher tous les profils fonctionnels et techniques liés au connecteur fiscal actuel.

Pour des exemples de configuration des connecteurs fiscaux et fournisseurs de documents fiscaux, voir [Exemples fiscaux d’intégration dans le SDK de Commerce](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Créer des profils fonctionnels de connecteur

Pour créer des profils fonctionnels de connecteur, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Profils fonctionnels de connecteur** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels de connecteur**).
1. Pour chaque combinaison d’un connecteur fiscal et d’un fournisseur de documents fiscaux associé à ce connecteur fiscal, créez un profil fonctionnel de connecteur en procédant comme suit :

    1. Sélectionnez un nom de connecteur.
    1. Sélectionnez un fournisseur de document.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Modifier les paramètres de mise en correspondance des données dans un profil fonctionnel de connecteur

Vous pouvez changer les paramètres de mise en correspondance des données dans un profil fonctionnel de connecteur. Le tableau suivant fournit quelques exemples de paramètres de mappage de données dans un profil fonctionnel de connecteur.

| Paramètre | Format | Exemple |
|-----------|--------|---------|
| Paramètres de taux de TVA | valeur : VATrate | 1 : 2 000, 2 : 1 800 |
| Mise en correspondance des codes de TVA | VATcode : valeur | vat20 : 1, vat18 : 2 |
| Mise en correspondance des types de modes de paiement | TenderType : Valeur | Disponibilités : 1, Carte : 2 |

Pour rétablir les paramètres par défaut définis dans la configuration du fournisseur de documents fiscaux, sélectionnez **Mettre à jour** sur la page **Profils fonctionnels du connecteur**.

> [!NOTE]
> Les profils fonctionnels du connecteur sont spécifiques à la société. Si vous prévoyez d’utiliser la même combinaison d’un connecteur fiscal et d’un fournisseur de documents fiscaux dans différentes sociétés, vous devez créer un profil fonctionnel de connecteur pour chaque entreprise.

### <a name="create-connector-technical-profiles"></a>Créer des profils techniques de connecteur

Pour créer des profils techniques de connecteur, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Profils techniques de connecteur** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Profils techniques de connecteur**).
1. Créez un profil technique de connecteur pour chaque connecteur fiscal en suivant ces étapes :

    1. Sélectionnez un nom de connecteur.
    1. Sélectionnez un type de connecteur :

        - Pour les périphériques ou services connectés à une station matérielle ou présents sur le réseau local, sélectionnez **Local**.
        - Pour les services externes, sélectionnez **Externe**.
        - Pour les connecteurs internes dans Commerce Runtime (CRT), sélectionnez **Interne**. 

    1. Sélectionnez un emplacement de connecteur :

        - Si le connecteur est situé sur la station matérielle, sélectionnez **Station matérielle**.
        - Si le connecteur est situé sur le registre du PDV, sélectionnez **Caisse enregistreuse**.

Les paramètres des onglets **Périphérique** et **Paramètres** dans un profil technique du connecteur peuvent être modifiés. Pour rétablir les paramètres par défaut définis dans la configuration du connecteur fiscal, sélectionnez **Mettre à jour**. Même si une nouvelle version d’une configuration XML est téléchargée, vous recevez un message stipulant que le connecteur fiscal actuel ou le fournisseur de documents fiscaux est déjà utilisé. Cette procédure ne remplace pas les modifications manuelles qui ont déjà été apportées aux profils fonctionnels du connecteur et des profils techniques du connecteur. Pour appliquer l’ensemble des paramètres par défaut depuis une nouvelle configuration, sélectionnez **Mettre à jour** sur la page **Profils fonctionnels du connecteur** ou **Profils techniques du connecteur**.

Si vous devez configurer des paramètres spécifiques pour un registre ou un magasin de PDV individuel, suivez ces étapes.

1. Sélectionnez l’élément du menu **Remplacer**.
1. Sur la page **Remplacer**, créez un enregistrement.
1. Sélectionnez un magasin ou un registre de PDV. Vous pouvez remplacer les paramètres du profil technique sélectionné pour un registre de PDV individuel ou tous les registres de PDV d’un magasin individuel.
1. Sur l’onglet **Périphérique**, entrez les paramètres pour le registre ou le magasin de PDV sélectionné.

### <a name="create-fiscal-connector-groups"></a>Créer des groupes de connecteurs fiscaux

Un groupe de connecteurs fiscaux associe des profils fonctionnels des connecteurs fiscaux exécutant des fonctions identiques et utilisés à la même étape d’un processus d’enregistrement fiscal. Par exemple, si plusieurs modèles fiscaux d’impression peuvent être utilisés dans un magasin, les connecteurs fiscaux pour ces imprimantes fiscales peuvent être associés en un groupe de connecteurs fiscaux.

Pour créer un groupe de connecteurs fiscaux, procédez comme suit.

1. Accédez à la page **Groupe de connecteurs fiscaux** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**).
1. Créez un groupe de connecteurs fiscaux.
1. Ajoutez des profils fonctionnels dans le groupe de connecteurs. Sur l’onglet **Profils fonctionnels**, sélectionnez **Ajouter**, puis sélectionnez un numéro de profil. Chaque connecteur fiscal au sein d’un groupe de connecteurs ne peut avoir qu’un profil fonctionnel.
1. Pour interrompre l’utilisation du profil fonctionnel, définissez **Désactiver** sur **Oui**. Cette modification affecte uniquement le groupe de connecteurs actuel. Vous pouvez continuer à utiliser le même profil fonctionnel dans d’autres groupes de connecteurs.

### <a name="create-a-fiscal-registration-process"></a>Créer un processus d’enregistrement fiscal

Un processus d’enregistrement fiscal est défini par la séquence des étapes d’enregistrement et du groupe de connecteurs utilisé dans chaque étape.

Pour créer un processus d’enregistrement fiscal, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Processus d’enregistrement fiscal** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**).
1. Créez un enregistrement pour chaque processus d’enregistrement fiscal unique.
1. Ajoutez des étapes d’inscription au processus en suivant ces étapes :

    1. Sélectionnez **Ajouter**.
    1. Sélectionnez un type de connecteur fiscal.
    1. Dans le champ **Numéro du groupe**, sélectionnez un groupe de connecteurs fiscaux approprié.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Affecter les entités du processus d’enregistrement fiscal aux profils du PDV

Pour affecter les entités du processus d’enregistrement fiscal aux profils du PDV, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Profils de fonctionnalité du PDV** (**Commerce et vente au détail \> Paramétrage du canal \> Paramétrage Point de vente \> Profils Point de vente \> Profils de fonctionnalité**). 
1. affectation du processus d’enregistrement fiscal aux profils de fonctionnalité du PDV.
1. Sélectionnez **Modifier**, puis, dans l’onglet **Processus d’enregistrement fiscal**, dans le champ **Numéro du processus**, sélectionnez un processus.
1. Sur l’onglet **Services fiscaux**, sélectionnez les profils techniques du connecteur avec l’emplacement du connecteur **S’inscrire**.
1. Accédez à la page **Profil matériel du PDV** (**Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Profils PDV \> Profils matériel**).
1. Affectez des profils techniques de connecteur à un profil matériel. 
1. Sélectionnez **Modifier**, puis, sur l’onglet **Périphériques fiscaux**, ajoutez une ligne. 
1. Dans le champ **Numéro de profil**, sélectionnez un profil technique du connecteur.
1. Sur l’onglet **Périphériques fiscaux**, sélectionnez les profils techniques du connecteur avec l’emplacement du connecteur **Station matérielle**.

> [!NOTE]
> Vous pouvez ajouter plusieurs profils techniques à un profil matériel identique. Toutefois, un profil matériel ou un profil de fonctionnalité de PDV doit avoir une seule intersection avec n’importe quel groupe de connecteurs fiscaux.

Le flux d’enregistrement fiscal est défini par le processus d’enregistrement fiscal ainsi que par certains paramètres de composants d’intégration fiscale : l’extension CRT pour le fournisseur de documents fiscaux et l’extension de la station matérielle pour le connecteur fiscal.

- L’abonnement des événements et des transactions à l’enregistrement fiscal est prédéfini dans le fournisseur de documents fiscaux.
- Le fournisseur de documents fiscaux est également responsable de l’identification du connecteur fiscal utilisé pour l’enregistrement fiscal. Il correspond aux profils fonctionnels du connecteur inclus dans le groupe de connecteurs fiscaux spécifié pour l’étape actuelle du processus d’enregistrement fiscal avec le profil technique du connecteur attribué au profil matériel de la station matérielle à laquelle le PDV est relié.
- Le fournisseur de documents fiscaux utilise les paramètres de mise en correspondance des données depuis la configuration du fournisseur de documents fiscaux pour transformer les données d’événement/de transaction, tels que les impôts et les paiements, tandis qu’un document fiscal est généré.
- Quand le fournisseur de documents fiscaux génère un document fiscal, le connecteur fiscal peut soit l’envoyer au périphérique fiscal en l’état, soit l’analyser et le transformer en une séquence de commandes de l’API du périphérique, selon la manière dont la communication est gérée.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Configurer des registres avec des restrictions d’enregistrement fiscal

Vous pouvez sélectionner des registres où l’enregistrement fiscal est interdit, par exxemple si vous devez fournir uniquement des opérations non fiscales, telles que la recherche de catalogue de produits, la recherche de clients ou la création de brouillon de transaction sur ces appareils.

Pour configurer des registres avec des restrictions d’enregistrement fiscal, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**.
1. Sélectionnez le processus requis.
1. Sélectionnez l’onglet **Registres de point de vente avec restrictions de processus fiscaux**.
1. Ajouter des registres avec restrictions de processus fiscaux, le cas échéant.

### <a name="validate-the-fiscal-registration-process"></a>Valider le processus d’enregistrement fiscal

Il est recommandé de valider le processus d’enregistrement fiscal dans les cas suivants :

- Vous avez terminé tous les paramètres pour un nouveau processus d’inscription. Ces paramètres incluent l’attribution des processus d’enregistrement aux profils de fonctionnalité PDV et aux profils matériels.
- Vous avez apporté des modifications à un processus d’enregistrement fiscal existant, et ces modifications peuvent entraîner la sélection d’un connecteur fiscal différent au moment de l’exécution. (Par exemple, vous avez modifié le groupe de connecteurs pour une étape du processus d’enregistrement fiscal, activé un profil fonctionnel de connecteur dans un groupe de connecteurs ou ajouté un nouveau profil fonctionnel de connecteur à un groupe de connecteurs.)
- Vous avez apporté des modifications à l’affectation des profils techniques du connecteur aux profils matériels.

Pour valider le processus d’enregistrement fiscal, procédez comme suit.

1. Dans Commerce Headquarters, accédez à la page **Proceessus d’enregistrement fiscal** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**).
1. Sélectionnez **Valider** pour valider le processus d’enregistrement fiscal.
1. Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1090** pour transférer des données vers la base de données des canaux.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configurer les textes fiscaux pour les remises

Dans certains cas, un texte spécifique doit être imprimé sur un reçu fiscal si une remise est appliquée. Vous pouvez définir les textes fiscaux pour les remises dans la page **Groupe de connecteurs fiscaux** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**).

- Pour les remises manuelles appliquées au PDV, vous devez configurer un texte fiscal pour le code d’informations ou le groupe de codes d’informations spécifié comme code d’informations **Remise de produit** dans le profil de fonctionnalité du PDV.

    1. Sur la page **Groupe de connecteurs fiscaux**, sélectionnez **Texte du reçu fiscal**.
    1. Dans l’onglet **Codes info**, sélectionnez **Ajouter**, puis sélectionnez un code info ou un groupe de codes info.
    1. Dans le champ **Numéro de code info**, sélectionnez une valeur.
    1. Dans le champ **Numéro de sous-code**, sélectionnez une valeur si un sous-code est requis pour le code info sélectionné.
    1. Dans le champ **Texte du reçu fiscal**, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.
    1. Définissez l’option **Imprimer l’entrée utilisateur sur le reçu fiscal** sur **Oui** pour remplacer le texte d’un reçu fiscal avec les informations qu’un utilisateur renseigne manuellement dans le système du PDV. Cette option s’applique uniquement aux codes info dont la saisie est de type **Texte**.

    > [!NOTE]
    > Vous pouvez préciser un texte fiscal afin que plusieurs codes info soient compatibles avec les scénarios où les groupes de codes info, codes info associés et codes info déclenchés sont utilisés. Dans ces scénarios, le reçu fiscal contient les textes fiscaux depuis tous les codes info associés à la ligne de transaction quand la remise est appliquée.

- Pour les remises spécifiques au canal, vous devez définir un texte fiscal pour l’ID de remise.

    1. Sur la page **Groupe de connecteurs fiscaux**, sélectionnez **Texte du reçu fiscal**.
    1. Dans l’onglet **Remises**, sélectionnez **Ajouter**, puis sélectionnez un ID de remise.
    1. Dans le champ **Texte du reçu fiscal**, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.

    > [!NOTE]
    > Si plusieurs remises sont appliquées à la même ligne de transaction, le reçu fiscal contient les textes fiscaux de toutes les remises associées à cette ligne de transaction.

## <a name="set-error-handling-settings"></a>Définir les paramètres de traitement des erreurs

Les options de traitement des erreurs disponibles dans l’intégration fiscale sont définies dans le processus d’enregistrement fiscal. Pour plus d’informations sur le traitement des erreurs de l’intégration fiscale, voir [Gestion des erreurs](fiscal-integration-for-retail-channel.md#error-handling).

Pour définir les paramètres de gestion des erreurs, procédez comme suit.

1. Dans la page **Processus d’enregistrement fiscal** (**Commerce et vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d’intégration fiscale**), vous pouvez définir les paramètres suivants pour chaque étape du processus d’enregistrement fiscal :

    - **Autoriser Ignorer** – Ce paramètre active l’option **Ignorer** dans la boîte de dialogue de traitement des erreurs.
    - **Autoriser Marquer comme enregistrée** – Ce paramètre active l’option **Marquer comme enregistrée** dans la boîte de dialogue de traitement des erreurs.
    - **Autoriser Reporter** : ce paramètre active l’option **Reporter** dans la boîte de dialogue de traitement des erreurs.
    - **Continuer au moment d’erreurs** : si ce paramètre est activé, le processus d’enregistrement fiscal peut se poursuivre sur l’appareil de PDV si l’enregistrement fiscal d’une transaction ou d’un événement échoue. Dans le cas contraire, pour exécuter l’enregistrement fiscal de la transaction ou de l’événement suivant, l’opérateur doit renouveler la tentative d’enregistrement fiscal échoué, l’ignorer, ou marquer la transaction ou l’événement comme enregistré. Pour plus d’informations, voir [Enregistrement fiscal facultatif](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Si le paramètre **Continuer au moment d’erreurs** est activé, les paramètres **Autoriser Ignorer** et **Autoriser Marquer comme enregistré** sont automatiquement désactivés.

1. Les options **Ignorer** et **Marquer comme enregistré** dans la boîte de dialogue de traitement des erreurs nécessite l’autorisation **Autoriser Ignorer l’enregistrement ou Marquer comme enregistré**. Pour activer cette autorisation, accédez à la page **Groupes d’autorisations** (**Commerce et vente au détail \> Employés \> Groupes d’autorisations**) et définissez l’option **Autoriser Ignorer l’enregistrement ou Marquer comme enregistré** sur **Oui**.
1. L’option **Reporter** dans la boîte de dialogue de traitement des erreurs exige que l’autorisation **Autoriser Reporter** soit activée. Pour activer l’autorisation, accédez à la page **Groupes d’autorisations** (**Commerce et vente au détail \> Employés \> Groupes d’autorisations**) et définissez l’option **Autoriser Reporter** sur **Oui**.
1. Les options **Ignorer**, **Marquer comme enregistrée** et **Reporter** permettent aux opérateurs de renseigner des informations supplémentaires quand l’enregistrement fiscal échoue. Pour rendre cette fonctionnalité disponible, vous devez spécifier les codes info **Ignorer**, **Marquer comme enregistrée** et **Reporter** sur un groupe de connecteurs fiscaux. Les informations que les opérateurs saisissent sont ensuite enregistrées comme transaction de code info liée à la transaction fiscale. Pour plus d’informations sur les codes info, voir [Codes info et groupes de codes info](../info-codes-retail.md).

    > [!NOTE]
    > La fonction de déclenchement **Produit** n’est pas prise en charge pour les codes info utilisés pour **Ignorer** et **Marquer comme enregistrée** dans les groupes de connecteurs fiscaux.

    - Sur la page **Groupe de connecteurs fiscaux**, sous l’onglet **Codes info**, sélectionnez les codes info ou les groupes de codes info dans les champs **Ignorer**, **Marquer comme enregistrée** et **Reporter**.

    > [!NOTE]
    > Un document fiscal et un document non fiscal peuvent être générés à chaque étape d’un processus fiscal d’enregistrement. Une extension de fournisseur de documents fiscaux identifie chaque type de transaction ou d’événement comme associé à des documents fiscaux ou non fiscaux. La fonctionnalité de gestion des erreurs s’applique uniquement aux documents fiscaux.
    >
    > - **Document fiscal** – Désigne un document obligatoire qui doit être enregistré avec succès (par exemple, un reçu fiscal).
    > - **Document non fiscal** – Désigne un document supplémentaire pour la transaction ou l’événement (par exemple, un bordereau de carte cadeau).

1. Si l’opérateur doit pouvoir continuer le traitement de l’opération en cours (par exemple, la création ou la finalisation d’une transaction) après la survenue d’une erreur de contrôle d’intégrité, vous devez activer l’autorisation **Autoriser d’ignorer l’erreur du contrôle d’intégrité** dans la page **Groupes d’autorisations** (**Commerce et vente au détail \> Employés \> Groupes d’autorisations**). Pour plus d’informations sur la procédure de contrôle d’intégrité, voir [Contrôle d’intégrité d’enregistrement fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurer les états X/Z fiscaux depuis le PDV

Pour activer les états X/Z fiscaux à exécuter depuis le PDV, vous devez ajouter de nouveaux boutons à la mise en page d’un écran de PDV.

- Sur la page **Groupes de boutons**, suivez les instructions d’installation dans [Ajouter des opérations de PDV aux mises de PDV à l’aide du concepteur de groupe de boutons](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) pour installer le concepteur et mettre à jour la mise en page d’un écran de PDV.

    1. Permet de sélectionner la mise en page à mettre à jour. 
    1. Ajoutez un nouveau bouton, puis définissez la propriété de bouton **Imprimer X fiscal**.
    1. Ajoutez un nouveau bouton, puis définissez la propriété de bouton **Imprimer Z fiscal**.
    1. Sur la page **Planification de la distribution**, exécutez la tâche **1090** pour transférer les changements vers la base de données des canaux.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Activer l’exécution manuelle d’un enregistrement fiscal reporté

Pour activer l’exécution manuelle d’un enregistrement fiscal reporté, vous devez ajouter un nouveau bouton à la disposition de l’appareil de PDV.

- Sur la page **Groupes de boutons**, suivez les instructions d’installation dans [Ajouter des opérations de PDV aux mises de PDV à l’aide du concepteur de groupe de boutons](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) pour installer le concepteur et mettre à jour la mise en page d’un écran de PDV.

    1. Permet de sélectionner la mise en page à mettre à jour.
    1. Ajoutez un nouveau bouton, puis définissez la propriété du bouton **Terminer le processus d’enregistrement fiscal**.
    1. Dans la page **Programme de distribution**, exécutez la tâche **1090** pour transférer vos modifications vers la base de données des canaux.


## <a name="view-connection-parameters-and-other-information-in-pos"></a>Afficher les paramètres de connexion et d’autres informations dans le PDV

Pour afficher les paramètres de connexion et d’autres informations dans le PDV, procédez comme suit.

1. Ouvrez Modern POS (MPOS) ou PDV de cloud (CPOS).
1. Sélectionnez **Paramètres**. Si l’intégration fiscale est activée, la section **Intégration fiscale** de droite affichera les informations suivantes :

    - Le statut de l’inscription fiscale
    - L’état de la dernière transaction fiscale
    - Nombre d’événements d’audit en attente

1. Sélectionnez **Détails** pour afficher les informations suivantes :

    - Étapes du processus d’enregistrement
    - Paramètres de connexion
    - Détails des événements d’audit
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
