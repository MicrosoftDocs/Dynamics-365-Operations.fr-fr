---
title: Module d’en-tête
description: Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 569fb5ac3d30be30044ef9b928ecf1f6dde20aab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211422"
---
# <a name="header-module"></a><span data-ttu-id="b4e15-103">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="b4e15-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b4e15-104">Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b4e15-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b4e15-105">Dans Dynamics 365 Commerce, un en-tête de page est configuré comme un fragment de page qui comprend l’en-tête, la bannière promotionnelle et les modules de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="b4e15-105">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="b4e15-106">Le module d’en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d’autres pages du site, un module d’icone de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="b4e15-106">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="b4e15-107">Un module d’en-tête est automatiquement optimisé pour l’appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="b4e15-107">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="b4e15-108">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="b4e15-108">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="b4e15-109">L’image suivante montre un exemple de module d’en-tête sur une page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="b4e15-109">The following image shows an example of a header module on a home page.</span></span>

![Exemple d’un module d’en-tête](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="b4e15-111">Propriétés d’un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="b4e15-111">Properties of a header module</span></span>

<span data-ttu-id="b4e15-112">Un module d’en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-112">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="b4e15-113">Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page.</span><span class="sxs-lookup"><span data-stu-id="b4e15-113">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="b4e15-114">Pour plus d’informations, voir [Ajouter un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="b4e15-114">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="b4e15-115">La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="b4e15-115">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="b4e15-116">Modules disponibles dans un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="b4e15-116">Modules that are available within a header module</span></span>

<span data-ttu-id="b4e15-117">Les modules suivants peuvent être utilisés dans un module d’en-tête :</span><span class="sxs-lookup"><span data-stu-id="b4e15-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="b4e15-118">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d’autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="b4e15-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="b4e15-119">Pour plus d’informations, voir [Module Menu de navigation](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="b4e15-119">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="b4e15-120">**Rechercher** – Le module de recherche permet aux utilisateurs d’entrer des critères de recherche pour des produits.</span><span class="sxs-lookup"><span data-stu-id="b4e15-120">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="b4e15-121">L’URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l’adresse **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-121">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="b4e15-122">Le module de recherche possède des propriétés qui vous permettent de supprimer l’étiquette ou le bouton de recherche selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b4e15-122">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="b4e15-123">Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.</span><span class="sxs-lookup"><span data-stu-id="b4e15-123">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="b4e15-124">**Icône de panier** - Le module d’icône de panier représente l’icône de panier, qui indique le nombre d’articles dans le panier à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="b4e15-124">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="b4e15-125">Pour plus d’informations, voir [Module Icône de panier](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="b4e15-125">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="b4e15-126">**Sélecteur de site** - Le module de sélecteur de site permet aux utilisateurs de parcourir différents sites prédéfinis, en fonction du marché, des régions et des paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="b4e15-126">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="b4e15-127">Pour plus d’informations, voir [Module Sélecteur de site](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="b4e15-127">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="b4e15-128">**Sélecteur de magasin** - Le module de sélecteur de magasin peut être inclus dans l'emplacement de sélecteur de magasin d'un module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="b4e15-128">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="b4e15-129">Il permet aux utilisateurs de parcourir et de trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="b4e15-129">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="b4e15-130">Les utilisateurs peuvent également spécifier un magasin préféré.</span><span class="sxs-lookup"><span data-stu-id="b4e15-130">Users can also specify a preferred store.</span></span> <span data-ttu-id="b4e15-131">Ce magasin sera alors affiché dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="b4e15-131">That store will then be shown in the header.</span></span> <span data-ttu-id="b4e15-132">Lorsque le module de sélecteur de magasin est inclus dans le module d'en-tête, sa propriété **Mode** doit être définie sur **Rechercher des magasins**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-132">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="b4e15-133">Pour plus d’informations, voir [Module Sélecteur de magasin](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="b4e15-133">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="b4e15-134">La prise en charge de l'utilisation du module d'icônes de panier dans les modules d'en-tête est disponible dans Dynamics 365 Commerce Version 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="b4e15-134">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="b4e15-135">La prise en charge de l'utilisation du module de sélecteur de site dans les modules d'en-tête est disponible dans Dynamics 365 Commerce Version 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="b4e15-135">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="b4e15-136">La prise en charge de l'utilisation du module de sélecteur de magasin dans les modules d'en-tête est disponible dans Dynamics 365 Commerce Version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="b4e15-136">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="b4e15-137">Créer un fragment d’en-tête pour une page</span><span class="sxs-lookup"><span data-stu-id="b4e15-137">Create a header fragment for a page</span></span>

<span data-ttu-id="b4e15-138">Pour créer un fragment d’en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b4e15-138">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="b4e15-139">Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="b4e15-139">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="b4e15-140">Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-140">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-141">Sélectionnez l’emplacement **Conteneur par défaut** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir l’écran**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-141">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="b4e15-142">Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-142">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b4e15-143">Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Consentement aux cookies**, **En-tête** et **Bannière promotionnelle**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-143">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-144">Dans le volet des propriétés du module **Bannière promotionnelle**, sélectionnez **Ajouter un message**, puis sélectionnez **Message**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-144">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="b4e15-145">Dans la boîte de dialogue **Message**, ajoutez du texte et des liens pour le contenu promotionnel, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-145">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-146">Dans le volet des propriétés du module **Consentement aux cookies**, ajoutez et configurez du texte et un lien vers la page de confidentialité du site.</span><span class="sxs-lookup"><span data-stu-id="b4e15-146">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="b4e15-147">Dans l’emplacement **Menu de navigation** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-147">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b4e15-148">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Menu de navigation**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-148">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-149">Dans le volet des propriétés du module du menu de navigation, sous **Source du menu de navigation**, sélectionnez **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-149">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="b4e15-150">Dans le volet des propriétés du module du menu de navigation, sous **Éléments de menu statiques**, sélectionnez **Ajouter un élément de menu**, puis sélectionnez **Élément du menu**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-150">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="b4e15-151">Dans la boîte de dialogue **Élément du menu**, sous **Texte de l’élément de menu**, entrez « Contact ».</span><span class="sxs-lookup"><span data-stu-id="b4e15-151">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="b4e15-152">Dans la boîte de dialogue **Élément du menu**, sous **Cible du lien d’élément de menu**, sélectionnez **Ajouter un lien**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-152">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="b4e15-153">Dans la boîte de dialogue **Ajouter un lien**, sélectionnez l’URL de la page « Contact » du site, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-153">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="b4e15-154">Dans la boîte de dialogue **Élément du menu**, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-154">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="b4e15-155">Dans l’emplacement **Recherche** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-155">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b4e15-156">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Recherche**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-156">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-157">Dans le volet de propriétés du module de recherche, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b4e15-157">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="b4e15-158">Dans l’emplacement **Icône de panier** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-158">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b4e15-159">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Icône de panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-159">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b4e15-160">Dans le volet de propriétés du module d’icône de panier, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b4e15-160">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="b4e15-161">Si vous souhaitez que l’icône de panier affiche un résumé du panier (également connu sous le nom de mini panier) lorsque les utilisateurs la survolent, sélectionnez **Afficher le mini panier**.</span><span class="sxs-lookup"><span data-stu-id="b4e15-161">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="b4e15-162">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="b4e15-162">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="b4e15-163">Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="b4e15-163">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="b4e15-164">Dans l’emplacement **En-tête** du module **Page par défaut**, ajoutez le fragment d’en-tête que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="b4e15-164">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="b4e15-165">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="b4e15-165">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4e15-166">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b4e15-166">Additional resources</span></span>

[<span data-ttu-id="b4e15-167">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="b4e15-167">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b4e15-168">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="b4e15-168">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b4e15-169">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="b4e15-169">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="b4e15-170">Module Bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="b4e15-170">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="b4e15-171">Module Menu de navigation</span><span class="sxs-lookup"><span data-stu-id="b4e15-171">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="b4e15-172">Consentement du cookie</span><span class="sxs-lookup"><span data-stu-id="b4e15-172">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="b4e15-173">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="b4e15-173">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="b4e15-174">Module de sélecteur de site</span><span class="sxs-lookup"><span data-stu-id="b4e15-174">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="b4e15-175">Module Sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="b4e15-175">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]