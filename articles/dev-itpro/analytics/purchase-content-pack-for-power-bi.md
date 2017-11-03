---
title: "Contenu Power BI Analyse des dépenses d'achat"
description: "Cette rubrique décrit ce qui est inclus dans le contenu Power BI Analyse des dépenses d'achat. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6485f36802fc4e327e223f47d65c4bdca11c1609
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="83cf5-104">Contenu Power BI Analyse des dépenses d'achat</span><span class="sxs-lookup"><span data-stu-id="83cf5-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="83cf5-105">Cette rubrique décrit ce qui est inclus dans le contenu Microsoft Power BI **Analyse des dépenses d'achat**.</span><span class="sxs-lookup"><span data-stu-id="83cf5-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="83cf5-106">Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.</span><span class="sxs-lookup"><span data-stu-id="83cf5-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="83cf5-107">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="83cf5-107">Overview</span></span>

<span data-ttu-id="83cf5-108">Le contenu Power BI **Analyse des dépenses d'achat** a été conçu pour aider les directeurs des achats et autres gestionnaires qui sont responsables des budgets à garder un œil sur les dépenses d'achat.</span><span class="sxs-lookup"><span data-stu-id="83cf5-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="83cf5-109">Les gestionnaires peuvent analyser les dépenses d'achat des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="83cf5-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="83cf5-110">Achat depuis le début de l'année (par groupe de fournisseurs et fournisseurs individuels, catégorie d'approvisionnement et produits individuels et emplacement du fournisseur)</span><span class="sxs-lookup"><span data-stu-id="83cf5-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="83cf5-111">Changement d'achat d'une année sur l'autre (par groupe de fournisseurs et catégorie d'approvisionnement)</span><span class="sxs-lookup"><span data-stu-id="83cf5-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="83cf5-112">Le contenu utilise les données transactionnelles d'achats, et fournit une vue globale des chiffres d'achats à l'échelle de l'entreprise et une répartition des dépenses d'achat par fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="83cf5-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="83cf5-113">Les rapports mettent l'accent sur les changements dans les dépenses d'achat au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="83cf5-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="83cf5-114">Par conséquent, les états peuvent être utilisés pour avertir les responsables sur les tendances positives et négatives de dépenses pour chaque fournisseur et produit.</span><span class="sxs-lookup"><span data-stu-id="83cf5-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="83cf5-115">En outre, les graphiques montrent les dépenses des différentes catégories d'approvisionnement et groupes de fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="83cf5-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="83cf5-116">Ainsi, les gestionnaires régionaux et de catégories peuvent utiliser les graphiques pour aider à identifier les changements dans le comportement des dépenses.</span><span class="sxs-lookup"><span data-stu-id="83cf5-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="83cf5-117">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="83cf5-117">Accessing the Power BI content</span></span>
<span data-ttu-id="83cf5-118">Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Juillet 2017), le contenu Power BI **Analyse des dépenses d'achat** s'affiche sur la page **Analyse des dépenses et des achats** (**Approvisionnements** > **Recherches et états** > **Analyse des performances d'achat** > **Analyse des dépenses et des achats**).</span><span class="sxs-lookup"><span data-stu-id="83cf5-118">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), the **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="83cf5-119">Mesures incluses dans le contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="83cf5-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="83cf5-120">Le contenu Power BI **Analyse des dépenses d'achat** comprend un état constitué d'un ensemble d'éléments de mesure.</span><span class="sxs-lookup"><span data-stu-id="83cf5-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="83cf5-121">Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux.</span><span class="sxs-lookup"><span data-stu-id="83cf5-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="83cf5-122">Le tableau suivant offre une vue d'ensemble des visualisations.</span><span class="sxs-lookup"><span data-stu-id="83cf5-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83cf5-123">Page d'état</span><span class="sxs-lookup"><span data-stu-id="83cf5-123">Report page</span></span></th>
<th><span data-ttu-id="83cf5-124">Graphiques</span><span class="sxs-lookup"><span data-stu-id="83cf5-124">Charts</span></span></th>
<th><span data-ttu-id="83cf5-125">Vignettes</span><span class="sxs-lookup"><span data-stu-id="83cf5-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="83cf5-126">Achat par fournisseur</span><span class="sxs-lookup"><span data-stu-id="83cf5-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-127">Les 10 principaux vendeurs par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="83cf5-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="83cf5-128">Achat total par groupe de fournisseurs / pays / nom (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="83cf5-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="83cf5-129">Achat par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="83cf5-130">Achat moyen par groupe de fournisseurs / pays / nom (histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="83cf5-131">Total des achats</span><span class="sxs-lookup"><span data-stu-id="83cf5-131">Total purchase</span></span></li>
<li><span data-ttu-id="83cf5-132">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="83cf5-133">Nombre total de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="83cf5-133">Total # vendors</span></span></li>
<li><span data-ttu-id="83cf5-134">Nombre total de fournisseurs actifs</span><span class="sxs-lookup"><span data-stu-id="83cf5-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="83cf5-135">Achat par produit</span><span class="sxs-lookup"><span data-stu-id="83cf5-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-136">Achat par catégorie d'approvisionnement / nom du produit (histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="83cf5-137">Achat total par catégorie d'approvisionnement / nom du produit (graphique à secteurs)</span><span class="sxs-lookup"><span data-stu-id="83cf5-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="83cf5-138">Les 10 principaux produits par achat (graphique à barres empilées)</span><span class="sxs-lookup"><span data-stu-id="83cf5-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="83cf5-139">Nombre total de produits</span><span class="sxs-lookup"><span data-stu-id="83cf5-139">Total # of products</span></span></li>
<li><span data-ttu-id="83cf5-140">Nombre total de produit actifs et pourcentage du total de produits</span><span class="sxs-lookup"><span data-stu-id="83cf5-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="83cf5-141">Nombre de produits constituant 80 % de l'achat</span><span class="sxs-lookup"><span data-stu-id="83cf5-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="83cf5-142">Achat par période*</span><span class="sxs-lookup"><span data-stu-id="83cf5-142">Purchase by period*</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-143">Achat par mois/jour (histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="83cf5-144">Variation en cumul annuel des achats (graphique cascade)</span><span class="sxs-lookup"><span data-stu-id="83cf5-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="83cf5-145">Croissance en cumul annuel des achats totaux (histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="83cf5-146">Relevé d'approvisionnement (matrice)</span><span class="sxs-lookup"><span data-stu-id="83cf5-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="83cf5-147">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="83cf5-148">% de croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="83cf5-149">Achat par emplacement de fournisseur</span><span class="sxs-lookup"><span data-stu-id="83cf5-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-150">Achat par ville</span><span class="sxs-lookup"><span data-stu-id="83cf5-150">Purchase by city</span></span></li>
<li><span data-ttu-id="83cf5-151">% de croissance en cumul annuel des achats</span><span class="sxs-lookup"><span data-stu-id="83cf5-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="83cf5-152">Achat par pays</span><span class="sxs-lookup"><span data-stu-id="83cf5-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="83cf5-153">Analyse des dépenses d'achat par période</span><span class="sxs-lookup"><span data-stu-id="83cf5-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-154">Achats de l'année en cours par mois / jour (graphique en courbes)</span><span class="sxs-lookup"><span data-stu-id="83cf5-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="83cf5-155">Achats de l'année en cours et de l'année dernière (graphique en courbes et histogramme)</span><span class="sxs-lookup"><span data-stu-id="83cf5-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="83cf5-156">Analyse des dépenses d'achat par fournisseur</span><span class="sxs-lookup"><span data-stu-id="83cf5-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="83cf5-157">10 principaux achats fournisseur en % (icône conique)</span><span class="sxs-lookup"><span data-stu-id="83cf5-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="83cf5-158">10 premiers fournisseurs avec dépenses augmentées en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="83cf5-159">10 premiers fournisseurs avec dépenses réduites en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="83cf5-160">\* Achats cette année et l'année dernière, et croissance par catégorie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="83cf5-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="83cf5-161">Extension du contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="83cf5-161">Extending the Power BI content</span></span>
<span data-ttu-id="83cf5-162">Grâce aux packs de contenu disponibles dans Microsoft Dynamics Lifecycle Services (LCS), vous pouvez fournir une analyse approfondie aux personnes qui ne se connectent pas à Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="83cf5-162">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="83cf5-163">Vous pouvez modifier ces packs de contenu pour qu'ils permettent d'inclure d'autres rapports ou visuels, et de publier les packs de contenu via votre locataire Power BI.com pour analyse.</span><span class="sxs-lookup"><span data-stu-id="83cf5-163">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="83cf5-164">Le contenu Power BI **Analyse des dépenses d'achat** se trouve dans la bibliothèque de ressources partagées dans LCS.</span><span class="sxs-lookup"><span data-stu-id="83cf5-164">You can find the **Purchase spend analysis** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="83cf5-165">Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="83cf5-165">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="83cf5-166">Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span><span class="sxs-lookup"><span data-stu-id="83cf5-166">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

<span data-ttu-id="83cf5-167">Veillez à télécharger le contenu **Analyse des dépenses d'achat** qui s'applique à la version de Dynamics 365 que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="83cf5-167">Be sure to download the **Purchase spend analysis** content that applies to the version of Dynamics 365 that you're using.</span></span>

> [!NOTE]
> <span data-ttu-id="83cf5-168">Si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations, le KB 4011327 doit être consulté au préalable pour ce contenu Power BI.</span><span class="sxs-lookup"><span data-stu-id="83cf5-168">If you're using Microsoft Dynamics 365 for Operations version 1611, KB 4011327 is a prerequisite for this Power BI content.</span></span> <span data-ttu-id="83cf5-169">Une fois que vous êtes connecté à LCS, vous pouvez accéder à la Base de connaissances à l'adresse https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span><span class="sxs-lookup"><span data-stu-id="83cf5-169">After you sign in to LCS, you can access the KB at https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="83cf5-170">Modèle de données et entités</span><span class="sxs-lookup"><span data-stu-id="83cf5-170">Data model and entities</span></span>
<span data-ttu-id="83cf5-171">Les données suivantes sont utilisées pour remplir les pages d'état dans le contenu Power BI **Analyse des dépenses d'achat**.</span><span class="sxs-lookup"><span data-stu-id="83cf5-171">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="83cf5-172">Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="83cf5-172">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="83cf5-173">Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses.</span><span class="sxs-lookup"><span data-stu-id="83cf5-173">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="83cf5-174">Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](power-bi-integration-entity-store.md)</span><span class="sxs-lookup"><span data-stu-id="83cf5-174">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="83cf5-175">Les mesures globales dans ce contenu sont le sous-ensemble des mesures globales qui sont disponibles dans le Cube d'achat dans Microsoft Dynamics AX 2012 et Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="83cf5-175">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="83cf5-176">Pour enregistrer les mesures globales du cube dans le magasin d'entités, vous devez les rendre déployables.</span><span class="sxs-lookup"><span data-stu-id="83cf5-176">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="83cf5-177">Pour plus d'informations, voir la procédure d'enregistrement des mesures globales dans le magasin d'entités dans [Vue d'ensemble de l'intégration de Power BI avec le magasin d'entités](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="83cf5-177">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="83cf5-178">Les mesures globales clés suivantes sont disponibles directement depuis l'entité Lignes de facture et sont utilisées comme base du contenu.</span><span class="sxs-lookup"><span data-stu-id="83cf5-178">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="83cf5-179">Entité</span><span class="sxs-lookup"><span data-stu-id="83cf5-179">Entity</span></span>        | <span data-ttu-id="83cf5-180">Mesures globales clés</span><span class="sxs-lookup"><span data-stu-id="83cf5-180">Key aggregate measurements</span></span> | <span data-ttu-id="83cf5-181">Source de données</span><span class="sxs-lookup"><span data-stu-id="83cf5-181">Data source</span></span>                                 | <span data-ttu-id="83cf5-182">Champ</span><span class="sxs-lookup"><span data-stu-id="83cf5-182">Field</span></span>              | <span data-ttu-id="83cf5-183">Description</span><span class="sxs-lookup"><span data-stu-id="83cf5-183">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="83cf5-184">Lignes de facture</span><span class="sxs-lookup"><span data-stu-id="83cf5-184">Invoice lines</span></span> | <span data-ttu-id="83cf5-185">Achats</span><span class="sxs-lookup"><span data-stu-id="83cf5-185">Purchase</span></span>                   | <span data-ttu-id="83cf5-186">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="83cf5-186">VendInvoiceTrans</span></span>                            | <span data-ttu-id="83cf5-187">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="83cf5-187">SUM(LineAmountMST)</span></span> | <span data-ttu-id="83cf5-188">Montant dans la monnaie de compte.</span><span class="sxs-lookup"><span data-stu-id="83cf5-188">The amount in the accounting currency.</span></span> |

<span data-ttu-id="83cf5-189">Le tableau suivant indique les mesures principales du contenu qui sont calculées à partir de l'entité Lignes de facture.</span><span class="sxs-lookup"><span data-stu-id="83cf5-189">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="83cf5-190">Mesure</span><span class="sxs-lookup"><span data-stu-id="83cf5-190">Measure</span></span>               | <span data-ttu-id="83cf5-191">Calcul</span><span class="sxs-lookup"><span data-stu-id="83cf5-191">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="83cf5-192">Achats de l'année en cours</span><span class="sxs-lookup"><span data-stu-id="83cf5-192">Purchase current year</span></span> | <span data-ttu-id="83cf5-193">Achat de l'année en cours = SUM('Invoice lines'\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="83cf5-193">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="83cf5-194">Achats l'année dernière</span><span class="sxs-lookup"><span data-stu-id="83cf5-194">Purchase last year</span></span>    | <span data-ttu-id="83cf5-195">Achats l'année dernière = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="83cf5-195">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="83cf5-196">Croissance des achats en cumul annuel</span><span class="sxs-lookup"><span data-stu-id="83cf5-196">YOY purchase growth</span></span>   | <span data-ttu-id="83cf5-197">Croissance d'achat en cumul annuel = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="83cf5-197">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="83cf5-198">Les dimensions clés suivantes dans le contenu sont utilisées comme filtres pour diviser les mesures globales afin d'atteindre une meilleure granularité et d'obtenir une analyse plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="83cf5-198">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="83cf5-199">Entité</span><span class="sxs-lookup"><span data-stu-id="83cf5-199">Entity</span></span>                 | <span data-ttu-id="83cf5-200">Exemples d'attributs</span><span class="sxs-lookup"><span data-stu-id="83cf5-200">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="83cf5-201">Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="83cf5-201">Vendors</span></span>                | <span data-ttu-id="83cf5-202">Groupes de fournisseurs, Pays ou régions des fournisseurs, Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="83cf5-202">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="83cf5-203">Produits</span><span class="sxs-lookup"><span data-stu-id="83cf5-203">Products</span></span>               | <span data-ttu-id="83cf5-204">Numéro de produit, Nom du produit, Nom des groupes d'articles</span><span class="sxs-lookup"><span data-stu-id="83cf5-204">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="83cf5-205">Catégories d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="83cf5-205">Procurement categories</span></span> | <span data-ttu-id="83cf5-206">Catégorie d'approvisionnement, Noms des catégories d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="83cf5-206">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="83cf5-207">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="83cf5-207">Legal entities</span></span>         | <span data-ttu-id="83cf5-208">Nom de l'entité juridique</span><span class="sxs-lookup"><span data-stu-id="83cf5-208">Legal entity name</span></span>                                     |
| <span data-ttu-id="83cf5-209">dates ;</span><span class="sxs-lookup"><span data-stu-id="83cf5-209">Dates</span></span>                  | <span data-ttu-id="83cf5-210">Dates, Contrepartie de l'année</span><span class="sxs-lookup"><span data-stu-id="83cf5-210">Dates, Year offset</span></span>                                    |

<span data-ttu-id="83cf5-211">Par défaut, le contenu affiche les données pour l'année civile en cours.</span><span class="sxs-lookup"><span data-stu-id="83cf5-211">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="83cf5-212">Toutefois, vous pouvez modifier le filtre date dans la section de filtres d'état.</span><span class="sxs-lookup"><span data-stu-id="83cf5-212">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="83cf5-213">Vous pouvez également modifier le filtre par société.</span><span class="sxs-lookup"><span data-stu-id="83cf5-213">You can also change the company filter.</span></span>

