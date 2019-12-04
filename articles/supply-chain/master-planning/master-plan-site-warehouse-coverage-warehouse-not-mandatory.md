---
title: Planification pour la couverture du site et de l'entrepôt, entrepôt non obligatoire
description: Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié. La dimension d'entrepôt n'est pas obligatoire.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cea228e04632bd61f60771b09481241df5d16bd3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813705"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="d79a8-104">Planification pour la couverture du site et de l'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="d79a8-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d79a8-105">Cette rubrique décrit comment un article disposant d'un site et d'un entrepôt comme dimensions de couverture est planifié.</span><span class="sxs-lookup"><span data-stu-id="d79a8-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="d79a8-106">La dimension d'entrepôt n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d79a8-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="d79a8-107">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d79a8-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="d79a8-108">La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="d79a8-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="d79a8-109">Ce paramètre ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="d79a8-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="d79a8-110">La dimension d'entrepôt n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d79a8-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="d79a8-111">L'entrepôt peut être connu mais n'est pas utilisé dans le calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="d79a8-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="d79a8-112">Les dimensions de site et d'entrepôt sont définies pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="d79a8-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="d79a8-113">D'autres dimensions peuvent également être définies pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="d79a8-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="d79a8-114">Elles ne sont toutefois pas affectées par la fonctionnalité multisite.</span><span class="sxs-lookup"><span data-stu-id="d79a8-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="d79a8-115">Le graphique suivant illustre l'exécution du calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="d79a8-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="d79a8-116">Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d79a8-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="d79a8-117">L'entrepôt est défini sur Manuel.</span><span class="sxs-lookup"><span data-stu-id="d79a8-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="d79a8-118">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="d79a8-119">Dans l'organisateur **Planification**, voir le champ **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="d79a8-120">La couverture d'article est définie pour l'article.</span><span class="sxs-lookup"><span data-stu-id="d79a8-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="d79a8-121">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="d79a8-122">Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="d79a8-123">Des relations de rechargement sont définies pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d79a8-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="d79a8-124">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="d79a8-125">Dans l'organisateur **Planification**, voir le groupe de champs **Entrepôt principal**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="d79a8-126">Le type de commande par défaut est défini à Production, Commande fournisseur, ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="d79a8-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="d79a8-127">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="d79a8-128">Sélectionnez l'article, puis dans le volet Actions, sous l'onglet **Planifier**, cliquez sur **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="d79a8-129">Dans l'écran **Paramètres de commande par défaut**, voir le **Type de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d79a8-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demande pour le site et l'entrepôt, pas l'entrepôt](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="d79a8-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d79a8-131">Additional resources</span></span>
--------

[<span data-ttu-id="d79a8-132">Vue d'ensemble de planification générale et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="d79a8-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="d79a8-133">Planification pour couverture de site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="d79a8-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="d79a8-134">Planification de couverture de site et d'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="d79a8-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="d79a8-135">Planification de couverture de site et d'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="d79a8-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="d79a8-136">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="d79a8-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



