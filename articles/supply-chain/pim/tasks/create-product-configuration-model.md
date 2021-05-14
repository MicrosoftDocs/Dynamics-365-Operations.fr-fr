---
title: Créer un modèle de configuration de produits
description: Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921363"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="39a20-103">Créer un modèle de configuration de produits</span><span class="sxs-lookup"><span data-stu-id="39a20-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39a20-104">Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants.</span><span class="sxs-lookup"><span data-stu-id="39a20-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="39a20-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="39a20-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="39a20-106">Créer un modèle de produit</span><span class="sxs-lookup"><span data-stu-id="39a20-106">Create a product model</span></span>

1. <span data-ttu-id="39a20-107">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="39a20-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="39a20-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="39a20-108">Select **New**.</span></span>
1. <span data-ttu-id="39a20-109">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="39a20-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="39a20-110">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="39a20-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="39a20-111">Dans le champ **Stratégie du solveur**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="39a20-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="39a20-112">La stratégie du solveur détermine la manière dont les contraintes sont traitées dans un modèle de configuration de produit basé sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="39a20-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="39a20-113">Cette sélection peut avoir un impact sur les performances du modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="39a20-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="39a20-114">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="39a20-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="39a20-115">Le composant racine représente le modèle de configuration de produit, mais il peut également être utilisé dans d’autres modèles de produit.</span><span class="sxs-lookup"><span data-stu-id="39a20-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="39a20-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="39a20-116">Select **OK**.</span></span>
1. <span data-ttu-id="39a20-117">Dans le champ **Réutiliser les configurations**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="39a20-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="39a20-118">Si le paramètre de réutilisation de configurations est défini sur oui, le système cherchera des configurations identiques après chaque session de configuration et les réutilisera s’il trouve une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="39a20-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="39a20-119">Ajouter des attributs</span><span class="sxs-lookup"><span data-stu-id="39a20-119">Add attributes</span></span>

1. <span data-ttu-id="39a20-120">Développer la section **Attributs**.</span><span class="sxs-lookup"><span data-stu-id="39a20-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="39a20-121">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="39a20-121">Select **Add**.</span></span>
3. <span data-ttu-id="39a20-122">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="39a20-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="39a20-123">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="39a20-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="39a20-124">Dans le champ **Nom du solveur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="39a20-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="39a20-125">Le nom de solveur est utilisé par le solveur de contrainte du configurateur de produit.</span><span class="sxs-lookup"><span data-stu-id="39a20-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="39a20-126">Il ne doit pas inclure d’espaces ou de caractères spéciaux, sauf _ (trait de soulignement.)</span><span class="sxs-lookup"><span data-stu-id="39a20-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="39a20-127">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="39a20-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="39a20-128">Le texte de description est affiché pour l’utilisateur de la configuration et il donc peut servir d’aide pour sélectionner la bonne valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="39a20-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="39a20-129">Saisissez ou sélectionnez une valeur dans le champ **Type d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="39a20-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="39a20-130">Le type d’attribut détermine les valeurs disponibles pour l’attribut.</span><span class="sxs-lookup"><span data-stu-id="39a20-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="39a20-131">Activez la case à cocher **Inclure dans la réutilisation**.</span><span class="sxs-lookup"><span data-stu-id="39a20-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="39a20-132">Cette option est disponible uniquement si l’option Réutiliser les configurations est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="39a20-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="39a20-133">Inclure un attribut dans la case à cocher de réutilisation signifie que cet attribut sera pris en compte lorsque le système recherchera une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="39a20-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="39a20-134">Ajouter des sous-composants</span><span class="sxs-lookup"><span data-stu-id="39a20-134">Add subcomponents</span></span>

1. <span data-ttu-id="39a20-135">Développez la section **Sous-composants**.</span><span class="sxs-lookup"><span data-stu-id="39a20-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="39a20-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="39a20-136">Select **Add**.</span></span>
3. <span data-ttu-id="39a20-137">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="39a20-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="39a20-138">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="39a20-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="39a20-139">Dans le champ **Nom du solveur**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="39a20-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="39a20-140">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="39a20-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="39a20-141">Dans le champ **Composant**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="39a20-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="39a20-142">Chaque sous-composant doit faire référence à une définition de composant.</span><span class="sxs-lookup"><span data-stu-id="39a20-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="39a20-143">Cette conception prend en charge les composants réutilisables et garantit qu’une fois qu’un composant a été défini, il peut être utilisé dans de nombreux modèles de produit.</span><span class="sxs-lookup"><span data-stu-id="39a20-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="39a20-144">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="39a20-144">Select **Save**.</span></span>
9. <span data-ttu-id="39a20-145">Sélectionnez **Détails de la ligne de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="39a20-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="39a20-146">L’écran détails de ligne de nomenclature permet à l’utilisateur de sélectionner les propriétés requises pour le sous-composant.</span><span class="sxs-lookup"><span data-stu-id="39a20-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="39a20-147">Chaque propriété peut se voir affecter une valeur fixe ou être mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="39a20-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="39a20-148">La mise en correspondance avec un attribut a pour résultat que la propriété de ligne de nomenclature prend des valeurs différentes selon la configuration sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="39a20-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="39a20-149">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="39a20-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="39a20-150">Chaque sous-composant représente un produit générique configurable avec la technologie de configuration basée sur les contraintes.</span><span class="sxs-lookup"><span data-stu-id="39a20-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="39a20-151">La référence est effectuée par le numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="39a20-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="39a20-152">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="39a20-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="39a20-153">Sélectionnez **Oui** dans le champ **Calcul**.</span><span class="sxs-lookup"><span data-stu-id="39a20-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="39a20-154">Définir l’option de calcul garantit que le produit sera inclus lors de l’exécution d’un calcul du coût du produit.</span><span class="sxs-lookup"><span data-stu-id="39a20-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="39a20-155">Sélectionnez l’onglet **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="39a20-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="39a20-156">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="39a20-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="39a20-157">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="39a20-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="39a20-158">Le champ de quantité détermine la quantité de ce produit qui sera consommée dans le produit configuré.</span><span class="sxs-lookup"><span data-stu-id="39a20-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="39a20-159">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="39a20-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="39a20-160">Dans le champ **Quantité de base**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="39a20-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="39a20-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="39a20-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]