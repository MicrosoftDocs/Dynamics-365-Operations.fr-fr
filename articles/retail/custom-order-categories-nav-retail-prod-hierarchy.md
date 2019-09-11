---
title: Modifier l'ordre de tri pour les entités de promotion des ventes
description: Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes dans Microsoft Dynamics 365 for Retail.
author: ashishharchwani
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2be3c1198ac6fff851be1bead2f0995202f1f0e7
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1866159"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="a08c8-103">Modifier l'ordre de tri pour les entités de promotion des ventes</span><span class="sxs-lookup"><span data-stu-id="a08c8-103">Change the sort order for merchandising entities</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a08c8-104">Les détaillants considèrent que la découverte d'un produit est l'outil principal pour l'interaction de clients entre les canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="a08c8-104">Retailers consider product discovery a primary tool for customer interaction across all retail channels.</span></span> <span data-ttu-id="a08c8-105">Différentes fonctionnalités peuvent aider les clients à découvrir facilement des produits.</span><span class="sxs-lookup"><span data-stu-id="a08c8-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="a08c8-106">Ils peuvent par exemple parcourir des catégories, faire des recherches, et filtrer.</span><span class="sxs-lookup"><span data-stu-id="a08c8-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="a08c8-107">Cette rubrique explique les concepts relatifs aux contrôle de l'ordre d'affichage pour différentes entités associées à un événement de promotion des ventes.</span><span class="sxs-lookup"><span data-stu-id="a08c8-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="a08c8-108">Elle décrit également comment modifier l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="a08c8-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="a08c8-109">Présentation</span><span class="sxs-lookup"><span data-stu-id="a08c8-109">Overview</span></span>

<span data-ttu-id="a08c8-110">La prise en charge du tri de différentes entités associées à un événement de promotion des ventes a été améliorée.</span><span class="sxs-lookup"><span data-stu-id="a08c8-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="a08c8-111">Cette prise en charge correspond désormais mieux aux scénarios client existants qui nécessitaient auparavant des extensions de la part des partenaires d'implémentation.</span><span class="sxs-lookup"><span data-stu-id="a08c8-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="a08c8-112">Dans les versions de Microsoft Dynamics 365 for Retail qui sont antérieures à la version 10.0.5, la commande de tri pour les catégories de la hiérarchie de navigation était dans l'ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="a08c8-112">In versions of Microsoft Dynamics 365 for Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="a08c8-113">La nouvelle fonctionnalité d'ordre de tri personnalisée permet aux responsables des ventes de configurer la commande de tri pour différentes entités associées à un événement de promotion des ventes entre tous les clients de l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="a08c8-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="a08c8-114">Ces clients incluent les sièges sociaux et les centres d'appels.</span><span class="sxs-lookup"><span data-stu-id="a08c8-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-retail-product-hierarchy"></a><span data-ttu-id="a08c8-115">Configuration de l'ordre d'affichage des catégories de la hiérarchie des produits vendus au détail</span><span class="sxs-lookup"><span data-stu-id="a08c8-115">Configure the display order for categories in the retail product hierarchy</span></span>

<span data-ttu-id="a08c8-116">Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a08c8-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="a08c8-117">Accédez à **Vente au détail \> Produits et catégories \> Hiérarchie des produits vendus au détail**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-117">Go to **Retail \> Products and categories \> Retail product hierarchy**.</span></span>
2. <span data-ttu-id="a08c8-118">Cliquez sur **Modifier la hiérarchie de la catégorie**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="a08c8-119">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-119">Click **Edit**.</span></span>
4. <span data-ttu-id="a08c8-120">Dans l'arborescence, développez **ALL \> Action Sports**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="a08c8-121">Dans l'arborescence, développez **ALL \> Team Sports**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="a08c8-122">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="a08c8-123">(Ce nombre peut être négatif.)</span><span class="sxs-lookup"><span data-stu-id="a08c8-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="a08c8-124">Répétez les étapes 4 à 6 pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.</span><span class="sxs-lookup"><span data-stu-id="a08c8-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="a08c8-125">L'ordre d'affichage pour la hiérarchie de navigation du canal est reportée dans le siège pour la hiérarchie des produits vendus au détail et les produits lancés par catégorie.</span><span class="sxs-lookup"><span data-stu-id="a08c8-125">The display order for the channel navigation hierarchy will be reflected in HQ for the retail product hierarchy and released products by category.</span></span>

![Hiérarchie des produits vendus au détail personnalisée triée par des valeurs négatives](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Tri personnalisé des produits lancés par catégorie selon la hiérarchie des produits vendus au détail](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="a08c8-128">Configuration de l'ordre d'affichage des catégories de la hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="a08c8-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="a08c8-129">Avant de pouvoir exécuter cette procédure, les données de démonstration doivent être installées dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="a08c8-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="a08c8-130">Allez dans **Vente au détail \> Produits et catégories \> Catégories de navigation du canal**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-130">Go to **Retail \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="a08c8-131">Dans la liste, sélectionnez la hiérarchie **Navigation de mode**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="a08c8-132">Cliquez sur **Modifier la hiérarchie de la catégorie**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="a08c8-133">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-133">Click **Edit**.</span></span>
5. <span data-ttu-id="a08c8-134">Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="a08c8-135">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="a08c8-136">Dans l'arborescence, sélectionnez **Fashion \> Womenswear \> Tops**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="a08c8-137">De même, vous pouvez définir l'ordre de tri pour les sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="a08c8-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="a08c8-138">Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Casual Shirts**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="a08c8-139">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="a08c8-140">Dans l'arborescence, sélectionnez **Fashion \> Menswear \> Coats & Jackets**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="a08c8-141">Entrez un nombre dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="a08c8-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="a08c8-142">Répétez pour toutes les catégories supplémentaires dont vous souhaitez modifier l'ordre.</span><span class="sxs-lookup"><span data-stu-id="a08c8-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="a08c8-143">L'ordre d'affichage pour la hiérarchie de navigation du canal apparaît dans le siège, le catalogue, puis les canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="a08c8-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and retail channels.</span></span>

![Tri de la hiérarchie de navigation du canal personnalisée](./media/ChannelNavCustomSorted.png)

![Tri de la hiérarchie de navigation du canal personnalisée selon la hiérarchie de navigation du canal](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV avec des catégories triées par personnalisation](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="a08c8-147">Par défaut, la fonctionnalité d'ordre de tri personnalisé est désactivée.</span><span class="sxs-lookup"><span data-stu-id="a08c8-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="a08c8-148">Pour savoir comment activer cette fonctionnalité et les autres, consultez [Gestion des fonctionnalités](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="a08c8-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>
