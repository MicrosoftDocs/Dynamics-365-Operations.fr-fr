---
title: Ajuster un format de gestion des états électroniques pour générer un document électronique personnalisé
description: Cette rubrique explique comment ajuster un format de gestion des états électroniques fourni par Microsoft afin de générer un document électronique personnalisé.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14976aab474b6571c2a25907f04fd4d7ae053e74
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323815"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>Ajuster un format de gestion des états électroniques pour générer un document électronique personnalisé

[!include[banner](../includes/banner.md)]

Les procédures de cette rubrique expliquent comment un utilisateur doté du rôle Administrateur système ou Consultant fonctionnel de gestion des états électroniques peut effectuer les tâches suivantes :

- Configurer les paramètres de la [structure de gestion des états électroniques](general-electronic-reporting.md).
- Importer les configurations de gestion des états électroniques fournies par Microsoft et utilisées pour générer un fichier de paiement lorsqu’un [paiement fournisseur](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) est traité.
- Créer une version personnalisée d’une configuration du format de gestion des états électroniques standard fournie par Microsoft.
- Modifier la configuration du format de gestion des états électroniques personnalisé afin de générer des fichiers de paiement qui répondent aux exigences d’une banque spécifique.
- Adopter les modifications apportées à la configuration du format de gestion des états électroniques standard dans la configuration du format de gestion des états électroniques personnalisée.

Toutes les procédures suivantes peuvent être effectuées dans la société **GBSI**. Aucun codage n’est requis.

- [Configurer la structure de gestion des états électroniques](#ConfigureFramework)

    - [Configurer les paramètres de gestion des états électroniques](#ConfigureParameters)
    - [Activer un fournisseur de configuration de gestion des états électroniques](#ActivateProvider)

        - [Consulter la liste des fournisseurs de configuration de gestion des états électroniques](#ReviewProvidersList)
        - [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#ActivateProvider)
        - [Activer un fournisseur de configuration de gestion des états électroniques](#ActivateAddedProvider)

- [Importer les configurations du format de gestion des états électroniques standard](#ImportERSolution1)

    - [Importer les configurations de gestion des états électroniques standard](#ImportERFormat1)
    - [Passer en revue les configurations de gestion des états électroniques importées](#ReviewImportedERSolution)

- [Préparer un paiement fournisseur pour traitement](#PrepareVendorPayment)

    - [Ajouter des informations bancaires pour un compte fournisseur](#AddBankAccount)
    - [Entrer un paiement fournisseur](#EnterVendorPayment)

- [Traiter un paiement fournisseur en utilisant le format de gestion des états électroniques standard](#ProcessVendorPayment1)

    - [Configurer le mode de paiement électronique](#ConfigureMethodOfPayment1)
    - [Traiter un paiement fournisseur](#ProcessPayment1)

- [Personnaliser le format de gestion des états électroniques standard](#CustomizeProvidedFormat)

    - [Créer un format personnalisé](#DeriveProvidedFormat)
    - [Modifier un format personnalisé](#ConfigureDerivedFormat)
    - [Marquer un format personnalisé comme exécutable](#MarkFormatRunnable)

- [Traiter un paiement fournisseur en utilisant le format de gestion des états électroniques personnalisé](#ProcessVendorPayment2)

    - [Configurer le mode de paiement électronique](#ConfigureMethodOfPayment2)
    - [Traiter un paiement fournisseur](#ProcessPayment2)

- [Importer les nouvelles versions des configurations du format de gestion des états électroniques standard](#ImportERSolution2)

    - [Importer les nouvelles versions des configurations de gestion des états électroniques standard](#ImportERFormat2)
    - [Passer en revue les configurations du format de gestion des états électroniques importées](#ReviewImportedERFormat)

- [Adopter les modifications de la nouvelle version d’un format importé dans un format personnalisé](#AdoptNewBaseVersion)

    - [Finaliser la version provisoire actuelle d’un format personnalisé](#CompleteDerivedFormat)
    - [Redéfinir un format personnalisé sur une nouvelle version de base](#RebaseDerivedFormat)
    - [Traiter un paiement fournisseur en utilisant un format de gestion des états électroniques redéfini](#ProcessPayment3)

- [Ressources supplémentaires](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurer la structure de gestion des états électroniques

En tant qu’utilisateur doté du rôle Consultant fonctionnel de gestion des états électroniques, vous devez configurer l’ensemble minimal des paramètres de gestion des états électroniques avant de pouvoir commencer à utiliser la structure de gestion des états électroniques pour créer une version personnalisée d’un format de gestion des états électroniques standard.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurer les paramètres de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Paramètres de gestion des états électroniques**.
3. Sur la page **Paramètres de gestion des états électroniques**, sous l’onglet **Général**, définissez l’option **Activer le mode de configuration** sur **Oui**.
4. Dans l’onglet **Pièces jointes**, définissez les paramètres suivants :

    - Dans le champ **Configurations**, sélectionnez le type **Fichier** pour la société **USMF**.
    - Dans les champs **Archive de tâche**, **Temporaire**, **Référence** et **Autres**, sélectionnez le type **Fichier**.

Pour plus d’informations sur les paramètres de gestion des états électroniques, voir [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

Chaque configuration de gestion des états électroniques ajoutée est marquée comme appartenant à un fournisseur de configuration de gestion des états électroniques. Le fournisseur de configuration de gestion des états électroniques activé dans l’espace de travail **Gestion des états électroniques** est utilisé à cet effet. Par conséquent, vous devez activer un fournisseur de configuration de gestion des états électroniques dans l’espace de travail **Gestion des états électroniques** avant de commencer à ajouter ou modifier des configurations de gestion des états électroniques.

> [!NOTE]
> Seul le propriétaire d’une configuration de gestion des états électroniques peut la modifier. Par conséquent, avant qu’une configuration de gestion des états électroniques puisse être modifiée, le fournisseur de configuration de gestion des états électroniques approprié doit être activé dans l’espace de travail **Gestion des états électroniques**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Consulter la liste des fournisseurs de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Table des fournisseurs de configuration**, chaque enregistrement de fournisseur a un nom et une URL uniques. Passez en revue le contenu de cette page. S’il existe déjà un enregistrement pour **Litware, Inc.** (`https://www.litware.com`), ignorez la procédure suivante, [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Ajouter un nouveau fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Fournisseurs de configuration**, sélectionnez **Nouveau**.
4. Dans le champ **Nom**, entrez **Litware, Inc.**
5. Dans le champ **Adresse Internet**, entrez `https://www.litware.com`.
6. Sélectionnez **Enregistrer**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**, puis sélectionnez **Activer**.

Pour plus d’informations sur les fournisseurs de configuration de gestion des états électroniques, voir [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importer les configurations du format de gestion des états électroniques standard

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>Importer les configurations de gestion des états électroniques standard

Pour ajouter les configurations de gestion des états électroniques standard à votre instance actuelle de Microsoft Dynamics 365 Finance, vous devez les importer depuis le [référentiel](general-electronic-reporting.md#Repository) de gestion des états électroniques qui a été configuré pour cette instance.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**, puis sélectionnez **Référentiels** pour afficher la liste des référentiels du fournisseur Microsoft.
3. Sur la page **Référentiels de configuration**, sélectionnez le référentiel de type **Global**, puis sélectionnez **Ouvrir**. Si vous êtes invité à autoriser la connexion à Regulatory Configuration Service, suivez les instructions d’autorisation.
4. Sur la page **Référentiel de configuration**, dans l’arborescence de configuration du volet gauche, sélectionnez la configuration de format **BACS (UK)**.
5. Dans l’organisateur **Versions**, sélectionnez la version **1.1** de la configuration du format de gestion des états électroniques sélectionnée.
6. Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance actuelle de Finance.

![Page du référentiel de configuration.](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> Si vous ne parvenez pas à accéder au [Référentiel global](er-download-configurations-global-repo.md), vous pouvez [télécharger les configurations](download-electronic-reporting-configuration-lcs.md) depuis Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Passer en revue les configurations de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**.
4. Notez qu’en plus du format de gestion des états électroniques **BACS (UK)** sélectionné, d’autres configurations de gestion des états électroniques requises ont été importées. Assurez-vous que les configurations de gestion des états électroniques suivantes sont disponibles dans l’arborescence de configuration :

    - **Modèle de paiement** – Cette configuration contient le composant de gestion des états électroniques Modèle de données qui représente la structure de données du domaine d’activité du paiement.
    - **Mise en correspondance des modèles de paiement 1611** – Cette configuration contient le composant de gestion des états électroniques Mise en correspondance des modèles qui décrit comment le modèle de données est rempli avec les données d’application au moment de l’exécution.
    - **BACS (UK)** – Cette configuration contient les composants de gestion des états électroniques Format et Mise en correspondance des formats. Le composant Format spécifie la présentation de l’état. Le composant Mise en correspondance des formats contient la source de données du modèle et spécifie comment la présentation de l’état est remplie en utilisant cette source de données au moment de l’exécution.

![Page de configurations avec les configurations ER spécifiées disponibles dans l'arborescence.](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>Préparer un paiement fournisseur pour traitement

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>Ajouter des informations bancaires pour un compte fournisseur

Vous devez ajouter des informations bancaires pour un compte fournisseur auquel il sera fait référence ultérieurement dans un paiement enregistré.

1. Accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**.
2. Sur la page **Tous les vendeurs**, sélectionnez le compte fournisseur **GB_SI_000001**, puis, dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Paramétrer**, sélectionnez **Comptes bancaires**.
3. Sur la page **Comptes bancaires fournisseur**, sélectionnez **Nouveau**, puis entrez les informations suivantes :

    1. Dans le champ **Compte bancaire**, entrez **GBP OPER**.
    2. Dans le champ **Groupes bancaires**, sélectionnez **BankGBP**.
    3. Dans le champ **Numéro de compte bancaire**, entrez **202015**.
    4. Dans le champ **Code SWIFT**, entrez <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.
    5. Dans le champ **IBAN**, entrez **GB33BUKB20201555555555**.
    6. Dans le champ **Numéro d’acheminement**, conservez la valeur par défaut, <a id="DefineRoutingNumber"></a>**123456**.

    ![Page Comptes bancaires fournisseur.](./media/er-quick-start2-bank-account.png)

4. Sélectionnez **Enregistrer**.
5. Fermez la page.
6. Sur la page **Tous les vendeurs**, ouvrez le compte fournisseur **GB_SI_000001**.
7. Sur la page Détails sur le fournisseur, sélectionnez **Modifier** pour rendre la page modifiable, si nécessaire.
8. Dans l’organisateur **Paiement**, dans le champ **Compte bancaire**, sélectionnez **GBP OPER**.

    ![Page Détails sur le fournisseur.](./media/er-quick-start2-bank-account-reference.png)

9. Sélectionnez **Enregistrer**.
10. Fermez la page.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>Entrer un paiement fournisseur

Vous devez entrer un nouveau paiement fournisseur en utilisant une [proposition de paiement](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md).

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Sur la page **Journal des paiements fournisseur**, sélectionnez **Nouveau**.
3. Dans le champ **Nom**, sélectionnez **VendPay**.
4. Sélectionnez **Lignes**.
5. Sélectionnez **Proposition de paiement** \> **Créer une proposition de paiement**.
6. Dans la boîte de dialogue **Proposition de paiement fournisseur**, configurez les conditions de filtrage des enregistrements pour le compte fournisseur **GB_SI_000001** uniquement, puis cliquez sur **OK**.
7. Sélectionnez la ligne de la facture **00000007_Inv**, puis sélectionnez **Créer un paiement**.

    ![Boîte de dialogue Proposition de paiement fournisseur.](./media/er-quick-start2-payment-proposal.png)

8. Vérifiez que le paiement entré est configuré pour utiliser le mode de paiement **Électronique**.

    ![Page Paiements fournisseur.](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>Traiter un paiement fournisseur en utilisant le format de gestion des états électroniques standard

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>Configurer le mode de paiement électronique

Vous devez configurer le mode de paiement électronique afin qu’il utilise la configuration du format de gestion des états électroniques importée.

1. Accédez à **Comptabilité fournisseur** \> **Paramétrage des paiements** \> **Modes de paiement**.
2. Sur la page **Modes de paiement – fournisseurs**, sélectionnez le mode de paiement **Électronique** dans le volet gauche.
3. Sélectionnez **Modifier**.
4. Dans l’organisateur **Formats de fichier**, définissez l’option **Format d’exportation électronique général** sur **Oui**.
5. Dans le champ **Exporter la configuration du format**, sélectionnez la configuration de format **BACS (UK)**.

    ![Modes de paiement - page fournisseurs pour configurer un mode de paiement électronique afin de traiter les paiements des fournisseurs à l'aide d'un format standard.](./media/er-quick-start2-method-of-payment1.png)

6. Sélectionnez **Enregistrer**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>Traiter un paiement fournisseur

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Sur la page **Journal des paiements fournisseur**, sélectionnez le journal des paiements que vous avez ajouté précédemment, puis sélectionnez **Lignes**.
3. Sur la page **Paiements fournisseur**, sélectionnez **Générer des paiements**.
4. Dans la boîte de dialogue **Générer des paiements**, entrez les informations suivantes :

    - Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
    - Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.

5. Cliquez sur **OK**.
6. Dans la boîte de dialogue **Paramètres des états électroniques**, définissez l’option **Imprimer l’état de contrôle** sur **Oui**, puis cliquez sur **OK**.

    ![Page de boîte de dialogue Paramètres des états électroniques.](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > En plus du fichier de paiement, vous pouvez maintenant générer l’état de contrôle.

7. Téléchargez le fichier zip, puis extrayez-en les fichiers suivants :

    - État de contrôle au format Excel
    - Fichier de paiement au format TXT

        Notez que, conformément à la [structure](#PositionRoutingNumber) du format de gestion des états électroniques fourni, la ligne de paiement du fichier généré commence par le numéro d’acheminement qui a été [défini](#DefineRoutingNumber) pour le compte bancaire configuré.

        ![Fichier de paiement au format TXT.](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personnaliser le format de gestion des états électroniques standard

Pour l’exemple illustré dans cette section, vous souhaitez utiliser les configurations de gestion des états électroniques fournies par Microsoft pour générer des fichiers de paiement fournisseur au format BACS, mais vous devez ajouter une personnalisation pour prendre en charge les exigences d’une banque spécifique. Vous souhaitez également pouvoir mettre à niveau votre format personnalisé lorsque de nouvelles versions des configurations de gestion des états électroniques deviennent disponibles. Cependant, vous souhaitez pouvoir effectuer la mise à niveau à moindre coût.

Dans ce cas, en tant que représentant de Litware, Inc., vous devez créer (dériver) une nouvelle configuration du format de gestion des états électroniques en utilisant la configuration fournie par Microsoft **BACS (UK)** comme base.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Créer un format personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **BACS (UK)**. Litware, Inc. utilisera la version 1.1 de cette configuration du format de gestion des états électroniques comme base pour la version personnalisée.
3. Sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante. Vous pouvez utiliser cette boîte de dialogue pour créer une configuration pour un format de paiement personnalisé.
4. Dans le groupe de champs **Nouveau**, sélectionnez l’option **Provenant du nom : BACS (UK), Microsoft**.
5. Dans le champ **Nom**, entrez **BACS (UK custom)**.

    ![Boîte de dialogue déroulante Créer une configuration.](./media/er-quick-start2-add-derived-format.png)

6. Sélectionnez **Créer une configuration**.

La version 1.1.1 de la configuration du format de gestion des états électroniques **BACS (UK custom)** est créée. Cette version présente le [statut](general-electronic-reporting.md#component-versioning) **Brouillon** et peut être modifiée. Le contenu actuel de votre format de gestion des états électroniques personnalisé correspond au contenu du format fourni par Microsoft.

![Page de configurations avec la version 1.1.1 de la configuration du format ER BACS (UK custom).](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>Modifier un format personnalisé

Vous devez configurer votre format personnalisé afin qu’il réponde aux exigences spécifiques à la banque. Par exemple, une banque peut exiger que les fichiers de paiement générés comprennent le code SWIFT (Society for Worldwide Interbank Financial Telecommunication) d’une banque à laquelle le rôle d’agent est affecté dans le paiement fournisseur traité. Les codes SWIFT sont des codes bancaires internationaux qui identifient des banques spécifiques dans le monde entier. Ils sont également appelés Codes identificateur de banque (BIC). Le code SWIFT doit comporter 11 caractères et doit être entré au début de chaque ligne de paiement d’un fichier de paiement généré.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **BACS (UK custom)**.
3. Dans l’organisateur **Versions**, sélectionnez la version **1.1.1** de la configuration sélectionnée.
4. Sélectionnez **Concepteur**.
5. Sur la page **Concepteur de formats**, sélectionnez **Afficher les détails** pour afficher d’autres informations sur les éléments de format.
6. Développez et passez en revue les éléments suivants :

    - Élément **BACSReportsFolder** de type **Dossier**. Cet élément permet de générer une sortie au format ZIP.
    - Élément **file** de type **Fichier**. Cet élément permet de générer un fichier de paiement au format TXT.
    - Élément **transactions** de type **Séquence**. Cet élément permet de générer une ligne de paiement unique dans un fichier de paiement.
    - Élément **transaction** de type **Séquence**. Cet élément permet de générer les fichiers individuels d’une ligne de paiement unique.

7. Sélectionnez l’élément **transaction**.

    ![Élément de transaction dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > L’état fourni est configuré de sorte que <a id="PositionRoutingNumber"></a>chaque ligne de paiement commence par le numéro d’acheminement bancaire. L’élément de format **vendBankRouteNum** est utilisé à cet effet. 

8. Sélectionnez **Ajouter**, puis sélectionnez le type **Texte\\Chaîne** de l’élément de format que vous ajoutez :

    1. Dans le champ **Nom**, entrez **vendBankSWIFT**.
    2. Dans le champ **Longueur minimum**, entrez **11**.
    3. Dans le champ **Longueur maximum**, entrez **11**.
    4. Cliquez sur **OK**.

    > [!NOTE]
    > L’élément **vendBankSWIFT** sera utilisé pour entrer le code SWIFT d’une banque fournisseur dans les fichiers générés.

9. Dans l’arborescence de la structure du format, sélectionnez **vendBankSWIFT**.
10. Sélectionnez **Déplacer vers le haut** pour déplacer l’élément de format sélectionné d’un niveau vers le haut. Répétez cette étape jusqu’à ce que l’élément **vendBankSWIFT** soit le <a id="PositionSWIFTCode"></a>premier élément sous l’élément parent **transaction**.

    ![VendBankSWIFT comme premier élément sous la transaction dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-derived-format1.png)

11. Alors que l’élément **vendBankSWIFT** est toujours sélectionné dans l’arborescence de la structure du format, sélectionnez l’onglet **Mise en correspondance**, puis développez la source de données **modèle**.
12. Développez **model.Payment** \> **model.Payment.CreditorAgent** et sélectionnez le champ de source de données **model.Payment.CreditorAgent.BICFI**. Ce champ de source de données expose le code SWIFT d’une banque fournisseur à laquelle le rôle d’agent est affecté dans le paiement fournisseur traité.
13. Sélectionnez **Lier**. L’élément de format **vendBankSWIFT** est maintenant lié au champ de source de données **model.Payment.CreditorAgent.BICFI**, afin que les codes SWIFT soient entrés dans les fichiers de paiement générés.

    ![Élément de format vendBankSWIFT lié au champ de source de données model.Payment.CreditorAgent.BICFI dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-derived-format2.png)

14. Sélectionnez **Enregistrer**.
15. Fermez la page du concepteur.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marquer un format personnalisé comme exécutable

Maintenant que la première version de votre format personnalisé a été créée et présente le statut **Brouillon**, vous pouvez l’exécuter à des fins de test. Pour exécuter l’état, vous devez traiter un paiement fournisseur en utilisant le mode de paiement qui fait référence à votre format de gestion des états électroniques personnalisé. Par défaut, lorsque vous appelez un format de gestion des états électroniques depuis l’application, seules les versions qui ont le statut **Terminé** et **Partagé** sont [prises en compte](general-electronic-reporting.md#component-versioning). Ce comportement permet de ne pas utiliser les formats de gestion des états électroniques dont les conceptions sont inachevées. Cependant, pour vos exécutions de test, vous pouvez forcer l’application à utiliser la version de votre format de gestion des états électroniques dont le statut est **Brouillon**. De cette façon, vous pouvez ajuster la version actuelle du format si des modifications sont nécessaires. Pour plus d’informations, voir [Applicabilité](electronic-reporting-destinations.md#applicability).

Pour utiliser la version provisoire d’un format de gestion des états électroniques, vous devez explicitement marquer le format de gestion des états électroniques.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.
4. Sélectionnez **Modifier** pour rendre la page active modifiable, selon les besoins.
5. Dans l’arborescence de configuration du volet gauche, sélectionnez **BACS (UK custom)**.
6. Définissez l’option **Exécuter le brouillon** sur **Oui**.

    ![Option Exécuter le brouillon de la page Configurations.](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>Traiter un paiement fournisseur en utilisant le format de gestion des états électroniques personnalisé

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>Configurer le mode de paiement électronique

Vous devez configurer le mode de paiement électronique afin que votre format de gestion des états électroniques personnalisé soit utilisé pour traiter les paiements fournisseur.

1. Accédez à **Comptabilité fournisseur** \> **Paramétrage des paiements** \> **Modes de paiement**.
2. Sur la page **Modes de paiement – fournisseurs**, sélectionnez le mode de paiement **Électronique** dans le volet gauche.
3. Sélectionnez **Modifier**.
4. Dans l’organisateur **Format de fichier**, définissez l’option **Format d’exportation électronique général** sur **Oui**.
5. Dans le champ **Exporter la configuration du format**, sélectionnez la configuration de format **BACS (UK custom)**.

    ![Modes de paiement - page fournisseurs pour configurer un mode de paiement électronique afin de traiter les paiements des fournisseurs à l'aide d'un format personnalisé.](./media/er-quick-start2-method-of-payment2.png)

6. Sélectionnez **Enregistrer**.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>Traiter un paiement fournisseur

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Sur la page **Journal des paiements fournisseur**, sélectionnez le journal des paiements que vous avez créé précédemment.
3. Sélectionnez **Lignes**.
4. Sur la page **Paiements fournisseur**, au-dessus de la grille, sélectionnez **Statut de paiement** \> **Aucun**.
5. Sélectionnez **Générer des paiements**.
6. Dans la boîte de dialogue **Générer des paiements**, entrez les informations suivantes :

    - Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
    - Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.

7. Cliquez sur **OK**.
8. Dans la boîte de dialogue **Paramètres des états électroniques**, définissez l’option **Imprimer l’état de contrôle** sur **Oui**, puis cliquez sur **OK**.

    > [!NOTE]
    > En plus du fichier de paiement, vous ne pouvez générer que l’état de contrôle.

9. Téléchargez le fichier zip, puis extrayez-en les fichiers suivants :

    - État de contrôle au format Excel
    - Fichier de paiement au format TXT

        Notez que, conformément à la structure de votre format de gestion des états électroniques personnalisé, la ligne de paiement du fichier généré [commence](#PositionSWIFTCode) maintenant par le code SWIFT qui a été [entré](#DefineSWIFTCode) pour le compte bancaire du vendeur dont le paiement a été traité.

        ![Fichier de paiement au format TXT utilisé pour traiter le paiement du fournisseur.](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>Importer les nouvelles versions des configurations du format de gestion des états électroniques standard

Pour l’exemple illustré dans cette section, vous recevez une notification concernant l’article de la base de connaissances [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046). Cette notification vous informe de la nouvelle version du format de gestion des états électroniques **BACS (UK)** qui a été publié par Microsoft. En plus de l’état de contrôle, cette nouvelle version permet aux utilisateurs de générer l’état Avis de paiement et l’état Note de participation pendant le traitement d’un paiement fournisseur. Vous souhaitez commencer à utiliser cette fonctionnalité.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>Importer les nouvelles versions des configurations de gestion des états électroniques standard

Pour ajouter les nouvelles versions des configurations de gestion des états électroniques à l’instance actuelle de Finance, vous devez les importer depuis le [référentiel](general-electronic-reporting.md#Repository) de gestion des états électroniques que vous avez configuré.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**, puis sélectionnez **Référentiels** pour afficher la liste des référentiels du fournisseur Microsoft.
3. Sur la page **Référentiels de configuration**, sélectionnez le référentiel de type **Global**, puis sélectionnez **Ouvrir**. Si vous êtes invité à autoriser la connexion à Regulatory Configuration Service, suivez les instructions d’autorisation.
4. Sur la page **Référentiel de configuration**, dans l’arborescence de configuration du volet gauche, sélectionnez la configuration de format **BACS (UK)**.
5. Dans l’organisateur **Versions**, sélectionnez la version **3.3** de la configuration du format de gestion des états électroniques sélectionnée.
6. Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance actuelle de Finance.

![Page Référentiel de configuration, raccourci Versions, bouton Importer.](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> Si vous ne parvenez pas à accéder au [Référentiel global](er-download-configurations-global-repo.md), vous pouvez [télécharger les configurations](download-electronic-reporting-configuration-lcs.md) depuis LCS.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>Passer en revue les configurations du format de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **BACS (UK)**.
4. Dans l’organisateur **Versions**, sélectionnez la version **3.3**.
5. Sélectionnez **Concepteur**.
6. Sur la page **Concepteur de formats**, développez l’élément de format **BACSReportsFolder**.
7.  Notez que la version 3.3 contient l’élément de format **PaymentAdviceReport** utilisé pour générer un état d’avis de paiement lorsqu’un paiement fournisseur est traité.

    ![Élément de format PaymentAdviceReport du concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-imported-solution2.png)

8. Fermez la page du concepteur.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>Adopter les modifications de la nouvelle version d’un format importé dans un format personnalisé

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>Finaliser la version provisoire actuelle d’un format personnalisé

Si vous souhaitez conserver l’état actuel de votre format personnalisé, finalisez la version provisoire 1.1.1 en modifiant son statut de **Brouillon** à **Terminé**.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, **BACS (UK)**, puis sélectionnez **BACS (UK custom)**.
4. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut** \> **Terminé**, puis cliquez sur **OK**.

Le statut de la version 1.1.1 passe de **Brouillon** à **Terminé** et la version devient en lecture seule. Une nouvelle version modifiable, 1.1.2, a été ajoutée et son statut est **Brouillon**. Vous pouvez utiliser cette version pour apporter d’autres modifications à votre format de gestion des états électroniques personnalisé.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>Redéfinir un format personnalisé sur une nouvelle version de base

Pour commencer à utiliser la nouvelle fonctionnalité de la version 3.3 du format **BACS (UK)** dans votre personnalisation, vous devez modifier la version de configuration de base pour la configuration personnalisée, **BACS (UK custom)**. Ce processus est appelé [redéfinition de la base](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase). Au lieu de la nouvelle version 1.1 de **BACS (UK)**, utilisez la version 3.3.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **BACS (UK custom)**.
3. Dans l’organisateur **Versions**, sélectionnez la version **1.1.2**, puis sélectionnez **Redéfinir**.
4. Dans la boîte de dialogue **Redéfinir**, dans le champ **Version cible**, sélectionnez la version **3.3** de la configuration de base pour l’appliquer en tant que nouvelle base et l’utiliser pour mettre à jour la configuration.

    ![Boîte de dialogue Redéfinir.](./media/er-quick-start2-rebase1.png)

5. Cliquez sur **OK**.
6. Notez que le numéro de la version provisoire a été modifié de **1.1.2** à **3.3.2** pour refléter les modifications de la version de base.

    Lorsque la version personnalisée et une nouvelle version de base sont fusionnées, des conflits peuvent être détectés à cause des modifications de format qui ne peuvent pas être fusionnées automatiquement.

    ![Configuration redéfinie avec des conflits sur la page Configurations.](./media/er-quick-start2-rebase2.png)

    Si des conflits sont détectés, ils doivent être résolus manuellement dans le concepteur de format.

7. Dans l’organisateur **Versions**, sélectionnez la version **3.3.2**.
8. Sélectionnez **Concepteur**.
9. Dans la page **Concepteur de formats**, dans l’organisateur **Détails**, sélectionnez un enregistrement de conflit de redéfinition, puis sélectionnez **Appliquer la valeur de base**.

    ![Enregistrement de conflit de redéfinition dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-rebase3.png)

10. Sélectionnez **Enregistrer**.

    L’enregistrement de conflit de redéfinition ne devrait plus s’afficher dans l’organisateur **Détails**.

    ![Conflit résolu dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > Vous avez résolu le conflit en confirmant que la version 3 du modèle de base doit être utilisée dans ce format de gestion des états électroniques.

11. Développez **BACSReportsFolder** \> **fichier** \> **transactions** \> **transaction**.
12. Sous l’onglet **Mise en correspondance**, notez que la version 3.3.2 de votre format de gestion des états électroniques personnalisé contient à la fois votre personnalisation (l’élément de format **vendBankSWIFT** et sa liaison) et la nouvelle fonctionnalité de la version 3.3 du format de gestion des états électroniques de base fournie par Microsoft (l’élément de format **PaymentAdviceReport** ainsi que ses éléments imbriqués et ses liaisons configurées). En quelques clics de souris, vous avez adopté les modifications d’une nouvelle version de base en les fusionnant avec votre personnalisation.

    ![Format fusionné dans le concepteur d’opérations de gestion des états électroniques.](./media/er-quick-start2-rebase5.png)

13. Fermez la page du concepteur.

> [!NOTE]
> L’action de redéfinition est réversible. Pour annuler cette redéfinition, sélectionnez la version **1.1.1** du format **BACS (personnalisé pour le Royaume-Uni)** dans l’organisateur **Versions**, puis sélectionnez **Obtenir cette version**. La version 3.3.2 sera alors renumérotée 1.1.2 et le contenu de la version provisoire 1.1.2 correspondra au contenu de la version 1.1.1.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>Traiter un paiement fournisseur en utilisant un format de gestion des états électroniques redéfini

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Sur la page **Journal des paiements fournisseur**, sélectionnez le journal des paiements que vous avez créé précédemment.
3. Sélectionnez **Lignes**.
4. Sur la page **Paiements fournisseur**, au-dessus de la grille, sélectionnez **Statut de paiement** \> **Aucun**.
5. Sélectionnez **Générer des paiements**.
6. Dans la boîte de dialogue **Générer des paiements**, entrez les informations suivantes :

    - Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
    - Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.

7. Cliquez sur **OK**.
8. Dans la boîte de dialogue **Paramètres des états électroniques**, entrez les informations suivantes :

    - Définissez l’option **Imprimer l’état de contrôle** sur **Oui**.
    - Définissez l’option **Imprimer un avis de paiement** sur **Oui**.

    ![Boîte de dialogue Paramètres de génération d’états électroniques.](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > En plus du fichier de paiement, vous pouvez maintenant générer à la fois l’état de contrôle et l’état d’avis de paiement.

9. Cliquez sur **OK**.
10. Téléchargez le fichier zip, puis extrayez-en les fichiers suivants :

    - État de contrôle au format Excel
    - État d’avis de paiement au format Excel

        ![État d’avis de paiement au format Excel.](./media/er-quick-start2-payment-advice-report.png)

    - Fichier de paiement au format TXT

        Notez que la ligne de paiement du fichier généré commence par le code SWIFT qui a été entré pour le compte bancaire d’un vendeur dont le paiement a été traité.

        ![Fichier de paiement au format TXT utilisé pour traiter le paiement du fournisseur à l'aide d'un format ER redéfini.](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Télécharger les configurations de gestion des états électroniques depuis Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Télécharger les configurations de gestion des états électroniques depuis le référentiel global du service de configuration](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
