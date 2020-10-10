---
title: Module Carte
description: Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: d2cbc67a186a76647a4f7ddc7942b15d3e469ece
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817204"
---
# <a name="map-module"></a><span data-ttu-id="0961f-103">Module Carte</span><span class="sxs-lookup"><span data-stu-id="0961f-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="0961f-104">Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0961f-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0961f-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="0961f-105">Overview</span></span>

<span data-ttu-id="0961f-106">Un module Carte affiche les emplacements des magasins sur une carte interactive affichée à l’aide du [Contrôle web Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="0961f-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="0961f-107">Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés dans les sièges Commerce.</span><span class="sxs-lookup"><span data-stu-id="0961f-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="0961f-108">Les modules Carte fournissent différentes vues, telles que Route, Aérien et Rue, que les utilisateurs peuvent sélectionner pour afficher des emplacements sur la carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="0961f-109">Ils permettent également des interactions telles que le zoom et l’utilisation de l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0961f-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="0961f-110">Un module Carte fonctionne conjointement avec le module Sélection de magasin pour déterminer les emplacements géographiques des magasins qui doivent être affichés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="0961f-111">Les modules Sélection de magasin et Carte interagissent lorsqu’un utilisateur sélectionne un magasin dans l’un de ces modules sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="0961f-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="0961f-112">Les modules Carte peuvent être étendus pour d’autres scénarios, au-delà de l’interaction avec les modules Sélection de magasin.</span><span class="sxs-lookup"><span data-stu-id="0961f-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="0961f-113">Cependant, la personnalisation du module est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0961f-113">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="0961f-114">Le module Carte est disponible dans Dynamics 365 Commerce version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="0961f-114">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="0961f-115">L’image suivante montre un exemple de module Carte utilisé sur une page d’emplacements de magasin.</span><span class="sxs-lookup"><span data-stu-id="0961f-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exemple d’un module du sélecteur de magasins](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="0961f-117">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="0961f-117">Module properties</span></span>

| <span data-ttu-id="0961f-118">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="0961f-118">Property name</span></span>             | <span data-ttu-id="0961f-119">Valeur </span><span class="sxs-lookup"><span data-stu-id="0961f-119">Value</span></span>                 | <span data-ttu-id="0961f-120">Description </span><span class="sxs-lookup"><span data-stu-id="0961f-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="0961f-121">Titre</span><span class="sxs-lookup"><span data-stu-id="0961f-121">Heading</span></span> | <span data-ttu-id="0961f-122">Détails</span><span class="sxs-lookup"><span data-stu-id="0961f-122">Text</span></span> | <span data-ttu-id="0961f-123">En-tête du module.</span><span class="sxs-lookup"><span data-stu-id="0961f-123">The heading for the module.</span></span> |
| <span data-ttu-id="0961f-124">Options de punaise : icône par défaut</span><span class="sxs-lookup"><span data-stu-id="0961f-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="0961f-125">Image</span><span class="sxs-lookup"><span data-stu-id="0961f-125">Image</span></span> | <span data-ttu-id="0961f-126">Image du symbole de punaise à utiliser pour les magasins affichés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="0961f-127">Options de punaise : icône active</span><span class="sxs-lookup"><span data-stu-id="0961f-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="0961f-128">Image</span><span class="sxs-lookup"><span data-stu-id="0961f-128">Image</span></span> | <span data-ttu-id="0961f-129">Image du symbole de punaise à utiliser pour un magasin sélectionné sur une carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="0961f-130">Options de punaise : couleur de l’icône par défaut</span><span class="sxs-lookup"><span data-stu-id="0961f-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="0961f-131">Chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="0961f-131">Character string</span></span> | <span data-ttu-id="0961f-132">Valeur texte ou hexadécimale de la couleur des symboles de punaise sur une carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="0961f-133">Options de punaise : couleur de l’icône active</span><span class="sxs-lookup"><span data-stu-id="0961f-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="0961f-134">Chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="0961f-134">Character string</span></span> | <span data-ttu-id="0961f-135">Valeur texte ou hexadécimale de la couleur des symboles de punaise sélectionnés sur une carte.</span><span class="sxs-lookup"><span data-stu-id="0961f-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="0961f-136">Afficher l’index</span><span class="sxs-lookup"><span data-stu-id="0961f-136">Show index</span></span> | <span data-ttu-id="0961f-137">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="0961f-137">**True** or **False**</span></span> | <span data-ttu-id="0961f-138">Si cette propriété est définie sur **Vrai**, chaque symbole de punaise indiquant un magasin affiche un index.</span><span class="sxs-lookup"><span data-stu-id="0961f-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="0961f-139">Cet index correspond à l’index dans la vue de liste affichée par le module Sélection de magasin.</span><span class="sxs-lookup"><span data-stu-id="0961f-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="0961f-140">Ajouter des URL de mappage autorisées aux instructions de la stratégie de sécurité du contenu d’un site</span><span class="sxs-lookup"><span data-stu-id="0961f-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="0961f-141">Pour que le module Carte interagisse avec Bing Maps, vous devez vous assurer que les URL de mappage suivantes sont autorisées (également appelées « URL sur liste verte ») conformément à la stratégie de sécurité du contenu (CSP) de votre site.</span><span class="sxs-lookup"><span data-stu-id="0961f-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="0961f-142">Ce paramétrage est effectué dans le générateur de site Commerce, en ajoutant des URL autorisées à différentes instructions CSP du site (par exemple, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="0961f-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="0961f-143">Pour plus d’informations, voir [Stratégie de sécurité du contenu](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="0961f-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="0961f-144">À la directive **connect-src**, ajoutez **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="0961f-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="0961f-145">À la directive **img-src**, ajoutez **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="0961f-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="0961f-146">Dans l’instruction **script-src**, ajoutez **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="0961f-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="0961f-147">Dans l’instruction **script style-src**, ajoutez **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="0961f-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="0961f-148">Ajouter un module Carte à une page</span><span class="sxs-lookup"><span data-stu-id="0961f-148">Add a map module to a page</span></span>

<span data-ttu-id="0961f-149">Pour des informations détaillées sur la configuration d’un module Carte sur une page, voir [Module Sélection de magasin](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="0961f-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="0961f-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0961f-150">Additional resources</span></span>

[<span data-ttu-id="0961f-151">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="0961f-151">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0961f-152">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="0961f-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0961f-153">Module Panier</span><span class="sxs-lookup"><span data-stu-id="0961f-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0961f-154">Module Sélection de magasin</span><span class="sxs-lookup"><span data-stu-id="0961f-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="0961f-155">Gérer Bing Cartes pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="0961f-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="0961f-156">Contrôle web Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="0961f-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
