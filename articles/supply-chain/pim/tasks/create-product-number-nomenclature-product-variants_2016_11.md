---
title: Créer une nomenclature de numéro de produit pour les variantes de produit configurées
description: Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07922a20d5c99640f32bb28ddddaffe846440667
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258873"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="0a108-103">Créer une nomenclature de numéro de produit pour les variantes de produit configurées</span><span class="sxs-lookup"><span data-stu-id="0a108-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0a108-104">Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable.</span><span class="sxs-lookup"><span data-stu-id="0a108-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="0a108-105">Cette procédure illustre également comment générer une nomenclature de configuration pour un composant du modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="0a108-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="0a108-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0a108-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0a108-107">La nouvelle nomenclature de numéros de produit est affectée au produit générique D0004.</span><span class="sxs-lookup"><span data-stu-id="0a108-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="0a108-108">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="0a108-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="0a108-109">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="0a108-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="0a108-110">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="0a108-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="0a108-111">Cliquez sur Nomenclature produit.</span><span class="sxs-lookup"><span data-stu-id="0a108-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="0a108-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="0a108-112">Click New.</span></span>
4. <span data-ttu-id="0a108-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0a108-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0a108-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="0a108-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-115">Click Add.</span></span>
7. <span data-ttu-id="0a108-116">Cliquez sur Numéro du produit générique.</span><span class="sxs-lookup"><span data-stu-id="0a108-116">Click Product master number.</span></span>
8. <span data-ttu-id="0a108-117">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-117">Click Add.</span></span>
9. <span data-ttu-id="0a108-118">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-118">Click Text constant.</span></span>
10. <span data-ttu-id="0a108-119">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="0a108-120">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="0a108-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-121">Click Add.</span></span>
13. <span data-ttu-id="0a108-122">Cliquez sur Configuration.</span><span class="sxs-lookup"><span data-stu-id="0a108-122">Click Configuration.</span></span>
14. <span data-ttu-id="0a108-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="0a108-124">Affecter la nomenclature de numéros de produit à un produit générique</span><span class="sxs-lookup"><span data-stu-id="0a108-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="0a108-125">Cliquez sur Produits génériques.</span><span class="sxs-lookup"><span data-stu-id="0a108-125">Click Product masters.</span></span>
2. <span data-ttu-id="0a108-126">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="0a108-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0a108-127">Par exemple, appliquez un filtre sur le champ Numéro de produit avec la valeur « D ».</span><span class="sxs-lookup"><span data-stu-id="0a108-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="0a108-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="0a108-129">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="0a108-129">Click Edit.</span></span>
5. <span data-ttu-id="0a108-130">Sélectionnez Oui dans le champ Utiliser la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="0a108-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="0a108-131">Dans le champ Nomenclature de numéros de variante de produit, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="0a108-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-132">Close the page.</span></span>
8. <span data-ttu-id="0a108-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="0a108-134">Créer une nomenclature pour un composant du modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="0a108-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="0a108-135">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="0a108-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="0a108-136">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0a108-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="0a108-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="0a108-138">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="0a108-138">Click Edit.</span></span>
5. <span data-ttu-id="0a108-139">Sélectionnez Oui dans le champ Utiliser la nomenclature de configuration.</span><span class="sxs-lookup"><span data-stu-id="0a108-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="0a108-140">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-140">Click Add.</span></span>
7. <span data-ttu-id="0a108-141">Cliquez sur Valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="0a108-141">Click Attribute value.</span></span>
8. <span data-ttu-id="0a108-142">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0a108-143">Dans le champ Attribut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="0a108-144">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-144">Click Add.</span></span>
11. <span data-ttu-id="0a108-145">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-145">Click Text constant.</span></span>
12. <span data-ttu-id="0a108-146">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="0a108-147">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="0a108-148">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-148">Click Add.</span></span>
15. <span data-ttu-id="0a108-149">Cliquez sur Valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="0a108-149">Click Attribute value.</span></span>
16. <span data-ttu-id="0a108-150">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="0a108-151">Dans le champ Attribut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="0a108-152">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-152">Click Add.</span></span>
19. <span data-ttu-id="0a108-153">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-153">Click Text constant.</span></span>
20. <span data-ttu-id="0a108-154">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="0a108-155">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="0a108-156">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-156">Click Add.</span></span>
23. <span data-ttu-id="0a108-157">Cliquez sur Valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="0a108-157">Click Attribute value.</span></span>
24. <span data-ttu-id="0a108-158">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="0a108-159">Dans le champ Attribut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="0a108-160">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-160">Click Add.</span></span>
27. <span data-ttu-id="0a108-161">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-161">Click Text constant.</span></span>
28. <span data-ttu-id="0a108-162">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="0a108-163">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="0a108-164">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-164">Click Add.</span></span>
31. <span data-ttu-id="0a108-165">Cliquez sur Valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="0a108-165">Click Attribute value.</span></span>
32. <span data-ttu-id="0a108-166">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="0a108-167">Dans le champ Attribut, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="0a108-168">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-168">Click Add.</span></span>
35. <span data-ttu-id="0a108-169">Cliquez sur Constante de texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-169">Click Text constant.</span></span>
36. <span data-ttu-id="0a108-170">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="0a108-171">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="0a108-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="0a108-172">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0a108-172">Click Add.</span></span>
39. <span data-ttu-id="0a108-173">Cliquez sur Valeur de souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="0a108-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="0a108-174">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0a108-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="0a108-175">Dans le champ Souche de numéros, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="0a108-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="0a108-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-176">Close the page.</span></span>
43. <span data-ttu-id="0a108-177">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-177">Close the page.</span></span>
44. <span data-ttu-id="0a108-178">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0a108-178">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]