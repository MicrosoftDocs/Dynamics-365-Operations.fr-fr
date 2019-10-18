---
title: Méthodes et conventions d'amortissement
description: Cet article fournit une vue d'ensemble des conventions d'amortissement et des méthodes d'amortissement prises en charge par Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f1320d0adaad783f856ed6404039e7954920340
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187335"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="c91a6-103">Méthodes et conventions d'amortissement</span><span class="sxs-lookup"><span data-stu-id="c91a6-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c91a6-104">Cet article fournit une vue d'ensemble des conventions d'amortissement et des méthodes d'amortissement prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c91a6-104">This article provides an overview of the supported depreciation conventions and depreciation methods.</span></span>

<span data-ttu-id="c91a6-105">Vous pouvez sélectionner diverses méthodes et conventions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="c91a6-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="c91a6-106">L'objet des méthodes est l'attribution de la valeur amortissable de l'immobilisation dans des périodes fiscales.</span><span class="sxs-lookup"><span data-stu-id="c91a6-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="c91a6-107">La valeur amortissable de l'immobilisation correspond au prix d'acquisition, moins la valeur de mise au rebut, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c91a6-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="c91a6-108">Si vous utilisez des conventions d'amortissement et que vous modifiez la dernière date d'exécution de l'amortissement pour une immobilisation, ce qui fait que certains amortissements ne sont pas pris en compte, l'amortissement de l'année précédente peut être supérieur ou inférieur aux prévisions.</span><span class="sxs-lookup"><span data-stu-id="c91a6-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="c91a6-109">L'amortissement est ajusté du nombre de périodes d'amortissement affectées par la modification de la dernière date d'exécution de l'amortissement.</span><span class="sxs-lookup"><span data-stu-id="c91a6-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="c91a6-110">Par exemple, si vous utilisez la convention d'amortissement semestrielle sur trois ans, l'amortissement dure normalement 3 ans 1/2.</span><span class="sxs-lookup"><span data-stu-id="c91a6-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="c91a6-111">Si vous modifiez la dernière date d'exécution de l'amortissement au cours des 3 ans 1/2, la dernière année d'amortissement se déplace sur le nombre de périodes affectées.</span><span class="sxs-lookup"><span data-stu-id="c91a6-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="c91a6-112">Si vous déplacez la date de trois mois, la dernière année aura neuf mois d'amortissement, contre six normalement.</span><span class="sxs-lookup"><span data-stu-id="c91a6-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="c91a6-113">Vous pouvez choisir parmi les conventions d'amortissement suivantes.</span><span class="sxs-lookup"><span data-stu-id="c91a6-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="c91a6-114">Semestre</span><span class="sxs-lookup"><span data-stu-id="c91a6-114">Half year</span></span>
-   <span data-ttu-id="c91a6-115">Mois complet</span><span class="sxs-lookup"><span data-stu-id="c91a6-115">Full month</span></span>
-   <span data-ttu-id="c91a6-116">Mi-trimestre</span><span class="sxs-lookup"><span data-stu-id="c91a6-116">Mid quarter</span></span>
-   <span data-ttu-id="c91a6-117">Mi-mois (1er du mois)</span><span class="sxs-lookup"><span data-stu-id="c91a6-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="c91a6-118">Mi-mois (15 du mois)</span><span class="sxs-lookup"><span data-stu-id="c91a6-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="c91a6-119">Semestre (début d'exercice)</span><span class="sxs-lookup"><span data-stu-id="c91a6-119">Half year (start of year)</span></span>
-   <span data-ttu-id="c91a6-120">Semestre (exercice suivant)</span><span class="sxs-lookup"><span data-stu-id="c91a6-120">Half year (next year)</span></span>

<span data-ttu-id="c91a6-121">Vous pouvez choisir parmi les méthodes d'amortissement suivantes.</span><span class="sxs-lookup"><span data-stu-id="c91a6-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="c91a6-122">Durée de vie linéaire</span><span class="sxs-lookup"><span data-stu-id="c91a6-122">Straight line service life</span></span>
-   <span data-ttu-id="c91a6-123">Dégressif</span><span class="sxs-lookup"><span data-stu-id="c91a6-123">Reducing balance</span></span>
-   <span data-ttu-id="c91a6-124">Manuel</span><span class="sxs-lookup"><span data-stu-id="c91a6-124">Manual</span></span>
-   <span data-ttu-id="c91a6-125">Facteur</span><span class="sxs-lookup"><span data-stu-id="c91a6-125">Factor</span></span>
-   <span data-ttu-id="c91a6-126">Consommation</span><span class="sxs-lookup"><span data-stu-id="c91a6-126">Consumption</span></span>
-   <span data-ttu-id="c91a6-127">Durée de vie linéaire restante</span><span class="sxs-lookup"><span data-stu-id="c91a6-127">Straight line life remaining</span></span>
-   <span data-ttu-id="c91a6-128">Amortissement dégressif de 200 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-128">200% reducing balance</span></span>
-   <span data-ttu-id="c91a6-129">Amortissement dégressif de 175 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-129">175% reducing balance</span></span>
-   <span data-ttu-id="c91a6-130">Amortissement dégressif de 150 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-130">150% reducing balance</span></span>
-   <span data-ttu-id="c91a6-131">Amortissement dégressif de 125 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="c91a6-132">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c91a6-132">Additional resources</span></span>
--------

[<span data-ttu-id="c91a6-133">Amortissement des immobilisations</span><span class="sxs-lookup"><span data-stu-id="c91a6-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="c91a6-134">Amortissement linéaire sur la durée de vie</span><span class="sxs-lookup"><span data-stu-id="c91a6-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="c91a6-135">Amortissement dégressif</span><span class="sxs-lookup"><span data-stu-id="c91a6-135">Reducing balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="c91a6-136">Amortissement manuel</span><span class="sxs-lookup"><span data-stu-id="c91a6-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="c91a6-137">Amortissement paramétrable</span><span class="sxs-lookup"><span data-stu-id="c91a6-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="c91a6-138">Amortissement de consommation</span><span class="sxs-lookup"><span data-stu-id="c91a6-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="c91a6-139">Amortissement linéaire sur la durée de vie restante</span><span class="sxs-lookup"><span data-stu-id="c91a6-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="c91a6-140">Amortissement dégressif de 125 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="c91a6-141">Amortissement dégressif de 150 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="c91a6-142">Amortissement dégressif de 175 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="c91a6-143">Amortissement dégressif de 200 %</span><span class="sxs-lookup"><span data-stu-id="c91a6-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)



