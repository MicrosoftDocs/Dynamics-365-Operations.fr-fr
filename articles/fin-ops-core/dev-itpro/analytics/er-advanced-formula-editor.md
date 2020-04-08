---
title: Éditeur de formule avancé d'états électroniques
description: Cette rubrique décrit comment l'éditeur de formule avancé peut être utilisé pour configurer des expressions dans les composants de format et de mappage de modèles ER (états électroniques).
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
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
ms.openlocfilehash: df402bc20753d2ba14295592f4b40e20f9fdc7bf
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138896"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="24e31-103">Éditeur de formule avancé d'états électroniques</span><span class="sxs-lookup"><span data-stu-id="24e31-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24e31-104">En plus de l'[éditeur de formule ](general-electronic-reporting-formula-designer.md) d'[états électroniques](general-electronic-reporting.md), vous pouvez utiliser l'éditeur avancé de formule d'états électroniques pour améliorer l'expérience de configuration des expressions d'états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="24e31-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="24e31-105">L'éditeur avancé est basé sur un navigateur et alimenté par l'[éditeur Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="24e31-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="24e31-106">Les fonctionnalités de l'éditeur avancé les plus couramment utilisées sont décrites dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="24e31-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="24e31-107">Mise en forme automatique du code</span><span class="sxs-lookup"><span data-stu-id="24e31-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="24e31-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="24e31-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="24e31-109">Remplissage de code</span><span class="sxs-lookup"><span data-stu-id="24e31-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="24e31-110">Navigation dans le code</span><span class="sxs-lookup"><span data-stu-id="24e31-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="24e31-111">Structuration du code</span><span class="sxs-lookup"><span data-stu-id="24e31-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="24e31-112">Rechercher et remplacer</span><span class="sxs-lookup"><span data-stu-id="24e31-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="24e31-113">Collage de données</span><span class="sxs-lookup"><span data-stu-id="24e31-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="24e31-114">Colorisation de la syntaxe</span><span class="sxs-lookup"><span data-stu-id="24e31-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="24e31-115"><a name="ActivateAdvEditor">Activer l'éditeur de formule avancé</a></span><span class="sxs-lookup"><span data-stu-id="24e31-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="24e31-116">Procédez comme suit pour commencer à utiliser l'éditeur de formule avancé dans votre instance de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="24e31-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="24e31-117">Accédez à **Administration d'organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="24e31-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="24e31-118">Dans la page **Configurations** , dans le volet Actions, sous l'onglet **Configurations** , dans le groupe **Paramètres avancés** , sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="24e31-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="24e31-119">Dans la boîte de dialogue **Paramètres utilisateur** dans la section **Traçage d'exécution** , définissez le paramètre **Activer l'éditeur de formule avancé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="24e31-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="24e31-120">[![Page Configurations d'ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="24e31-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="24e31-121">N'oubliez pas que ce paramètre est spécifique à l'utilisateur et à l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="24e31-121">Be aware that this parameter is user specific and company specific.</span></span>

## <a name=""></a><span data-ttu-id="24e31-122"><a name="Autoformatting">Mise en forme automatique du code</a></span><span class="sxs-lookup"><span data-stu-id="24e31-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="24e31-123">Lorsque vous écrivez une expression complexe qui se compose de plusieurs lignes de code, le retrait d'une nouvelle ligne entrée sera automatique en fonction de celui de la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="24e31-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="24e31-124">Vous pouvez sélectionner des lignes et modifier leur retrait en tapant sur **Tab** ou **Maj + Tab**.</span><span class="sxs-lookup"><span data-stu-id="24e31-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="24e31-125">[![Éditeur de formule ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="24e31-126">La mise en forme automatique vous permet de conserver l'expression entière bien formatée pour faciliter la maintenance et simplifier la compréhension de la logique configurée.</span><span class="sxs-lookup"><span data-stu-id="24e31-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="24e31-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="24e31-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="24e31-128">L'éditeur fournit une saisie de mots pour vous aider à écrire l'expression plus rapidement et à éviter les fautes de frappe.</span><span class="sxs-lookup"><span data-stu-id="24e31-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="24e31-129">Lorsque vous commencez à ajouter du nouveau texte, l'éditeur propose automatiquement une liste des fonctions prises en charge dans les fonctions ER qui contiennent les caractères que vous avez saisis.</span><span class="sxs-lookup"><span data-stu-id="24e31-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="24e31-130">Vous pouvez également déclencher IntelliSense à n'importe quel endroit d'une expression configurée en tapant sur **Ctrl + Espace**.</span><span class="sxs-lookup"><span data-stu-id="24e31-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="24e31-131">[![Éditeur de formule ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="24e31-132"><a name="CodeCompletion">Remplissage de code</a></span><span class="sxs-lookup"><span data-stu-id="24e31-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="24e31-133">L'éditeur fournit automatiquement le remplissage de code comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="24e31-134">En insérant un crochet de fermeture lorsqu'un crochet d'ouverture est entré, en gardant le curseur à l'intérieur des crochets.</span><span class="sxs-lookup"><span data-stu-id="24e31-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="24e31-135">En insérant le deuxième symbole de guillemet lorsque le premier est entré, en gardant le curseur à l'intérieur des guillemets.</span><span class="sxs-lookup"><span data-stu-id="24e31-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="24e31-136">En insérant le deuxième symbole de guillemets doubles lorsque le premier est entré, en gardant le curseur à l'intérieur des guillemets.</span><span class="sxs-lookup"><span data-stu-id="24e31-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="24e31-137">[![Éditeur de formule ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="24e31-138">Lorsque vous pointez sur le crochet tapé, le deuxième crochet de cette paire est automatiquement mis en surbrillance pour afficher la construction qu'ils prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="24e31-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="24e31-139"><a name="CodeNavigation">Navigation dans le code</a></span><span class="sxs-lookup"><span data-stu-id="24e31-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="24e31-140">Vous pouvez localiser les symboles ou les lignes requis dans votre expression en tapant la commande **Aller à** à l'aide de la palette de commandes ou du menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="24e31-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="24e31-141">Par exemple, pour passer à la ligne **8**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="24e31-142">Appuyez sur **Ctrl + G**, entrez la valeur **8**, puis appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="24e31-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="24e31-143">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-143">-or-</span></span>

- <span data-ttu-id="24e31-144">Appuyez sur **F1**, tapez **G**, sélectionnez **Aller à la ligne**, entrez la valeur **8** et appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="24e31-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="24e31-145">[![Éditeur de formule ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="24e31-146"><a name="CodeStructuring">Structuration du code</a></span><span class="sxs-lookup"><span data-stu-id="24e31-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="24e31-147">Le code de certaines fonctions, telles que [SI](er-functions-logical-if.md) ou [CAS](er-functions-logical-case.md), est automatiquement structuré.</span><span class="sxs-lookup"><span data-stu-id="24e31-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="24e31-148">Vous pouvez développer et réduire une ou toutes les régions de pliage de ce code pour réduire la partie modifiable d'une expression afin de vous concentrer uniquement sur l'élément de code qui nécessite votre attention.</span><span class="sxs-lookup"><span data-stu-id="24e31-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="24e31-149">Les commandes bascules plier/déplier peuvent être utilisées pour cela.</span><span class="sxs-lookup"><span data-stu-id="24e31-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="24e31-150">Par exemple, pour plier toutes les régions, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="24e31-151">Appuyez sur **Ctrl + K**</span><span class="sxs-lookup"><span data-stu-id="24e31-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="24e31-152">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-152">-or-</span></span>

- <span data-ttu-id="24e31-153">Appuyez sur **F1**, appuyez sur **FO**, sélectionnez **Pliez tout**, puis appuyez sur **Entrée**</span><span class="sxs-lookup"><span data-stu-id="24e31-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="24e31-154">Pour déplier toutes les régions, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="24e31-155">Appuyez sur **Ctrl + J**</span><span class="sxs-lookup"><span data-stu-id="24e31-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="24e31-156">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-156">-or-</span></span>
  
- <span data-ttu-id="24e31-157">Appuyez sur **F1**, tapez **UN**, sélectionnez **Déplier tout**, puis appuyez sur **Entrée**</span><span class="sxs-lookup"><span data-stu-id="24e31-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="24e31-158">[![Éditeur de formule ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="24e31-159"><a name="FindAndReplace">Rechercher et remplacer</a></span><span class="sxs-lookup"><span data-stu-id="24e31-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="24e31-160">Pour rechercher des occurrences de certains textes, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="24e31-161">Appuyez sur **Ctrl + F** puis sur **F3** pour trouver l'occurrence suivante du texte sélectionné, ou appuyez sur **Maj + F3** pour trouver l'occurrence précédente.</span><span class="sxs-lookup"><span data-stu-id="24e31-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="24e31-162">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-162">-or-</span></span>
  
- <span data-ttu-id="24e31-163">Appuyez sur **F1**, tapez **F**, puis sélectionnez l'option requise pour rechercher le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="24e31-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="24e31-164">Pour remplacer des occurrences d'un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="24e31-165">Appuyez sur **Ctrl + H**.</span><span class="sxs-lookup"><span data-stu-id="24e31-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="24e31-166">Entrez le texte alternatif et sélectionnez l'option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l'expression actuelle.</span><span class="sxs-lookup"><span data-stu-id="24e31-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="24e31-167">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-167">-or-</span></span>
  
- <span data-ttu-id="24e31-168">Appuyez sur **F1**, tapez **R**, puis sélectionnez l'option requise pour remplacer le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="24e31-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="24e31-169">Entrez le texte alternatif et sélectionnez l'option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l'expression actuelle.</span><span class="sxs-lookup"><span data-stu-id="24e31-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="24e31-170">Pour modifier toutes les occurrences d'un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="24e31-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="24e31-171">Appuyez sur **Ctrl + F2** puis entrez le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="24e31-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="24e31-172">- ou -</span><span class="sxs-lookup"><span data-stu-id="24e31-172">-or-</span></span>
  
- <span data-ttu-id="24e31-173">Appuyez sur **F1**, tapez **C**, puis sélectionnez l'option requise pour modifier le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="24e31-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="24e31-174">Saisissez le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="24e31-174">Enter the alternative text.</span></span>

<span data-ttu-id="24e31-175">[![Éditeur de formule ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="24e31-176"><a name="DataPasting">Collage des fonctions et des sources de données</a></span><span class="sxs-lookup"><span data-stu-id="24e31-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="24e31-177">Vous pouvez sélectionner **Ajouter une source de données**, qui colle à l'expression actuelle une source de données actuellement sélectionnée sur le volet de gauche **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="24e31-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="24e31-178">Vous pouvez de même sélectionner **Ajouter une fonction**, qui colle à l'expression actuelle une fonction actuellement sélectionnée sur le volet de droite **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="24e31-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="24e31-179">Si vous utilisez l'éditeur de formule ER, une fonction sélectionnée ou une source de données sélectionnée sera toujours collée à la fin de l'expression configurée.</span><span class="sxs-lookup"><span data-stu-id="24e31-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="24e31-180">Lorsque vous utilisez l'éditeur de formule ER avancé, une fonction sélectionnée ou une source de données sélectionnée peut être collée à n'importe quelle partie de l'expression configurée.</span><span class="sxs-lookup"><span data-stu-id="24e31-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="24e31-181">Vous devrez utiliser le curseur pour spécifier où vous souhaitez coller les données.</span><span class="sxs-lookup"><span data-stu-id="24e31-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="24e31-182">[![Éditeur de formule ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="24e31-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="24e31-183"><a name="SyntaxColorization">Colorisation de la syntaxe</a></span><span class="sxs-lookup"><span data-stu-id="24e31-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="24e31-184">Actuellement, différentes couleurs sont utilisées pour mettre en évidence les parties d'expressions suivantes :</span><span class="sxs-lookup"><span data-stu-id="24e31-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="24e31-185">Le texte entre crochets doubles pouvant représenter un ID d'étiquette d'un texte constant.</span><span class="sxs-lookup"><span data-stu-id="24e31-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="24e31-186">[![Éditeur de formule ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="24e31-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24e31-187">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="24e31-187">Additional resources</span></span>

- [<span data-ttu-id="24e31-188">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="24e31-188">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="24e31-189">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="24e31-189">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="24e31-190">Éditeur Monaco</span><span class="sxs-lookup"><span data-stu-id="24e31-190">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)
