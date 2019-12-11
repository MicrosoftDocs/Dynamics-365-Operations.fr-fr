---
title: Module En-tête
description: Cette rubrique couvre les modules d'en-tête et décrit leur création dans Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697273"
---
# <a name="header-module"></a><span data-ttu-id="9d343-103">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="9d343-103">Header module</span></span>

<span data-ttu-id="9d343-104">[!include [banner](../includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="9d343-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="9d343-105">Cette rubrique couvre les modules d'en-tête et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d343-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9d343-106">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="9d343-106">Overview</span></span>

<span data-ttu-id="9d343-107">Un module d'en-tête est un conteneur spécial utilisé pour héberger tous les modules qui s'affichent dans l'en-tête d'une page.</span><span class="sxs-lookup"><span data-stu-id="9d343-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="9d343-108">Par exemple, il peut comprendre votre logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="9d343-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="9d343-109">Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="9d343-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="9d343-110">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="9d343-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="9d343-111">Propriétés d'un en-tête</span><span class="sxs-lookup"><span data-stu-id="9d343-111">Properties of a header</span></span>

<span data-ttu-id="9d343-112">Comme les conteneurs génériques, un module d'en-tête prend en charge les propriétés pour l'**en-tête** et la **largeur**.</span><span class="sxs-lookup"><span data-stu-id="9d343-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="9d343-113">Un module d'en-tête a plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="9d343-113">A header module has multiple slots.</span></span> <span data-ttu-id="9d343-114">Par exemple, des emplacements pour un message d'information, un menu de navigation, le logo, une barre de recherche, une icône de panier, une icône de liste de souhaits, et des informations sur le compte.</span><span class="sxs-lookup"><span data-stu-id="9d343-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="9d343-115">Chaque emplacement prend en charge un ensemble spécifique de modules.</span><span class="sxs-lookup"><span data-stu-id="9d343-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="9d343-116">Modules disponibles dans le module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="9d343-116">Modules that are available in a header module</span></span>

<span data-ttu-id="9d343-117">Les modules suivants peuvent être utilisés dans un module d'en-tête :</span><span class="sxs-lookup"><span data-stu-id="9d343-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="9d343-118">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="9d343-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="9d343-119">La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="9d343-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="9d343-120">Les articles configurés s'affichent alors comme navigation d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="9d343-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="9d343-121">En outre, les liens de navigation statiques peuvent être configurés, et des liens associés à d'autres pages du site de commerce électronique peuvent être fournis.</span><span class="sxs-lookup"><span data-stu-id="9d343-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="9d343-122">L'en-tête lui-même peut être aligné à gauche, droite, ou centre.</span><span class="sxs-lookup"><span data-stu-id="9d343-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="9d343-123">**Icône de panier** – L'icône du panier est une icône spéciale qui représente le panier.</span><span class="sxs-lookup"><span data-stu-id="9d343-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="9d343-124">Elle s'affiche dans l'en-tête et indique le nombre d'articles dans le panier.</span><span class="sxs-lookup"><span data-stu-id="9d343-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="9d343-125">Un lien vers la page de panier doit accompagner l'icône du panier, de sorte que les clients puissent être redirigés vers la page de panier lorsqu'ils interagissent avec l'icône.</span><span class="sxs-lookup"><span data-stu-id="9d343-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="9d343-126">**Icône de liste de souhaits** – L'icône de liste de souhaits s'affiche dans l'en-tête et indique le nombre d'articles ajoutés à la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="9d343-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="9d343-127">Un lien vers la page de liste de souhaits doit accompagner cette icône, de sorte que les clients puissent être redirigés vers la page de liste de souhaits lorsqu'ils interagissent avec l'icône.</span><span class="sxs-lookup"><span data-stu-id="9d343-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="9d343-128">**Module de connexion** – Le module de connexion s'affiche dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="9d343-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="9d343-129">Il permet aux clients de se connecter à son compte ou de s'inscrire pour un compte.</span><span class="sxs-lookup"><span data-stu-id="9d343-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="9d343-130">Si le client est déjà connecté, le module peut être configuré pour afficher des liens sur la page du compte, la page Historique des commandes, ou une autre page.</span><span class="sxs-lookup"><span data-stu-id="9d343-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="9d343-131">**Module Logo** – Ce module affiche le logo qui représente le détaillant et la marque.</span><span class="sxs-lookup"><span data-stu-id="9d343-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="9d343-132">Il s'agit d'une image avec un lien.</span><span class="sxs-lookup"><span data-stu-id="9d343-132">It's an image that has a link.</span></span> <span data-ttu-id="9d343-133">Le lien est généralement configuré de sorte qu'il redirige vers la page d'accueil, afin que les clients puissent rapidement revenir à la page d'accueil des pages du site.</span><span class="sxs-lookup"><span data-stu-id="9d343-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="9d343-134">**Alerte** – Une alerte s'affiche dans l'en-tête et est utilisée pour afficher un message intégré qui s'applique à toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="9d343-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="9d343-135">Par exemple, une alerte peut afficher un message, par exemple « Les soldes annuelles se terminent dans 2 jours ».</span><span class="sxs-lookup"><span data-stu-id="9d343-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="9d343-136">**Barre de recherche** – La barre de recherche permet aux utilisateurs d'entrer des termes de recherche afin de rechercher des produits.</span><span class="sxs-lookup"><span data-stu-id="9d343-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="9d343-137">Le module doit être configuré avec l'URL de la page de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="9d343-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="9d343-138">Le paramètre de chaîne de requête peut être configuré (la valeur par défaut est **« q »**).</span><span class="sxs-lookup"><span data-stu-id="9d343-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="9d343-139">La barre de recherche a un emplacement de suggestion automatique où le module de suggestion automatique doit être ajouté.</span><span class="sxs-lookup"><span data-stu-id="9d343-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="9d343-140">**Suggestion automatique** – Le module de suggestion automatique affiche des résultats suggérés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="9d343-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="9d343-141">Ces résultats peuvent être des mots clés, des produits, ou des catégories si le terme de recherche est trouvé.</span><span class="sxs-lookup"><span data-stu-id="9d343-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="9d343-142">Créer un module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="9d343-142">Create a header module</span></span>

<span data-ttu-id="9d343-143">Pour créer un module d'en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d343-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="9d343-144">Créez un fragment de page qui inclut un module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="9d343-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="9d343-145">Ajoutez les modules aux emplacements dans le module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="9d343-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="9d343-146">Mettez à jour les paramètres pour chaque module.</span><span class="sxs-lookup"><span data-stu-id="9d343-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="9d343-147">Enregistrez le fragment de page.</span><span class="sxs-lookup"><span data-stu-id="9d343-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="9d343-148">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="9d343-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="9d343-149">Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="9d343-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="9d343-150">Sur la page par défaut, ajoutez le fragment de page contenant le module d'en-tête à l'en-tête de l'emplacement principal.</span><span class="sxs-lookup"><span data-stu-id="9d343-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="9d343-151">Enregistrez le modèle.</span><span class="sxs-lookup"><span data-stu-id="9d343-151">Save the template.</span></span> 
1. <span data-ttu-id="9d343-152">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="9d343-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d343-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9d343-153">Additional resources</span></span>

[<span data-ttu-id="9d343-154">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="9d343-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9d343-155">Module Container</span><span class="sxs-lookup"><span data-stu-id="9d343-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="9d343-156">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="9d343-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9d343-157">Module Panier</span><span class="sxs-lookup"><span data-stu-id="9d343-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="9d343-158">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="9d343-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="9d343-159">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="9d343-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="9d343-160">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="9d343-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="9d343-161">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="9d343-161">Footer module</span></span>](author-footer-module.md)
