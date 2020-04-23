---
title: Module d'en-tête
description: Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/13/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cec138ebefbd2beb2f1cf6302ce58d8bbc5c4bbd
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261442"
---
# <a name="header-module"></a><span data-ttu-id="41587-103">Module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="41587-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="41587-104">Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="41587-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="41587-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="41587-105">Overview</span></span>

<span data-ttu-id="41587-106">Dans Dynamics 365 Commerce, un en-tête de page comprend plusieurs modules, tels que les modules d'en-tête, de menu de navigation, de recherche, de bannière promotionnelle et de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="41587-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="41587-107">Le module d'en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, un symbole de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="41587-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="41587-108">Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="41587-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="41587-109">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="41587-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="41587-110">Propriétés d'un module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="41587-110">Properties of a header module</span></span>

<span data-ttu-id="41587-111">Un module d'en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**.</span><span class="sxs-lookup"><span data-stu-id="41587-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="41587-112">Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page.</span><span class="sxs-lookup"><span data-stu-id="41587-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="41587-113">Pour plus d'informations, voir [Ajouter un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="41587-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="41587-114">La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="41587-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="41587-115">Modules disponibles dans le module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="41587-115">Modules that are available in a header module</span></span>

<span data-ttu-id="41587-116">Les modules suivants peuvent être utilisés dans un module d'en-tête :</span><span class="sxs-lookup"><span data-stu-id="41587-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="41587-117">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="41587-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="41587-118">La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="41587-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="41587-119">Le menu de navigation a une propriété **Source de navigation** qui est utilisée pour spécifier les éléments de menu statique et les éléments de menu de navigation Serveur de vente au détail comme source.</span><span class="sxs-lookup"><span data-stu-id="41587-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="41587-120">Si des éléments de menu statique sont spécifiés comme source, des liens relatifs vers d'autres pages du site peuvent être fournis.</span><span class="sxs-lookup"><span data-stu-id="41587-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="41587-121">Les articles configurés s'affichent alors comme navigation d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="41587-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="41587-122">**Rechercher** – Le module de recherche permet aux utilisateurs d'entrer des critères de recherche pour des produits.</span><span class="sxs-lookup"><span data-stu-id="41587-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="41587-123">L'URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l'adresse **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="41587-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="41587-124">Le module de recherche possède des propriétés qui vous permettent de supprimer l'étiquette ou le bouton de recherche selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="41587-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="41587-125">Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.</span><span class="sxs-lookup"><span data-stu-id="41587-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>
- <span data-ttu-id="41587-126">**Icône de panier** - Le module d'icône de panier représente l'icône de panier, qui indique le nombre d'articles dans le panier à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="41587-126">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="41587-127">Pour plus d'informations, voir [Module Icône de panier](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="41587-127">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="41587-128">Créer un module d'en-tête pour une page</span><span class="sxs-lookup"><span data-stu-id="41587-128">Create a header module for a page</span></span>

<span data-ttu-id="41587-129">Pour créer un module d'en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="41587-129">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="41587-130">Créez un fragment nommé **fragment d'en-tête**, puis ajoutez un module de conteneur à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="41587-130">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="41587-131">Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="41587-131">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="41587-132">Ajoutez des modules de bannière promotionnelle et de consentement aux cookies au module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="41587-132">Add a promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="41587-133">Ajoutez un autre module de conteneur au fragment puis définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="41587-133">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="41587-134">Ajoutez un module d'en-tête au deuxième module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="41587-134">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="41587-135">Dans l'emplacement **menu de navigation** du module d'en-tête, ajoutez un module de menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="41587-135">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="41587-136">Dans le volet de propriétés du module de menu de navigation, configurez les propriétés du module de menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="41587-136">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="41587-137">Dans l'emplacement **Rechercher** du module d'en-tête, ajoutez un module de recherche.</span><span class="sxs-lookup"><span data-stu-id="41587-137">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="41587-138">Dans le volet de propriétés du module de recherche, configurez les propriétés du module de recherche.</span><span class="sxs-lookup"><span data-stu-id="41587-138">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="41587-139">Dans l'emplacement **Icône de panier** du module d'en-tête, ajoutez un module d'icône de panier.</span><span class="sxs-lookup"><span data-stu-id="41587-139">In the **Cart icon** slot of the header module, add a cart icon module.</span></span> 
1. <span data-ttu-id="41587-140">Dans le volet de propriétés du module Icône de panier, configurez les propriétés du module Icône de panier.</span><span class="sxs-lookup"><span data-stu-id="41587-140">In the property pane for the cart icon module, configure the properties of the cart icon module.</span></span> <span data-ttu-id="41587-141">Si vous souhaitez que l'icône du panier affiche un mini-panier lorsque vous passez la souris dessus, sélectionnez **Vrai** pour **Afficher le mini panier**.</span><span class="sxs-lookup"><span data-stu-id="41587-141">If you want the cart icon to display a mini cart when hovered over, select **True** for **Show mini cart**.</span></span>
1. <span data-ttu-id="41587-142">Enregistrez le fragment de page, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="41587-142">Save the page fragment, finish editing, and publish it.</span></span> 


<span data-ttu-id="41587-143">Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="41587-143">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="41587-144">Dans l'emplacement **Principal** de la page par défaut, ajoutez le fragment de page d'en-tête qui contient le module d'en-tête à l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="41587-144">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="41587-145">Enregistrez le modèle, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="41587-145">Save the template, finish editing, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="41587-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="41587-146">Additional resources</span></span>

[<span data-ttu-id="41587-147">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="41587-147">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="41587-148">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="41587-148">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="41587-149">Module de zone d'achat</span><span class="sxs-lookup"><span data-stu-id="41587-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="41587-150">Module de panier</span><span class="sxs-lookup"><span data-stu-id="41587-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="41587-151">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="41587-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="41587-152">Module de validation</span><span class="sxs-lookup"><span data-stu-id="41587-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="41587-153">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="41587-153">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="41587-154">Module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="41587-154">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="41587-155">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="41587-155">Footer module</span></span>](author-footer-module.md)
