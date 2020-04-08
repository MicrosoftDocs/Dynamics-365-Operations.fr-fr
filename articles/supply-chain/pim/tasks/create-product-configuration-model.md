---
title: Créer un modèle de configuration de produits
description: Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5bdbf9a0708a8e5ae15516ffd603fa0e01595dc8
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147800"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="136d5-103">Créer un modèle de configuration de produits</span><span class="sxs-lookup"><span data-stu-id="136d5-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="136d5-104">Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants.</span><span class="sxs-lookup"><span data-stu-id="136d5-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="136d5-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="136d5-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="136d5-106">Créer un modèle de produit</span><span class="sxs-lookup"><span data-stu-id="136d5-106">Create a product model</span></span>
1. <span data-ttu-id="136d5-107">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="136d5-108">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="136d5-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="136d5-109">Click New.</span></span>
4. <span data-ttu-id="136d5-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="136d5-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="136d5-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="136d5-112">Dans le champ Stratégie du solveur, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="136d5-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="136d5-113">La stratégie du solveur détermine la manière dont les contraintes sont traitées dans un modèle de configuration de produit basé sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="136d5-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="136d5-114">Cette sélection peut avoir un impact sur les performances du modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="136d5-115">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="136d5-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="136d5-116">Le composant racine représente le modèle de configuration de produit, mais il peut également être utilisé dans d'autres modèles de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="136d5-117">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="136d5-117">Click OK.</span></span>
9. <span data-ttu-id="136d5-118">Dans le champ Réutiliser les configurations, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="136d5-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="136d5-119">Si le paramètre de réutilisation de configurations est défini sur oui, le système cherchera des configurations identiques après chaque session de configuration et les réutilisera s'il trouve une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="136d5-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="136d5-120">Ajouter des attributs</span><span class="sxs-lookup"><span data-stu-id="136d5-120">Add attributes</span></span>
1. <span data-ttu-id="136d5-121">Développer la section Attributs.</span><span class="sxs-lookup"><span data-stu-id="136d5-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="136d5-122">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="136d5-122">Click Add.</span></span>
3. <span data-ttu-id="136d5-123">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="136d5-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="136d5-124">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="136d5-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="136d5-125">Dans le champ Nom du solveur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="136d5-126">Le nom de solveur est utilisé par le solveur de contrainte du configurateur de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="136d5-127">Il ne doit pas inclure d'espaces ou de caractères spéciaux, sauf _ (trait de soulignement.)</span><span class="sxs-lookup"><span data-stu-id="136d5-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="136d5-128">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="136d5-129">Le texte de description est affiché pour l'utilisateur de la configuration et il donc peut servir d'aide pour sélectionner la bonne valeur d'attribut.</span><span class="sxs-lookup"><span data-stu-id="136d5-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="136d5-130">Saisissez ou sélectionnez une valeur dans le champ Type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="136d5-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="136d5-131">Le type d'attribut détermine les valeurs disponibles pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="136d5-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="136d5-132">Activez la case à cocher Inclure dans la réutilisation.</span><span class="sxs-lookup"><span data-stu-id="136d5-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="136d5-133">Cette option est disponible uniquement si l'option Réutiliser les configurations est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="136d5-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="136d5-134">Inclure un attribut dans la case à cocher de réutilisation signifie que cet attribut sera pris en compte lorsque le système recherchera une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="136d5-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="136d5-135">Ajouter des sous-composants</span><span class="sxs-lookup"><span data-stu-id="136d5-135">Add subcomponents</span></span>
1. <span data-ttu-id="136d5-136">Développez la section Sous-composants.</span><span class="sxs-lookup"><span data-stu-id="136d5-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="136d5-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="136d5-137">Click Add.</span></span>
3. <span data-ttu-id="136d5-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="136d5-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="136d5-139">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="136d5-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="136d5-140">Dans le champ Nom du solveur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="136d5-141">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="136d5-142">Dans le champ Composant, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="136d5-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="136d5-143">Chaque sous-composant doit faire référence à une définition de composant.</span><span class="sxs-lookup"><span data-stu-id="136d5-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="136d5-144">Cette conception prend en charge les composants réutilisables et garantit qu'une fois qu'un composant a été défini, il peut être utilisé dans de nombreux modèles de produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="136d5-145">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="136d5-145">Click Save.</span></span>
9. <span data-ttu-id="136d5-146">Cliquez sur Détails de ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="136d5-146">Click BOM line details.</span></span>
    * <span data-ttu-id="136d5-147">L'écran détails de ligne de nomenclature permet à l'utilisateur de sélectionner les propriétés requises pour le sous-composant.</span><span class="sxs-lookup"><span data-stu-id="136d5-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="136d5-148">Chaque propriété peut se voir affecter une valeur fixe ou être mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="136d5-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="136d5-149">La mise en correspondance avec un attribut a pour résultat que la propriété de ligne de nomenclature prend des valeurs différentes selon la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="136d5-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="136d5-150">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="136d5-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="136d5-151">Chaque sous-composant représente un produit générique configurable avec la technologie de configuration basée sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="136d5-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="136d5-152">La référence est effectuée par le numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="136d5-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="136d5-153">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="136d5-153">Select the Set check box.</span></span>
12. <span data-ttu-id="136d5-154">Sélectionnez Oui dans le champ Calcul.</span><span class="sxs-lookup"><span data-stu-id="136d5-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="136d5-155">Définir l'option de calcul garantit que le produit sera inclus lors de l'exécution d'un calcul du coût du produit.</span><span class="sxs-lookup"><span data-stu-id="136d5-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="136d5-156">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="136d5-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="136d5-157">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="136d5-157">Select the Set check box.</span></span>
15. <span data-ttu-id="136d5-158">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="136d5-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="136d5-159">Le champ de quantité détermine la quantité de ce produit qui sera consommée dans le produit configuré.</span><span class="sxs-lookup"><span data-stu-id="136d5-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="136d5-160">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="136d5-160">Select the Set check box.</span></span>
17. <span data-ttu-id="136d5-161">Dans le champ Quantité de base, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="136d5-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="136d5-162">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="136d5-162">Click OK.</span></span>

