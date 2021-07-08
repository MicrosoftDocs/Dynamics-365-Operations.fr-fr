---
title: Éditeur de formule avancé d’états électroniques
description: Cette rubrique décrit comment l’éditeur de formule avancé peut être utilisé pour configurer des expressions dans les composants de format et de mappage de modèles ER (états électroniques).
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f7f80928e1d3f5d4892f72d4bd2fd09b70a26c1f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270705"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="0ecc9-103">Éditeur de formule avancé d’états électroniques</span><span class="sxs-lookup"><span data-stu-id="0ecc9-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ecc9-104">En plus de l’[éditeur de formule ](general-electronic-reporting-formula-designer.md) d’[états électroniques](general-electronic-reporting.md), vous pouvez utiliser l’éditeur avancé de formule d’états électroniques pour améliorer l’expérience de configuration des expressions d’états électroniques (ER).</span><span class="sxs-lookup"><span data-stu-id="0ecc9-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="0ecc9-105">L’éditeur avancé est basé sur un navigateur et alimenté par l’[éditeur Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="0ecc9-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="0ecc9-106">Les fonctionnalités de l’éditeur avancé les plus couramment utilisées sont décrites dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="0ecc9-107">Mise en forme automatique du code</span><span class="sxs-lookup"><span data-stu-id="0ecc9-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="0ecc9-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="0ecc9-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="0ecc9-109">Remplissage de code</span><span class="sxs-lookup"><span data-stu-id="0ecc9-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="0ecc9-110">Navigation dans le code</span><span class="sxs-lookup"><span data-stu-id="0ecc9-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="0ecc9-111">Structuration du code</span><span class="sxs-lookup"><span data-stu-id="0ecc9-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="0ecc9-112">Rechercher et remplacer</span><span class="sxs-lookup"><span data-stu-id="0ecc9-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="0ecc9-113">Collage de données</span><span class="sxs-lookup"><span data-stu-id="0ecc9-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="0ecc9-114">Colorisation de la syntaxe</span><span class="sxs-lookup"><span data-stu-id="0ecc9-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="0ecc9-115"><a name="ActivateAdvEditor">Activer l’éditeur de formule avancé</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="0ecc9-116">Procédez comme suit pour commencer à utiliser l’éditeur de formule avancé dans votre instance de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="0ecc9-117">Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="0ecc9-118">Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="0ecc9-119">Dans la boîte de dialogue **Paramètres utilisateur** dans la section **Traçage d’exécution**, définissez le paramètre **Activer l’éditeur de formule avancé** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="0ecc9-120">[![Boîte de dialogue Paramètres utilisateur, paramètre Activer l’éditeur de formule avancé en surbrillance](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-120">[![User parameters dialog box, Enable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0ecc9-121">N’oubliez pas que ce paramètre est spécifique à l’utilisateur et à l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-121">Be aware that this parameter is user specific and company specific.</span></span>

<span data-ttu-id="0ecc9-122">À partir de Microsoft Dynamics 365 Finance version 10.0.19, vous pouvez contrôler quel éditeur de formule ER est proposé par défaut.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-122">Starting in Microsoft Dynamics 365 Finance version 10.0.19, you can control what ER formula editor is offered by default.</span></span> <span data-ttu-id="0ecc9-123">Effectuez les étapes suivantes pour activer l’éditeur de formule avancé pour tous les utilisateurs et sociétés de l’instance Finance actuelle.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-123">Complete the following steps to enable the advanced formula editor for all users and companies of the current Finance instance.</span></span>

1.  <span data-ttu-id="0ecc9-124">Ouvrez l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-124">Open the **Feature management** workspace.</span></span>
2.  <span data-ttu-id="0ecc9-125">Recherchez et sélectionnez la fonctionnalité **Définir l’éditeur de formule ER avancé comme éditeur par défaut pour tous les utilisateurs** dans la liste, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-125">Find and select the feature **Set the ER advanced formula editor as the default one for all users** in the list, and then select **Enable now**.</span></span>
3.  <span data-ttu-id="0ecc9-126">Accédez à **Administration d’organisation** > **États électroniques** > **Configurations**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-126">Go to **Organization administration** > **Electronic reporting** > **Configurations**.</span></span>
4.  <span data-ttu-id="0ecc9-127">Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-127">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
5.  <span data-ttu-id="0ecc9-128">Dans la boîte de dialogue **Paramètres utilisateur**, recherchez le paramètre **Désactiver l’éditeur de formule avancé** et vérifiez qu’il est défini sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-128">In the **User parameters** dialog box, find the **Disable advanced formula editor** parameter and verify that it is set to **No**.</span></span>

<span data-ttu-id="0ecc9-129">[![Boîte de dialogue Paramètres utilisateur, paramètre Désactiver l’éditeur de formule avancé en surbrillance](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-129">[![User parameters dialog box, Disable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0ecc9-130">Les valeurs des paramètres **Activer l’éditeur de formule avancé** et **Désactiver l’éditeur de formule avancé** sont conservés séparément pour chaque utilisateur et sont proposés dans la boîte de dialogue **Paramètres utilisateur** en fonction du statut de la fonctionnalité **Définir l’éditeur de formule ER avancé comme éditeur par défaut pour tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-130">The values of the parameters **Enable advanced formula editor** and **Disable advanced formula editor** are kept separate for each user and offered on the **User parameters** dialog box depending on the status of the **Set the ER advanced formula editor as the default one for all users** feature.</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-131"><a name="Autoformatting">Mise en forme automatique du code</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-131"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="0ecc9-132">Lorsque vous écrivez une expression complexe qui se compose de plusieurs lignes de code, le retrait d’une nouvelle ligne entrée sera automatique en fonction de celui de la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-132">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="0ecc9-133">Vous pouvez sélectionner des lignes et modifier leur retrait en tapant sur **Tab** ou **Maj + Tab**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-133">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="0ecc9-134">[![GIF de l’éditeur de formule ER montrant la sélection de lignes et la modification de l’indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-134">[![ER formula editor gif showing selecting lines and changing the indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="0ecc9-135">La mise en forme automatique vous permet de conserver l’expression entière bien formatée pour faciliter la maintenance et simplifier la compréhension de la logique configurée.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-135">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-136"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-136"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="0ecc9-137">L’éditeur fournit une saisie de mots pour vous aider à écrire l’expression plus rapidement et à éviter les fautes de frappe.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-137">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="0ecc9-138">Lorsque vous commencez à ajouter du nouveau texte, l’éditeur propose automatiquement une liste des fonctions prises en charge dans les fonctions ER qui contiennent les caractères que vous avez saisis.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-138">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="0ecc9-139">Vous pouvez également déclencher IntelliSense à n’importe quel endroit d’une expression configurée en tapant sur **Ctrl + Espace**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-139">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="0ecc9-140">[![GIF de l’éditeur de formule ER montrant le déclenchement d’IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-140">[![ER formula editor gif showing triggering IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-141"><a name="CodeCompletion">Remplissage de code</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-141"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="0ecc9-142">L’éditeur fournit automatiquement le remplissage de code comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-142">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="0ecc9-143">En insérant un crochet de fermeture lorsqu’un crochet d’ouverture est entré, en gardant le curseur à l’intérieur des crochets.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-143">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="0ecc9-144">En insérant le deuxième symbole de guillemet lorsque le premier est entré, en gardant le curseur à l’intérieur des guillemets.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-144">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="0ecc9-145">En insérant le deuxième symbole de guillemets doubles lorsque le premier est entré, en gardant le curseur à l’intérieur des guillemets.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-145">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="0ecc9-146">[![GIF de l’éditeur de formule ER montrant l’éditeur assurant la saisie automatique du code](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-146">[![ER formula editor gif showing the editor automatically providing code completion](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="0ecc9-147">Lorsque vous pointez sur le crochet tapé, le deuxième crochet de cette paire est automatiquement mis en surbrillance pour afficher la construction qu’ils prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-147">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-148"><a name="CodeNavigation">Navigation dans le code</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-148"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="0ecc9-149">Vous pouvez localiser les symboles ou les lignes requis dans votre expression en tapant la commande **Aller à** à l’aide de la palette de commandes ou du menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-149">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="0ecc9-150">Par exemple, pour passer à la ligne **8**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-150">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="0ecc9-151">Appuyez sur **Ctrl + G**, entrez la valeur **8**, puis appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-151">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="0ecc9-152">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-152">-or-</span></span>

- <span data-ttu-id="0ecc9-153">Appuyez sur **F1**, tapez **G**, sélectionnez **Aller à la ligne**, entrez la valeur **8** et appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-153">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="0ecc9-154">[![GIF de l’éditeur de formule ER montrant comment localiser des parties d’une expression à l’aide de la palette de commandes](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-154">[![ER formula editor gif showing how to locate parts of an expression using the command palette](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-155"><a name="CodeStructuring">Structuration du code</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-155"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="0ecc9-156">Le code de certaines fonctions, telles que [SI](er-functions-logical-if.md) ou [CAS](er-functions-logical-case.md), est automatiquement structuré.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-156">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="0ecc9-157">Vous pouvez développer et réduire une ou toutes les régions de pliage de ce code pour réduire la partie modifiable d’une expression afin de vous concentrer uniquement sur l’élément de code qui nécessite votre attention.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-157">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="0ecc9-158">Les commandes bascules plier/déplier peuvent être utilisées pour cela.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-158">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="0ecc9-159">Par exemple, pour plier toutes les régions, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-159">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="0ecc9-160">Appuyez sur **Ctrl + K**</span><span class="sxs-lookup"><span data-stu-id="0ecc9-160">Press **Ctrl+K**</span></span>

  <span data-ttu-id="0ecc9-161">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-161">-or-</span></span>

- <span data-ttu-id="0ecc9-162">Appuyez sur **F1**, appuyez sur **FO**, sélectionnez **Pliez tout**, puis appuyez sur **Entrée**</span><span class="sxs-lookup"><span data-stu-id="0ecc9-162">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="0ecc9-163">Pour déplier toutes les régions, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-163">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="0ecc9-164">Appuyez sur **Ctrl + J**</span><span class="sxs-lookup"><span data-stu-id="0ecc9-164">Press **Ctrl+J**</span></span>

  <span data-ttu-id="0ecc9-165">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-165">-or-</span></span>
  
- <span data-ttu-id="0ecc9-166">Appuyez sur **F1**, tapez **UN**, sélectionnez **Déplier tout**, puis appuyez sur **Entrée**</span><span class="sxs-lookup"><span data-stu-id="0ecc9-166">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="0ecc9-167">[![GIF de l’éditeur de formule ER montrant le dépliement du code](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-167">[![ER formula editor gif showing code being unfolded](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-168"><a name="FindAndReplace">Rechercher et remplacer</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-168"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="0ecc9-169">Pour rechercher des occurrences de certains textes, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-169">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="0ecc9-170">Appuyez sur **Ctrl + F** puis sur **F3** pour trouver l’occurrence suivante du texte sélectionné, ou appuyez sur **Maj + F3** pour trouver l’occurrence précédente.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-170">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="0ecc9-171">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-171">-or-</span></span>
  
- <span data-ttu-id="0ecc9-172">Appuyez sur **F1**, tapez **F**, puis sélectionnez l’option requise pour rechercher le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-172">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="0ecc9-173">Pour remplacer des occurrences d’un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-173">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="0ecc9-174">Appuyez sur **Ctrl + H**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-174">Press **Ctrl+H**.</span></span> <span data-ttu-id="0ecc9-175">Entrez le texte alternatif et sélectionnez l’option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l’expression actuelle.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-175">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="0ecc9-176">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-176">-or-</span></span>
  
- <span data-ttu-id="0ecc9-177">Appuyez sur **F1**, tapez **R**, puis sélectionnez l’option requise pour remplacer le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-177">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="0ecc9-178">Entrez le texte alternatif et sélectionnez l’option de remplacement pour remplacer le texte sélectionné ou toutes les occurrences de ce texte dans l’expression actuelle.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-178">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="0ecc9-179">Pour modifier toutes les occurrences d’un certain texte, sélectionnez le texte dans votre expression et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-179">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="0ecc9-180">Appuyez sur **Ctrl + F2** puis entrez le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-180">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="0ecc9-181">- ou -</span><span class="sxs-lookup"><span data-stu-id="0ecc9-181">-or-</span></span>
  
- <span data-ttu-id="0ecc9-182">Appuyez sur **F1**, tapez **C**, puis sélectionnez l’option requise pour modifier le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-182">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="0ecc9-183">Saisissez le texte de remplacement.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-183">Enter the alternative text.</span></span>

<span data-ttu-id="0ecc9-184">[![GIF de l’éditeur de formule ER montrant la fonction Rechercher et remplacer](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-184">[![ER formula editor gif showing find and replace](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-185"><a name="DataPasting">Collage des fonctions et des sources de données</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-185"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="0ecc9-186">Vous pouvez sélectionner **Ajouter une source de données**, qui colle à l’expression actuelle une source de données actuellement sélectionnée sur le volet de gauche **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-186">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="0ecc9-187">Vous pouvez de même sélectionner **Ajouter une fonction**, qui colle à l’expression actuelle une fonction actuellement sélectionnée sur le volet de droite **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-187">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="0ecc9-188">Si vous utilisez l’éditeur de formule ER, une fonction sélectionnée ou une source de données sélectionnée sera toujours collée à la fin de l’expression configurée.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-188">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="0ecc9-189">Lorsque vous utilisez l’éditeur de formule ER avancé, une fonction sélectionnée ou une source de données sélectionnée peut être collée à n’importe quelle partie de l’expression configurée.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-189">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="0ecc9-190">Vous devrez utiliser le curseur pour spécifier où vous souhaitez coller les données.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-190">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="0ecc9-191">[![GIF de l’éditeur de formule ER montrant l’ajout d’une source de données et le collage d’une fonction](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-191">[![ER formula editor gif showing adding a data source and pasting a function](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="0ecc9-192"><a name="SyntaxColorization">Colorisation de la syntaxe</a></span><span class="sxs-lookup"><span data-stu-id="0ecc9-192"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="0ecc9-193">Actuellement, différentes couleurs sont utilisées pour mettre en évidence les parties d’expressions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-193">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="0ecc9-194">Le texte entre crochets doubles pouvant représenter un ID d’étiquette d’un texte constant.</span><span class="sxs-lookup"><span data-stu-id="0ecc9-194">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="0ecc9-195">[![Éditeur de formule ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="0ecc9-195">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="0ecc9-196">Limitations</span><span class="sxs-lookup"><span data-stu-id="0ecc9-196">Limitations</span></span>

<span data-ttu-id="0ecc9-197">L’éditeur est actuellement pris en charge dans les navigateurs Web suivants :</span><span class="sxs-lookup"><span data-stu-id="0ecc9-197">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="0ecc9-198">Chrome</span><span class="sxs-lookup"><span data-stu-id="0ecc9-198">Chrome</span></span>
- <span data-ttu-id="0ecc9-199">Bord</span><span class="sxs-lookup"><span data-stu-id="0ecc9-199">Edge</span></span>
- <span data-ttu-id="0ecc9-200">Firefox</span><span class="sxs-lookup"><span data-stu-id="0ecc9-200">Firefox</span></span>
- <span data-ttu-id="0ecc9-201">Opera</span><span class="sxs-lookup"><span data-stu-id="0ecc9-201">Opera</span></span>
- <span data-ttu-id="0ecc9-202">Safari</span><span class="sxs-lookup"><span data-stu-id="0ecc9-202">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ecc9-203">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0ecc9-203">Additional resources</span></span>

- [<span data-ttu-id="0ecc9-204">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="0ecc9-204">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="0ecc9-205">Concepteur de formule dans la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="0ecc9-205">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="0ecc9-206">Éditeur Monaco</span><span class="sxs-lookup"><span data-stu-id="0ecc9-206">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
