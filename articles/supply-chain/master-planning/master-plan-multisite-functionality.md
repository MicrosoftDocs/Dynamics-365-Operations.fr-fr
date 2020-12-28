---
title: Vue d'ensemble de planification générale et fonctionnalité multisite
description: La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2adbac35d556314b3ec9916e2b7b2706ce3528c9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428124"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="ed201-103">Vue d'ensemble de planification générale et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="ed201-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed201-104">La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ed201-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="ed201-105">La dimension de site est obligatoire, et vous pouvez définir la dimension d'entrepôt comme étant obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ed201-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="ed201-106">Lorsqu'une dimension est obligatoire, une valeur de dimension doit être entrée pour tous les mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="ed201-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="ed201-107">Par conséquent, lors de la planification, le site et l'entrepôt pour la demande initiale sont connus.</span><span class="sxs-lookup"><span data-stu-id="ed201-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="ed201-108">La dimension de site est également cohérente afin que, lors de l'éclatement de la demande de niveau inférieur, la valeur du site ne change pas.</span><span class="sxs-lookup"><span data-stu-id="ed201-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="ed201-109">Lorsque l'entrepôt n'est pas obligatoire, il se peut qu'il ne soit pas connu à partir de la demande initiale.</span><span class="sxs-lookup"><span data-stu-id="ed201-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="ed201-110">Le moteur de planification doit déterminer l'entrepôt à utiliser en fonction des paramètres définis pour l'article, les entrepôts individuels et les détails de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="ed201-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="ed201-111">Les rubriques suivantes décrivent le fonctionnement du moteur de planification, lorsque différents paramètres sont définis, pour déterminer l'entrepôt à utiliser.</span><span class="sxs-lookup"><span data-stu-id="ed201-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="ed201-112">Planification de couverture de site et d'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="ed201-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ed201-113">Planification pour couverture de site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="ed201-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="ed201-114">Planification de couverture de site et d'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="ed201-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ed201-115">Planification pour couverture de site, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="ed201-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="ed201-116">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="ed201-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



