---
title: Créer une hiérarchie de navigation du canal
description: Cette rubrique décrit comment créer une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5df46de9dadfa0b7160a9b340ef36fdf963a0ad3
ms.sourcegitcommit: 6c2f5c3b038f696532c335e20b0fbafa155d6858
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5951906"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="71fad-103">Créer une hiérarchie de navigation dans un canal</span><span class="sxs-lookup"><span data-stu-id="71fad-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="71fad-104">Cette rubrique décrit comment créer une hiérarchie de navigation de canal dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="71fad-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="71fad-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="71fad-105">Overview</span></span>

<span data-ttu-id="71fad-106">Une hiérarchie de navigation de canal est utilisée pour regrouper et organiser les produits en catégories afin de pouvoir les parcourir en ligne ou dans un point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="71fad-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="71fad-107">Créer une hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="71fad-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="71fad-108">Pour créer une hiérarchie de navigation du canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="71fad-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="71fad-109">Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Catégories de navigation du canal**.</span><span class="sxs-lookup"><span data-stu-id="71fad-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="71fad-110">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="71fad-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="71fad-111">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="71fad-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="71fad-112">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="71fad-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="71fad-113">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="71fad-113">Select **Create**.</span></span>
1. <span data-ttu-id="71fad-114">Dans le volet Actions, sélectionnez **Nouveau nœud de catégorie** pour créer un nœud racine.</span><span class="sxs-lookup"><span data-stu-id="71fad-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="71fad-115">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="71fad-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="71fad-116">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="71fad-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="71fad-117">Dans la zone **Nom convivial**, entrez un nom convivial.</span><span class="sxs-lookup"><span data-stu-id="71fad-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="71fad-118">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="71fad-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="71fad-119">L’image suivante montre un exemple de nœud racine.</span><span class="sxs-lookup"><span data-stu-id="71fad-119">The following image shows a example root node.</span></span>

![Exemple de nœud racine](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="71fad-121">Crer des nœuds de catégorie de navigation</span><span class="sxs-lookup"><span data-stu-id="71fad-121">Create navigation category nodes</span></span>

<span data-ttu-id="71fad-122">Pour créer des nœuds de catégorie de navigation supplémentaires pour représenter les catégories de produits sur le canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="71fad-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="71fad-123">Dans le volet de navigation, sélectionnez le nœud parent auquel ajouter une catégorie.</span><span class="sxs-lookup"><span data-stu-id="71fad-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="71fad-124">Dans le volet Actions, sélectionnez **Nouveau nœud de catégories**.</span><span class="sxs-lookup"><span data-stu-id="71fad-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="71fad-125">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="71fad-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="71fad-126">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="71fad-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="71fad-127">Dans la zone **Nom convivial**, entrez un nom convivial.</span><span class="sxs-lookup"><span data-stu-id="71fad-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="71fad-128">Dans la zone **Ordre d’affichage**, entrez un ordre d’affichage (optionnel).</span><span class="sxs-lookup"><span data-stu-id="71fad-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="71fad-129">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="71fad-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="71fad-130">L’image suivante montre un exemple d’une hiérarchie de navigation de canal terminée.</span><span class="sxs-lookup"><span data-stu-id="71fad-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Exemple de hiérarchie du canal](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="71fad-132">Ajouter des produits à des nœuds de catégorie</span><span class="sxs-lookup"><span data-stu-id="71fad-132">Add products to category nodes</span></span>

<span data-ttu-id="71fad-133">Pour ajouter des produits à des nœuds de catégorie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="71fad-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="71fad-134">Sélectionnez un nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="71fad-134">Select a category node.</span></span>
1. <span data-ttu-id="71fad-135">Sous **Produits**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="71fad-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="71fad-136">Recherchez les nouveaux produits que vous souhaitez ajouter à l’aide du numéro de produit ou du nom du produit, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="71fad-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="71fad-137">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="71fad-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="71fad-138">L’ajout de produits à un nœud à l’intérieur de la hiérarchie de navigation de canal n’est pas suffisant pour que les produits apparaissent sur un canal sélectionné, les produits doivent également être assortis à un canal.</span><span class="sxs-lookup"><span data-stu-id="71fad-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a channel.</span></span> <span data-ttu-id="71fad-139">Pour plus d'informations sur les assortiments, voir [Gestion des assortiments](assortments.md).</span><span class="sxs-lookup"><span data-stu-id="71fad-139">For more information on assortments, see [Assortment management](assortments.md).</span></span>

<span data-ttu-id="71fad-140">L’image suivant présente un exemple de nœud avec produits ajoutés.</span><span class="sxs-lookup"><span data-stu-id="71fad-140">The following image shows an example node with products added.</span></span>

![Produits ajoutés à un nœud de catégorie](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="71fad-142">Ajouter des groupes d’attributs de produit à des nœuds de catégorie</span><span class="sxs-lookup"><span data-stu-id="71fad-142">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="71fad-143">Les groupes d’attributs doivent être créés avant de pouvoir les ajouter à un nœud dans la hiérarchie de navigation des canaux.</span><span class="sxs-lookup"><span data-stu-id="71fad-143">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="71fad-144">Pour ajouter un produit d’un groupe d’attributs à un nœud de catégorie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="71fad-144">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="71fad-145">Sélectionnez un nœud de catégorie.</span><span class="sxs-lookup"><span data-stu-id="71fad-145">Select a category node.</span></span>
1. <span data-ttu-id="71fad-146">Sous **Groupe d’attributs de produit**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="71fad-146">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="71fad-147">Recherchez le ou les groupes d’attributs que vous souhaitez ajouter, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="71fad-147">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="71fad-148">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="71fad-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="71fad-149">L’image suivant présente un exemple de nœud avec des groupes d’attributs de produits ajoutés.</span><span class="sxs-lookup"><span data-stu-id="71fad-149">The following image shows a sample node with product attribute groups added.</span></span>

![Groupes d’attributs de produit sur un nœud](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="71fad-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="71fad-151">Additional resources</span></span>

[<span data-ttu-id="71fad-152">Paramétrer des assortiments</span><span class="sxs-lookup"><span data-stu-id="71fad-152">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="71fad-153">Gérer les attributs et les groupes d’attributs</span><span class="sxs-lookup"><span data-stu-id="71fad-153">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
