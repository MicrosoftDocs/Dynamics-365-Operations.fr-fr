---
title: Appliquer les paramètres d’affichage pour les dimensions du produit
description: Cette rubrique couvre les paramètres d’affichage des dimensions du produit et explique comment les appliquer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117223"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="5341b-103">Appliquer les paramètres d’affichage pour les dimensions du produit</span><span class="sxs-lookup"><span data-stu-id="5341b-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="5341b-104">Cette rubrique couvre les paramètres d’affichage des dimensions du produit et explique comment les appliquer dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5341b-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5341b-105">Dynamics 365 Commerce prend en charge les dimensions de taille, de style et de couleur pour distinguer les variantes du produit.</span><span class="sxs-lookup"><span data-stu-id="5341b-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="5341b-106">Les dimensions sont généralement affichées comme valeurs de texte, telles que « Petit », « Moyen » et « Grand » pour les tailles et « Noir » et « Marron » pour les couleurs.</span><span class="sxs-lookup"><span data-stu-id="5341b-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="5341b-107">Cependant, si un produit prend en charge de nombreuses variantes, il peut être difficile de parcourir les variantes du produit, car plusieurs sélections sont nécessaires pour afficher l’image de chaque variante.</span><span class="sxs-lookup"><span data-stu-id="5341b-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="5341b-108">Pour faciliter la recherche de variantes de produit, la version 10.0.20 de Commerce peut utiliser des images et des codes hexadécimaux (hex) pour afficher les dimensions comme échantillons.</span><span class="sxs-lookup"><span data-stu-id="5341b-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="5341b-109">Dans le générateur de sites de Commerce, les paramètres de dimension sont définis dans **Paramètres du site \> Extensions \> Paramètres de dimension**.</span><span class="sxs-lookup"><span data-stu-id="5341b-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="5341b-110">L’illustration suivante montre un exemple de paramètres de dimension dans le générateur de sites.</span><span class="sxs-lookup"><span data-stu-id="5341b-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Exemple de paramètres de site dans le générateur de sites de Commerce](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="5341b-112">Deux paramètres de dimension sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="5341b-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="5341b-113">**Dimensions à afficher comme image** : spécifiez les dimensions qui doivent apparaître comme échantillons dans les pages du site d’e-commerce, telles que les pages de détails du produit (PDP) et les pages de la liste de résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="5341b-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="5341b-114">Toute combinaison de dimensions de couleur, de taille et de style peut être affichée comme échantillon.</span><span class="sxs-lookup"><span data-stu-id="5341b-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="5341b-115">Si une dimension est sélectionnée pour être affichée comme échantillon, le rendu du module Commerce recherchera une configuration disponible d’un échantillon de code hexadécimal.</span><span class="sxs-lookup"><span data-stu-id="5341b-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="5341b-116">Si aucun code hexadécimal n’est configuré, la logique système recherchera une configuration d’un échantillon d’URL d’image.</span><span class="sxs-lookup"><span data-stu-id="5341b-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="5341b-117">Si ni un code hexadécimal ni une URL d’image ne sont configurés, le texte sera affiché.</span><span class="sxs-lookup"><span data-stu-id="5341b-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="5341b-118">L’illustration suivante montre un exemple dans lequel la page des détails d’un produit sur un site d’e-commerce comprend des échantillons de couleur et de taille.</span><span class="sxs-lookup"><span data-stu-id="5341b-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="5341b-119">Dans cet exemple, un code hexadécimal est configuré pour la dimension de couleur.</span><span class="sxs-lookup"><span data-stu-id="5341b-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="5341b-120">Par conséquent, les échantillons sont affichés comme couleurs.</span><span class="sxs-lookup"><span data-stu-id="5341b-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="5341b-121">Cependant, ni un code hexadécimal ni une URL d’image ne sont configurés pour la dimension de taille.</span><span class="sxs-lookup"><span data-stu-id="5341b-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="5341b-122">Par conséquent, le texte est affiché.</span><span class="sxs-lookup"><span data-stu-id="5341b-122">Therefore, text is shown.</span></span>

    ![Exemple de la dimension de couleur affichée comme échantillons dans la page des détails d’un produit d’e-commerce](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="5341b-124">**Dimensions à afficher dans la fiche produit** : spécifiez les dimensions qui doivent apparaître sur les fiches produit affichées dans les listes et dans les pages de liste.</span><span class="sxs-lookup"><span data-stu-id="5341b-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="5341b-125">Pour qu’une dimension puisse apparaître sur une fiche produit, ce paramètre doit être activé pour cette dimension.</span><span class="sxs-lookup"><span data-stu-id="5341b-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="5341b-126">Le paramètre **Dimensions à afficher comme image** doit également être activé.</span><span class="sxs-lookup"><span data-stu-id="5341b-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="5341b-127">Le comportement de sélection d’échantillons dans les fiches produit est optimisé pour la dimension de couleur.</span><span class="sxs-lookup"><span data-stu-id="5341b-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="5341b-128">Pour les autres dimensions, une extension de vue peut être nécessaire pour personnaliser le comportement de sélection d’échantillons.</span><span class="sxs-lookup"><span data-stu-id="5341b-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="5341b-129">L’illustration suivante montre un exemple dans lequel une page de liste sur un site d’e-commerce contient des fiches produit incluant des échantillons de couleur.</span><span class="sxs-lookup"><span data-stu-id="5341b-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Exemple de la dimension de couleur affichée comme échantillons dans une page de liste d’e- commerce](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="5341b-131">Pour plus d’informations sur la configuration des dimensions du produit afin qu’elles s’affichent comme échantillons dans les pages du site, consultez [Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="5341b-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5341b-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5341b-132">Additional resources</span></span>

[<span data-ttu-id="5341b-133">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="5341b-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5341b-134">Module de résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="5341b-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="5341b-135">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="5341b-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="5341b-136">Configurer les valeurs des dimensions du produit pour qu’elles apparaissent en tant qu’échantillons</span><span class="sxs-lookup"><span data-stu-id="5341b-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
