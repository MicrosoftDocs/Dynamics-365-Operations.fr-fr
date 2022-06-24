---
title: Suivre les résultats de l’état généré et les comparer aux valeurs de base
description: Cet article explique comment comparer les résultats des états ER générés avec des valeurs d’état de référence.
author: NickSelin
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 168060f6dee7420a496e06cc3a85f5b10239c2cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847370"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Suivre les résultats de rapport généré et les comparer avec des valeurs de base

[!include[banner](../includes/banner.md)]

Vous pouvez suivre les résultats des formats de génération d’états électroniques (ER) qui génèrent les documents électroniques sortants. Lorsque la génération du suivi est activée (à l’aide du paramètre utilisateur ER **Exécuter en mode débogage**), un nouvel enregistrement de suivi est généré dans le journal d’exécution du format ER chaque fois qu’un état ER est exécuté. Les détails suivants sont enregistrés dans chaque suivi généré :

- Tous les avertissements générés par les règles de validation
- Toutes les erreurs générées par les règles de validation
- Tous les fichiers générés qui sont enregistrés en tant que pièces jointes de l’enregistrement de suivi

Vous pouvez enregistrer plusieurs fichiers d’application de base pour un format ER. Les fichiers sont considérés comme des fichiers de base lorsqu’ils décrivent les résultats attendus des états exécutés. Si un fichier de référence est disponible pour un format ER qui a été exécuté alors que la génération du suivi a été activée, le suivi enregistre, en plus des détails mentionnés précédemment, le résultat de la comparaison du document électronique généré avec le fichier de référence. En un clic, vous pouvez également obtenir le document électronique généré et son fichier de base dans un fichier zip unique. Vous pouvez ensuite effectuer une comparaison détaillée à l’aide d’un outil externe tel que WinDiff.

Vous pouvez évaluer le suivi pour analyser si les documents électroniques générés comprennent le contenu attendu. Vous pouvez effectuer cette évaluation dans un environnement de test d’acceptation par l’utilisateur (UAT) lorsque la base du code a été modifiée (par exemple, lorsque vous avez migré vers une nouvelle instance de l’application, installé des correctifs logiciels ou déployé des modifications du code). De cette manière, vous pouvez vérifier que l’évaluation n’affecte pas l’exécution des états ER utilisés. Pour la plupart des états ER, l’évaluation peut être effectuée en mode sans assistance.

Pour plus d’informations sur cette fonction, lisez les guides de tâches **ER Générer des états et comparer les résultats (partie 1)** et **ER Générer des états et comparer les résultats (partie 2)**, qui font partie du processus d’entreprise **7.5.4.3 Tester les solutions/services informatiques (10679)** et qui peuvent être téléchargés à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Ces guides de tâches vous guident tout au long du processus de configuration de la structure ER pour utiliser les fichiers de base pour évaluer les documents électroniques générés.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Exemple : suivre les résultats de rapport généré et les comparer avec des valeurs de référence

Cette procédure explique comment configurer la structure ER pour collecter des informations sur les exécutions de format ER, puis pour évaluer les résultats de ces exécutions. Dans le cadre de cette évaluation, les documents générés sont comparés à leurs fichiers de référence. Dans cet exemple, vous créerez les configurations ER requises pour la société fictive, Litware, Inc. Cette procédure est destinée aux utilisateurs auxquels le rôle Administrateur système ou Développeur d’états électroniques a été affecté. Ces étapes peuvent être effectuées à l’aide d’un ensemble de données quelconque.

Pour effectuer les étapes de cet exemple, vous devez commencer par effectuer les étapes de la rubrique, [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, vérifiez que le fournisseur de configuration pour l’exemple de société Litware, Inc. est répertorié, et qu’il est marqué comme **Actif**. Si ce fournisseur de configuration ne s’affiche pas, suivez les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Configurer les paramètres de gestion des documents

1. Accédez à **Administration d’organisation** \> **Gestion des documents** \> **Types de documents**, puis créez un nouveau type de document pour stocker les fichiers de référence.
2. Dans le champ **Classe**, entrez **Fichier joint**.
3. Dans le champ **Groupe**, entrez **Fichier**.

![Page Types de documents.](media/GER-BaselineSample-SetupDocumentType.PNG "Capture d’écran de la page de types de document")

> [!NOTE]
> Un nouveau type de document portant le même nom doit être configuré pour chaque ensemble de données pour lequel vous prévoyez d’utiliser la fonction de référence d’ER.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Configurer les paramètres ER pour commencer à utiliser la fonction de référence

1. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.

    ![Espace de travail des états électroniques.](media/GER-BaselineSample-ERWorkspace.PNG "Capture d’écran de l’espace de travail de gestion des états électroniques")

2. Dans l’onglet **Pièces jointes**, dans le champ **Base de référence**, entrez ou sélectionnez le type de document que vous venez de créer.

    ![Onglet Pièces jointes de la page Paramètres de gestion des états électroniques.](media/GER-BaselineSample-ERParameters.PNG "Capture d’écran des Paramètres de gestion des états électroniques")

3. Sélectionnez **Enregistrer**, puis fermez la page **Paramètres de la génération d’états électroniques**.

### <a name="add-a-new-er-model-configuration"></a>Ajouter une nouvelle configuration du modèle ER

1. Dans l’espace de travail **Génération des états électroniques**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
2. Dans le volet Actions, sélectionnez **Créer une configuration**.
3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, tapez **Modèle d’apprentissage des références ER**.
4. Sélectionnez **Créer une configuration** pour confirmer la création d’une nouvelle entrée de modèle de données ER.

![Boîte de dialogue Créer une configuration, ajouter une nouvelle configuration de modèle ER.](media/GER-BaselineSample-ModelAdd.PNG "Capture d’écran de la boîte de dialogue de menu déroulant Créer une configuration")

### <a name="design-a-data-model"></a>Élaborer un modèle de données

1. Dans la page **Configurations**, dans le volet Action, sélectionnez **Concepteur**.
2. Sélectionnez **Nouveau**.
3. Dans la boîte de dialogue déroulante, dans le champ **Nom**, enrez **Racine**.
4. Sélectionnez **Ajouter**.
5. Sélectionnez **Référence racine**.
6. Sélectionnez **OK**, puis sélectionnez **Enregistrer**.
7. Fermez la page **Concepteur de modèle**.
8. Sélectionnez **Modifier le statut**.
9. Sélectionnez **Terminer**, puis sélectionnez **OK**.

![Page Configurations.](media/GER-BaselineSample-ModelComplete.PNG "Capture d’écran de la page Configurations")

### <a name="add-a-new-er-format-configuration"></a>Ajouter une nouvelle configuration du format ER

1. Dans la page **Configurations**, dans le volet Action, sélectionnez **Créer une configuration**.
2. Dans la boîte de dialogue déroulante, dans le groupe de champs **Nouveau**, sélectionnez l’option **Format basé sur le modèle de données Modèle d’apprentissage des références ER**.
3. Dans le champ **Nom**, entrez **Format pour l’apprentissage des références ER**.
4. Sélectionnez **Créer une configuration** pour confirmer la création d’une nouvelle entrée de format ER.

![Boîte de dialogue Créer une configuration, ajouter une nouvelle configuration de format ER.](media/GER-BaselineSample-FormatAdd.PNG "Capture d’écran de la boîte de dialogue de menu déroulant Créer une configuration")

### <a name="design-a-format"></a>Concevoir un format

Pour cet exemple, vous allez créer un format ER simple pour générer des documents XML.

1. Dans la page **Configurations**, dans le volet Action, sélectionnez **Concepteur**.
2. Sélectionnez **Ajoutez racine**.
3. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **Common\\File**.
    2. Dans le champ **Nom**, entrez **Production**.
    3. Cliquez sur **OK**.

4. Sélectionnez **Ajouter**.
5. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **XML\\Element**.
    2. Dans le champ **Nom**, entrez **Document**.
    3. Cliquez sur **OK**.

6. Dans l’arborescence, sélectionnez **Résultat\\Document**.
7. Sélectionnez **Ajouter**.
8. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **XML\\Attribute**.
    2. Dans le champ **Nom**, entrez **Identifiant**.
    3. Cliquez sur **OK**.

    ![Page du concepteur de format, attribut XML sélectionné dans l’arborescence.](media/GER-BaselineSample-FormatLayoutDesign.PNG "Capture d’écran de la page Concepteur de format")

9. Dans l’onglet **Mise en correspondance**, sélectionnez **Supprimer**.
10. Sélectionnez **Ajoutez racine**.
11. Dans la boîte de dialogue déroulante, dans l’arborescence, sélectionnez **Général\\Paramètres d’entrée utilisateur**, puis procédez comme suit :

    1. Dans le champ **Nom**, entrez **Identifiant**.
    2. Dans le champ **Étiquette**, entrez **Entrer l’identifiant**.
    3. Cliquez sur **OK**.

12. Dans l’arborescence, sélectionnez **Résultat\\Document\\Id**.
13. Sélectionnez **Lier**, puis sélectionnez **Enregistrer**.

![Page de concepteur de format, onglet Mappage.](media/GER-BaselineSample-FormatMappingDesign.PNG "Capture d’écran de la page Concepteur de format")

Selon la structure conçue, le format configuré génère un fichier XML. Ce fichier XML contient l’élément **Racine** qui a l’attribut **ID** défini sur la valeur que l’utilisateur entre dans la boîte de dialogue de l’exécution ER.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Générer un nouveau fichier de base de référence pour un format ER conçu

1. Dans la page **Configurations**, sous l’organisateur **Versions**, sélectionnez **Exécuter**.
2. Dans le champ **Entrer l’identifiant**, entrez **1**.
3. Cliquez sur **OK**.

    ![Boîte de dialogue Paramètres de génération d’états électroniques.](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Capture d’écran de la boîte de dialogue Paramètres de gestion des états électroniques")

4. Enregistrez une copie locale du fichier **out.Admin.xml** qui est généré, afin de pouvoir l’utiliser ultérieurement comme base de référence de ce format ER.

    ![Notification concernant le fichier généré dans la page Configurations.](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Capture d’écran de la notification concernant le fichier généré dans la page Configurations")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Configurer les paramètres ER pour utiliser la fonction de référence

1. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**.
2. Définissez l’option **Exécuter en mode débogage** sur **Oui**.
3. Cliquez sur **OK**.

![Boîte de dialogue Paramètres utilisateur.](media/GER-BaselineSample-ERUserParameters.PNG "Capture d’écran de la boîte de dialogue Paramètres de l’utilisateur")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Ajouter une nouvelle base de référence pour un format ER conçu

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans le volet Actions, sélectionnez **Bases de référence**.

    ![Bouton Bases de référence sur la page Configurations.](media/GER-BaselineSample-OpenBaselinePage.PNG "Capture d’écran du bouton Références de base dans la page Configurations")

3. Dans le volet Actions, sélectionnez **Nouveau**.
4. Sélectionnez le format ER **Format pour l’apprentissage des références ER** que vous avez conçu précédemment.
5. Sélectionnez **Enregistrer**.

![Page Références de base du format de gestion des états électroniques.](media/GER-BaselineSample-AddBaseline.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")

La base de référence est ajoutée au format **Format pour l’apprentissage des références ER**.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Configurer une règle de référence pour la référence ajoutée

1. Dans la page **Références de format de la génération d’états électroniques**, dans le volet Actions, sélectionnez le bouton **Pièces jointes** (le symbole de trombone).
2. Dans le volet Actions, sélectionnez **Nouveau** \> **Fichier**. Dans les paramètres ER, le type de document **Fichier** doit avoir été précédemment sélectionné comme type de document utilisé pour enregistrer les fichiers de base de référence.
3. Sélectionnez **Parcourir**, puis sélectionnez le fichier **out.Admin.xml** qui a été généré lorsque vous avez effectué le format ER configuré précédemment.

    ![Page Pièces jointes.](media/GER-BaselineSample-UploadBaselineFile.PNG "Capture d’écran de la page Pièces jointes")

4. Fermez la page **Pièces jointes**.
5. Dans l’organisateur **Bases de référence**, sélectionnez **Nouveau**.
6. Dans le champ **Nom**, entrez **Base de référence 1**.
7. Dans le champ **Nom du composant de fichier**, entrez ou sélectionnez **Résultat**. Cette valeur indique que la base de référence configurée sera comparée à un fichier généré à l’aide de l’élément de format **Résultat**.
8. Dans le champ **Masque du nom de fichier**, entrez **\*.xml**.

    > [!NOTE]
    > Vous pouvez définir le masque du nom de fichier. Lorsque le masque du nom de fichier est défini, l’enregistrement de la base de référence sera utilisé pour évaluer la sortie générée uniquement lorsque le nom du fichier de sortie généré correspond au masque.

9. Si la base de référence configurée ne doit être utilisée que lorsque le format ER **Format pour l’apprentissage des références ER** est exécuté par des utilisateurs connectés dans des sociétés spécifiques, sélectionnez celles-ci dans le champ **Sociétés**.
10. Dans le champ **Base de référence**, entrez ou sélectionnez la pièce jointe **out.Admin**.
11. Sélectionnez **Enregistrer**.

![Références de base de la gestion des états électroniques, Raccourci Bases de références avec une base sélectionnée.](media/GER-BaselineSample-SetupBaselineLine.PNG "Capture d’écran de la page Références de base de la gestion des états électroniques")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Exécutez le format ER conçu et consultez le journal pour analyser les résultats

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans l’arborescence, développez **Modèle d’apprentissage des références ER**, puis sélectionnez **Modèle d’apprentissage des références ER\\Format pour l’apprentissage des références ER**.
3. Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
4. Dans le champ **Entrer l’identifiant**, entrez **1**.
5. Cliquez sur **OK**.
6. Accédez à **Administration d’organisation** \> **États électroniques** \> **Journaux de débogage des configurations**.

    ![Page des journaux d’exécution de rapports électroniques, avec des lignes de base égales.](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Capture d’écran de la page Journaux d’exécution de la gestion des états électroniques")

    > [!NOTE]
    > Le journal d’exécution contient des informations sur le résultat de la comparaison du fichier généré avec la base de référence configurée. Dans cet exemple, le journal indique que le fichier généré et la base de référence sont égaux.

7. Sélectionnez **Supprimer tout**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Exécutez le format ER conçu et consultez le journal pour analyser les résultats

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans l’arborescence, développez **Modèle d’apprentissage des références ER**, puis sélectionnez **Modèle d’apprentissage des références ER\\Format pour l’apprentissage des références ER**.
3. Dans l’organisateur **Versions**, sélectionnez **Exécuter**.
4. Dans le champ **Entrer l’identifiant**, entrez **2**.
5. Cliquez sur **OK**.
6. Accédez à **Administration d’organisation** \> **États électroniques** \> **Journaux de débogage des configurations**.

    ![Page des journaux d’exécution de rapports électroniques, avec des lignes de base différentes.](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Capture d’écran de la page Journaux d’exécution de la gestion des états électroniques")

    > [!NOTE]
    > Le journal d’exécution contient des informations sur le résultat de la comparaison du fichier généré avec la base de référence configurée. Dans cet exemple, le journal indique que le fichier généré et la base de référence sont différents.

7. Sélectionnez **Comparer**.

> [!NOTE]
> Le fichier généré et le fichier de base de référence sont présentés dans un fichier zip. Vous pouvez utiliser des outils externes de comparaison tels que WinDiff pour comparer les fichiers et examiner les différences.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
