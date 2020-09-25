---
title: Module Carte
description: Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ca531e6cbf0a1044b0a13e5cdf42c7b4f0498fe5
ms.sourcegitcommit: 629988f1a704d62648d98649056931b8c33b9e08
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3811182"
---
# <a name="map-module"></a><span data-ttu-id="a5f3d-103">Module Carte</span><span class="sxs-lookup"><span data-stu-id="a5f3d-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="a5f3d-104">Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a5f3d-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="a5f3d-105">Overview</span></span>

<span data-ttu-id="a5f3d-106">Un module Carte affiche les emplacements des magasins sur une carte interactive affichée à l’aide du [Contrôle web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="a5f3d-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="a5f3d-107">Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés dans les sièges Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="a5f3d-108">Les modules Carte fournissent différentes vues, telles que Route, Aérien et Rue, que les utilisateurs peuvent sélectionner pour afficher des emplacements sur la carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="a5f3d-109">Ils permettent également des interactions telles que le zoom et l’utilisation de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="a5f3d-110">Un module Carte fonctionne conjointement avec le module Sélection de magasin pour déterminer les emplacements géographiques des magasins qui doivent être affichés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="a5f3d-111">Les modules Sélection de magasin et Carte interagissent lorsqu’un utilisateur sélectionne un magasin dans l’un de ces modules sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="a5f3d-112">Les modules Carte peuvent être étendus pour d’autres scénarios, au-delà de l’interaction avec les modules Sélection de magasin.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="a5f3d-113">Cependant, la personnalisation du module est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-113">However, module customization is required.</span></span>

<span data-ttu-id="a5f3d-114">Le module Carte a été introduit dans la version 10.0.13 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="a5f3d-115">L’image suivante montre un exemple de module Carte utilisé sur une page d’emplacements de magasin.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exemple d’un module du sélecteur de magasins](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="a5f3d-117">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="a5f3d-117">Module properties</span></span>

| <span data-ttu-id="a5f3d-118">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="a5f3d-118">Property name</span></span>             | <span data-ttu-id="a5f3d-119">Valeur </span><span class="sxs-lookup"><span data-stu-id="a5f3d-119">Value</span></span>                 | <span data-ttu-id="a5f3d-120">Description </span><span class="sxs-lookup"><span data-stu-id="a5f3d-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="a5f3d-121">Titre</span><span class="sxs-lookup"><span data-stu-id="a5f3d-121">Heading</span></span> | <span data-ttu-id="a5f3d-122">Détails</span><span class="sxs-lookup"><span data-stu-id="a5f3d-122">Text</span></span> | <span data-ttu-id="a5f3d-123">En-tête du module.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-123">The heading for the module.</span></span> |
| <span data-ttu-id="a5f3d-124">Options de punaise : icône par défaut</span><span class="sxs-lookup"><span data-stu-id="a5f3d-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="a5f3d-125">Image</span><span class="sxs-lookup"><span data-stu-id="a5f3d-125">Image</span></span> | <span data-ttu-id="a5f3d-126">Image du symbole de punaise à utiliser pour les magasins affichés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="a5f3d-127">Options de punaise : icône active</span><span class="sxs-lookup"><span data-stu-id="a5f3d-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="a5f3d-128">Image</span><span class="sxs-lookup"><span data-stu-id="a5f3d-128">Image</span></span> | <span data-ttu-id="a5f3d-129">Image du symbole de punaise à utiliser pour un magasin sélectionné sur une carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="a5f3d-130">Options de punaise : couleur de l’icône par défaut</span><span class="sxs-lookup"><span data-stu-id="a5f3d-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="a5f3d-131">Chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="a5f3d-131">Character string</span></span> | <span data-ttu-id="a5f3d-132">Valeur texte ou hexadécimale de la couleur des symboles de punaise sur une carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="a5f3d-133">Options de punaise : couleur de l’icône active</span><span class="sxs-lookup"><span data-stu-id="a5f3d-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="a5f3d-134">Chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="a5f3d-134">Character string</span></span> | <span data-ttu-id="a5f3d-135">Valeur texte ou hexadécimale de la couleur des symboles de punaise sélectionnés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="a5f3d-136">Afficher l’index</span><span class="sxs-lookup"><span data-stu-id="a5f3d-136">Show index</span></span> | <span data-ttu-id="a5f3d-137">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="a5f3d-137">**True** or **False**</span></span> | <span data-ttu-id="a5f3d-138">Si cette propriété est définie sur **Vrai**, chaque symbole de punaise indiquant un magasin affiche un index.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="a5f3d-139">Cet index correspond à l’index dans la vue de liste affichée par le module Sélection de magasin.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="a5f3d-140">Ajouter des URL de mappage autorisées aux instructions de la stratégie de sécurité du contenu d’un site</span><span class="sxs-lookup"><span data-stu-id="a5f3d-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="a5f3d-141">Pour que le module Carte interagisse avec Bing Maps, vous devez vous assurer que les URL de mappage suivantes sont autorisées (également appelées « URL sur liste verte ») conformément à la stratégie de sécurité du contenu (CSP) de votre site.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="a5f3d-142">Ce paramétrage est effectué dans le générateur de site Commerce, en ajoutant des URL autorisées à différentes instructions CSP du site (par exemple, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="a5f3d-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="a5f3d-143">Pour plus d’informations, voir [Stratégie de sécurité du contenu](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="a5f3d-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="a5f3d-144">À la directive **connect-src**, ajoutez **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="a5f3d-145">À la directive **img-src**, ajoutez **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="a5f3d-146">Dans l’instruction **script-src**, ajoutez **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="a5f3d-147">Dans l’instruction **script style-src**, ajoutez **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="a5f3d-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="a5f3d-148">Ajouter un module Carte à une page</span><span class="sxs-lookup"><span data-stu-id="a5f3d-148">Add a map module to a page</span></span>

<span data-ttu-id="a5f3d-149">Pour des informations détaillées sur la configuration d’un module Carte sur une page, voir [Module Sélection de magasin](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="a5f3d-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="a5f3d-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a5f3d-150">Additional resources</span></span>

[<span data-ttu-id="a5f3d-151">Vue d’ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="a5f3d-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a5f3d-152">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="a5f3d-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="a5f3d-153">Module de panier</span><span class="sxs-lookup"><span data-stu-id="a5f3d-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a5f3d-154">Module de sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="a5f3d-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="a5f3d-155">Gérer les Bing Cartes pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="a5f3d-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="a5f3d-156">Contrôle web Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="a5f3d-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
