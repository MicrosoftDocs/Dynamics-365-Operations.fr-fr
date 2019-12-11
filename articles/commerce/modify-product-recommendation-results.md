---
title: Gérer les résultats de recommandation produit fondées sur l'IA et le ML
description: Cette rubrique explique comment personnaliser les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770068"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="094ff-103">Gérer les résultats de recommandation produit fondées sur l'IA et le ML</span><span class="sxs-lookup"><span data-stu-id="094ff-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="094ff-104">Cette rubrique explique comment personnaliser les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="094ff-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="094ff-105">Après avoir activé les recommandations de produit, les paramètres par défaut prennent effet ; ces paramètres peuvent servir pour de nombreux besoins.</span><span class="sxs-lookup"><span data-stu-id="094ff-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="094ff-106">Il est recommandé prévoir du temps pour évaluer si les résultats correspondent au mouvement de vente de produits.</span><span class="sxs-lookup"><span data-stu-id="094ff-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="094ff-107">Nous vous conseillons d'évaluer les résultats quelques jours avant de modifier les paramètres si nécessaire avant de tester à nouveau.</span><span class="sxs-lookup"><span data-stu-id="094ff-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="094ff-108">Compréhension des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="094ff-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="094ff-109">Avant de modifier les paramètres, renseignez-vous sur la façon dont ils vont affecter les résultats ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="094ff-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="094ff-110">Liste des produits tendance</span><span class="sxs-lookup"><span data-stu-id="094ff-110">Trending product list</span></span>

<span data-ttu-id="094ff-111">La liste de produits **Tendance** a deux paramètres qui peuvent être modifiés : ![Exemple de paramètres par défaut de la liste Tendance](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="094ff-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="094ff-112">**Inclure les nouveaux produits des X dernier jours** - Les produits qui ont été ajoutés au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour sélectionner des candidats de produit.</span><span class="sxs-lookup"><span data-stu-id="094ff-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="094ff-113">La valeur par défaut dans l'image suggère que les produits datant de 180 jours peuvent être utilisés dans la liste des produits tendance.</span><span class="sxs-lookup"><span data-stu-id="094ff-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="094ff-114">**Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="094ff-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="094ff-115">La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits tendance.</span><span class="sxs-lookup"><span data-stu-id="094ff-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="094ff-116">Liste des meilleures ventes de produits</span><span class="sxs-lookup"><span data-stu-id="094ff-116">Best selling product list</span></span>

<span data-ttu-id="094ff-117">En fonction de votre entreprise, les meilleures ventes peuvent apporter des résultats différents de la tendance, même si elles utilisent les données de transaction pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="094ff-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="094ff-118">Comme les meilleures ventes n'ont aucune limité basée sur une date d'assortiment, les meilleures ventes peut encore mettre des produits plus anciens et très populaires en évidence qui peuvent avoir baissé dans la liste des tendances.</span><span class="sxs-lookup"><span data-stu-id="094ff-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="094ff-119">La liste du produit avec **La meilleure vente** a un paramètre qui peut être modifié :</span><span class="sxs-lookup"><span data-stu-id="094ff-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Exemple de paramètre par défaut de liste de meilleures ventes](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="094ff-121">**Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="094ff-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="094ff-122">La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits les plus vendus.</span><span class="sxs-lookup"><span data-stu-id="094ff-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="094ff-123">Manuellement ajouter ou supprimer des produits des listes de recommandations</span><span class="sxs-lookup"><span data-stu-id="094ff-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="094ff-124">Pour Nouveau, Tendance ou Meilleure vente</span><span class="sxs-lookup"><span data-stu-id="094ff-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="094ff-125">Accédez à **Vente au détail** > **Recommandations de produits** > **Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="094ff-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="094ff-126">Dans la liste des paramètres partagés de vente au détail, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="094ff-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="094ff-127">Sélectionnez la liste à laquelle ajouter ou supprimer des produits.</span><span class="sxs-lookup"><span data-stu-id="094ff-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="094ff-128">Pour ajouter des produits à la table, sélectionnez **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="094ff-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="094ff-129">Dans la colonne Produit, recherchez un produit par **Nom** ou **Numéro de produit.**
![Exemple de la recherche d'un produit sur la nouvelle liste de produits](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="094ff-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="094ff-130">Dans la colonne Type de ligne, sélectionnez l'une des deux options :</span><span class="sxs-lookup"><span data-stu-id="094ff-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="094ff-131">**Inclure** – force un produit au dessus de la liste</span><span class="sxs-lookup"><span data-stu-id="094ff-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="094ff-132">**Exclure** – supprime un produit de la liste qui s'affiche ![Exemple d'Inclure ou Exclure un produit de la nouvelle liste de produits](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="094ff-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="094ff-133">La modification de l'**Ordre d'affichage** modifie l'ordre dans lequel les produits marqués à **Inclure** s'affichent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="094ff-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="094ff-134">Si deux produits ont la même valeur d'**ordre d'affichage**, l'ordre final de ces deux résultats peut différer du back-office.</span><span class="sxs-lookup"><span data-stu-id="094ff-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="094ff-135">Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="094ff-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="094ff-136">Pour D'autres client aiment également ou Fréquemment achetés ensemble</span><span class="sxs-lookup"><span data-stu-id="094ff-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="094ff-137">Dans le contexte des listes **Fréquemment achetés ensemble** ou **D'autres clients aiment également**, le Machine Learning permet d'analyser les modèles d'achat des consommateurs pour recommander des produits liés généralement achetés ensemble pour un seul produit d'origine.</span><span class="sxs-lookup"><span data-stu-id="094ff-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="094ff-138">Un **produit initial** est le produit pour lequel vous voulez générer des résultats.</span><span class="sxs-lookup"><span data-stu-id="094ff-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="094ff-139">Dans le contexte de l'ajustement manuel des listes de recommandations, vous ajoutez ou supprimez des résultats pour ce produit.</span><span class="sxs-lookup"><span data-stu-id="094ff-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="094ff-140">Procédez comme suit pour ajouter ou supprimer manuellement des résultats pour un produit d'origine :</span><span class="sxs-lookup"><span data-stu-id="094ff-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="094ff-141">Sélectionnez le **Produit d'origine**.</span><span class="sxs-lookup"><span data-stu-id="094ff-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="094ff-142">Dans la colonne **Produit**, recherchez un produit par **Nom** ou **Numéro de produit.**
![Exemple de la recherche d'un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="094ff-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="094ff-143">Dans la colonne **Type de ligne**, sélectionnez l'une des deux options :</span><span class="sxs-lookup"><span data-stu-id="094ff-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="094ff-144">**Inclure** – force un produit au dessus de la liste</span><span class="sxs-lookup"><span data-stu-id="094ff-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="094ff-145">**Exclure** – supprime un produit de la liste qui s'affiche</span><span class="sxs-lookup"><span data-stu-id="094ff-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="094ff-146">![Exemple de Inclure ou Exclure un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="094ff-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="094ff-147">Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez Supprimer.</span><span class="sxs-lookup"><span data-stu-id="094ff-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="094ff-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="094ff-148">Additional resources</span></span>

[<span data-ttu-id="094ff-149">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="094ff-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="094ff-150">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="094ff-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="094ff-151">Ajouter des listes de recommandation produit aux pages</span><span class="sxs-lookup"><span data-stu-id="094ff-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
