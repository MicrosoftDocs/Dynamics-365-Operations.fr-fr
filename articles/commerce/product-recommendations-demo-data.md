---
title: Créer des recommandations avec des données de démonstration
description: Cette rubrique fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 59b4dd7a29af739d92a20f6fe55eff9f201fcb6d
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454554"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="816e2-103">Créer des recommandations avec des données de démonstration</span><span class="sxs-lookup"><span data-stu-id="816e2-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="816e2-104">Cette rubrique fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.</span><span class="sxs-lookup"><span data-stu-id="816e2-104">This topic provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="816e2-105">Les recommandations de produit omnicanal offrent un ensemble de listes de produits générées de manière programmée ou traitées de manière éditoriale.</span><span class="sxs-lookup"><span data-stu-id="816e2-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="816e2-106">Ces listes peuvent être utilisées dans différents scénarios, selon les besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="816e2-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="816e2-107">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="816e2-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="816e2-108">Les recommandations de produit des environnements de niveau 2 ou Dynamics 365 supérieurs sont automatiquement calculées selon les données client.</span><span class="sxs-lookup"><span data-stu-id="816e2-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="816e2-109">L'utilisation des données de démonstration des recommandations produit ne désactive pas les solutions de recommandations produit déjà fournies dans l'environnement et les coûts associés à cet usage.</span><span class="sxs-lookup"><span data-stu-id="816e2-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="816e2-110">Pour les environnements de niveau 1, les recommandations de produit sont basées uniquement sur les données de démonstration statiques stockées dans un fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="816e2-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="816e2-111">Activation des données de démonstration des recommandations de produit dans un environnement</span><span class="sxs-lookup"><span data-stu-id="816e2-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="816e2-112">Pour activer les données de démonstration de produit, vous devez déployer la version préliminaire de l'extension de démonstration de Dynamics 365 Commerce vers l'environnement respectif.</span><span class="sxs-lookup"><span data-stu-id="816e2-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="816e2-113">Cela active automatiquement les données de démonstration de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="816e2-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="816e2-114">Données de démonstration par défaut</span><span class="sxs-lookup"><span data-stu-id="816e2-114">Default demo data</span></span>
<span data-ttu-id="816e2-115">Chaque environnement de type Onebox est fourni avec un jeu préchargé de données de démonstration (recommandations de produit) stockées dans le fichier reco_demo_data.csv qui se trouve dans Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="816e2-115">Each OneBox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="816e2-116">Les données sont structurées selon les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="816e2-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="816e2-117">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="816e2-117">Column name</span></span>         | <span data-ttu-id="816e2-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="816e2-118">Mandatory</span></span>          | <span data-ttu-id="816e2-119">Description</span><span class="sxs-lookup"><span data-stu-id="816e2-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="816e2-120">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="816e2-120">Possible values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="816e2-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="816e2-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="816e2-123">Le type de liste de recommandation produit spécifique que le point de données de démonstration est sur le point de générer.</span><span class="sxs-lookup"><span data-stu-id="816e2-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="816e2-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="816e2-124">RecoBestSelling</span></span></li><li><span data-ttu-id="816e2-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="816e2-125">RecoNew</span></span></li><li><span data-ttu-id="816e2-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="816e2-126">RecoTrending</span></span></li><li><span data-ttu-id="816e2-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="816e2-127">RecoCart</span></span></li><li><span data-ttu-id="816e2-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="816e2-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="816e2-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="816e2-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="816e2-131">Le nombre d'unité opérationnelle spécifique où les recommandations produit sont prévues.</span><span class="sxs-lookup"><span data-stu-id="816e2-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="816e2-132">Catégorie</span><span class="sxs-lookup"><span data-stu-id="816e2-132">Category</span></span>            |                    |    <span data-ttu-id="816e2-133">La catégorie pour laquelle la liste spécifique doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="816e2-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="816e2-134">Si aucune catégorie n'est spécifiée, la liste est destinée uniquement pour le haut de la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="816e2-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="816e2-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="816e2-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="816e2-136">Pour les listes nécessitant une valeur initiale (RecoPeopleAlsoBuy et RecoCart), le produit pour lequel ces listes doivent présenter des produits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="816e2-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="816e2-137">CustomerId</span><span class="sxs-lookup"><span data-stu-id="816e2-137">CustomerId</span></span>          |                    |    <span data-ttu-id="816e2-138">Pour les listes qui nécessitent un identifiant client (RecoPicks).</span><span class="sxs-lookup"><span data-stu-id="816e2-138">For lists that require a customer identifier (RecoPicks).</span></span>  <span data-ttu-id="816e2-139">La valeur par défaut « 0 » s'applique à tous les clients.</span><span class="sxs-lookup"><span data-stu-id="816e2-139">The default value '0' applies to all customers.</span></span>          |                                                                              |
| <span data-ttu-id="816e2-140">ItemIds</span><span class="sxs-lookup"><span data-stu-id="816e2-140">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="816e2-142">Un ou plusieurs produits à renvoyer en retour, séparés par ’;’.</span><span class="sxs-lookup"><span data-stu-id="816e2-142">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="816e2-143">Données de démonstration personnalisées</span><span class="sxs-lookup"><span data-stu-id="816e2-143">Customize demo data</span></span>
<span data-ttu-id="816e2-144">Vous pouvez modifier les données de démonstration par défaut avec toute information de catégorie ou de produit configurée au siège.</span><span class="sxs-lookup"><span data-stu-id="816e2-144">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="816e2-145">Une fois le fichier CSV mis à jour, les recommandations de produit qui sont renvoyées aux clients reflèteront immédiatement les modifications.</span><span class="sxs-lookup"><span data-stu-id="816e2-145">After you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="816e2-146">L'extension contient un fichier de données appelé 'RecoMockDataset.csv' qui vous permet de contrôler le jeu de données utilisé pour activer les résultats d'imitations de recommandations.</span><span class="sxs-lookup"><span data-stu-id="816e2-146">The extension contains a datafile called 'RecoMockDataset.csv', which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="816e2-147">Le nom de fichier peut être contrôlé via la configuration d'extension à l'aide du paramètre **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="816e2-147">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="816e2-148">Cela vous permet d'avoir plusieurs jeux de données disponibles entre lesquels basculer pour une configuration plus simple.</span><span class="sxs-lookup"><span data-stu-id="816e2-148">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="816e2-149">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="816e2-149">Additional resources</span></span>

[<span data-ttu-id="816e2-150">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="816e2-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="816e2-151">Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="816e2-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="816e2-152">Activer les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="816e2-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="816e2-153">Activer les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="816e2-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="816e2-154">Désactiver les recommandations personnalisées</span><span class="sxs-lookup"><span data-stu-id="816e2-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="816e2-155">Ajouter des recommandations produit sur PDV</span><span class="sxs-lookup"><span data-stu-id="816e2-155">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="816e2-156">Ajouter des recommandations à l'écran de transaction</span><span class="sxs-lookup"><span data-stu-id="816e2-156">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="816e2-157">Ajuster des résultats des recommandations AI-ML</span><span class="sxs-lookup"><span data-stu-id="816e2-157">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="816e2-158">Créer manuellement des recommandations sélectionnées</span><span class="sxs-lookup"><span data-stu-id="816e2-158">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="816e2-159">FAQ sur les recommandations produit</span><span class="sxs-lookup"><span data-stu-id="816e2-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
