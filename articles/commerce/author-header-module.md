---
title: Module d'en-tête
description: Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025656"
---
# <a name="header-module"></a><span data-ttu-id="fc639-103">Module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="fc639-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fc639-104">Cette rubrique couvre les modules d'en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fc639-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fc639-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="fc639-105">Overview</span></span>

<span data-ttu-id="fc639-106">Dans Dynamics 365 Commerce, un en-tête de page comprend plusieurs modules, tels que les modules d'en-tête, de menu de navigation, de recherche, de bannière promotionnelle et de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="fc639-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="fc639-107">Le module d'en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, un symbole de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="fc639-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="fc639-108">Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="fc639-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="fc639-109">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="fc639-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="fc639-110">Propriétés d'un module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="fc639-110">Properties of a header module</span></span>

<span data-ttu-id="fc639-111">Un module d'en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**.</span><span class="sxs-lookup"><span data-stu-id="fc639-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="fc639-112">Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page.</span><span class="sxs-lookup"><span data-stu-id="fc639-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="fc639-113">Pour plus d'informations, voir [Ajouter un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="fc639-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="fc639-114">La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="fc639-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="fc639-115">Modules disponibles dans le module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="fc639-115">Modules that are available in a header module</span></span>

<span data-ttu-id="fc639-116">Les modules suivants peuvent être utilisés dans un module d'en-tête :</span><span class="sxs-lookup"><span data-stu-id="fc639-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="fc639-117">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="fc639-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="fc639-118">La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fc639-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="fc639-119">Le menu de navigation a une propriété **Source de navigation** qui est utilisée pour spécifier les éléments de menu statique et les éléments de menu de navigation Serveur de vente au détail comme source.</span><span class="sxs-lookup"><span data-stu-id="fc639-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="fc639-120">Si des éléments de menu statique sont spécifiés comme source, des liens relatifs vers d'autres pages du site peuvent être fournis.</span><span class="sxs-lookup"><span data-stu-id="fc639-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="fc639-121">Les articles configurés s'affichent alors comme navigation d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="fc639-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="fc639-122">**Rechercher** – Le module de recherche permet aux utilisateurs d'entrer des critères de recherche pour des produits.</span><span class="sxs-lookup"><span data-stu-id="fc639-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="fc639-123">L'URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l'adresse **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="fc639-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="fc639-124">Le module de recherche possède des propriétés qui vous permettent de supprimer l'étiquette ou le bouton de recherche selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fc639-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="fc639-125">Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.</span><span class="sxs-lookup"><span data-stu-id="fc639-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="fc639-126">Créer un module d'en-tête pour une page</span><span class="sxs-lookup"><span data-stu-id="fc639-126">Create a header module for a page</span></span>

<span data-ttu-id="fc639-127">Pour créer un module d'en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fc639-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="fc639-128">Créez un fragment nommé **fragment d'en-tête**, puis ajoutez un module de conteneur à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="fc639-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="fc639-129">Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="fc639-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="fc639-130">Ajoutez des modules de bannière promotionnelle et de consentement aux cookies au module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="fc639-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="fc639-131">Ajoutez un autre module de conteneur au fragment puis définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="fc639-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="fc639-132">Ajoutez un module d'en-tête au deuxième module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="fc639-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="fc639-133">Dans l'emplacement **menu de navigation** du module d'en-tête, ajoutez un module de menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="fc639-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="fc639-134">Dans le volet de propriétés du module de menu de navigation, configurez les propriétés du module de menu de navigation.</span><span class="sxs-lookup"><span data-stu-id="fc639-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="fc639-135">Dans l'emplacement **Rechercher** du module d'en-tête, ajoutez un module de recherche.</span><span class="sxs-lookup"><span data-stu-id="fc639-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="fc639-136">Dans le volet de propriétés du module de recherche, configurez les propriétés du module de recherche.</span><span class="sxs-lookup"><span data-stu-id="fc639-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="fc639-137">Enregistrez le fragment de page, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="fc639-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="fc639-138">Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="fc639-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="fc639-139">Dans l'emplacement **Principal** de la page par défaut, ajoutez le fragment de page d'en-tête qui contient le module d'en-tête à l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="fc639-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="fc639-140">Enregistrez le modèle, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="fc639-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc639-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fc639-141">Additional resources</span></span>

[<span data-ttu-id="fc639-142">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="fc639-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="fc639-143">Module Container</span><span class="sxs-lookup"><span data-stu-id="fc639-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="fc639-144">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="fc639-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="fc639-145">Module Panier</span><span class="sxs-lookup"><span data-stu-id="fc639-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="fc639-146">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="fc639-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="fc639-147">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="fc639-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="fc639-148">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="fc639-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="fc639-149">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="fc639-149">Footer module</span></span>](author-footer-module.md)
