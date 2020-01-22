---
title: Obtenir des recommandations produit à l'aide de données de démonstration
description: Ce document fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
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
ms.openlocfilehash: af8a30e69d9ed143e045950efdcece207f6da14c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697932"
---
# <a name="get-product-recommendations-using-demo-data"></a><span data-ttu-id="057e0-103">Obtenir des recommandations produit à l'aide de données de démonstration</span><span class="sxs-lookup"><span data-stu-id="057e0-103">Get product recommendations using demo data</span></span>
<span data-ttu-id="057e0-104">Ce document fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.</span><span class="sxs-lookup"><span data-stu-id="057e0-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="057e0-105">Les recommandations de produit omnicanal offrent un ensemble de listes de produits générées de manière programmée ou traitées de manière éditoriale.</span><span class="sxs-lookup"><span data-stu-id="057e0-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="057e0-106">Ces listes peuvent être utilisées dans différents scénarios, selon les besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="057e0-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="057e0-107">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="057e0-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="057e0-108">Les recommandations de produit des environnements de niveau 2 ou Dynamics 365 supérieurs sont automatiquement calculées selon les données client.</span><span class="sxs-lookup"><span data-stu-id="057e0-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="057e0-109">L'utilisation des données de démonstration des recommandations produit ne désactive pas les solutions de recommandations produit déjà fournies dans l'environnement et les coûts associés à cet usage.</span><span class="sxs-lookup"><span data-stu-id="057e0-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="057e0-110">Pour les environnements de niveau 1, les recommandations de produit sont basées uniquement sur les données de démonstration statiques stockées dans un fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="057e0-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="057e0-111">Activation des données de démonstration des recommandations de produit dans un environnement</span><span class="sxs-lookup"><span data-stu-id="057e0-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="057e0-112">Pour activer les données de démonstration de produit, vous devez déployer la version préliminaire de l'extension de démonstration de Dynamics 365 Commerce vers l'environnement respectif.</span><span class="sxs-lookup"><span data-stu-id="057e0-112">To enable product recommensations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="057e0-113">Cela active automatiquement les données de démonstration de recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="057e0-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="057e0-114">Données de démonstration par défaut</span><span class="sxs-lookup"><span data-stu-id="057e0-114">Default demo data</span></span>
<span data-ttu-id="057e0-115">Chaque environnement de type Onebox est fourni avec un jeu préchargé de données de démonstration de recommandations produit stockées dans le fichier .csv à part ‘reco_demo_data.csv’, situé dans le Retail Server.</span><span class="sxs-lookup"><span data-stu-id="057e0-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated ‘reco_demo_data.csv’ file, located on the Retail Server.</span></span>

<span data-ttu-id="057e0-116">Les données sont structurées selon les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="057e0-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="057e0-117">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="057e0-117">Column name</span></span>         | <span data-ttu-id="057e0-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="057e0-118">Mandatory</span></span>          | <span data-ttu-id="057e0-119">Description</span><span class="sxs-lookup"><span data-stu-id="057e0-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="057e0-120">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="057e0-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="057e0-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="057e0-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="057e0-123">Le type de liste de recommandation produit spécifique que le point de données de démonstration est sur le point de générer.</span><span class="sxs-lookup"><span data-stu-id="057e0-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="057e0-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="057e0-124">RecoBestSelling</span></span></li><li><span data-ttu-id="057e0-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="057e0-125">RecoNew</span></span></li><li><span data-ttu-id="057e0-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="057e0-126">RecoTrending</span></span></li><li><span data-ttu-id="057e0-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="057e0-127">RecoCart</span></span></li><li><span data-ttu-id="057e0-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="057e0-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="057e0-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="057e0-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="057e0-131">Le nombre d'unité opérationnelle spécifique où les recommandations produit sont prévues.</span><span class="sxs-lookup"><span data-stu-id="057e0-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="057e0-132">Catégorie</span><span class="sxs-lookup"><span data-stu-id="057e0-132">Category</span></span>            |                    |    <span data-ttu-id="057e0-133">La catégorie pour laquelle la liste spécifique doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="057e0-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="057e0-134">Si aucune catégorie n'est spécifiée, la liste est destinée uniquement pour le haut de la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="057e0-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="057e0-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="057e0-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="057e0-136">Pour les listes nécessitant une valeur initiale (RecoPeopleAlsoBuy et RecoCart), le produit pour lequel ces listes doivent présenter des produits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="057e0-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="057e0-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="057e0-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="057e0-139">Un ou plusieurs produits à renvoyer en retour, séparés par ’;’.</span><span class="sxs-lookup"><span data-stu-id="057e0-139">One or more products to be returned as the result, separated by ‘;’.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="057e0-140">Données de démonstration personnalisées</span><span class="sxs-lookup"><span data-stu-id="057e0-140">Customize demo data</span></span>
<span data-ttu-id="057e0-141">Vous pouvez modifier les données de démonstration par défaut avec toute information de catégorie ou de produit configurée au siège.</span><span class="sxs-lookup"><span data-stu-id="057e0-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="057e0-142">Une fois le fichier CSV mis à jour, les recommandations de produit qui sont renvoyées aux clients reflèteront immédiatement les modifications.</span><span class="sxs-lookup"><span data-stu-id="057e0-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="057e0-143">L'extension contient un fichier de données appelé 'RecoMockDataset.csv' qui vous permet de contrôler le jeu de données utilisé pour activer les résultats d'imitations de recommandations.</span><span class="sxs-lookup"><span data-stu-id="057e0-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="057e0-144">Le nom de fichier peut être contrôlé via la configuration d'extension à l'aide du paramètre **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="057e0-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="057e0-145">Cela vous permet d'avoir plusieurs jeux de données disponibles entre lesquels basculer pour une configuration plus simple.</span><span class="sxs-lookup"><span data-stu-id="057e0-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="057e0-146">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="057e0-146">Additional Resources</span></span>

[<span data-ttu-id="057e0-147">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="057e0-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="057e0-148">Planification de l'environnement</span><span class="sxs-lookup"><span data-stu-id="057e0-148">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)