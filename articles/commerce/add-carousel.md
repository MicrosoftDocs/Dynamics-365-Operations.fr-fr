---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025779"
---
# <a name="carousel-module"></a><span data-ttu-id="7d692-103">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="7d692-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7d692-104">Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d692-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7d692-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="7d692-105">Overview</span></span>

<span data-ttu-id="7d692-106">Un module Carrousel sert à mettre des plusieurs articles publicitaires (dont des images enrichies) dans une bannière de carrousel tournante à laquelle les clients peuvent accéder.</span><span class="sxs-lookup"><span data-stu-id="7d692-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="7d692-107">Par exemple, un détaillant peut utiliser un module Carrousel sur une page d'accueil pour présenter plusieurs nouveaux produits ou promotions.</span><span class="sxs-lookup"><span data-stu-id="7d692-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="7d692-108">Vous pouvez ajouter des modules de bloc de contenu dans un module carrousel.</span><span class="sxs-lookup"><span data-stu-id="7d692-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="7d692-109">Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.</span><span class="sxs-lookup"><span data-stu-id="7d692-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="7d692-110">Exemples de modules Carrousel dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="7d692-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="7d692-111">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="7d692-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="7d692-112">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="7d692-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="7d692-113">Un carrousel peut être utilisé sur n'importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.</span><span class="sxs-lookup"><span data-stu-id="7d692-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="7d692-114">Propriétés du module Carrousel</span><span class="sxs-lookup"><span data-stu-id="7d692-114">Carousel module properties</span></span>

| <span data-ttu-id="7d692-115">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="7d692-115">Property name</span></span>             | <span data-ttu-id="7d692-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="7d692-116">Value</span></span>                 | <span data-ttu-id="7d692-117">Description</span><span class="sxs-lookup"><span data-stu-id="7d692-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="7d692-118">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="7d692-118">Autoplay</span></span>                  | <span data-ttu-id="7d692-119">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="7d692-119">**True** or **False**</span></span> | <span data-ttu-id="7d692-120">Si la valeur est définie sur **Vrai**, la transition entre les articles à l'intérieur du carrousel survient automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7d692-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="7d692-121">Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d'un article à l'autre.</span><span class="sxs-lookup"><span data-stu-id="7d692-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="7d692-122">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="7d692-122">Slide transition interval</span></span> | <span data-ttu-id="7d692-123">Valeur en secondes</span><span class="sxs-lookup"><span data-stu-id="7d692-123">A value in seconds</span></span>    | <span data-ttu-id="7d692-124">Intervalle des transitions entre les articles.</span><span class="sxs-lookup"><span data-stu-id="7d692-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="7d692-125">Type de transition</span><span class="sxs-lookup"><span data-stu-id="7d692-125">Transition type</span></span>           | <span data-ttu-id="7d692-126">**Diapositive** ou **Fondu**</span><span class="sxs-lookup"><span data-stu-id="7d692-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="7d692-127">L'effet de transition entre les articles.</span><span class="sxs-lookup"><span data-stu-id="7d692-127">The transition effect between items.</span></span> |
| <span data-ttu-id="7d692-128">Masquer le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="7d692-128">Hide carousel flipper</span></span>     | <span data-ttu-id="7d692-129">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="7d692-129">**True** or **False**</span></span> | <span data-ttu-id="7d692-130">Si la valeur est définie sur **Vrai**, le flipper du carrousel et l'indicateur de séquence sont masqués.</span><span class="sxs-lookup"><span data-stu-id="7d692-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="7d692-131">Autoriser le rejet du carrousel</span><span class="sxs-lookup"><span data-stu-id="7d692-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="7d692-132">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="7d692-132">**True** or **False**</span></span> | <span data-ttu-id="7d692-133">Si la valeur est définie sur **Vrai**, les utilisateurs peuvent ignorer le caroussel.</span><span class="sxs-lookup"><span data-stu-id="7d692-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="7d692-134">Ajouter un module de carrousel à une page</span><span class="sxs-lookup"><span data-stu-id="7d692-134">Add a carousel module to a page</span></span>

<span data-ttu-id="7d692-135">Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7d692-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="7d692-136">Créez un modèle de page nommé **modèle de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="7d692-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="7d692-137">Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="7d692-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="7d692-138">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="7d692-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="7d692-139">Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s'appelle **page de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="7d692-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="7d692-140">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="7d692-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="7d692-141">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir l'écran**.</span><span class="sxs-lookup"><span data-stu-id="7d692-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="7d692-142">Dans **Contour de la page**, ajoutez un module carrousel au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="7d692-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="7d692-143">Ajouter un module de bloc de contenu au module caroussel.</span><span class="sxs-lookup"><span data-stu-id="7d692-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="7d692-144">Définissez les propriétés du module de bloc de contenu en fournissant **En-tête**, **Lien**, **Disposition**et d'autres propriétés.</span><span class="sxs-lookup"><span data-stu-id="7d692-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="7d692-145">Ajoutez et configurez un autre module de bloc de contenu.</span><span class="sxs-lookup"><span data-stu-id="7d692-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="7d692-146">Définissez des propriétés supplémentaires pour le module carrousel selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="7d692-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="7d692-147">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="7d692-147">Save and preview the page.</span></span> <span data-ttu-id="7d692-148">La page doit afficher un carrousel avec deux modules à l'intérieur (un module de bannière et un module de fonctionnalité).</span><span class="sxs-lookup"><span data-stu-id="7d692-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="7d692-149">Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l'effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="7d692-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="7d692-150">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="7d692-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d692-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7d692-151">Additional resources</span></span>

[<span data-ttu-id="7d692-152">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="7d692-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7d692-153">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="7d692-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="7d692-154">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="7d692-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="7d692-155">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="7d692-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="7d692-156">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="7d692-156">Video player module</span></span>](add-video-player.md)
