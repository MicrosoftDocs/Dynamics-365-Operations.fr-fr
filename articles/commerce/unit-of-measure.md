---
title: Appliquer les paramètres d'unité de mesure
description: Cette rubrique couvre les paramètres d'unité de mesure et décrit leur application dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
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
ms.openlocfilehash: d1fba966434b80c9b64c1f4d9b6b87993d59c0bf
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022372"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="ee43c-103">Appliquer les paramètres d'unité de mesure</span><span class="sxs-lookup"><span data-stu-id="ee43c-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="ee43c-104">Cette rubrique couvre les paramètres d'unité de mesure et décrit leur application dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee43c-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ee43c-105">Un produit peut être vendu en différentes unités, par exemple en « unité », en « paire » et en « douzaine »</span><span class="sxs-lookup"><span data-stu-id="ee43c-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="ee43c-106">Au siège de Commerce, l'unité de mesure de vente par produit peut être définie pour un produit et affichée sur un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="ee43c-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="ee43c-107">Par exemple, si un détaillant vend un produit à la fois individuellement et par dizaines, les unités de mesure disponibles peuvent être affichées avec d'autres informations sur le produit.</span><span class="sxs-lookup"><span data-stu-id="ee43c-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="ee43c-108">Dans l'exemple de l'illustration suivante, une unité de mesure de vente par **unité** a été configuré pour un produit au siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee43c-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Exemple de produit configuré avec une unité de mesure au siège de Commerce](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="ee43c-110">La prise en charge de l'application et de l'affichage de l'unité de mesure est disponible à partir de la version 10.0.19 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee43c-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="ee43c-111">Paramètres d'unité de mesure</span><span class="sxs-lookup"><span data-stu-id="ee43c-111">Unit of measure settings</span></span>

<span data-ttu-id="ee43c-112">Les paramètres d'affichage des unités de mesure sont définis dans le générateur de site Commerce, dans **Paramètres du site \> Extensions \> Afficher l'unité de mesure des produits**.</span><span class="sxs-lookup"><span data-stu-id="ee43c-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="ee43c-113">Il existe trois paramètres pris en charge :</span><span class="sxs-lookup"><span data-stu-id="ee43c-113">There are three supported settings:</span></span>

- <span data-ttu-id="ee43c-114">**Ne pas afficher** - Lorsque ce paramètre est sélectionné, le site de commerce électronique n'affiche pas l'unité de mesure du produit.</span><span class="sxs-lookup"><span data-stu-id="ee43c-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="ee43c-115">Ce comportement est celui par défaut.</span><span class="sxs-lookup"><span data-stu-id="ee43c-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="ee43c-116">**Affichage dans l'expérience d'achat du produit** - Lorsque ce paramètre est sélectionné, l'unité de mesure est affichée sur les pages des détails du produit, du panier, de la caisse, de l'historique des commandes et des détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="ee43c-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="ee43c-117">**Affichage dans la navigation du produit et l'expérience d'achat** - Lorsque ce paramètre est sélectionné, l'unité de mesure est affichée sur les pages d'expérience d'achat du produit et également pendant l'expérience de navigation du produit.</span><span class="sxs-lookup"><span data-stu-id="ee43c-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="ee43c-118">Les unités de mesure sont alors affichées dans les résultats de recherche et les modules de collecte de produits.</span><span class="sxs-lookup"><span data-stu-id="ee43c-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee43c-119">Les paramètres d'affichage des unités de mesure sont disponibles à partir de la version 10.0.19 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ee43c-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="ee43c-120">Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="ee43c-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="ee43c-121">Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="ee43c-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="ee43c-122">Modules qui utilisent les paramètres d'unité de mesure</span><span class="sxs-lookup"><span data-stu-id="ee43c-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="ee43c-123">Les modules qui utilisent les paramètres d'unité de mesure incluent la zone d'achat, la liste de souhaits, le panier, l'icône du panier, le conteneur de résultats de recherche, la collection de produits, le paiement et les modules de détails de la commande.</span><span class="sxs-lookup"><span data-stu-id="ee43c-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="ee43c-124">Dans l'exemple de l'illustration suivante, une page de détails du produit (PDP) montre l'unité de mesure (**unité**) pour un produit.</span><span class="sxs-lookup"><span data-stu-id="ee43c-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Exemple de PDP qui montre l'unité de mesure](./media/Productunit-PDP.png)

<span data-ttu-id="ee43c-126">Dans l'exemple de l'illustration suivante, un module de collecte de produits montre l'unité de mesure (**unité**) pour un produit.</span><span class="sxs-lookup"><span data-stu-id="ee43c-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Exemple de module de collecte de produits affichant l'unité de mesure](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="ee43c-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ee43c-128">Additional resources</span></span>

[<span data-ttu-id="ee43c-129">Vue d’ensemble de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="ee43c-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ee43c-130">Module Panier</span><span class="sxs-lookup"><span data-stu-id="ee43c-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ee43c-131">Module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="ee43c-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ee43c-132">Pages et modules Gestion des comptes</span><span class="sxs-lookup"><span data-stu-id="ee43c-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="ee43c-133">Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules</span><span class="sxs-lookup"><span data-stu-id="ee43c-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
