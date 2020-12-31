---
title: Fonction LISTOFFIELDS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTOFFIELDS États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d8d9f41d6ee5256f560c83486c95ecd47f5b081
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686510"
---
# <a name="listoffields-er-function"></a><span data-ttu-id="ec4b1-103">Fonction LISTOFFIELDS ER</span><span class="sxs-lookup"><span data-stu-id="ec4b1-103">LISTOFFIELDS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec4b1-104">La fonction `LISTOFFIELDS` renvoie une valeur *Liste des enregistrements* créée en fonction de la structure de l’argument spécifié du type *Énumération* ou *Conteneur (enregistrement)*.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="ec4b1-105">Syntaxe 1</span><span class="sxs-lookup"><span data-stu-id="ec4b1-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="ec4b1-106">Syntaxe 2</span><span class="sxs-lookup"><span data-stu-id="ec4b1-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="ec4b1-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="ec4b1-107">Arguments</span></span>

<span data-ttu-id="ec4b1-108">`path` : Référence de source de données</span><span class="sxs-lookup"><span data-stu-id="ec4b1-108">`path`: Data source reference</span></span>

<span data-ttu-id="ec4b1-109">Chemin d’accès de référence valide d’une source de données de l’un des types de données suivants :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="ec4b1-110">Énumération du modèle</span><span class="sxs-lookup"><span data-stu-id="ec4b1-110">Model enumeration</span></span>
- <span data-ttu-id="ec4b1-111">Énumération de format</span><span class="sxs-lookup"><span data-stu-id="ec4b1-111">Format enumeration</span></span>
- <span data-ttu-id="ec4b1-112">Énumération des applications</span><span class="sxs-lookup"><span data-stu-id="ec4b1-112">Application enumeration</span></span>
- <span data-ttu-id="ec4b1-113">Conteneur (enregistrement)</span><span class="sxs-lookup"><span data-stu-id="ec4b1-113">Container (record)</span></span>

<span data-ttu-id="ec4b1-114">`language` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="ec4b1-114">`language`: *String*</span></span>

<span data-ttu-id="ec4b1-115">Texte qui représente un code de langue.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="ec4b1-116">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="ec4b1-116">Return values</span></span>

<span data-ttu-id="ec4b1-117">*Liste d’enregistrements*</span><span class="sxs-lookup"><span data-stu-id="ec4b1-117">*Record list*</span></span>

<span data-ttu-id="ec4b1-118">Liste des enregistrements résultante.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ec4b1-119">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="ec4b1-119">Usage notes</span></span>

<span data-ttu-id="ec4b1-120">La liste créée comprend des enregistrements avec les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="ec4b1-121">**Nom** (type de données *Chaîne*)</span><span class="sxs-lookup"><span data-stu-id="ec4b1-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="ec4b1-122">**Étiquette** (type de données *Chaîne*)</span><span class="sxs-lookup"><span data-stu-id="ec4b1-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="ec4b1-123">**Description** (type de données *Chaîne*)</span><span class="sxs-lookup"><span data-stu-id="ec4b1-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="ec4b1-124">**IsTranslated** (type de données *Booléen*)</span><span class="sxs-lookup"><span data-stu-id="ec4b1-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="ec4b1-125">Si l’argument `path` fait référence à une source de données de type *Conteneur (enregistrement)*, pour chaque champ de l’enregistrement de conteneur référencé, un nouvel enregistrement est ajouté à la liste qui est créée.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="ec4b1-126">Pour chaque enregistrement créé, le champ **Nom** renvoie le nom du champ de l’enregistrement de conteneur référencé pour lequel l’enregistrement en cours a été créé.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="ec4b1-127">Si l’argument `path` fait référence à une source de données de l’un des types *Énumération*, pour chaque valeur d’énumération de l’énumération référencée, un nouvel enregistrement est ajouté à la liste qui est créée.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="ec4b1-128">Pour chaque enregistrement créé, le champ **Nom** renvoie la valeur de l’énumération référencée pour laquelle l’enregistrement en cours a été créé, le champ **Description** renvoie la description de cette énumération et le champ **Étiquette** renvoie l’étiquette de cette énumération.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="ec4b1-129">Au moment de l’exécution, lorsque la syntaxe 1 est utilisée, les champs **Étiquette** et **Description** doivent renvoyer des valeurs basées sur les paramètres de langue du format d’états électroniques (ER) en cours d’exécution :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="ec4b1-130">Si les étiquettes et les descriptions de la langue demandée sont disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur cette langue, et le champ **IsTranslated** renvoie **True**.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="ec4b1-131">Si les étiquettes et les descriptions de la langue demandée ne sont pas disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur la langue **EN-US** par défaut, et le champ **IsTranslated** renvoie **False**.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="ec4b1-132">Au moment de l’exécution, lorsque la syntaxe 2 est utilisée, les champs **Étiquette** et **Description** doivent renvoyer des valeurs basées sur la langue définie comme deuxième argument de la fonction appelée :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="ec4b1-133">Si les étiquettes et les descriptions de la langue demandée sont disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur cette langue, et le champ **IsTranslated** renvoie **True**.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="ec4b1-134">Si les étiquettes et les descriptions de la langue demandé ne sont pas disponibles, les champs **Étiquette** et **Description** renvoient des valeurs basées sur la langue **EN-US**, et le champ **IsTranslated** renvoie **False**.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="ec4b1-135">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ec4b1-135">Example 1</span></span>

<span data-ttu-id="ec4b1-136">Dans l’illustration suivante, une énumération est présentée dans un modèle de données ER.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="ec4b1-137">Les détails suivants sont illustrés dans le graphique ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="ec4b1-138">L’énumération du modèle est insérée dans un état comme source de données.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="ec4b1-139">Une expression ER utilise l’énumération de modèle comme paramètre de la fonction `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="ec4b1-140">Une source de données du type *Liste d’enregistrements* est insérée dans un état à l’aide de l’expression ER créée.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="ec4b1-141">L’exemple suivant montre les éléments de format ER liés à la source de données du type *Liste d’enregistrements* créée à l’aide de la fonction `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="ec4b1-142">L’illustration suivante présente le résultat de l’exécution du format conçu.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="ec4b1-143">Selon les paramètres de langue configurés pour les éléments de format **FILE** et **FOLDER** parents, le texte traduit pour les étiquettes et les descriptions est renseigné dans la sortie du format ER.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="ec4b1-144">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="ec4b1-144">Example 2</span></span>

<span data-ttu-id="ec4b1-145">Vous utilisez le type de source de données *Champ calculé* pour configurer les sources de données **enumType\_de** et **enumType\_deCH** pour l’énumération du modèle de données **enumType** :</span><span class="sxs-lookup"><span data-stu-id="ec4b1-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="ec4b1-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="ec4b1-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="ec4b1-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="ec4b1-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="ec4b1-148">Dans ce cas, vous pouvez utiliser l’expression suivante pour obtenir l’étiquette de la valeur d’énumération en allemand suisse, si la traduction est disponible.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="ec4b1-149">Si la traduction suisse-allemande n’est pas disponible, l’étiquette est en allemand.</span><span class="sxs-lookup"><span data-stu-id="ec4b1-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="ec4b1-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ec4b1-150">Additional resources</span></span>

[<span data-ttu-id="ec4b1-151">Fonctions de liste</span><span class="sxs-lookup"><span data-stu-id="ec4b1-151">List functions</span></span>](er-functions-category-list.md)
