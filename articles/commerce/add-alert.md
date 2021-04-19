---
title: Module de bannière promotionnelle
description: Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: be3cc9729b58fce9ebc9885d8cb20b63114362a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796244"
---
# <a name="promo-banner-module"></a><span data-ttu-id="89f7c-103">Module Bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="89f7c-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89f7c-104">Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="89f7c-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="89f7c-105">Les modules de bannière promotionnelle sont utilisés pour afficher des messages d’information intégrés dans une page.</span><span class="sxs-lookup"><span data-stu-id="89f7c-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="89f7c-106">Ils peuvent être utilisés pour afficher des promotions à l’échelle du site qui figurent sur toutes les pages d’un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="89f7c-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="89f7c-107">Les modules de bannière promotionnelle prennent en charge un texte et un lien.</span><span class="sxs-lookup"><span data-stu-id="89f7c-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="89f7c-108">Si plusieurs messages sont ajoutés à un module de bannière promotionnelle, il devient une bannière carrousel tournante qui permet aux clients de parcourir tous les messages.</span><span class="sxs-lookup"><span data-stu-id="89f7c-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="89f7c-109">Les modules de bannière promotionnelle sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n’importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="89f7c-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="89f7c-110">Exemples d’utilisation de bannières promotionnelles dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="89f7c-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="89f7c-111">Les bannières promotionnelles peuvent être utilisées dans l’en-tête du site pour afficher des promotions ou des messages à l’échelle du site, comme dans les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="89f7c-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="89f7c-112">« Les soldes annuelles se terminent dans 10 jours »</span><span class="sxs-lookup"><span data-stu-id="89f7c-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="89f7c-113">« Réalisez des économisez avec les soldes de la rentrée.</span><span class="sxs-lookup"><span data-stu-id="89f7c-113">"Save big with back to school sale.</span></span> <span data-ttu-id="89f7c-114">Achetez dès maintenant. »</span><span class="sxs-lookup"><span data-stu-id="89f7c-114">Shop Now."</span></span>

<span data-ttu-id="89f7c-115">« Profitez des soldes de Thanksgiving ! »</span><span class="sxs-lookup"><span data-stu-id="89f7c-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="89f7c-116">L’image suivante montre un exemple d’une bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="89f7c-116">The following image shows an example of a promo banner.</span></span>

![Exemple d’un module de bannière promotionnelle](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="89f7c-118">Propriétés du module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="89f7c-118">Promo banner module properties</span></span>

| <span data-ttu-id="89f7c-119">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="89f7c-119">Property name</span></span>             | <span data-ttu-id="89f7c-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="89f7c-120">Value</span></span>                              | <span data-ttu-id="89f7c-121">Description</span><span class="sxs-lookup"><span data-stu-id="89f7c-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="89f7c-122">Messages de bannière</span><span class="sxs-lookup"><span data-stu-id="89f7c-122">Banner messages</span></span>           | <span data-ttu-id="89f7c-123">Texte et liens</span><span class="sxs-lookup"><span data-stu-id="89f7c-123">Text and links</span></span>                     | <span data-ttu-id="89f7c-124">Un groupe de texte et de liens.</span><span class="sxs-lookup"><span data-stu-id="89f7c-124">An array of text and links.</span></span> |
| <span data-ttu-id="89f7c-125">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="89f7c-125">Autoplay</span></span>                  | <span data-ttu-id="89f7c-126">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="89f7c-126">**True** or **False**</span></span>              | <span data-ttu-id="89f7c-127">Une valeur qui indique si les messages sont automatiquement parcourus, si plusieurs messages sont configurés.</span><span class="sxs-lookup"><span data-stu-id="89f7c-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="89f7c-128">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="89f7c-128">Slide transition interval</span></span> | <span data-ttu-id="89f7c-129">Un certain nombre de millisecondes (ms)</span><span class="sxs-lookup"><span data-stu-id="89f7c-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="89f7c-130">L’intervalle qui est utilisé pour parcourir les messages.</span><span class="sxs-lookup"><span data-stu-id="89f7c-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="89f7c-131">Ignorer</span><span class="sxs-lookup"><span data-stu-id="89f7c-131">Allow dismiss</span></span>             | <span data-ttu-id="89f7c-132">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="89f7c-132">**True** or **False**</span></span>              | <span data-ttu-id="89f7c-133">Si la valeur est définie sur **Vrai**, les clients peuvent ignorer l’alerte.</span><span class="sxs-lookup"><span data-stu-id="89f7c-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="89f7c-134">Afficher le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="89f7c-134">Show carousel flipper</span></span>     | <span data-ttu-id="89f7c-135">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="89f7c-135">**True** or **False**</span></span>              | <span data-ttu-id="89f7c-136">Valeur qui indique si les flippers du carrousel doivent être affichés, afin que les clients puissent parcourir manuellement plusieurs éléments de bannière.</span><span class="sxs-lookup"><span data-stu-id="89f7c-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="89f7c-137">Alignement du texte</span><span class="sxs-lookup"><span data-stu-id="89f7c-137">Text alignment</span></span>            | <span data-ttu-id="89f7c-138">**Droite**, **Gauche** ou **Centre**</span><span class="sxs-lookup"><span data-stu-id="89f7c-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="89f7c-139">L’alignement du texte dans le module de bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="89f7c-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="89f7c-140">Lien</span><span class="sxs-lookup"><span data-stu-id="89f7c-140">Link</span></span>                      | <span data-ttu-id="89f7c-141">Une URL</span><span class="sxs-lookup"><span data-stu-id="89f7c-141">A URL</span></span>                              | <span data-ttu-id="89f7c-142">URL pour un lien supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="89f7c-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="89f7c-143">Ajouter un module de bannière promotionnelle à une page</span><span class="sxs-lookup"><span data-stu-id="89f7c-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="89f7c-144">Pour ajouter un module de bannière promotionnelle à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="89f7c-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="89f7c-145">Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="89f7c-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="89f7c-146">Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="89f7c-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="89f7c-147">Dans **Contour de la page**, ajoutez un module **Page par défaut** à l’emplacement **Corps**.</span><span class="sxs-lookup"><span data-stu-id="89f7c-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="89f7c-148">Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.</span><span class="sxs-lookup"><span data-stu-id="89f7c-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="89f7c-149">Utilisez le modèle que vous venez de générer pour créer une page qui s’appelle **page de bannière promotionnelle**.</span><span class="sxs-lookup"><span data-stu-id="89f7c-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="89f7c-150">À l’emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="89f7c-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="89f7c-151">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="89f7c-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="89f7c-152">Dans **Contour de la page**, ajoutez un module bannière promotionnelle au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="89f7c-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="89f7c-153">Dans les paramètres du module de bannière, ajoutez un ou plusieurs messages de bannière.</span><span class="sxs-lookup"><span data-stu-id="89f7c-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="89f7c-154">Chaque message peut avoir du texte avec un lien.</span><span class="sxs-lookup"><span data-stu-id="89f7c-154">Each message can have text together with a link.</span></span> <span data-ttu-id="89f7c-155">Vous pouvez modifier les autres propriétés pour personnaliser davantage le module.</span><span class="sxs-lookup"><span data-stu-id="89f7c-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="89f7c-156">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="89f7c-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="89f7c-157">En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="89f7c-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="89f7c-158">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="89f7c-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="89f7c-159">Une bannière promotionnelle est généralement utilisée dans l’emplacement d’en-tête de page ou un emplacement de sous-titre.</span><span class="sxs-lookup"><span data-stu-id="89f7c-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="89f7c-160">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="89f7c-160">Additional resources</span></span>

[<span data-ttu-id="89f7c-161">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="89f7c-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="89f7c-162">Module Carrousel</span><span class="sxs-lookup"><span data-stu-id="89f7c-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="89f7c-163">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="89f7c-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="89f7c-164">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="89f7c-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="89f7c-165">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="89f7c-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]