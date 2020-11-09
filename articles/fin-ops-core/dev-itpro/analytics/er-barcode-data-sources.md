---
title: Utiliser des sources de données de codes-barres pour générer des images de codes-barres
description: Cette rubrique explique comment utiliser des sources de données de codes-barres pour générer des images de codes-barres.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: c549a476f854ffcf962ffb62e430b459d3445734
ms.sourcegitcommit: cc78f9bf585082ce65c2ab0b011ff62620fa883d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088195"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Utiliser des sources de données de codes-barres pour générer des images de codes-barres

[!include[banner](../includes/banner.md)]

Vous pouvez utiliser la structure [États électroniques (ER)](general-electronic-reporting.md) pour concevoir des [composants au format ER](general-electronic-reporting.md#FormatComponentOutbound) que vous pouvez exécuter pour générer les documents sortants électroniques et imprimables dont vous avez besoin. Pour générer un document sortant au format Microsoft Office, vous devez spécifier la présentation de l'état en utilisant soit un document Microsoft Excel ou un document Microsoft Word en tant que modèle d'état. Le [Concepteur d'opérations de gestion des états électroniques](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) vous permet de joindre un document Excel ou Word en tant que modèle pour un format ER. Les éléments nommés suivants dans le modèle joint sont associés aux éléments du composant de format configuré :

- Contrôles de contenu dans Word
- Feuilles, plages, cellules, formes et images nommées dans Excel

Ces éléments nommés sont utilisés comme des espaces réservés pour les données entrées dans un document généré lors de l'exécution d'un format ER. Les éléments de format ER sont liés avec les sources de données. Ces sources de données spécifient les données qui seront entrées dans les documents générés lors de l'exécution. Pour plus d'informations, voir [Intégrer des images et des formes dans les documents que vous générez à l'aide de la gestion d'ER](electronic-reporting-embed-images-shapes.md).

ER prend désormais en charge le type de source de données **Code-barres**. Par conséquent, vous pouvez maintenant générer une image qui représente le code-barres pour le texte spécifié. Lorsque vous configurez un format ER, vous pouvez spécifier les sources de données du type **Code-barres** pour générer des images de code-barres. Vous pouvez ensuite ajouter ces images aux documents commerciaux générés, tels que les commandes, les factures, les bons de livraison et les reçus. Vous pouvez également les ajouter à différents types d'étiquettes, telles que les étiquettes de produits et d'étagères, ainsi que les étiquettes d'emballage et d'expédition.

Les espaces réservés suivants peuvent être utilisés dans les modèles d'état pour entrer des images de code-barres :

- [Image](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) contrôle de contenu pour Word
- [Image](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) objet dans Excel

En utilisant une source de données du type **Code-barres** , vous pouvez générer des codes-barres dans les formats suivants :

- Codes-barres unidimensionnels :

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Intelligent Mail
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Codes-barres bidimensionnels :

    - Aztec
    - Data Matrix
    - Code QR

Lorsque vous configurez une source de données **Code-barres** , vous pouvez définir des paramètres de rendu spécifiques qui sont utilisés pour générer une image :

- **Largeur** - Spécifiez la largeur du code-barres en pixels. Une valeur de **0** (zéro) indique que la largeur par défaut est utilisée. La signification peut varier pour différents formats.
- **Hauteur** - Spécifiez la hauteur du code-barres en pixels. Une valeur de **0** (zéro) indique que la hauteur par défaut est utilisée. La signification peut varier pour différents formats.
- **Marge** - Spécifiez la taille de la marge du code-barres en pixels. La marge est la zone de chaque côté d'un code-barres qui doit être dégagée (zone silencieuse). Une valeur de **0** (zéro) indique que la marge par défaut est utilisée. La signification peut varier pour différents formats.
- **Contenu de sortie** - Paramétrez la valeur sur **Oui** pour générer une image de code-barres qui contient les informations codées sous forme de texte. La valeur par défaut est **Non**.
- **Codage** - Spécifiez le type de caractères qui sont encodés dans l'image de code-barres générée. Par défaut, l'encodage **UTF-8** est utilisé.

> [!IMPORTANT]
> Lorsque vous ajoutez une nouvelle source de données **Code-barres** , vous devez la placer sous un autre élément (conteneur) en tant qu'élément imbriqué.
>
> Lorsque vous liez une source de données **Code-barres** à un élément de cellule dans un format, et l'élément de cellule représente un contrôle de contenu Word ou une image Excel, la source de données est présentée dans cette liaison comme une fonction qui a un seul paramètre du type **Chaîne**. Vous devez utiliser ce paramètre pour spécifier le texte qui doit être transformé en une image de code-barres et lu lorsqu'un code-barres généré est numérisé.

Pour en savoir plus sur cette fonctionnalité, exécutez les exemples décrits dans cette rubrique.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Exemple : Générer un chèque de paiement contenant un code-barres qui code le montant à payer

Cet exemple montre comment un utilisateur du rôle **Administrateur du système** ou **Consultant fonctionnel des états électroniques** peut configurer un format ER qui contient un modèle utilisé pour générer un document sortant au format Excel contenant un code-barres. Voici un aperçu des étapes impliquées.

1. [Effectuer les tâches préalables](#ExamplePrerequisites).
2. [Activer un fournisseur de configuration](#ExampleProvider).
3. [Importer la solution ER fournie](#ExampleImportSolution).
4. [Générer un chèque de paiement](#ExampleGenerateCheque).
5. [Examiner le chèque de paiement généré](#ExampleReviewGeneratedCheque).
6. [Modifier le format de la solution ER fournie](#ExampleModifyFormat).

    1. [Appliquer un nouveau modèle de chèque](#ExampleModifyFormatApplyTemplate).
    2. [Ajouter une nouvelle source de données de code-barres](#ExampleModifyFormatAddDataSource).
    3. [Lier un nouvel élément de format](#ExampleModifyFormatBindFormatElement).
    4. [Rendre la version modifiée disponible pour les exécutions de tests](#ExampleModifyFormatMakeVersionAvailable).

        1. [Compléter la version au format modifié](#CompleteToRun).
        2. [Rendre la version provisoire disponible pour utilisation](#MarkToRun).

7. [Générer un chèque de paiement](#ExampleGenerateCheque2).
8. [Convertir le chèque généré en PDF](#ExampleConvertToPDF).

Dans cet exemple, vous utiliserez la solution ER fournie qui a été configurée pour générer des chèques de paiement. Cette solution génère des chèques de paiement où le montant à payer est écrit à la fois sous forme de nombre et de texte. Vous allez modifier cette solution ER afin que le chèque comprenne également un code-barres généré où le montant à payer est codé et peut être lu à l'aide d'un lecteur de code-barres.

Ces étapes peuvent être effectuées dans la société fictive **USMF** dans Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Effectuer les tâches préalables

Pour terminer cet exemple, vous devez avoir accès à la société USMF pour l'un des rôles suivants :

- Consultant fonctionnel des états électroniques
- Administrateur système

Si vous n'avez pas encore terminé l'exemple dans la rubrique [Intégrer des images et des formes dans les documents que vous générez à l'aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md), téléchargez les configurations suivantes de l'exemple de solution ER.

| Description du contenu         | Nom de fichier                   |
|-----------------------------|-----------------------------|
| Configuration de modèle de données ER | Modèle pour les chèques.xml       |
| Configuration de format ER     | Format d'impression des chèques.xml |

En outre, téléchargez le fichier Excel suivant qui contient le modèle modifié pour la solution ER fournie.

| Description du contenu | Nom de fichier                 |
|---------------------|---------------------------|
| Modèle d'état     | Modèle de chèque Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Activer un fournisseur de configuration

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation** , dans la section **Fournisseurs de configuration** , vérifiez que le [fournisseur de configuration](general-electronic-reporting.md#Provider) pour l'exemple de société **Litware, Inc.** est répertorié, et qu'il est marqué comme actif. S'il n'est pas répertorié ou s'il n'est pas marqué comme actif, suivez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Rendre l'exemple de société actif sur la page Configurations de localisation](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importer la solution ER fournie

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation** , dans la section **Configurations** , sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations** , si la configuration **Modèle pour les chèques** n'est pas disponible dans l'arborescence, suivez la procédure permettant d'importer la configuration du modèle de données ER :

    1. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
    2. Dans la boîte de dialogue, sélectionnez **Parcourir** , recherchez et sélectionnez le fichier **Modèle pour les chèques.xml** , puis sélectionnez **OK**.

4. Si la configuration **Format d'impression des chèques** n'est pas disponible dans l'arborescence, suivez la procédure permettant d'importer la configuration du format ER :

    1. Sur le volet Action, sélectionnez **Exchange** \> **Charger depuis le fichier XML**.
    2. Dans la boîte de dialogue, sélectionnez **Parcourir** , recherchez et sélectionnez le fichier **Format d'impression des chèques.xml** , puis sélectionnez **OK**.

5. Dans l'arborescence de configuration, développez **Modèle pour les chèques**.
6. Consultez la liste des configurations ER importées dans l'arborescence de configuration.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Générer un chèque de paiement

1. Accédez à **Gestion de la trésorerie et de la banque** \> **Comptes bancaires** \> **Comptes bancaires**.
2. Sur le page **Comptes bancaires** , sélectionnez le compte **USMF OPER**.
3. Sur la page Détails du compte bancaire, dans le volet Actions, sous l'onglet **Paramétrer** , dans le groupe **Disposition** , sélectionnez **Chèque**.
4. Sur la page **Mise en page des chèques** , sélectionnez **Modifier**.
5. Dans le raccourci **Général** , définissez l'option **Format d'exportation électronique générique** sur **Oui**.
6. Dans le champ **Exporter la configuration du format** , sélectionnez le format ER **Format d'impression des chèques** que vous avez importé précédemment.
7. Dans le volet Actions, sélectionnez **Test d'impression**.
8. Dans la boîte de dialogue, définissez l'option **Format de chèque négociable** sur **Oui** , puis sélectionnez **OK**.

    ![Boîte de dialogue Mise en page des chèques - Test d'impression](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Examiner le chèque de paiement généré.

- Ouvrez le chèque généré dans Excel.
2. Examinez le chèque généré.

    ![Chèque de paiement généré dans Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Modifier le format de la solution ER fournie

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Appliquer un nouveau modèle de chèque

Vous pouvez utiliser l'application de bureau Excel pour ouvrir le fichier **Modèle de chèque Excel.xlsx** que vous avez importé précédemment. Notez que ce modèle diffère du modèle que vous avez utilisé pour générer un chèque de paiement dans la solution ER fournie. En outre, il comprend un élément **AmountBarcode** pour l'image de code-barres.

![Élément AmountBarcode dans le modèle Excel](./media/er-barcode-data-source-cheque2.png)

Vous devez maintenant modifier la solution ER puis [réappliquer](modify-electronic-reporting-format-reapply-excel-template.md) le modèle modifié.

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation** , dans la section **Configurations** , sélectionnez **Configurations des états**.
3. Sur la page **Configurations** , dans l'arborescence de configuration, développez **Modèle de chèques** et sélectionnez **Format d'impression des chèques**.
4. Dans le volet Actions, sélectionnez **Concepteur**.
5. Dans le Concepteur d'opérations de gestion des états électroniques, sélectionnez l'onglet **Mise en correspondance** sur le côté droit de la page, puis, dans le volet d'arborescence des formats à gauche, sélectionnez **Développer/Réduire**.
6. Notez que tous les éléments de format de cellule sont liés aux sources de données appropriées.

    ![Liaison d'éléments de format de cellule à des sources de données dans le Concepteur d'opérations de gestion des états électroniques](./media/er-barcode-data-source-cells-bound.png)

7. Sélectionnez l'onglet **Format** sur le côté droit de la page.
8. Dans le volet Actions, sélectionnez les points de suspension ( **...** ), puis sélectionnez **Importer**.
9. Dans le groupe **Importation** , sélectionnez **Mise à jour depuis Excel** , puis sélectionnez **Mettre à jour le modèle**.
10. Dans la boîte de dialogue, accédez au fichier **Modèle de chèque Excel.xlsx** enregistré sur votre ordinateur, sélectionnez-le, puis sélectionnez **OK** pour confirmer que le modèle sélectionné doit être appliqué.
11. Sélectionnez l'onglet **Mise en correspondance** sur le côté droit de la page, puis, dans le volet d'arborescence des formats à gauche, sélectionnez **Développer/Réduire**.
12. Notez que l'élément de cellule **AmountBarcode** a été ajouté au format. Cet élément est associé à l'élément **AmountBarcode** qui a été ajouté au modèle Excel modifié en tant qu'espace réservé pour une image de code-barres.

    ![Élément de cellule AmountBarcode ajouté au format dans le Concepteur d'opérations de gestion des états électroniques](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Ajouter une nouvelle source de données de code-barres.

Ensuite, vous devez ajouter une nouvelle source de données du type **Code-barres**.

1. Dans le Concepteur d'opérations de gestion des états électroniques, dans l'onglet **Mise en correspondance** sur le côté droit de la page, sélectionnez la source de données **Imprimer**.
2. Sélectionnez **Ajouter** , puis dans le groupe **Fonctions** , sélectionnez le type de source de données **Code-barres**.

    ![Sélection du type de source de données Code-barres](./media/er-barcode-data-source-add.png)

3. Dans la boîte de dialogue déroulante, dans le champ **Nom** , entrez **Code-barres**.
4. Dans le champ **Format de code-barres** , sélectionnez **Code 128**.
5. Dans le champ **Largeur** , entrez **500**.
6. Cliquez sur **OK**.

    ![Boîte de dialogue Propriétés de la source de données](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Lier un nouvel élément de format

Ensuite, vous devez lier le nouvel élément de format à la source de données que vous venez d'ajouter.

1. Dans le Concepteur d'opérations de gestion des états électroniques, dans l'onglet **Mise en correspondance** sur le côté droit de la page, sélectionnez la source de données **print\\barcode**.
2. Dans le volet d'arborescence des formats à gauche, sélectionnez l'élément de cellule **AmountBarcode** , puis sélectionnez **Lier**.
3. Dans le volet Actions, sélectionnez **Afficher les détails**.
4. Notez que, parce que la source de données **Code-barres** est représentée dans la liaison comme une fonction qui contient un seul paramètre, le nom de l'élément de format lié a été automatiquement pris comme argument de ce paramètre.

    ![Détails de la source de données Code-barres dans le Concepteur d'opérations de gestion des états électroniques](./media/er-barcode-data-source-bind1.png)

5. Sélectionnez **Modifier la formule** pour ajuster la liaison.

    Vous ne voulez pas que le nom de l'élément de cellule soit renvoyé. Par conséquent, vous devez configurer une expression qui renvoie du texte contenant le montant à payer du chèque en cours. Parce que la plage du parent **ChequeLines** est liée à la source de données **model.cheques** , le montant payable du chèque en cours est disponible dans le champ **model.cheques.attributes.amount** du type de données **Réel**.

6. Dans le champ **Formule** , entrez **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Sélectionnez **Enregistrer** , puis fermez le [Concepteur de formule ER](general-electronic-reporting-formula-designer.md).
8. Notez que la liaison a été ajustée.

    ![Ajustement de liaison dans le Concepteur d'opérations de gestion des états électroniques](./media/er-barcode-data-source-bind2.png)

9. Sélectionnez **Enregistrer** , puis fermez le Concepteur d'opérations de gestion des états électroniques.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Rendre la version modifiée disponible pour les exécutions de tests.

Par défaut, les seules versions qui ont le statut **Terminé** et **Partagé** sont utilisées lorsque vous exécutez un format ER.

Si vous avez finalisé vos modifications, vous pouvez terminer votre travail avec la version provisoire actuelle et rendre vos modifications disponibles pour utilisation. Pour obtenir des instructions, consultez la section [Compléter la version au format modifié](#CompleteToRun) qui suit.

Si vous souhaitez continuer à travailler avec la version provisoire actuelle, mais que vous devez l'utiliser pour générer des vérifications, vous devez spécifier explicitement que vous souhaitez utiliser la version provisoire du format pour l'exécution. Pour obtenir des instructions, consultez la section [Rendre la version provisoire disponible pour utilisation](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Compléter la version au format modifié.

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation** , dans la section **Configurations** , sélectionnez **Configurations des états**.
3. Sur la page **Configurations** , dans l'arborescence de configuration, développez **Modèle de chèques** et sélectionnez **Format d'impression des chèques**.
4. Dans le raccourci **Versions** , sélectionnez l'enregistrement ayant un statut **Brouillon**.
5. Sélectionnez **Modifier le statut** , puis sélectionnez **Terminer**.
6. Dans la boîte de dialogue, sélectionnez **OK**.

Le statut de la version actuelle passe de **Brouillon** à **Terminé** et une nouvelle version qui a le statut **Brouillon** est créé. Vous pouvez utiliser cette nouvelle version provisoire pour appliquer des modifications supplémentaires.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Rendre la version provisoire disponible pour utilisation.

1. Accédez à **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation** , dans la section **Configurations** , sélectionnez **Configurations des états**.
3. Dans la page **Configurations** , dans le volet Actions, sous l'onglet **Configurations** , dans le groupe **Paramètres avancés** , sélectionnez **Paramètres utilisateur**.
4. Dans la boîte de dialogue, définissez les options **Exécuter la configuration** sur **Oui** , puis sélectionnez **OK**.
5. Dans l'arborescence de configuration, développez **Modèle de chèques** et sélectionnez **Format d'impression des chèques**.
6. Définissez l'option **Exécuter le brouillon** sur **Oui**.
7. Sélectionnez **Enregistrer**.

La version provisoire du format sélectionné est marquée comme disponible pour utilisation lorsque le format sélectionné est exécuté.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Générer un chèque de paiement

1. Accédez à **Gestion de la trésorerie et de la banque** \> **Comptes bancaires** \> **Comptes bancaires**.
2. Sur le page **Comptes bancaires** , sélectionnez le compte **USMF OPER**.
3. Sur la page Détails du compte bancaire, dans le volet Actions, sous l'onglet **Paramétrer** , dans le groupe **Disposition** , sélectionnez **Chèque**.
4. Sur la page **Mise en page des chèques** , dans le volet Actions, sélectionnez **Test d'impression**.
5. Dans la boîte de dialogue, définissez l'option **Format de chèque négociable** sur **Oui**.
6. Cliquez sur **OK**.
7. Examinez le chèque généré. Notez qu'un code-barres a été généré pour coder le montant payable du chèque.

    ![Chèque de paiement généré avec code-barres dans Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Une exception est levée si l'argument d'une source de données **Code-barres** n'est pas conforme aux exigences appropriées spécifiques au format de code-barres. Par exemple, lorsque la source de données **Code-barres** est appelée pour générer un code-barres [EAN-8](https://wikipedia.org/wiki/EAN-8) pour le texte fourni, une exception est levée si la longueur du texte dépasse sept caractères.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Convertir le chèque généré en PDF.

Comme décrit dans la rubrique [Générer des formulaires FTI imprimables](er-generate-printable-fti-forms.md#finland), vous pouvez utiliser une police spéciale pour produire des codes-barres dans un document généré. Dans ce cas, des transformations supplémentaires du document généré peuvent dépendre de la disponibilité de cette police dans l'environnement de transformation. Par exemple, si vous essayez de convertir un document au format PDF ou de le prévisualiser dans un environnement où la police est manquante, les codes-barres ne s'afficheront pas correctement.

Cependant, lorsque vous utilisez la source de données **Code-barres** pour produire des codes-barres, le rendu de ces codes-barres ne dépend d'aucune police. Par conséquent, vous pouvez facilement convertir les documents contenant les codes-barres au format PDF. L'illustration suivante montre l'aperçu d'un chèque de paiement généré qui a été [converti](electronic-reporting-destinations.md#OutputConversionToPDF) en PDF, basé sur le paramètre de l'ER configuré [destination](electronic-reporting-destinations.md).

![Aperçu du PDF d'un chèque de paiement](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Limitations

> [!NOTE]
> Certains types de codes-barres générés ont un rapport hauteur/largeur fixe. Ce comportement est logique si vous avez activé la fonctionnalité **Activer l'utilisation de la bibliothèque EPPlus dans le cadre d'états électroniques** pour travailler avec des documents Excel dans ER. Dans ce cas, une image est entrée dans un espace réservé dont le rapport hauteur/largeur est verrouillé. Par conséquent, lorsque les dimensions d'un espace réservé dans un modèle correspondent au rapport d'une image qui est entrée, une image réelle dans un document généré peut être redimensionnée pour conserver le rapport d'aspect requis. Pour empêcher le redimensionnement de l'image, utilisez un espace réservé qui a un rapport hauteur/largeur attendu.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des États électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)
- [Langage de formule dans la gestion des états électroniques](er-formula-language.md)
- [Fonction NUMBERFORMAT](er-functions-text-numberformat.md)
