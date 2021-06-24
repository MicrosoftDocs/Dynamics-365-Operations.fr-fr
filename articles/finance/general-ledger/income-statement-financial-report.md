---
title: Rapport financier du relevé des revenus
description: Cet article décrit l’état par défaut des comptes de résultats. Il décrit également les blocs de construction associés à cet état.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ab5e7a2675705cc2265b7f894d9b12d4465aea1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187818"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="b54e3-104">Rapport financier du relevé des revenus</span><span class="sxs-lookup"><span data-stu-id="b54e3-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b54e3-105">Cet article décrit l’état par défaut des comptes de résultats.</span><span class="sxs-lookup"><span data-stu-id="b54e3-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="b54e3-106">Il décrit également les blocs de construction associés à cet état.</span><span class="sxs-lookup"><span data-stu-id="b54e3-106">It also describes the building blocks that are associated with this report.</span></span> 

## <a name="default-income-statement-report"></a><span data-ttu-id="b54e3-107">Rapport par défaut du relevé des revenus</span><span class="sxs-lookup"><span data-stu-id="b54e3-107">Default income statement report</span></span>

| <span data-ttu-id="b54e3-108">État par défaut</span><span class="sxs-lookup"><span data-stu-id="b54e3-108">Default report</span></span>             | <span data-ttu-id="b54e3-109">Fonction</span><span class="sxs-lookup"><span data-stu-id="b54e3-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b54e3-110">Relevé des revenus – Par défaut.</span><span class="sxs-lookup"><span data-stu-id="b54e3-110">Income Statement – Default</span></span> | <span data-ttu-id="b54e3-111">Permet d’afficher la rentabilité de l’organisation pour la période en cours ainsi que pour l’année en cours.</span><span class="sxs-lookup"><span data-stu-id="b54e3-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="b54e3-112">Blocs élémentaires</span><span class="sxs-lookup"><span data-stu-id="b54e3-112">Building blocks</span></span>
<span data-ttu-id="b54e3-113">Le rapport financier du relevé des revenus utilise les blocs élémentaires suivants.</span><span class="sxs-lookup"><span data-stu-id="b54e3-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="b54e3-114">Rapport par défaut</span><span class="sxs-lookup"><span data-stu-id="b54e3-114">Default report</span></span>             | <span data-ttu-id="b54e3-115">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="b54e3-115">Row definition</span></span>                     | <span data-ttu-id="b54e3-116">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="b54e3-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="b54e3-117">Relevé des revenus – Par défaut</span><span class="sxs-lookup"><span data-stu-id="b54e3-117">Income Statement - Default</span></span> | <span data-ttu-id="b54e3-118">Récapitulatif du relevé des revenus – Par défaut</span><span class="sxs-lookup"><span data-stu-id="b54e3-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="b54e3-119">Périodique et Année en cours – Par défaut</span><span class="sxs-lookup"><span data-stu-id="b54e3-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="b54e3-120">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="b54e3-120">Row definition</span></span>

<span data-ttu-id="b54e3-121">La définition de ligne, Récapitulatif du relevé des revenus – Par défaut, contient une section pour chaque partie d’un relevé de revenus traditionnel.</span><span class="sxs-lookup"><span data-stu-id="b54e3-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="b54e3-122">La dimension Catégorie de compte principal est utilisée afin d’établir cette définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="b54e3-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="b54e3-123">Par conséquent, n’importe qui peut générer le rapport sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="b54e3-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="b54e3-124">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="b54e3-124">Column Definition</span></span>

<span data-ttu-id="b54e3-125">Les définitions de colonne contiennent différents types de colonnes afin d’offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="b54e3-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="b54e3-126">**Périodique et Année en cours – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="b54e3-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="b54e3-127">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="b54e3-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="b54e3-128">**DF** – Données financières pour la période en cours</span><span class="sxs-lookup"><span data-stu-id="b54e3-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="b54e3-129">**DF** – Données financières pour l’année en cours</span><span class="sxs-lookup"><span data-stu-id="b54e3-129">**FD** – Financial data for the year to date</span></span>



## <a name="additional-resources"></a><span data-ttu-id="b54e3-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b54e3-130">Additional resources</span></span>

[<span data-ttu-id="b54e3-131">Vue d’ensemble des états financiers</span><span class="sxs-lookup"><span data-stu-id="b54e3-131">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="b54e3-132">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="b54e3-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="b54e3-133">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="b54e3-133">Dynamics Financial Reporting Blog</span></span>](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]