---
title: "Déterminer la version de nomenclature"
description: "Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7e6745a52138e545b557fa1aa286cd49481b2ecd
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="determine-the-bom-version"></a><span data-ttu-id="3300b-103">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="3300b-103">Determine the BOM version</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3300b-104">Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.</span><span class="sxs-lookup"><span data-stu-id="3300b-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="3300b-105">La dimension du site est toujours identifiée et indiquée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="3300b-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="3300b-106">Le processus suivant permet de déterminer la version de nomenclature à utiliser :</span><span class="sxs-lookup"><span data-stu-id="3300b-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="3300b-107">Si une version de nomenclature est définie pour l'article dans le site de la demande, la nomenclature spécifique au site est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3300b-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="3300b-108">Si aucune version de nomenclature n'est définie pour l'article dans le site de la demande, une nomenclature générale est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3300b-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="3300b-109">Une telle nomenclature n'indique pas de site et est valide pour plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="3300b-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="3300b-110">Si une nomenclature générale existe, elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="3300b-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="3300b-111">S'il n'y a aucune version de nomenclature à utiliser, l'éclatement de la demande est arrêté à ce stade.</span><span class="sxs-lookup"><span data-stu-id="3300b-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="3300b-112">Une version de nomenclature valide (spécifique au site ou générale) doit satisfaire aux critères requis de date et de quantité.</span><span class="sxs-lookup"><span data-stu-id="3300b-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>






