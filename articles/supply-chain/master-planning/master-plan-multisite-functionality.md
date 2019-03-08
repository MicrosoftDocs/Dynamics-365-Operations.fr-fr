---
title: Planification et fonctionnalité multisite
description: La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10981e0fe201566c83fd28c792000865bc533cd3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317428"
---
# <a name="master-planning-and-multisite-functionality"></a><span data-ttu-id="bc197-103">Planification et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="bc197-103">Master planning and multisite functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc197-104">La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="bc197-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="bc197-105">La dimension de site est obligatoire, et vous pouvez définir la dimension d'entrepôt comme étant obligatoire.</span><span class="sxs-lookup"><span data-stu-id="bc197-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="bc197-106">Lorsqu'une dimension est obligatoire, une valeur de dimension doit être entrée pour tous les mouvements de stock.</span><span class="sxs-lookup"><span data-stu-id="bc197-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="bc197-107">Par conséquent, lors de la planification, le site et l'entrepôt pour la demande initiale sont connus.</span><span class="sxs-lookup"><span data-stu-id="bc197-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="bc197-108">La dimension de site est également cohérente afin que, lors de l'éclatement de la demande de niveau inférieur, la valeur du site ne change pas.</span><span class="sxs-lookup"><span data-stu-id="bc197-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="bc197-109">Lorsque l'entrepôt n'est pas obligatoire, il se peut qu'il ne soit pas connu à partir de la demande initiale.</span><span class="sxs-lookup"><span data-stu-id="bc197-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="bc197-110">Le moteur de planification doit déterminer l'entrepôt à utiliser en fonction des paramètres définis pour l'article, les entrepôts individuels et les détails de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bc197-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="bc197-111">Les rubriques suivantes décrivent le fonctionnement du moteur de planification, lorsque différents paramètres sont définis, pour déterminer l'entrepôt à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bc197-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="bc197-112">Planification - couverture du site et de l'entrepôt, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="bc197-112">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="bc197-113">Planification - couverture du site, entrepôt obligatoire</span><span class="sxs-lookup"><span data-stu-id="bc197-113">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="bc197-114">Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire</span><span class="sxs-lookup"><span data-stu-id="bc197-114">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="bc197-115">Planification - couverture du site, entrepôt no obligatoire</span><span class="sxs-lookup"><span data-stu-id="bc197-115">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="bc197-116">Planification - Méthode de détermination de la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="bc197-116">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



