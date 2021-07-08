---
title: Créer des variantes de produits prédéfinies
description: Cette procédure décrit la création des variantes de produit pour un produit générique à l’aide des combinaisons de dimensions de produit.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270478"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="5c2cf-103">Variantes de produits prédéfinies</span><span class="sxs-lookup"><span data-stu-id="5c2cf-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="5c2cf-104">Exemple de scénario : Créer des variantes de produits prédéfinies</span><span class="sxs-lookup"><span data-stu-id="5c2cf-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="5c2cf-105">Cet exemple de scénario décrit la création des variantes de produit pour un produit générique à l’aide des combinaisons de dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="5c2cf-106">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="5c2cf-106">Make demo data available</span></span>

<span data-ttu-id="5c2cf-107">Pour suivre ce scénario en utilisant les valeurs suggérées ici, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique *USMF*.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="5c2cf-108">Étape 1 : Créer un produit générique</span><span class="sxs-lookup"><span data-stu-id="5c2cf-108">Step 1: Create a product master</span></span>

<span data-ttu-id="5c2cf-109">Pour créer un produit générique :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-109">To create a product master:</span></span>

1. <span data-ttu-id="5c2cf-110">Accédez à **Gestion des informations sur les produits > Produits > Produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="5c2cf-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-111">Select **New**.</span></span>
1. <span data-ttu-id="5c2cf-112">Si le champ **Numéro de produit** n’affiche pas déjà un nombre, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="5c2cf-113">Cette étape n’est requise que si aucune souche de numéros n’a été paramétrée pour ce champ.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="5c2cf-114">Entrez un nom dans le champ **Nom du produit**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="5c2cf-115">Dans le champ **Groupe de dimensions de produit**, sélectionnez le groupe de dimensions de produit *SizeCol* (Taille et couleur).</span><span class="sxs-lookup"><span data-stu-id="5c2cf-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="5c2cf-116">Sélectionnez **OK** pour créer et ouvrir le nouveau produit générique.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="5c2cf-117">Étape 2 : Ajouter des dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="5c2cf-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="5c2cf-118">Cet exemple décrit la manière d’entrer manuellement les dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="5c2cf-119">Vous pouvez également choisir de sélectionner un groupe de tailles, de couleurs ou de styles incluant les valeurs de dimension de produit à utiliser.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="5c2cf-120">Pour ajouter des dimensions de produit :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-120">To add product dimensions:</span></span>

1. <span data-ttu-id="5c2cf-121">La nouvelle fiche produit étant toujours ouverte, sélectionnez **Dimensions de produit** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="5c2cf-122">Ouvrez l’onglet **Taille** et sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="5c2cf-123">Définissez les paramètres suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="5c2cf-124">**Taille** – Permet de sélectionner une valeur de taille.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="5c2cf-125">**Nom** - Entrez un nom pour la taille.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="5c2cf-126">Sélectionnez **Nouveau** dans la barre d’outils et ajoutez une deuxième taille à la grille avec un nouvelle **Taille** et un nouveau **Nom**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="5c2cf-127">Ouvrez l’onglet **Couleurs** et sélectionnez **Nouveau** dans la barre d’outils pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="5c2cf-128">Définissez les paramètres suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="5c2cf-129">**Couleur** – Sélectionnez une valeur de couleur.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="5c2cf-130">**Nom** - Entrez un nom pour la couleur.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="5c2cf-131">Sélectionnez **Nouveau** dans la barre d’outils et ajoutez une deuxième couleur à la grille avec un nouvelle **Couleur** et un nouveau **Nom**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="5c2cf-132">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-132">Select **Save**.</span></span>
1. <span data-ttu-id="5c2cf-133">Fermez la page pour revenir à votre nouveau produit générique.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="5c2cf-134">Étape 3 : Générer des variantes de produits</span><span class="sxs-lookup"><span data-stu-id="5c2cf-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="5c2cf-135">Cette section décrit comment générer des variantes de produit lorsque la fonctionnalité *Améliorations de la page de suggestions de variantes* n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="5c2cf-136">Consultez la section suivante pour plus de détails sur la façon de générer des variantes de produit lorsque cette fonctionnalité est disponible.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="5c2cf-137">Pour générer des variantes de produits :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-137">To generate product variants:</span></span>

1. <span data-ttu-id="5c2cf-138">La nouvelle fiche produit étant toujours ouverte, sélectionnez **Variantes de produit** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="5c2cf-139">Dans le volet Actions, sélectionnez **Suggestions de variantes**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="5c2cf-140">Le système génère une liste avec toutes les combinaisons possibles des tailles et des couleurs que vous avez définies pour le produit.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="5c2cf-141">Sélectionnez **Sélectionner tout** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="5c2cf-142">Dans cet exemple, sélectionnez toutes les variantes possibles.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="5c2cf-143">Si vous souhaitez utiliser uniquement un sous-ensemble des combinaisons de dimensions de produit possibles, cochez uniquement les cases requises selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="5c2cf-144">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-144">Select **Create**.</span></span>
1. <span data-ttu-id="5c2cf-145">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="5c2cf-146">Suggestions de variantes améliorées</span><span class="sxs-lookup"><span data-stu-id="5c2cf-146">Improved variant suggestions</span></span>

<span data-ttu-id="5c2cf-147">La page *Améliorations de la page de suggestions de variantes* la fonctionnalité améliore les **Suggestions de variantes** pour résoudre les problèmes de performances et d’utilisabilité pour les entreprises qui ont un grand nombre de combinaisons de dimensions de produits.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="5c2cf-148">Le processus amélioré de sélection des valeurs de dimension de produit pour lesquelles générer des suggestions de variantes permet d’identifier et de libérer plus rapidement et plus facilement l’ensemble de variantes de produit approprié.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="5c2cf-149">Les améliorations suivantes sont ajoutées par cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="5c2cf-150">**Génération différée de suggestions de variantes :** la page **Suggestions de variantes** n’affiche plus de suggestions lorsque vous l’ouvrez pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="5c2cf-151">Au lieu de cela, vous devez choisir explicitement les valeurs dont vous aurez besoin, puis sélectionner le bouton **Suggérer** pour générer les combinaisons.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="5c2cf-152">Cela rend le processus plus visible et interactif.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="5c2cf-153">**Sélection des valeurs de dimensions :** lorsque vous avez de nombreuses valeurs de dimension, vous souhaitez généralement générer des suggestions de variantes qui n’en incluent que quelques-unes (par exemple lors de l’introduction d’un nouvel ensemble de couleurs ou de styles).</span><span class="sxs-lookup"><span data-stu-id="5c2cf-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="5c2cf-154">Grâce à la conception améliorée, vous pouvez sélectionner les valeurs de dimension pour lesquelles vous souhaitez générer des suggestions de variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="5c2cf-155">Cela augmente considérablement la pertinence des variantes suggérées et améliore à la fois les performances du système et la productivité des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="5c2cf-156">Activer la fonctionnalité d’amélioration de la page de suggestions de variantes</span><span class="sxs-lookup"><span data-stu-id="5c2cf-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="5c2cf-157">Avant de pouvoir utiliser la fonctionnalité *Amélioration de la page de suggestions de variantes*, elle doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="5c2cf-158">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="5c2cf-159">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5c2cf-160">**Module :** *Gestion des informations sur les produits*</span><span class="sxs-lookup"><span data-stu-id="5c2cf-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="5c2cf-161">**Nom de la fonctionnalité :** *Amélioration de la page de suggestions de variantes*</span><span class="sxs-lookup"><span data-stu-id="5c2cf-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="5c2cf-162">Travailler avec les suggestions de variantes améliorées</span><span class="sxs-lookup"><span data-stu-id="5c2cf-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="5c2cf-163">Pour générer des suggestions de variantes de produit lorsque la fonctionnalité *Améliorations de la page de suggestions de variantes* est activée :</span><span class="sxs-lookup"><span data-stu-id="5c2cf-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="5c2cf-164">Ouvrez ou créez un produit générique et ajoutez-y les dimensions de produit requises, comme décrit dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="5c2cf-165">Le nouveau produit générique étant toujours ouvert, sélectionnez **Variantes de produit** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="5c2cf-166">Dans le volet Actions, sélectionnez **Suggestions de variantes**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="5c2cf-167">Sélectionnez les valeurs que vous souhaitez utiliser pour chaque dimension.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="5c2cf-168">Dans la barre d’outils supérieure, sélectionnez **Suggérer**.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="5c2cf-169">Le système génère une liste avec toutes les combinaisons possibles des tailles et des couleurs que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="5c2cf-170">Sur le raccourci **Variantes suggérées**, cochez la case de chaque combinaison de dimensions de produit que vous souhaitez utiliser ou sélectionnez **Sélectionner tout** dans la barre d’outils pour les sélectionner toutes.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="5c2cf-171">Sélectionnez **Créer** pour ajouter les variantes au produit générique actuel.</span><span class="sxs-lookup"><span data-stu-id="5c2cf-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
