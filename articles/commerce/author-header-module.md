---
title: Module d’en-tête
description: Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686620"
---
# <a name="header-module"></a><span data-ttu-id="70eb0-103">Module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="70eb0-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="70eb0-104">Cette rubrique couvre les modules d’en-tête et décrit comment créer des en-têtes de page dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="70eb0-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="70eb0-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="70eb0-105">Overview</span></span>

<span data-ttu-id="70eb0-106">Dans Dynamics 365 Commerce, un en-tête de page comprend plusieurs modules, tels que les modules d’en-tête, de menu de navigation, de recherche, de bannière promotionnelle et de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="70eb0-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="70eb0-107">Le module d’en-tête comprend un logo de site, des liens vers la hiérarchie de navigation, des liens vers d’autres pages du site, un symbole de panier, un symbole de liste de souhaits, des options de connexion et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="70eb0-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="70eb0-108">Un module d’en-tête est automatiquement optimisé pour l’appareil sur lequel le site est affiché (autrement dit, pour un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="70eb0-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="70eb0-109">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="70eb0-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="70eb0-110">L’image suivante montre un exemple de module d’en-tête sur une page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="70eb0-110">The following image shows an example of a header module on a home page.</span></span>

![Exemple d’un module d’en-tête](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="70eb0-112">Propriétés d’un module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="70eb0-112">Properties of a header module</span></span>

<span data-ttu-id="70eb0-113">Un module d’en-tête prend en charge les propriétés suivantes : **Image de logo**, **Lien vers le logo** et **Liens de mon compte**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="70eb0-114">Les propriétés **Image de logo** et **Lien vers le logo** sont utilisées pour définir un logo sur la page.</span><span class="sxs-lookup"><span data-stu-id="70eb0-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="70eb0-115">Pour plus d’informations, voir [Ajouter un logo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="70eb0-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="70eb0-116">La propriété **Liens de mon compte** peut être utilisée pour définir les pages de compte pour lesquelles le propriétaire du site souhaite afficher des liens rapides dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="70eb0-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="70eb0-117">Modules disponibles dans le module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="70eb0-117">Modules that are available in a header module</span></span>

<span data-ttu-id="70eb0-118">Les modules suivants peuvent être utilisés dans un module d’en-tête :</span><span class="sxs-lookup"><span data-stu-id="70eb0-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="70eb0-119">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d’autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="70eb0-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="70eb0-120">La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="70eb0-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="70eb0-121">Le menu de navigation a une propriété **Source de navigation** qui est utilisée pour spécifier les éléments de menu statique et les éléments de menu de navigation Serveur de vente au détail comme source.</span><span class="sxs-lookup"><span data-stu-id="70eb0-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="70eb0-122">Si des éléments de menu statique sont spécifiés comme source, des liens relatifs vers d’autres pages du site peuvent être fournis.</span><span class="sxs-lookup"><span data-stu-id="70eb0-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="70eb0-123">Les articles configurés s’affichent alors comme navigation d’en-tête.</span><span class="sxs-lookup"><span data-stu-id="70eb0-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="70eb0-124">**Rechercher** – Le module de recherche permet aux utilisateurs d’entrer des critères de recherche pour des produits.</span><span class="sxs-lookup"><span data-stu-id="70eb0-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="70eb0-125">L’URL de la page de recherche par défaut et les paramètres de la requête de recherche doivent être fournis à l’adresse **Paramètres du site \> Extensions**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="70eb0-126">Le module de recherche possède des propriétés qui vous permettent de supprimer l’étiquette ou le bouton de recherche selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="70eb0-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="70eb0-127">Le module de recherche prend également en charge les options de suggestion automatique, telles que les résultats de recherche de produits, de mots clés et de catégories.</span><span class="sxs-lookup"><span data-stu-id="70eb0-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="70eb0-128">**Icône de panier** - Le module d’icône de panier représente l’icône de panier, qui indique le nombre d’articles dans le panier à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="70eb0-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="70eb0-129">Pour plus d’informations, voir [Module Icône de panier](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="70eb0-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="70eb0-130">Créer un module d’en-tête pour une page</span><span class="sxs-lookup"><span data-stu-id="70eb0-130">Create a header module for a page</span></span>

<span data-ttu-id="70eb0-131">Pour créer un module d’en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="70eb0-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="70eb0-132">Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment.</span><span class="sxs-lookup"><span data-stu-id="70eb0-132">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="70eb0-133">Dans la boîte de dialogue **Nouveau fragment de page**, sélectionnez le module **Conteneur**, entrez un nom pour le fragment de page, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-133">In the **New page fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-134">Sélectionnez l’emplacement **Conteneur par défaut** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="70eb0-135">Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-136">Dans la boîte de dialogue **Ajouter un module**, sélectionnez les modules **Bannière promotionnelle** et **Consentement aux cookies**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-137">Dans l’emplacement **Conteneur par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-138">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-139">Sélectionnez l’emplacement **Conteneur** puis, dans le volet des propriétés de droite, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="70eb0-140">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-141">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **En-tête**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-142">Dans l’emplacement **Menu de navigation** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-143">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Menu de navigation**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-144">Dans le volet de propriétés du module de menu de navigation, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="70eb0-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="70eb0-145">Dans l’emplacement **Recherche** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Recherche**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-147">Dans le volet de propriétés du module de recherche, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="70eb0-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="70eb0-148">Dans l’emplacement **Icône de panier** du module En-tête, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="70eb0-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Icône de panier**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="70eb0-150">Dans le volet de propriétés du module d’icône de panier, configurez les propriétés selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="70eb0-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="70eb0-151">Si vous souhaitez que l’icône de panier affiche un résumé du panier (également connu sous le nom de mini panier) lorsque les utilisateurs la survolent, sélectionnez **Afficher le mini panier**.</span><span class="sxs-lookup"><span data-stu-id="70eb0-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="70eb0-152">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="70eb0-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="70eb0-153">Pour vous assurer qu’un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="70eb0-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="70eb0-154">Dans l’emplacement **En-tête** du module **Page par défaut**, ajoutez le fragment d’en-tête que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="70eb0-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="70eb0-155">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="70eb0-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70eb0-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="70eb0-156">Additional resources</span></span>

[<span data-ttu-id="70eb0-157">Vue d’ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="70eb0-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="70eb0-158">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="70eb0-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="70eb0-159">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="70eb0-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="70eb0-160">Module de panier</span><span class="sxs-lookup"><span data-stu-id="70eb0-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="70eb0-161">Module Icône de panier</span><span class="sxs-lookup"><span data-stu-id="70eb0-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="70eb0-162">Module de validation</span><span class="sxs-lookup"><span data-stu-id="70eb0-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="70eb0-163">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="70eb0-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="70eb0-164">Module d’en-tête</span><span class="sxs-lookup"><span data-stu-id="70eb0-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="70eb0-165">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="70eb0-165">Footer module</span></span>](author-footer-module.md)
