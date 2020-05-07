---
title: Module de bannière promotionnelle
description: Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 12cabbf0b8d9f337f15a8cd6cb1f2a85100b75f7
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269772"
---
# <a name="promo-banner-module"></a><span data-ttu-id="15acf-103">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="15acf-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="15acf-104">Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="15acf-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="15acf-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="15acf-105">Overview</span></span>

<span data-ttu-id="15acf-106">Les modules de bannière promotionnelle sont utilisés pour afficher des messages d'information intégrés dans une page.</span><span class="sxs-lookup"><span data-stu-id="15acf-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="15acf-107">Ils peuvent être utilisés pour afficher des promotions à l'échelle du site qui figurent sur toutes les pages d'un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="15acf-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="15acf-108">Les modules de bannière promotionnelle prennent en charge un texte et un lien.</span><span class="sxs-lookup"><span data-stu-id="15acf-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="15acf-109">Si plusieurs messages sont ajoutés à un module de bannière promotionnelle, il devient une bannière carrousel tournante qui permet aux clients de parcourir tous les messages.</span><span class="sxs-lookup"><span data-stu-id="15acf-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="15acf-110">Les modules de bannière promotionnelle sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="15acf-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="15acf-111">Exemples d'utilisation de bannières promotionnelles dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="15acf-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="15acf-112">Les bannières promotionnelles peuvent être utilisées dans l'en-tête du site pour afficher des promotions ou des messages à l'échelle du site, comme dans les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="15acf-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="15acf-113">« Les soldes annuelles se terminent dans 10 jours »</span><span class="sxs-lookup"><span data-stu-id="15acf-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="15acf-114">« Réalisez des économisez avec les soldes de la rentrée.</span><span class="sxs-lookup"><span data-stu-id="15acf-114">"Save big with back to school sale.</span></span> <span data-ttu-id="15acf-115">Achetez dès maintenant. »</span><span class="sxs-lookup"><span data-stu-id="15acf-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="15acf-116">Propriétés du module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="15acf-116">Promo banner module properties</span></span>

| <span data-ttu-id="15acf-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="15acf-117">Property name</span></span>             | <span data-ttu-id="15acf-118">Value</span><span class="sxs-lookup"><span data-stu-id="15acf-118">Value</span></span>                              | <span data-ttu-id="15acf-119">Description</span><span class="sxs-lookup"><span data-stu-id="15acf-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="15acf-120">Messages de bannière</span><span class="sxs-lookup"><span data-stu-id="15acf-120">Banner messages</span></span>           | <span data-ttu-id="15acf-121">Texte et liens</span><span class="sxs-lookup"><span data-stu-id="15acf-121">Text and links</span></span>                     | <span data-ttu-id="15acf-122">Un groupe de texte et de liens.</span><span class="sxs-lookup"><span data-stu-id="15acf-122">An array of text and links.</span></span> |
| <span data-ttu-id="15acf-123">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="15acf-123">Autoplay</span></span>                  | <span data-ttu-id="15acf-124">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="15acf-124">**True** or **False**</span></span>              | <span data-ttu-id="15acf-125">Une valeur qui indique si les messages sont automatiquement parcourus, si plusieurs messages sont configurés.</span><span class="sxs-lookup"><span data-stu-id="15acf-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="15acf-126">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="15acf-126">Slide transition interval</span></span> | <span data-ttu-id="15acf-127">Un certain nombre de millisecondes (ms)</span><span class="sxs-lookup"><span data-stu-id="15acf-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="15acf-128">L'intervalle qui est utilisé pour parcourir les messages.</span><span class="sxs-lookup"><span data-stu-id="15acf-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="15acf-129">Ignorer</span><span class="sxs-lookup"><span data-stu-id="15acf-129">Allow dismiss</span></span>             | <span data-ttu-id="15acf-130">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="15acf-130">**True** or **False**</span></span>              | <span data-ttu-id="15acf-131">Si la valeur est définie sur **Vrai**, les clients peuvent ignorer l'alerte.</span><span class="sxs-lookup"><span data-stu-id="15acf-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="15acf-132">Afficher le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="15acf-132">Show carousel flipper</span></span>     | <span data-ttu-id="15acf-133">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="15acf-133">**True** or **False**</span></span>              | <span data-ttu-id="15acf-134">Valeur qui indique si les flippers du carrousel doivent être affichés, afin que les clients puissent parcourir manuellement plusieurs éléments de bannière.</span><span class="sxs-lookup"><span data-stu-id="15acf-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="15acf-135">Alignement du texte</span><span class="sxs-lookup"><span data-stu-id="15acf-135">Text alignment</span></span>            | <span data-ttu-id="15acf-136">**Droite**, **Gauche** ou **Centre**</span><span class="sxs-lookup"><span data-stu-id="15acf-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="15acf-137">L'alignement du texte dans le module de bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="15acf-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="15acf-138">Lien</span><span class="sxs-lookup"><span data-stu-id="15acf-138">Link</span></span>                      | <span data-ttu-id="15acf-139">Une URL</span><span class="sxs-lookup"><span data-stu-id="15acf-139">A URL</span></span>                              | <span data-ttu-id="15acf-140">URL pour un lien supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="15acf-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="15acf-141">Ajouter un module de bannière promotionnelle à une page</span><span class="sxs-lookup"><span data-stu-id="15acf-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="15acf-142">Pour ajouter un module de bannière promotionnelle à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="15acf-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="15acf-143">Sélectionnez **Nouveau** pour créer un modèle de page.</span><span class="sxs-lookup"><span data-stu-id="15acf-143">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="15acf-144">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="15acf-144">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="15acf-145">Dans **Contour de la page**, ajoutez un module **Page par défaut** à l'emplacement **Corps**.</span><span class="sxs-lookup"><span data-stu-id="15acf-145">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="15acf-146">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="15acf-146">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="15acf-147">Utilisez le modèle que vous venez de générer pour créer une page qui s'appelle **page de bannière promotionnelle**.</span><span class="sxs-lookup"><span data-stu-id="15acf-147">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="15acf-148">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="15acf-148">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="15acf-149">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="15acf-149">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="15acf-150">Dans **Contour de la page**, ajoutez un module bannière promotionnelle au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="15acf-150">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="15acf-151">Dans les paramètres du module de bannière, ajoutez un ou plusieurs messages de bannière.</span><span class="sxs-lookup"><span data-stu-id="15acf-151">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="15acf-152">Chaque message peut avoir du texte avec un lien.</span><span class="sxs-lookup"><span data-stu-id="15acf-152">Each message can have text together with a link.</span></span> <span data-ttu-id="15acf-153">Vous pouvez modifier les autres propriétés pour personnaliser davantage le module.</span><span class="sxs-lookup"><span data-stu-id="15acf-153">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="15acf-154">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="15acf-154">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="15acf-155">En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="15acf-155">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="15acf-156">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="15acf-156">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="15acf-157">Une bannière promotionnelle est généralement utilisée dans l'emplacement d'en-tête de page ou un emplacement de sous-titre.</span><span class="sxs-lookup"><span data-stu-id="15acf-157">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="15acf-158">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="15acf-158">Additional resources</span></span>

[<span data-ttu-id="15acf-159">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="15acf-159">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="15acf-160">Module de carrousel</span><span class="sxs-lookup"><span data-stu-id="15acf-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="15acf-161">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="15acf-161">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="15acf-162">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="15acf-162">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="15acf-163">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="15acf-163">Video player module</span></span>](add-video-player.md)
