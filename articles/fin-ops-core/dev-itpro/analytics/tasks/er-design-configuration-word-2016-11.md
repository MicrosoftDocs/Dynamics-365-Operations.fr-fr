---
title: Réutiliser les configurations ER avec des modèles Excel pour générer des rapports au format Word
description: Cette rubrique décrit comment les formats d’état conçus pour générer des états sous forme de classeurs Excel peuvent être configurés pour générer des états sous forme de documents Word.
author: NickSelin
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab4cd4a390782936a74977ac2aef3790aa8ac1af
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891693"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Réutiliser les configurations ER avec des modèles Excel pour générer des rapports au format Word

[!include [banner](../../includes/banner.md)]

Pour générer les rapports comme documents Microsoft Word, vous pouvez [configurer](../er-design-configuration-word.md) un nouveau [format](../general-electronic-reporting.md#FormatComponentOutbound) de [gestion des états électroniques](../general-electronic-reporting.md). Vous pouvez également réutiliser un format de gestion des états électroniques qui a été conçu à l’origine pour générer des états sous forme de classeurs Excel. Dans ce cas, vous devez remplacer le modèle Excel par un modèle Word.

Les procédures suivantes montrent comment un utilisateur ayant le rôle d’administrateur système ou le rôle de développeur d’états électroniques peut configurer un format de gestion des états électroniques pour générer des rapports sous forme de fichiers Word en réutilisant un format de gestion des états électroniques conçu pour générer des rapports sous forme de fichiers Excel.

Ces procédures peuvent être effectuées dans la société GBSI.

## <a name="prerequisites"></a>Conditions préalables

Pour exécuter ces procédures, vous devez tout d’abord suivre les étapes du guide de tâches [Concevoir une configuration pour générer des états au format OPENXML](er-design-reports-openxml-2016-11.md).

Vous devez également télécharger et enregistrer localement les modèles suivants pour l’exemple d’état :

- [Modèle d’état de paiement (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=862266)
- [Modèle lié d’état de paiement (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=862266)

Ces procédures concernent une fonctionnalité qui a été ajoutée dans Dynamics 365 for Operations version 1611 (novembre 2016).

## <a name="select-the-existing-er-report-configuration"></a>Sélectionnez la configuration d’états électroniques existante

1. Dans Dynamics 365 Finance, accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Assurez-vous que le fournisseur de la configuration **Litware, Inc.** est sélectionné comme **Actif**. Si ce n’est pas le cas, suivez les étapes du guide de tâche [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).
3. Sélectionnez **Configurations des états**. Vous réutiliserez la configuration pour la gestion des états électroniques existante conçue pour générer la sortie d’état au format OPENXML.
4. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **Exemple d’état sur les feuilles de calcul**.

    > [!NOTE]
    > La version provisoire du format pour la gestion des états électroniques sélectionnés peut être modifiée dans l’organisateur **Versions**.

5. Sélectionnez **Concepteur**.
6. Sur la page **Concepteur de format**, notez que le titre de l’élément de format racine indique qu’un modèle Excel est actuellement utilisé.

![Sélectionner la configuration existante](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Consulter le modèle Word téléchargé

1. Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReport.docx** que vous avez téléchargé précédemment.
2. Vérifiez que le modèle ne contient que la mise en page du document que vous souhaitez générer comme sortie de gestion des états électroniques.

![Disposition du modèle Word dans l’application de bureau](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Remplacer le modèle Excel par le modèle Word et ajouter une partie XML personnalisée

Actuellement, le document Excel est utilisé comme modèle pour générer la sortie au format OPENXML. Vous remplacerez ce modèle par le modèle Word SampleVendPaymDocReport.docx que vous avez téléchargé antérieurement. Vous développerez également le modèle Word en ajoutant une partie XML personnalisée.

1. Dans Finance, sur la page **Concepteur de format**, dans l’onglet **Format**, sélectionnez **Documents joints**.
2. Sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle Excel existant. Sélectionnez **Oui** pour confirmer la modification.
3. Sélectionnez **Nouveau** \> **Fichier**.

    > [!NOTE]
    > Vous devez sélectionner un type de document qui a été [configuré](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dans les paramètres de gestion des états électroniques pour stocker les modèles aux formats de gestion des états électroniques.

4. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReport.docx** que vous avez téléchargé précédemment.
5. Cliquez sur **OK**.
6. Fermez la page **Pièces jointes**.
7. Sur la page **Concepteur de format**, dans le champ **Modèle**, entrez ou sélectionnez le fichier **SampleVendPaymDocReport.docx** pour utiliser ce modèle Word au lieu du modèle Excel précédemment utilisé.
8. Sélectionnez **Enregistrer**.

    Outre les modifications de configuration de stockage, l’action **Enregistrer** met également à jour le modèle Word joint. La structure hiérarchique du format conçu est ajoutée au document Word joint en tant que nouvelle partie XML personnalisée nommée **État**. Le modèle Word joint contient non seulement la mise en page du document que nous souhaitons générer comme sortie de gestion des états électroniques, mais également la structure des données que la gestion des états électroniques renseignera dans ce modèle au moment de l’exécution.

9. Notez que le titre de l’élément de format racine indique qu’un modèle Word est actuellement utilisé.

    ![Remplacer le modèle Excel par le modèle Word et ajouter une partie XML personnalisée](../media/er-design-configuration-word-2016-11-image03.gif)

10. Dans l’onglet **Format**, sélectionnez **Pièces jointes**.

Vous pouvez maintenant mettre en correspondance des éléments de la partie XML personnalisée **État** et des contrôles de contenu du document Word.

Si vous connaissez bien le processus de conception des documents Word comme formulaires qui contiennent les [contrôles de contenu](/office/client-developer/word/content-controls-in-word) mis en correspondance avec les éléments des [pièces XML personnalisées](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), exécutez toutes les étapes de la prochaine procédure pour créer le document. Pour plus de détails, voir [Créer des formulaires à remplir ou imprimer dans Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). Sinon, passez à la procédure suivante.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Obtenir un document Word contenant une partie XML personnalisée et effectuer un mappage de données

1. Dans Finance, sur la page **Documents joints**, sélectionnez **Ouvrir** pour télécharger le modèle sélectionné depuis Finance et le stocker localement sous forme de document Word.
3. Dans l’application de bureau Word, ouvrez le document que vous venez de télécharger.
4. Dans l’onglet **Développeur**, sélectionnez **Volet de mise en correspondance XML**.

    > [!NOTE]
    > Si l’onglet **Développeur** n’apparaît pas sur le ruban, personnalisez le ruban pour l’ajouter.

5. Dans le volet **Mise en correspondance XML**, dans le champ **Partie XML personnalisée**, sélectionnez la partie XML personnalisée **État**.
6. Mettez en correspondance des éléments de la partie XML personnalisée **État** sélectionnée et des contrôles de contenu du document Word.
7. Enregistrez le document Word mis à jour localement sous **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Examiner le modèle Word dans lequel la partie XML personnalisée est mappée aux contrôles de contenu

1. Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReportBounded.docx**.
2. Vérifiez que le modèle contient la mise en page du document que vous souhaitez générer comme sortie de gestion des états électroniques. Les contrôles de contenu qui sont utilisés comme espaces réservés pour les données que la gestion des états électroniques entrera dans ce modèle lors de l’exécution sont basés sur les mappages configurés entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu du document Word.

![Aperçu du modèle Word dans l’application de bureau](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Charger le modèle Word dans lequel la partie XML personnalisée est mappée aux contrôles de contenu

1. Dans Finance, sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle Word qui n’a pas de mappage entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu. Sélectionnez **Oui** pour confirmer la modification.
2. Sélectionnez **Nouveau** \> **Fichier** pour ajouter un nouveau fichier de modèle contenant des mappages entre les éléments de la partie XML personnalisée **État** et les contrôles de contenu.

    > [!NOTE]
    > Vous devez sélectionner un type de document qui a été [configuré](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dans les paramètres de gestion des états électroniques pour stocker les modèles aux formats de gestion des états électroniques.

3. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReportBounded.docx** que vous avez téléchargé ou préparé en suivant la procédure dans la section [Obtenir un Word avec une partie XML personnalisée pour faire le mappage de données](#get-word-doc).
4. Cliquez sur **OK**.
5. Fermez la page **Pièces jointes**.
6. Sur la page **Concepteur de format**, dans le champ **Modèle**, sélectionnez le document que vous venez de télécharger.
7. Sélectionnez **Enregistrer**.
8. Fermez la page **Concepteur de format**.

## <a name="mark-the-configured-format-as-runnable"></a>Marquer le format configuré comme exécutable

Pour exécuter la version brouillon du format modifiable, vous devez le rendre [exécutable](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. Dans Finance, sur la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
2. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.
3. Sélectionnez **Modifier** pour rendre la page active modifiable, selon les besoins.
4. Pour la configuration **Exemple d’état sur les feuilles de calcul** actuellement sélectionnée, définissez l’option **Exécuter le brouillon** sur **Oui**.
5. Sélectionnez **Enregistrer**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Exécuter le format pour créer une sortie au format Word

1. Dans Finance, accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.
2. Dans un journal des paiements que vous avez saisi précédemment, sélectionnez **Lignes**.
3. Sur la page **Paiements fournisseur**, sélectionnez toutes les lignes de la grille.
4. Sélectionnez **Statut de paiement** \> **Aucun**.

    ![Paiements pour traitement sur la page Paiements fournisseur](../media/er-design-configuration-word-2016-11-image05.png)

5. Dans le volet Actions, sélectionnez **Générer les paiements**.
6. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
    2. Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.
    3. Cliquez sur **OK**.

7. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, sélectionnez **OK**.
8. La sortie générée se présente sous le format Word et contient les détails des paiements traités. Analysez la sortie générée.

    ![Sortie générée au format Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Créer une configuration de gestion des états électroniques pour générer des états au format Word](../er-design-configuration-word.md)
- [Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]