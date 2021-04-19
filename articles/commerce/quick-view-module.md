---
title: Module de visualisation rapide
description: Cette rubrique couvre les modules de visualisation rapide et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d7e88163fd9b8dc4f5636ed29e2c4248aece52bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792169"
---
# <a name="quick-view-module"></a><span data-ttu-id="1b743-103">Module de visualisation rapide</span><span class="sxs-lookup"><span data-stu-id="1b743-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1b743-104">Cette rubrique couvre les modules de visualisation rapide et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1b743-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1b743-105">Le module de visualisation rapide permet aux utilisateurs d’afficher rapidement les informations sur les produits lorsqu’ils les parcourent sur une page de liste et d’ajouter un ou plusieurs produits au panier à partir de la page de liste, sans avoir à accéder à la page de détails du produit (PDP).</span><span class="sxs-lookup"><span data-stu-id="1b743-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="1b743-106">Le module de visualisation rapide fournit un aperçu des informations sur le produit dont les utilisateurs ont besoin pour décider de l’ajouter au panier.</span><span class="sxs-lookup"><span data-stu-id="1b743-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="1b743-107">Il fournit également un lien vers le PDP, afin que les utilisateurs puissent afficher des détails supplémentaires sur le produit et des options d’achat.</span><span class="sxs-lookup"><span data-stu-id="1b743-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="1b743-108">Le module de visualisation rapide est pris en charge par les modules [Collecte de produits](product-collection-module-overview.md) et [Résultats de recherche](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="1b743-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b743-109">Le module de visualisation rapide est disponible à partir de la version 10.0.17 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="1b743-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="1b743-110">L’illustration suivante montre un exemple du module de visualisation rapide sur une page de liste de produits.</span><span class="sxs-lookup"><span data-stu-id="1b743-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Exemple de module de visualisation rapide sur une page de liste de produits](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="1b743-112">Propriétés du module</span><span class="sxs-lookup"><span data-stu-id="1b743-112">Module properties</span></span>

<span data-ttu-id="1b743-113">Le module de visualisation rapide prend en charge certaines des fonctions du module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="1b743-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="1b743-114">Par conséquent, les propriétés d’un module de visualisation rapide ressemblent à celles d’un module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="1b743-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="1b743-115">Propriété</span><span class="sxs-lookup"><span data-stu-id="1b743-115">Property</span></span> | <span data-ttu-id="1b743-116">Valeurs</span><span class="sxs-lookup"><span data-stu-id="1b743-116">Values</span></span> | <span data-ttu-id="1b743-117">Description</span><span class="sxs-lookup"><span data-stu-id="1b743-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="1b743-118">Balise d’en-tête</span><span class="sxs-lookup"><span data-stu-id="1b743-118">Heading tag</span></span> | <span data-ttu-id="1b743-119">**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**</span><span class="sxs-lookup"><span data-stu-id="1b743-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="1b743-120">Cette propriété définit la balise d’en-tête du titre du produit.</span><span class="sxs-lookup"><span data-stu-id="1b743-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="1b743-121">Si le module de visualisation rapide se trouve en haut de la page, cette propriété doit être définie sur **H1** pour répondre aux normes d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="1b743-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="1b743-122">Autoriser un prix personnalisé</span><span class="sxs-lookup"><span data-stu-id="1b743-122">Allow custom price</span></span> | <span data-ttu-id="1b743-123">**Vrai** ou **Faux**</span><span class="sxs-lookup"><span data-stu-id="1b743-123">**True** or **False**</span></span> | <span data-ttu-id="1b743-124">Si cette propriété est définie sur **True**, l’utilisateur peut saisir un prix personnalisé.</span><span class="sxs-lookup"><span data-stu-id="1b743-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="1b743-125">Prix minimal</span><span class="sxs-lookup"><span data-stu-id="1b743-125">Minimum price</span></span> | <span data-ttu-id="1b743-126">Entier</span><span class="sxs-lookup"><span data-stu-id="1b743-126">Integer</span></span> | <span data-ttu-id="1b743-127">Cette propriété n’est applicable que si la propriété **Autoriser un prix personnalisé** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="1b743-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="1b743-128">Elle définit le prix minimum que l’utilisateur peut saisir (par exemple, 1 $).</span><span class="sxs-lookup"><span data-stu-id="1b743-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="1b743-129">Prix maximal</span><span class="sxs-lookup"><span data-stu-id="1b743-129">Maximum price</span></span> | <span data-ttu-id="1b743-130">Entier</span><span class="sxs-lookup"><span data-stu-id="1b743-130">Integer</span></span> | <span data-ttu-id="1b743-131">Cette propriété n’est applicable que si la propriété **Autoriser un prix personnalisé** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="1b743-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="1b743-132">Elle définit le prix maximal que l’utilisateur peut saisir (par exemple, 1 000 $).</span><span class="sxs-lookup"><span data-stu-id="1b743-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="1b743-133">Paramètres du générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="1b743-133">Commerce site builder settings</span></span>

<span data-ttu-id="1b743-134">Tout comme le module de zone d’achat, le module de visualisation rapide respecte les paramètres de **Paramètres du site \> Extensions \> Ajouter un article au panier**.</span><span class="sxs-lookup"><span data-stu-id="1b743-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="1b743-135">Cependant, le paramètre **Page Accéder au panier** est ignoré, car il est incompatible avec l’objectif du module de visualisation rapide, qui est de permettre aux utilisateurs de parcourir plusieurs produits sur une page de liste et de les ajouter au panier sans s’éloigner de la page de liste.</span><span class="sxs-lookup"><span data-stu-id="1b743-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="1b743-136">Ajouter un module de visualisation rapide à un module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="1b743-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="1b743-137">Il est possible d’ajouter un module de visualisation rapide aux modules de collecte de produits et des résultats de recherche.</span><span class="sxs-lookup"><span data-stu-id="1b743-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="1b743-138">Pour ajouter un module de visualisation rapide à un module de collecte de produits dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1b743-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1b743-139">Allez dans **Pages**, puis sélectionnez la page d’accueil du site Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="1b743-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="1b743-140">Allez dans n’importe quel module **Collecte de produits** sur la page d’accueil, sélectionnez les points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="1b743-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1b743-141">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module de **visualisation rapide**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b743-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1b743-142">Dans le volet des propriétés du module de **visualisation rapide**, sélectionnez **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="1b743-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="1b743-143">Dans la boîte de dialogue **En-tête**, définissez le champ **Niveau d’en-tête** sur **H2**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b743-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="1b743-144">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="1b743-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b743-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b743-145">Additional resources</span></span>

[<span data-ttu-id="1b743-146">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="1b743-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1b743-147">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="1b743-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1b743-148">Module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="1b743-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="1b743-149">Module des résultats de recherche</span><span class="sxs-lookup"><span data-stu-id="1b743-149">Search results module</span></span>](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
