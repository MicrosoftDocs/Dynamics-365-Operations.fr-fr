---
title: "Rapport financier du relevé des revenus"
description: "Cet article décrit l'état par défaut des comptes de résultats. Il décrit également les blocs de construction associés à cet état."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8ca90b949a1a2b5af4a0fd78ddf80d5add2565b9
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="f18d4-104">Rapport financier du relevé des revenus</span><span class="sxs-lookup"><span data-stu-id="f18d4-104">Income statement financial report</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f18d4-105">Cet article décrit l'état par défaut des comptes de résultats.</span><span class="sxs-lookup"><span data-stu-id="f18d4-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="f18d4-106">Il décrit également les blocs de construction associés à cet état.</span><span class="sxs-lookup"><span data-stu-id="f18d4-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="f18d4-107">Rapport par défaut du relevé des revenus</span><span class="sxs-lookup"><span data-stu-id="f18d4-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="f18d4-108">État par défaut</span><span class="sxs-lookup"><span data-stu-id="f18d4-108">Default report</span></span>             | <span data-ttu-id="f18d4-109">Fonction</span><span class="sxs-lookup"><span data-stu-id="f18d4-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f18d4-110">Relevé des revenus – Par défaut.</span><span class="sxs-lookup"><span data-stu-id="f18d4-110">Income Statement – Default</span></span> | <span data-ttu-id="f18d4-111">Permet d'afficher la rentabilité de l'organisation pour la période en cours ainsi que pour l'année en cours.</span><span class="sxs-lookup"><span data-stu-id="f18d4-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="f18d4-112">Blocs élémentaires</span><span class="sxs-lookup"><span data-stu-id="f18d4-112">Building blocks</span></span>
<span data-ttu-id="f18d4-113">Le rapport financier du relevé des revenus utilise les blocs élémentaires suivants.</span><span class="sxs-lookup"><span data-stu-id="f18d4-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="f18d4-114">Rapport par défaut</span><span class="sxs-lookup"><span data-stu-id="f18d4-114">Default report</span></span>             | <span data-ttu-id="f18d4-115">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="f18d4-115">Row definition</span></span>                     | <span data-ttu-id="f18d4-116">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="f18d4-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="f18d4-117">Relevé des revenus - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f18d4-117">Income Statement - Default</span></span> | <span data-ttu-id="f18d4-118">Récapitulatif du relevé des revenus - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f18d4-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="f18d4-119">Périodique et Année en cours - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f18d4-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="f18d4-120">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="f18d4-120">Row definition</span></span>

<span data-ttu-id="f18d4-121">La définition de ligne, Récapitulatif du relevé des revenus - Par défaut, contient une section pour chaque partie d'un relevé de revenus traditionnel.</span><span class="sxs-lookup"><span data-stu-id="f18d4-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="f18d4-122">La dimension Catégorie de compte principal est utilisée afin d'établir cette définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="f18d4-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="f18d4-123">Par conséquent, n'importe qui peut générer le rapport sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="f18d4-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="f18d4-124">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="f18d4-124">Column Definition</span></span>

<span data-ttu-id="f18d4-125">Les définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="f18d4-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="f18d4-126">**Périodique et Année en cours – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="f18d4-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="f18d4-127">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="f18d4-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f18d4-128">**DF** – Données financières pour la période en cours</span><span class="sxs-lookup"><span data-stu-id="f18d4-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="f18d4-129">**DF** – Données financières pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="f18d4-129">**FD** – Financial data for the year to date</span></span>

 

<a name="see-also"></a><span data-ttu-id="f18d4-130">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f18d4-130">See also</span></span>
--------

[<span data-ttu-id="f18d4-131">États financiers</span><span class="sxs-lookup"><span data-stu-id="f18d4-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="f18d4-132">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="f18d4-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="f18d4-133">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="f18d4-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




