---
title: Ajuster les résultats de recommandation produit fondées sur l'IA et le ML
description: Cette rubrique explique comment personnaliser les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b9e370faed7feb0640959a9fcc4b608f18f9ffc1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263944"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="6fce9-103">Ajuster les résultats de recommandation produit fondées sur l'IA et le ML</span><span class="sxs-lookup"><span data-stu-id="6fce9-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6fce9-104">Cette rubrique explique comment ajuster les résultats de recommandation de produit basés sur l'intelligence artificielle et le Machine Learning (IA et ML) votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="6fce9-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="6fce9-105">Après avoir activé les recommandations de produit, les paramètres par défaut prennent effet ; ces paramètres peuvent servir pour de nombreux besoins.</span><span class="sxs-lookup"><span data-stu-id="6fce9-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="6fce9-106">Il est recommandé prévoir du temps pour évaluer si les résultats correspondent au mouvement de vente de produits.</span><span class="sxs-lookup"><span data-stu-id="6fce9-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="6fce9-107">Nous vous conseillons d'évaluer les résultats quelques jours avant de modifier les paramètres si nécessaire avant de tester à nouveau.</span><span class="sxs-lookup"><span data-stu-id="6fce9-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="6fce9-108">Compréhension des paramètres de la liste des recommandations</span><span class="sxs-lookup"><span data-stu-id="6fce9-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="6fce9-109">Avant de modifier les paramètres, renseignez-vous sur la façon dont ils vont affecter les résultats ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6fce9-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="6fce9-110">Liste des produits « Tendance »</span><span class="sxs-lookup"><span data-stu-id="6fce9-110">"Trending" product list</span></span>

<span data-ttu-id="6fce9-111">La liste de produits « Tendance » a deux paramètres modifiables :</span><span class="sxs-lookup"><span data-stu-id="6fce9-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Exemple de paramètre par défaut de la liste « Tendance »](./media/exampletrendingparameters.png)

1. <span data-ttu-id="6fce9-113">**Inclure les nouveaux produits des X dernier jours** - Les produits qui ont été ajoutés au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour sélectionner des candidats de produit.</span><span class="sxs-lookup"><span data-stu-id="6fce9-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="6fce9-114">La valeur par défaut dans l'image suggère que les produits datant de 180 jours peuvent être utilisés dans la liste des produits tendance.</span><span class="sxs-lookup"><span data-stu-id="6fce9-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="6fce9-115">**Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="6fce9-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="6fce9-116">La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits tendance.</span><span class="sxs-lookup"><span data-stu-id="6fce9-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="6fce9-117">Liste de produits « Meilleure vente »</span><span class="sxs-lookup"><span data-stu-id="6fce9-117">"Best selling" product list</span></span>

<span data-ttu-id="6fce9-118">En fonction de votre entreprise, la liste « Meilleure vente » peut apporter des résultats différents de ceux de la liste « Tendance », même si elles utilisent toutes les deux les données de transaction pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="6fce9-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="6fce9-119">Comme les meilleures ventes n'ont aucune limité basée sur une date d'assortiment, les meilleures ventes peut encore mettre des produits plus anciens et très populaires en évidence qui peuvent avoir baissé dans la liste des tendances.</span><span class="sxs-lookup"><span data-stu-id="6fce9-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="6fce9-120">La liste de produits « Meilleure vente » a un paramètre modifiable :</span><span class="sxs-lookup"><span data-stu-id="6fce9-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Exemple de paramètre par défaut de liste de meilleures ventes](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="6fce9-122">**Inclure les ventes des X dernier jours** - Les transactions de ventes qui ont eu lieu au cours du nombre de jours spécifié avant la date actuelle peuvent être utilisés pour commander des produits.</span><span class="sxs-lookup"><span data-stu-id="6fce9-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="6fce9-123">La valeur par défaut ci-dessus suggère que tous les achats effectués d'un produit dans les 30 derniers jours soient utilisés pour déterminer l'emplacement du produit dans la liste de produits les plus vendus.</span><span class="sxs-lookup"><span data-stu-id="6fce9-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="6fce9-124">Manuellement ajouter ou supprimer des produits des listes de recommandations</span><span class="sxs-lookup"><span data-stu-id="6fce9-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="6fce9-125">Pour les listes « Nouveau », « Tendance » ou « Meilleure vente »</span><span class="sxs-lookup"><span data-stu-id="6fce9-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="6fce9-126">Accédez à **Retail et Commerce** > **Recommandations de produits** > **Paramètres des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="6fce9-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="6fce9-127">Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.</span><span class="sxs-lookup"><span data-stu-id="6fce9-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="6fce9-128">Sélectionnez la liste à laquelle ajouter ou supprimer des produits.</span><span class="sxs-lookup"><span data-stu-id="6fce9-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="6fce9-129">Pour ajouter des produits à la table, sélectionnez **Ajouter une ligne**.</span><span class="sxs-lookup"><span data-stu-id="6fce9-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="6fce9-130">Sous la colonne Produit, recherchez un produit par **Nom** ou par **Numéro de produit.**</span><span class="sxs-lookup"><span data-stu-id="6fce9-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Exemple de recherche d'un produit dans la nouvelle liste de produits](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="6fce9-132">Dans la colonne Type de ligne, sélectionnez l'une des deux options :</span><span class="sxs-lookup"><span data-stu-id="6fce9-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="6fce9-133">**Inclure** – force un produit au dessus de la liste</span><span class="sxs-lookup"><span data-stu-id="6fce9-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="6fce9-134">**Exclure** – supprime un produit de la liste qui s'affiche</span><span class="sxs-lookup"><span data-stu-id="6fce9-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Exemple d'inclusion ou d'exclusion d'un produit de la nouvelle liste de produits](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="6fce9-136">La modification de l'**Ordre d'affichage** modifie l'ordre dans lequel les produits marqués à **Inclure** s'affichent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6fce9-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="6fce9-137">Si deux produits ont la même valeur d'**ordre d'affichage**, l'ordre final de ces deux résultats peut différer du back-office.</span><span class="sxs-lookup"><span data-stu-id="6fce9-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="6fce9-138">Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6fce9-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="6fce9-139">Pour les listes « D'autres client aiment également » ou « Fréquemment achetés ensemble »</span><span class="sxs-lookup"><span data-stu-id="6fce9-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="6fce9-140">Dans le contexte des listes « Fréquemment achetés ensemble » ou « D'autres clients aiment également », l'apprentissage machine permet d'analyser les schémas d'achat des consommateurs pour recommander des produits liés généralement achetés ensemble pour un seul produit d'origine.</span><span class="sxs-lookup"><span data-stu-id="6fce9-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="6fce9-141">Un *produit initial* est le produit pour lequel vous voulez générer des résultats.</span><span class="sxs-lookup"><span data-stu-id="6fce9-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="6fce9-142">Dans le contexte de l'ajustement manuel des listes de recommandations, vous ajoutez ou supprimez des résultats pour ce produit.</span><span class="sxs-lookup"><span data-stu-id="6fce9-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="6fce9-143">Procédez comme suit pour ajouter ou supprimer manuellement des résultats pour un produit d'origine :</span><span class="sxs-lookup"><span data-stu-id="6fce9-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="6fce9-144">Sélectionnez le **Produit d'origine**.</span><span class="sxs-lookup"><span data-stu-id="6fce9-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="6fce9-145">Dans la colonne **Produit**, recherchez un produit par **Nom** ou **Numéro de produit.**
![Exemple de la recherche d'un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="6fce9-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="6fce9-146">Dans la colonne **Type de ligne**, sélectionnez l'une des deux options :</span><span class="sxs-lookup"><span data-stu-id="6fce9-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="6fce9-147">**Inclure** – force un produit au dessus de la liste</span><span class="sxs-lookup"><span data-stu-id="6fce9-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="6fce9-148">**Exclure** – supprime un produit de la liste qui s'affiche</span><span class="sxs-lookup"><span data-stu-id="6fce9-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="6fce9-149">![Exemple de Inclure ou Exclure un produit sur la liste Fréquemment achetés ensemble](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="6fce9-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="6fce9-150">Pour supprimer des produits de la table : sélectionnez la ligne à supprimer et sélectionnez Supprimer.</span><span class="sxs-lookup"><span data-stu-id="6fce9-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="6fce9-151">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6fce9-151">Additional resources</span></span>

[<span data-ttu-id="6fce9-152">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6fce9-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6fce9-153">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6fce9-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6fce9-154">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6fce9-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6fce9-155">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="6fce9-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="6fce9-156">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="6fce9-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6fce9-157">Activer les recommandations « acheter des aspects similaires »</span><span class="sxs-lookup"><span data-stu-id="6fce9-157">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="6fce9-158">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="6fce9-158">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6fce9-159">Ajouter des recommandations à l’écran de transaction</span><span class="sxs-lookup"><span data-stu-id="6fce9-159">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6fce9-160">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="6fce9-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6fce9-161">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="6fce9-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6fce9-162">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="6fce9-162">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]