---
title: Entités de données de produit
description: Cette rubrique fournit des informations sur les différentes entités pouvant être utilisées pour importer et exporter des données produit.
author: cvocph
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 83191ea3d07ec9e2ed6261ee997e06b802ee7645
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935937"
---
# <a name="product-data-entities"></a><span data-ttu-id="0089f-103">Entités de données de produit</span><span class="sxs-lookup"><span data-stu-id="0089f-103">Product data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0089f-104">Pour importer et exporter des données de produit, vous devez utiliser des entités de données.</span><span class="sxs-lookup"><span data-stu-id="0089f-104">To import and export product data, you must use data entities.</span></span> <span data-ttu-id="0089f-105">Le tableau suivant fournit des détails sur les entités de données liées au produit et décrit le but de chacune.</span><span class="sxs-lookup"><span data-stu-id="0089f-105">The following table provides details about the product-related data entities and describes the purpose of each.</span></span>

| <span data-ttu-id="0089f-106">Entité</span><span class="sxs-lookup"><span data-stu-id="0089f-106">Entity</span></span> | <span data-ttu-id="0089f-107">Nom de l'arbre d'objets d'application (AOT) (type)</span><span class="sxs-lookup"><span data-stu-id="0089f-107">Application Object Tree (AOT) name (type)</span></span> | <span data-ttu-id="0089f-108">Notes</span><span class="sxs-lookup"><span data-stu-id="0089f-108">Notes</span></span> |
|--------|-------------------------------------------|-------|
| <span data-ttu-id="0089f-109">Produits V2</span><span class="sxs-lookup"><span data-stu-id="0089f-109">Products V2</span></span> | <span data-ttu-id="0089f-110">EcoResProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="0089f-110">EcoResProductV2Entity</span></span> | <span data-ttu-id="0089f-111">Cette entité est utilisée pour importer et exporter des produits distincts des produits partagés et des produits génériques.</span><span class="sxs-lookup"><span data-stu-id="0089f-111">This entity is used to import and export shared products-distinct products and product masters.</span></span> <span data-ttu-id="0089f-112">Elle permet des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-112">It allows for updates.</span></span> <span data-ttu-id="0089f-113">Elle ne prend pas en charge les opérations SQL basées sur un ensemble.</span><span class="sxs-lookup"><span data-stu-id="0089f-113">It doesn't support set-based SQL operations.</span></span> <span data-ttu-id="0089f-114">Elle este activé pour le protocole OData (Open Data Protocol).</span><span class="sxs-lookup"><span data-stu-id="0089f-114">It's enabled for Open Data Protocol (OData).</span></span> |
| <span data-ttu-id="0089f-115">Produits lancés V2</span><span class="sxs-lookup"><span data-stu-id="0089f-115">Released products V2</span></span> | <span data-ttu-id="0089f-116">EcoResReleasedProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="0089f-116">EcoResReleasedProductV2Entity</span></span> | <span data-ttu-id="0089f-117">Cette entité est utilisée pour importer et exporter des produits distincts des produits lancés et des produits génériques.</span><span class="sxs-lookup"><span data-stu-id="0089f-117">This entity is used to import and export released products-distinct products and product masters.</span></span> <span data-ttu-id="0089f-118">Elle permet des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-118">It allows for updates.</span></span> <span data-ttu-id="0089f-119">Cela nécessite que le produit partagé soit déjà créé.</span><span class="sxs-lookup"><span data-stu-id="0089f-119">It requires that the shared product already be created.</span></span> <span data-ttu-id="0089f-120">Lorsqu'un nouveau produit commercialisé est importé, une version du produit partagé est créée.</span><span class="sxs-lookup"><span data-stu-id="0089f-120">When a new released product is imported, a release of the shared product occurs.</span></span> <span data-ttu-id="0089f-121">Il existe également des entités distinctes qui peuvent être utilisées pour importer et exporter des produits génériques lancés et des variantes distinctes lancées.</span><span class="sxs-lookup"><span data-stu-id="0089f-121">There are also separate entities that can be used to import and export released product masters and released distinct variants.</span></span> <span data-ttu-id="0089f-122">Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble ni les opérations de suppression.</span><span class="sxs-lookup"><span data-stu-id="0089f-122">This entity doesn't support set-based SQL operations or delete operations.</span></span> <span data-ttu-id="0089f-123">Elle est activée pour OData.</span><span class="sxs-lookup"><span data-stu-id="0089f-123">It's enabled for OData.</span></span> |
| <span data-ttu-id="0089f-124">Création de produit lancé V2</span><span class="sxs-lookup"><span data-stu-id="0089f-124">Released product creation V2</span></span> | <span data-ttu-id="0089f-125">EcoResReleasedProductCreationV2Entity</span><span class="sxs-lookup"><span data-stu-id="0089f-125">EcoResReleasedProductCreationV2Entity</span></span> | <span data-ttu-id="0089f-126">Cette entité est utilisée pour importer des produits partagés et des produits lancés en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="0089f-126">This entity is used to import shared products and released products in one step.</span></span> <span data-ttu-id="0089f-127">Bien qu'elle prenne en charge les exportations, cette utilisation n'est pas recommandée, car le but de l'entité est la création de produits.</span><span class="sxs-lookup"><span data-stu-id="0089f-127">Although it supports exports, that use isn't recommended, because the purpose of the entity is product creation.</span></span> <span data-ttu-id="0089f-128">Elle ne prend pas en charge les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-128">It doesn't support updates.</span></span> <span data-ttu-id="0089f-129">Elle prend en charge un ensemble limité de champs (champs disponibles dans la boîte de dialogue de création de produit).</span><span class="sxs-lookup"><span data-stu-id="0089f-129">It supports a limited set of fields (fields that are available in the product creation dialog box).</span></span> <span data-ttu-id="0089f-130">Elle ne prend pas en charge les opérations SQL basées sur un ensemble.</span><span class="sxs-lookup"><span data-stu-id="0089f-130">It doesn't support set-based SQL operations.</span></span> <span data-ttu-id="0089f-131">Elle n'est pas exposé via OData.</span><span class="sxs-lookup"><span data-stu-id="0089f-131">It isn't exposed through OData.</span></span> |
| <span data-ttu-id="0089f-132">Variantes de produit</span><span class="sxs-lookup"><span data-stu-id="0089f-132">Product variants</span></span> | <span data-ttu-id="0089f-133">EcoResProductVariantEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-133">EcoResProductVariantEntity</span></span> | <span data-ttu-id="0089f-134">Cette entité est utilisée pour importer et exporter des variantes de produit partagées.</span><span class="sxs-lookup"><span data-stu-id="0089f-134">This entity is used to import and export shared product variants.</span></span> <span data-ttu-id="0089f-135">Elle permet des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-135">It allows for updates.</span></span> <span data-ttu-id="0089f-136">Cela nécessite que des valeurs de dimension soient déjà créées.</span><span class="sxs-lookup"><span data-stu-id="0089f-136">It requires that dimension values already be created.</span></span> <span data-ttu-id="0089f-137">La clé d'intégration correspond au produit générique plus les dimensions du produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-137">The integration key is the product master plus product dimensions.</span></span> <span data-ttu-id="0089f-138">Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble.</span><span class="sxs-lookup"><span data-stu-id="0089f-138">This entity doesn't support set-based SQL operations.</span></span> <span data-ttu-id="0089f-139">Elle est activée pour OData.</span><span class="sxs-lookup"><span data-stu-id="0089f-139">It's enabled for OData.</span></span> <span data-ttu-id="0089f-140">Elle prend en charge les opérations de suppression.</span><span class="sxs-lookup"><span data-stu-id="0089f-140">It supports delete operations.</span></span> <span data-ttu-id="0089f-141">Elle ne peut pas être étendue par l'ajout de nouvelles dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-141">It can't be extended through the addition of new product dimensions.</span></span> |
| <span data-ttu-id="0089f-142">Variantes de produit par identification du numéro de produit</span><span class="sxs-lookup"><span data-stu-id="0089f-142">Product variants by product number identification</span></span> | <span data-ttu-id="0089f-143">EcoResProductNumberIdentifiedProductVariantEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-143">EcoResProductNumberIdentifiedProductVariantEntity</span></span> | <span data-ttu-id="0089f-144">Cette entité est utilisée pour importer et exporter des variantes de produit partagées.</span><span class="sxs-lookup"><span data-stu-id="0089f-144">This entity is used to import and export shared product variants.</span></span> <span data-ttu-id="0089f-145">Elle permet des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-145">It allows for updates.</span></span> <span data-ttu-id="0089f-146">Cela nécessite que des valeurs de dimension soient déjà créées.</span><span class="sxs-lookup"><span data-stu-id="0089f-146">It requires that dimension values already be created.</span></span> <span data-ttu-id="0089f-147">La clé d'intégration est le numéro de produit (alors que la clé d'intégration pour l'entité **Variantes de produits** est le produit générique plus les dimensions du produit).</span><span class="sxs-lookup"><span data-stu-id="0089f-147">The integration key is the product number (whereas the integration key for the **Product variants** entity is the product master plus product dimensions).</span></span> |
| <span data-ttu-id="0089f-148">Variantes de produit lancé</span><span class="sxs-lookup"><span data-stu-id="0089f-148">Released product variants</span></span> | <span data-ttu-id="0089f-149">EcoResReleasedProductVariantEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-149">EcoResReleasedProductVariantEntity</span></span> | <span data-ttu-id="0089f-150">Cette entité est utilisée pour importer et exporter des variantes de produit lancées.</span><span class="sxs-lookup"><span data-stu-id="0089f-150">This entity is used to import and export released product variants.</span></span> <span data-ttu-id="0089f-151">Elle permet des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0089f-151">It allows for updates.</span></span> <span data-ttu-id="0089f-152">Cela nécessite que les variantes de produit partagées soit déjà créées.</span><span class="sxs-lookup"><span data-stu-id="0089f-152">It requires that shared product variants already be created.</span></span> <span data-ttu-id="0089f-153">Lorsqu'une nouvelle variante de produit commercialisé est importée, une variante du produit partagé est créée.</span><span class="sxs-lookup"><span data-stu-id="0089f-153">When a new released product variant is imported, a release of the shared product variant occurs.</span></span> <span data-ttu-id="0089f-154">Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble.</span><span class="sxs-lookup"><span data-stu-id="0089f-154">This entity doesn't support set-based SQL operations.</span></span> <span data-ttu-id="0089f-155">Elle est activée pour OData.</span><span class="sxs-lookup"><span data-stu-id="0089f-155">It's enabled for OData.</span></span> <span data-ttu-id="0089f-156">Bien qu'elle prenne en charge les opérations de suppression, cette utilisation entraîne actuellement une corruption des données en raison d'un bogue dans la plateforme actuelle.</span><span class="sxs-lookup"><span data-stu-id="0089f-156">Although it supports delete operations, that use currently causes data corruption because of a bug in the current platform.</span></span> <span data-ttu-id="0089f-157">Cette entité ne peut pas être étendue par l'ajout de nouvelles dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-157">This entity can't be extended through the addition of new product dimensions.</span></span> |
| <span data-ttu-id="0089f-158">Variantes de produit lancé par identification du numéro de produit</span><span class="sxs-lookup"><span data-stu-id="0089f-158">Released product variants by product number identification</span></span> | <span data-ttu-id="0089f-159">EcoResProductNumberIdentifiedReleasedProductVariantEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-159">EcoResProductNumberIdentifiedReleasedProductVariantEntity</span></span> | <span data-ttu-id="0089f-160">Cette entité ressemble à l'entité **Variantes de produit lancé**, mais la clé d'intégration est le numéro de produit au lieu du produit générique plus les dimensions du produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-160">This entity resembles the **Released product variants** entity, but the integration key is the product number instead of the product master plus product dimensions.</span></span> <span data-ttu-id="0089f-161">Elle ne peut pas être étendue par l'ajout de nouvelles dimensions de produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-161">It can be extended through the addition of new product dimensions.</span></span> |
| <span data-ttu-id="0089f-162">Produits lancés vendables</span><span class="sxs-lookup"><span data-stu-id="0089f-162">Sellable released products</span></span> | <span data-ttu-id="0089f-163">EcoResSellableReleasedProductEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-163">EcoResSellableReleasedProductEntity</span></span> | <span data-ttu-id="0089f-164">Cette entité est utilisée pour exporter uniquement des produits vendables.</span><span class="sxs-lookup"><span data-stu-id="0089f-164">This entity is used to export only sellable products.</span></span> <span data-ttu-id="0089f-165">Les produits vendables sont des produits ayant toutes les informations requises pour être utilisés dans une commande client.</span><span class="sxs-lookup"><span data-stu-id="0089f-165">Sellable products are products that have the information that they require in order to be used in a sales order.</span></span> <span data-ttu-id="0089f-166">Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="0089f-166">The same rules apply when a product is validated by using the **Validate** function on the **Released products** page.</span></span> |
| <span data-ttu-id="0089f-167">Produits distincts lancés V2</span><span class="sxs-lookup"><span data-stu-id="0089f-167">Released Distinct products V2</span></span> | <span data-ttu-id="0089f-168">EcoResDistinctProductV2Entity</span><span class="sxs-lookup"><span data-stu-id="0089f-168">EcoResDistinctProductV2Entity</span></span> | <span data-ttu-id="0089f-169">Cette entité est utilisée pour exporter uniquement des produits distincts.</span><span class="sxs-lookup"><span data-stu-id="0089f-169">This entity is used to export distinct products.</span></span> <span data-ttu-id="0089f-170">Ces produits distincts peuvent être des produits, des produits de sous-types et des variantes de produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-170">Those distinct products can be products, subtype products, and product variants.</span></span> |
| <span data-ttu-id="0089f-171">Produits génériques lancés V2</span><span class="sxs-lookup"><span data-stu-id="0089f-171">Released products masters V2</span></span> | <span data-ttu-id="0089f-172">EcoResProductMasterV2Entity</span><span class="sxs-lookup"><span data-stu-id="0089f-172">EcoResProductMasterV2Entity</span></span> | <span data-ttu-id="0089f-173">Cette entité est utilisée pour importer et exporter des produits génériques.</span><span class="sxs-lookup"><span data-stu-id="0089f-173">This entity is used to import and export product masters.</span></span> <span data-ttu-id="0089f-174">Elle n'est pas activée pour la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="0089f-174">It isn't enabled for data management.</span></span> |
| <span data-ttu-id="0089f-175">Article - Code-barres</span><span class="sxs-lookup"><span data-stu-id="0089f-175">Item - bar code</span></span> | <span data-ttu-id="0089f-176">EcoResProductBarcodeEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-176">EcoResProductBarcodeEntity</span></span> | <span data-ttu-id="0089f-177">Cette entité est utilisée pour exporter des produits et des codes-barres.</span><span class="sxs-lookup"><span data-stu-id="0089f-177">This entity is used to export products and bar codes.</span></span> |
| <span data-ttu-id="0089f-178">États du cycle de vie des produits</span><span class="sxs-lookup"><span data-stu-id="0089f-178">Product lifecycle states</span></span> | <span data-ttu-id="0089f-179">EcoResProductLifecycleSateEntity</span><span class="sxs-lookup"><span data-stu-id="0089f-179">EcoResProductLifecycleSateEntity</span></span> | <span data-ttu-id="0089f-180">Cette entité est utilisée pour importer et exporter les différents états du cycle de vie du produit qui peuvent être attribués à un produit.</span><span class="sxs-lookup"><span data-stu-id="0089f-180">This entity is used to import and export the different product lifecycle states that can be assigned to a product.</span></span> |

> [!NOTE]
> <span data-ttu-id="0089f-181">Vous pouvez utiliser l'entité de données **Produits lancés V2** pour importer des produits dans le système uniquement si le produit partagé a déjà été créé.</span><span class="sxs-lookup"><span data-stu-id="0089f-181">You can use the **Released Products V2** data entity to import products into the system only if the shared product has already been created.</span></span> <span data-ttu-id="0089f-182">Sinon, pour importer des produits dans le système, vous devez utiliser l'entité de données **Création de produit**.</span><span class="sxs-lookup"><span data-stu-id="0089f-182">Otherwise, to import products into the system, you must use the **Product creation** data entity.</span></span>