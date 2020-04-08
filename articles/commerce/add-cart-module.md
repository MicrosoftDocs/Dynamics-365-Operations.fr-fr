---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154015"
---
# <a name="cart-module"></a><span data-ttu-id="ea277-103">Module Panier</span><span class="sxs-lookup"><span data-stu-id="ea277-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ea277-104">Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ea277-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ea277-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="ea277-105">Overview</span></span>

<span data-ttu-id="ea277-106">Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse.</span><span class="sxs-lookup"><span data-stu-id="ea277-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ea277-107">Le module montre également un résumé de la commande et permet au client d'appliquer ou de supprimer des codes promotionnels.</span><span class="sxs-lookup"><span data-stu-id="ea277-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ea277-108">Le module de panier prend en charge la caisse connectée et la caisse d'invité.</span><span class="sxs-lookup"><span data-stu-id="ea277-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ea277-109">Il prend également en charge un lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="ea277-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ea277-110">Vous pouvez configurer l'itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.</span><span class="sxs-lookup"><span data-stu-id="ea277-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ea277-111">Le module de panier affiche les données selon l'ID du panier, qui est un cookie de navigateur disponible sur tout le site.</span><span class="sxs-lookup"><span data-stu-id="ea277-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ea277-112">Propriétés et emplacements du module de panier</span><span class="sxs-lookup"><span data-stu-id="ea277-112">Cart module properties and slots</span></span>

<span data-ttu-id="ea277-113">Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d'achat** et **Articles dans votre panier**.</span><span class="sxs-lookup"><span data-stu-id="ea277-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ea277-114">Modules qui peuvent être utilisés dans un module de panier</span><span class="sxs-lookup"><span data-stu-id="ea277-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ea277-115">**Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier.</span><span class="sxs-lookup"><span data-stu-id="ea277-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ea277-116">Les messages sont pilotés par le système de gestion de contenu (CMS).</span><span class="sxs-lookup"><span data-stu-id="ea277-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ea277-117">Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».</span><span class="sxs-lookup"><span data-stu-id="ea277-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ea277-118">**Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ea277-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ea277-119">Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité.</span><span class="sxs-lookup"><span data-stu-id="ea277-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ea277-120">Pour plus d'informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ea277-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="ea277-121">Paramètres du module de panier</span><span class="sxs-lookup"><span data-stu-id="ea277-121">Cart module settings</span></span>

<span data-ttu-id="ea277-122">Les modules de panier ont les paramètres suivants qui peuvent être configurés sur **Paramètres du site \> Extensions** :</span><span class="sxs-lookup"><span data-stu-id="ea277-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ea277-123">**Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier.</span><span class="sxs-lookup"><span data-stu-id="ea277-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ea277-124">Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.</span><span class="sxs-lookup"><span data-stu-id="ea277-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ea277-125">**Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock.</span><span class="sxs-lookup"><span data-stu-id="ea277-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="ea277-126">Ce contrôle de stock est réalisé en cas d'expédition de l'article ou en cas de prélévement de l'article au magasin.</span><span class="sxs-lookup"><span data-stu-id="ea277-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="ea277-127">Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.</span><span class="sxs-lookup"><span data-stu-id="ea277-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="ea277-128">**Tampon quantité disponible** - Cette propriété est utilisée pour spécifier un numéro de tampon pour le stock.</span><span class="sxs-lookup"><span data-stu-id="ea277-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="ea277-129">Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact.</span><span class="sxs-lookup"><span data-stu-id="ea277-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="ea277-130">Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé.</span><span class="sxs-lookup"><span data-stu-id="ea277-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="ea277-131">Par conséquent, lorsque des ventes se produisent rapidement sur plusieurs canaux, et que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.</span><span class="sxs-lookup"><span data-stu-id="ea277-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="ea277-132">**Revenir aux achats** - Cette propriété est utilisée pour spécifier l'itinéraire pour le lien **Revenir aux achats**.</span><span class="sxs-lookup"><span data-stu-id="ea277-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ea277-133">L'itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d'accueil ou vers toute autre page du site.</span><span class="sxs-lookup"><span data-stu-id="ea277-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ea277-134">Interaction avec l'unité d'échelle commerciale</span><span class="sxs-lookup"><span data-stu-id="ea277-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ea277-135">Le module de panier extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="ea277-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ea277-136">L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l'unité d'échelle commerciale.</span><span class="sxs-lookup"><span data-stu-id="ea277-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ea277-137">Ajouter un module de panier à une page</span><span class="sxs-lookup"><span data-stu-id="ea277-137">Add a cart module to a page</span></span>

<span data-ttu-id="ea277-138">Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ea277-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ea277-139">Créez un fragment nommé **Fragment de panier**, puis ajoutez un module de panier au nouveau fragment.</span><span class="sxs-lookup"><span data-stu-id="ea277-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="ea277-140">Ajoutez un en-tête au module de panier.</span><span class="sxs-lookup"><span data-stu-id="ea277-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="ea277-141">Ajoutez un module de sélecteur de magasins au module de panier.</span><span class="sxs-lookup"><span data-stu-id="ea277-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="ea277-142">Enregistrez le fragment, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="ea277-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="ea277-143">Créez un modèle **Modèle de panier**, puis ajoutez le fragment de panier que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="ea277-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="ea277-144">Enregistrez le modèle, terminez de le modifier et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="ea277-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="ea277-145">Créez une page qui utilise le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="ea277-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="ea277-146">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="ea277-146">Save and preview the page.</span></span>
1. <span data-ttu-id="ea277-147">Terminez de modifier la page, puis publiez-la.</span><span class="sxs-lookup"><span data-stu-id="ea277-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ea277-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ea277-148">Additional resources</span></span>

[<span data-ttu-id="ea277-149">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="ea277-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ea277-150">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="ea277-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ea277-151">Module du sélecteur de magasins</span><span class="sxs-lookup"><span data-stu-id="ea277-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="ea277-152">Module de zone d'achat</span><span class="sxs-lookup"><span data-stu-id="ea277-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ea277-153">Module de validation</span><span class="sxs-lookup"><span data-stu-id="ea277-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ea277-154">Module de confirmation de commande</span><span class="sxs-lookup"><span data-stu-id="ea277-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ea277-155">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="ea277-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ea277-156">Module Pied de page</span><span class="sxs-lookup"><span data-stu-id="ea277-156">Footer module</span></span>](author-footer-module.md)
