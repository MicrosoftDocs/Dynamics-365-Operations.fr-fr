---
title: Module de bloc de contenu riche
description: Cette rubrique couvre les modules de contenu riche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785419"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="e0ed3-103">Module de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="e0ed3-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e0ed3-104">Cette rubrique couvre les modules de contenu riche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e0ed3-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="e0ed3-105">Overview</span></span>

<span data-ttu-id="e0ed3-106">Un module de bloc de contenu riche est un conteneur spécial dans lequel un ou plusieurs articles de bloc de contenu riche peuvent être placés.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="e0ed3-107">Les modules en bloc de contenu riche sont utilisés pour le contenu textuel dans une page.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="e0ed3-108">Ce contenu peut être informationnel ou promotionnel.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="e0ed3-109">Les modules de bloc de contenu riche sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="e0ed3-110">Ils sont autonomes et ne dépendent du contexte de page ou d'un autre module.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="e0ed3-111">Exemples de modules de bloc de contenu riche dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="e0ed3-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="e0ed3-112">Les modules de bloc de contenu riche peuvent être utilisés comme suit :</span><span class="sxs-lookup"><span data-stu-id="e0ed3-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="e0ed3-113">Pour présenter des fonctionnalités de produit sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="e0ed3-114">À titre indicatif sur n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-114">For informational purposes on any page.</span></span> <span data-ttu-id="e0ed3-115">Par exemple, ils peuvent expliquer les avantages des programmes de fidélité, décrire les stratégies d'expédition et de retour, répondre aux questions fréquentes, ou offrir du contenu « À propos de nous ».</span><span class="sxs-lookup"><span data-stu-id="e0ed3-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="e0ed3-116">Pour ajouter des messages personnalisés sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="e0ed3-117">(par exemple, « Expédition gratuite pour les commandes de plus de 50 $ »).</span><span class="sxs-lookup"><span data-stu-id="e0ed3-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="e0ed3-118">Pour les exclusions de responsabilité et les détails de contact sur les pages de détails des produits, des pages de panier, les pages de caisse et d'autres pages (par exemple, « L'expédition et les retours sont soumis à des stratégies de magasin »).</span><span class="sxs-lookup"><span data-stu-id="e0ed3-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="e0ed3-119">Propriétés du module de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="e0ed3-119">Content rich block module properties</span></span>

| <span data-ttu-id="e0ed3-120">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="e0ed3-120">Property name</span></span>     | <span data-ttu-id="e0ed3-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="e0ed3-121">Value</span></span>                                 | <span data-ttu-id="e0ed3-122">Propriété</span><span class="sxs-lookup"><span data-stu-id="e0ed3-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="e0ed3-123">Nombre de colonnes</span><span class="sxs-lookup"><span data-stu-id="e0ed3-123">Number of columns</span></span> | <span data-ttu-id="e0ed3-124">Un numéro de **1** à **4**</span><span class="sxs-lookup"><span data-stu-id="e0ed3-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="e0ed3-125">Nombre de colonnes dans le bloc de contenu riche.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="e0ed3-126">Il peut y avoir jusqu'à quatre colonnes.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="e0ed3-127">Largeur</span><span class="sxs-lookup"><span data-stu-id="e0ed3-127">Width</span></span>             | <span data-ttu-id="e0ed3-128">**Remplir le conteneur** ou **Remplir l'écran**</span><span class="sxs-lookup"><span data-stu-id="e0ed3-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="e0ed3-129">Si la valeur est définie sur **Remplir le conteneur**, les articles à l'intérieur du conteneur sont limités à la largeur du conteneur.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="e0ed3-130">Si la valeur est définie **Plein écran**, les articles ne sont pas soumis à la largeur du conteneur mais peuvent entrer dans le mode pleine page.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="e0ed3-131">Vous pouvez modifier la valeur pour obtenir la disposition appropriée.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="e0ed3-132">Propriétés du module d'article de bloc de contenu riche</span><span class="sxs-lookup"><span data-stu-id="e0ed3-132">Content rich block item module properties</span></span>

| <span data-ttu-id="e0ed3-133">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="e0ed3-133">Property name</span></span> | <span data-ttu-id="e0ed3-134">Valeur</span><span class="sxs-lookup"><span data-stu-id="e0ed3-134">Value</span></span>          | <span data-ttu-id="e0ed3-135">Description</span><span class="sxs-lookup"><span data-stu-id="e0ed3-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="e0ed3-136">Paragraphe</span><span class="sxs-lookup"><span data-stu-id="e0ed3-136">Paragraph</span></span>     | <span data-ttu-id="e0ed3-137">Texte du paragraphe</span><span class="sxs-lookup"><span data-stu-id="e0ed3-137">Paragraph text</span></span> | <span data-ttu-id="e0ed3-138">Texte qui accompagne chaque article de bloc de contenu riche.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="e0ed3-139">Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="e0ed3-140">Ajouter un module de bloc de contenu riche à une page</span><span class="sxs-lookup"><span data-stu-id="e0ed3-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="e0ed3-141">Pour ajouter un module de bloc de contenu riche à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e0ed3-142">Créez un modèle de page nommé **modèle de contenu**.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="e0ed3-143">À l'emplacement **Principal** de la page par défaut, ajoutez un module de bloc de contenu riche.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="e0ed3-144">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="e0ed3-145">Utilisez le modèle de contenu que vous venez de créer pour créer une page qui s'appelle **page Contenu**.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="e0ed3-146">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de bloc de contenu riche.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="e0ed3-147">Dans les propriétés du module de bloc de contenu riche, définissez le nombre de colonnes sur **2**.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="e0ed3-148">Dans le module de bloc de contenu riche, sélectionnez **Ajouter un module**, puis ajoutez un article de bloc de contenu riche (par exemple, **item1**).</span><span class="sxs-lookup"><span data-stu-id="e0ed3-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="e0ed3-149">Dans le nouvel article de bloc de contenu riche, ajoutez le texte du paragraphe.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="e0ed3-150">Dans le module de bloc de contenu riche, sélectionnez **Ajouter un module**, puis ajoutez un article de bloc de contenu riche (par exemple, **item2**).</span><span class="sxs-lookup"><span data-stu-id="e0ed3-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="e0ed3-151">Dans le nouvel article de bloc de contenu riche, ajoutez le texte du paragraphe.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="e0ed3-152">Enregistrer la page et affichez un aperçu des modifications.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="e0ed3-153">Vous devez voir deux blocs de texte riche dans une vue à deux colonne.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="e0ed3-154">Archivez la page, et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ed3-155">Si vous ajoutez un troisième article de bloc de contenu riche, il sera empilé sous les deux articles que vous avez déjà ajoutés.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="e0ed3-156">En modifiant le nombre de colonnes et d'articles dans le conteneur, vous pouvez obtenir différentes dispositions pour le contenu textuel.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0ed3-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e0ed3-157">Additional resources</span></span>

[<span data-ttu-id="e0ed3-158">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="e0ed3-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e0ed3-159">Module Alerte</span><span class="sxs-lookup"><span data-stu-id="e0ed3-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="e0ed3-160">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="e0ed3-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="e0ed3-161">Module Placement de contenu</span><span class="sxs-lookup"><span data-stu-id="e0ed3-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="e0ed3-162">Module Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="e0ed3-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="e0ed3-163">Module Bannière</span><span class="sxs-lookup"><span data-stu-id="e0ed3-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="e0ed3-164">Module Lecteur vidéo</span><span class="sxs-lookup"><span data-stu-id="e0ed3-164">Video player module</span></span>](add-video-player.md)

