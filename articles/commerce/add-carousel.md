---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785235"
---
# <a name="carousel-module"></a><span data-ttu-id="4f1c7-103">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="4f1c7-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4f1c7-104">Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4f1c7-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="4f1c7-105">Overview</span></span>

<span data-ttu-id="4f1c7-106">Un module Carrousel sert à mettre des plusieurs articles publicitaires dans un carrousel auquel les clients peuvent accéder.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="4f1c7-107">Il s'agit d'un module spécial de conteneur qui héberge d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="4f1c7-108">Par exemple, un détaillant peut utiliser un module Carrousel sur une page d'accueil pour présenter plusieurs nouveaux produits ou promotions.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="4f1c7-109">Vous pouvez ajouter des modules Bannière et Fonctionnalités dans un module Carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="4f1c7-110">Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="4f1c7-111">Exemples de modules Carrousel dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="4f1c7-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="4f1c7-112">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="4f1c7-113">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="4f1c7-114">Un carrousel peut être utilisé sur n'importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="4f1c7-115">Propriétés du module Carrousel</span><span class="sxs-lookup"><span data-stu-id="4f1c7-115">Carousel module properties</span></span>

| <span data-ttu-id="4f1c7-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="4f1c7-116">Property name</span></span>             | <span data-ttu-id="4f1c7-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="4f1c7-117">Value</span></span>                                | <span data-ttu-id="4f1c7-118">Description</span><span class="sxs-lookup"><span data-stu-id="4f1c7-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="4f1c7-119">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="4f1c7-119">Autoplay</span></span>                  | <span data-ttu-id="4f1c7-120">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="4f1c7-120">**True** or **False**</span></span>                | <span data-ttu-id="4f1c7-121">Si la valeur est définie sur **Vrai**, la transition entre les articles à l'intérieur du carrousel survient automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="4f1c7-122">Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d'un article à l'autre.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="4f1c7-123">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="4f1c7-123">Slide transition interval</span></span> | <span data-ttu-id="4f1c7-124">Valeur en secondes</span><span class="sxs-lookup"><span data-stu-id="4f1c7-124">A value in seconds</span></span>                   | <span data-ttu-id="4f1c7-125">Intervalle des transitions entre les articles.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="4f1c7-126">Animation de la transition</span><span class="sxs-lookup"><span data-stu-id="4f1c7-126">Transition animation</span></span>      | <span data-ttu-id="4f1c7-127">**Diapositive** ou **Fondu**</span><span class="sxs-lookup"><span data-stu-id="4f1c7-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="4f1c7-128">Effet de transition.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-128">The transition effect.</span></span> |
| <span data-ttu-id="4f1c7-129">Largeur</span><span class="sxs-lookup"><span data-stu-id="4f1c7-129">Width</span></span>                     | <span data-ttu-id="4f1c7-130">**Adapter le conteneur** ou **Remplir l'écran**</span><span class="sxs-lookup"><span data-stu-id="4f1c7-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="4f1c7-131">Si la valeur est définie sur **Adapter le conteneur**, les articles à l'intérieur du carrousel sont limités à la largeur du carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="4f1c7-132">Si la valeur est définie **Plein écran**, les articles ne sont pas soumis à la largeur du carrousel mais peuvent entrer dans le mode pleine page.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="4f1c7-133">Vous pouvez modifier la valeur pour obtenir la disposition appropriée.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="4f1c7-134">Ajouter un module de carrousel à une page</span><span class="sxs-lookup"><span data-stu-id="4f1c7-134">Add a carousel module to a page</span></span>

<span data-ttu-id="4f1c7-135">Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="4f1c7-136">Créez un modèle de page nommé **modèle de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="4f1c7-137">À l'emplacement **Principal** de la page par défaut, ajoutez un module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="4f1c7-138">Ajoutez un module de bannière au module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="4f1c7-139">Ajoutez un module de fonctionnalité au module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="4f1c7-140">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="4f1c7-141">Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s'appelle **page de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="4f1c7-142">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="4f1c7-143">Définissez la propriété **Largeur** du module de carrousel sur **Plein écran**.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="4f1c7-144">Définissez la propriété **Animation de transition** sur **Diapositive**.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="4f1c7-145">Ajoutez un module de bannière au module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="4f1c7-146">Dans le module de bannière, ajoutez une image et un en-tête, puis sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="4f1c7-147">Ajoutez un module de fonctionnalité au module de carrousel.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="4f1c7-148">Dans le module de fonctionnalité, ajoutez une image, un en-tête, et un paragraphe de texte.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="4f1c7-149">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-149">Save and preview the page.</span></span> <span data-ttu-id="4f1c7-150">La page doit afficher un carrousel avec deux modules à l'intérieur (un module de bannière et un module de fonctionnalité).</span><span class="sxs-lookup"><span data-stu-id="4f1c7-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="4f1c7-151">Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l'effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="4f1c7-152">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="4f1c7-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f1c7-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="4f1c7-153">Additional resources</span></span>

[<span data-ttu-id="4f1c7-154">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="4f1c7-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4f1c7-155">Module Alerte</span><span class="sxs-lookup"><span data-stu-id="4f1c7-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="4f1c7-156">Module de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="4f1c7-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="4f1c7-157">Module Placement de contenu</span><span class="sxs-lookup"><span data-stu-id="4f1c7-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="4f1c7-158">Module Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="4f1c7-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="4f1c7-159">Module Bannière</span><span class="sxs-lookup"><span data-stu-id="4f1c7-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="4f1c7-160">Module Lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="4f1c7-160">Video player module</span></span>](add-video-player.md)
