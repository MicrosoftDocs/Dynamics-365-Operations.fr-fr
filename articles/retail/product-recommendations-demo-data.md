---
title: Données de démonstration des recommandations de produit omnicanal
description: Ce document vise à fournir des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872324"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="959bf-103">Données de démonstration des recommandations de produit omnicanal</span><span class="sxs-lookup"><span data-stu-id="959bf-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="959bf-104">Ce document vise à fournir des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.</span><span class="sxs-lookup"><span data-stu-id="959bf-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="959bf-105">Les recommandations de produit omnicanal offrent un ensemble de listes de produits générées de manière programmée ou traitées de manière éditoriale.</span><span class="sxs-lookup"><span data-stu-id="959bf-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="959bf-106">Ces listes peuvent être utilisées dans différents scénarios, selon les besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="959bf-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="959bf-107">Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="959bf-107">For more information about product recommendation lists, see [Product recommendations overview.](../commerce/product-recommendations.md)</span></span>

<span data-ttu-id="959bf-108">Les recommandations de produit des environnements de niveau 2 ou Dynamics supérieurs sont automatiquement calculées selon les données client.</span><span class="sxs-lookup"><span data-stu-id="959bf-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="959bf-109">L'utilisation des données de démonstration des recommandations produit ne désactive pas les solutions de recommandations produit déjà fournies dans l'environnement et les coûts associés à cet usage.</span><span class="sxs-lookup"><span data-stu-id="959bf-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="959bf-110">Pour les environnements de niveau 1, les recommandations de produit sont basées uniquement sur les données de démonstration statiques stockées dans un fichier .csv.</span><span class="sxs-lookup"><span data-stu-id="959bf-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="959bf-111">Activation des données de démonstration des recommandations de produit dans un environnement</span><span class="sxs-lookup"><span data-stu-id="959bf-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="959bf-112">Les clients doivent déployer l'**extension de démonstration de Dynamics 365 Commerce (version préliminaire)** vers l'environnement respectif, ce qui active automatiquement les données de démonstration des recommandations de produit.</span><span class="sxs-lookup"><span data-stu-id="959bf-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="959bf-113">Données de démonstration par défaut</span><span class="sxs-lookup"><span data-stu-id="959bf-113">Default demo data</span></span>
<span data-ttu-id="959bf-114">Chaque environnement de type Onebox est fourni avec un jeu préchargé de données de démonstration de recommandations produit stockées dans le fichier .csv à part **‘reco_demo_data.csv’**, situé dans le même dossier que ce document sur Retail Server.</span><span class="sxs-lookup"><span data-stu-id="959bf-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="959bf-115">Ces données sont structurées selon les colonnes suivantes</span><span class="sxs-lookup"><span data-stu-id="959bf-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="959bf-116">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="959bf-116">Column name</span></span>         | <span data-ttu-id="959bf-117">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="959bf-117">Mandatory</span></span>          | <span data-ttu-id="959bf-118">Description</span><span class="sxs-lookup"><span data-stu-id="959bf-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="959bf-119">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="959bf-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="959bf-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="959bf-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="959bf-122">Le type de liste de recommandation produit spécifique que le point de données de démonstration est sur le point de générer.</span><span class="sxs-lookup"><span data-stu-id="959bf-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="959bf-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="959bf-123">RecoBestSelling</span></span></li><li><span data-ttu-id="959bf-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="959bf-124">RecoNew</span></span></li><li><span data-ttu-id="959bf-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="959bf-125">RecoTrending</span></span></li><li><span data-ttu-id="959bf-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="959bf-126">RecoCart</span></span></li><li><span data-ttu-id="959bf-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="959bf-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="959bf-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="959bf-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="959bf-130">Le nombre d'unité opérationnelle spécifique où les recommandations produit sont prévues.</span><span class="sxs-lookup"><span data-stu-id="959bf-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="959bf-131">Catégorie</span><span class="sxs-lookup"><span data-stu-id="959bf-131">Category</span></span>            |                    |    <span data-ttu-id="959bf-132">La catégorie pour laquelle la liste spécifique doit être retournée.</span><span class="sxs-lookup"><span data-stu-id="959bf-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="959bf-133">Si aucune catégorie n'est spécifiée, la liste est destinée uniquement pour le haut de la hiérarchie de navigation.</span><span class="sxs-lookup"><span data-stu-id="959bf-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="959bf-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="959bf-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="959bf-135">Pour les listes nécessitant une valeur initiale (RecoPeopleAlsoBuy et RecoCart), le produit pour lequel ces listes doivent présenter des produits supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="959bf-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="959bf-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="959bf-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="959bf-138">Un ou plusieurs produits à renvoyer en retour, séparés par **« ;  »**.</span><span class="sxs-lookup"><span data-stu-id="959bf-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="959bf-139">Données de démonstration personnalisées</span><span class="sxs-lookup"><span data-stu-id="959bf-139">Customize demo data</span></span>
<span data-ttu-id="959bf-140">Les clients peuvent modifier les données de démonstration par défaut avec toute information de catégorie ou de produit configurée au siège.</span><span class="sxs-lookup"><span data-stu-id="959bf-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="959bf-141">Une fois le fichier CSV mis à jour, les recommandations produit renvoyées aux clients reflèteront immédiatement les modifications.</span><span class="sxs-lookup"><span data-stu-id="959bf-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="959bf-142">L'extension contient un fichier de données appelé RecoMockDataset.csv qui permet au client de contrôler le jeu de données utilisé pour activer les résultats d'imitations de recommandations.</span><span class="sxs-lookup"><span data-stu-id="959bf-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="959bf-143">Le nom de fichier peut être contrôlé via la configuration d'extension à l'aide du paramètre **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="959bf-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="959bf-144">Cela permet aux clients d'avoir plusieurs jeux de données disponibles entre lesquels basculer pour une configuration plus simple.</span><span class="sxs-lookup"><span data-stu-id="959bf-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="959bf-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="959bf-145">Additional resources</span></span>

[<span data-ttu-id="959bf-146">Vue d'ensemble des recommandations produit</span><span class="sxs-lookup"><span data-stu-id="959bf-146">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="959bf-147">Planification de l'environnement</span><span class="sxs-lookup"><span data-stu-id="959bf-147">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
