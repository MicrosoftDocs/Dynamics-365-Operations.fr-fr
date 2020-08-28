---
title: Activer les recommandations « acheter des aspects similaires »
description: Cette rubrique décrit comment activer les recommandations de produits « Acheter des aspects similaires » dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2e57965a1073982a7b6c34b79dbf6e5b90d7ee30
ms.sourcegitcommit: 15c68822f4d412bfc609be31b3702f18c81ea0bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3666306"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="6869c-103">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="6869c-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6869c-104">Cette rubrique décrit comment activer les recommandations de produits « Acheter des aspects similaires » dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6869c-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6869c-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6869c-105">Overview</span></span>

<span data-ttu-id="6869c-106">La fonctionnalité de recommandations « Acheter des aspects similaires » dans Dynamics 365 Commerce utilise la puissance de l’intelligence artificielle et du Machine Learning (IA-ML) pour fournir des recommandations pour des produits visuellement similaires aux clients.</span><span class="sxs-lookup"><span data-stu-id="6869c-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="6869c-107">En mettant à disposition des recommandations de type « acheter des aspects similaires » pour tous les canaux de vente au détail dans Commerce, les détaillants peuvent accroître la satisfaction de leurs clients en aidant les clients à trouver facilement ce qu’ils veulent.</span><span class="sxs-lookup"><span data-stu-id="6869c-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="6869c-108">La fonctionnalité de recommandations « Acheter des aspects similaires » utilise des images de produits de variantes de produits initiaux pour rechercher et recommander des produits visuellement similaires dans le catalogue de produits d’un détaillant.</span><span class="sxs-lookup"><span data-stu-id="6869c-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="6869c-109">Les recommandations « Acheter des aspects similaires » sont disponibles dans les expériences de point de vente (PDV) et d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="6869c-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="6869c-110">Exemple de scénarios</span><span class="sxs-lookup"><span data-stu-id="6869c-110">Example scenarios</span></span>

- <span data-ttu-id="6869c-111">Un client regarde un pull rayé noir et reçoit une recommandation pour un pull similaire en rouge.</span><span class="sxs-lookup"><span data-stu-id="6869c-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="6869c-112">Le client sélectionne le produit recommandé au lieu du produit initialement consulté, puis reçoit des recommandations pour des produits similaires en rouge.</span><span class="sxs-lookup"><span data-stu-id="6869c-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="6869c-113">Un client utilise les recommandations « Acheter des aspects similaires » pour découvrir des boucles d’oreilles assorties à une bague qu’il souhaite acheter.</span><span class="sxs-lookup"><span data-stu-id="6869c-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="6869c-114">Activer les recommandations « Acheter des aspects similaires » au siège Commerce</span><span class="sxs-lookup"><span data-stu-id="6869c-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="6869c-115">Les recommandations de produit sont uniquement prises en charge pour les utilisateurs de Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="6869c-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6869c-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6869c-116">Prerequisites</span></span>

<span data-ttu-id="6869c-117">Avant que les détaillants puissent commencer à montrer aux clients des recommandations « Acheter des aspects similaires », il y a deux étapes préalables :</span><span class="sxs-lookup"><span data-stu-id="6869c-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="6869c-118">[Activer les recommandations de produits](enable-product-recommendations.md) au siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="6869c-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="6869c-119">Confirmez que le serveur multimédia prend en charge les appels HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6869c-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="6869c-120">Pour que le moteur de recommandations accède aux images des produits, les détaillants doivent générer les URL des produits.</span><span class="sxs-lookup"><span data-stu-id="6869c-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="6869c-121">Pour générer des URL de produits dans le siège Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6869c-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6869c-122">Accédez à **Images de produits**.</span><span class="sxs-lookup"><span data-stu-id="6869c-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="6869c-123">Dans le volet Actions, sélectionnez **Définir le modèle de support**.</span><span class="sxs-lookup"><span data-stu-id="6869c-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="6869c-124">Dans le volet des propriétés **Définir le modèle de support**, sous **URL de support**, sélectionnez **Générer des URL**.</span><span class="sxs-lookup"><span data-stu-id="6869c-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="6869c-125">Lorsque vous activez la fonction de recommandations « Acheter des aspects similaires », le processus de génération de listes de recommandations de produits commence.</span><span class="sxs-lookup"><span data-stu-id="6869c-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="6869c-126">Un jour peut être nécessaire avant que ces listes soient disponibles et visibles en ligne et aux terminaux de PDV.</span><span class="sxs-lookup"><span data-stu-id="6869c-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="6869c-127">Pour activer la fonctionnalité de recommandations « Acheter des aspects similaires » au siège Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6869c-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6869c-128">Accédez à **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="6869c-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="6869c-129">Dans la liste des fonctionnalités disponibles, recherchez et sélectionnez **Achetez des aspects similaires**.</span><span class="sxs-lookup"><span data-stu-id="6869c-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="6869c-130">Dans le volet droit, sélectionnez **Activer** pour activer le service.</span><span class="sxs-lookup"><span data-stu-id="6869c-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="6869c-131">L’illustration suivante montre la fonctionnalité **Acheter des aspects similaires** sur la page **Gestion des fonctionnalités** au siège Commerce.</span><span class="sxs-lookup"><span data-stu-id="6869c-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![La fonctionnalité Acheter des aspects similaires sur la page Gestion des fonctionnalités du siège Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="6869c-133">Une fois les tâches précédentes terminées, les terminaux de PDV sont automatiquement améliorés avec un volet **Acheter des produits similaires**.</span><span class="sxs-lookup"><span data-stu-id="6869c-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="6869c-134">En sélectionnant **En savoir plus**, les utilisateurs de terminaux de PDV peuvent être redirigés vers une page dédiée à la page « Acheter des aspects similaires » qui peut être filtrée davantage.</span><span class="sxs-lookup"><span data-stu-id="6869c-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="6869c-135">Si vous désactivez la fonctionnalité de recommandations « Acheter des aspects similaires », aucun autre type de recommandation de produit n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="6869c-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="6869c-136">Pour plus d’informations sur les recommandation de produit, voir [Vue d’ensemble des recommandations de produits](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6869c-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="6869c-137">Ajouter un bouton Acheter des aspects similaires aux pages de détails du produit à l’aide du générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="6869c-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="6869c-138">Une fois que vous avez activé la fonctionnalité de recommandations « Acheter des aspects similaires » dans le siège Commerce, une option dans le générateur de site Commerce permet aux détaillants d’ajouter un bouton **Achetez des aspects similaires** dans la zone d’achat de n’importe quelle page de détails de produit (PDP).</span><span class="sxs-lookup"><span data-stu-id="6869c-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="6869c-139">Un client qui clique sur ce bouton est redirigé vers une page dédiée « Acheter des aspects similaires » qui renvoie des produits visuellement similaires.</span><span class="sxs-lookup"><span data-stu-id="6869c-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="6869c-140">Là, le client peut utiliser des sélecteurs pour filtrer davantage les produits.</span><span class="sxs-lookup"><span data-stu-id="6869c-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="6869c-141">Pour ajouter un bouton **Acheter des aspects similaires** à une PDP à l’aide du générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6869c-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6869c-142">Ouvrez une page de générateur de site existante qui contient un module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="6869c-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="6869c-143">Dans le volet de navigation de gauche, sélectionnez le module de zone d’achat.</span><span class="sxs-lookup"><span data-stu-id="6869c-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="6869c-144">Dans le volet de navigation de droite, cochez la case **Activer le lien Acheter des aspects similaires**.</span><span class="sxs-lookup"><span data-stu-id="6869c-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="6869c-145">Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="6869c-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="6869c-146">Une fois la page publiée, la PDP comprendra un bouton **Achetez des aspects similaires**.</span><span class="sxs-lookup"><span data-stu-id="6869c-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="6869c-147">L’illustration suivante montre la case à cocher **Activer le lien Acheter des aspects similaires** et le bouton **Achetez des aspects similaires** sur un exemple de PDP dans le générateur de site.</span><span class="sxs-lookup"><span data-stu-id="6869c-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Case à cocher Activer le lien Acheter des aspects similaires et le bouton Achetez des aspects similaires sur une PDP dans le générateur de site](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="6869c-149">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6869c-149">Additional resources</span></span>

[<span data-ttu-id="6869c-150">Vue d’ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6869c-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6869c-151">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6869c-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6869c-152">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6869c-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6869c-153">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="6869c-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6869c-154">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="6869c-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6869c-155">Ajouter des recommandations à l’écran de transaction</span><span class="sxs-lookup"><span data-stu-id="6869c-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6869c-156">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="6869c-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6869c-157">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="6869c-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6869c-158">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="6869c-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6869c-159">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6869c-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
