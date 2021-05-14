---
title: Créer une nomenclature de numéro de produit pour les variantes de produit configurées
description: Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921009"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="81c86-103">Créer une nomenclature de numéro de produit pour les variantes de produit configurées</span><span class="sxs-lookup"><span data-stu-id="81c86-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="81c86-104">Cette procédure décrit comment paramétrer une nomenclature de numéros de produit pour des variantes de produit configurées, et comment elle peut être associée à un produit générique configurable.</span><span class="sxs-lookup"><span data-stu-id="81c86-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="81c86-105">Cette procédure illustre également comment générer une nomenclature de configuration pour un composant du modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="81c86-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="81c86-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="81c86-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="81c86-107">La nouvelle nomenclature de numéros de produit est affectée au produit générique D0004.</span><span class="sxs-lookup"><span data-stu-id="81c86-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="81c86-108">Cette tâche est généralement effectuée par un concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="81c86-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="81c86-109">Créer une nomenclature de numéros de produit</span><span class="sxs-lookup"><span data-stu-id="81c86-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="81c86-110">Accédez à **Gestion des informations sur les produits \> Configuration \> Nomenclature produit**.</span><span class="sxs-lookup"><span data-stu-id="81c86-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="81c86-111">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="81c86-111">Select **New**.</span></span>
1. <span data-ttu-id="81c86-112">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="81c86-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="81c86-113">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="81c86-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="81c86-114">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-114">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-115">Sélectionnez **Numéro du produit générique**.</span><span class="sxs-lookup"><span data-stu-id="81c86-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="81c86-116">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-116">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-117">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="81c86-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="81c86-118">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-119">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="81c86-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="81c86-120">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-120">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-121">Sélectionnez **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="81c86-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="81c86-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="81c86-123">Affecter la nomenclature de numéros de produit à un produit générique</span><span class="sxs-lookup"><span data-stu-id="81c86-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="81c86-124">Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="81c86-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="81c86-125">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="81c86-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="81c86-126">Par exemple, appliquez un filtre sur le champ **Numéro de produit** avec la valeur « D ».</span><span class="sxs-lookup"><span data-stu-id="81c86-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="81c86-127">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="81c86-128">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="81c86-128">Select **Edit**.</span></span>
1. <span data-ttu-id="81c86-129">Sélectionnez *Oui* dans le champ **Utiliser la nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="81c86-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="81c86-130">Entrez ou sélectionnez une valeur dans le champ **Nomenclature de numéros de variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="81c86-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-131">Close the page.</span></span>
1. <span data-ttu-id="81c86-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="81c86-133">Créer une nomenclature pour un composant du modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="81c86-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="81c86-134">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="81c86-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="81c86-135">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="81c86-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="81c86-136">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="81c86-137">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="81c86-137">Select **Edit**.</span></span>
1. <span data-ttu-id="81c86-138">Sélectionnez *Oui* dans le champ **Utiliser la nomenclature de configuration**.</span><span class="sxs-lookup"><span data-stu-id="81c86-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="81c86-139">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-139">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-140">Sélectionnez **Valeur d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="81c86-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="81c86-141">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-142">Dans le champ **Attribut**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81c86-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-143">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-143">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-144">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="81c86-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="81c86-145">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-146">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="81c86-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="81c86-147">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-147">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-148">Sélectionnez **Valeur d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="81c86-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="81c86-149">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-150">Dans le champ **Attribut**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81c86-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-151">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-151">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-152">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="81c86-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="81c86-153">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-154">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="81c86-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="81c86-155">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-155">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-156">Sélectionnez **Valeur d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="81c86-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="81c86-157">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-158">Dans le champ **Attribut**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81c86-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-159">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-159">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-160">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="81c86-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="81c86-161">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-162">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="81c86-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="81c86-163">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-163">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-164">Sélectionnez **Valeur d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="81c86-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="81c86-165">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-166">Dans le champ **Attribut**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81c86-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-167">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-167">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-168">Sélectionnez **Texte constant**.</span><span class="sxs-lookup"><span data-stu-id="81c86-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="81c86-169">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-170">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="81c86-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="81c86-171">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81c86-171">Select **Add**.</span></span>
1. <span data-ttu-id="81c86-172">Sélectionnez **Valeur de souche de numéros**.</span><span class="sxs-lookup"><span data-stu-id="81c86-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="81c86-173">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="81c86-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="81c86-174">Dans le champ **Souche de numéros**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="81c86-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="81c86-175">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-175">Close the page.</span></span>
1. <span data-ttu-id="81c86-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-176">Close the page.</span></span>
1. <span data-ttu-id="81c86-177">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="81c86-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]