---
title: "Planification pour la couverture du site et de l'entrepôt, entrepôt obligatoire"
description: "Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié. La dimension d'entrepôt n'est pas obligatoire."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bc4b54b25edf0f1a47839e8a8253db5a8c595a8f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="f9bcb-104">Planification pour la couverture du site et de l'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="f9bcb-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f9bcb-105">Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="f9bcb-106">La dimension d'entrepôt n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="f9bcb-107">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9bcb-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f9bcb-108">La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f9bcb-109">La dimension d'entrepôt est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f9bcb-110">Les dimensions de site et d'entrepôt sont définies pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="f9bcb-111">D'autres dimensions peuvent également être définies pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="f9bcb-112">Elles ne sont toutefois pas affectées par la fonctionnalité multisite.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="f9bcb-113">Le graphique suivant illustre l'exécution du calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="f9bcb-114">Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="f9bcb-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="f9bcb-115">L'entrepôt est défini sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="f9bcb-116">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f9bcb-117">Dans l'organisateur **Planification**, voir le champ **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="f9bcb-118">La couverture d'article est définie pour l'article.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="f9bcb-119">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f9bcb-120">Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-120">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="f9bcb-121">Des relations de rechargement sont définies pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="f9bcb-122">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f9bcb-123">Dans l'organisateur **Planification**, voir le groupe de champs **Entrepôt principal**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="f9bcb-124">Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="f9bcb-125">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f9bcb-126">Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-126">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="f9bcb-127">Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="f9bcb-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Couverture de l'entrepôt et du site de la demande en cas d'obligation](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="f9bcb-129">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f9bcb-129">See also</span></span>
--------

[<span data-ttu-id="f9bcb-130">Planification et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="f9bcb-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="f9bcb-131">Planification - couverture du site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="f9bcb-131">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f9bcb-132">Planification - couverture du site, entrepôt no obligatoire</span><span class="sxs-lookup"><span data-stu-id="f9bcb-132">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f9bcb-133">Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="f9bcb-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f9bcb-134">Planification - Méthode de détermination de la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="f9bcb-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




