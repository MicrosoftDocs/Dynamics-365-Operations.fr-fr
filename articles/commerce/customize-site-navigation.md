---
title: Personnaliser la navigation dans le site
description: Cette rubrique décrit la procédure de création d’une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cfd0a9559eb2b596adb822b228929e6855711bb4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222607"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="8c88c-103">Personnaliser la navigation dans le site</span><span class="sxs-lookup"><span data-stu-id="8c88c-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8c88c-104">Cette rubrique décrit la procédure de création d’une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8c88c-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="8c88c-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="8c88c-105">Overview</span></span>

<span data-ttu-id="8c88c-106">Les vitrines en ligne permettent généralement aux clients de découvrir et parcourir des produits en navigant dans les catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="8c88c-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="8c88c-107">Cette fonctionnalité est généralement fournie par des onglets en haut de la page ou une barre de navigation à gauche.</span><span class="sxs-lookup"><span data-stu-id="8c88c-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="8c88c-108">Dans Dynamics 365 Commerce, vous pouvez créer et gérer la structure hiérarchique de votre navigation par catégorie et les produits inclus dans les différentes catégories.</span><span class="sxs-lookup"><span data-stu-id="8c88c-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="8c88c-109">Créer une hiérarchie de navigation du canal</span><span class="sxs-lookup"><span data-stu-id="8c88c-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="8c88c-110">Pour créer une hiérarchie de navigation du canal, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8c88c-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="8c88c-111">Accédez à **Commerce et vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="8c88c-112">Sélectionnez **Hiérarchies des catégories**, puis sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="8c88c-113">Nommez la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="8c88c-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c88c-114">La catégorie principale que vous créez est le nœud de catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="8c88c-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="8c88c-115">Elle n'est pas affichée sur votre site.</span><span class="sxs-lookup"><span data-stu-id="8c88c-115">It won't be shown on your site.</span></span> <span data-ttu-id="8c88c-116">Pour créer une hiérarchie de catégories dans laquelle un seul nœud principal s'affiche sur votre site, créez et nommez la catégorie en tant qu'enfant de la catégorie racine.</span><span class="sxs-lookup"><span data-stu-id="8c88c-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="8c88c-117">Sélectionnez **Nouveau nœud de catégorie**, puis nommez la catégorie.</span><span class="sxs-lookup"><span data-stu-id="8c88c-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="8c88c-118">Continuez à créer des catégories jumelles et parents comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="8c88c-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="8c88c-119">Vous pouvez ensuite affecter les produits à chaque catégorie que vous avez créée sous la catégorie principale.</span><span class="sxs-lookup"><span data-stu-id="8c88c-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="8c88c-120">Personnalisation de l'ordre de catégories</span><span class="sxs-lookup"><span data-stu-id="8c88c-120">Customize the order of categories</span></span>

<span data-ttu-id="8c88c-121">Par défaut, les catégories que vous définissez s'affichent dans l'ordre alphabétique sur votre site.</span><span class="sxs-lookup"><span data-stu-id="8c88c-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="8c88c-122">Toutefois, vous pouvez également personnaliser l'ordre d'affichage de catégories.</span><span class="sxs-lookup"><span data-stu-id="8c88c-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="8c88c-123">Affectation d'un type de hiérarchie de catégories</span><span class="sxs-lookup"><span data-stu-id="8c88c-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="8c88c-124">Accédez à **Commerce et vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="8c88c-125">Sélectionnez **Hiérarchie de catégories**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="8c88c-126">Sur le volet Actions, sous l'onglet **Hiérarchie de catégories**, dans le groupe **Paramétrer**, cliquez sur **Associer le type de hiérarchie**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="8c88c-127">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-127">Select **New**.</span></span>
1. <span data-ttu-id="8c88c-128">Dans le champ **Type de hiérarchie de catégories**, sélectionnez **Hiérarchie de navigation du canal**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="8c88c-129">Dans le champ **Hiérarchie de catégories**, sélectionnez la hiérarchie de navigation de canal que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="8c88c-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="8c88c-130">Publier des hiérarchies de navigation nouvelles ou mises à jour</span><span class="sxs-lookup"><span data-stu-id="8c88c-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="8c88c-131">Pour rendre la hiérarchie de navigation disponible sur votre vitrine en ligne, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8c88c-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="8c88c-132">Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="8c88c-133">Dans l'arborescence à gauche, sélectionnez votre magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="8c88c-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="8c88c-134">Sélectionnez **Publier les mises à jour du canal**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="8c88c-135">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="8c88c-136">Dans la liste, recherchez et sélectionnez **Tâche 1040**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="8c88c-137">Sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="8c88c-137">Select **Run now**.</span></span>
1. <span data-ttu-id="8c88c-138">Répétez les étapes 5 et 6 pour les tâches 1070 et 1150.</span><span class="sxs-lookup"><span data-stu-id="8c88c-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="8c88c-139">Afficher les catégories sur votre site</span><span class="sxs-lookup"><span data-stu-id="8c88c-139">Show categories on your site</span></span>

<span data-ttu-id="8c88c-140">Pour afficher la hiérarchie de catégories de votre vitrine en ligne, vous devez ajouter le module du menu de navigation à l'emplacement approprié dans un modèle ou un fragment.</span><span class="sxs-lookup"><span data-stu-id="8c88c-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="8c88c-141">Le module du menu de navigation affiche alors la hiérarchie de navigation, si tant est que vous avez publié votre hiérarchie de navigation sur le canal auquel votre site est associé.</span><span class="sxs-lookup"><span data-stu-id="8c88c-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="8c88c-142">Le module du menu de navigation qui est inclus dans la bibliothèque de modules permet aux utilisateurs d'accéder uniquement aux catégories qui n'ont pas de sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="8c88c-142">The navigation menu module that is included in the module library lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="8c88c-143">Si vos clients peuvent accéder aux catégories qui ont des sous-catégories, vous devez personnaliser le module du menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="8c88c-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="8c88c-144">Ajouter des options de navigation personnalisée</span><span class="sxs-lookup"><span data-stu-id="8c88c-144">Add custom navigation options</span></span>

<span data-ttu-id="8c88c-145">Dans le menu de navigation, vous pouvez ajouter des options de navigation qui ne font pas partie de votre hiérarchie de catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="8c88c-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="8c88c-146">Par exemple, à la fin de la liste de catégories de produit, vous pouvez ajouter un élément **Nous contacter** qui désigne une page de contact que vous avez paramétrée pour votre site.</span><span class="sxs-lookup"><span data-stu-id="8c88c-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="8c88c-147">Pour ajouter des options de navigation personnalisées à votre menu de navigation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="8c88c-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="8c88c-148">Dans le modèle ou le fragment que vous souhaitez personnaliser, sélectionnez le module du menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="8c88c-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="8c88c-149">Dans le volet de propriété, sous l'onglet **Données**, sélectionnez **Ajouter un article** pour créer un article de navigation du système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="8c88c-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="8c88c-150">Entrez le texte du lien et une URL.</span><span class="sxs-lookup"><span data-stu-id="8c88c-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="8c88c-151">Répétez les étapes 2 et 3 pour ajouter des options de navigation plus personnalisées.</span><span class="sxs-lookup"><span data-stu-id="8c88c-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="8c88c-152">Lorsque vous avez terminé, sélectionnez **Enregistrer** pour enregistrer le modèle ou le fragment, puis cliquez sur **Terminer la modification** pour l'archiver.</span><span class="sxs-lookup"><span data-stu-id="8c88c-152">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c88c-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8c88c-153">Additional resources</span></span>

[<span data-ttu-id="8c88c-154">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="8c88c-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="8c88c-155">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="8c88c-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="8c88c-156">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="8c88c-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="8c88c-157">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="8c88c-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="8c88c-158">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="8c88c-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="8c88c-159">Créer une URL de page</span><span class="sxs-lookup"><span data-stu-id="8c88c-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="8c88c-160">Utilisation de groupes de publication</span><span class="sxs-lookup"><span data-stu-id="8c88c-160">Work with publish groups</span></span>](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]