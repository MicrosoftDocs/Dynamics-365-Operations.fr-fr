---
title: Calculs du modèle de configuration de produit
description: Cette rubrique décrit comment créer des calculs pour les attributs dans un modèle de configuration de produit
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829616"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="104c2-103">Calculs du modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="104c2-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="104c2-104">Cette rubrique décrit comment créer des calculs pour les attributs dans un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="104c2-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="104c2-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="104c2-105">Prerequisites</span></span>

<span data-ttu-id="104c2-106">Les calculs sont utilisés dans un modèle de configuration de produit pour calculer les valeurs de configuration pour un produit.</span><span class="sxs-lookup"><span data-stu-id="104c2-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="104c2-107">Avant de pouvoir commencer à configurer des calculs, le modèle de configuration de produit associé doit exister.</span><span class="sxs-lookup"><span data-stu-id="104c2-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="104c2-108">Pour une présentation du processus de paramétrage des modèles de configuration et des tâches associées, voir [Paramétrer un modèle de configuration de produit](set-up-maintain-product-configuration-model.md).</span><span class="sxs-lookup"><span data-stu-id="104c2-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="104c2-109">Création d’un calcul</span><span class="sxs-lookup"><span data-stu-id="104c2-109">Create a calculation</span></span>

<span data-ttu-id="104c2-110">Un calcul se compose d’une expression et d’un attribut cible.</span><span class="sxs-lookup"><span data-stu-id="104c2-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="104c2-111">Pour plus d’informations, voir [FAQ sur les calculs pour les modèles de configuration de produit](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="104c2-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="104c2-112">Pour créer un calcul pour un modèle de produit existant, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="104c2-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="104c2-113">Accédez à **Gestion des informations sur les produits \> Commun \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="104c2-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="104c2-114">Ouvrez un modèle de configuration de produit, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="104c2-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="104c2-115">Sur le raccourci **Calculs**, sélectionnez **Ajouter** pour ajouter un calcul, puis définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="104c2-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="104c2-116">**Nom** : Entrez un nom pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="104c2-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="104c2-117">**Description** : entrez une description du calcul.</span><span class="sxs-lookup"><span data-stu-id="104c2-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="104c2-118">**Attribut cible** : sélectionnez l’attribut pour lequel vous effectuez le calcul.</span><span class="sxs-lookup"><span data-stu-id="104c2-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="104c2-119">Sélectionnez **Modifier l’expression**.</span><span class="sxs-lookup"><span data-stu-id="104c2-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="104c2-120">Dans la boîte de dialogue **Entrer un calcul**, ajoutez les attributs, opérateurs et valeurs requis à l’expression.</span><span class="sxs-lookup"><span data-stu-id="104c2-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="104c2-121">Pour plus d’informations sur l’utilisation de ces éléments, voir la rubrique [Contraintes d’expression et contraintes de table dans les modèles de configuration du produit](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="104c2-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="104c2-122">Lorsque votre expression est prête, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="104c2-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="104c2-123">Exemples de calcul</span><span class="sxs-lookup"><span data-stu-id="104c2-123">Calculation examples</span></span>

<span data-ttu-id="104c2-124">Cette section fournit quelques exemples illustrant le fonctionnement des calculs.</span><span class="sxs-lookup"><span data-stu-id="104c2-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="104c2-125">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="104c2-125">Example 1</span></span>

<span data-ttu-id="104c2-126">L’attribut cible est de type booléen, et le calcul utilise l’expression conditionnelle suivante :</span><span class="sxs-lookup"><span data-stu-id="104c2-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="104c2-127">Cette expression renvoie la valeur *True* à l’attribut cible si `decimalAttribute2` est supérieur ou égal à `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="104c2-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="104c2-128">Sinon, elle renvoie une valeur *False*.</span><span class="sxs-lookup"><span data-stu-id="104c2-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="104c2-129">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="104c2-129">Example 2</span></span>

<span data-ttu-id="104c2-130">Cet exemple utilise l’attribut texte `textFixedList` comme attribut cible.</span><span class="sxs-lookup"><span data-stu-id="104c2-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="104c2-131">Cet attribut contient la liste fixe suivante.</span><span class="sxs-lookup"><span data-stu-id="104c2-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="104c2-132">Valeur</span><span class="sxs-lookup"><span data-stu-id="104c2-132">Value</span></span> | <span data-ttu-id="104c2-133">Valeur de solveur</span><span class="sxs-lookup"><span data-stu-id="104c2-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="104c2-134">A</span><span class="sxs-lookup"><span data-stu-id="104c2-134">A</span></span> | <span data-ttu-id="104c2-135">1a</span><span class="sxs-lookup"><span data-stu-id="104c2-135">1a</span></span> |
| <span data-ttu-id="104c2-136">o</span><span class="sxs-lookup"><span data-stu-id="104c2-136">B</span></span> | <span data-ttu-id="104c2-137">2b</span><span class="sxs-lookup"><span data-stu-id="104c2-137">2b</span></span> |
| <span data-ttu-id="104c2-138">C</span><span class="sxs-lookup"><span data-stu-id="104c2-138">C</span></span> | <span data-ttu-id="104c2-139">2c</span><span class="sxs-lookup"><span data-stu-id="104c2-139">2c</span></span> |

<span data-ttu-id="104c2-140">La capture d’écran suivante montre à quoi peuvent ressembler les paramètres de cet attribut dans votre système.</span><span class="sxs-lookup"><span data-stu-id="104c2-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="104c2-141">![Paramètres de type d’attribut pour l’exemple 2](media/model-calculations-example2.png "Paramètres de type d’attribut pour l’exemple 2")</span><span class="sxs-lookup"><span data-stu-id="104c2-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="104c2-142">L’attribut est utilisé dans l’instruction conditionnelle suivante :</span><span class="sxs-lookup"><span data-stu-id="104c2-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="104c2-143">Si `integerAttribute` est inférieur à 150, cette instruction renvoie la valeur textuelle du premier enregistrement de la liste fixe, *A*. Sinon, elle renvoie la valeur textuelle du troisième enregistrement de la liste fixe, *C*.</span><span class="sxs-lookup"><span data-stu-id="104c2-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="104c2-144">La liste fixe équivaut à une énumération de base zéro (enum) et ses valeurs sont accessibles par la valeur entière appropriée.</span><span class="sxs-lookup"><span data-stu-id="104c2-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="104c2-145">Par conséquent, la première valeur de liste fixe (*A*) correspond à *0*, la deuxième valeur (*B*) correspond à *1* et la troisième valeur (*C*) correspond à *2*.</span><span class="sxs-lookup"><span data-stu-id="104c2-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="104c2-146">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="104c2-146">Example 3</span></span>

<span data-ttu-id="104c2-147">Cet exemple utilise l’attribut cible `textFixedList` de l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="104c2-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="104c2-148">Il utilise également un autre attribut texte, `textAttribute`, qui contient la liste fixe suivante.</span><span class="sxs-lookup"><span data-stu-id="104c2-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="104c2-149">Valeur</span><span class="sxs-lookup"><span data-stu-id="104c2-149">Value</span></span> | <span data-ttu-id="104c2-150">Valeur de solveur</span><span class="sxs-lookup"><span data-stu-id="104c2-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="104c2-151">AA</span><span class="sxs-lookup"><span data-stu-id="104c2-151">AA</span></span> | <span data-ttu-id="104c2-152">1aa</span><span class="sxs-lookup"><span data-stu-id="104c2-152">1aa</span></span> |
| <span data-ttu-id="104c2-153">BB</span><span class="sxs-lookup"><span data-stu-id="104c2-153">BB</span></span> | <span data-ttu-id="104c2-154">2bb</span><span class="sxs-lookup"><span data-stu-id="104c2-154">2bb</span></span> |

<span data-ttu-id="104c2-155">La capture d’écran suivante montre à quoi peuvent ressembler les paramètres de cet attribut dans votre système.</span><span class="sxs-lookup"><span data-stu-id="104c2-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="104c2-156">![Paramètres de type d’attribut pour l’exemple 3](media/model-calculations-example3.png "Paramètres de type d’attribut pour l’exemple 3")</span><span class="sxs-lookup"><span data-stu-id="104c2-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="104c2-157">La valeur de l’attribut `textFixedList` est calculée à l’aide de l’instruction conditionnelle suivante :</span><span class="sxs-lookup"><span data-stu-id="104c2-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="104c2-158">Si la valeur de `textAttribute` a une valeur de solveur égale à *1aa*, cette expression renvoie la valeur textuelle du premier enregistrement de la liste fixe `textFixedList`, *A*. Sinon, elle renvoie la valeur textuelle du troisième enregistrement de la liste fixe `textFixedList`, *C*.</span><span class="sxs-lookup"><span data-stu-id="104c2-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="104c2-159">L’instruction conditionnelle doit utiliser la valeur de solveur de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="104c2-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="104c2-160">Seuls les attributs texte de liste fixe peuvent être utilisés dans les calculs.</span><span class="sxs-lookup"><span data-stu-id="104c2-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="104c2-161">Voir également :</span><span class="sxs-lookup"><span data-stu-id="104c2-161">See also</span></span>

- [<span data-ttu-id="104c2-162">Forums aux questions sur les calculs pour les modèles de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="104c2-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="104c2-163">Ajouter une contrainte d’expression à un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="104c2-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="104c2-164">Vue d’ensemble des modèles de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="104c2-164">Product configuration models overview</span></span>](product-configuration-models.md)
