---
title: Concepteur de formule dans les états électroniques (ER)
description: Cet article fournit des informations sur l’utilisation du concepteur de formule dans les États électroniques (ER).
author: kfend
ms.date: 04/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 283c882300ece460c18ffebe572238e7629f8dee
ms.sourcegitcommit: a1d14836b40cfc556f045c6a0d2b4cc71064a6af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "9476799"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Concepteur de formule dans les états électroniques (ER)

[!include [banner](../includes/banner.md)]

Cet article décrit l’utilisation du concepteur de formule dans la génération d’états électroniques (ER). Lorsque vous créez un format pour un document électronique spécifique dans ER, vous pouvez utiliser des formules pour transformer les données afin qu’elles répondent aux exigences d’exécution et de mise en forme du document. Ces formules sont semblables aux formules dans Microsoft Excel. Plusieurs types de fonctions sont pris en charge dans les formules : texte, date et heure, mathématique, logique, informations, et des formules de conversion du type de données ainsi que d’autres fonctions spécifiques au domaine de métier.

## <a name="formula-designer-overview"></a>Vue d’ensemble du concepteur de formule

ER prend en charge le concepteur de formule. Par conséquent, au moment de la conception, vous pouvez configurer des expressions qui peuvent être utilisées pour les tâches suivantes au moment de l’exécution :

- Transformez les données provenant d’une base de données d’une application, et qui doivent être saisies dans un modèle de données ER conçues pour être une source de données pour les formats ER. (Par exemple, ces transformations peuvent inclure le filtrage, le regroupement et la conversion des types de données.)
- Mettre en forme des données qui doivent être émises vers un document électronique en cours de génération en accord avec la disposition et les conditions d’un format ER spécifique. (Par exemple, la mise en forme peut être effectuée en accord avec la langue, la culture ou le codage demandé.)
- Contrôler le processus de création de documents électroniques. (Par exemple, les expressions peuvent activer ou désactiver l’émission d’éléments spécifiques du format, en fonction des données de traitement. Elles peuvent également interrompre le processus de création du document ou envoyer des messages aux utilisateurs.)

Vous pouvez ouvrir la page **Concepteur de formule** lorsque vous effectuez l’une des actions suivantes :

- Lier des articles sources de données aux composants de modèle de données.
- Lier des articles sources de données aux composants de format.
- Effectuer la mise à jour des champs calculés dans le cadre des sources de données.
- Définir des conditions pour modifier et afficher les paramètres d’entrée utilisateur.
- Définir les valeurs par défaut pour les paramètres d’entrée utilisateur.
- Créer des transformations d’un format.
- Définir les conditions d’activation pour les composants du format.
- Définir les noms de fichiers pour les composants FICHIER du format.
- Définir les conditions des validations du contrôle de processus.
- Définir le texte de message des validations du contrôle de processus.

## <a name="data-binding"></a><a name="Binding"></a>Liaison de données

Le concepteur de formule ER permet de définir une expression qui transforme des données reçues des sources de données à saisir de la manière suivante dans le consommateur de données au moment de l’exécution :

- Des sources de données de l’application et des paramètres d’exécution à un modèle de données ER
- D’un modèle de données ER à un format ER
- Des sources de données de l’application et des paramètres d’exécution à un format ER

La figure suivante présente la création d’une expression de ce type. Dans cet exemple, l’expression arrondit la valeur du champ **Intrastat.AmountMST** dans la table Déclaration d’échanges de biens à deux décimales et retourne la valeur arrondie.

[![Expression de liaison de données.](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

La figure suivante présente l’utilisation d’une expression de ce type. Dans cet exemple, le résultat de l’expression conçue est saisi dans le composant **Transaction.InvoicedAmount** du modèle de données **Modèle de déclaration de taxe** .

[![Expression de liaison de données utilisée.](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

À l’exécution, la formule conçue, `ROUND (Intrastat.AmountMST, 2)`, arrondit la valeur du champ **AmountMST** pour chaque enregistrement de la table Déclaration d’échanges de biens à deux décimales. Elle saisit ensuite la valeur arrondie dans le composant **Transaction.InvoicedAmount** du modèle de données **Déclaration de taxe**.

## <a name="data-formatting"></a><a name="Transformation"></a>Mise en forme des données

Le concepteur de formule ER permet de définir une expression qui formate les données reçues des sources de données, afin que les données puissent être envoyées dans le cadre de la génération d’un document électronique. Vous disposez peut-être d’une mise en forme qui doit être appliquée comme règle classique pour être réutilisée pour un format. Dans ce cas, vous pouvez entrer cette mise en forme une fois dans la configuration du format comme transformation nommée ayant une expression de mise en forme. Cette transformation nommée peut ensuite être liée à de nombreux composants de format dont la sortie doit être mise en forme en fonction de l’expression de mise en forme créée.

La figure suivante présente la création d’une transformation de ce type. Dans cet exemple, la transformation **TrimmedString** tronque les données entrantes du type de données *Chaîne* en supprimant les espaces de début et de fin. Elle retourne ensuite la valeur de chaîne tronquée.

[![Transformation.](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

La figure suivante présente l’utilisation d’une transformation de ce type. Dans cet exemple, plusieurs composants de format envoient le texte comme résultat de la génération du document électronique au moment de l’exécution. Tous ces composants de format font référence à la transformation **TrimmedString** par son nom.

[![Transformation utilisée.](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Lorsque les composants de format, comme le composant **partyName** dans l’illustration précédente, font référence à la transformation **TrimmedString**, cette dernière renvoie le texte comme résultat de la génération du document électronique. Le texte n’inclut pas les espaces de début et de fin.

Si vous avez une mise en forme qui doit être appliquée individuellement, vous pouvez introduire cette mise en page en tant qu’expression individuelle d’une liaison d’un composant de format spécifique. La figure suivante présente une expression de ce type. Dans cet exemple, le composant de format **partyType** est lié à la source de données via une expression qui convertit les données entrantes du champ **Model.Company.RegistrationType** dans la source de données en texte en majuscules. L’expression envoie ensuite ce texte comme résultat dans le document électronique.

[![Application de la mise en forme à un composant individuel.](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>Contrôle des flux de processus

Le concepteur de formule ER permet de définir les expressions utilisées pour contrôler le flux de processus de génération de documents électroniques. Vous pouvez effectuer les tâches suivantes :

- Définir des conditions qui déterminent quand un processus de création de document doit être arrêté.
- Spécifier les expressions qui créent des messages pour l’utilisateur, relatifs aux processus arrêtés ou lancent des messages de journal d’exécution relatifs à la continuité du processus de génération d’états.
- Spécifier les noms de fichier de la génération de documents électroniques, et contrôler les conditions de leur création.

Chaque règle du contrôle des flux de processus est conçue comme un contrôle individuel. La figure suivante présente une validation de ce type. Voici une explication de la configuration dans cet exemple :

- La validation est évaluée lorsque le nœud **INSTAT** est créé lors de la génération du fichier XML.
- Si la liste des transactions est vide, la validation arrête le processus d’exécution et renvoie la valeur **FALSE**.
- La validation renvoie un message d’erreur qui inclut le texte du libellé SYS70894 dans la langue de l’utilisateur.

[![Validation.](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Le concepteur de formule ER peut également être utilisé pour générer un nom de fichier permettant de générer un document électronique et de contrôler le processus de création de fichier. La figure suivante présente la création d’un contrôle des flux de processus de ce type. Voici une explication de la configuration dans cet exemple :

- La liste des enregistrements de la source de données **model.Intrastat** est divisée en lots. Chaque lot contient jusqu’à 1 000 enregistrements.
- Le résultat crée un fichier zip qui contient un fichier au format XML pour chaque lot qui a été créé.
- Une expression renvoie un nom de fichier pour générer des documents électroniques en concaténant le nom de fichier et son extension. Pour le deuxième traitement par lots et tous les traitements par lots suivants, le nom de fichier contient l’ID traitement par lots comme suffixe.
- Une expression active (en renvoyant la valeur **TRUE**) le processus de création de fichier pour les lots contenant au moins un enregistrement.

[![Contrôle des flux de processus.](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>Contrôle du contenu des documents

Le concepteur de formule ER peut être utilisé pour configurer les expressions contrôlant quelles données sont placées dans les documents électroniques générés au moment de l’exécution. Les expressions peuvent activer ou désactiver l’émission d’éléments spécifiques du format, en fonction des données de traitement et de la logique configurée. Ces expressions peuvent être entrées pour un seul élément de format dans le champ **Activé** sur l’onglet **Mise en correspondance** sur la page **Concepteur des opérations**. Vous pouvez entrer les expressions sous la forme d’une condition logique retournant une valeur *Booléenne*:

- Si la condition renvoie **True**, l’élément de format actuel est exécuté.
- Si la condition renvoie **False**, l’élément de format actuel est ignoré.

La figure suivante présente des expressions de ce type. (La version 11.12.11 de la configuration de format du **Format du virement bancaire ISO20022 (NO)** fournie par Microsoft est utilisée comme exemple.) Le composant de format **XMLHeader** est configuré pour décrire la structure du message de virement selon les normes de message XML ISO 20022. Le composant de format **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** est configuré pour ajouter l’élément XML **Ustrd** au message généré et pour placer les informations de remise dans un format non structuré comme texte des éléments XML suivants :

- Le composant **PaymentNotes** est utilisé pour générer le texte des notes de paiement.
- Le composant **DelimitedSequence** génère les numéros de facture séparés par une virgule utilisés pour régler le transfert actuel de crédit.

[![Composants PaymentNotes et DelimitedSequence.](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> Les composants **PaymentNotes** et **DelimitedSequence** sont libellés à l’aide d’un point d’interrogation. Un point d’interrogation indique que l’utilisation d’un composant est conditionnelle. Dans ce cas, l’utilisation des composants est basée sur les critères suivants :
>
> - L’expression `@.PaymentsNotes <> ""` définie pour le composant **PaymentNotes**, active (en retournant **TRUE**) l’élément XML **Ustrd** à renseigner avec le texte des notes de paiement, si ce texte pour le virement actuel n’est pas vide.
>
>    [![Expression pour le composant PaymentNotes.](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - L’expression `@.PaymentsNotes = ""` définie pour le composant **DelimitedSequence** active (en retournant **TRUE**) l’élément **XML Ustrd** à renseigner avec une liste des numéros de facture séparés par une virgule qui sont utilisés pour régler le virement actuel si le texte des notes de paiement pour ce virement est vide.
>
>    [![Expression pour le composant DelimitedSequence.](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Selon cette configuration, le message généré pour chaque paiement de débit, l’élément XML **Ustrd**, contient soit le texte des notes de paiement soit, si ce texte est vide, une liste des numéros de facture séparés par une virgule utilisés pour régler le paiement.

## <a name="assistance-in-formulas-writing"></a>Assistance à la rédaction de formules

### <a name="data-sources-navigator"></a>Navigateur dans les sources de données

Vous pouvez modifier une formule qui représente un élément d’une source de données structurées. Lorsque vous avez configuré vos paramètres ER pour présenter le chemin d’accès à un élément d’une source de données structurée comme [chemin d’accès relatif](relative-path-data-bindings-er-models-format.md), le signe « arobase » (@) est [montré](er-formula-language.md#relative-path) dans la formule au lieu de la partie restante du chemin absolu de l’arborescence hiérarchique utilisée. Cette partie restante du chemin d’accès absolu pointe vers un élément parent de l’élément modifiable. Dans la version Finance **10.0.30 et versions ultérieures**, sur la page **Concepteur de formules**, dans le volet **Source de données**, vous pouvez sélectionner l’option **Accéder à @** pour positionner le curseur de l’arborescence des sources de données sur un élément qui est le parent de l’élément modifiable. La structure de tous les éléments ascendants réduits est automatiquement et récursivement développée, si nécessaire. Cette expansion peut vous aider à visualiser rapidement l’élément de base de l’élément modifiable, à observer les jumeaux de l’élément modifiable dans l’arborescence des sources de données et à utiliser chacun d’eux dans la formule modifiable, si nécessaire.

![Utilisez l’option « Accéder à @ » pour positionner le curseur de l’arborescence des sources de données sur un élément parent de l’élément modifiable sur la page Concepteur de formules.](./media/er_formula-designer-data-sources-navigator.gif)

### <a name="data-sources-picker"></a>Sélecteur de sources de données

Sur la page **Concepteur de formules**, dans le volet de gauche **Sources de données**, sélectionnez un élément d’une source de données que vous souhaitez intégrer à la formule modifiable. Puis sélectionnez **Ajouter une source de données**. Notez que l’élément sélectionné est ajouté au texte de la formule modifiable.

> [!TIP]
> Lorsque vous utilisez l’option **Ajouter une source de données** dans l’éditeur de formule par défaut, l’élément sélectionné est toujours ajouté à la fin du texte de la formule. Lorsque vous faites la même chose dans l’[éditeur de formule avancé](er-advanced-formula-editor.md), l’élément sélectionné est inséré dans le texte de la formule à la position actuelle du curseur.

### <a name="built-in-functions-picker"></a>Sélection de fonctions intégrées

Sur la page **Concepteur de formules**, dans le volet de droite **Fonctions**, sélectionnez une fonction intégrée ER que vous souhaitez intégrer à la formule modifiable. Puis, sélectionnez **Ajouter une fonction**. Notez que la fonction sélectionnée est ajoutée au texte de la formule modifiable.

> [!TIP]
> Lorsque vous utilisez l’option **Ajouter une fonction** dans l’éditeur de formule par défaut, la fonction sélectionnée est toujours ajoutée à la fin du texte de la formule. Lorsque vous faites la même chose dans l’[éditeur de formule avancé](er-advanced-formula-editor.md), la fonction sélectionnée est insérée dans le texte de la formule à la position actuelle du curseur.

### <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>Validation des formules configurées

Sur la page **Concepteur de formule**, sélectionnez **Tester** pour valider le fonctionnement de la formule configurée.

[![Sélection du test pour valider une formule.](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Lorsque les valeurs des arguments de formule sont requises, vous pouvez ouvrir la boîte de dialogue **Tester l’expression** sur la page **Concepteur de formule**. Dans la plupart des cas, ces arguments doivent être définis manuellement, car les liaisons configurées ne sont pas exécutées au moment de la conception. L’onglet **Résultat du test** sur la **Concepteur de formule** affiche le résultat de l’exécution de la formule configurée.

L’exemple suivant montre comment tester la formule configurée pour le domaine du commerce extérieur pour vous assurer que le code de marchandise de la déclaration d’échanges de biens ne contient que des chiffres.

Lorsque vous testez cette formule, vous pouvez utiliser la boîte de dialogue **Tester l’expression** pour spécifier la valeur du code de produit de la déclaration d’échanges de biens à tester.

[![Spécification du code de produit de la déclaration d’échanges de biens pour les tests.](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Après avoir spécifié le code de marchandise de la déclaration d’échanges de biens et sélectionné **OK**, l’onglet **Résultat du test** sur la page **Concepteur de formule** affiche le résultat de l’exécution de la formule configurée. Vous pouvez ensuite évaluer si le résultat est acceptable. Si le résultat n’est pas acceptable, vous pouvez mettre à jour la formule et la tester à nouveau.

[![Résultat de test.](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Certaines formules ne peuvent pas être testées au moment de la conception. Par exemple, une formule peut renvoyer le résultat d’un type de données qui ne peut pas être affiché sur l’onglet **Résultat du test**. Dans ce cas, vous recevez un message d’erreur indiquant que la formule ne peut pas être testée.

[![Message d’erreur.](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble des États électroniques](general-electronic-reporting.md)
- [Langage de formule dans la gestion des états électroniques](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
