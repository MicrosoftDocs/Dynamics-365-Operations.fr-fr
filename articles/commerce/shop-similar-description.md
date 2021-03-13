---
title: Activer les recommandations « acheter des descriptions similaires »
description: Cette rubrique décrit comment activer la fonctionnalité de recommandations de produits « acheter des descriptions similaires » dans Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b3b7abf47a3bdacaa4b91ae32b68a809a84b0b1d
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098626"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="f29be-103">Activer les recommandations « acheter des descriptions similaires »</span><span class="sxs-lookup"><span data-stu-id="f29be-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f29be-104">Cette rubrique décrit comment activer la fonctionnalité de recommandations de produits « acheter des descriptions similaires » dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f29be-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f29be-105">La fonctionnalité de recommandations « Acheter des description similaires » dans Dynamics 365 Commerce utilise l’intelligence artificielle et le Machine Learning (IA-ML) pour recommander des produits dont les descriptions correspondent à ce que recherchent les clients.</span><span class="sxs-lookup"><span data-stu-id="f29be-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="f29be-106">En mettant à disposition des recommandations de type « acheter des descriptions similaires » pour tous les canaux de vente au détail dans Commerce, les détaillants peuvent aider leurs clients à trouver facilement ce qu’ils veulent.</span><span class="sxs-lookup"><span data-stu-id="f29be-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="f29be-107">La fonctionnalité de recommandations « acheter des descriptions similaires » utilise le nom et la description de produits initiaux pour rechercher et recommander des produits similaires dans le catalogue de produits d’un détaillant.</span><span class="sxs-lookup"><span data-stu-id="f29be-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="f29be-108">Les recommandations « acheter des descriptions similaires » sont disponibles dans les expériences de point de vente (PDV) et d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="f29be-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="f29be-109">Exemple de scénarios</span><span class="sxs-lookup"><span data-stu-id="f29be-109">Example scenarios</span></span>

<span data-ttu-id="f29be-110">Les exemples de scénarios suivants illustrent les types de recommandations que la fonctionnalité « acheter des descriptions similaires » peut fournir :</span><span class="sxs-lookup"><span data-stu-id="f29be-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="f29be-111">Un client regarde une paire de lunettes à monture rétro et reçoit un ensemble de recommandations pour d'autres lunettes avec un design similaire, dans le contexte du secteur du détaillant.</span><span class="sxs-lookup"><span data-stu-id="f29be-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="f29be-112">Un client utilise les recommandations de la fonctionnalité « acheter des descriptions similaires » pour découvrir des saveurs de café similaires à une saveur qu'il avait précédemment achetée chez le détaillant.</span><span class="sxs-lookup"><span data-stu-id="f29be-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="f29be-113">Définir les recommandations « acheter des descriptions similaires »</span><span class="sxs-lookup"><span data-stu-id="f29be-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="f29be-114">Les recommandations de produit sont uniquement prises en charge pour les utilisateurs de Commerce qui ont migré leur stockage vers Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="f29be-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f29be-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f29be-115">Prerequisites</span></span>

<span data-ttu-id="f29be-116">Avant de pouvoir montrer aux clients des recommandations de type « acheter des descriptions similaires », vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="f29be-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="f29be-117">[Activer les recommandations de produits](enable-product-recommendations.md) au siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="f29be-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="f29be-118">Confirmez que le serveur multimédia prend en charge les appels HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f29be-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="f29be-119">Activer la fonctionnalité de recommandations « acheter des descriptions similaires »</span><span class="sxs-lookup"><span data-stu-id="f29be-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="f29be-120">Pour activer la fonctionnalité de recommandations « acheter des descriptions similaires » dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f29be-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="f29be-121">Dans l'espace de travail **Gestion des fonctionnalités**, dans la liste des fonctionnalités disponibles, recherchez et sélectionnez **Acheter des descriptions similaires**.</span><span class="sxs-lookup"><span data-stu-id="f29be-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="f29be-122">Dans le volet droit, sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="f29be-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="f29be-123">Une fois la fonctionnalité activée, le système commence à générer des listes de recommandations de produits.</span><span class="sxs-lookup"><span data-stu-id="f29be-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="f29be-124">Il peut falloir jusqu'à une journée avant que les listes soient disponibles et visibles en ligne et sur les terminaux de PDV.</span><span class="sxs-lookup"><span data-stu-id="f29be-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="f29be-125">Si vous désactivez cette fonctionnalité, les autres types de recommandations de produits ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="f29be-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="f29be-126">Pour plus d’informations sur les recommandations de produit, voir [Vue d’ensemble des recommandations de produits](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="f29be-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="f29be-127">Ajouter un bouton Acheter des descriptions similaires aux pages de détails du produit</span><span class="sxs-lookup"><span data-stu-id="f29be-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="f29be-128">Une fois que vous avez activé la fonctionnalité de recommandations « acheter des descriptions similaires » dans Commerce Headquarters, vous pouvez ajouter un bouton **Acheter des descriptions similaires** dans la zone d’achat de n’importe quelle page de détails de produit (PDP).</span><span class="sxs-lookup"><span data-stu-id="f29be-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="f29be-129">Un client qui clique sur ce bouton est redirigé vers une page dédiée **Acheter des descriptions similaires** qui affiche des produits visuellement similaires.</span><span class="sxs-lookup"><span data-stu-id="f29be-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="f29be-130">Le client peut ensuite utiliser des sélecteurs pour filtrer davantage les produits.</span><span class="sxs-lookup"><span data-stu-id="f29be-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="f29be-131">Pour ajouter un bouton **Acheter des descriptions similaires** à une PDP à l’aide du générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f29be-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f29be-132">Ouvrez une page de générateur de site existante qui contient un module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="f29be-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="f29be-133">Dans le volet de navigation de gauche, sélectionnez le module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="f29be-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="f29be-134">Dans le volet de navigation de droite, cochez la case **Activer le lien Acheter des descriptions similaires**.</span><span class="sxs-lookup"><span data-stu-id="f29be-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="f29be-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f29be-135">Select **Save**.</span></span>
1. <span data-ttu-id="f29be-136">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="f29be-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="f29be-137">Une fois la page publiée, la PDP comprendra un bouton **Achetez des descriptions similaires**.</span><span class="sxs-lookup"><span data-stu-id="f29be-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="f29be-138">L’illustration suivante montre la case à cocher **Activer le lien Acheter des descriptions similaires** et le bouton **Acheter des descriptions similaires** sur un exemple de PDP dans le générateur de site.</span><span class="sxs-lookup"><span data-stu-id="f29be-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![Case à cocher Activer le lien Acheter des descriptions similaires et bouton Acheter des descriptions similaires sur une PDP dans le générateur de site](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="f29be-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f29be-140">Additional resources</span></span>

[<span data-ttu-id="f29be-141">Vue d’ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f29be-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="f29be-142">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f29be-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="f29be-143">Activer les recommandations de produit</span><span class="sxs-lookup"><span data-stu-id="f29be-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="f29be-144">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="f29be-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="f29be-145">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="f29be-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="f29be-146">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="f29be-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="f29be-147">FAQ sur les recommandations de produit</span><span class="sxs-lookup"><span data-stu-id="f29be-147">Product recommendations FAQ</span></span>](faq-recommendations.md)
