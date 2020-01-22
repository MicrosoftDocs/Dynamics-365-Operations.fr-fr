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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885476"
---
# <a name="header-module"></a><span data-ttu-id="bf869-103">Module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="bf869-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="bf869-104">Cette rubrique couvre les modules d'en-tête et décrit leur création dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bf869-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bf869-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="bf869-105">Overview</span></span>

<span data-ttu-id="bf869-106">Un module d'en-tête est un conteneur spécial utilisé pour héberger tous les modules qui s'affichent dans l'en-tête d'une page.</span><span class="sxs-lookup"><span data-stu-id="bf869-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="bf869-107">Par exemple, il peut comprendre votre logo de site, des liens vers la hiérarchie de navigation, des liens vers d'autres pages du site, et la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="bf869-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="bf869-108">Un module d'en-tête est automatiquement optimisé pour l'appareil sur lequel le site est affiché (autrement dit, un périphérique de bureau ou un appareil mobile).</span><span class="sxs-lookup"><span data-stu-id="bf869-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="bf869-109">Par exemple, sur un appareil mobile, la barre de navigation est réduite en un bouton **Menu** (qui est parfois appelé *menu hamburger*).</span><span class="sxs-lookup"><span data-stu-id="bf869-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="bf869-110">Propriétés d'un en-tête</span><span class="sxs-lookup"><span data-stu-id="bf869-110">Properties of a header</span></span>

<span data-ttu-id="bf869-111">Comme les conteneurs génériques, un module d'en-tête prend en charge les propriétés pour l'**en-tête** et la **largeur**.</span><span class="sxs-lookup"><span data-stu-id="bf869-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="bf869-112">Un module d'en-tête a plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="bf869-112">A header module has multiple slots.</span></span> <span data-ttu-id="bf869-113">Par exemple, des emplacements pour un message d'information, un menu de navigation, le logo, une barre de recherche, une icône de panier, une icône de liste de souhaits, et des informations sur le compte.</span><span class="sxs-lookup"><span data-stu-id="bf869-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="bf869-114">Chaque emplacement prend en charge un ensemble spécifique de modules.</span><span class="sxs-lookup"><span data-stu-id="bf869-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="bf869-115">Modules disponibles dans le module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="bf869-115">Modules that are available in a header module</span></span>

<span data-ttu-id="bf869-116">Les modules suivants peuvent être utilisés dans un module d'en-tête :</span><span class="sxs-lookup"><span data-stu-id="bf869-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="bf869-117">**Menu de navigation** – Le menu de navigation représente la hiérarchie de navigation du canal et d'autres liens de navigation statiques.</span><span class="sxs-lookup"><span data-stu-id="bf869-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="bf869-118">La hiérarchie de navigation du canal peut être configurée dans Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="bf869-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="bf869-119">Les articles configurés s'affichent alors comme navigation d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="bf869-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="bf869-120">En outre, les liens de navigation statiques peuvent être configurés, et des liens associés à d'autres pages du site de commerce électronique peuvent être fournis.</span><span class="sxs-lookup"><span data-stu-id="bf869-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="bf869-121">L'en-tête lui-même peut être aligné à gauche, droite, ou centre.</span><span class="sxs-lookup"><span data-stu-id="bf869-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="bf869-122">**Icône de panier** – L'icône du panier est une icône spéciale qui représente le panier.</span><span class="sxs-lookup"><span data-stu-id="bf869-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="bf869-123">Elle s'affiche dans l'en-tête et indique le nombre d'articles dans le panier.</span><span class="sxs-lookup"><span data-stu-id="bf869-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="bf869-124">Un lien vers la page de panier doit accompagner l'icône du panier, de sorte que les clients puissent être redirigés vers la page de panier lorsqu'ils interagissent avec l'icône.</span><span class="sxs-lookup"><span data-stu-id="bf869-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="bf869-125">**Icône de liste de souhaits** – L'icône de liste de souhaits s'affiche dans l'en-tête et indique le nombre d'articles ajoutés à la liste de souhaits du client.</span><span class="sxs-lookup"><span data-stu-id="bf869-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="bf869-126">Un lien vers la page de liste de souhaits doit accompagner cette icône, de sorte que les clients puissent être redirigés vers la page de liste de souhaits lorsqu'ils interagissent avec l'icône.</span><span class="sxs-lookup"><span data-stu-id="bf869-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="bf869-127">**Module de connexion** – Le module de connexion s'affiche dans l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="bf869-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="bf869-128">Il permet aux clients de se connecter à son compte ou de s'inscrire pour un compte.</span><span class="sxs-lookup"><span data-stu-id="bf869-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="bf869-129">Si le client est déjà connecté, le module peut être configuré pour afficher des liens sur la page du compte, la page Historique des commandes, ou une autre page.</span><span class="sxs-lookup"><span data-stu-id="bf869-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="bf869-130">**Module Logo** – Ce module affiche le logo qui représente le détaillant et la marque.</span><span class="sxs-lookup"><span data-stu-id="bf869-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="bf869-131">Il s'agit d'une image avec un lien.</span><span class="sxs-lookup"><span data-stu-id="bf869-131">It's an image that has a link.</span></span> <span data-ttu-id="bf869-132">Le lien est généralement configuré de sorte qu'il redirige vers la page d'accueil, afin que les clients puissent rapidement revenir à la page d'accueil des pages du site.</span><span class="sxs-lookup"><span data-stu-id="bf869-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="bf869-133">**Alerte** – Une alerte s'affiche dans l'en-tête et est utilisée pour afficher un message intégré qui s'applique à toutes les pages du site.</span><span class="sxs-lookup"><span data-stu-id="bf869-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="bf869-134">Par exemple, une alerte peut afficher un message, par exemple « Les soldes annuelles se terminent dans 2 jours ».</span><span class="sxs-lookup"><span data-stu-id="bf869-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="bf869-135">**Barre de recherche** – La barre de recherche permet aux utilisateurs d'entrer des termes de recherche afin de rechercher des produits.</span><span class="sxs-lookup"><span data-stu-id="bf869-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="bf869-136">Le module doit être configuré avec l'URL de la page de résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="bf869-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="bf869-137">Le paramètre de chaîne de requête peut être configuré (la valeur par défaut est **« q »**).</span><span class="sxs-lookup"><span data-stu-id="bf869-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="bf869-138">La barre de recherche a un emplacement de suggestion automatique où le module de suggestion automatique doit être ajouté.</span><span class="sxs-lookup"><span data-stu-id="bf869-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="bf869-139">**Suggestion automatique** – Le module de suggestion automatique affiche des résultats suggérés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bf869-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="bf869-140">Ces résultats peuvent être des mots clés, des produits, ou des catégories si le terme de recherche est trouvé.</span><span class="sxs-lookup"><span data-stu-id="bf869-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="bf869-141">Créer un module d'en-tête</span><span class="sxs-lookup"><span data-stu-id="bf869-141">Create a header module</span></span>

<span data-ttu-id="bf869-142">Pour créer un module d'en-tête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bf869-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="bf869-143">Créez un fragment de page qui inclut un module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="bf869-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="bf869-144">Ajoutez les modules aux emplacements dans le module d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="bf869-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="bf869-145">Mettez à jour les paramètres pour chaque module.</span><span class="sxs-lookup"><span data-stu-id="bf869-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="bf869-146">Enregistrez le fragment de page.</span><span class="sxs-lookup"><span data-stu-id="bf869-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="bf869-147">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="bf869-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="bf869-148">Pour vous assurer qu'un en-tête apparaît sur chaque page, suivez ces étapes pour chaque modèle de page créé pour le site.</span><span class="sxs-lookup"><span data-stu-id="bf869-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="bf869-149">Sur la page par défaut, ajoutez le fragment de page contenant le module d'en-tête à l'en-tête de l'emplacement principal.</span><span class="sxs-lookup"><span data-stu-id="bf869-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="bf869-150">Enregistrez le modèle.</span><span class="sxs-lookup"><span data-stu-id="bf869-150">Save the template.</span></span> 
1. <span data-ttu-id="bf869-151">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="bf869-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf869-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bf869-152">Additional resources</span></span>

[<span data-ttu-id="bf869-153">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="bf869-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bf869-154">Module Container</span><span class="sxs-lookup"><span data-stu-id="bf869-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="bf869-155">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="bf869-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="bf869-156">Module Panier</span><span class="sxs-lookup"><span data-stu-id="bf869-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="bf869-157">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="bf869-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="bf869-158">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="bf869-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="bf869-159">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="bf869-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="bf869-160">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="bf869-160">Footer module</span></span>](author-footer-module.md)
