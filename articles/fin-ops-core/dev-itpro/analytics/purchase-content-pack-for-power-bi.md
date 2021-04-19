---
title: Contenu Power BI Analyse des dépenses et des achats
description: Cette rubrique décrit ce qui est inclus dans le contenu Power BI Analyse des dépenses d’achat.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9741b5f30f5e62b9e80000953113377fe016253
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749367"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="f0791-103">Contenu Power BI Analyse des dépenses et des achats</span><span class="sxs-lookup"><span data-stu-id="f0791-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0791-104">Cette rubrique décrit ce qui est inclus dans le contenu Microsoft Power BI **Analyse des dépenses d’achat**.</span><span class="sxs-lookup"><span data-stu-id="f0791-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="f0791-105">Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.</span><span class="sxs-lookup"><span data-stu-id="f0791-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="f0791-106">Présentation</span><span class="sxs-lookup"><span data-stu-id="f0791-106">Overview</span></span>

<span data-ttu-id="f0791-107">Le contenu Power BI **Analyse des dépenses d’achat** a été conçu pour aider les directeurs des achats et autres gestionnaires qui sont responsables des budgets à effectuer le suivi des dépenses d’achat.</span><span class="sxs-lookup"><span data-stu-id="f0791-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="f0791-108">Les gestionnaires peuvent analyser les dépenses d’achat des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="f0791-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="f0791-109">Achat depuis le début de l’année (par groupe de fournisseurs et fournisseurs individuels, catégorie d’approvisionnement et produits individuels et emplacement du fournisseur)</span><span class="sxs-lookup"><span data-stu-id="f0791-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="f0791-110">Changement d’achat d’une année sur l’autre (par groupe de fournisseurs et catégorie d’approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="f0791-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="f0791-111">Le contenu utilise les données transactionnelles d’achats, et fournit une vue globale des chiffres d’achats à l’échelle de l’entreprise et une répartition des dépenses d’achat par fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="f0791-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="f0791-112">Les rapports mettent l’accent sur les changements dans les dépenses d’achat au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="f0791-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="f0791-113">Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="f0791-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="f0791-114">En outre, les graphiques montrent les dépenses des différentes catégories d’approvisionnement et groupes de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="f0791-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="f0791-115">Ainsi, les gestionnaires régionaux et de catégories peuvent utiliser les graphiques pour aider à identifier les changements dans le comportement des dépenses.</span><span class="sxs-lookup"><span data-stu-id="f0791-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="f0791-116">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="f0791-116">Accessing the Power BI content</span></span>
<span data-ttu-id="f0791-117">Le contenu Power BI **Analyse des dépenses d’achat** s’affiche sur la page **Analyse des dépenses et des achats** (**Approvisionnements** \> **Recherches et états** \> **Analyse des performances d’achat** \> **Analyse des dépenses et des achats**).</span><span class="sxs-lookup"><span data-stu-id="f0791-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="f0791-118">Mesures incluses dans le pack de contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="f0791-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="f0791-119">Le pack de contenu Power BI **Analyse des dépenses d’achat** comprend un état constitué d’un ensemble d’éléments de mesure.</span><span class="sxs-lookup"><span data-stu-id="f0791-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="f0791-120">Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux.</span><span class="sxs-lookup"><span data-stu-id="f0791-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="f0791-121">Les sections suivantes offrent une vue d’ensemble des visualisations.</span><span class="sxs-lookup"><span data-stu-id="f0791-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="f0791-122">Page État des achats par fournisseur</span><span class="sxs-lookup"><span data-stu-id="f0791-122">Purchase by vendor report page</span></span>
<span data-ttu-id="f0791-123">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-123">**Charts**</span></span>
- <span data-ttu-id="f0791-124">Les 10 principaux vendeurs par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="f0791-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="f0791-125">Achat total par groupe de fournisseurs / pays / nom (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="f0791-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="f0791-126">Achat par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="f0791-127">Achat moyen par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="f0791-128">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="f0791-128">**Tiles**</span></span>
- <span data-ttu-id="f0791-129">Total des achats</span><span class="sxs-lookup"><span data-stu-id="f0791-129">Total purchase</span></span>
- <span data-ttu-id="f0791-130">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-130">YOY purchase growth</span></span>
- <span data-ttu-id="f0791-131">Nombre total de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="f0791-131">Total # vendors</span></span>
- <span data-ttu-id="f0791-132">Nombre total de fournisseurs actifs</span><span class="sxs-lookup"><span data-stu-id="f0791-132">Total # of active vendors</span></span>

<span data-ttu-id="f0791-133">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="f0791-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="f0791-134">Page État des achats par produit</span><span class="sxs-lookup"><span data-stu-id="f0791-134">Purchase by product report page</span></span>

<span data-ttu-id="f0791-135">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-135">**Charts**</span></span>
- <span data-ttu-id="f0791-136">Achat par catégorie d’approvisionnement / nom du produit (histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="f0791-137">Achat total par catégorie d’approvisionnement / nom du produit (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="f0791-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="f0791-138">Les 10 principaux produits par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="f0791-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="f0791-139">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="f0791-139">**Tiles**</span></span>
- <span data-ttu-id="f0791-140">Nombre total de produits</span><span class="sxs-lookup"><span data-stu-id="f0791-140">Total # of products</span></span></li>
- <span data-ttu-id="f0791-141">Nombre total de produit actifs et pourcentage du total de produits</span><span class="sxs-lookup"><span data-stu-id="f0791-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="f0791-142">Nombre de produits constituant 80 % de l’achat</span><span class="sxs-lookup"><span data-stu-id="f0791-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="f0791-143">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="f0791-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="f0791-144">Page État des achats par période</span><span class="sxs-lookup"><span data-stu-id="f0791-144">Purchase by period report page</span></span>
<span data-ttu-id="f0791-145">Cette page affiche les achats de cette année et de l’année dernière, et la croissance par catégorie d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="f0791-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="f0791-146">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-146">**Charts**</span></span> 
- <span data-ttu-id="f0791-147">Achat par mois/jour (histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="f0791-148">Variation en cumul annuel des achats (graphique cascade)</span><span class="sxs-lookup"><span data-stu-id="f0791-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="f0791-149">Croissance en cumul annuel des achats totaux (histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="f0791-150">Relevé d’approvisionnement (matrice)</span><span class="sxs-lookup"><span data-stu-id="f0791-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="f0791-151">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="f0791-151">**Tiles**</span></span>
- <span data-ttu-id="f0791-152">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-152">YOY purchase growth</span></span>
- <span data-ttu-id="f0791-153">% de croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-153">YOY purchase growth %</span></span>

<span data-ttu-id="f0791-154">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="f0791-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="f0791-155">Page État des achats par emplacement de fournisseur</span><span class="sxs-lookup"><span data-stu-id="f0791-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="f0791-156">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-156">**Charts**</span></span>
- <span data-ttu-id="f0791-157">Achat par ville</span><span class="sxs-lookup"><span data-stu-id="f0791-157">Purchase by city</span></span>
- <span data-ttu-id="f0791-158">% de croissance en cumul annuel des achats</span><span class="sxs-lookup"><span data-stu-id="f0791-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="f0791-159">Achat par pays</span><span class="sxs-lookup"><span data-stu-id="f0791-159">Purchase by country</span></span>

<span data-ttu-id="f0791-160">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="f0791-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="f0791-161">Page État des analyses des dépenses d’achat par période</span><span class="sxs-lookup"><span data-stu-id="f0791-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="f0791-162">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-162">**Charts**</span></span> 
- <span data-ttu-id="f0791-163">Achats de l’année en cours par mois / jour (graphique en courbes)</span><span class="sxs-lookup"><span data-stu-id="f0791-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="f0791-164">Achats de l’année en cours et de l’année dernière (graphique en courbes et histogramme)</span><span class="sxs-lookup"><span data-stu-id="f0791-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="f0791-165">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="f0791-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="f0791-166">Page État des analyses des dépenses d’achat par fournisseur</span><span class="sxs-lookup"><span data-stu-id="f0791-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="f0791-167">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="f0791-167">**Charts**</span></span> 
- <span data-ttu-id="f0791-168">10 principaux achats fournisseur en % (icône conique)</span><span class="sxs-lookup"><span data-stu-id="f0791-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="f0791-169">10 premiers fournisseurs avec dépenses augmentées en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="f0791-170">10 premiers fournisseurs avec dépenses réduites en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="f0791-171">**Exemple :** 
</span><span class="sxs-lookup"><span data-stu-id="f0791-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="f0791-172">Modèle de données et entités</span><span class="sxs-lookup"><span data-stu-id="f0791-172">Data model and entities</span></span>
<span data-ttu-id="f0791-173">Les données suivantes sont utilisées pour remplir les pages d’état dans le contenu Power BI **Analyse des dépenses d’achat**.</span><span class="sxs-lookup"><span data-stu-id="f0791-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="f0791-174">Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="f0791-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="f0791-175">Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses.</span><span class="sxs-lookup"><span data-stu-id="f0791-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="f0791-176">Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="f0791-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="f0791-177">Les mesures globales dans ce pack de contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d’achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="f0791-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="f0791-178">Pour enregistrer les mesures globales du cube dans le magasin d’entités, vous devez les rendre déployables.</span><span class="sxs-lookup"><span data-stu-id="f0791-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="f0791-179">Pour plus d’informations, voir la procédure d’enregistrement des mesures globales dans le magasin d’entités dans [Intégration de Power BI avec le magasin d’entités](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="f0791-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="f0791-180">Les mesures globales clés suivantes sont disponibles directement depuis l’entité Lignes de facture et sont utilisées comme base du contenu.</span><span class="sxs-lookup"><span data-stu-id="f0791-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="f0791-181">Entité</span><span class="sxs-lookup"><span data-stu-id="f0791-181">Entity</span></span>        | <span data-ttu-id="f0791-182">Mesures globales clés</span><span class="sxs-lookup"><span data-stu-id="f0791-182">Key aggregate measurements</span></span> | <span data-ttu-id="f0791-183">Source de données</span><span class="sxs-lookup"><span data-stu-id="f0791-183">Data source</span></span>                                 | <span data-ttu-id="f0791-184">Champ</span><span class="sxs-lookup"><span data-stu-id="f0791-184">Field</span></span>              | <span data-ttu-id="f0791-185">Description</span><span class="sxs-lookup"><span data-stu-id="f0791-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="f0791-186">Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="f0791-186">Invoice lines</span></span> | <span data-ttu-id="f0791-187">Achats</span><span class="sxs-lookup"><span data-stu-id="f0791-187">Purchase</span></span>                   | <span data-ttu-id="f0791-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="f0791-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="f0791-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="f0791-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="f0791-190">Montant dans la monnaie de compte.</span><span class="sxs-lookup"><span data-stu-id="f0791-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="f0791-191">Le tableau suivant indique les mesures principales du contenu qui sont calculées à partir de l’entité Lignes de facture.</span><span class="sxs-lookup"><span data-stu-id="f0791-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="f0791-192">Mesure</span><span class="sxs-lookup"><span data-stu-id="f0791-192">Measure</span></span>               | <span data-ttu-id="f0791-193">Calcul</span><span class="sxs-lookup"><span data-stu-id="f0791-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f0791-194">Achats de l’année en cours</span><span class="sxs-lookup"><span data-stu-id="f0791-194">Purchase current year</span></span> | <span data-ttu-id="f0791-195">Achat de l’année en cours = SUM(’Invoice lines’\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="f0791-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="f0791-196">Achats l’année dernière</span><span class="sxs-lookup"><span data-stu-id="f0791-196">Purchase last year</span></span>    | <span data-ttu-id="f0791-197">Achats l’année dernière = CALCULATE(SUM(’Invoice lines’\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="f0791-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="f0791-198">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="f0791-198">YOY purchase growth</span></span>   | <span data-ttu-id="f0791-199">Croissance d’achat en cumul annuel = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="f0791-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="f0791-200">Les dimensions clés suivantes dans le contenu sont utilisées comme filtres pour diviser les mesures globales afin d’atteindre une meilleure granularité et d’obtenir une analyse plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="f0791-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="f0791-201">Entité</span><span class="sxs-lookup"><span data-stu-id="f0791-201">Entity</span></span>                 | <span data-ttu-id="f0791-202">Exemples d’attributs</span><span class="sxs-lookup"><span data-stu-id="f0791-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="f0791-203">Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="f0791-203">Vendors</span></span>                | <span data-ttu-id="f0791-204">Groupes de fournisseurs, Pays ou régions des fournisseurs, Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="f0791-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="f0791-205">Produits</span><span class="sxs-lookup"><span data-stu-id="f0791-205">Products</span></span>               | <span data-ttu-id="f0791-206">Numéro de produit, Nom du produit, Nom des groupes d’articles</span><span class="sxs-lookup"><span data-stu-id="f0791-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="f0791-207">Catégories d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="f0791-207">Procurement categories</span></span> | <span data-ttu-id="f0791-208">Catégorie d’approvisionnement, Noms des catégories d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="f0791-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="f0791-209">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="f0791-209">Legal entities</span></span>         | <span data-ttu-id="f0791-210">Nom de l’entité juridique</span><span class="sxs-lookup"><span data-stu-id="f0791-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="f0791-211">dates ;</span><span class="sxs-lookup"><span data-stu-id="f0791-211">Dates</span></span>                  | <span data-ttu-id="f0791-212">Dates, Contrepartie de l’année</span><span class="sxs-lookup"><span data-stu-id="f0791-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="f0791-213">Par défaut, le contenu affiche les données pour l’année civile en cours.</span><span class="sxs-lookup"><span data-stu-id="f0791-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="f0791-214">Toutefois, vous pouvez modifier le filtre date dans la section de filtres d’état.</span><span class="sxs-lookup"><span data-stu-id="f0791-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="f0791-215">Vous pouvez également modifier le filtre par société.</span><span class="sxs-lookup"><span data-stu-id="f0791-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]