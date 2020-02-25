---
title: Module de bloc de texte
description: Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025595"
---
# <a name="text-block-module"></a><span data-ttu-id="58447-103">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="58447-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="58447-104">Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="58447-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="58447-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="58447-105">Overview</span></span>

<span data-ttu-id="58447-106">Un module de bloc de texte est un module utilisé pour ajouter du contenu textuel.</span><span class="sxs-lookup"><span data-stu-id="58447-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="58447-107">Ce contenu peut être informationnel ou promotionnel.</span><span class="sxs-lookup"><span data-stu-id="58447-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="58447-108">Les modules de bloc de texte sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="58447-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="58447-109">Ils sont autonomes et ne dépendent du contexte de page ou d'un autre module.</span><span class="sxs-lookup"><span data-stu-id="58447-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="58447-110">Exemples de modules de bloc de texte dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="58447-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="58447-111">Les modules de bloc de texte peuvent être utilisés comme suit :</span><span class="sxs-lookup"><span data-stu-id="58447-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="58447-112">Pour présenter des fonctionnalités de produit sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="58447-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="58447-113">À titre indicatif sur n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="58447-113">For informational purposes on any page.</span></span> <span data-ttu-id="58447-114">Par exemple, ils peuvent expliquer les avantages des programmes de fidélité, décrire les stratégies d'expédition et de retour, répondre aux questions fréquentes, ou offrir du contenu « À propos de nous ».</span><span class="sxs-lookup"><span data-stu-id="58447-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="58447-115">Pour ajouter des messages personnalisés sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="58447-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="58447-116">(par exemple, « Expédition gratuite pour les commandes de plus de 50 $ »).</span><span class="sxs-lookup"><span data-stu-id="58447-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="58447-117">Pour les exclusions de responsabilité et les détails de contact sur les pages de détails des produits, des pages de panier, les pages de caisse et d'autres pages (par exemple, « L'expédition et les retours sont soumis à des stratégies de magasin »).</span><span class="sxs-lookup"><span data-stu-id="58447-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="58447-118">Propriétés de module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="58447-118">Text block module properties</span></span>

| <span data-ttu-id="58447-119">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="58447-119">Property name</span></span>     | <span data-ttu-id="58447-120">Value</span><span class="sxs-lookup"><span data-stu-id="58447-120">Value</span></span>                                            | <span data-ttu-id="58447-121">Description</span><span class="sxs-lookup"><span data-stu-id="58447-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="58447-122">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="58447-122">Rich text</span></span>         | <span data-ttu-id="58447-123">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="58447-123">Rich text</span></span>                                        | <span data-ttu-id="58447-124">Texte du paragraphe.</span><span class="sxs-lookup"><span data-stu-id="58447-124">Paragraph text.</span></span> <span data-ttu-id="58447-125">Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques.</span><span class="sxs-lookup"><span data-stu-id="58447-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="58447-126">Nom de classe personnalisé</span><span class="sxs-lookup"><span data-stu-id="58447-126">Custom class name</span></span> | <span data-ttu-id="58447-127">Un nom de classe de feuilles de style en cascade (CSS)</span><span class="sxs-lookup"><span data-stu-id="58447-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="58447-128">Le nom d'une classe CSS personnalisée qu'un développeur fournit pour formater ce module.</span><span class="sxs-lookup"><span data-stu-id="58447-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="58447-129">Le nom de classe doit être défini dans le pack de thème.</span><span class="sxs-lookup"><span data-stu-id="58447-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="58447-130">Taille de la police</span><span class="sxs-lookup"><span data-stu-id="58447-130">Font size</span></span>         | <span data-ttu-id="58447-131">**Petit**, **Moyen**, **Grand** ou **X-Large**</span><span class="sxs-lookup"><span data-stu-id="58447-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="58447-132">La taille de police du contenu.</span><span class="sxs-lookup"><span data-stu-id="58447-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="58447-133">Ajouter un module de bloc de texte à une page</span><span class="sxs-lookup"><span data-stu-id="58447-133">Add a text block module to a page</span></span>

<span data-ttu-id="58447-134">Pour ajouter un module de bloc de texte à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="58447-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="58447-135">Créez un modèle de page nommé **modèle de contenu**.</span><span class="sxs-lookup"><span data-stu-id="58447-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="58447-136">Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.</span><span class="sxs-lookup"><span data-stu-id="58447-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="58447-137">Terminez la modification du modèle et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="58447-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="58447-138">Utilisez le modèle de contenu que vous venez de créer pour créer une page qui s'appelle **page Contenu**.</span><span class="sxs-lookup"><span data-stu-id="58447-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="58447-139">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="58447-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="58447-140">Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="58447-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="58447-141">Ajoutez un module de bloc de texte au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="58447-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="58447-142">Dans le volet des propriétés du module de bloc de texte, ajoutez du texte au champ **RTF**.</span><span class="sxs-lookup"><span data-stu-id="58447-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="58447-143">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="58447-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58447-144">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="58447-144">Additional resources</span></span>

[<span data-ttu-id="58447-145">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="58447-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="58447-146">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="58447-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="58447-147">Module de carrousel</span><span class="sxs-lookup"><span data-stu-id="58447-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="58447-148">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="58447-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="58447-149">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="58447-149">Video player module</span></span>](add-video-player.md)

