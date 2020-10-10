---
title: Module d’en-tête
description: Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99457b2c98eae0ddd898f852630d690140a5a4c5
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817008"
---
# <a name="header-module"></a><span data-ttu-id="fb77e-103">Module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="fb77e-103">Header module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="fb77e-104">Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fb77e-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fb77e-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="fb77e-105">Overview</span></span>

<span data-ttu-id="fb77e-106">Dans Dynamics 365 Commerce, un en-tête de page est configuré comme un fragment de page qui comprend l’en-tête, la bannière promotionnelle et les modules de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="fb77e-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="fb77e-107">Le module d’en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d’autres pages du site, un module d’icone de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="fb77e-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="fb77e-108">Un module d’en-tête est automatiquement optimisé pour l’appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="fb77e-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="fb77e-109">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="fb77e-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="fb77e-110">L’image suivante montre un exemple de module d’en-tête sur une page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="fb77e-110">The following image shows an example of a header module on a home page.</span></span>

![Exemple d’un module d’en-tête](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="fb77e-112">Propriétés d’un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="fb77e-112">Properties of a header module</span></span>

<span data-ttu-id="fb77e-113">Un module d’en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="fb77e-114">Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page.</span><span class="sxs-lookup"><span data-stu-id="fb77e-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="fb77e-115">Pour plus d’informations, voir [Ajouter un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="fb77e-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="fb77e-116">La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="fb77e-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="fb77e-117">Modules disponibles dans un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="fb77e-117">Modules that are available within a header module</span></span>

<span data-ttu-id="fb77e-118">Les modules suivants peuvent être utilisés dans un module d’en-tête :</span><span class="sxs-lookup"><span data-stu-id="fb77e-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="fb77e-119">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d’autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="fb77e-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="fb77e-120">Pour plus d’informations, voir [Module Menu de navigation](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="fb77e-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="fb77e-121">**Rechercher** – Le module de recherche permet aux utilisateurs d’entrer des critères de recherche pour des produits.</span><span class="sxs-lookup"><span data-stu-id="fb77e-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="fb77e-122">L’URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l’adresse **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="fb77e-123">Le module de recherche possède des propriétés qui vous permettent de supprimer l’étiquette ou le bouton de recherche selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fb77e-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="fb77e-124">Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.</span><span class="sxs-lookup"><span data-stu-id="fb77e-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="fb77e-125">**Icône de panier** - Le module d’icône de panier représente l’icône de panier, qui indique le nombre d’articles dans le panier à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="fb77e-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="fb77e-126">Pour plus d’informations, voir [Module Icône de panier](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="fb77e-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="fb77e-127">Créer un fragment d’en-tête pour une page</span><span class="sxs-lookup"><span data-stu-id="fb77e-127">Create a header fragment for a page</span></span>

<span data-ttu-id="fb77e-128">Pour créer un fragment d’en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fb77e-128">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="fb77e-129">Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="fb77e-129">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="fb77e-130">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-130">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-131">Sélectionnez l’emplacement **Conteneur par défaut** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir l’écran**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-131">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="fb77e-132">Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-132">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fb77e-133">Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Consentement aux cookies**, **En-tête** et **Bannière promotionnelle**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-133">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-134">Dans le volet des propriétés du module **Bannière promotionnelle**, sélectionnez **Ajouter un message**, puis sélectionnez **Message**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-134">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="fb77e-135">Dans la boîte de dialogue **Message**, ajoutez du texte et des liens pour le contenu promotionnel, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-135">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-136">Dans le volet des propriétés du module **Consentement aux cookies**, ajoutez et configurez du texte et un lien vers la page de confidentialité du site.</span><span class="sxs-lookup"><span data-stu-id="fb77e-136">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="fb77e-137">Dans l’emplacement **Menu de navigation** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-137">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fb77e-138">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Menu de navigation**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-138">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-139">Dans le volet des propriétés du module du menu de navigation, sous **Source du menu de navigation**, sélectionnez **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-139">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="fb77e-140">Dans le volet des propriétés du module du menu de navigation, sous **Éléments de menu statiques**, sélectionnez **Ajouter un élément de menu**, puis sélectionnez **Élément du menu**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-140">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="fb77e-141">Dans la boîte de dialogue **Élément du menu**, sous **Texte de l’élément de menu**, entrez « Contact ».</span><span class="sxs-lookup"><span data-stu-id="fb77e-141">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="fb77e-142">Dans la boîte de dialogue **Élément du menu**, sous **Cible du lien d’élément de menu**, sélectionnez **Ajouter un lien**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-142">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="fb77e-143">Dans la boîte de dialogue **Ajouter un lien**, sélectionnez l’URL de la page « Contact » du site, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-143">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="fb77e-144">Dans la boîte de dialogue **Élément du menu**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-144">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="fb77e-145">Dans l’emplacement **Recherche** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fb77e-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Recherche**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-147">Dans le volet de propriétés du module de recherche, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fb77e-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="fb77e-148">Dans l’emplacement **Icône de panier** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fb77e-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Icône de panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="fb77e-150">Dans le volet de propriétés du module d’icône de panier, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fb77e-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="fb77e-151">Si vous souhaitez que l’icône de panier affiche un résumé du panier (également connu sous le nom de mini panier) lorsque les utilisateurs la survolent, sélectionnez **Afficher le mini panier**.</span><span class="sxs-lookup"><span data-stu-id="fb77e-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="fb77e-152">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="fb77e-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="fb77e-153">Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="fb77e-153">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="fb77e-154">Dans l’emplacement **En-tête** du module **Page par défaut**, ajoutez le fragment d’en-tête que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="fb77e-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="fb77e-155">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="fb77e-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb77e-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fb77e-156">Additional resources</span></span>

[<span data-ttu-id="fb77e-157">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="fb77e-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="fb77e-158">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="fb77e-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="fb77e-159">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="fb77e-159">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="fb77e-160">Module Bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="fb77e-160">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="fb77e-161">Module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="fb77e-161">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="fb77e-162">Consentement du cookie</span><span class="sxs-lookup"><span data-stu-id="fb77e-162">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="fb77e-163">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="fb77e-163">Footer module</span></span>](author-footer-module.md)
