---
title: Vue d'ensemble des recommandations produit
description: Cette rubrique fournit des informations générales sur les recommandations de produit. Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent, et même les produits qu'il n'ont pas initialement prévu à acheter.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412141"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="7eb3d-104">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="7eb3d-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7eb3d-105">Microsoft Dynamics 365 Commerce peut être utilisé pour afficher les recommandations de produit sur le site web de commerce électronique et l'appareil du point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="7eb3d-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="7eb3d-106">Les recommandations de produit sont des articles qu'un client peut être intéressé dans.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="7eb3d-107">Les recommandations sont basés sur les tendances d'achat d'autres clients dans les magasins en ligne et traditionnels.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="7eb3d-108">Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent tout en ayant une expérience qui les sert bien.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="7eb3d-109">La vente croisée et la vente incitative peuvent même être utilisées pour aider les clients à trouver des produits supplémentaires qu'ils n'avaient pas initialement prévu à acheter.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="7eb3d-110">Lorsque des recommandations sont utilisées pour aider à la découverte de produit, elles peuvent créer des opportunités de conversion supplémentaires, aider à augmenter le produit des ventes, et même à améliorer la satisfaction la rétention des clients.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="7eb3d-111">Dans e-Commerce, les recommandations de produit sont optimisées par les technologies de Machine Learning de recommandations Microsoft à une grande échelle.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="7eb3d-112">Service de recommandation</span><span class="sxs-lookup"><span data-stu-id="7eb3d-112">Recommendation service</span></span>

<span data-ttu-id="7eb3d-113">Le service de recommandations des produits utilise les technologies d'intelligence artificielle et d'apprentissage automatique (AI-ML) de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="7eb3d-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="7eb3d-114">Les données au format requis par le service de recommandation sont extraites de la base de données opérationnelle de Commerce et envoyées à Azure Data Lake Storage ou au magasin Entité.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="7eb3d-115">Le service de recommandations utilise les données stockées pour former des modèles de recommandation pour les listes **D'autres client aiment également**, **Fréquemment achetés ensemble**, **Nouveau**, **Meilleure vente**, et **Tendance**.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="7eb3d-116">Scénarios</span><span class="sxs-lookup"><span data-stu-id="7eb3d-116">Scenarios</span></span>

<span data-ttu-id="7eb3d-117">Les recommandations de produit sont disponibles pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="7eb3d-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="7eb3d-118">**Sur n'importe quelle page de magasin pour naviguer ou page de destination dans le commerce électronique :** Si les clients ou les vendeurs visitent une page de magasin, le moteur de recommandations peut proposer des produits dans les listes **Nouveau**, **Meilleure vente**, et **Tendance**.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="7eb3d-119">**Sur la page de détails de produit :** Si les clients ou les vendeurs visitent une page **Détails de produit**, le moteur de recommandations suggère des articles supplémentaires qui sont susceptibles d'être achetés.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="7eb3d-120">Ces articles figurent dans la liste **D'autres clients aiment également**.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="7eb3d-121">**Sur la page de transaction ou la page d'extraction :** Le moteur de recommandations suggère des articles, selon la liste entière d'articles dans le panier.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="7eb3d-122">Ces articles figurent dans la liste **Fréquemment achetés ensemble**.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="7eb3d-123">**Recommandations personnalisées :** les spécialistes du marketing peuvent fournir aux clients connectés une liste personnalisée **Nos choix pour vous**, en plus des nouvelles fonctionnalités qui permettent de personnaliser les scénarios de liste existants en fonction du client.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="7eb3d-124">Pour en savoir plus, voir [Activer les recommandations personnalisées.](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="7eb3d-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="7eb3d-125">Types de recommandations produit</span><span class="sxs-lookup"><span data-stu-id="7eb3d-125">Types of product recommendations</span></span>

<span data-ttu-id="7eb3d-126">Le tableau suivant décrit les différents types de recommandations de produits automatisés disponibles pour les détaillants à mettre en œuvre dans leur solution Dynamics 365 Commerce via le [module de collecte de produits](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7eb3d-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="7eb3d-127">Les détaillants peuvent également afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="7eb3d-128">Module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="7eb3d-128">Product collection module</span></span>  | <span data-ttu-id="7eb3d-129">Type</span><span class="sxs-lookup"><span data-stu-id="7eb3d-129">Type</span></span> | <span data-ttu-id="7eb3d-130">Description</span><span class="sxs-lookup"><span data-stu-id="7eb3d-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="7eb3d-131">Nouveau</span><span class="sxs-lookup"><span data-stu-id="7eb3d-131">New</span></span>                        | <span data-ttu-id="7eb3d-132">Algorithmique</span><span class="sxs-lookup"><span data-stu-id="7eb3d-132">Algorithmic</span></span> | <span data-ttu-id="7eb3d-133">Ce module affiche une liste des nouveaux produits qui ont été mis en correspondance récemment avec les canaux et les catalogues.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="7eb3d-134">Meilleures ventes</span><span class="sxs-lookup"><span data-stu-id="7eb3d-134">Best selling</span></span>               | <span data-ttu-id="7eb3d-135">Algorithmique</span><span class="sxs-lookup"><span data-stu-id="7eb3d-135">Algorithmic</span></span> | <span data-ttu-id="7eb3d-136">Ce module affiche une liste des produits qui sont classés selon le nombre de ventes le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="7eb3d-137">Tendances</span><span class="sxs-lookup"><span data-stu-id="7eb3d-137">Trending</span></span>                   | <span data-ttu-id="7eb3d-138">Algorithmique</span><span class="sxs-lookup"><span data-stu-id="7eb3d-138">Algorithmic</span></span> | <span data-ttu-id="7eb3d-139">Ce module affiche une liste des produits les plus performants pendant une période donnée, classés selon le plus grand nombre de ventes.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="7eb3d-140">Fréquemment achetés ensemble</span><span class="sxs-lookup"><span data-stu-id="7eb3d-140">Frequently bought together</span></span> | <span data-ttu-id="7eb3d-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="7eb3d-141">AI-ML</span></span> | <span data-ttu-id="7eb3d-142">Ce module recommande une liste de produits qui sont couramment achetés avec le contenu du panier actuel du consommateur.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="7eb3d-143">Les personnes aiment également</span><span class="sxs-lookup"><span data-stu-id="7eb3d-143">People also like</span></span>           | <span data-ttu-id="7eb3d-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="7eb3d-144">AI-ML</span></span> | <span data-ttu-id="7eb3d-145">Ce module recommande des produits pour un produit initial donné en fonction des habitudes d'achat des consommateurs.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="7eb3d-146">Nos choix pour vous</span><span class="sxs-lookup"><span data-stu-id="7eb3d-146">Picks for you</span></span>              | <span data-ttu-id="7eb3d-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="7eb3d-147">AI-ML</span></span> | <span data-ttu-id="7eb3d-148">Ce module recommande une liste personnalisée de produits en fonction des modèles d'achat de l'utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="7eb3d-149">Pour un utilisateur invité, cette liste sera réduite.</span><span class="sxs-lookup"><span data-stu-id="7eb3d-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="7eb3d-150">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7eb3d-150">Additional resources</span></span>

[<span data-ttu-id="7eb3d-151">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7eb3d-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="7eb3d-152">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="7eb3d-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="7eb3d-153">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="7eb3d-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="7eb3d-154">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="7eb3d-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="7eb3d-155">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="7eb3d-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="7eb3d-156">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="7eb3d-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="7eb3d-157">Ajouter des recommandations à l’écran de transaction</span><span class="sxs-lookup"><span data-stu-id="7eb3d-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="7eb3d-158">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="7eb3d-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="7eb3d-159">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="7eb3d-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="7eb3d-160">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="7eb3d-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="7eb3d-161">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="7eb3d-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
