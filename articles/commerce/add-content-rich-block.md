---
title: Module de bloc de texte
description: Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412203"
---
# <a name="text-block-module"></a><span data-ttu-id="c0fac-103">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="c0fac-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c0fac-104">Cette rubrique couvre les modules de bloc de texte et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0fac-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c0fac-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="c0fac-105">Overview</span></span>

<span data-ttu-id="c0fac-106">Un module de bloc de texte est un module utilisé pour ajouter du contenu textuel.</span><span class="sxs-lookup"><span data-stu-id="c0fac-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="c0fac-107">Ce contenu peut être informationnel ou promotionnel.</span><span class="sxs-lookup"><span data-stu-id="c0fac-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="c0fac-108">Les modules de bloc de texte sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="c0fac-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="c0fac-109">Ils sont autonomes et ne dépendent du contexte de page ou d'un autre module.</span><span class="sxs-lookup"><span data-stu-id="c0fac-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="c0fac-110">Exemples de modules de bloc de texte dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="c0fac-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="c0fac-111">Les modules de bloc de texte peuvent être utilisés comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0fac-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="c0fac-112">Pour présenter des fonctionnalités de produit sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="c0fac-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="c0fac-113">À titre indicatif sur n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="c0fac-113">For informational purposes on any page.</span></span> <span data-ttu-id="c0fac-114">Par exemple, ils peuvent expliquer les avantages des programmes de fidélité, décrire les stratégies d'expédition et de retour, répondre aux questions fréquentes, ou offrir du contenu « À propos de nous ».</span><span class="sxs-lookup"><span data-stu-id="c0fac-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="c0fac-115">Pour ajouter des messages personnalisés sur une page de détails des produits.</span><span class="sxs-lookup"><span data-stu-id="c0fac-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="c0fac-116">(par exemple, « Expédition gratuite pour les commandes de plus de 50 $ »).</span><span class="sxs-lookup"><span data-stu-id="c0fac-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="c0fac-117">Pour les exclusions de responsabilité et les détails de contact sur les pages de détails des produits, des pages de panier, les pages de caisse et d'autres pages (par exemple, « L'expédition et les retours sont soumis à des stratégies de magasin »).</span><span class="sxs-lookup"><span data-stu-id="c0fac-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="c0fac-118">L'image suivante montre un exemple de module de bloc de texte utilisé sur une page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="c0fac-118">The following image shows an example of a text block module that is used on a home page.</span></span>

![Exemple d'un module de bloc de texte](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="c0fac-120">Propriétés de module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="c0fac-120">Text block module properties</span></span>

| <span data-ttu-id="c0fac-121">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="c0fac-121">Property name</span></span>     | <span data-ttu-id="c0fac-122">Valeur</span><span class="sxs-lookup"><span data-stu-id="c0fac-122">Value</span></span>                                            | <span data-ttu-id="c0fac-123">Description</span><span class="sxs-lookup"><span data-stu-id="c0fac-123">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="c0fac-124">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="c0fac-124">Rich text</span></span>         | <span data-ttu-id="c0fac-125">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="c0fac-125">Rich text</span></span>                                        | <span data-ttu-id="c0fac-126">Texte du paragraphe.</span><span class="sxs-lookup"><span data-stu-id="c0fac-126">Paragraph text.</span></span> <span data-ttu-id="c0fac-127">Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques.</span><span class="sxs-lookup"><span data-stu-id="c0fac-127">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="c0fac-128">Nom de classe personnalisé</span><span class="sxs-lookup"><span data-stu-id="c0fac-128">Custom class name</span></span> | <span data-ttu-id="c0fac-129">Un nom de classe de feuilles de style en cascade (CSS)</span><span class="sxs-lookup"><span data-stu-id="c0fac-129">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="c0fac-130">Le nom d'une classe CSS personnalisée qu'un développeur fournit pour formater ce module.</span><span class="sxs-lookup"><span data-stu-id="c0fac-130">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="c0fac-131">Le nom de classe doit être défini dans le pack de thème.</span><span class="sxs-lookup"><span data-stu-id="c0fac-131">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="c0fac-132">Taille de la police</span><span class="sxs-lookup"><span data-stu-id="c0fac-132">Font size</span></span>         | <span data-ttu-id="c0fac-133">**Petit**, **Moyen**, **Grand** ou **X-Large**</span><span class="sxs-lookup"><span data-stu-id="c0fac-133">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="c0fac-134">La taille de police du contenu.</span><span class="sxs-lookup"><span data-stu-id="c0fac-134">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="c0fac-135">Ajouter un module de bloc de texte à une page</span><span class="sxs-lookup"><span data-stu-id="c0fac-135">Add a text block module to a page</span></span>

<span data-ttu-id="c0fac-136">Pour ajouter un module de bloc de texte à une nouvelle page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c0fac-136">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c0fac-137">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="c0fac-137">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c0fac-138">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de contenu**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-138">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="c0fac-139">Dans l'emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-139">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c0fac-140">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Page par défaut**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-140">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c0fac-141">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="c0fac-141">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="c0fac-142">Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.</span><span class="sxs-lookup"><span data-stu-id="c0fac-142">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="c0fac-143">Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle **Modèle de contenu**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-143">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="c0fac-144">Sous **Nom de la page**, entrez **Page de contenu**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-144">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="c0fac-145">Dans l'emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-145">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c0fac-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-146">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c0fac-147">Dans le volet de propriétés du module conteneur, définissez la propriété **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-147">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="c0fac-148">Dans l'emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-148">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c0fac-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-149">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="c0fac-150">Dans le volet des propriétés du module de bloc de texte, ajoutez du texte au champ **RTF**.</span><span class="sxs-lookup"><span data-stu-id="c0fac-150">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="c0fac-151">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="c0fac-151">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="c0fac-152">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="c0fac-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c0fac-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c0fac-153">Additional resources</span></span>

[<span data-ttu-id="c0fac-154">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="c0fac-154">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c0fac-155">Module Bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="c0fac-155">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="c0fac-156">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="c0fac-156">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="c0fac-157">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="c0fac-157">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="c0fac-158">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="c0fac-158">Video player module</span></span>](add-video-player.md)

