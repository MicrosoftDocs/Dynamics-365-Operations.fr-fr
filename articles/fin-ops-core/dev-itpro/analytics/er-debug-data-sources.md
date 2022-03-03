---
title: Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation
description: Cette rubrique explique comment vous pouvez déboguer les sources de données d’un format ER exécuté pour mieux comprendre le flux de données et la transformation configurés.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 02aee8c6ec3b2720c2fcbb17f15791d88d688a34
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323759"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Lorsque vous [configurez](tasks/er-format-configuration-2016-11.md) une solution de gestion des états électroniques (ER) pour générer des documents sortants, vous définissez les méthodes qui sont utilisées pour obtenir des données issues de l’application et pour les entrer dans la sortie qui est générée. Pour rendre le support de cycle de vie de la solution ER plus efficace, votre solution doit consister en un modèle de données ER et ses composants de mise en correspondance, et aussi un format ER et ses composants de mise en correspondance, de sorte que la mise en correspondance des modèles est spécifique à l’application, tandis que d’autres composants restent indépendants de l’application. Par conséquent, plusieurs composants ER peuvent affecter le processus de saisie des données dans la sortie générée.

Parfois, les données de la sortie générée sont différentes des mêmes données dans la base de données d’application. Dans ces cas, vous souhaiterez déterminer quel composant ER est responsable de la transformation des données. La fonction de débogage de source de données ER réduit considérablement le temps et les coûts impliqués dans cette enquête. Vous pouvez interrompre l’exécution d’un format ER et ouvrir l’interface du débogueur de source de données. Là, vous pouvez parcourir les sources de données disponibles et sélectionner une source de données individuelle pour l’exécution. Cette exécution manuelle simule l’exécution de la source de données pendant l’exécution réelle d’un format ER. Le résultat est présenté sur une page où vous pouvez analyser les données reçues.

Pour activer la fonction de débogage de la source de données, définissez l’option **Activer le débogage des données lors de l’exécution du format** sur **Oui** dans les paramètres utilisateur ER. Vous pouvez ensuite démarrer le débogage de la source de données pendant que vous exécutez un format ER pour générer des documents sortants. Vous pouvez également utiliser l’option **Démarrer le débogage** pour lancer le débogage de la source de données pour un format ER configuré dans le [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).

Cette rubrique fournit des instructions pour lancer le débogage de la source de données pour les formats ER exécutés. Il explique comment les informations peuvent vous aider à comprendre le flux de données et les transformations de données. Les exemples de cette rubrique utilisent le processus technique pour le traitement des paiements fournisseur.

## <a name="limitations"></a>Limitations

Le débogueur de source de données peut être utilisé pour accéder aux données des sources de données utilisées dans les formats ER qui sont exécutés pour générer des documents sortants. Il ne peut pas être utilisé pour déboguer des sources de données de formats ER conçus pour analyser des documents entrants.

Les paramètres suivants des formats ER ne sont actuellement pas accessibles pour le débogage de la source de données :

- Transformations de format
- Format et mise en correspondance des règles de validation
- Activation des expressions
- Détails de la collecte de données en mémoire

## <a name="prerequisites"></a>Conditions préalables

- Pour terminer les exemples de cette rubrique, vous devez avoir accès aux [rôles](../sysadmin/tasks/assign-users-security-roles.md) suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel de gestion des états électroniques
    - Administrateur système

- La société doit être paramétrée sur **DEMF**.

- Suivez les étapes de l’[Annexe 1](#appendix1) de cette rubrique pour télécharger les composants de la solution Microsoft ER requis pour traiter les paiements des fournisseurs.
- Suivez les étapes de l’[Annexe 2](#appendix2) de cette rubrique pour préparer la comptabilité fournisseur pour le traitement des paiements des fournisseurs à l’aide de la solution ER que vous téléchargerez.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>Traiter un paiement fournisseur pour obtenir un fichier de paiement

1. Suivez les étapes de l’[Annexe 3](#appendix3) de cette rubrique pour traiter les paiements des fournisseurs.

    ![Traitement des paiements fournisseur en cours.](./media/er-data-debugger-process-payment.png)

2. Téléchargez et enregistrez le fichier zip sur votre ordinateur local.
3. Extrayez le fichier de paiement **Transfert de crédit ISO20022.xml** à partir du fichier zip.
4. Ouvrez le fichier de paiement extrait à l’aide de la visionneuse de fichiers XML.

    Dans le fichier de paiement, le code IBAN (International Bank Account Number) du compte bancaire du fournisseur ne contient aucun espace. Par conséquent, il diffère de la valeur qui était [entrée](#enteredIBANcode) sur la page **Comptes bancaires**.

    ![Code IBAN sans espaces.](./media/er-data-debugger-payment-file.png)

    Vous pouvez utiliser le débogueur de sources de données ER pour savoir quel composant de la solution ER est utilisé pour tronquer les espaces dans le code IBAN.

## <a name="turn-on-data-source-debugging"></a>Activer le débogage des sources de données

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Paramétrez l’option **Activer le débogage des données lors de l’exécution du format** sur **Oui**.

    > [!NOTE]
    > Ce paramètre est spécifique à l’utilisateur et à l’entreprise.

    ![Boîte de dialogue Paramètres utilisateur.](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>Traiter un paiement fournisseur pour le débogage

1. Suivez les étapes de l’[Annexe 3](#appendix3) de cette rubrique pour traiter les paiements des fournisseurs.
2. Dans la boîte de message, sélectionnez **Oui** pour confirmer que vous souhaitez interrompre le traitement des paiements fournisseur et démarrer le débogage de la source de données à la place sur la page **Déboguer les sources de données**.

    ![Boîte de message de confirmation.](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>Déboguer les sources de données utilisées dans le traitement des paiements

### <a name="debug-the-model-mapping"></a>Déboguer la mise en correspondance des modèles

1. Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Mise en correspondance de modèles** pour commencer à déboguer à partir de ce composant ER.
2. Dans le volet de la source de données sur la gauche, sélectionnez la source de données **\$notSentTransactions**, puis sélectionnez **Lire tous les enregistrements**.

    Vous pouvez sélectionner **Lire 1 enregistrement**, **Lire 10 enregistrements**, **Lire 100 enregistrements** ou **Lire tous les enregistrements** pour forcer le nombre approprié d’enregistrements à lire à partir de la source de données sélectionnée. De cette façon, vous pouvez simuler l’accès à la source de données à partir du format ER en cours d’exécution.

3. Dans le volet des données de droite, sélectionnez **Développer tout**.

    Vous pouvez voir que la source de données sélectionnée du type **Liste des enregistrements** contient un seul enregistrement.

4. Développez la source de données **\$notSentTransactions** et sélectionnez la méthode **vendBankAccountInTransactionCompany ()** imbriquée.
5. Développez la méthode **vendBankAccountInTransactionCompany()**, puis sélectionnez le champ **IBAN**.
6. Sélectionnez **Obtenir la valeur**.

    Vous pouvez sélectionner **Obtenir la valeur** pour forcer la lecture d’un champ sélectionné de la source de données sélectionnée. De cette façon, vous pouvez simuler l’accès à ce champ à partir du format ER en cours d’exécution.

7. Sélectionnez **Développer tout**.

    ![Valeur du champ IBAN dans la mise en correspondance des modèles.](./media/er-data-debugger-debugging-model-mapping.png)

    Comme vous pouvez le voir, la mise en correspondance des modèles n’est pas responsable des espaces tronqués, car le code IBAN qu’il renvoie pour le compte bancaire du fournisseur comprend des espaces. Par conséquent, vous devez continuer le débogage de la source de données.

### <a name="debug-the-format-mapping"></a>Déboguer la mise en correspondance des formats

1. Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Mise en correspondance des formats** pour continuer à déboguer à partir de ce composant ER.
2. Sélectionnez la source de données **\$PaymentByDebtor**, puis sélectionnez **Lire tous les enregistrements**.
3. Développez **\$PaymentByDebtor**.
4. Développez **\$PaymentByDebtor.Lines**, puis sélectionnez **Lire tous les enregistrements**.
5. Développez **\$PaymentByDebtor.Lines.CreditorAccount**.
6. Développez **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, puis sélectionnez **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.
7. Sélectionnez **Obtenir la valeur**.
8. Sélectionnez **Développer tout**.

    ![Valeur du champ IBAN dans la mise en correspondance des formats.](./media/er-data-debugger-debugging-format-mapping.png)

    Comme vous pouvez le voir, les sources de données de la mise en correspondance des formats ne sont pas responsables des espaces tronqués, car le code IBAN qu’elles renvoient pour le compte bancaire du fournisseur comprend des espaces. Par conséquent, vous devez continuer le débogage de la source de données.

### <a name="debug-the-format"></a>Déboguer le format

1. Sur la page **Déboguer les sources de données**, dans le volet Actions, sélectionnez **Format** pour continuer à déboguer à partir de ce composant ER.
2. Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, puis sélectionnez **Lire tous les enregistrements**.
3. Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, puis sélectionnez **Lire tous les enregistrements**.
4. Développez les éléments de format pour sélectionner **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, puis sélectionnez **Obtenir la valeur**.
5. Sélectionnez **Développer tout**.

    ![Valeur du champ IBAN dans le format.](./media/er-data-debugger-debugging-format.png)

   Comme vous pouvez le voir, la liaison de format n’est pas responsable des espaces tronqués, car le code IBAN qu’elle renvoie pour le compte bancaire du fournisseur comprend des espaces. Par conséquent, l’élément **BankIBAN** est configuré pour utiliser une transformation de format qui tronque les espaces.

6. Fermez le débogueur de source de données.

### <a name="review-the-format-transformations"></a>Examiner les transformations de format

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, sélectionnez **Modèle de paiement** \> **ISO20022 Credit transfer**.
3. Sélectionnez **Concepteur**, puis développez les éléments pour sélectionner **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.

    ![Élément BankIBAN sur la page Concepteur de format.](./media/er-data-debugger-referred-transformation.png)

    Comme vous pouvez le voir, l’élément **BankIBAN** est configuré pour utiliser la transformation **supprimer non alphanumérique**.

4. Sélectionnez l’onglet **Transformations**.

    ![Onglet Transformations de l’élément BankIBAN.](./media/er-data-debugger-transformation.png)

    Comme vous pouvez le voir, la transformation **supprimer non alphanumérique** est configurée pour utiliser une expression qui tronque les espaces de la chaîne de texte fournie.

## <a name="start-to-debug-in-the-operation-designer"></a>Commencer à déboguer dans le Concepteur d’opérations

Lorsque vous configurez une version provisoire du format ER pouvant être exécutée directement à partir du concepteur d’opérations, vous pouvez accéder au débogueur de source de données en sélectionnant **Démarrer le débogage** dans le volet Action.

![Bouton Démarrer le débogage sur la page Concepteur de format.](./media/er-data-debugger-run-from-designer.png)

La mise en correspondance des formats et des composants de format du format ER en cours de modification sont disponibles pour le débogage.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>Commencer à déboguer dans le Concepteur de mise en correspondance des modèles

Lorsque vous configurez une mise en correspondance des modèles ER pouvant être exécutée à partir de la page **Mise en correspondance des modèles**, vous pouvez accéder au débogueur de source de données en sélectionnant **Démarrer le débogage** dans le volet Action.

![Bouton Démarrer le débogage sur la page Concepteur de mise en correspondances de modèles.](./media/er-data-debugger-run-from-designer-mapping.png)

Le composant de mise en correspondance des modèles de la mise en correspondance ER en cours de modification est disponible pour le débogage.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>Annexe 1 : Obtenir une solution ER

### <a name="download-an-er-solution"></a>Télécharger une solution ER

Si vous souhaitez utiliser une solution ER pour générer un fichier de paiement électronique pour un paiement fournisseur qui est traité, vous pouvez [télécharger](download-electronic-reporting-configuration-lcs.md) le format de paiement ER **Transfert de crédit ISO20022** disponible dans la bibliothèque de ressources partagées dans Microsoft Dynamics Lifecycle Services (LCS) ou à partir du référentiel global.

![Importation du format de paiement ER sur la page Référentiel de configuration.](./media/er-data-debugger-import-from-repo.png)

En plus du format ER sélectionné, les [configurations](general-electronic-reporting.md#Configuration) suivantes doivent être automatiquement importées dans votre instance de Microsoft Dynamics 365 Finance dans le cadre de la solution ER **Transfert de crédit ISO20022** :

- Configuration du modèle de données ER **Modèle de paiement**
- Configuration format ER **Virement ISO20022**
- **Mise en correspondance du modèle de paiement 1611** Configuration de la mise en correspondance du modèle ER
- Configuration de la mise en correspondance du modèle ER **Mise en correspondance du modèle de paiement avec le transfert ISO20022 de destination**

Vous pouvez trouver ces configurations sur la page **Configurations** de la structure ER (**Administration de l’organisation** \> **Rapports électroniques** \> **Configurations**).

![Configurations importées sur la page Configurations.](./media/er-data-debugger-configurations.png)

Si l’une des configurations répertoriées précédemment manque dans l’arborescence de configuration, vous devez les télécharger manuellement à partir de la bibliothèque de ressources partagées LCS de la même manière que vous avez téléchargé le format de paiement ER **Transfert de crédit ISO20022**.

### <a name="analyze-the-downloaded-er-solution"></a>Analyser la solution ER téléchargée

#### <a name="review-the-model-mapping"></a>Examiner la mise en correspondance des modèles

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Modèle de paiement** \> **Mise en correspondance du modèle de paiement 1611**.
3. Sélectionnez **Concepteur**.
4. Sélectionnez l’enregistrement de mise en correspondance **Mise en correspondance du modèle de paiement ISO20022 CT**.
5. Sélectionnez **Concepteur**, puis passez en revue le mappage de modèle ouvert.

    Notez que le champ **Paiements** du modèle de données est lié à la source de données **\$notSentTransactions** qui renvoie la liste des lignes de paiement fournisseur en cours de traitement.

    ![Champ Paiements sur la page Concepteur de mise en correspondance des modèles.](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>Examiner la mise en correspondance des formats

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Modèle de paiement** \> **Transfert de crédit ISO20022**.
3. Sélectionnez **Concepteur**.
4. Sur l’onglet **Mise en correspondance**, passez en revue la mise en correspondance de formats qui est ouverte.

    Notez que l’élément **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** du fichier **ISO20022CTReports** \> **XMLHeader** est lié à la source de données **\$PaymentByDebtor** configurée pour regrouper les enregistrements du champ Modèles de données **Paiements**.

    ![Élément PmtInf sur la page Concepteur de format.](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>Examiner le format

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Modèle de paiement** \> **Transfert de crédit ISO20022**.
3. Sélectionnez **Concepteur**, puis passez en revue le format qui est ouvert.

    Notez que l’élément de format sous **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** est configuré pour saisir le code IBAN du compte fournisseur dans le fichier de paiement.

    ![Élément de format BankIBAN sur la page Concepteur de format.](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>Annexe 2 : Configurer le module Comptabilité fournisseur

### <a name="modify-a-vendor-property"></a>Modifier une propriété de fournisseur

1. Accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**.
2. Sélectionnez un fournisseur **DE-01002**, puis dans le volet Actions, sous l’onglet **Fournisseur**, dans le groupe **Paramétrer**, sélectionnez **Comptes bancaires**.
3. Dans le raccourci **Identification**, dans le champ **IBAN**, <a name="enteredIBANcode"></a>saisissez **GB33 BUKB 2020 1555 5555 55**.
4. Sélectionnez **Enregistrer**.

![Champ IBAN paramétré sur la page Comptes bancaires fournisseur.](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>Paramétrer un mode de paiement

1. Accédez à **Comptabilité fournisseur** \> **Paramétrage des paiements** \> **Modes de paiement**.
2. Sélectionnez le mode de paiement **SEPA CT**.
3. Dans le raccourci **Formats de fichier**, dans la section **Formats de fichier**, définissez l’option **Format d’exportation électronique générique** sur **Oui**.
4. Dans le champ **Exporter la configuration du format**, sélectionnez le champ ER **Transfert de crédit ISO20022**.
5. Sélectionnez **Enregistrer**.

![Paramètres des formats de fichier sur la page Modes de paiement.](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>Ajouter un paiement fournisseur

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Ajouter un journal des paiements.
3. Sélectionnez **Lignes** et ajoutez une nouvelle ligne de paiement.
4. Dans le champ **Compte**, sélectionnez le fournisseur **DE-01002**.
5. Dans le champ **Débit**, saisissez une valeur.
6. Dans le champ **Mode de paiement**, sélectionnez **SEPA CT**.
7. Sélectionnez **Enregistrer**.

![Paiement fournisseur ajouté sur la page Paiements fournisseur.](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>Annexe 3 : Traiter un paiement fournisseur

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements fournisseur**.
2. Sur la page **Journal de paiement fournisseur**, sélectionnez le journal des paiements que vous avez créé précédemment, puis sélectionnez **Lignes**.
3. Sélectionnez la ligne de paiement, puis sélectionnez **Statut de paiement** \> **Aucun(e)**.
4. Sélectionnez **Générer des paiements**.
5. Dans le champ **Mode de paiement**, sélectionnez **SEPA CT**.
6. Dans le champ **Compte bancaire**, sélectionnez **DEMF OPER**.
7. Dans la boîte de dialogue **Générer des paiements**, sélectionnez **OK**.
8. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
