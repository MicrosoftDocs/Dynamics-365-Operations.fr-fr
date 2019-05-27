---
title: Déterminer la version de nomenclature
description: Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf125e2b75c4dfa406f4f05b249e6fdb49c84b7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556919"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="aa2c8-103">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="aa2c8-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa2c8-104">Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="aa2c8-105">La dimension du site est toujours identifiée et indiquée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="aa2c8-106">Le processus suivant permet de déterminer la version de nomenclature à utiliser :</span><span class="sxs-lookup"><span data-stu-id="aa2c8-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="aa2c8-107">Si une version de nomenclature est définie pour l'article dans le site de la demande, la nomenclature spécifique au site est utilisée.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="aa2c8-108">Si aucune version de nomenclature n'est définie pour l'article dans le site de la demande, une nomenclature générale est utilisée.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="aa2c8-109">Une telle nomenclature n'indique pas de site et est valide pour plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="aa2c8-110">Si une nomenclature générale existe, elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="aa2c8-111">S'il n'y a aucune version de nomenclature à utiliser, l'éclatement de la demande est arrêté à ce stade.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="aa2c8-112">Une version de nomenclature valide (spécifique au site ou générale) doit satisfaire aux critères requis de date et de quantité.</span><span class="sxs-lookup"><span data-stu-id="aa2c8-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>





