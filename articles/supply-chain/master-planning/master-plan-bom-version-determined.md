---
title: Déterminer la version de nomenclature
description: Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 766c857cca603f84bb7fcef2c7eea3bc76620c19
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428127"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="a8bcf-103">Déterminer la version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="a8bcf-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8bcf-104">Lors de l'éclatement d'une demande, si le type d'ordre par défaut d'un article est défini sur Production, le moteur de planification détecte une version de nomenclature valide dans le site.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="a8bcf-105">La dimension du site est toujours identifiée et indiquée dans la transaction de demande.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="a8bcf-106">Le processus suivant permet de déterminer la version de nomenclature à utiliser :</span><span class="sxs-lookup"><span data-stu-id="a8bcf-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="a8bcf-107">Si une version de nomenclature est définie pour l'article dans le site de la demande, la nomenclature spécifique au site est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="a8bcf-108">Si aucune version de nomenclature n'est définie pour l'article dans le site de la demande, une nomenclature générale est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="a8bcf-109">Une telle nomenclature n'indique pas de site et est valide pour plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="a8bcf-110">Si une nomenclature générale existe, elle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="a8bcf-111">S'il n'y a aucune version de nomenclature à utiliser, l'éclatement de la demande est arrêté à ce stade.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="a8bcf-112">Une version de nomenclature valide (spécifique au site ou générale) doit satisfaire aux critères requis de date et de quantité.</span><span class="sxs-lookup"><span data-stu-id="a8bcf-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>





