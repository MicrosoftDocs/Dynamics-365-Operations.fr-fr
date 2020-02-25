---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025434"
---
# <a name="cart-module"></a><span data-ttu-id="3e55d-103">Module Panier</span><span class="sxs-lookup"><span data-stu-id="3e55d-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3e55d-104">Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e55d-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e55d-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="3e55d-105">Overview</span></span>

<span data-ttu-id="3e55d-106">Un module de panier est utilisé pour afficher les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse.</span><span class="sxs-lookup"><span data-stu-id="3e55d-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="3e55d-107">Par exemple, il inclut tous les articles qui ont été ajoutés au panier et une synthèse de commande.</span><span class="sxs-lookup"><span data-stu-id="3e55d-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="3e55d-108">Il permet également au client d'appliquer ou de supprimer des codes promotionnels.</span><span class="sxs-lookup"><span data-stu-id="3e55d-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="3e55d-109">Le module de panier prend en charge la caisse connectée et la caisse d'invité.</span><span class="sxs-lookup"><span data-stu-id="3e55d-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="3e55d-110">Il prend également en charge un lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="3e55d-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="3e55d-111">Vous pouvez configurer l'itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.</span><span class="sxs-lookup"><span data-stu-id="3e55d-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="3e55d-112">Le module de panier affiche des données sur l'ID panier.</span><span class="sxs-lookup"><span data-stu-id="3e55d-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="3e55d-113">L'ID panier est un cookie du navigateur dans le site.</span><span class="sxs-lookup"><span data-stu-id="3e55d-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="3e55d-114">Propriétés et emplacements du module de panier</span><span class="sxs-lookup"><span data-stu-id="3e55d-114">Cart module properties and slots</span></span>

<span data-ttu-id="3e55d-115">Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d'achat** et **Articles dans votre panier**.</span><span class="sxs-lookup"><span data-stu-id="3e55d-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="3e55d-116">Modules qui peuvent être utilisés dans un module de panier</span><span class="sxs-lookup"><span data-stu-id="3e55d-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="3e55d-117">**Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier.</span><span class="sxs-lookup"><span data-stu-id="3e55d-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="3e55d-118">Les messages sont pilotés par le système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="3e55d-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="3e55d-119">Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».</span><span class="sxs-lookup"><span data-stu-id="3e55d-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="3e55d-120">**Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="3e55d-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="3e55d-121">Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="3e55d-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="3e55d-122">Le module du sélecteur de magasins est intégré avec l'interface de programmation d'application (API) de géocodage Bing Cartes pour convertir l'emplacement en une latitude et une longitude.</span><span class="sxs-lookup"><span data-stu-id="3e55d-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="3e55d-123">Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés Vente au détail dans Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="3e55d-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="3e55d-124">Ce module prend en charge deux propriétés : **Rayon de recherche** et **Lien vers les conditions d'utilisation**.</span><span class="sxs-lookup"><span data-stu-id="3e55d-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="3e55d-125">La propriété **Rayon de recherche** définit le rayon de recherche des magasins, en miles.</span><span class="sxs-lookup"><span data-stu-id="3e55d-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="3e55d-126">Si aucune valeur n'est spécifiée, le rayon de recherche par défaut, 50 miles, est utilisé.</span><span class="sxs-lookup"><span data-stu-id="3e55d-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="3e55d-127">Si Bings Cartes ou tout autre service externe est utilisé, la propriété **Lien vers les conditions d'utilisation** peut être utilisée pour fournir un lien vers les conditions d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="3e55d-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="3e55d-128">Un lien vers les conditions d'utilisation est requis pour le service Bing Cartes.</span><span class="sxs-lookup"><span data-stu-id="3e55d-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="3e55d-129">Paramètres du module de panier</span><span class="sxs-lookup"><span data-stu-id="3e55d-129">Cart module settings</span></span>

<span data-ttu-id="3e55d-130">Les modules de panier ont les paramètres suivants qui peuvent être configurés sur **Paramètres du site \> Extensions** :</span><span class="sxs-lookup"><span data-stu-id="3e55d-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="3e55d-131">**Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier.</span><span class="sxs-lookup"><span data-stu-id="3e55d-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="3e55d-132">Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="3e55d-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="3e55d-133">**Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock.</span><span class="sxs-lookup"><span data-stu-id="3e55d-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="3e55d-134">Ce contrôle de stock est réalisé pour les cas où l'article sera expédié et pour les cas où il sera prélevé en magasin.</span><span class="sxs-lookup"><span data-stu-id="3e55d-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="3e55d-135">Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.</span><span class="sxs-lookup"><span data-stu-id="3e55d-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="3e55d-136">**Tampon quantité disponible** - Cette propriété est utilisée pour spécifier un numéro de tampon pour le stock.</span><span class="sxs-lookup"><span data-stu-id="3e55d-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="3e55d-137">Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact.</span><span class="sxs-lookup"><span data-stu-id="3e55d-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="3e55d-138">Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé.</span><span class="sxs-lookup"><span data-stu-id="3e55d-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="3e55d-139">Par conséquent, lorsque des ventes se produisent rapidement sur plusieurs canaux, et que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.</span><span class="sxs-lookup"><span data-stu-id="3e55d-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="3e55d-140">**Revenir aux achats** - Cette propriété est utilisée pour spécifier l'itinéraire pour le lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="3e55d-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="3e55d-141">Cet itinéraire peut être configuré au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="3e55d-141">This route can be configured at the site level.</span></span> <span data-ttu-id="3e55d-142">Cette configuration permet aux détaillants de ramener le client à la page d'accueil ou à toute autre page du site.</span><span class="sxs-lookup"><span data-stu-id="3e55d-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="3e55d-143">Interaction avec l'unité d'échelle commerciale</span><span class="sxs-lookup"><span data-stu-id="3e55d-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="3e55d-144">Le module de panier extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="3e55d-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="3e55d-145">L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l'unité d'échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="3e55d-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="3e55d-146">Ajouter un module de panier à une page</span><span class="sxs-lookup"><span data-stu-id="3e55d-146">Add a cart module to a page</span></span>

<span data-ttu-id="3e55d-147">Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3e55d-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3e55d-148">Créez un fragment nommé **Fragment de panier**, puis ajoutez un module de panier à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="3e55d-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="3e55d-149">Ajoutez un en-tête au module de panier.</span><span class="sxs-lookup"><span data-stu-id="3e55d-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="3e55d-150">Ajoutez un module de sélecteur de magasins au module de panier.</span><span class="sxs-lookup"><span data-stu-id="3e55d-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="3e55d-151">Enregistrez le fragment, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="3e55d-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="3e55d-152">Créez un modèle **Modèle de panier**, puis ajoutez le fragment de panier que vous venez de créer à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="3e55d-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="3e55d-153">Enregistrez le modèle, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="3e55d-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="3e55d-154">Créez une page qui utilise le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="3e55d-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="3e55d-155">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="3e55d-155">Save and preview the page.</span></span>
1. <span data-ttu-id="3e55d-156">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="3e55d-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e55d-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3e55d-157">Additional resources</span></span>

[<span data-ttu-id="3e55d-158">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="3e55d-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3e55d-159">Module Container</span><span class="sxs-lookup"><span data-stu-id="3e55d-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3e55d-160">Module Zone d'achat</span><span class="sxs-lookup"><span data-stu-id="3e55d-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="3e55d-161">Module Paiement</span><span class="sxs-lookup"><span data-stu-id="3e55d-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3e55d-162">Module Confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="3e55d-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="3e55d-163">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="3e55d-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="3e55d-164">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="3e55d-164">Footer module</span></span>](author-footer-module.md)
