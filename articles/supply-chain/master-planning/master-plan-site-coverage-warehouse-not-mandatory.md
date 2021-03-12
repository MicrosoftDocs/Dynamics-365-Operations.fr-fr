---
title: Planification pour couverture de site, entrepôt non obligatoire
description: Cette rubrique décrit comment un article disposant de la dimension du site comme couverture est planifié.
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe5cb5f9d21afcd12f3041bb9acc89fff360c95e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970454"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="fce32-103">Planification pour couverture de site, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="fce32-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fce32-104">Cette rubrique décrit comment un article disposant de la dimension du site comme couverture est planifié.</span><span class="sxs-lookup"><span data-stu-id="fce32-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="fce32-105">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fce32-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="fce32-106">La dimension de site est définie sur obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="fce32-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="fce32-107">La dimension d'entrepôt n'est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="fce32-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="fce32-108">L'entrepôt peut être connu mais n'est pas utilisé dans le calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="fce32-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="fce32-109">La dimension de site est définie pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="fce32-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="fce32-110">La dimension d'entrepôt n'est pas définie pour la planification de la couverture.</span><span class="sxs-lookup"><span data-stu-id="fce32-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="fce32-111">Par conséquent, l'offre et la demande sont agrégées par site (et d'autres dimensions planifiées, éventuellement).</span><span class="sxs-lookup"><span data-stu-id="fce32-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="fce32-112">Le graphique suivant illustre l'exécution du calcul de planification.</span><span class="sxs-lookup"><span data-stu-id="fce32-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="fce32-113">Les paramètres indiqués dans le graphique, et leurs emplacements, sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="fce32-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="fce32-114">La couverture d'article est définie pour l'article.</span><span class="sxs-lookup"><span data-stu-id="fce32-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="fce32-115">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="fce32-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="fce32-116">Sélectionnez l'article, puis cliquez sur **Plan &gt; Couverture de l'article**.</span><span class="sxs-lookup"><span data-stu-id="fce32-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="fce32-117">Des relations de rechargement sont définies pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fce32-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="fce32-118">Cliquez sur **Gestion des stocks &gt; Paramétrage &gt; Décomposition du stock &gt; Entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="fce32-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="fce32-119">Dans l'onglet **Planification**, voir le groupe de champs **Entrepôt principal**.</span><span class="sxs-lookup"><span data-stu-id="fce32-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="fce32-120">Par défaut, le type de commande est défini sur Production, Commande fournisseur ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="fce32-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="fce32-121">Cliquez sur **Gestion des informations sur les produits &gt; Produits &gt; Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="fce32-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="fce32-122">Sélectionnez l'article, puis cliquez sur **Plan &gt; Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fce32-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="fce32-123">Dans l'écran **Paramètres de commande par défaut**, consultez le champ **Type de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="fce32-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Demande pour l'entrepôt de couverture du site non obligatoire](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="fce32-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fce32-125">Additional resources</span></span>
--------

[<span data-ttu-id="fce32-126">Vue d'ensemble de planification générale et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="fce32-126">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="fce32-127">Planification de couverture de site et d'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="fce32-127">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="fce32-128">Planification pour couverture de site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="fce32-128">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="fce32-129">Planification pour couverture de site, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="fce32-129">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="fce32-130">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="fce32-130">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



