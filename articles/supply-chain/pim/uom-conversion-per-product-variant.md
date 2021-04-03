---
title: Conversion d’unité de mesure selon la variante de produit
description: Cette rubrique explique comment paramétrer les conversions d’unités de mesure selon les variantes de produit. Elle inclut un exemple de paramétrage.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: ddb6c614ede98e46e46ff284a1a16669bbaaaf66
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258045"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="831da-104">Conversion d’unité de mesure selon la variante de produit</span><span class="sxs-lookup"><span data-stu-id="831da-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="831da-105">Cette rubrique explique comment paramétrer les conversions d’unités de mesure pour différentes variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="831da-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="831da-106">Vous pouvez utiliser les variantes de produit pour créer des variations d’un seul produit au lieu de créer plusieurs produits à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="831da-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="831da-107">Par exemple, une variante de produit peut être un T-shirt d’une taille et d’une couleur données.</span><span class="sxs-lookup"><span data-stu-id="831da-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="831da-108">Auparavant, les conversions d’unités ne pouvaient être configurées que sur la fiche produit.</span><span class="sxs-lookup"><span data-stu-id="831da-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="831da-109">Par conséquent, toutes les variantes de produit avaient les mêmes règles de conversion d’unité.</span><span class="sxs-lookup"><span data-stu-id="831da-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="831da-110">Cependant, lorsque la fonctionnalité *Conversions d’unités de mesure pour les variantes de produit* est activée, si vos T-shirts sont vendus dans des boîtes et que le nombre de T-shirts pouvant être emballés dans une boîte dépend de la taille des T-shirts, vous pouvez maintenant configurer des conversions d’unités entre les différentes tailles de chemises et les boîtes utilisées pour l’emballage.</span><span class="sxs-lookup"><span data-stu-id="831da-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="831da-111">Activez la fonctionnalité dans votre système</span><span class="sxs-lookup"><span data-stu-id="831da-111">Turn on the feature in your system</span></span>

<span data-ttu-id="831da-112">Si vous ne voyez pas cette fonctionnalité dans votre système, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Conversions d’unités de mesure pour les variantes de produit*.</span><span class="sxs-lookup"><span data-stu-id="831da-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="831da-113">Paramétrage d’un produit pour la conversion d’unités par variante</span><span class="sxs-lookup"><span data-stu-id="831da-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="831da-114">Les variantes de produit peuvent être créées uniquement pour les produits génériques.</span><span class="sxs-lookup"><span data-stu-id="831da-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="831da-115">Pour plus d’informations, voir [Création d’un produit générique](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="831da-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="831da-116">La fonctionnalité *Conversions d’unités de mesure pour les variantes de produit* n’est pas disponible pour les produits configurés pour les processus en poids variable.</span><span class="sxs-lookup"><span data-stu-id="831da-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="831da-117">Pour configurer une fiche produit pour prendre en charge la conversion d’unités par variante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="831da-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="831da-118">Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="831da-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="831da-119">Créez ou ouvrez une fiche produit pour accéder à la page **Détails du produit**.</span><span class="sxs-lookup"><span data-stu-id="831da-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="831da-120">Définissez l’option **Autoriser les conversions des unités de mesure** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="831da-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="831da-121">Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Conversions d’unités**.</span><span class="sxs-lookup"><span data-stu-id="831da-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="831da-122">La page **Conversions d’unités** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="831da-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="831da-123">Sélectionnez l’un des onglets suivants :</span><span class="sxs-lookup"><span data-stu-id="831da-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="831da-124">**Conversions intra-classe :** Sélectionnez cet onglet pour convertir entre les unités appartenant à la même classe d’unités.</span><span class="sxs-lookup"><span data-stu-id="831da-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="831da-125">**Conversions inter-classe :** Sélectionnez cet onglet pour convertir entre les unités appartenant à des classes d’unités différentes.</span><span class="sxs-lookup"><span data-stu-id="831da-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="831da-126">Cliquez sur **Nouveau** pour ajouter une nouvelle unité.</span><span class="sxs-lookup"><span data-stu-id="831da-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="831da-127">Définissez le champ **Créer une conversion pour** sur l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="831da-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="831da-128">**Produit :** Si vous sélectionnez cette valeur, vous pouvez paramétrer une conversion d’unité pour le produit générique.</span><span class="sxs-lookup"><span data-stu-id="831da-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="831da-129">Cette conversion d’unité sera utilisée comme solution de rechange pour toutes les variantes de produit pour lesquelles aucune conversion d’unité n’est définie.</span><span class="sxs-lookup"><span data-stu-id="831da-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="831da-130">**Variante de produit :** Si vous sélectionnez cette valeur, vous pouvez paramétrer une conversion d’unités pour une variante de produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="831da-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="831da-131">Utilisez le champ **Variante de produit** pour sélectionner la variante.</span><span class="sxs-lookup"><span data-stu-id="831da-131">Use the **Product variant** field to select the variant.</span></span>

    <span data-ttu-id="831da-132">![Ajout d’une nouvelle conversion d’unité](media/uom-new-conversion.png "Ajout d’une nouvelle conversion d’unité")</span><span class="sxs-lookup"><span data-stu-id="831da-132">![Adding a new unit conversion](media/uom-new-conversion.png "Adding a new unit conversion")</span></span>

1. <span data-ttu-id="831da-133">Utilisez les autres champs fournis pour configurer votre conversion d’unité.</span><span class="sxs-lookup"><span data-stu-id="831da-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="831da-134">Cliquez sur **OK** pour enregistrer la nouvelle conversion d’unité.</span><span class="sxs-lookup"><span data-stu-id="831da-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="831da-135">Vous pouvez ouvrir la page **Conversions d’unités** d’un produit ou d’une variante de produit à partir de l’une des pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="831da-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="831da-136">Détails de produit</span><span class="sxs-lookup"><span data-stu-id="831da-136">Product details</span></span>
> - <span data-ttu-id="831da-137">Détails des produits lancés</span><span class="sxs-lookup"><span data-stu-id="831da-137">Released products details</span></span>
> - <span data-ttu-id="831da-138">Variantes de produit lancé</span><span class="sxs-lookup"><span data-stu-id="831da-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="831da-139">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="831da-139">Example scenario</span></span>

<span data-ttu-id="831da-140">Dans ce scénario, une société vend des T-shirts dans les tailles S, M, L et XL.</span><span class="sxs-lookup"><span data-stu-id="831da-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="831da-141">Le T-shirt est défini comme produit, et les différentes tailles sont définies en tant que variantes de ce produit.</span><span class="sxs-lookup"><span data-stu-id="831da-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="831da-142">Les chemises sont emballées dans des boîtes.</span><span class="sxs-lookup"><span data-stu-id="831da-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="831da-143">Pour les tailles S, M et L, il peut y avoir cinq chemises dans chaque boîte.</span><span class="sxs-lookup"><span data-stu-id="831da-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="831da-144">Cependant, pour la taille XL, il n’y a de la place que pour quatre chemises dans chaque boîte.</span><span class="sxs-lookup"><span data-stu-id="831da-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="831da-145">La société souhaite suivre les différentes variantes de T-shirts dans l’unité *Pièces* mais vend les T-shirts dans l’unité *Boîtes*.</span><span class="sxs-lookup"><span data-stu-id="831da-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="831da-146">Pour les tailles S, M et L, la conversion entre l’unité d’inventaire et l’unité de vente est de 1 boîte = 5 pièces.</span><span class="sxs-lookup"><span data-stu-id="831da-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="831da-147">Pour une taille XL, la conversion est de 1 boîte = 4 pièces.</span><span class="sxs-lookup"><span data-stu-id="831da-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="831da-148">Sur la page **Détails des produits lancés** pour le produit **T-Shirt**, ouvrez la page **Conversions d’unité**.</span><span class="sxs-lookup"><span data-stu-id="831da-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="831da-149">Dans la page **Conversions d’unité**, paramétrez la conversion d’unité suivante pour la variante de produit lancé **XL**.</span><span class="sxs-lookup"><span data-stu-id="831da-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="831da-150">Champ</span><span class="sxs-lookup"><span data-stu-id="831da-150">Field</span></span>                 | <span data-ttu-id="831da-151">Paramètre</span><span class="sxs-lookup"><span data-stu-id="831da-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="831da-152">Créer une conversion pour</span><span class="sxs-lookup"><span data-stu-id="831da-152">Create conversion for</span></span> | <span data-ttu-id="831da-153">Variante de produit</span><span class="sxs-lookup"><span data-stu-id="831da-153">Product variant</span></span>         |
    | <span data-ttu-id="831da-154">Variante de produit</span><span class="sxs-lookup"><span data-stu-id="831da-154">Product variant</span></span>       | <span data-ttu-id="831da-155">T-shirt : : XL : :</span><span class="sxs-lookup"><span data-stu-id="831da-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="831da-156">Unité - De</span><span class="sxs-lookup"><span data-stu-id="831da-156">From unit</span></span>             | <span data-ttu-id="831da-157">Boîtes</span><span class="sxs-lookup"><span data-stu-id="831da-157">Boxes</span></span>                   |
    | <span data-ttu-id="831da-158">Facteur</span><span class="sxs-lookup"><span data-stu-id="831da-158">Factor</span></span>                | <span data-ttu-id="831da-159">4</span><span class="sxs-lookup"><span data-stu-id="831da-159">4</span></span>                       |
    | <span data-ttu-id="831da-160">À l’unité</span><span class="sxs-lookup"><span data-stu-id="831da-160">To Unit</span></span>               | <span data-ttu-id="831da-161">Pièces</span><span class="sxs-lookup"><span data-stu-id="831da-161">Pieces</span></span>                  |

1. <span data-ttu-id="831da-162">Comme les variantes de produit **S**, **M** et **L** ont la même conversion d’unité entre les unités *Boîte* et *Pièces*, vous pouvez définir la conversion d’unité suivante pour ces variantes de produit dans le produit générique.</span><span class="sxs-lookup"><span data-stu-id="831da-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="831da-163">Champ</span><span class="sxs-lookup"><span data-stu-id="831da-163">Field</span></span>                 | <span data-ttu-id="831da-164">Paramètre</span><span class="sxs-lookup"><span data-stu-id="831da-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="831da-165">Créer une conversion pour</span><span class="sxs-lookup"><span data-stu-id="831da-165">Create conversion for</span></span> | <span data-ttu-id="831da-166">Produit</span><span class="sxs-lookup"><span data-stu-id="831da-166">Product</span></span> |
    | <span data-ttu-id="831da-167">Produit</span><span class="sxs-lookup"><span data-stu-id="831da-167">Product</span></span>               | <span data-ttu-id="831da-168">T-shirt</span><span class="sxs-lookup"><span data-stu-id="831da-168">T-Shirt</span></span> |
    | <span data-ttu-id="831da-169">Unité - De</span><span class="sxs-lookup"><span data-stu-id="831da-169">From unit</span></span>             | <span data-ttu-id="831da-170">Boîtes</span><span class="sxs-lookup"><span data-stu-id="831da-170">Boxes</span></span>   |
    | <span data-ttu-id="831da-171">Facteur</span><span class="sxs-lookup"><span data-stu-id="831da-171">Factor</span></span>                | <span data-ttu-id="831da-172">5</span><span class="sxs-lookup"><span data-stu-id="831da-172">5</span></span>       |
    | <span data-ttu-id="831da-173">À l’unité</span><span class="sxs-lookup"><span data-stu-id="831da-173">To Unit</span></span>               | <span data-ttu-id="831da-174">Pièces</span><span class="sxs-lookup"><span data-stu-id="831da-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="831da-175">Utilisation d’Excel pour mettre à jour les conversions d’unité</span><span class="sxs-lookup"><span data-stu-id="831da-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="831da-176">Si un produit comporte de nombreuses variantes avec des conversions d’unités différentes, il est judicieux d’exporter les conversions d’unité vers un classeur Microsoft Excel, de les mettre à jour, puis de les publier à nouveau dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="831da-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="831da-177">Pour exporter des conversions d’unité vers Excel, sur la page **Conversions d’unités**, dans le volet Actions, sélectionnez **Ouvrir dans Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="831da-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="831da-178">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="831da-178">Additional resources</span></span>

[<span data-ttu-id="831da-179">Gérer l’unité de mesure</span><span class="sxs-lookup"><span data-stu-id="831da-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]