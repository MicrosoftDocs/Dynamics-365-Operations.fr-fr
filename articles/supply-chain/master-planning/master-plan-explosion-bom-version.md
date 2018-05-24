---
title: "Éclatement d'une version de nomenclature"
description: "Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 80c9fa6ec98bd2cdc3edd5329e2a619ef9cc8cb2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="122bd-103">Éclatement d'une version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="122bd-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="122bd-104">Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="122bd-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="122bd-105">Un éclatement de la demande d'une version de nomenclature crée une demande pour chaque ligne de nomenclature au niveau d'un site spécifique, et éventuellement d'un entrepôt spécifique.</span><span class="sxs-lookup"><span data-stu-id="122bd-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="122bd-106">Dans une nomenclature spécifique à un site, un entrepôt spécifique peut être défini pour chaque ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="122bd-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="122bd-107">En outre, pour chaque ligne de nomenclature, les paramètres de dimension de l'article déterminent si un entrepôt est requis ou non.</span><span class="sxs-lookup"><span data-stu-id="122bd-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="122bd-108">La demande qui en résulte pour chaque ligne de nomenclature devient le point de départ d'un autre éclatement de la demande.</span><span class="sxs-lookup"><span data-stu-id="122bd-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="122bd-109">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="122bd-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="122bd-110">La dimension de site est obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="122bd-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="122bd-111">La dimension de site est cohérente.</span><span class="sxs-lookup"><span data-stu-id="122bd-111">The site dimension is consistent.</span></span> <span data-ttu-id="122bd-112">Le site pour la demande de niveau inférieur est donc identique au site de la transaction de demande initiale.</span><span class="sxs-lookup"><span data-stu-id="122bd-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="122bd-113">L'illustration suivante présente le processus d'éclatement de la demande de planification.</span><span class="sxs-lookup"><span data-stu-id="122bd-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Éclatement de la demande à l'aide d'une version de nomenclature](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="122bd-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="122bd-115">Additional resources</span></span>
--------

[<span data-ttu-id="122bd-116">Planification - Méthode de détermination de la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="122bd-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="122bd-117">Planification et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="122bd-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)




