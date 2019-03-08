---
title: États financiers du bilan
description: Cet article décrit les états par défaut des bilans. Il décrit également les blocs de construction associés à ces états.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ff778af1bb3af3a10132ab3193ad1cd5daa24e1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "342291"
---
# <a name="balance-sheet-financial-reports"></a><span data-ttu-id="f724c-104">États financiers du bilan</span><span class="sxs-lookup"><span data-stu-id="f724c-104">Balance sheet financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f724c-105">Cet article décrit les états par défaut des bilans.</span><span class="sxs-lookup"><span data-stu-id="f724c-105">This article describes the default reports for balance sheets.</span></span> <span data-ttu-id="f724c-106">Il décrit également les blocs de construction associés à ces états.</span><span class="sxs-lookup"><span data-stu-id="f724c-106">It also describes the building blocks that are associated with these reports.</span></span> 

<a name="default-balance-sheet-reports"></a><span data-ttu-id="f724c-107">États du bilan par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-107">Default balance sheet reports</span></span>
-----------------------------

<span data-ttu-id="f724c-108">Par défaut, le bilan se distingue par deux états.</span><span class="sxs-lookup"><span data-stu-id="f724c-108">There are two default balance sheet reports.</span></span> <span data-ttu-id="f724c-109">Dans un état, les sections sont empilées.</span><span class="sxs-lookup"><span data-stu-id="f724c-109">On one report, the sections are stacked.</span></span> <span data-ttu-id="f724c-110">Dans l'autre état, les sections sont côte à côte.</span><span class="sxs-lookup"><span data-stu-id="f724c-110">On the other report, the sections are side by side.</span></span>

| <span data-ttu-id="f724c-111">État par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-111">Default report</span></span>                       | <span data-ttu-id="f724c-112">Fonction</span><span class="sxs-lookup"><span data-stu-id="f724c-112">What it does</span></span>                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f724c-113">Bilan – Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-113">Balance Sheet – Default</span></span>              | <span data-ttu-id="f724c-114">Permet d'afficher la position financière de l'organisation pour l'année.</span><span class="sxs-lookup"><span data-stu-id="f724c-114">Provides a view of the organization's financial position for the year.</span></span>                                                                 |
| <span data-ttu-id="f724c-115">Bilan côte à côte bilan – Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-115">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="f724c-116">Permet d'afficher la position financière de l'organisation pour l'année.</span><span class="sxs-lookup"><span data-stu-id="f724c-116">Provides a view of the organization's financial position for the year.</span></span> <span data-ttu-id="f724c-117">Les actifs et passifs et les capitaux propres des actionnaires sont affichés côte à côte.</span><span class="sxs-lookup"><span data-stu-id="f724c-117">Assets and liability and shareholder’s equity are side by side.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="f724c-118">Blocs élémentaires</span><span class="sxs-lookup"><span data-stu-id="f724c-118">Building blocks</span></span>
<span data-ttu-id="f724c-119">Les rapports financiers du relevé des revenus utilisent les blocs élémentaires suivants.</span><span class="sxs-lookup"><span data-stu-id="f724c-119">The balance sheet financial reports use the following building blocks.</span></span>

| <span data-ttu-id="f724c-120">État par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-120">Default report</span></span>                       | <span data-ttu-id="f724c-121">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="f724c-121">Row definition</span></span>                       | <span data-ttu-id="f724c-122">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="f724c-122">Column definition</span></span>             |
|--------------------------------------|--------------------------------------|-------------------------------|
| <span data-ttu-id="f724c-123">Bilan - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-123">Balance Sheet - Default</span></span>              | <span data-ttu-id="f724c-124">Bilan - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-124">Balance Sheet - Default</span></span>              | <span data-ttu-id="f724c-125">Année en cours et écart - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-125">YTD and Variance - Default</span></span>    |
| <span data-ttu-id="f724c-126">Bilan côte à côte bilan – Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-126">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="f724c-127">Bilan côte à côte bilan – Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-127">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="f724c-128">Colonne Année en cours - Par défaut</span><span class="sxs-lookup"><span data-stu-id="f724c-128">Year to Date Column - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="f724c-129">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="f724c-129">Row definition</span></span>

<span data-ttu-id="f724c-130">Les définitions de ligne pour les deux états du bilan contiennent les sections de chaque partie d'un bilan traditionnel.</span><span class="sxs-lookup"><span data-stu-id="f724c-130">The row definitions for both balance sheet reports contain sections for each part of a traditional balance sheet.</span></span> <span data-ttu-id="f724c-131">L'état côte à côte inclut un saut de colonne, de telle sorte que le passif et les capitaux propres du propriétaire s'affichent en regard de l'actif.</span><span class="sxs-lookup"><span data-stu-id="f724c-131">The side-by-side report includes a column break, so that liability and the owner’s equity appear next to assets.</span></span> <span data-ttu-id="f724c-132">La dimension Catégorie de compte principal est utilisée afin d'établir les deux définitions de ligne.</span><span class="sxs-lookup"><span data-stu-id="f724c-132">The Main Account Category dimension is used to build both row definitions.</span></span> <span data-ttu-id="f724c-133">Par conséquent, n'importe qui peut générer les rapports sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="f724c-133">Therefore, anyone can generate the reports without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="f724c-134">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="f724c-134">Column definition</span></span>

<span data-ttu-id="f724c-135">Les définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="f724c-135">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="f724c-136">**Année en cours et écart – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="f724c-136">**YTD and Variance – Default column types:**</span></span>
    -   <span data-ttu-id="f724c-137">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="f724c-137">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f724c-138">**DF** – Données financières pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="f724c-138">**FD** – Year-to-date financial data for the current year</span></span>
    -   <span data-ttu-id="f724c-139">**DF** – Données financières pour l'année passée</span><span class="sxs-lookup"><span data-stu-id="f724c-139">**FD** – Year-to-date financial data for the last year</span></span>
    -   <span data-ttu-id="f724c-140">**CALC** – Écart résultant de la soustraction entre l'année passée et l'année en cours</span><span class="sxs-lookup"><span data-stu-id="f724c-140">**CALC** – The variance from subtracting last year from this year</span></span>

<!-- -->

-   <span data-ttu-id="f724c-141">**Colonne Année en cours – Par défaut :**</span><span class="sxs-lookup"><span data-stu-id="f724c-141">**Year to Date Column – Default:**</span></span>
    -   <span data-ttu-id="f724c-142">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="f724c-142">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="f724c-143">**DF** – Données financières pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="f724c-143">**FD** – Year-to-date financial data for the current year</span></span>



<a name="additional-resources"></a><span data-ttu-id="f724c-144">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f724c-144">Additional resources</span></span>
--------

[<span data-ttu-id="f724c-145">États financiers</span><span class="sxs-lookup"><span data-stu-id="f724c-145">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="f724c-146">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="f724c-146">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="f724c-147">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="f724c-147">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)



