---
title: Éclatement d'une version de nomenclature
description: Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 380f8069a726e53084164a5ac1fc0a0a99c83590
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213743"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="75e02-103">Éclatement d'une version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="75e02-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75e02-104">Cet article décrit un scénario de planification qui implique l'éclatement d'une version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="75e02-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="75e02-105">Un éclatement de la demande d'une version de nomenclature crée une demande pour chaque ligne de nomenclature au niveau d'un site spécifique, et éventuellement d'un entrepôt spécifique.</span><span class="sxs-lookup"><span data-stu-id="75e02-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="75e02-106">Dans une nomenclature spécifique à un site, un entrepôt spécifique peut être défini pour chaque ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="75e02-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="75e02-107">En outre, pour chaque ligne de nomenclature, les paramètres de dimension de l'article déterminent si un entrepôt est requis ou non.</span><span class="sxs-lookup"><span data-stu-id="75e02-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="75e02-108">La demande qui en résulte pour chaque ligne de nomenclature devient le point de départ d'un autre éclatement de la demande.</span><span class="sxs-lookup"><span data-stu-id="75e02-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="75e02-109">Ce scénario de planification implique les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="75e02-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="75e02-110">La dimension de site est obligatoire et doit être entrée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="75e02-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="75e02-111">La dimension de site est cohérente.</span><span class="sxs-lookup"><span data-stu-id="75e02-111">The site dimension is consistent.</span></span> <span data-ttu-id="75e02-112">Le site pour la demande de niveau inférieur est donc identique au site de la transaction de demande initiale.</span><span class="sxs-lookup"><span data-stu-id="75e02-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="75e02-113">L'illustration suivante présente le processus d'éclatement de la demande de planification.</span><span class="sxs-lookup"><span data-stu-id="75e02-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Éclatement de la demande à l'aide d'une version de nomenclature](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="75e02-115">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="75e02-115">Additional resources</span></span>
--------

[<span data-ttu-id="75e02-116">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="75e02-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="75e02-117">Vue d'ensemble de planification générale et fonctionnalité multisite</span><span class="sxs-lookup"><span data-stu-id="75e02-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)



