---
title: Contenu Power BI Analyse des dépenses et des achats
description: Cette rubrique décrit ce qui est inclus dans le contenu Power BI Analyse des dépenses d’achat. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3f556cf2e506c57e465c2a86485d2cdd4cf8b65e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680612"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="33a41-104">Contenu Power BI Analyse des dépenses et des achats</span><span class="sxs-lookup"><span data-stu-id="33a41-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33a41-105">Cette rubrique décrit ce qui est inclus dans le contenu Power BI **Analyse des dépenses d’achat**.</span><span class="sxs-lookup"><span data-stu-id="33a41-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="33a41-106">Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.</span><span class="sxs-lookup"><span data-stu-id="33a41-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="33a41-107">Présentation</span><span class="sxs-lookup"><span data-stu-id="33a41-107">Overview</span></span>

<span data-ttu-id="33a41-108">Le contenu Power BI **Analyse des dépenses d’achat** a été conçu pour aider les directeurs des achats et autres gestionnaires qui sont responsables des budgets à effectuer le suivi des dépenses d’achat.</span><span class="sxs-lookup"><span data-stu-id="33a41-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="33a41-109">Les gestionnaires peuvent analyser les dépenses d’achat des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="33a41-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="33a41-110">Achat depuis le début de l’année (par groupe de fournisseurs et fournisseurs individuels, catégorie d’approvisionnement et produits individuels et emplacement du fournisseur)</span><span class="sxs-lookup"><span data-stu-id="33a41-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="33a41-111">Changement d’achat d’une année sur l’autre (par groupe de fournisseurs et catégorie d’approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="33a41-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="33a41-112">Le contenu utilise les données transactionnelles d’achats, et fournit une vue globale des chiffres d’achats à l’échelle de l’entreprise et une répartition des dépenses d’achat par fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="33a41-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="33a41-113">Les rapports mettent l’accent sur les changements dans les dépenses d’achat au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="33a41-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="33a41-114">Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="33a41-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="33a41-115">En outre, les graphiques montrent les dépenses des différentes catégories d’approvisionnement et groupes de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="33a41-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="33a41-116">Ainsi, les gestionnaires régionaux et de catégories peuvent utiliser les graphiques pour aider à identifier les changements dans le comportement des dépenses.</span><span class="sxs-lookup"><span data-stu-id="33a41-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="33a41-117">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="33a41-117">Accessing the Power BI content</span></span>
<span data-ttu-id="33a41-118">Le contenu Power BI **Analyse des dépenses d’achat** s’affiche sur la page **Analyse des dépenses et des achats** (**Approvisionnements** \> **Recherches et états** \> **Analyse des performances d’achat** \> **Analyse des dépenses et des achats**).</span><span class="sxs-lookup"><span data-stu-id="33a41-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="33a41-119">Mesures incluses dans le pack de contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="33a41-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="33a41-120">Le pack de contenu Power BI **Analyse des dépenses d’achat** comprend un état constitué d’un ensemble d’éléments de mesure.</span><span class="sxs-lookup"><span data-stu-id="33a41-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="33a41-121">Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux.</span><span class="sxs-lookup"><span data-stu-id="33a41-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="33a41-122">Les sections suivantes offrent une vue d’ensemble des visualisations.</span><span class="sxs-lookup"><span data-stu-id="33a41-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="33a41-123">Page État des achats par fournisseur</span><span class="sxs-lookup"><span data-stu-id="33a41-123">Purchase by vendor report page</span></span>
<span data-ttu-id="33a41-124">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-124">**Charts**</span></span>
- <span data-ttu-id="33a41-125">Les 10 principaux vendeurs par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="33a41-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="33a41-126">Achat total par groupe de fournisseurs / pays / nom (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="33a41-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="33a41-127">Achat par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="33a41-128">Achat moyen par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="33a41-129">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="33a41-129">**Tiles**</span></span>
- <span data-ttu-id="33a41-130">Total des achats</span><span class="sxs-lookup"><span data-stu-id="33a41-130">Total purchase</span></span>
- <span data-ttu-id="33a41-131">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-131">YOY purchase growth</span></span>
- <span data-ttu-id="33a41-132">Nombre total de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="33a41-132">Total # vendors</span></span>
- <span data-ttu-id="33a41-133">Nombre total de fournisseurs actifs</span><span class="sxs-lookup"><span data-stu-id="33a41-133">Total # of active vendors</span></span>

<span data-ttu-id="33a41-134">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="33a41-134">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="33a41-135">Page État des achats par produit</span><span class="sxs-lookup"><span data-stu-id="33a41-135">Purchase by product report page</span></span>

<span data-ttu-id="33a41-136">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-136">**Charts**</span></span>
- <span data-ttu-id="33a41-137">Achat par catégorie d’approvisionnement / nom du produit (histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="33a41-138">Achat total par catégorie d’approvisionnement / nom du produit (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="33a41-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="33a41-139">Les 10 principaux produits par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="33a41-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="33a41-140">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="33a41-140">**Tiles**</span></span>
- <span data-ttu-id="33a41-141">Nombre total de produits</span><span class="sxs-lookup"><span data-stu-id="33a41-141">Total # of products</span></span></li>
- <span data-ttu-id="33a41-142">Nombre total de produit actifs et pourcentage du total de produits</span><span class="sxs-lookup"><span data-stu-id="33a41-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="33a41-143">Nombre de produits constituant 80 % de l’achat</span><span class="sxs-lookup"><span data-stu-id="33a41-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="33a41-144">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="33a41-144">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="33a41-145">Page État des achats par période</span><span class="sxs-lookup"><span data-stu-id="33a41-145">Purchase by period report page</span></span>
<span data-ttu-id="33a41-146">Cette page affiche les achats de cette année et de l’année dernière, et la croissance par catégorie d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="33a41-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="33a41-147">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-147">**Charts**</span></span> 
- <span data-ttu-id="33a41-148">Achat par mois/jour (histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="33a41-149">Variation en cumul annuel des achats (graphique cascade)</span><span class="sxs-lookup"><span data-stu-id="33a41-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="33a41-150">Croissance en cumul annuel des achats totaux (histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="33a41-151">Relevé d’approvisionnement (matrice)</span><span class="sxs-lookup"><span data-stu-id="33a41-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="33a41-152">**Vignettes**</span><span class="sxs-lookup"><span data-stu-id="33a41-152">**Tiles**</span></span>
- <span data-ttu-id="33a41-153">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-153">YOY purchase growth</span></span>
- <span data-ttu-id="33a41-154">% de croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-154">YOY purchase growth %</span></span>

<span data-ttu-id="33a41-155">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="33a41-155">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="33a41-156">Page État des achats par emplacement de fournisseur</span><span class="sxs-lookup"><span data-stu-id="33a41-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="33a41-157">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-157">**Charts**</span></span>
- <span data-ttu-id="33a41-158">Achat par ville</span><span class="sxs-lookup"><span data-stu-id="33a41-158">Purchase by city</span></span>
- <span data-ttu-id="33a41-159">% de croissance en cumul annuel des achats</span><span class="sxs-lookup"><span data-stu-id="33a41-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="33a41-160">Achat par pays</span><span class="sxs-lookup"><span data-stu-id="33a41-160">Purchase by country</span></span>

<span data-ttu-id="33a41-161">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="33a41-161">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="33a41-162">Page État des analyses des dépenses d’achat par période</span><span class="sxs-lookup"><span data-stu-id="33a41-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="33a41-163">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-163">**Charts**</span></span> 
- <span data-ttu-id="33a41-164">Achats de l’année en cours par mois / jour (graphique en courbes)</span><span class="sxs-lookup"><span data-stu-id="33a41-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="33a41-165">Achats de l’année en cours et de l’année dernière (graphique en courbes et histogramme)</span><span class="sxs-lookup"><span data-stu-id="33a41-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="33a41-166">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="33a41-166">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="33a41-167">Page État des analyses des dépenses d’achat par fournisseur</span><span class="sxs-lookup"><span data-stu-id="33a41-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="33a41-168">**Graphiques**</span><span class="sxs-lookup"><span data-stu-id="33a41-168">**Charts**</span></span> 
- <span data-ttu-id="33a41-169">10 principaux achats fournisseur en % (icône conique)</span><span class="sxs-lookup"><span data-stu-id="33a41-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="33a41-170">10 premiers fournisseurs avec dépenses augmentées en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="33a41-171">10 premiers fournisseurs avec dépenses réduites en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="33a41-172">**Exemple :** 
</span><span class="sxs-lookup"><span data-stu-id="33a41-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="33a41-173">Modèle de données et entités</span><span class="sxs-lookup"><span data-stu-id="33a41-173">Data model and entities</span></span>
<span data-ttu-id="33a41-174">Les données suivantes sont utilisées pour remplir les pages d’état dans le contenu Power BI **Analyse des dépenses d’achat**.</span><span class="sxs-lookup"><span data-stu-id="33a41-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="33a41-175">Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="33a41-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="33a41-176">Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses.</span><span class="sxs-lookup"><span data-stu-id="33a41-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="33a41-177">Pour plus d’informations, voir [Intégration de Power BI au magasin d’entité](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="33a41-177">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="33a41-178">Les mesures globales dans ce pack de contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d’achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="33a41-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="33a41-179">Pour enregistrer les mesures globales du cube dans le magasin d’entités, vous devez les rendre déployables.</span><span class="sxs-lookup"><span data-stu-id="33a41-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="33a41-180">Pour plus d’informations, voir la procédure d’enregistrement des mesures globales dans le magasin d’entités dans [Intégration de Power BI avec le magasin d’entités](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="33a41-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="33a41-181">Les mesures globales clés suivantes sont disponibles directement depuis l’entité Lignes de facture et sont utilisées comme base du contenu.</span><span class="sxs-lookup"><span data-stu-id="33a41-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="33a41-182">Entité</span><span class="sxs-lookup"><span data-stu-id="33a41-182">Entity</span></span>        | <span data-ttu-id="33a41-183">Mesures globales clés</span><span class="sxs-lookup"><span data-stu-id="33a41-183">Key aggregate measurements</span></span> | <span data-ttu-id="33a41-184">Source de données</span><span class="sxs-lookup"><span data-stu-id="33a41-184">Data source</span></span>                                 | <span data-ttu-id="33a41-185">Champ</span><span class="sxs-lookup"><span data-stu-id="33a41-185">Field</span></span>              | <span data-ttu-id="33a41-186">Description</span><span class="sxs-lookup"><span data-stu-id="33a41-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="33a41-187">Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="33a41-187">Invoice lines</span></span> | <span data-ttu-id="33a41-188">Achats</span><span class="sxs-lookup"><span data-stu-id="33a41-188">Purchase</span></span>                   | <span data-ttu-id="33a41-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="33a41-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="33a41-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="33a41-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="33a41-191">Montant dans la monnaie de compte.</span><span class="sxs-lookup"><span data-stu-id="33a41-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="33a41-192">Le tableau suivant indique les mesures principales du contenu qui sont calculées à partir de l’entité Lignes de facture.</span><span class="sxs-lookup"><span data-stu-id="33a41-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="33a41-193">Mesure</span><span class="sxs-lookup"><span data-stu-id="33a41-193">Measure</span></span>               | <span data-ttu-id="33a41-194">Calcul</span><span class="sxs-lookup"><span data-stu-id="33a41-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="33a41-195">Achats de l’année en cours</span><span class="sxs-lookup"><span data-stu-id="33a41-195">Purchase current year</span></span> | <span data-ttu-id="33a41-196">Achat de l’année en cours = SUM(’Invoice lines’\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="33a41-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="33a41-197">Achats l’année dernière</span><span class="sxs-lookup"><span data-stu-id="33a41-197">Purchase last year</span></span>    | <span data-ttu-id="33a41-198">Achats l’année dernière = CALCULATE(SUM(’Invoice lines’\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="33a41-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="33a41-199">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="33a41-199">YOY purchase growth</span></span>   | <span data-ttu-id="33a41-200">Croissance d’achat en cumul annuel = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="33a41-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="33a41-201">Les dimensions clés suivantes dans le contenu sont utilisées comme filtres pour diviser les mesures globales afin d’atteindre une meilleure granularité et d’obtenir une analyse plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="33a41-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="33a41-202">Entité</span><span class="sxs-lookup"><span data-stu-id="33a41-202">Entity</span></span>                 | <span data-ttu-id="33a41-203">Exemples d’attributs</span><span class="sxs-lookup"><span data-stu-id="33a41-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="33a41-204">Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="33a41-204">Vendors</span></span>                | <span data-ttu-id="33a41-205">Groupes de fournisseurs, Pays ou régions des fournisseurs, Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="33a41-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="33a41-206">Produits</span><span class="sxs-lookup"><span data-stu-id="33a41-206">Products</span></span>               | <span data-ttu-id="33a41-207">Numéro de produit, Nom du produit, Nom des groupes d’articles</span><span class="sxs-lookup"><span data-stu-id="33a41-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="33a41-208">Catégories d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="33a41-208">Procurement categories</span></span> | <span data-ttu-id="33a41-209">Catégorie d’approvisionnement, Noms des catégories d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="33a41-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="33a41-210">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="33a41-210">Legal entities</span></span>         | <span data-ttu-id="33a41-211">Nom de l’entité juridique</span><span class="sxs-lookup"><span data-stu-id="33a41-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="33a41-212">dates ;</span><span class="sxs-lookup"><span data-stu-id="33a41-212">Dates</span></span>                  | <span data-ttu-id="33a41-213">Dates, Contrepartie de l’année</span><span class="sxs-lookup"><span data-stu-id="33a41-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="33a41-214">Par défaut, le contenu affiche les données pour l’année civile en cours.</span><span class="sxs-lookup"><span data-stu-id="33a41-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="33a41-215">Toutefois, vous pouvez modifier le filtre date dans la section de filtres d’état.</span><span class="sxs-lookup"><span data-stu-id="33a41-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="33a41-216">Vous pouvez également modifier le filtre par société.</span><span class="sxs-lookup"><span data-stu-id="33a41-216">You can also change the company filter.</span></span>
