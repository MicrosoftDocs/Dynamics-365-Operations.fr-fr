---
title: Créer un hiérarchie de produit
description: Cette rubrique décrit comment créer une hiérarchie de produit dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412193"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="e6860-103">Créer un hiérarchie de produit</span><span class="sxs-lookup"><span data-stu-id="e6860-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e6860-104">Cette rubrique décrit comment créer une hiérarchie de produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6860-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e6860-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e6860-105">Overview</span></span>

<span data-ttu-id="e6860-106">Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e6860-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="e6860-107">Ces canaux de vente au détail comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels).</span><span class="sxs-lookup"><span data-stu-id="e6860-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="e6860-108">Chaque canal de magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel.</span><span class="sxs-lookup"><span data-stu-id="e6860-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="e6860-109">Vous devez paramétrer tous ces éléments avant de pouvoir créer un canal de magasin de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e6860-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="e6860-110">Une hiérarchie de produit Commerce est utilisée pour définir la hiérarchie des produits globale pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e6860-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="e6860-111">Vous pouvez utiliser une hiérarchie de produit Commerce pour la promotion des ventes, la tarification et les promotions, la génération d'états et la planification d'assortiment.</span><span class="sxs-lookup"><span data-stu-id="e6860-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="e6860-112">Une seule hiérarchie de produits Commerce peut être affectée par organisation.</span><span class="sxs-lookup"><span data-stu-id="e6860-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="e6860-113">Créer et configurer une hiérarchie de produit</span><span class="sxs-lookup"><span data-stu-id="e6860-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="e6860-114">Pour créer et configurer une hiérarchie de produit Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e6860-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="e6860-115">Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Hiérarchie de produit Commerce**.</span><span class="sxs-lookup"><span data-stu-id="e6860-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="e6860-116">Si aucune hiérarchie n'existe encore, dans le **Volet Actions**, sélectionnez **Nouveau** pour créer la racine de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="e6860-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="e6860-117">Sous **Général** :</span><span class="sxs-lookup"><span data-stu-id="e6860-117">Under **General**:</span></span>
    1. <span data-ttu-id="e6860-118">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="e6860-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="e6860-119">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="e6860-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="e6860-120">Dans la zone **Nom convivial**, entrez un nom convivial.</span><span class="sxs-lookup"><span data-stu-id="e6860-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="e6860-121">Paramétrez **Actif** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e6860-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="e6860-122">Ajouter des nœuds de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="e6860-122">Add hierarchy nodes</span></span>

<span data-ttu-id="e6860-123">Pour ajouter des nœuds de hiérarchie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e6860-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="e6860-124">Dans le volet Actions, sélectionnez **Modifier la hiérarchie de catégories**.</span><span class="sxs-lookup"><span data-stu-id="e6860-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="e6860-125">Sélectionnez le nœud parent auquel vous souhaitez ajouter un nouveau nœud, puis sélectionnez **Nouveau nœud de catégorie**.</span><span class="sxs-lookup"><span data-stu-id="e6860-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="e6860-126">Dans la section **Général**, fournissez les éléments suivants : **Nom**, **Description**, **Nom convivial** et **Mots clés**.</span><span class="sxs-lookup"><span data-stu-id="e6860-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="e6860-127">Sous **Général** :</span><span class="sxs-lookup"><span data-stu-id="e6860-127">Under **General**:</span></span>
    1. <span data-ttu-id="e6860-128">Dans la zone **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="e6860-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="e6860-129">Entrez une description dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="e6860-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="e6860-130">Dans la zone **Nom convivial**, entrez un nom convivial.</span><span class="sxs-lookup"><span data-stu-id="e6860-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="e6860-131">Dans la zone **Mots clés**, saisissez les mots clés pertinents.</span><span class="sxs-lookup"><span data-stu-id="e6860-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="e6860-132">Dans la zone **Ordre d'affichage**, entrez un nombre pour l'ordre d'affichage (optionnel).</span><span class="sxs-lookup"><span data-stu-id="e6860-132">In the **Display order** box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="e6860-133">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e6860-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="e6860-134">Répétez les étapes ci-dessus pour ajouter des nœuds supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="e6860-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="e6860-135">L'image suivante montre la création d'un nœud de hiérarchie de produit.</span><span class="sxs-lookup"><span data-stu-id="e6860-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Créer un hiérarchie de produit](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="e6860-137">Autres paramètres</span><span class="sxs-lookup"><span data-stu-id="e6860-137">Other settings</span></span>

<span data-ttu-id="e6860-138">Des groupes d'attributs de catégorie peuvent également être affectés à chaque groupe selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="e6860-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="e6860-139">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e6860-139">Additional resources</span></span>

[<span data-ttu-id="e6860-140">hiérarchies Commerce</span><span class="sxs-lookup"><span data-stu-id="e6860-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="e6860-141">Gérer les produits et catégories de produits </span><span class="sxs-lookup"><span data-stu-id="e6860-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="e6860-142">Modifier l'ordre de tri pour les entités de promotion des ventes</span><span class="sxs-lookup"><span data-stu-id="e6860-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)
