---
title: Automatiser les tests avec la gestion des états électroniques
description: Cet article explique comment utiliser la fonctionnalité de base de la structure de génération d’états électroniques (ER) pour automatiser le test de certaines fonctionnalités.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: df2baa988bb634db11d819dd84ef73eaa560bab9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892767"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatiser les tests avec la gestion des états électroniques

[!include[banner](../includes/banner.md)]

Cet article explique comment utiliser la structure de génération d’états électroniques (ER) pour automatiser le test de certaines fonctionnalités. L’exemple de cet article montre comment automatiser le test du traitement des paiements fournisseur.

L’application utilise la structure ER pour générer les fichiers de paiement et les documents associés lors du traitement des paiements fournisseur. La structure ER se compose d’un modèle de données, de mises en correspondance de modèle et de composants de format qui prennent en charge le traitement des paiements pour différents types de paiements et la génération des documents dans différents formats. Ces composants peuvent être téléchargés à partir de Microsoft Dynamics Lifecycle Services (LCS) et importés dans l’instance.

Vous pouvez personnaliser chaque composant de Microsoft et l’utiliser comme base de votre propre composant personnalisé. En créant une version personnalisée, vous pouvez effectuer des modifications pour prendre en charge des besoins spécifiques. Par exemple, vous pouvez ajuster le modèle de données ER et la mise en correspondance de modèle ER pour accéder à des données spécifiques à un client d’application, ou vous pouvez modifier un format ER pour modifier la mise en page d’un document généré.

Vous pouvez utiliser les formats ER personnalisés pour traiter les fichiers de paiement qui génèrent les paiements fournisseur et également pour traiter les états de contrôle. Le contrôle de versions est pris en charge dans les composants d’états électroniques. Par conséquent, Microsoft peut fournir des versions mises à jour des solutions ER pour le traitement des paiements fournisseur, et vous pouvez automatiquement fusionner la version mise à jour avec votre composant personnalisé en refondant celui-ci. Toutefois, vous devez tester la version refondée pour vous assurer qu’elle fonctionne comme prévu.

Les modèles de données ER et les mises en correspondance de modèles ER sont communes à de nombreux formats ER utilisés pour traiter les paiements de différents types et générer les documents de paiement spécifiques à chaque région ou pays. Par conséquent, il est très souhaitable d’automatiser l’acceptation par les utilisateurs et les tests d’intégration de sorte à le faire automatiquement dans plusieurs sociétés, mais en prenant en compte le contexte national/régional de chaque société cible, en utilisant différents jeux de données, etc.

Pour plus d’informations sur la création d’une version personnalisée d’un format basé sur le format reçu d’un fournisseur de configuration, voir [ER Mettre à niveau votre format en adoptant la nouvelle version de base de ce format](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Concepts clés

Les utilisateurs expérimentés peuvent créer un test d’acceptation par les utilisateurs et d’intégration sans devoir écrire de code source.

- Utilisez la fonctionnalité de référence ER pour comparer les documents générés aux copies maîtres. Pour plus d’informations, voir [Suivre les résultats de rapport généré et les comparer avec des valeurs de référence](er-trace-reports-compare-baseline.md).
- Utilisez l’enregistreur de tâches pour enregistrer des scénarios de test, et inclure l’évaluation par rapport à la référence. Pour plus d’informations, voir [Ressources de l’enregistreur de tâches](../user-interface/task-recorder.md).
- Groupez les scénarios de test pour les scénarios de test requis. Pour plus d’informations, voir [Créer et automatiser les tests d’acceptation par les utilisateurs](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Utilisez le concepteur de processus d’entreprise (BPM) de LCS pour créer des bibliothèques pour les tests d’acceptation par les utilisateurs.
    - Utilisez des bibliothèque de test BPM pour créer un plan de test et des suites de test dans les services Microsoft Azure DevOps Services (Azure DevOps).

Les utilisateurs expérimentés peuvent exécuter des tests d’acceptation par les utilisateurs et d’intégration.

- Utilisez la suite RSAT (Regression Suite Automation Tool) pour exécuter des scénarios de test de la suite de tests souhaitée.
- Envoyez un rapport des résultats de test dans Azure DevOps, puis utilisez ce service pour examiner ces résultats.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir réaliser les tâches de cet article, vous devez remplir les conditions requises suivantes :

- Déployez une topologie qui prend en charge l’automatisation des tests. Vous devez avoir accès à l’instance de cette topologie pour le rôle **Administrateur système**. Cette topologie doit contenir les données de démonstration qui seront utilisées dans cet exemple. Pour plus d’informations, voir [Déployer et utiliser un environnement qui prend en charge l’élaboration continue et l’automatisation des tests](../perf-test/continuous-build-test-automation.md).
- Pour exécuter automatiquement les tests d’acceptation par les utilisateurs et d’intégration, vous devez installer RSAT dans la topologie que vous utilisez et le configurer de la manière appropriée. Pour plus d’informations sur l’installation et la configuration de RSAT pour qu’il fonctionne avec les applications de finances et d’opérations et Azure DevOps, voir [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Prêtez attention aux conditions préalables à l’utilisation de l’outil. L’illustration suivante montre un exemple des paramètres RSAT. Le rectangle bleu entoure les paramètres qui spécifient l’accès à Azure DevOps. Le rectangle vert entoure les paramètres qui spécifient l’accès à l’instance.

    ![Paramètres RSAT.](media/GER-Configure.png "Capture d’écran de la boîte de dialogue Paramètres RSAT")

- Pour organiser des scénarios de test en suites afin de garantir l’ordre correct d’exécution, de manière à pouvoir collecter les journaux des exécutions de test aux fins d’autres génération d’états et d’examen, vous devez accéder à Azure DevOps à partir de la topologie déployée.
- Pour réaliser l’exemple de cet article, nous vous recommandons de télécharger [Utilisation de la génération d’états électroniques pour les tests RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Ce fichier zip contient les guides de tâche suivants :

    | Contenu                                           | Nom et emplacement du fichier |
    |---------------------------------------------------|------------------------|
    | Exemple d’enregistrement de tâche pour préparer les données de test | Prepare\\Recording.xml |
    | Exemple d’enregistrement de tâche pour traiter les paiements fournisseur   | Process\\Recording.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Préparation du module Comptabilité fournisseur pour traiter les paiements fournisseur

1. Connectez-vous à votre instance.
2. Téléchargez les configurations de génération d’états électroniques suivantes depuis LCS. Pour plus d’instructions, voir [Importer une configuration ER à partir de Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md)

    - **Modèle de paiment** Configuration du modèle ER
    - **Mise en correspondance du modèle de paiement 1611** Configuration de la mise en correspondance du modèle ER
    - **BACS (UK)** Configuration de format ER

    ![Configurations de gestion des états électroniques.](media/GER-Configurations.png "Capture d’écran de la page Configurations dans la gestion des états électroniques")

3. Sélectionnez la société de démonstration **GBSI**, dont le contexte national/régional est celui de la Grande-Bretagne.
4. Configuration des paramètres de la comptabilité fournisseur :

    1. Accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Modes de paiement**.
    2. Sélectionnez le mode de paiement **Électronique**.
    3. Configurez le mode de paiement sélectionné afin qu’il utilise le format ER **BACS (UK)** que vous avez téléchargé précédemment pour le traitement des paiements fournisseur :

        1. Dans l’organisateur **Formats de fichier**, définissez l’option **Format d’exportation électronique générique** sur **Oui**.
        2. Dans le champ **Exporter la configuration du format**, sélectionnez **BACS (UK)**.

    ![Page des modes de paiement.](media/GER-APParameters.png "Capture d’écran de la page Modes de paiement")

    > [!NOTE]
    > Si vous avez la version dérivée de ce format ER créée pour prendre en charge les personnalisations, vous pouvez sélectionner cette configuration dans le mode de paiement **Électronique**.

5. Créez un exemple de paiement fournisseur :

    1. Accédez à **AComptabilité fournisseur \> Paiements \> Journal des paiements**.
    2. Assurez-vous que vous n’avez pas validé le journal des paiements.

        ![Page du journal des paiements.](media/GER-APJournal.png "Capture d’écran de la page Journal de paiement")

    3. Sélectionnez **Lignes**, puis entrez une ligne comportant les informations suivantes.

        | Champ               | Exemple de valeur   |
        |---------------------|-----------------|
        | Nom du fournisseur         | GB\_SI\_000001  |
        | Débit               | 1,000.00        |
        | Devise            | GBP             |
        | Type de compte de contrepartie | Banque            |
        | Compte de contrepartie      | GBSI OPER       |
        | Mode de paiement   | Électronique      |

    ![Page Paiements fournisseur.](media/GER-APJournalLines.png "Capture d’écran de la page Paiements fournisseur")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Préparer la structure ER pour tester le traitement des paiements fournisseur

### <a name="configure-er-parameters"></a>Configurer les paramètres ER

1. Accédez à **Administration d’organisation \> États électroniques \> Paramètres des états électroniques**.
2. Dans l’onglet **Pièces jointes**, dans le champ **Référence**, sélectionnez **Fichier** comme type de document utilisé par la structure DM (Gestion des documents) pour conserver les documents relatifs à la fonction de référence en tant que pièces jointes DM.

    ![Page Paramètres de la gestion des états électroniques.](media/GER-ERParameters.png "Capture d’écran de la page Paramètres de gestion des états électroniques")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Générer des copies de référence des documents relatifs aux paiements fournisseur

1. Accédez à **AComptabilité fournisseur \> Paiements \> Journal des paiements**.
2. Sélectionnez **Lignes**.
3. Sélectionnez **Générer des paiements**.
4. Sélectionnez le mode de paiement **Électronique**.
5. Sélectionnez le compte bancaire **GBSI OPER**.
6. Définissez l’option **Imprimer l’état de contrôle** sur **Oui**.
7. Téléchargez la sortie générée en tant que fichier zip.
8. Ouvrez le fichier téléchargé.
9. Extrayez les fichiers suivants du fichier téléchargé :

    - Fichier de paiement **Fichier** au format texte
    - État de contrôle **ERVendOutPaymControlReport** au format XLSX

    ![Fichiers extraits.](media/GER-APJournalProcessed.png "Capture d’écran des noms de fichiers extraits dans l’explorateur Windows")

### <a name="turn-on-the-er-baseline-feature"></a>Activation de la fonction de référence ER

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Dans le volet Actions, sous l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**.
3. Définissez l’option **Exécuter en mode débogage** sur **Oui**.

En activant le paramètre **Exécuter en mode débogage**, vous forcez la structure ER à exécuter les actions suivantes après l’exécution de n’importe quel format ER qui génère les documents sortants :

1. Déterminez si une référence a été configurée pour un des composants du format ER exécuté.
2. Déterminez si chaque référence configurée s’applique dans les conditions actuelles (code société de la société connectée, nom de fichier et extension du fichier résultant, etc.).
3. Pour chacune des références applicables, exécutez les actions suivantes :

    1. Comparez la sortie qui est générée lors de l’exécution du format ER avec la référence correspondante.
    2. Enregistrez le résultat de la comparaison dans le journal de débogage des configurations ER.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Configuration des références ER pour le traitement des paiements fournisseur

1. Accédez à **Administration d’organisation \> États électroniques \> Configurations**.
2. Sélectionnez **Références**.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Références**, sélectionnez le format **BACS (UK)**.
5. Sélectionnez **Pièces jointes**.
6. Ajoutez une nouvelle référence pour le fichier de paiement fournisseur :

    1. Sélectionnez **Nouveau**.
    2. Dans le champ **Type**, sélectionnez le type de document DM **Fichier** que vous avez configuré dans les paramètres ER pour enregistrer les artefacts de référence.
    3. Recherchez le fichier de paiement **Fichier** enregistré localement en format texte.
    4. Dans le champ **Description**, entrez **Fichier de paiement TXT**.

7. Ajoutez une nouvelle base de référence pour l’état de contrôle pour le paiement fournisseur :

    1. Sélectionnez **Nouveau**.
    2. Dans le champ **Type**, sélectionnez le type de document DM **Fichier** que vous avez configuré dans les paramètres ER pour enregistrer les artefacts de référence.
    3. Recherchez l’état de contrôle **ERVendOutPaymControlReport** enregistré localement en format XLSX.
    4. Dans le champ **Description**, entrez **État de contrôle de paiement XLSX**.

    ![Bases de référence pour l’état de contrôle et le fichier de paiement fournisseur.](media/GER-BaselineAttachments.png "Capture d’écran de la page Configurations avec l’état de contrôle de paiement XLSX sélectionné")

8. Fermez la page.
9. Dans l’organisateur **Bases de référence**, sélectionnez **Nouveau** pour configurer une base de référence pour le fichier de paiement :

    1. Nommez la ligne **Paramètre de référence pour le fichier de paiement**.
    2. Dans le champ **Nom du fichier de composant**, sélectionnez **fichier** pour appliquer cette base de référence au format ER de sortie qui génère le fichier de paiement au format texte BACS (UK).
    3. Dans le champ **Sociétés**, sélectionnez **GBSI** pour appliquer cette base de référence lors de l’exécution du format ER **BACS (UK)** sur la société de GBSI.
    4. Dans le champ **Masque de nom de fichier**, entrez **\*.TXT** pour n’appliquer cette base de référence qu’aux sorties du composant de format **fichier** ayant l’extension de nom de fichier **.txt**.
    5. Dans le champ **Base de référence**, sélectionnez **Fichier de paiement TXT** afin que cette base de référence soit utilisée pour comparaison avec la sortie générée.

10. Sélectionnez **Nouveau** pour configurer une base de référence pour l’état de contrôle :

    1. Nommez la ligne **Paramètre de référence pour l’état de contrôle**.
    2. Dans le champ **Nom du fichier de composant**, sélectionnez **ERVendOutPaymControlReport** pour appliquer cette base de référence au format ER de sortie qui génère l’état de contrôle.
    3. Dans le champ **Sociétés**, sélectionnez **GBSI** pour appliquer cette base de référence lors de l’exécution du format ER **BACS (UK)** sur la société de GBSI.
    4. Dans le champ **Masque de nom de fichier**, entrez **\*.XLSX** pour n’appliquer cette base de référence qu’aux sorties du composant de format **ERVendOutPaymControlReport** ayant l’extension de nom de fichier **.xlsx**.
    5. Dans le champ **Base de référence**, sélectionnez **État de contrôle de paiement XLSX** afin que cette base de référence soit utilisée pour comparaison avec la sortie générée.

    ![Organisateur Bases de référence sur la page Configurations.](media/GER-BaselineRules.png "Capture d’écran de l’organisateur Références de base dans la page Configurations")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Enregistrement des tests pour valider le traitement des paiements fournisseur

En tant qu’utilisateur expérimenté, vous pouvez enregistrer vos propres étapes pour tester le traitement des paiements fournisseur. Nous vous recommandons de lire (et modifier, le cas échéant) l’enregistrement de tâche **Prepare\\Recording.xml** que vous avez téléchargé précédemment. Cet enregistrement permet de définir toutes les données de test à l’état correct. Cette étape est obligatoire car le test peut être effectué plusieurs fois, et chaque test doit utiliser les données dans le même état.

### <a name="reset-user-settings"></a>Réinitialiser les paramètres utilisateur

1. Ouvrez le tableau de bord par défaut.
2. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage).
3. Sélectionnez **Options utilisateur**.
4. Sélectionnez **Données d’utilisation**.
5. Sélectionnez **Réinitialiser**.
6. Sélectionnez **Oui** pour confirmer que vous souhaitez réinitialiser les données d’utilisation.
7. Fermez la page.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Enregistrement des étapes de préparation des données de test

1. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage).
2. Sélectionnez **Enregistreur de tâches**.
3. Sélectionnez **Lire l’enregistrement**.
4. Sélectionnez **Ouvrir à partir de ce PC**.
5. Sélectionnez **Parcourir**, puis sélectionnez le fichier **Prepare\\Recording.xml** enregistré localement.
6. Sélectionnez **Démarrer**.
7. Continuez de sélectionner **Lire l’étape en attente suivante** jusqu’à ce que toutes les étapes de l’enregistrement aient été lues.

Cet enregistrement de tâche exécute les actions suivantes :

1. Définissez le statut de la ligne de paiement traitée sur **Aucun**.

    ![Enregistrement de tâche, étapes 3 à 4.](media/GER-Recording1Review1.png "Capture d’écran de l’enregistrement de tâche, étapes 3 à 4")

2. Activez le paramètre utilisateur ER **Exécuter en mode débogage**.

    ![Enregistrement de tâche, étapes 9 à 10.](media/GER-Recording1Review2.png "Capture d’écran de l’enregistrement de tâche, étapes 9 à 10")

3. Nettoyez le journal de débogage ER contenant les résultats de la comparaison des fichiers générés aux bases de référence.

    ![Enregistrement de tâche, étapes 13 à 15.](media/GER-Recording1Review3.png "Capture d’écran de l’enregistrement de tâche, étapes 13 à 15")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Enregistrement des étapes pour tester le traitement des paiements fournisseur

Nous vous recommandons de lire (et modifier, le cas échéant) l’enregistrement de tâche **Process\\Recording.xml** que vous avez téléchargé précédemment. Cet enregistrement est utilisé pour traiter les paiements fournisseur et valider les résultats de la comparaison des documents générés aux bases de référence correspondantes.

1. Sélectionnez le bouton **Paramètres** (le symbole d’engrenage).
2. Sélectionnez **Enregistreur de tâches**.
3. Sélectionnez **Lire l’enregistrement**.
4. Sélectionnez **Ouvrir à partir de ce PC**.
5. Sélectionnez **Parcourir**, puis sélectionnez le fichier **Process\\Recording.xml** enregistré localement.
6. Sélectionnez **Démarrer**.
7. Continuez de sélectionner **Lire l’étape en attente suivante** jusqu’à ce que toutes les étapes de l’enregistrement aient été lues.

Cet enregistrement de tâche exécute les actions suivantes :

1. Démarrez le traitement des paiements fournisseur.
2. Sélectionnez les paramètres d’exécution appropriés, puis activez la génération d’un état de contrôle.

    ![Enregistrement de tâche, étapes 3 à 8.](media/GER-Recording2Review1.png "Capture d’écran de l’enregistrement de tâche, étapes 3 à 8")

3. Accédez au journal de débogage ER pour enregistrer les résultats de la comparaison des fichiers de sortie aux bases de référence correspondantes.

    Dans le journal de débogage ER, les résultats de la comparaison apparaissent dans le champ **Texte généré**. Les champs **Composant de format** et **Chemin du format ayant provoqué une entrée de journal** font référence au composant de fichier pour lequel la sortie générée a été comparée à la base de référence.

    ![Entrées sur la page Journaux d’exécution de la gestion des états électroniques.](media/GER-ERDebugLog.png "Capture d’écran des entrées sur la page Journaux d’exécution de la gestion des états électroniques")

4. La comparaison de la sortie actuelle à la base de référence est enregistrée à l’aide de l’option **Valider** de l’enregistreur de tâches, en sélectionnant **Valeur actuelle**.

    ![Utilisation de l’option Valider pour comparaison avec la valeur actuelle.](media/GER-TRRecordValidation.png "Capture d’écran de l’utilisation de l’option Valider pour comparaison avec la valeur actuelle")

    L’illustration suivante présente l’aspect des étapes de validation enregistrées dans l’enregistrement de tâche.

    ![Enregistrement de tâche, étapes 13 et 15.](media/GER-Recording2Review2.png "Capture d’écran de l’enregistrement de tâche, étapes 13 et 15")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Ajout des tests enregistrés à Azure DevOps

1. Ouvrez l’environnement Azure DevOps.
2. Sélectionnez le projet que vous avez défini dans les paramètres RSAT lorsque vous avez [configuré l’outil](#prerequisites).
3. Sélectionnez le plan de test que vous avez défini dans les paramètres RSAT lorsque vous avez [configuré l’outil](#prerequisites).
4. Créez un scénario de test pour le plan de test sélectionné :

    1. Nommez le scénario de test **Préparation des données pour tester le traitement des paiements fournisseur électroniques**.
    2. Associez le fichier **Recording.xml** du dossier **Prepare** que vous avez téléchargé précédemment.

5. Créez un scénario de test pour le plan de test sélectionné :

    1. Nommez le scénario de test **Test du traitement des paiements fournisseur à l’aide du format ER BACS (UK)**.
    2. Associez le fichier **Recording.xml** du dossier **Process** que vous avez téléchargé précédemment.

    ![Nouveaux scénarios de test pour le plan de test sélectionné.](media/GER-RSAT-DevOps-Tests-Passed.png "Capture d’écran des nouveaux scénarios de test pour le plan de test sélectionné")

> [!NOTE]
> Prêtez attention à l’ordre d’exécution correct des tests qui sont ajoutés.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Préparation de RSAT pour l’exécution des tests enregistrés

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Chargement des tests d’Azure DevOps vers RSAT

1. Ouvrez l’application locale RSAT dans la topologie actuelle.
2. Sélectionnez **Charger** pour charger les tests qui résident actuellement dans Azure DevOps dans RSAT.

    ![Tests chargés dans RSAT.](media/GER-RSAT-RSAT-Tests-Loaded.png "Capture d’écran des tests chargés dans RSAT")

### <a name="create-automation-and-parameters-files"></a>Créer des fichiers de paramètres et d’automatisation

1. Dans RSAT, sélectionnez les tests que vous avez chargés à partir d’Azure DevOps.
2. Sélectionnez **Nouveau** pour créer des fichiers de paramètres et d’automatisation.

    ![Fichiers de paramètres et d’automatisation RSAT créés dans RSAT.](media/GER-RSAT-RSAT-Tests-Initiated.png "Capture d’écran des fichiers de paramètres et d’automatisation RSAT créés dans RSAT")

### <a name="modify-the-parameters-files"></a>Modification des fichiers de paramètres

1. Dans RSAT, sélectionnez le scénario de test **Préparation des données pour tester le traitement des paiements fournisseur électroniques**.
2. Sélectionnez **Modifier**.
3. Dans le classeur Microsoft Excel qui est ouvert, sur la feuille de calcul **Général**, modifiez le code société en **GBSI**, car cette société est utilisée pour l’exécution du test.
4. Dans RSAT, sélectionnez le scénario de test **Test du traitement des paiements fournisseur à l’aide du format ER BACS (UK)**.
5. Sélectionnez **Modifier**.
6. Dans le classeur Excel qui est ouvert, sur la feuille de calcul **Général**, modifiez le code société en **GBSI**.
7. Dans la feuille de calcul **ERFormatMappingRunLogTable**, remarquez que les cellules A:3 et C : 3 contiennent le texte des champs de la table du journal de débogage ER utilisés pour valider les résultats de la comparaison de la sortie par rapport à la base de référence. Ces textes seront utilisés pour évaluer les enregistrements du journal de débogage ER créés lors de l’exécution du test.

    ![Feuille de calcul ERFormatMappingRunLogTable.](media/GER-RSAT-RSAT-ExcelParameters.png "Capture d’écran de la feuille de calcul ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Exécution des tests et analyse des résultats

### <a name="run-the-tests-in-rsat"></a>Exécution des tests dans RSAT

1. Dans RSAT, sélectionnez les tests chargés.
2. Sélectionnez **Exécuter**.

Notez que les scénarios de test sont automatiquement exécutés dans l’application à l’aide d’un navigateur Web.

### <a name="analyze-the-results-of-test-execution"></a>Analyse des résultats de l’exécution du test

Les résultats de l’exécution de tests sont stockés dans RSAT. Notez que les deux tests ont été réussis.

![Tests réussis dans RSAT.](media/GER-RSAT-RSAT-Tests-Passed.png "Capture d’écran de tests qui réussis dans RSAT")

Notez que les résultats de l’exécution des tests sont également envoyés à Azure DevOps aux fins d’analyse approfondie.

![Résultats de l’exécution du test dans Azure DevOps.](media/GER-RSAT-DevOps-Tests-Added.png "Capture d’écran des résultats de l’exécution du test dans Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Simuler une situation d’échec du test

Cette suite de tests doit échouer quand au moins une des sorties générées ne concorde pas avec la base de référence correspondance. Pour atteindre cette situation, vous pouvez utiliser votre version dérivée du format **BACS (UK)** pour générer un fichier de paiement au contenu différent de la base de référence correspondante. Pour simuler ce cas, vous pouvez utiliser le même format **BACS (UK)** mais modifier le montant du paiement de la ligne de paiement traitée.

1. Ouvrez l’application et accédez à **Comptabilité fournisseur \> Paiements \> Journal des paiements**.
2. Sélectionnez **Lignes**.
3. Sélectionnez la ligne de paiement, puis sélectionnez **Statut du paiement \> Aucun(e)**.
4. Dans le champ **Débit** changez la valeur de **1 000,00** à **2 000,00**.
5. Sélectionnez **Enregistrer** pour enregistrer les modifications.

### <a name="run-the-tests-in-rsat"></a>Exécution des tests dans RSAT

1. Dans RSAT, sélectionnez les tests chargés.
2. Sélectionnez **Exécuter**.

Notez que les scénarios de test sont automatiquement exécutés dans l’application à l’aide d’un navigateur Web.

### <a name="analyze-the-results-of-test-execution"></a>Analyse des résultats de l’exécution du test

Les résultats de l’exécution de tests sont stockés dans RSAT. Notez que le deuxième test a échoué lors de la deuxième exécution.

![Résultats de l’échec du test dans RSAT.](media/GER-RSAT-RSAT-Tests-Failed.png "Capture d’écran des résultats de l’échec de test dans RSAT")

Notez que les résultats de l’exécution des tests sont également envoyés à Azure DevOps aux fins d’analyse approfondie.

![Résultats de l’échec du test dans Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed.png "Capture d’écran des résultats de l’échec de test dans Azure DevOps")

Vous pouvez accéder au statut de chaque test. Vous pouvez également accéder au journal d’exécution afin d’analyser les motifs de l’échec. Dans l’illustration suivante, le journal d’exécution indique que l’échec s’est produit en raison de la différence de contenu entre le fichier de paiement généré et sa base de référence.

![Journal d’exécution pour analyser l’échec dans Azure DevOps.](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Capture d’écran du journal d’exécution pour analyser l’échec dans Azure DevOps")

Par conséquent, comme vous avez vu, il est possible d’évaluer le fonctionnement de n’importe quel format ER à l’aide de RSAT comme plateforme de test et des scénarios de test fondés sur l’enregistreur de tâches qui utilisent la fonction de base de référence.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Ressources de l’enregistreur de tâches](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Créer et automatiser les tests d’acceptation par l’utilisateur](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Déployer et utiliser un environnement qui prend charge l’élaboration continue et l’automatisation des tests](../perf-test/continuous-build-test-automation.md)
- [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md)
- [ER Mettre à niveau votre format en adoptant la nouvelle version de base de ce format](tasks/er-upgrade-format.md)
- [ER Charger une configuration à partir de Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]