---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: f399e4c5618b65b781fdd3ec835e841614579313
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269726"
---
# <a name="carousel-module"></a><span data-ttu-id="14906-103">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="14906-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="14906-104">Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="14906-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="14906-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="14906-105">Overview</span></span>

<span data-ttu-id="14906-106">Un module Carrousel sert à mettre des plusieurs articles publicitaires (dont des images enrichies) dans une bannière de carrousel tournante à laquelle les clients peuvent accéder.</span><span class="sxs-lookup"><span data-stu-id="14906-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="14906-107">Par exemple, un détaillant peut utiliser un module Carrousel sur une page d'accueil pour présenter plusieurs nouveaux produits ou promotions.</span><span class="sxs-lookup"><span data-stu-id="14906-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="14906-108">Vous pouvez ajouter des modules de bloc de contenu dans un module carrousel.</span><span class="sxs-lookup"><span data-stu-id="14906-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="14906-109">Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.</span><span class="sxs-lookup"><span data-stu-id="14906-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="14906-110">Exemples de modules Carrousel dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="14906-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="14906-111">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="14906-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="14906-112">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="14906-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="14906-113">Un carrousel peut être utilisé sur n'importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.</span><span class="sxs-lookup"><span data-stu-id="14906-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="14906-114">Propriétés du module Carrousel</span><span class="sxs-lookup"><span data-stu-id="14906-114">Carousel module properties</span></span>

| <span data-ttu-id="14906-115">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="14906-115">Property name</span></span>             | <span data-ttu-id="14906-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="14906-116">Value</span></span>                 | <span data-ttu-id="14906-117">Description</span><span class="sxs-lookup"><span data-stu-id="14906-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="14906-118">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="14906-118">Autoplay</span></span>                  | <span data-ttu-id="14906-119">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="14906-119">**True** or **False**</span></span> | <span data-ttu-id="14906-120">Si la valeur est définie sur **Vrai**, la transition entre les articles à l'intérieur du carrousel survient automatiquement.</span><span class="sxs-lookup"><span data-stu-id="14906-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="14906-121">Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d'un article à l'autre.</span><span class="sxs-lookup"><span data-stu-id="14906-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="14906-122">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="14906-122">Slide transition interval</span></span> | <span data-ttu-id="14906-123">Valeur en secondes</span><span class="sxs-lookup"><span data-stu-id="14906-123">A value in seconds</span></span>    | <span data-ttu-id="14906-124">Intervalle des transitions entre les articles.</span><span class="sxs-lookup"><span data-stu-id="14906-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="14906-125">Type de transition</span><span class="sxs-lookup"><span data-stu-id="14906-125">Transition type</span></span>           | <span data-ttu-id="14906-126">**Diapositive** ou **Fondu**</span><span class="sxs-lookup"><span data-stu-id="14906-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="14906-127">L'effet de transition entre les articles.</span><span class="sxs-lookup"><span data-stu-id="14906-127">The transition effect between items.</span></span> |
| <span data-ttu-id="14906-128">Masquer le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="14906-128">Hide carousel flipper</span></span>     | <span data-ttu-id="14906-129">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="14906-129">**True** or **False**</span></span> | <span data-ttu-id="14906-130">Si la valeur est définie sur **Vrai**, le flipper du carrousel et l'indicateur de séquence sont masqués.</span><span class="sxs-lookup"><span data-stu-id="14906-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="14906-131">Autoriser le rejet du carrousel</span><span class="sxs-lookup"><span data-stu-id="14906-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="14906-132">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="14906-132">**True** or **False**</span></span> | <span data-ttu-id="14906-133">Si la valeur est définie sur **Vrai**, les utilisateurs peuvent ignorer le caroussel.</span><span class="sxs-lookup"><span data-stu-id="14906-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="14906-134">Ajouter un module de carrousel à une page</span><span class="sxs-lookup"><span data-stu-id="14906-134">Add a carousel module to a page</span></span>

<span data-ttu-id="14906-135">Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="14906-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="14906-136">Sélectionnez **Nouveau** pour créer un modèle de page.</span><span class="sxs-lookup"><span data-stu-id="14906-136">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="14906-137">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de carrousel**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="14906-137">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="14906-138">Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="14906-138">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="14906-139">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="14906-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="14906-140">Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s'appelle **Page de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="14906-140">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="14906-141">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="14906-141">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="14906-142">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir l'écran**.</span><span class="sxs-lookup"><span data-stu-id="14906-142">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="14906-143">Dans **Contour de la page**, ajoutez un module carrousel au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="14906-143">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="14906-144">Ajouter un module de bloc de contenu au module caroussel.</span><span class="sxs-lookup"><span data-stu-id="14906-144">Add a content block module to the carousel module.</span></span> <span data-ttu-id="14906-145">Définissez les propriétés du module de bloc de contenu en fournissant **En-tête**, **Lien**, **Disposition**et d'autres propriétés.</span><span class="sxs-lookup"><span data-stu-id="14906-145">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="14906-146">Ajoutez et configurez un autre module de bloc de contenu.</span><span class="sxs-lookup"><span data-stu-id="14906-146">Add and configure another content block module.</span></span>
1. <span data-ttu-id="14906-147">Définissez des propriétés supplémentaires pour le module carrousel selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="14906-147">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="14906-148">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="14906-148">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="14906-149">La page doit afficher un carrousel avec deux modules à l'intérieur (un module de bannière et un module de fonctionnalité).</span><span class="sxs-lookup"><span data-stu-id="14906-149">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="14906-150">Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l'effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="14906-150">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="14906-151">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="14906-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="14906-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="14906-152">Additional resources</span></span>

[<span data-ttu-id="14906-153">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="14906-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="14906-154">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="14906-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="14906-155">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="14906-155">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="14906-156">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="14906-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="14906-157">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="14906-157">Video player module</span></span>](add-video-player.md)
