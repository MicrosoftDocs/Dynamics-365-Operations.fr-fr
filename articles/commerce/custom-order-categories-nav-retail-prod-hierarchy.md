---
title: Modifier l'ordre de tri pour les entités de promotion des ventes
description: Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 67807c53a6ffc6dd09cc6f0e48218e2ee2de559f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207773"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="bc959-103">Modifier l'ordre de tri pour les entités de promotion des ventes</span><span class="sxs-lookup"><span data-stu-id="bc959-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bc959-104">Les détaillants considèrent que la découverte d'un produit est l'outil principal pour l'interaction de clients entre les canaux.</span><span class="sxs-lookup"><span data-stu-id="bc959-104">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span> <span data-ttu-id="bc959-105">Différentes fonctionnalités peuvent aider les clients à découvrir facilement des produits.</span><span class="sxs-lookup"><span data-stu-id="bc959-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="bc959-106">Ils peuvent par exemple parcourir des catégories, faire des recherches, et filtrer.</span><span class="sxs-lookup"><span data-stu-id="bc959-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="bc959-107">Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes.</span><span class="sxs-lookup"><span data-stu-id="bc959-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="bc959-108">Elle décrit également comment modifier l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="bc959-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="bc959-109">Présentation</span><span class="sxs-lookup"><span data-stu-id="bc959-109">Overview</span></span>

<span data-ttu-id="bc959-110">La prise en charge du tri de différentes entités associées à un événement de promotion des ventes a été améliorée.</span><span class="sxs-lookup"><span data-stu-id="bc959-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="bc959-111">Cette prise en charge correspond désormais mieux aux scénarios client existants qui nécessitaient auparavant des extensions de la part des partenaires d'implémentation.</span><span class="sxs-lookup"><span data-stu-id="bc959-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="bc959-112">Dans les versions de Retail qui sont antérieures à la version 10.0.5, la commande de tri pour les catégories de la hiérarchie de navigation était dans l'ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="bc959-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="bc959-113">La nouvelle fonctionnalité d'ordre de tri personnalisée permet aux responsables des ventes de configurer la commande de tri pour différentes entités associées à un événement de promotion des ventes entre tous les clients de l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="bc959-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="bc959-114">Ces clients incluent les sièges sociaux et les centres d'appels.</span><span class="sxs-lookup"><span data-stu-id="bc959-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a><span data-ttu-id="bc959-115">Configuration de l'ordre d'affichage des catégories de la hiérarchie des produits</span><span class="sxs-lookup"><span data-stu-id="bc959-115">Configure the display order for categories in the product hierarchy</span></span>

<span data-ttu-id="bc959-116">Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="bc959-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="bc959-117">Accédez à **Commerce et vente au détail \> Produits et catégories \> Hiérarchie des produits Commerce**.</span><span class="sxs-lookup"><span data-stu-id="bc959-117">Go to **Retail and Commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
2. <span data-ttu-id="bc959-118">Cliquez sur **Modifier la hiérarchie de la catégorie**.</span><span class="sxs-lookup"><span data-stu-id="bc959-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="bc959-119">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bc959-119">Click **Edit**.</span></span>
4. <span data-ttu-id="bc959-120">Dans l'arborescence, développez **ALL \> Action Sports**.</span><span class="sxs-lookup"><span data-stu-id="bc959-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="bc959-121">Dans l'arborescence, développez **ALL \> Team Sports**.</span><span class="sxs-lookup"><span data-stu-id="bc959-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="bc959-122">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="bc959-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="bc959-123">(Ce nombre peut être négatif.)</span><span class="sxs-lookup"><span data-stu-id="bc959-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="bc959-124">Répétez les étapes 4 à 6 pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.</span><span class="sxs-lookup"><span data-stu-id="bc959-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="bc959-125">L'ordre d'affichage pour la hiérarchie de navigation du canal est reportée dans le siège pour la hiérarchie des produits Commerce et les produits lancés par catégorie.</span><span class="sxs-lookup"><span data-stu-id="bc959-125">The display order for the channel navigation hierarchy will be reflected in HQ for the commerce product hierarchy and released products by category.</span></span>

![Hiérarchie des produits personnalisée triée par des valeurs négatives](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Tri personnalisé des produits lancés par catégorie selon la hiérarchie des produits](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="bc959-128">Configuration de l'ordre d'affichage des catégories de la hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="bc959-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="bc959-129">Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="bc959-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="bc959-130">Allez dans **Commerce et vente au détail \> Produits et catégories \> Catégories de navigation du canal**.</span><span class="sxs-lookup"><span data-stu-id="bc959-130">Go to **Retail and Commerce \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="bc959-131">Dans la liste, sélectionnez la hiérarchie **Navigation de mode**.</span><span class="sxs-lookup"><span data-stu-id="bc959-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="bc959-132">Cliquez sur **Modifier la hiérarchie de la catégorie**.</span><span class="sxs-lookup"><span data-stu-id="bc959-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="bc959-133">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bc959-133">Click **Edit**.</span></span>
5. <span data-ttu-id="bc959-134">Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.</span><span class="sxs-lookup"><span data-stu-id="bc959-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="bc959-135">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="bc959-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="bc959-136">Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.</span><span class="sxs-lookup"><span data-stu-id="bc959-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="bc959-137">De même, vous pouvez définir l'ordre de tri pour les sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="bc959-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="bc959-138">Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Casual Shirts**.</span><span class="sxs-lookup"><span data-stu-id="bc959-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="bc959-139">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="bc959-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="bc959-140">Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Coats & Jackets**.</span><span class="sxs-lookup"><span data-stu-id="bc959-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="bc959-141">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="bc959-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="bc959-142">Répétez pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.</span><span class="sxs-lookup"><span data-stu-id="bc959-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="bc959-143">L'ordre d'affichage pour la hiérarchie de navigation du canal apparaît dans le siège, le catalogue, puis les canaux.</span><span class="sxs-lookup"><span data-stu-id="bc959-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and channels.</span></span>

![Tri de la hiérarchie de navigation du canal personnalisée](./media/ChannelNavCustomSorted.png)

![Tri de la hiérarchie de navigation du canal personnalisée selon la hiérarchie de navigation du canal](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV avec des catégories triées par personnalisation](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="bc959-147">Par défaut, la fonctionnalité d'ordre de tri personnalisé est désactivée.</span><span class="sxs-lookup"><span data-stu-id="bc959-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="bc959-148">Pour savoir comment activer cette fonctionnalité et les autres, consultez [Gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="bc959-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]