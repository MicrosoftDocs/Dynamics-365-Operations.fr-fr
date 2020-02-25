---
title: Module de bannière promotionnelle
description: Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025618"
---
# <a name="promo-banner-module"></a><span data-ttu-id="f4cf8-103">Module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="f4cf8-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f4cf8-104">Cette rubrique couvre les modules de bannière promotionnelle et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f4cf8-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="f4cf8-105">Overview</span></span>

<span data-ttu-id="f4cf8-106">Les modules de bannière promotionnelle sont utilisés pour afficher des messages d'information intégrés dans une page.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="f4cf8-107">Ils peuvent être utilisés pour afficher des promotions à l'échelle du site qui figurent sur toutes les pages d'un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="f4cf8-108">Les modules de bannière promotionnelle prennent en charge un texte et un lien.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="f4cf8-109">Si plusieurs messages sont ajoutés à un module de bannière promotionnelle, il devient une bannière carrousel tournante qui permet aux clients de parcourir tous les messages.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="f4cf8-110">Les modules de bannière promotionnelle sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="f4cf8-111">Exemples d'utilisation de bannières promotionnelles dans le commerce électronique</span><span class="sxs-lookup"><span data-stu-id="f4cf8-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="f4cf8-112">Les bannières promotionnelles peuvent être utilisées dans l'en-tête du site pour afficher des promotions ou des messages à l'échelle du site, comme dans les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="f4cf8-113">« Les soldes annuelles se terminent dans 10 jours »</span><span class="sxs-lookup"><span data-stu-id="f4cf8-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="f4cf8-114">« Réalisez des économisez avec les soldes de la rentrée.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-114">"Save big with back to school sale.</span></span> <span data-ttu-id="f4cf8-115">Achetez dès maintenant. »</span><span class="sxs-lookup"><span data-stu-id="f4cf8-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="f4cf8-116">Propriétés du module de bannière promotionnelle</span><span class="sxs-lookup"><span data-stu-id="f4cf8-116">Promo banner module properties</span></span>

| <span data-ttu-id="f4cf8-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="f4cf8-117">Property name</span></span>             | <span data-ttu-id="f4cf8-118">Value</span><span class="sxs-lookup"><span data-stu-id="f4cf8-118">Value</span></span>                              | <span data-ttu-id="f4cf8-119">Description</span><span class="sxs-lookup"><span data-stu-id="f4cf8-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="f4cf8-120">Messages de bannière</span><span class="sxs-lookup"><span data-stu-id="f4cf8-120">Banner messages</span></span>           | <span data-ttu-id="f4cf8-121">Texte et liens</span><span class="sxs-lookup"><span data-stu-id="f4cf8-121">Text and links</span></span>                     | <span data-ttu-id="f4cf8-122">Un groupe de texte et de liens.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-122">An array of text and links.</span></span> |
| <span data-ttu-id="f4cf8-123">Lire automatiquement</span><span class="sxs-lookup"><span data-stu-id="f4cf8-123">Autoplay</span></span>                  | <span data-ttu-id="f4cf8-124">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="f4cf8-124">**True** or **False**</span></span>              | <span data-ttu-id="f4cf8-125">Une valeur qui indique si les messages sont automatiquement parcourus, si plusieurs messages sont configurés.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="f4cf8-126">Intervalle de transition entre les diapositives</span><span class="sxs-lookup"><span data-stu-id="f4cf8-126">Slide transition interval</span></span> | <span data-ttu-id="f4cf8-127">Un certain nombre de millisecondes (ms)</span><span class="sxs-lookup"><span data-stu-id="f4cf8-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="f4cf8-128">L'intervalle qui est utilisé pour parcourir les messages.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="f4cf8-129">Ignorer</span><span class="sxs-lookup"><span data-stu-id="f4cf8-129">Allow dismiss</span></span>             | <span data-ttu-id="f4cf8-130">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="f4cf8-130">**True** or **False**</span></span>              | <span data-ttu-id="f4cf8-131">Si la valeur est définie sur **Vrai**, les clients peuvent ignorer l'alerte.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="f4cf8-132">Afficher le flipper du carrousel</span><span class="sxs-lookup"><span data-stu-id="f4cf8-132">Show carousel flipper</span></span>     | <span data-ttu-id="f4cf8-133">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="f4cf8-133">**True** or **False**</span></span>              | <span data-ttu-id="f4cf8-134">Valeur qui indique si les flippers du carrousel doivent être affichés, afin que les clients puissent parcourir manuellement plusieurs éléments de bannière.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="f4cf8-135">Alignement du texte</span><span class="sxs-lookup"><span data-stu-id="f4cf8-135">Text alignment</span></span>            | <span data-ttu-id="f4cf8-136">**Droite**, **Gauche** ou **Centre**</span><span class="sxs-lookup"><span data-stu-id="f4cf8-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="f4cf8-137">L'alignement du texte dans le module de bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="f4cf8-138">Lien</span><span class="sxs-lookup"><span data-stu-id="f4cf8-138">Link</span></span>                      | <span data-ttu-id="f4cf8-139">Une URL</span><span class="sxs-lookup"><span data-stu-id="f4cf8-139">A URL</span></span>                              | <span data-ttu-id="f4cf8-140">URL pour un lien supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="f4cf8-141">Ajouter un module de bannière promotionnelle à une page</span><span class="sxs-lookup"><span data-stu-id="f4cf8-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="f4cf8-142">Pour ajouter un module de bannière promotionnelle à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f4cf8-143">Créez un modèle de page nommé **modèle de bannière promotionnelle**.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="f4cf8-144">Dans **Contour de la page**, ajoutez un module **Page par défaut** à l'emplacement **Corps**.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="f4cf8-145">Archivez le modèle, et publiez-le.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="f4cf8-146">Utilisez le modèle que vous venez de générer pour créer une page qui s'appelle **page de bannière promotionnelle**.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="f4cf8-147">À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="f4cf8-148">Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="f4cf8-149">Dans **Contour de la page**, ajoutez un module bannière promotionnelle au module conteneur.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="f4cf8-150">Dans les paramètres du module de bannière, ajoutez un ou plusieurs messages de bannière.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="f4cf8-151">Chaque message peut avoir du texte avec un lien.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-151">Each message can have text together with a link.</span></span> <span data-ttu-id="f4cf8-152">Vous pouvez modifier les autres propriétés pour personnaliser davantage le module.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="f4cf8-153">Enregistrez et affichez un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-153">Save and preview the page.</span></span> <span data-ttu-id="f4cf8-154">En haut de la page, vous devez voir une alerte avec le texte que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="f4cf8-155">Terminez la modification de la page et publiez-la.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4cf8-156">Une bannière promotionnelle est généralement utilisée dans l'emplacement d'en-tête de page ou un emplacement de sous-titre.</span><span class="sxs-lookup"><span data-stu-id="f4cf8-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="f4cf8-157">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f4cf8-157">Additional resources</span></span>

[<span data-ttu-id="f4cf8-158">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="f4cf8-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f4cf8-159">Module de carrousel</span><span class="sxs-lookup"><span data-stu-id="f4cf8-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="f4cf8-160">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="f4cf8-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="f4cf8-161">Module de bloc de contenu</span><span class="sxs-lookup"><span data-stu-id="f4cf8-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="f4cf8-162">Module de lecture vidéo</span><span class="sxs-lookup"><span data-stu-id="f4cf8-162">Video player module</span></span>](add-video-player.md)
