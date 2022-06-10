---
title: Supprimer les contrôles de contenu Word dans les rapports générés
description: Cette rubrique explique comment configurer un format d’état électronique (ER) pour générer des états en tant que fichiers Microsoft Word dans lesquels les contrôles de contenu sont supprimés.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 2c2d79c9ea36c42cfc0f6ba0d3c81d063d8d9446
ms.sourcegitcommit: 6c1bf233748c4bc70fc5a1a9711758cdfd9e07dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2022
ms.locfileid: "8782174"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Supprimer les contrôles de contenu Word dans les rapports générés

[!include [banner](../includes/banner.md)]

Pour générer des états en tant que documents Microsoft Word, vous devez concevoir un modèle pour les états sous forme de document Word. Ce modèle doit contenir des contrôles de contenu Word en tant qu’espaces réservés pour les données qui seront renseignées au moment de l’exécution. Pour utiliser le document Word créé comme modèle pour vos états, vous pouvez [configurer](er-design-configuration-word.md) une nouvelle [solution](er-quick-start1-new-solution.md) de [gestion des états électroniques](general-electronic-reporting.md). La solution doit inclure une [configuration](general-electronic-reporting.md#Configuration) de gestion des états électroniques qui contient un composant de format de gestion des états électroniques. Ce format ER doit être configuré pour utiliser le modèle conçu pour la génération d’états.

Dans la version 10.0.6 et ultérieures de Dynamics 365 Finance, vous pouvez configurer des formules dans votre format ER pour supprimer certains contrôles de contenu Word dans les documents générés.

Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de consultant fonctionnel des états électroniques peut configurer un format ER qui génère des états sous forme de fichiers Word et supprime certains des contrôles de contenu dans les rapports générés qui ont été configurés à l’aide d’un modèle Word.

Ces étapes peuvent être effectuées dans la société GBSI.

## <a name="prerequisites"></a>Conditions préalables

Pour réaliser ces étapes, vous devez d’abord effectuer les étapes des guides de tâche suivants :

- [Concevoir une configuration pour générer des états au format OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Réutiliser les configurations des états électroniques avec des modèles Excel pour générer des rapports au format Word](./tasks/er-design-configuration-word-2016-11.md)

Lorsque vous avez terminé les étapes de ces guides de tâches, les éléments suivants sont préparés :

- Un format ER **Exemple d’état sur les feuilles de calcul** configuré pour générer un document au format Word
- Une version [Brouillon](general-electronic-reporting.md#component-versioning) du format ER **Exemple d’état sur les feuilles de calcul** marqué comme **Exécutable**
- Un mode de paiement **Électronique** configuré pour utiliser le format ER **Exemple d’état sur les feuilles de calcul** pour le traitement des paiements fournisseur

Vous devez également télécharger et enregistrer le modèle suivant pour l’exemple d’état :

- [Modèle lié 2 d’état de paiement (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/1/9/b/19b36e39-861a-414e-9150-9880d9d2487c/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Consulter le modèle Word téléchargé

1. Dans l’application de bureau Word, ouvrez le fichier de modèle **SampleVendPaymDocReportBounded2.docx** que vous avez téléchargé précédemment.
2. Vérifiez que le fichier de modèle contient une section récapitulative qui affiche les montants de paiement totaux pour chaque code devise rencontré dans les paiements traités.

    - La section récapitulative se trouve dans un tableau distinct du document Word.
    - La première ligne de ce tableau contient les en-têtes des colonnes du tableau comme en-tête de section.
    - La deuxième ligne de ce tableau contient le contrôle de contenu répétitif en tant que détails de la section.
    - Ce contrôle de contenu est mappé sur le champ **SummaryLines** de la partie XML personnalisée **État**.
    - Sur la base de ce mappage, le contrôle de contenu est associé à l’élément **SummaryLines** du format ER modifiable.

    > [!NOTE]
    > Le contrôle de contenu répétitif est balisé par la clé **SummaryLines** qui correspond au champ de la partie XML personnalisée à laquelle elle a été mappée.

    ![Disposition du modèle Word.](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Sélectionnez la configuration d’états électroniques existante

Pour les étapes suivantes, vous réutiliserez la configuration ER existante que vous avez configurée lorsque vous avez effectué les étapes des guides de tâches mentionnés précédemment.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques**.
2. Sélectionnez **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de paiement**, puis sélectionnez **Exemple d’état sur les feuilles de calcul**.
4. Sélectionnez **Concepteur** pour modifier la version brouillon du format ER sélectionné.

## <a name="replace-the-current-template-with-the-new-template"></a>Remplacer le modèle actuel par le nouveau modèle

Actuellement, le fichier SampleVendPaymDocReportBounded.docx est utilisé comme modèle pour générer la sortie au format Word. Dans les étapes suivantes, vous remplacerez ce modèle Word par le nouveau modèle Word, SampleVendPaymDocReportBounded2.docx, que vous avez téléchargé précédemment.

1. Dans la page **Concepteur de formats**, sélectionnez **Documents joints**.
2. Sur la page **Documents joints**, sélectionnez **Supprimer** pour supprimer le modèle existant.
3. Sélectionnez **Oui** pour confirmer la suppression.
4. Sélectionnez **Nouveau** \> **Fichier**.
5. Sélectionnez **Parcourir**, puis recherchez et sélectionnez le fichier **SampleVendPaymDocReportBounded2.docx** que vous avez téléchargé précédemment.
6. Cliquez sur **OK**.
7. Fermez la page **Pièces jointes**.
8. Sur la page **Concepteur de format**, dans le champ **Modèle**, entrez ou sélectionnez le fichier **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Exécuter le format pour créer une sortie Word

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.
2. Sur la page **Paiements fournisseur**, sur l’onglet **Liste**, sélectionnez tous les paiements.
3. Sélectionnez **Statut de paiement** \> **Aucun**.
4. Sélectionnez **Générer des paiements**.
5. Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
6. Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.
7. Cliquez sur **OK**.
8. Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, sélectionnez **OK** et analysez la sortie générée.

    ![Paiements pour traitement sur la page Paiements fournisseur.](./media/er-design-configuration-word-suppress-controls-image2.gif)

    La sortie est présentée au format Word et contient la section récapitulative.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Configurer le format modifiable pour supprimer la section récapitulative

Si vous souhaitez supprimer la section récapitulative dans un document généré, sur la base de la demande d’un utilisateur qui exécute ce format ER, vous devez modifier le format ER modifiable.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques** et ouvrez la version brouillon du format ER à modifier.
2. Sélectionnez **Configurations des états**. 
3. Sur la page **Configurations**, dans l’arborescence de configuration, développez **Modèle de paiement** \> **Exemple d’état sur les feuilles de calcul**.
4. Sélectionnez **Concepteur**.
5. Sur la page **Concepteur de formats**, développez **Word** et sélectionnez **SummaryLines**.
6. Sur l’onglet **Mappage**, ajoutez une nouvelle source de données pour demander à l’utilisateur, au moment de l’exécution, si la section récapitulative doit être supprimée :

    1. Sélectionnez **Ajoutez racine**.
    2. Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Général\Paramètre d’entrée utilisateur** pour ouvrir la boîte de dialogue **Propriétés de la source de données « Paramètre d’entrée utilisateur »**.
    3. Dans le champ **Nom**, entrez **uipSuppress**.
    4. Dans le champ **Libellé**, entrez **Supprimer la section récapitulative**.
    5. Dans le champ **Nom du type de données des opérations**, sélectionnez ou entrez **NoYes**.
    6. Cliquez sur **OK**.

7. Ajoutez une nouvelle source de données du type d’énumération d’application **NoYes**.

    1. Sélectionnez **Ajoutez racine**.
    2. Dans la boîte de dialogue **Ajouter une source de données**, sélectionnez **Dynamics 365 for Operations\Énumération** pour ouvrir la boite de dialogue **Propriétés de la source de données « Enumération »**.
    3. Dans le champ **Nom**, entrez **enumNoYes**.
    4. Dans le champ **Libellé**, entrez **Supprimer les options**.
    5. Dans le champ **Nom du type de données des opérations**, sélectionnez ou entrez **NoYes**.
    6. Cliquez sur **OK**.

8. Pour l’élément de format **SummaryLines** sélectionné, configurez la formule pour spécifier quand le contrôle de contenu Word associé à l’élément de format sélectionné doit être supprimé :

    1. Sur l’onglet **Mappage**, dans la section **Supprimé**, sélectionnez **Modifier** pour ouvrir la page **[Concepteur de formule](general-electronic-reporting-formula-designer.md)**.
    2. Dans le champ **Formule**, entrez la formule `uipSuppress = enumNoYes.Yes`.
    3. Sélectionnez **Enregistrer** et fermez la page du **Concepteur de formule**.

        > [!NOTE]
        > Cette formule sera appliquée à un document généré **après l’exécution de tous les autres éléments de format**. Pour appliquer cette formule, un contrôle de contenu Word référencé en tant qu’élément de format pour lequel la formule est configurée (**SummaryLines** dans ce cas) se trouve dans un document généré. Ce contrôle de contenu est ensuite complètement supprimé, ainsi que la ligne du tableau Word qui le contient. La ligne de détails de la section récapitulative est supprimée du document généré.
        >
        > Au moment de la conception, vous pouvez configurer la formule **Supprimé** pour un élément de format, même si aucun contrôle de contenu dans le modèle Word que vous utilisez n’a de balise correspondant au nom d’un élément de format pour lequel la propriété **Supprimé** est configurée. Lorsque vous validez le format au moment de la conception, vous recevez un [avertissement](er-components-inspections.md#i14) à propos de cette incohérence.
        >
        > Au moment de l’exécution, une exception est levée si aucun contrôle de contenu dans le modèle Word que vous utilisez n’a de balise correspondant au nom d’un élément de format pour lequel la propriété **Supprimé** est configurée.

    4. Sur l’onglet **Mappage**, dans la section **Supprimé**, définissez l’option **Avec parent** sur **Oui**.

        > [!NOTE]
        > Vous devez définir cette option sur **Oui** pour supprimer l’ensemble du tableau Word en tant qu’objet parent de la ligne contenant les détails de la section récapitulative. Si vous définissez cette option sur **Non**, la ligne d’en-tête de section reste dans le document généré.

9. Sélectionnez **Enregistrer** pour enregistrer les modifications dans le format modifiable.

    ![Sortie générée au format Word.](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Exécuter le format modifié pour créer une sortie Word

1. Accédez à **Comptabilité fournisseur** \> **Paiements** \> **Journal des paiements**.
2. Sélectionnez le journal des paiements que vous avez créé, puis sélectionnez **Lignes**.
3. Sur la page **Paiements fournisseur**, sélectionnez toutes les lignes, puis sélectionnez **Statut de paiement** \> **Aucun**.
4. Sélectionnez **Générer des paiements**.
5. Dans le champ **Mode de paiement**, sélectionnez **Électronique**.
6. Dans le champ **Compte bancaire**, sélectionnez **GBSI OPER**.
7. Cliquez sur **OK**.
8. Dans la boîte de dialogue **Paramètres de génération d’états électroniques**, dans le champ **Supprimer la section récapitulative**, sélectionnez **Oui**.
9. Sélectionnez **OK** et analysez la sortie générée.

    ![Sortie générée au format Word.](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Notez que la sortie ne contient pas la section récapitulative, car elle a été supprimée.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Concevoir une configuration pour générer des états au format OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Concevoir une configuration des états électroniques pour générer des états au format Word](er-design-configuration-word.md)
- [Réutiliser les configurations des états électroniques avec des modèles Excel pour générer des rapports au format Word](./tasks/er-design-configuration-word-2016-11.md)
- [Inspectez le composant ER configuré pour éviter les problèmes d’exécution](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
