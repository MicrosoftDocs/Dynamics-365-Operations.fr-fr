---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f09f3f98d174f965a75e27ee6a5c2ed8599042fc
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3816984"
---
# <a name="carousel-module"></a><span data-ttu-id="05032-103">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="05032-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="05032-104">Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="05032-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="05032-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="05032-105">Overview</span></span>

<span data-ttu-id="05032-106">Un module Carrousel sert à mettre des plusieurs articles publicitaires (dont des images enrichies) dans une bannière de carrousel tournante à laquelle les clients peuvent accéder.</span><span class="sxs-lookup"><span data-stu-id="05032-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="05032-107">Par exemple, un détaillant peut utiliser un module Carrousel sur une page d’accueil pour présenter plusieurs nouveaux produits ou promotions.</span><span class="sxs-lookup"><span data-stu-id="05032-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="05032-108">Vous pouvez ajouter des modules de bloc de contenu dans un module carrousel.</span><span class="sxs-lookup"><span data-stu-id="05032-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="05032-109">Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.</span><span class="sxs-lookup"><span data-stu-id="05032-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="05032-110">Exemples de modules Carrousel dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="05032-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="05032-111">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="05032-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="05032-112">Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.</span><span class="sxs-lookup"><span data-stu-id="05032-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="05032-113">Un carrousel peut être utilisé sur n’importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.</span><span class="sxs-lookup"><span data-stu-id="05032-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="05032-114">L’image suivante montre un exemple de module de carrousel utilisé sur une page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="05032-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="05032-115">Ce module de carrousel contient plusieurs éléments de bloc de contenu.</span><span class="sxs-lookup"><span data-stu-id="05032-115">This carousel module contains multiple content block items.</span></span>

![Exemple d’un module de carrousel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="05032-117">Propriétés du module Carrousel</span><span class="sxs-lookup"><span data-stu-id="05032-117">Carousel module properties</span></span>

| <span data-ttu-id="05032-118">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="05032-118">Property name</span></span>             | <span data-ttu-id="05032-119">Valeur</span><span class="sxs-lookup"><span data-stu-id="05032-119">Value</span></span>                 | <span data-ttu-id="05032-120">Description</span><span class="sxs-lookup"><span data-stu-id="05032-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="05032-121">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="05032-121">Autoplay</span></span>                  | <span data-ttu-id="05032-122">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="05032-122">**True** or **False**</span></span> | <span data-ttu-id="05032-123">Si la valeur est définie sur **Vrai**, la transition entre les articles à l’intérieur du carrousel survient automatiquement.</span><span class="sxs-lookup"><span data-stu-id="05032-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="05032-124">Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d’un article à l’autre.</span><span class="sxs-lookup"><span data-stu-id="05032-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="05032-125">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="05032-125">Slide transition interval</span></span> | <span data-ttu-id="05032-126">Valeur en secondes</span><span class="sxs-lookup"><span data-stu-id="05032-126">A value in seconds</span></span>    | <span data-ttu-id="05032-127">Intervalle des transitions entre les articles.</span><span class="sxs-lookup"><span data-stu-id="05032-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="05032-128">Type de transition</span><span class="sxs-lookup"><span data-stu-id="05032-128">Transition type</span></span>           | <span data-ttu-id="05032-129">**Diapositive** ou **Fondu**</span><span class="sxs-lookup"><span data-stu-id="05032-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="05032-130">L’effet de transition entre les articles.</span><span class="sxs-lookup"><span data-stu-id="05032-130">The transition effect between items.</span></span> |
| <span data-ttu-id="05032-131">Masquer le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="05032-131">Hide carousel flipper</span></span>     | <span data-ttu-id="05032-132">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="05032-132">**True** or **False**</span></span> | <span data-ttu-id="05032-133">Si la valeur est définie sur **Vrai**, le flipper du carrousel et l’indicateur de séquence sont masqués.</span><span class="sxs-lookup"><span data-stu-id="05032-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="05032-134">Autoriser le rejet du carrousel</span><span class="sxs-lookup"><span data-stu-id="05032-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="05032-135">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="05032-135">**True** or **False**</span></span> | <span data-ttu-id="05032-136">Si la valeur est définie sur **Vrai**, les utilisateurs peuvent ignorer le caroussel.</span><span class="sxs-lookup"><span data-stu-id="05032-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="05032-137">Ajouter un module de carrousel à une page</span><span class="sxs-lookup"><span data-stu-id="05032-137">Add a carousel module to a page</span></span>

<span data-ttu-id="05032-138">Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="05032-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="05032-139">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="05032-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="05032-140">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de carrousel**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="05032-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="05032-141">Dans l’emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="05032-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="05032-142">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="05032-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="05032-143">Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s’appelle **Page de carrousel**.</span><span class="sxs-lookup"><span data-stu-id="05032-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="05032-144">À l’emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="05032-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="05032-145">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir l’écran**.</span><span class="sxs-lookup"><span data-stu-id="05032-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="05032-146">Dans **Contour de la page**, ajoutez un module carrousel au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="05032-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="05032-147">Ajouter un module de bloc de contenu au module caroussel.</span><span class="sxs-lookup"><span data-stu-id="05032-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="05032-148">Définissez les propriétés du module de bloc de contenu en fournissant **En-tête**, **Lien**, **Disposition**et d’autres propriétés.</span><span class="sxs-lookup"><span data-stu-id="05032-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="05032-149">Ajoutez et configurez un autre module de bloc de contenu.</span><span class="sxs-lookup"><span data-stu-id="05032-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="05032-150">Définissez des propriétés supplémentaires pour le module carrousel selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="05032-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="05032-151">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="05032-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="05032-152">La page doit afficher un carrousel avec deux modules à l’intérieur (un module de bannière et un module de fonctionnalité).</span><span class="sxs-lookup"><span data-stu-id="05032-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="05032-153">Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l’effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="05032-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="05032-154">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="05032-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05032-155">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="05032-155">Additional resources</span></span>

[<span data-ttu-id="05032-156">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="05032-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="05032-157">Module Bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="05032-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="05032-158">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="05032-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="05032-159">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="05032-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="05032-160">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="05032-160">Video player module</span></span>](add-video-player.md)
