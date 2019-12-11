---
title: Personnaliser la navigation dans le site
description: Cette rubrique décrit la procédure de création d'une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8e1efb4a7484bd4626886c0f9aa40c3e4dfe304a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697472"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="d0bc7-103">Personnaliser la navigation dans le site</span><span class="sxs-lookup"><span data-stu-id="d0bc7-103">Customize site navigation</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d0bc7-104">Cette rubrique décrit la procédure de création d'une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="d0bc7-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="d0bc7-105">Overview</span></span>

<span data-ttu-id="d0bc7-106">Les vitrines en ligne permettent généralement aux clients de découvrir et parcourir des produits en navigant dans les catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="d0bc7-107">Cette fonctionnalité est généralement fournie par des onglets en haut de la page ou une barre de navigation à gauche.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="d0bc7-108">Dans Dynamics 365 Commerce, vous pouvez créer et gérer la structure hiérarchique de votre navigation par catégorie et les produits inclus dans les différentes catégories.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-retail-channel-navigation-hierarchy"></a><span data-ttu-id="d0bc7-109">Créer une hiérarchie de navigation du canal de vente au détail</span><span class="sxs-lookup"><span data-stu-id="d0bc7-109">Create a retail channel navigation hierarchy</span></span>

<span data-ttu-id="d0bc7-110">Pour créer une hiérarchie de navigation du canal de vente au détail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-110">To create a retail channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="d0bc7-111">Accédez à **Vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-111">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="d0bc7-112">Sélectionnez **Hiérarchies des catégories**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="d0bc7-113">Nommez la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0bc7-114">La catégorie principale que vous créez est le nœud de catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="d0bc7-115">Elle n'est pas affichée sur votre site.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-115">It won't be shown on your site.</span></span> <span data-ttu-id="d0bc7-116">Pour créer une hiérarchie de catégories dans laquelle un seul nœud principal s'affiche sur votre site, créez et nommez la catégorie en tant qu'enfant de la catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="d0bc7-117">Sélectionnez **Nouveau nœud de catégorie**, puis nommez la catégorie.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="d0bc7-118">Continuez à créer des catégories jumelles et parents comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="d0bc7-119">Vous pouvez ensuite affecter les produits à chaque catégorie que vous avez créée sous la catégorie principale.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="d0bc7-120">Personnalisation de l'ordre de catégories</span><span class="sxs-lookup"><span data-stu-id="d0bc7-120">Customize the order of categories</span></span>

<span data-ttu-id="d0bc7-121">Par défaut, les catégories que vous définissez s'affichent dans l'ordre alphabétique sur votre site.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="d0bc7-122">Toutefois, vous pouvez également personnaliser l'ordre d'affichage de catégories.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="d0bc7-123">Affectation d'un type de hiérarchie de catégories</span><span class="sxs-lookup"><span data-stu-id="d0bc7-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="d0bc7-124">Accédez à **Vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-124">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="d0bc7-125">Sélectionnez **Hiérarchie de catégories**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="d0bc7-126">Sur le volet Actions, sous l'onglet **Hiérarchie de catégories**, dans le groupe **Paramétrer**, cliquez sur **Associer le type de hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="d0bc7-127">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-127">Select **New**.</span></span>
1. <span data-ttu-id="d0bc7-128">Dans le champ **Type de hiérarchie de catégories**, sélectionnez **Hiérarchie de navigation du canal de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-128">In the **Category hierarchy type** field, select **Retail channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="d0bc7-129">Dans le champ **Hiérarchie de catégories**, sélectionnez la hiérarchie de navigation de canal que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="d0bc7-130">Publier des hiérarchies de navigation nouvelles ou mises à jour</span><span class="sxs-lookup"><span data-stu-id="d0bc7-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="d0bc7-131">Pour rendre la hiérarchie de navigation disponible sur votre vitrine en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="d0bc7-132">Accédez à **Vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-132">Go to **Retail \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="d0bc7-133">Dans l'arborescence à gauche, sélectionnez votre magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="d0bc7-134">Sélectionnez **Publier les mises à jour du canal**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="d0bc7-135">Accédez à **Vente au détail \> Informatique de vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-135">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="d0bc7-136">Dans la liste, recherchez et sélectionnez **Tâche 1040**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="d0bc7-137">Sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-137">Select **Run now**.</span></span>
1. <span data-ttu-id="d0bc7-138">Répétez les étapes 5 et 6 pour les tâches 1070 et 1150.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="d0bc7-139">Afficher les catégories sur votre site</span><span class="sxs-lookup"><span data-stu-id="d0bc7-139">Show categories on your site</span></span>

<span data-ttu-id="d0bc7-140">Pour afficher la hiérarchie de catégories de votre vitrine en ligne, vous devez ajouter le module du menu de navigation à l'emplacement approprié dans un modèle ou un fragment.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="d0bc7-141">Le module du menu de navigation affiche alors la hiérarchie de navigation, si tant est que vous avez publié votre hiérarchie de navigation de vente au détail sur le canal auquel votre site est associé.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your retail navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="d0bc7-142">Le module du menu de navigation qui est inclus dans le kit de démarrage du magasin permet aux utilisateurs d'accéder uniquement aux catégories qui n'ont pas de sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="d0bc7-143">Si vos clients peuvent accéder aux catégories qui ont des sous-catégories, vous devez personnaliser le module du menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="d0bc7-144">Ajouter des options de navigation personnalisée</span><span class="sxs-lookup"><span data-stu-id="d0bc7-144">Add custom navigation options</span></span>

<span data-ttu-id="d0bc7-145">Dans le menu de navigation, vous pouvez ajouter des options de navigation qui ne font pas partie de votre hiérarchie de catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="d0bc7-146">Par exemple, à la fin de la liste de catégories de produit, vous pouvez ajouter un élément **Nous contacter** qui désigne une page de contact que vous avez paramétrée pour votre site.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="d0bc7-147">Pour ajouter des options de navigation personnalisées à votre menu de navigation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="d0bc7-148">Dans le modèle ou le fragment que vous souhaitez personnaliser, sélectionnez le module du menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="d0bc7-149">Dans le volet de propriété, sous l'onglet **Données**, sélectionnez **Ajouter un article** pour créer un article de navigation du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="d0bc7-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="d0bc7-150">Entrez le texte du lien et une URL.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="d0bc7-151">Répétez les étapes 2 et 3 pour ajouter des options de navigation plus personnalisées.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="d0bc7-152">Lorsque vous avez terminé, enregistrez le modèle ou le fragment, et archivez-le.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0bc7-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d0bc7-153">Additional resources</span></span>

[<span data-ttu-id="d0bc7-154">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="d0bc7-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="d0bc7-155">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="d0bc7-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="d0bc7-156">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="d0bc7-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="d0bc7-157">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="d0bc7-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="d0bc7-158">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="d0bc7-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="d0bc7-159">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="d0bc7-159">Create a page URL</span></span>](create-page-url.md)
