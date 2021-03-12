---
title: Module de bannière promotionnelle
description: Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a77196be69bb71d917bf84c633199a3af3fbf478
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986027"
---
# <a name="promo-banner-module"></a><span data-ttu-id="31090-103">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="31090-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="31090-104">Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="31090-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="31090-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="31090-105">Overview</span></span>

<span data-ttu-id="31090-106">Les modules de bannière promotionnelle sont utilisés pour afficher des messages d'information intégrés dans une page.</span><span class="sxs-lookup"><span data-stu-id="31090-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="31090-107">Ils peuvent être utilisés pour afficher des promotions à l'échelle du site qui figurent sur toutes les pages d'un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="31090-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="31090-108">Les modules de bannière promotionnelle prennent en charge un texte et un lien.</span><span class="sxs-lookup"><span data-stu-id="31090-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="31090-109">Si plusieurs messages sont ajoutés à un module de bannière promotionnelle, il devient une bannière carrousel tournante qui permet aux clients de parcourir tous les messages.</span><span class="sxs-lookup"><span data-stu-id="31090-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="31090-110">Les modules de bannière promotionnelle sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="31090-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="31090-111">Exemples d'utilisation de bannières promotionnelles dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="31090-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="31090-112">Les bannières promotionnelles peuvent être utilisées dans l'en-tête du site pour afficher des promotions ou des messages à l'échelle du site, comme dans les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="31090-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="31090-113">« Les soldes annuelles se terminent dans 10 jours »</span><span class="sxs-lookup"><span data-stu-id="31090-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="31090-114">« Réalisez des économisez avec les soldes de la rentrée.</span><span class="sxs-lookup"><span data-stu-id="31090-114">"Save big with back to school sale.</span></span> <span data-ttu-id="31090-115">Achetez dès maintenant. »</span><span class="sxs-lookup"><span data-stu-id="31090-115">Shop Now."</span></span>

<span data-ttu-id="31090-116">« Profitez des soldes de Thanksgiving ! »</span><span class="sxs-lookup"><span data-stu-id="31090-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="31090-117">L'image suivante montre un exemple d'une bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="31090-117">The following image shows an example of a promo banner.</span></span>

![Exemple d'un module de bannière promotionnelle](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="31090-119">Propriétés du module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="31090-119">Promo banner module properties</span></span>

| <span data-ttu-id="31090-120">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="31090-120">Property name</span></span>             | <span data-ttu-id="31090-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="31090-121">Value</span></span>                              | <span data-ttu-id="31090-122">Description</span><span class="sxs-lookup"><span data-stu-id="31090-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="31090-123">Messages de bannière</span><span class="sxs-lookup"><span data-stu-id="31090-123">Banner messages</span></span>           | <span data-ttu-id="31090-124">Texte et liens</span><span class="sxs-lookup"><span data-stu-id="31090-124">Text and links</span></span>                     | <span data-ttu-id="31090-125">Un groupe de texte et de liens.</span><span class="sxs-lookup"><span data-stu-id="31090-125">An array of text and links.</span></span> |
| <span data-ttu-id="31090-126">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="31090-126">Autoplay</span></span>                  | <span data-ttu-id="31090-127">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="31090-127">**True** or **False**</span></span>              | <span data-ttu-id="31090-128">Une valeur qui indique si les messages sont automatiquement parcourus, si plusieurs messages sont configurés.</span><span class="sxs-lookup"><span data-stu-id="31090-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="31090-129">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="31090-129">Slide transition interval</span></span> | <span data-ttu-id="31090-130">Un certain nombre de millisecondes (ms)</span><span class="sxs-lookup"><span data-stu-id="31090-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="31090-131">L'intervalle qui est utilisé pour parcourir les messages.</span><span class="sxs-lookup"><span data-stu-id="31090-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="31090-132">Ignorer</span><span class="sxs-lookup"><span data-stu-id="31090-132">Allow dismiss</span></span>             | <span data-ttu-id="31090-133">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="31090-133">**True** or **False**</span></span>              | <span data-ttu-id="31090-134">Si la valeur est définie sur **Vrai**, les clients peuvent ignorer l'alerte.</span><span class="sxs-lookup"><span data-stu-id="31090-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="31090-135">Afficher le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="31090-135">Show carousel flipper</span></span>     | <span data-ttu-id="31090-136">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="31090-136">**True** or **False**</span></span>              | <span data-ttu-id="31090-137">Valeur qui indique si les flippers du carrousel doivent être affichés, afin que les clients puissent parcourir manuellement plusieurs éléments de bannière.</span><span class="sxs-lookup"><span data-stu-id="31090-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="31090-138">Alignement du texte</span><span class="sxs-lookup"><span data-stu-id="31090-138">Text alignment</span></span>            | <span data-ttu-id="31090-139">**Droite**, **Gauche** ou **Centre**</span><span class="sxs-lookup"><span data-stu-id="31090-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="31090-140">L'alignement du texte dans le module de bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="31090-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="31090-141">Lien</span><span class="sxs-lookup"><span data-stu-id="31090-141">Link</span></span>                      | <span data-ttu-id="31090-142">Une URL</span><span class="sxs-lookup"><span data-stu-id="31090-142">A URL</span></span>                              | <span data-ttu-id="31090-143">URL pour un lien supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="31090-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="31090-144">Ajouter un module de bannière promotionnelle à une page</span><span class="sxs-lookup"><span data-stu-id="31090-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="31090-145">Pour ajouter un module de bannière promotionnelle à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="31090-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="31090-146">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="31090-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="31090-147">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="31090-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="31090-148">Dans **Contour de la page**, ajoutez un module **Page par défaut** à l'emplacement **Corps**.</span><span class="sxs-lookup"><span data-stu-id="31090-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="31090-149">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="31090-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="31090-150">Utilisez le modèle que vous venez de générer pour créer une page qui s'appelle **page de bannière promotionnelle**.</span><span class="sxs-lookup"><span data-stu-id="31090-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="31090-151">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="31090-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="31090-152">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="31090-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="31090-153">Dans **Contour de la page**, ajoutez un module bannière promotionnelle au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="31090-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="31090-154">Dans les paramètres du module de bannière, ajoutez un ou plusieurs messages de bannière.</span><span class="sxs-lookup"><span data-stu-id="31090-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="31090-155">Chaque message peut avoir du texte avec un lien.</span><span class="sxs-lookup"><span data-stu-id="31090-155">Each message can have text together with a link.</span></span> <span data-ttu-id="31090-156">Vous pouvez modifier les autres propriétés pour personnaliser davantage le module.</span><span class="sxs-lookup"><span data-stu-id="31090-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="31090-157">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="31090-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="31090-158">En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="31090-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="31090-159">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="31090-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="31090-160">Une bannière promotionnelle est généralement utilisée dans l'emplacement d'en-tête de page ou un emplacement de sous-titre.</span><span class="sxs-lookup"><span data-stu-id="31090-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="31090-161">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="31090-161">Additional resources</span></span>

[<span data-ttu-id="31090-162">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="31090-162">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="31090-163">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="31090-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="31090-164">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="31090-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="31090-165">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="31090-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="31090-166">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="31090-166">Video player module</span></span>](add-video-player.md)
