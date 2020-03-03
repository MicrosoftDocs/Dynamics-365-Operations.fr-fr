---
title: Éditeur de formule avancé d'états électroniques
description: Cette rubrique décrit comment l'éditeur de formule avancé peut être utilisé pour configurer des expressions dans les composants de format et de mappage de modèles ER (états électroniques).
author: NickSelin
manager: AnnBe
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d183f77da1dda0c4f04e4e48ab3db0133f494a55
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015213"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Éditeur de formule avancé d'états électroniques

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

En plus de l'[éditeur de formule ](general-electronic-reporting-formula-designer.md) d'[états électroniques](general-electronic-reporting.md), vous pouvez utiliser l'éditeur avancé de formule d'états électroniques pour améliorer l'expérience de configuration des expressions d'états électroniques (ER). L'éditeur avancé est basé sur un navigateur et alimenté par l'[éditeur Monaco](https://microsoft.github.io/monaco-editor). Les fonctionnalités de l'éditeur avancé les plus couramment utilisées sont décrites dans cette rubrique :

- [Mise en forme automatique du code](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Remplissage de code](#CodeCompletion)
- [Navigation dans le code](#CodeNavigation)
- [Structuration du code](#CodeStructuring)
- [Rechercher et remplacer](#FindAndReplace)
- [Collage de données](#DataPasting)
- [Colorisation de la syntaxe](#SyntaxColorization)

## <a name="ActivateAdvEditor">Activer l'éditeur de formule avancé</a>

Procédez comme suit pour commencer à utiliser l'éditeur de formule avancé dans votre instance de Microsoft Dynamics 365 Finance.

1.  Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.
2.  Dans la page **Configurations** , dans le volet Actions, sous l'onglet **Configurations** , dans le groupe **Paramètres avancés** , sélectionnez **Paramètres utilisateur**.
3.  Dans la boîte de dialogue **Paramètres utilisateur** dans la section **Traçage d'exécution** , définissez le paramètre **Activer l'éditeur de formule avancé** sur **Oui**.

[![Page Configurations d'ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> N'oubliez pas que ce paramètre est spécifique à l'utilisateur et à l'entreprise.

## <a name="Autoformatting">Mise en forme automatique du code</a>

Lorsque vous écrivez une expression complexe qui se compose de plusieurs lignes de code, le retrait d'une nouvelle ligne entrée sera automatique en fonction de celui de la ligne précédente. Vous pouvez sélectionner des lignes et modifier leur retrait en tapant sur **Tab** ou **Maj + Tab**.

[![Éditeur de formule ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

La mise en forme automatique vous permet de conserver l'expression entière bien formatée pour faciliter la maintenance et simplifier la compréhension de la logique configurée.

## <a name="IntelliSense">IntelliSense</a>

L'éditeur fournit une saisie de mots pour vous aider à écrire l'expression plus rapidement et à éviter les fautes de frappe. Lorsque vous commencez à ajouter du nouveau texte, l'éditeur propose automatiquement une liste des fonctions prises en charge dans les fonctions ER qui contiennent les caractères que vous avez saisis. Vous pouvez également déclencher IntelliSense à n'importe quel endroit d'une expression configurée en tapant sur **Ctrl + Espace**.

[![Éditeur de formule ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name="CodeCompletion">Remplissage de code</a>

L'éditeur fournit automatiquement le remplissage de code comme suit :

- En insérant un crochet de fermeture lorsqu'un crochet d'ouverture est entré, en gardant le curseur à l'intérieur des crochets.
- En insérant le deuxième symbole de guillemet lorsque le premier est entré, en gardant le curseur à l'intérieur des guillemets.
- En insérant le deuxième symbole de guillemets doubles lorsque le premier est entré, en gardant le curseur à l'intérieur des guillemets.

[![Éditeur de formule ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Lorsque vous pointez sur le crochet tapé, le deuxième crochet de cette paire est automatiquement mis en surbrillance pour afficher la construction qu'ils prennent en charge.

## <a name="CodeNavigation">Navigation dans le code</a>

Vous pouvez localiser les symboles ou les lignes requis dans votre expression en tapant la commande **Aller à** à l'aide de la palette de commandes ou du menu contextuel.

Par exemple, pour passer à la ligne **8**, procédez comme suit :

- Appuyez sur **Ctrl + G**, entrez la valeur **8**, puis appuyez sur **Entrée**.

  - ou -

- Appuyez sur **F1**, tapez **G**, sélectionnez **Aller à la ligne**, entrez la valeur **8** et appuyez sur **Entrée**.

[![Éditeur de formule ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name="CodeStructuring">Structuration du code</a>

Le code de certaines fonctions, telles que [SI](er-functions-logical-if.md) ou [CAS](er-functions-logical-case.md), est automatiquement structuré. Vous pouvez développer et réduire une ou toutes les régions de pliage de ce code pour réduire la partie modifiable d'une expression afin de vous concentrer uniquement sur l'élément de code qui nécessite votre attention. Les commandes bascules plier/déplier peuvent être utilisées pour cela.

Par exemple, pour plier toutes les régions, procédez comme suit :

- Appuyez sur **Ctrl + K**

  - ou -

- Appuyez sur **F1**, appuyez sur **FO**, sélectionnez **Pliez tout**, puis appuyez sur **Entrée**

Pour déplier toutes les régions, procédez comme suit :

- Appuyez sur **Ctrl + J**

  - ou -
  
- Appuyez sur **F1**, tapez **UN**, sélectionnez **Déplier tout**, puis appuyez sur **Entrée**

[![Éditeur de formule ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name="FindAndReplace">Rechercher et remplacer</a>

Pour rechercher des occurrences de certains textes, sélectionnez le texte dans votre expression et procédez comme suit :

- Appuyez sur **Ctrl + F** puis sur **F3** pour trouver l'occurrence suivante du texte sélectionné, ou appuyez sur **Maj + F3** pour trouver l'occurrence précédente.

  - ou -
  
- Appuyez sur **F1**, tapez **F**, puis sélectionnez l'option requise pour rechercher le texte sélectionné.

Pour remplacer des occurrences d'un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :

- Appuyez sur **Ctrl + H**. Entrez le texte alternatif et sélectionnez l'option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l'expression actuelle.

  - ou -
  
- Appuyez sur **F1**, tapez **R**, puis sélectionnez l'option requise pour remplacer le texte sélectionné. Entrez le texte alternatif et sélectionnez l'option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l'expression actuelle.

Pour modifier toutes les occurrences d'un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :

- Appuyez sur **Ctrl + F2** puis entrez le texte de remplacement.

  - ou -
  
- Appuyez sur **F1**, tapez **C**, puis sélectionnez l'option requise pour modifier le texte sélectionné. Saisissez le texte de remplacement.

[![Éditeur de formule ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name="DataPasting">Collage des fonctions et des sources de données</a>

Vous pouvez sélectionner **Ajouter une source de données**, qui colle à l'expression actuelle une source de données actuellement sélectionnée sur le volet de gauche **Source de données**. Vous pouvez de même sélectionner **Ajouter une fonction**, qui colle à l'expression actuelle une fonction actuellement sélectionnée sur le volet de droite **Fonctions**. Si vous utilisez l'éditeur de formule ER, une fonction sélectionnée ou une source de données sélectionnée sera toujours collée à la fin de l'expression configurée. Lorsque vous utilisez l'éditeur de formule ER avancé, une fonction sélectionnée ou une source de données sélectionnée peut être collée à n'importe quelle partie de l'expression configurée. Vous devrez utiliser le curseur pour spécifier où vous souhaitez coller les données.

[![Éditeur de formule ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name="SyntaxColorization">Colorisation de la syntaxe</a>

Actuellement, différentes couleurs sont utilisées pour mettre en évidence les parties d'expressions suivantes :

- Le texte entre crochets doubles pouvant représenter un ID d'étiquette d'un texte constant.

[![Éditeur de formule ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des états électroniques](general-electronic-reporting.md)
- [Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)
- [Éditeur Monaco](https://microsoft.github.io/monaco-editor)