---
title: Vue d'ensemble des recommandations produit
description: Cette rubrique fournit des informations générales sur les recommandations de produit. Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent, et même les produits qu'il n'ont pas initialement prévu à acheter.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: e249c7d450510a3a9a33158e9e1c33f832a1f91c
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024977"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="f34ed-104">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f34ed-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f34ed-105">Microsoft Dynamics 365 Commerce peut être utilisé pour afficher les recommandations de produit sur le site web de commerce électronique et l'appareil du point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="f34ed-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="f34ed-106">Les recommandations de produit sont des articles qu'un client peut être intéressé dans.</span><span class="sxs-lookup"><span data-stu-id="f34ed-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="f34ed-107">Les recommandations sont basés sur les tendances d'achat d'autres clients dans les magasins en ligne et traditionnels.</span><span class="sxs-lookup"><span data-stu-id="f34ed-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="f34ed-108">Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent tout en ayant une expérience qui les sert bien.</span><span class="sxs-lookup"><span data-stu-id="f34ed-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="f34ed-109">La vente croisée et la vente incitative peuvent même être utilisées pour aider les clients à trouver des produits supplémentaires qu'ils n'avaient pas initialement prévu à acheter.</span><span class="sxs-lookup"><span data-stu-id="f34ed-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="f34ed-110">Lorsque des recommandations sont utilisées pour aider à la découverte de produit, elles peuvent créer des opportunités de conversion supplémentaires, aider à augmenter le produit des ventes, et même à améliorer la satisfaction la rétention des clients.</span><span class="sxs-lookup"><span data-stu-id="f34ed-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="f34ed-111">Dans Commerce, les recommandations de produit sont optimisées par les technologies de Machine Learning de recommandations Microsoft à une grande échelle.</span><span class="sxs-lookup"><span data-stu-id="f34ed-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="f34ed-112">Scénarios</span><span class="sxs-lookup"><span data-stu-id="f34ed-112">Scenarios</span></span>

<span data-ttu-id="f34ed-113">Les recommandations de produit sont disponibles pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="f34ed-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="f34ed-114">**Sur n'importe quelle page de magasin pour naviguer ou page de destination dans le commerce électronique :** Si les clients ou les vendeurs visitent une page de magasin, le moteur de recommandations peut proposer des produits dans les listes **Nouveau**, **Meilleure vente**, et **Tendance**.</span><span class="sxs-lookup"><span data-stu-id="f34ed-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="f34ed-115">**Sur la page de détails de produit :** Si les clients ou les vendeurs visitent une page **Détails de produit**, le moteur de recommandations suggère des articles supplémentaires qui sont susceptibles d'être achetés.</span><span class="sxs-lookup"><span data-stu-id="f34ed-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="f34ed-116">Ces articles figurent dans la liste **D'autres clients aiment également**.</span><span class="sxs-lookup"><span data-stu-id="f34ed-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="f34ed-117">**Sur la page de transaction ou la page d'extraction :** Le moteur de recommandations suggère des articles, selon la liste entière d'articles dans le panier.</span><span class="sxs-lookup"><span data-stu-id="f34ed-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="f34ed-118">Ces articles figurent dans la liste **Fréquemment achetés ensemble**.</span><span class="sxs-lookup"><span data-stu-id="f34ed-118">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="f34ed-119">**Recommandations personnalisées :** les spécialistes du marketing peuvent fournir aux clients connectés une liste personnalisée **Nos choix pour vous**, en plus des nouvelles fonctionnalités qui permettent de personnaliser les scénarios de liste existants en fonction du client.</span><span class="sxs-lookup"><span data-stu-id="f34ed-119">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="f34ed-120">Pour en savoir plus, consultez la documentation sur les fonctionnalités : [Activer les recommandations personnalisées.](personalized-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="f34ed-120">To learn more, please see the feature documenation: [enable personalized recommedations.](personalized-recommendations.md)</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="f34ed-121">Service de recommandation</span><span class="sxs-lookup"><span data-stu-id="f34ed-121">Recommendation service</span></span>

<span data-ttu-id="f34ed-122">Les recommandations de produit utilisent les technologies de Machine Learning de recommandations de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="f34ed-122">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="f34ed-123">Les données au format requis par le service de recommandation sont extraites de la base de données opérationnelle de Commerce et envoyées au magasin Entité.</span><span class="sxs-lookup"><span data-stu-id="f34ed-123">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="f34ed-124">Le service de recommandation utilise les données pour former des modèles de recommandation pour les listes **D'autres client aiment également**, **Fréquemment achetés ensemble**, **Nouveau**, **Meilleure vente**, et **Tendance**.</span><span class="sxs-lookup"><span data-stu-id="f34ed-124">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f34ed-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f34ed-125">Additional resources</span></span>

[<span data-ttu-id="f34ed-126">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="f34ed-126">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="f34ed-127">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="f34ed-127">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="f34ed-128">Vue d'ensemble du module de collecte de produits</span><span class="sxs-lookup"><span data-stu-id="f34ed-128">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="f34ed-129">Créer des listes de recommandations produit éditées</span><span class="sxs-lookup"><span data-stu-id="f34ed-129">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="f34ed-130">Gérer les résultats de recommandation produit fondées sur l'IA et le ML</span><span class="sxs-lookup"><span data-stu-id="f34ed-130">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="f34ed-131">Ajouter des listes de recommandation produit aux pages</span><span class="sxs-lookup"><span data-stu-id="f34ed-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
