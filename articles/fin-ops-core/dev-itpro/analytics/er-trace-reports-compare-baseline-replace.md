---
title: Améliorations des résultats de suivi des rapports de gestion des états électroniques générés et comparaisons avec les valeurs de référence
description: Cette rubrique fournit des informations sur l'utilisation de la fonction de référence ER, améliorée dans la version Microsoft Dynamics 365 for Finance and Operations 10.0.3 (juin 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: a260be0f8659106907b26bf69bee3b33b09d0c24
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181333"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Améliorations des résultats de suivi des rapports de gestion des états électroniques générés et comparaisons avec les valeurs de référence

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le premier ensemble d'améliorations apportées à la fonction de référence de la structure de génération d'états électroniques (ER). Ces améliorations sont disponibles dans Microsoft Dynamics 365 for Finance and Operations 10.0.3 (juin 2019) et les versions ultérieures.

## <a name="automate-the-setting-of-baseline-rules"></a>Automatisation du paramétrage des règles de référence

La rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md) explique comment configurer la structure ER pour collecter les informations sur les exécutions de format ER et évaluer les résultats de ces exécutions. L'exemple de cette rubrique présente les étapes à accomplir.

En voici quelques-unes :

- Exécutez un format ER pour générer un fichier de sortie, et enregistrez le fichier localement.
- Ajoutez le fichier enregistré localement comme pièce jointe à la référence ajoutée à un format ER.
- Configurez la règle de référence pour la référence ajoutée. Cette configuration inclut les étapes suivantes :

    - Spécifiez un élément de format ER utilisé pour générer un fichier de sortie.
    - Sélectionnez la pièce jointe qui renvoie au fichier de sortie généré.

> [!NOTE]
> Ces étapes doivent être effectuées manuellement, même si les fonctionnalités ER permettent de les automatiser. Pour en savoir plus sur cette fonction, réalisez l'exemple suivant.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Exemple : Automatisation du paramétrage des règles de référence

Pour accomplir les étapes de cet exemple, vous devez d'abord réaliser les étapes de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md), jusqu'à la section « Ajouter une nouvelle référence à un format ER défini ».

### <a name="review-added-baseline"></a>Examiner la référence ajoutée

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Références**.

    > [!NOTE]
    > Le bouton **Références** du volet Actions n'est disponible que lorsque le paramètre utilisateur ER **Exécuter en mode de débogage** est activé pour la société en cours.

La référence a été ajoutée pour le format **Format pour l'apprentissage des références ER** sélectionné, mais les règles de la référence n'ont pas encore été ajoutées à celle-ci.

![Page des références de format de la génération d'états électroniques](media/GER-BaselineSample-AddBaseline2.PNG "Capture d'écran de la page des références de format de la génération d'états électroniques")

### <a name="make-a-new-baseline-rule"></a>Établir une nouvelle règle de référence

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Dans l'arborescence, développez **Modèle d'apprentissage des références ER**.
3. Dans l'arborescence, sélectionnez **Modèle d'apprentissage des références ER\\Format pour l'apprentissage des références ER**.
4. Dans l'organisateur **Versions**, sélectionnez **Exécuter**.
5. Dans le champ **Entrer l'identifiant**, entrez **1**.
6. Définissez l'option **Créer des fichiers de référence** sur **Oui**.
7. Cliquez sur **OK**.

    ![Boîte de dialogue Paramètres de la génération d'états électroniques](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Capture d'écran de la boîte de dialogue Paramètres de la génération d'états électroniques")

8. Sélectionnez **Références**.

    ![Page des références de format de la génération d'états électroniques](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Capture d'écran de la page des références de format de la génération d'états électroniques")

    Le fichier de sortie généré a été associé automatiquement à la référence du format ER exécuté. La règle de référence a été ajoutée automatiquement à cette référence. Elle contient également la référence au fichier joint.

9. Dans le champ **Nom**, entrez **Base de référence 1**.
10. Dans le champ **Masque du nom de fichier**, entrez **.xml**.
11. Sélectionnez **Enregistrer**.

### <a name="run-the-format"></a>Exécuter le format

Vous êtes maintenant prêt à accomplir les étapes restantes de l'exemple de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md), en commençant par la section « Exécuter le format ER défini et examiner le fichier journal pour analyser les résultats ».

> [!NOTE]
> Lorsque vous supprimez la règle de référence automatiquement ajoutée dans l'organisateur **Références**, la pièce jointe référencée n'est pas automatiquement supprimée.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Configurez la référence de sorte qu'elle ignore les éléments qui changent en permanence de la sortie ER.

Lorsqu'un format ER a été conçu pour contenir des informations qui changent lors de l'exécution du format, celui-ci doit utiliser la fonction de référence ER pour comparer les résultats obtenus avec les valeurs de référence. Par exemple, les informations peuvent être la date et l'heure du traitement, ou l'identificateur unique d'un document généré dans différents formats (identificateur global unique \[GUID\], etc.). Les nouvelles fonctionnalités ER permettent de configurer la règle de référence de manière à ce qu'elle ignore les éléments variables d'un format ER lorsque le format est exécuté dans le but de comparer les valeurs de référence avec celles de l'exécution du format. Pour en savoir plus sur cette fonction, réalisez l'exemple suivant.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Exemple : Configurer la référence de sorte qu'elle ignore les éléments qui changent en permanence de la sortie ER.

Pour accomplir les étapes de cet exemple, vous devez d'abord réaliser les étapes de la rubrique [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Modifier un format ER configuré

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Dans l'arborescence, développez **Modèle d'apprentissage des références ER**.
3. Dans l'arborescence, sélectionnez **Modèle d'apprentissage des références ER\\Format pour l'apprentissage des références ER**.
4. Sélectionnez **Concepteur**.
5. Dans l'arborescence, sélectionnez **Résultat\\Document**.
6. Sélectionnez **Ajouter**.
7. Dans la boîte de dialogue déroulante, dans l'arborescence, sélectionnez **XML\\Attribut**.
8. Dans le champ **Nom**, entrez **ProcessingDateTime**.
9. Cliquez sur **OK**.
10. Dans l'onglet **Mise en correspondance**, dans l'arborescence, sélectionnez **Résultat\\Document\\ProcessingDateTime**.
11. Sélectionnez **Modifier la formule**.
12. Dans le champ **Formule**, entrez l'expression suivante : **DATETIMEFORMAT(NOW(), "O")**
13. Sélectionnez **Enregistrer**, puis sélectionnez **Test**.
14. Sélectionnez **Test** de nouveau pour tester à nouveau l'expression configurée.

    ![Page du concepteur de formule](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Capture d'écran de la page du concepteur de formule")

    > [!NOTE]
    > L'onglet **Résultat du test** indique que l'expression configurée retourne une valeur différente de date et d'heure chaque fois qu'elle a été appelée.

15. Fermez la page du **Concepteur de formule**, puis sélectionnez **Enregistrer**.

    ![Page du concepteur de format](media/GER-BaselineSample-FormatMappingDesign2.PNG "Capture d'écran de la page du concepteur de format")

16. Fermez la page **Concepteur de format**.

### <a name="remove-an-existing-baseline-rule"></a>Supprimer une règle de référence existante

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Références**.
3. Dans la liste des références, sélectionnez celle qui a été configurée pour le format **Format pour l'apprentissage des références ER**.
4. Dans l'organisateur **Références**, sélectionnez **Supprimer** pour supprimer la règle de référence que vous avez définie précédemment.

![Page des références de format de la génération d'états électroniques](media/GER-BaselineSample-AddBaseline3.PNG "Capture d'écran de la page des références de format de la génération d'états électroniques")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Définir les substitutions de liaisons du format ER défini

1. Dans la page **Configurations**, sous l'organisateur **Remplacements**, sélectionnez **Sélectionner des composants**.
2. Dans l'arborescence des composants de format, développez **Résultat**, développez **Résultat\\Document**, puis activez la case à cocher pour **Résultat\\Document\\ProcessingDateTime**.

    ![Boîte de dialogue Sélectionner des composants](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Capture d'écran de la boîte de dialogue Sélectionner des composants")

3. Cliquez sur **OK**.

![Page des références de format de la génération d'états électroniques](media/GER-BaselineSample-AddBaseline4.PNG "Capture d'écran de la page des références de format de la génération d'états électroniques")

Le composant du format ER sélectionné a été ajouté à la liste des composants dans l'organisateur **Remplacements**. Lorsque le format ER de référence est exécuté en mode de débogage, la liaison du format pour chaque composant est remplacée par la liaison affichée dans la colonne **Liaison**. Pour modifier la liaison par défaut pour un composant répertorié dans l'organisateur **Remplacements**, sélectionnez **Éditer**.

### <a name="make-a-new-baseline-rule"></a>Établir une nouvelle règle de référence

Suivez les étapes de la section « Exemple :Automatisation du paramétrage des règles de référence » plus haut dans cette rubrique. Une notification vous indique que le fichier de sortie a été généré à l'aide des paramètres de référence, et qu'un remplacement forcé des liaisons du format a eu lieu.

![Notification dans la page Configurations](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Capture d'écran de la notification dans la page Configurations")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Supprimer les avertissements concernant le remplacement des liaisons de format

En définissant des paramètres ER spécifiques, vous pouvez supprimer les notifications qui avertissent du remplacement des liaisons du format. Cette opération peut être utile lorsque les liaisons de format sont remplacées en mode sans assistance à l'aide de Regression Suite Automation Tool. Dans ce cas, l'avertissement peut être considéré comme un échec du scénario de test exécuté.

1. Dans la page **Configurations**, dans le volet Actions, sous l'onglet **Configurations**, sélectionnez **Paramètres utilisateur**.
2. Définissez l'option **Supprimer les avertissements relatifs à la référence** sur **Oui**, puis sélectionnez **OK**.

![Boîte de dialogue Paramètres utilisateur](media/GER-BaselineSample-ERUserParameters1.png "Capture d'écran de la boîte de dialogue Paramètres utilisateur")

### <a name="review-the-generated-baseline-file"></a>Examiner le fichier de référence généré

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Sélectionnez **Références**.
3. Sélectionnez **Pièces jointes**.

    ![Page Pièces jointes](media/GER-BaselineSample-AttachedBaselineFile.PNG "Capture d'écran de la page Pièces jointes")

    > [!NOTE]
    > Le fichier généré contient le texte de la date et de l'heure du traitement (**« # »**) à partir de la liaison qui a été configurée dans la règle de référence ajoutée, et non à partir de la liaison du format.

4. Fermez la page **Pièces jointes**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Exécutez le format ER conçu et consultez le journal pour analyser les résultats

1. Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2. Dans l'arborescence, développez **Modèle d'apprentissage des références ER**.
3. Dans l'arborescence, sélectionnez **Modèle d'apprentissage des références ER\\Format pour l'apprentissage des références ER**.
4. Dans l'organisateur **Versions**, sélectionnez **Exécuter**.
5. Dans le champ **Entrer l'identifiant**, entrez **1**.
6. Cliquez sur **OK**.
7. Accédez à **Administration d'organisation** \> **États électroniques** \> **Journaux de débogage des configurations**.

Le journal d'exécution contient des informations sur le résultat de la comparaison du fichier généré avec la base de référence configurée. Le journal indique que le fichier généré et la référence sont égaux, même si le format exécuté contient la liaison permettant d'entrer une valeur de date et d'heure changeant en permanence dans le fichier de sortie.

> [!NOTE]
> Bien que le fichier de sortie ait été généré à l'aide de paramètres de référence qui forcent le remplacement des liaisons du format, vous ne recevez aucun avertissement concernant ce remplacement.

## <a name="exchange-baseline-settings-between-environments"></a>Échanger les paramètres de référence entre environnements

### <a name="export-baseline-settings"></a>Exporter les paramètres de référence

Les nouvelles fonctionnalités ER vous permettent d'exporter les paramètres de référence pour le format ER sélectionné à partir de l'environnement actuel et de les enregistrer sous la forme de fichiers XML. 

Pour exporter les paramètres de référence, dans la page **Références de format de la génération d'états électroniques**, sélectionnez **Exporter**.

### <a name="import-baseline-settings"></a>Importer les paramètres de base

Les paramètres de référence exportés peuvent être importés dans un autre environnement. L'environnement doit d'abord être importé en tant que format ER. Vous pouvez ensuite importer les paramètres de référence.

Pour importer les paramètres de référence à partir d'un fichier XML enregistré localement, dans la page **Références de format de la génération d'états électroniques**, sélectionnez **Importer**, puis sélectionnez **Parcourir** pour sélectionner le fichier XML.

![Boîte de dialogue Importer des paramètres de référence](media/GER-BaselineSample-ImportBaseline1.PNG "Capture d'écran de la boîte de dialogue Importer des paramètres de référence")

Pour importer des paramètres de référence à partir d'un fichier XML stocké sur le serveur Microsoft SharePoint, en fonction des paramètres de gestion des documents et du type de document sélectionné, dans la page **Références de format de la génération d'états électroniques**, sélectionnez **Importer à partir d'une source**. Sélectionnez ensuite le type de document et le fichier XML. Type de document requis pour accéder au dossier SharePoint doit être configuré à l'avance.

![Boîte de dialogue Importer à partir d'une source](media/GER-BaselineSample-ImportBaseline2.PNG "Capture d'écran de la boîte de dialogue Importer à partir d'une source")

> [!NOTE]
> Vous pouvez utiliser l'enregistreur de tâches pour enregistrer les étapes de sélection du type de document requis et du nom du fichier dans la boîte de dialogue **Importer à partir d'une source**. De cette manière, vous pouvez conserver les paramètres de référence requis sur le serveur SharePoint et les importer automatiquement en les lisant dans un enregistrement de tâche au moment de l'exécution des tests automatisés à l'aide de Regression Suite Automation Tool.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Suivre les résultats de rapport généré et les comparer avec des valeurs de base](er-trace-reports-compare-baseline.md)
- [Enregistreur de tâches](../user-interface/task-recorder.md)
