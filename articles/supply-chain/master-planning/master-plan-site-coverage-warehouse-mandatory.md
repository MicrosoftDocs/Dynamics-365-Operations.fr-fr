---
title: Planification pour couverture de site, entrepôt obligatoire
description: Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié. L'entrepôt est une dimension obligatoire.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72240e7db8ec914220cb8f8f1185a91a304ff66b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977961"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="ce790-104">Planification pour couverture de site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="ce790-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce790-105">Cette rubrique décrit comment un article disposant du site comme dimension de couverture est planifié.</span><span class="sxs-lookup"><span data-stu-id="ce790-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="ce790-106">L'entrepôt est une dimension obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ce790-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="ce790-107">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce790-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="ce790-108">La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="ce790-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="ce790-109">Ce paramètre ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="ce790-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="ce790-110">La dimension d'entrepôt est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="ce790-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="ce790-111">La dimension de site est définie pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="ce790-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="ce790-112">D'autres dimensions peuvent également être définies pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="ce790-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="ce790-113">Elles ne sont toutefois pas affectées par la fonctionnalité multisite.</span><span class="sxs-lookup"><span data-stu-id="ce790-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="ce790-114">La dimension d'entrepôt n'est pas définie pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="ce790-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="ce790-115">Par conséquent, l'offre et la demande sont agrégées par site (et d'autres dimensions planifiées, éventuellement).</span><span class="sxs-lookup"><span data-stu-id="ce790-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="ce790-116">Le graphique suivant illustre l'exécution du calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="ce790-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="ce790-117">Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ce790-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="ce790-118">La couverture d'article est définie pour l'article.</span><span class="sxs-lookup"><span data-stu-id="ce790-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="ce790-119">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="ce790-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ce790-120">Sélectionnez l'article, puis cliquez sur **Plan &gt; Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="ce790-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="ce790-121">Des relations de rechargement sont définies pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ce790-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="ce790-122">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="ce790-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="ce790-123">Dans l'onglet **Planification**, voir le groupe de champs **Entrepôt principal**.</span><span class="sxs-lookup"><span data-stu-id="ce790-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="ce790-124">Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="ce790-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="ce790-125">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="ce790-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="ce790-126">Sélectionnez l'article, puis cliquez sur **Plan &gt; Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="ce790-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="ce790-127">Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="ce790-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demande pour l'entrepôt de couverture du site obligatoire](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="ce790-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="ce790-129">Additional resources</span></span>
--------

[<span data-ttu-id="ce790-130">Vue d'ensemble de planification générale et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="ce790-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="ce790-131">Planification de couverture de site et d'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="ce790-131">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ce790-132">Planification pour couverture de site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="ce790-132">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ce790-133">Planification de couverture de site et d'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="ce790-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ce790-134">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="ce790-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



