---
title: Module du sélecteur de magasins
description: Cette rubrique couvre le module du sélecteur de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157338"
---
# <a name="store-selector-module"></a><span data-ttu-id="dd500-103">Module du sélecteur de magasins</span><span class="sxs-lookup"><span data-stu-id="dd500-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd500-104">Cette rubrique couvre le module du sélecteur de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dd500-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dd500-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="dd500-105">Overview</span></span>

<span data-ttu-id="dd500-106">Un module du sélecteur de magasins est utilisé pour le scénario client « Acheter en ligne, retirer en magasin » (BOPIS).</span><span class="sxs-lookup"><span data-stu-id="dd500-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="dd500-107">Il affiche une liste des magasins où un produit est disponible pour retrait, ainsi que les heures d'ouverture et l'inventaire des produits pour chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="dd500-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="dd500-108">Le module du sélecteur de magasins nécessite le contexte d'un produit et un emplacement de recherche pour trouver des magasins.</span><span class="sxs-lookup"><span data-stu-id="dd500-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="dd500-109">En l'absence d'un emplacement de recherche, il s'agit par défaut de l'emplacement du navigateur du client, à condition que le client donne son consentement.</span><span class="sxs-lookup"><span data-stu-id="dd500-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="dd500-110">Le module a une boîte de saisie qui permet au client d'entrer un emplacement (code postal, ou ville et état) pour trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="dd500-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="dd500-111">Le module du sélecteur de magasins est intégré avec l'interface de programmation d'application (API) de géocodage Bing Cartes pour convertir l'emplacement en une latitude et une longitude.</span><span class="sxs-lookup"><span data-stu-id="dd500-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="dd500-112">Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés Commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dd500-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dd500-113">Le module du sélecteur de magasins peut être ajouté à un module de zone d'achat sur la page de détails du produit (PDP) pour afficher les magasins où un produit est disponible pour retrait.</span><span class="sxs-lookup"><span data-stu-id="dd500-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="dd500-114">Il peut également être ajouté à un module de panier.</span><span class="sxs-lookup"><span data-stu-id="dd500-114">It can also be added to a cart module.</span></span> <span data-ttu-id="dd500-115">Lorsqu'il est ajouté à un module de panier, le module du sélecteur de magasins affiche les options de retrait pour chaque élément de ligne de panier.</span><span class="sxs-lookup"><span data-stu-id="dd500-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="dd500-116">De plus, avec un codage personnalisé, ce module peut être ajouté à d'autres pages ou modules via des extensions et des personnalisations.</span><span class="sxs-lookup"><span data-stu-id="dd500-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="dd500-117">Pour que le scénario BOPIS fonctionne, les produits doivent être configurés avec le mode de livraison « retrait client ».</span><span class="sxs-lookup"><span data-stu-id="dd500-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="dd500-118">Sinon, le module ne sera pas affiché sur les pages respectives.</span><span class="sxs-lookup"><span data-stu-id="dd500-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="dd500-119">Pour plus d'informations sur la configuration du mode de livraison, consultez [Configurer les modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="dd500-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="dd500-120">L'image suivante montre un exemple de module du sélecteur de magasins utilisé sur un PDP.</span><span class="sxs-lookup"><span data-stu-id="dd500-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Exemple d'un module du sélecteur de magasins](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="dd500-122">Utilisation du module de sélecteur de magasins dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="dd500-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="dd500-123">Un module de sélecteur de magasins peut être utilisé sur une page de détails du produit (PDP) pour trouver les magasins à proximité où un produit est disponible pour retrait.</span><span class="sxs-lookup"><span data-stu-id="dd500-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="dd500-124">Un module de sélecteur de magasins peut être utilisé sur une page de panier pour trouver les magasins à proximité où un produit dans le panier est disponible pour retrait.</span><span class="sxs-lookup"><span data-stu-id="dd500-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="dd500-125">Propriétés du module de sélecteur de magasins</span><span class="sxs-lookup"><span data-stu-id="dd500-125">Store selector module properties</span></span>

| <span data-ttu-id="dd500-126">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="dd500-126">Property name</span></span>             | <span data-ttu-id="dd500-127">Valeur </span><span class="sxs-lookup"><span data-stu-id="dd500-127">Value</span></span>                 | <span data-ttu-id="dd500-128">Description </span><span class="sxs-lookup"><span data-stu-id="dd500-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="dd500-129">Rayon de recherche</span><span class="sxs-lookup"><span data-stu-id="dd500-129">Search radius</span></span> | <span data-ttu-id="dd500-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="dd500-130">Number</span></span> | <span data-ttu-id="dd500-131">Définit le rayon de recherche des magasins, en kilomètres.</span><span class="sxs-lookup"><span data-stu-id="dd500-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="dd500-132">Si aucune valeur n'est spécifiée, le rayon de recherche par défaut, 50 kilomètres, est utilisé.</span><span class="sxs-lookup"><span data-stu-id="dd500-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="dd500-133">Conditions d'utilisation du service</span><span class="sxs-lookup"><span data-stu-id="dd500-133">Terms of Service</span></span> | <span data-ttu-id="dd500-134">URL</span><span class="sxs-lookup"><span data-stu-id="dd500-134">URL</span></span>    |  <span data-ttu-id="dd500-135">L'URL des conditions de service est requis pour le service Bing Cartes.</span><span class="sxs-lookup"><span data-stu-id="dd500-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="dd500-136">Ajouter un module de sélecteur de magasins à une page</span><span class="sxs-lookup"><span data-stu-id="dd500-136">Add a store selector module to a page</span></span>

<span data-ttu-id="dd500-137">Un module de sélecteur de magasins a besoin du contexte d'un produit, il ne peut donc être utilisé que dans les modules de zone d'achat et de panier.</span><span class="sxs-lookup"><span data-stu-id="dd500-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="dd500-138">Les modules de sélecteur de magasins ne fonctionnent pas en dehors de ces modules.</span><span class="sxs-lookup"><span data-stu-id="dd500-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="dd500-139">Pour plus d'informations sur l'ajout d'un module de sélecteur de magasins à un module de zone d'achat, consultez [Module de zone d'achat](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="dd500-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="dd500-140">Pour plus d'informations sur l'ajout d'un module de sélecteur de magasins à un module de panier, consultez [Module de panier](add-cart-module.md).</span><span class="sxs-lookup"><span data-stu-id="dd500-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd500-141">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dd500-141">Additional resources</span></span>

[<span data-ttu-id="dd500-142">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="dd500-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dd500-143">Module de zone d'achat</span><span class="sxs-lookup"><span data-stu-id="dd500-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="dd500-144">Module de chariot</span><span class="sxs-lookup"><span data-stu-id="dd500-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="dd500-145">Visite rapide de PDP</span><span class="sxs-lookup"><span data-stu-id="dd500-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="dd500-146">Visite rapide du panier et du paiement</span><span class="sxs-lookup"><span data-stu-id="dd500-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="dd500-147">Paramétrer des modes de livraison</span><span class="sxs-lookup"><span data-stu-id="dd500-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
