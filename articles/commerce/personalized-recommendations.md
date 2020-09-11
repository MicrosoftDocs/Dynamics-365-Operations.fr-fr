---
title: Activer les recommandations de produit personnalisées
description: Cette rubrique explique comment proposer des recommandations de produit personnalisées aux clients dans Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
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
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8a61ef0720839d371701f2f0a1fdec7e85a5feb7
ms.sourcegitcommit: d3b970c3b93d8be12886b1c5a6bf91f0b33726dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "3700864"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="79e13-103">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="79e13-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="79e13-104">Cette rubrique explique comment proposer des recommandations de produit personnalisées aux clients dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="79e13-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="79e13-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="79e13-105">Overview</span></span>

<span data-ttu-id="79e13-106">Dans Dynamics 365 Commerce, les détaillants peuvent proposer des recommandations de produit personnalisées (également appelées personnalisation).</span><span class="sxs-lookup"><span data-stu-id="79e13-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="79e13-107">Ainsi, des recommandations personnalisées peuvent être intégrées dans l’expérience client en ligne et au point de vente (PDV).</span><span class="sxs-lookup"><span data-stu-id="79e13-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="79e13-108">Si la fonctionnalité de personnalisation est activée, le système peut associer les informations d’achat et de produit d’un utilisateur pour générer des recommandations de produit individualisées.</span><span class="sxs-lookup"><span data-stu-id="79e13-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="79e13-109">Conditions préalables à la personnalisation</span><span class="sxs-lookup"><span data-stu-id="79e13-109">Personalization prerequisites</span></span>

<span data-ttu-id="79e13-110">Avant de proposer des recommandations de produit personnalisées aux clients, notez que les recommandations de produit ne sont prises en charge que pour les utilisateurs Commerce qui ont migré leur stockage vers Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="79e13-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="79e13-111">Pour que les clients puissent recevoir les recommandations de produit personnalisées, les détaillants doivent [activer les recommandations de produit](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="79e13-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79e13-112">En activant les recommandations de produit, vous activez également la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="79e13-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="79e13-113">Cependant, si vous désactivez la personnalisation, vous ne désactivez pas les autres types de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="79e13-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="79e13-114">Pour plus d’informations sur les recommandation de produit, voir [Vue d’ensemble des recommandations de produit](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="79e13-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="79e13-115">Activer la personnalisation</span><span class="sxs-lookup"><span data-stu-id="79e13-115">Turn on personalization</span></span>

<span data-ttu-id="79e13-116">Pour activer la personnalisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="79e13-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="79e13-117">Au siège de Commerce, recherchez **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="79e13-117">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="79e13-118">Sélectionnez **Tout** pour voir une liste des fonctionnalités disponibles.</span><span class="sxs-lookup"><span data-stu-id="79e13-118">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="79e13-119">Dans la zone de recherche, saisissez **Recommandations**.</span><span class="sxs-lookup"><span data-stu-id="79e13-119">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="79e13-120">Sélectionnez la fonctionnalité **Recommandations de produit personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="79e13-120">Select the **Personalized product recommendations** feature.</span></span>
1. <span data-ttu-id="79e13-121">Dans le volet des propriétés **Recommandations de produit personnalisées**, sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="79e13-121">In the **Personalized product recommendations** properties pane, select **Enable now**.</span></span>

![Activation de la personnalisation](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> <span data-ttu-id="79e13-123">Lorsque vous activez la personnalisation, la génération des listes de recommandations de produit personnalisées démarre.</span><span class="sxs-lookup"><span data-stu-id="79e13-123">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="79e13-124">Un jour peut être nécessaire avant que ces listes soient disponibles et visibles en ligne et au point de vente.</span><span class="sxs-lookup"><span data-stu-id="79e13-124">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="79e13-125">Listes personnalisées</span><span class="sxs-lookup"><span data-stu-id="79e13-125">Personalized lists</span></span>

<span data-ttu-id="79e13-126">Outre l’autorisation de la personnalisation des listes générées par machine existantes, le service des recommandations permet de personnaliser l’expérience de découverte des produits en ligne et au point de vente.</span><span class="sxs-lookup"><span data-stu-id="79e13-126">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="79e13-127">Après l’activation de la personnalisation, les détaillants peuvent montrer aux acheteurs des listes personnalisées « Nos choix pour vous » en ligne ou des listes « Recommandé pour le client » sur les terminaux de PDV.</span><span class="sxs-lookup"><span data-stu-id="79e13-127">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="79e13-128">De plus, les détaillants peuvent appliquer la personnalisation aux listes de recommandations de produit existantes et fournir des expériences de désactivation du Règlement général sur la protection des données (RGPD) aux utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="79e13-128">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="79e13-129">Si vous désactivez la personnalisation, vous désactivez également ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="79e13-129">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="79e13-130">Listes « Nos choix pour vous » en ligne</span><span class="sxs-lookup"><span data-stu-id="79e13-130">Online "Picks for you" lists</span></span>

<span data-ttu-id="79e13-131">Une liste « Nos choix pour vous » est une liste d’apprentissage machine basée sur l’intelligence artificielle (AI-ML) qui communique à un utilisateur authentifié une liste personnalisée de produits suggérés.</span><span class="sxs-lookup"><span data-stu-id="79e13-131">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="79e13-132">Cette liste est basée sur l’historique d’achat omnicanal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="79e13-132">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="79e13-133">Les recommandations personnalisées sont mises à jour dynamiquement à mesure que l’utilisateur effectue plus d’achats.</span><span class="sxs-lookup"><span data-stu-id="79e13-133">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="79e13-134">Ce type de liste prend également en charge le filtrage par catégorie, afin que les détaillants puissent afficher les meilleurs choix, en fonction des hiérarchies de navigation.</span><span class="sxs-lookup"><span data-stu-id="79e13-134">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="79e13-135">Pour pouvoir afficher la liste « Nos choix pour vous » sur une page de commerce électronique, les exigences utilisateur suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="79e13-135">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="79e13-136">L’utilisateur doit être connecté.</span><span class="sxs-lookup"><span data-stu-id="79e13-136">Users must be signed in.</span></span> <span data-ttu-id="79e13-137">Les utilisateurs anonymes n’affichent pas les recommandations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="79e13-137">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="79e13-138">L’utilisateur doit avoir au moins un achat sur le compte.</span><span class="sxs-lookup"><span data-stu-id="79e13-138">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="79e13-139">Les utilisateurs doivent accepter la réception des recommandations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="79e13-139">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="79e13-140">L’illustration suivante donne l’exemple d’une liste « Nos choix pour vous » sur la page d’une boutique en ligne.</span><span class="sxs-lookup"><span data-stu-id="79e13-140">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Listes Nos choix pour vous en ligne](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="79e13-142">Listes « Recommandé pour le client » au point de vente</span><span class="sxs-lookup"><span data-stu-id="79e13-142">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="79e13-143">Pour améliorer leur expérience de clientèle, les détaillants peuvent personnaliser les pages de détails client existantes en ajoutant une liste contextuelle « Recommandé pour le client ».</span><span class="sxs-lookup"><span data-stu-id="79e13-143">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="79e13-144">L’illustration suivante donne l’exemple d’une liste « Recommandé pour le client » sur un terminal de PDV.</span><span class="sxs-lookup"><span data-stu-id="79e13-144">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Listes Recommandé pour le client au point de vente](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="79e13-146">Appliquer la personnalisation aux listes de recommandations existantes</span><span class="sxs-lookup"><span data-stu-id="79e13-146">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="79e13-147">Les détaillants peuvent appliquer la personnalisation aux listes de recommandations existantes, telles que « Nouveau », « Tendance », « Meilleure vente », « D’autres clients aiment également » et « Fréquemment achetés ensemble ».</span><span class="sxs-lookup"><span data-stu-id="79e13-147">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="79e13-148">Lorsque la personnalisation est appliquée aux listes existantes, les articles précédemment achetés par un utilisateur connecté sont supprimés de ces listes.</span><span class="sxs-lookup"><span data-stu-id="79e13-148">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="79e13-149">Pour les utilisateurs anonymes et les utilisateurs qui ont refusé de recevoir les recommandations personnalisées, les versions par défaut des listes existantes sont affichées.</span><span class="sxs-lookup"><span data-stu-id="79e13-149">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="79e13-150">Par conséquent, les détaillants n’ont pas à gérer manuellement des expériences de page distinctes.</span><span class="sxs-lookup"><span data-stu-id="79e13-150">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="79e13-151">Par exemple, un utilisateur connecté a déjà acheté la montre noire et les bottes de travail marron qui apparaissent dans la liste « Tendance - Par défaut » dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="79e13-151">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="79e13-152">Par conséquent, l’utilisateur affiche de nouveaux produits en remplacement de ces produits, comme indiqué dans la liste « Tendance - Personnalisée ».</span><span class="sxs-lookup"><span data-stu-id="79e13-152">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Application de la personnalisation](./media/applypersonalization.png)

<span data-ttu-id="79e13-154">Pour appliquer la personnalisation à une liste de recommandations existante dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="79e13-154">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="79e13-155">Ouvrez une page de générateur de site existante qui contient un module de collecte de produits.</span><span class="sxs-lookup"><span data-stu-id="79e13-155">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="79e13-156">Dans le volet de navigation de gauche, sélectionnez le module de collecte de produits.</span><span class="sxs-lookup"><span data-stu-id="79e13-156">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="79e13-157">Dans le volet de navigation de droite, sous **Produits**, sélectionnez la liste.</span><span class="sxs-lookup"><span data-stu-id="79e13-157">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="79e13-158">Dans la boîte de dialogue **Sélectionner la configuration de liste de produit**, sous **Type**, sélectionnez le type de liste.</span><span class="sxs-lookup"><span data-stu-id="79e13-158">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="79e13-159">Cochez la case **Appliquer la personnalisation**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="79e13-159">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Application de la personnalisation à une liste de tendances](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="79e13-161">Enregistrez la page, terminez de la modifier, puis publiez-la.</span><span class="sxs-lookup"><span data-stu-id="79e13-161">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="79e13-162">Après la publication de la page, les utilisateurs connectés affichent les listes de tendances personnalisées.</span><span class="sxs-lookup"><span data-stu-id="79e13-162">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79e13-163">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="79e13-163">Additional resources</span></span>

[<span data-ttu-id="79e13-164">Vue d’ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="79e13-164">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="79e13-165">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="79e13-165">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="79e13-166">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="79e13-166">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="79e13-167">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="79e13-167">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="79e13-168">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="79e13-168">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="79e13-169">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="79e13-169">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="79e13-170">Ajouter des recommandations à l’écran de transaction</span><span class="sxs-lookup"><span data-stu-id="79e13-170">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="79e13-171">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="79e13-171">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="79e13-172">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="79e13-172">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="79e13-173">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="79e13-173">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="79e13-174">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="79e13-174">Product recommendations FAQ</span></span>](faq-recommendations.md)
