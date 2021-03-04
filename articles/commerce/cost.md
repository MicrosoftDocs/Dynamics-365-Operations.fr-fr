---
title: Configuration des coûts pour la gestion des commandes distribuées (DOM)
description: Cette rubrique décrit la configuration des coûts pour la fonctionnalité de gestion des commandes distribuées (DOM) dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b96780745e8dd8a6e2b46a3286bf4a6a307d886c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001047"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="ff2d8-103">Configuration des coûts pour la gestion des commandes distribuées (DOM)</span><span class="sxs-lookup"><span data-stu-id="ff2d8-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff2d8-104">Les organisations prennent en compte plusieurs composants de coût pour déterminer l’emplacement optimal à partir duquel traiter une commande.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="ff2d8-105">Certains de ces composants de coût sont le coût d’expédition, le coût de gestion et le coût d’emballage.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="ff2d8-106">Une combinaison de ces coûts est calculée pour déterminer l’emplacement d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="ff2d8-107">Lorsque la première itération de la gestion des commandes distribuées (DOM) dans Dynamics 365 Commerce a optimisé l’affectation des commandes à des emplacements d’exécution, elle a pris en compte la distance uniquement.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-107">When the first iteration of distributed order management (DOM) in Dynamics 365 Commerce optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="ff2d8-108">Bien que la distance puisse être mise en corrélation avec le coût, elle n’est pas considérée comme un coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="ff2d8-109">Par exemple, un mode d’expédition de nuit coûte plus de trois jours d’expédition ou sept jours d’expédition sur la même distance.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="ff2d8-110">La fonction de configuration des coûts permet aux détaillants de définir et de configurer des composants de coût supplémentaires qui seront calculés et pris en compte pour déterminer l’emplacement optimal à partir duquel traiter des lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="ff2d8-111">Lorsque des composants de coût sont configurés, le solveur DOM utilise uniquement ces définitions de coût pour déterminer l’emplacement optimal pour traiter une commande.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="ff2d8-112">Il ne considère pas le composant de distance comme un coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="ff2d8-113">Toutefois, si aucun composant de coût n’est configuré, le solveur DOM utilise le composant de distance comme coût pour déterminer l’emplacement optimal pour traiter une commande.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="ff2d8-114">Paramétrer des composants de coût</span><span class="sxs-lookup"><span data-stu-id="ff2d8-114">Set up cost components</span></span>

<span data-ttu-id="ff2d8-115">Deux principaux types de composants de coût peuvent être définis dans le système : **Expédition** et **Autre**.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="ff2d8-116">Ces deux types de composants de coût prennent en charge plusieurs bases de calcul, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ff2d8-117">Type de composant de coût</span><span class="sxs-lookup"><span data-stu-id="ff2d8-117">Cost component type</span></span></th>
<th><span data-ttu-id="ff2d8-118">Base de calcul</span><span class="sxs-lookup"><span data-stu-id="ff2d8-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ff2d8-119">Expédition</span><span class="sxs-lookup"><span data-stu-id="ff2d8-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="ff2d8-120">Simple</span><span class="sxs-lookup"><span data-stu-id="ff2d8-120">Simple</span></span></li>
<li><span data-ttu-id="ff2d8-121">Progressif</span><span class="sxs-lookup"><span data-stu-id="ff2d8-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="ff2d8-122">Autre</span><span class="sxs-lookup"><span data-stu-id="ff2d8-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="ff2d8-123">Commande client</span><span class="sxs-lookup"><span data-stu-id="ff2d8-123">Sales order</span></span></li>
<li><span data-ttu-id="ff2d8-124">Ligne de vente</span><span class="sxs-lookup"><span data-stu-id="ff2d8-124">Sales line</span></span></li>
<li><span data-ttu-id="ff2d8-125">Emplacement</span><span class="sxs-lookup"><span data-stu-id="ff2d8-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="ff2d8-126">Type de composant de coût Expédition</span><span class="sxs-lookup"><span data-stu-id="ff2d8-126">Shipping cost component type</span></span>

<span data-ttu-id="ff2d8-127">Cette section explique comment paramétrer chaque combinaison du type de composant de coût **Expédition** et d’une base de calcul pour les coûts d’expédition.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="ff2d8-128">Elle explique également comment le solveur DOM utilise chaque combinaison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="ff2d8-129">Type de composant de coût = Expédition et Base de calcul = Simple</span><span class="sxs-lookup"><span data-stu-id="ff2d8-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="ff2d8-130">Si une combinaison du type de composant de coût **Expédition** et de la base de calcul **Simple** est utilisée, le coût d’expédition pour un mode de livraison est basé sur un coût ou une distance forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="ff2d8-131">Vous devez paramétrer les champs suivants pour cette combinaison :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="ff2d8-132">**Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="ff2d8-133">**Description** – Entrez le nom et la description du facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="ff2d8-134">**Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="ff2d8-135">Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="ff2d8-136">**Actif** – Indique si le facteur de coût est actif.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="ff2d8-137">Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="ff2d8-138">**Société** – Spécifiez l’entité juridique pour laquelle le facteur de coût est configuré.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="ff2d8-139">Toutes les lignes des critères de calcul doivent s’appliquer à la même entité juridique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="ff2d8-140">**Modes de livraison** – Spécifiez les modes de livraison pour lesquels le coût est configuré.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="ff2d8-141">**Type de calcul** – Spécifiez le mode de calcul du coût pour un mode de livraison spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="ff2d8-142">Deux types de calcul sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="ff2d8-143">**Fixe** – Un coût forfaitaire est utilisé pour le mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="ff2d8-144">Si vous sélectionnez ce type de calcul, le champ **Coût** définit le coût forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="ff2d8-145">**Par unité de distance** – Le coût pour le mode de livraison est calculé comme la valeur de coût spécifiée dans le champ **Coût** multipliée par la distance entre l’adresse de livraison et les emplacements.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="ff2d8-146">**Coût** – Spécifiez la valeur de coût qui est utilisée conjointement avec le champ **Type de calcul** pour calculer le coût pour un mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="ff2d8-147">Type de composant de coût = Expédition et Base de calcul = Progressif</span><span class="sxs-lookup"><span data-stu-id="ff2d8-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="ff2d8-148">Si une combinaison du type de composant de coût **Expédition** et de la base de calcul **Progressif** est utilisée, le coût d’expédition pour un mode de livraison est basé sur un coût ou une distance forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="ff2d8-149">Toutefois, dans cette combinaison, la distance est basée sur une plage de distances progressives.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="ff2d8-150">Vous devez paramétrer les champs suivants pour cette combinaison :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="ff2d8-151">**Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="ff2d8-152">**Description** – Entrez le nom et la description du facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="ff2d8-153">**Coût par défaut** – Spécifiez le coût qui doit être utilisé pour un mode de livraison si la distance entre l’adresse de livraison et l’emplacement n’est pas comprise dans les distances progressives pour le mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="ff2d8-154">**Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="ff2d8-155">Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="ff2d8-156">**Actif** – Indique si le facteur de coût est actif.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="ff2d8-157">Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="ff2d8-158">**Société** – Spécifiez l’entité juridique pour laquelle le facteur de coût est configuré.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="ff2d8-159">Toutes les lignes des critères de calcul doivent s’appliquer à la même entité juridique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="ff2d8-160">**Modes de livraison** – Spécifiez les modes de livraison pour lesquels le coût est configuré.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="ff2d8-161">**Type de distance** – Spécifiez si la définition de la distance progressive est une distance à vol d’oiseau ou une distance kilométrique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="ff2d8-162">**Unités de distance** – Spécifiez l’unité de mesure de la distance progressive.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="ff2d8-163">**Distance à partir de** – Spécifiez la plage de début de la distance progressive.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="ff2d8-164">**Distance jusqu’à** – Spécifiez la plage de fin de la distance progressive.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="ff2d8-165">**Type de calcul** – Spécifiez le mode de calcul du coût pour un mode de livraison et une distance progressive spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="ff2d8-166">Deux types de calcul sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="ff2d8-167">**Fixe** – Un coût forfaitaire est utilisé pour le mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="ff2d8-168">Si vous sélectionnez ce type de calcul, le champ **Coût** définit le coût forfaitaire.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="ff2d8-169">**Par unité de distance** – Le coût pour le mode de livraison et la distance progressive est calculé comme la valeur de coût spécifiée dans le champ **Coût** multipliée par la distance entre l’adresse de livraison et les emplacements.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="ff2d8-170">**Coût** – Spécifiez la valeur de coût qui est utilisée conjointement avec le champ **Type de calcul** pour calculer le coût pour un mode de livraison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="ff2d8-171">Lorsque vous définissez des distances progressives, le système valide qu’aucune distance ne manque ou que des distances ne se chevauchent pas.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="ff2d8-172">Le type de distance utilisé pour un mode de livraison doit être le même pour toutes les distances progressives.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="ff2d8-173">Type de composant de coût Autre</span><span class="sxs-lookup"><span data-stu-id="ff2d8-173">Other cost component type</span></span>

<span data-ttu-id="ff2d8-174">Cette section explique comment paramétrer chaque combinaison du type de composant de coût **Autre** et d’un autre type de coût pour les coûts hors expédition.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="ff2d8-175">Elle explique également comment le solveur DOM utilise chaque combinaison.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="ff2d8-176">Type de composant de coût = Autre et Autre type de coût = Commande client</span><span class="sxs-lookup"><span data-stu-id="ff2d8-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="ff2d8-177">Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Commande client** est utilisée pour définir les coûts hors expédition au niveau de la commande client.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="ff2d8-178">Vous devez paramétrer les champs suivants pour cette combinaison :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="ff2d8-179">**Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="ff2d8-180">**Description** – Entrez le nom et la description du facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="ff2d8-181">**Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="ff2d8-182">Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="ff2d8-183">**Actif** – Indique si le facteur de coût est actif.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="ff2d8-184">Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="ff2d8-185">**Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau de la commande client.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="ff2d8-186">Type de composant de coût = Autre et Autre type de coût = Ligne de vente</span><span class="sxs-lookup"><span data-stu-id="ff2d8-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="ff2d8-187">Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Ligne de vente** est utilisée pour définir les coûts hors expédition au niveau de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="ff2d8-188">Vous devez paramétrer les champs suivants pour cette combinaison :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="ff2d8-189">**Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="ff2d8-190">**Description** – Entrez le nom et la description du facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="ff2d8-191">**Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="ff2d8-192">Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="ff2d8-193">**Actif** – Indique si le facteur de coût est actif.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="ff2d8-194">Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="ff2d8-195">**Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="ff2d8-196">Type de composant de coût = Autre et Autre type de coût = Emplacement</span><span class="sxs-lookup"><span data-stu-id="ff2d8-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="ff2d8-197">Une combinaison du type de composant de coût **Autre** et de l’autre type de coût **Emplacement** est utilisée pour définir les coûts hors expédition pour un groupe d’emplacements ou un emplacement individuel.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="ff2d8-198">Vous devez paramétrer les champs suivants pour cette combinaison :</span><span class="sxs-lookup"><span data-stu-id="ff2d8-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="ff2d8-199">**Facteur de coût** – Entrez un identificateur unique pour le facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="ff2d8-200">**Description** – Entrez le nom et la description du facteur de coût.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="ff2d8-201">**Date de début** et **Date de fin** – Vous pouvez utiliser ces champs pour limiter le facteur de coût pour une plage de dates spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="ff2d8-202">Si vous laissez ces champs vides, le facteur de coût est valide pour une période indéfinie.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="ff2d8-203">**Actif** – Indique si le facteur de coût est actif.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="ff2d8-204">Le solveur DOM ne prend en compte que les facteurs de coût actifs associés au profil d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="ff2d8-205">**Groupe d’exécution** – Spécifiez le groupe d’emplacements pour lesquels le coût hors expédition est défini.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="ff2d8-206">**Emplacement d’exécution** – Spécifiez l’emplacement pour lequel le coût hors expédition est défini.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff2d8-207">Vous ne pouvez pas spécifier un groupe d’exécution et un emplacement d’exécution sur la même ligne pour les critères de calcul basés sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="ff2d8-208">**Coût** – Spécifiez la valeur de coût pour un coût hors expédition au niveau du groupe d’exécution ou au niveau de l’emplacement d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff2d8-209">Pour que DOM prenne en compte ces coûts au moment de l’exécution, vous devez ajouter le facteur de coût au profil d’exécution approprié.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>
