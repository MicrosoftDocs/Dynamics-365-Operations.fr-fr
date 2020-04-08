---
title: Créer un produit dans Commerce
description: Cette rubrique décrit comment créer un produit dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: eb2dd36c6149f2aa40305cd57eac060b232b09e5
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138559"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="508a7-103">Créer un produit dans Commerce</span><span class="sxs-lookup"><span data-stu-id="508a7-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="508a7-104">Cette rubrique décrit comment créer un produit dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="508a7-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="508a7-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="508a7-105">Overview</span></span>

<span data-ttu-id="508a7-106">Un produit est principalement défini par un numéro, un nom, ainsi qu'une description du produit.</span><span class="sxs-lookup"><span data-stu-id="508a7-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="508a7-107">Toutefois, d'autres données sont également nécessaires afin de décrire un produit ou un service :</span><span class="sxs-lookup"><span data-stu-id="508a7-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="508a7-108">Créer un nouveau produit</span><span class="sxs-lookup"><span data-stu-id="508a7-108">Create a new product</span></span>

1. <span data-ttu-id="508a7-109">Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Produits lancés par catégorie**.</span><span class="sxs-lookup"><span data-stu-id="508a7-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="508a7-110">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="508a7-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="508a7-111">Dans la liste déroulante **Type de produit**, sélectionnez **Article** ou **Service**.</span><span class="sxs-lookup"><span data-stu-id="508a7-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="508a7-112">Dans la liste déroulante **Sous-type de produit**, sélectionnez **Produit** (si le produit n'aura pas de variantes) ou **Produit générique** (si le produit aura des variantes).</span><span class="sxs-lookup"><span data-stu-id="508a7-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="508a7-113">Dans la zone **Numéro de produit**, entrez un numéro de produit s'il n'est pas déjà prérempli.</span><span class="sxs-lookup"><span data-stu-id="508a7-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="508a7-114">Dans la zone **Nom de produit**, entrez un nom de produit.</span><span class="sxs-lookup"><span data-stu-id="508a7-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="508a7-115">Dans la zone **Nom de recherche**, entrez un nom de recherche.</span><span class="sxs-lookup"><span data-stu-id="508a7-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="508a7-116">Dans la liste déroulante **Catégorie de vente au détail**, sélectionnez une catégorie appropriée.</span><span class="sxs-lookup"><span data-stu-id="508a7-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="508a7-117">Si le produit est un kit, sélectionnez **Oui** pour **Kit de produits**.</span><span class="sxs-lookup"><span data-stu-id="508a7-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="508a7-118">Si le sous-type de produit est un produit générique, définissez le **Groupe de dimensions de produit** pour inclure les variantes prises en charge.</span><span class="sxs-lookup"><span data-stu-id="508a7-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="508a7-119">Les options incluent les suivantes : **Couleur**, **Taille**, **Style** et **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="508a7-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="508a7-120">Vous devrez peut-être créer des groupes de dimensions de produit supplémentaires si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="508a7-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="508a7-121">Dans la liste déroulante **Technologie de configuration**, sélectionnez une option appropriée.</span><span class="sxs-lookup"><span data-stu-id="508a7-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="508a7-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="508a7-122">Select **OK**.</span></span>

<span data-ttu-id="508a7-123">L'image suivant présente un exemple de produit ajouté.</span><span class="sxs-lookup"><span data-stu-id="508a7-123">The following image shows an example product being added.</span></span>

![Créer un produit](media/create-new-product.png)

<span data-ttu-id="508a7-125">Une fois qu'un produit est ajouté, des données supplémentaires peuvent être paramétrées pour lui, telles que **Description du produit**, **Groupes de variantes**, **Groupes de dimensions**, **Attributs du produit** et **Produits connexes**.</span><span class="sxs-lookup"><span data-stu-id="508a7-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="508a7-126">L'image suivante montre les détails supplémentaires d'un produit.</span><span class="sxs-lookup"><span data-stu-id="508a7-126">The following image shows a product's additional details.</span></span>

![Détails de produit](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="508a7-128">Créer des variantes de produits</span><span class="sxs-lookup"><span data-stu-id="508a7-128">Create product variants</span></span>

<span data-ttu-id="508a7-129">Si le sous-type de produit est **Produit générique**, des variantes spécifiques devront être créées.</span><span class="sxs-lookup"><span data-stu-id="508a7-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="508a7-130">Pour créer des variantes de produits, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="508a7-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="508a7-131">Dans le volet Actions, sélectionnez **Variantes de produit**.</span><span class="sxs-lookup"><span data-stu-id="508a7-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="508a7-132">Si des groupes de variantes ont été sélectionnés dans le volet Actions, sélectionnez \**Suggestions de variantes*.</span><span class="sxs-lookup"><span data-stu-id="508a7-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="508a7-133">Sélectionnez les variantes que vous souhaitez prendre en charge pour le produit.</span><span class="sxs-lookup"><span data-stu-id="508a7-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="508a7-134">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="508a7-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="508a7-135">Lancement d'un produit</span><span class="sxs-lookup"><span data-stu-id="508a7-135">Release a product</span></span>

<span data-ttu-id="508a7-136">Pour vendre un produit, il doit d'abord être remis à une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="508a7-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="508a7-137">Sur la page du produit, sélectionnez **Lancer des produits**.</span><span class="sxs-lookup"><span data-stu-id="508a7-137">From the product page, select **Release products**.</span></span>

    ![Lancer des produits](media/create-new-product-3.png)

1. <span data-ttu-id="508a7-139">Sélectionnez le produit à lancer, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="508a7-139">Select the product to release, and then select **Next**.</span></span>

    ![Choisissez le produit à lancer](media/create-new-product-4.png)

1. <span data-ttu-id="508a7-141">Sélectionnez le jeu de variantes de produit à lancer, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="508a7-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Choisissez des variantes à lancer](media/create-new-product-5.png)

1. <span data-ttu-id="508a7-143">Sélectionnez l'entité juridique, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="508a7-143">Select the legal entity, and then select **Next**.</span></span>

    ![Choisir une entité juridique](media/create-new-product-6.png)

1. <span data-ttu-id="508a7-145">Sélectionnez **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="508a7-145">Select **Finish**.</span></span>

    ![Terminer le lancement de produit](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="508a7-147">Configurer un produit lancé</span><span class="sxs-lookup"><span data-stu-id="508a7-147">Configure a released product</span></span>

<span data-ttu-id="508a7-148">Une fois qu'un produit est lancé, il nécessitera alors une configuration supplémentaire qui comprend l'ajout d'un prix au produit.</span><span class="sxs-lookup"><span data-stu-id="508a7-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="508a7-149">Dans le Volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Produits et catégories \> Produits lancés par catégorie**.</span><span class="sxs-lookup"><span data-stu-id="508a7-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="508a7-150">Sélectionnez le nœud de catégorie de produit pour le produit qui a été lancé, puis sélectionnez le produit dans la liste des produits.</span><span class="sxs-lookup"><span data-stu-id="508a7-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="508a7-151">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="508a7-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="508a7-152">Dans la section **Achat**, configurez toutes les propriétés requises, y compris **Unité**, **Prix**  et **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="508a7-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="508a7-153">Dans le volet Actions, sélectionnez **Valider** pour garantir qu'aucune erreur n'est signalée pour les champs manquants.</span><span class="sxs-lookup"><span data-stu-id="508a7-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="508a7-154">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="508a7-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="508a7-155">L'image suivante présente un exemple de configuration pour un produit lancé.</span><span class="sxs-lookup"><span data-stu-id="508a7-155">The following image shows an example configuration for a released product.</span></span>

![Configurer un produit lancé](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="508a7-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="508a7-157">Additional resources</span></span>

[<span data-ttu-id="508a7-158">Créer des entités juridiques</span><span class="sxs-lookup"><span data-stu-id="508a7-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="508a7-159">Créer un groupe de variantes</span><span class="sxs-lookup"><span data-stu-id="508a7-159">Create a variant group</span></span>](create-variant-group.md) 
