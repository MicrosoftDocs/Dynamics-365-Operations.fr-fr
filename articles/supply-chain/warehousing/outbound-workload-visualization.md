---
title: Visualisation de la charge de travail sortante
description: Cette rubrique fournit des informations sur la visualisation de la charge de travail sortante. Cette fonctionnalité permet aux responsables d'entrepôt et aux superviseurs de créer des graphiques de charge de travail personnalisés qui peuvent être utilisés pour surveiller la progression du travail en cours et la quantité qui reste. Les gestionnaires d'entrepôt peuvent créer plusieurs vues et configurer une actualisation automatique selon leurs besoins.
author: Mirzaab
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: cbfb395c9103ff31979bfd57333f689e38915652
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645429"
---
# <a name="outbound-workload-visualization"></a><span data-ttu-id="010e5-105">Visualisation de la charge de travail sortante</span><span class="sxs-lookup"><span data-stu-id="010e5-105">Outbound workload visualization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="010e5-106">Les capacités de configuration avancées accessibles depuis la page **Visualisation de la charge de travail sortante** permettent aux responsables d'entrepôt et aux superviseurs de créer des graphiques de charge de travail personnalisés qui peuvent être utilisés pour surveiller la progression du travail en cours et la quantité qui reste.</span><span class="sxs-lookup"><span data-stu-id="010e5-106">Advanced setup capabilities that are accessible from the **Outbound workload visualization** page let warehouse managers and supervisors create custom workload charts that can be used to monitor the progress of current work and the amount of it that remains.</span></span> <span data-ttu-id="010e5-107">Les gestionnaires d'entrepôt peuvent créer plusieurs vues et configurer une actualisation automatique selon leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="010e5-107">Warehouse managers can create multiple views and set up automatic refresh as they require.</span></span> <span data-ttu-id="010e5-108">Les visualisations de charge de travail sortante peuvent être affichées sur les pages de performances de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="010e5-108">Outbound workload visualizations are suitable for display on warehouse performance pages.</span></span>

<span data-ttu-id="010e5-109">Cette fonctionnalité peut être utilisée pour suivre la progression du travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="010e5-109">This functionality can be used to track the progress of picking work.</span></span> <span data-ttu-id="010e5-110">La fonctionnalité est intégrée à la gestion de la main-d'œuvre et, si la gestion de la main-d'œuvre est configurée, les visualisations de la charge de travail sortante peuvent afficher un calcul du nombre d'heures restantes pour le travail de prélèvement affiché (filtré).</span><span class="sxs-lookup"><span data-stu-id="010e5-110">The feature is integrated with labor management, and if labor management is set up, outbound workload visualizations can show a calculation of the number of hours that remain for the picking work that is shown (filtered).</span></span>

## <a name="turn-on-the-outbound-workload-visualization-feature"></a><span data-ttu-id="010e5-111">Activer la fonctionnalité de visualisation de la charge de travail sortante</span><span class="sxs-lookup"><span data-stu-id="010e5-111">Turn on the Outbound workload visualization feature</span></span>

<span data-ttu-id="010e5-112">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="010e5-112">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="010e5-113">Les administrateurs peuvent utiliser les paramètres de [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="010e5-113">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="010e5-114">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="010e5-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="010e5-115">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="010e5-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="010e5-116">**Nom de la fonctionnalité :** *Visualisation de la charge de travail sortante*</span><span class="sxs-lookup"><span data-stu-id="010e5-116">**Feature name:** *Outbound workload visualization*</span></span>

## <a name="set-up-outbound-workload-visualizations"></a><span data-ttu-id="010e5-117">Configuration des visualisations de la charge de travail sortante</span><span class="sxs-lookup"><span data-stu-id="010e5-117">Set up outbound workload visualizations</span></span>

<span data-ttu-id="010e5-118">Pour configurer vos visualisations, créez une collection de filtres (vues) et concevez chaque filtre de sorte qu'il affiche un type d'analyse différent.</span><span class="sxs-lookup"><span data-stu-id="010e5-118">To set up your visualizations, you create a collection of filters (views) and design each filter so that it shows a different type of analysis.</span></span> <span data-ttu-id="010e5-119">Utilisez la page **Configurer les filtres** pour concevoir les filtres.</span><span class="sxs-lookup"><span data-stu-id="010e5-119">You use the **Configure filters** page to design the filters.</span></span>

<span data-ttu-id="010e5-120">Pour configurer une visualisation de la charge de travail sortante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="010e5-120">To set up an outbound workload visualization, follow these steps.</span></span>

1. <span data-ttu-id="010e5-121">Aller à **Gestion des entrepôts \> Rapports de surveillance des entrepôts \> Visualisation de la charge de travail sortante**.</span><span class="sxs-lookup"><span data-stu-id="010e5-121">Go to **Warehouse management \> Warehouse monitoring reports \> Outbound workload visualization**.</span></span>

    <span data-ttu-id="010e5-122">La page **Visualisation de la charge de travail sortante** apparaît.</span><span class="sxs-lookup"><span data-stu-id="010e5-122">The **Outbound workload visualization** page appears.</span></span> <span data-ttu-id="010e5-123">Une fois que vous avez créé des filtres, cette page affichera votre visualisation.</span><span class="sxs-lookup"><span data-stu-id="010e5-123">After you create some filters, this page will show your visualization.</span></span> <span data-ttu-id="010e5-124">Vous pouvez créer autant de filtres que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="010e5-124">You can create as many filters as you want.</span></span> <span data-ttu-id="010e5-125">Tous les filtres que vous créez sont enregistrés sous votre compte utilisateur, afin que vous puissiez les utiliser ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="010e5-125">All the filters that you create are saved under your user account, so that you can use them later.</span></span> <span data-ttu-id="010e5-126">En d'autres termes, chaque utilisateur aura son propre ensemble de filtres qu'il a créé.</span><span class="sxs-lookup"><span data-stu-id="010e5-126">In other words, each user will have their own set of filters that they created.</span></span> <span data-ttu-id="010e5-127">Ces filtres ne seront pas partagés avec d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="010e5-127">Those filters won't be shared with other users.</span></span>

1. <span data-ttu-id="010e5-128">Sur la page **Visualisation de la charge de travail sortante**, dans le volet Actions, sur l'onglet **Filtres**, sélectionnez **Configurer les filtres**.</span><span class="sxs-lookup"><span data-stu-id="010e5-128">On the **Outbound workload visualization** page, on the Action Pane, on the **Filters** tab, select **Configure filters**.</span></span>
1. <span data-ttu-id="010e5-129">Sur la page **Configurer les filtres**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter un filtre, puis définissez les champs suivants pour celui-ci :</span><span class="sxs-lookup"><span data-stu-id="010e5-129">On the **Configure filters** page, on the Action Pane, select **New** to add a filter, and then set the following fields for it:</span></span>

    - <span data-ttu-id="010e5-130">**Tableau des groupes de l'axe X** – Sélectionnez le tableau contenant le champ à utiliser pour regrouper les valeurs de l'axe X.</span><span class="sxs-lookup"><span data-stu-id="010e5-130">**X-axis group table** – Select the table that contains the field that should be used to group the X-axis values.</span></span>
    - <span data-ttu-id="010e5-131">**Champ du groupe de l'axe X** – Parmi les champs de la table que vous avez sélectionnés dans le **Tableau des groupes de l'axe X**, sélectionnez le champ à utiliser pour regrouper les valeurs de l'axe X.</span><span class="sxs-lookup"><span data-stu-id="010e5-131">**X-axis group field** – From among the fields of the table that you selected in the **X-axis group table** field, select the field that should be used to group the X-axis values.</span></span>
    - <span data-ttu-id="010e5-132">**Tableau des valeurs de l'axe X** – Sélectionnez le tableau contenant le champ à utiliser pour analyser de manière avancée les groupes.</span><span class="sxs-lookup"><span data-stu-id="010e5-132">**X-axis value table** – Select the table that contains the field that should be used to further analyze the groups.</span></span>
    - <span data-ttu-id="010e5-133">**Champ de la valeur de l'axe X** – Parmi les champs de la table que vous avez sélectionnés dans le **Tableau des valeurs de l'axe X**, sélectionnez le champ qui fournit les valeurs à analyser pour chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="010e5-133">**X-axis value field** – From among the fields of the table that you selected in the **X-axis value table** field, select the field that provides the values that should be analyzed for each group.</span></span>
    - <span data-ttu-id="010e5-134">**Actualisation automatique** – Sélectionnez si la visualisation doit être actualisée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="010e5-134">**Auto-refresh** – Select whether the visualization should automatically be refreshed.</span></span>
    - <span data-ttu-id="010e5-135">**Intervalle d'actualisation (minutes)** – Entrez le nombre de minutes entre les actualisations automatiques.</span><span class="sxs-lookup"><span data-stu-id="010e5-135">**Refresh interval (minutes)** – Enter the number of minutes between automatic refreshes.</span></span>
    - <span data-ttu-id="010e5-136">**Niveau d'affichage** – Sélectionnez si le graphique doit afficher des lignes ouvertes ou des nombres d'en-têtes ouverts.</span><span class="sxs-lookup"><span data-stu-id="010e5-136">**Display level** – Select whether the chart should show open lines or open header counts.</span></span>
    - <span data-ttu-id="010e5-137">**Type de prélèvement** – Si vous définissez le champ **Niveau d'affichage** sur _Lignes ouvertes_, indiquez si le nombre de lignes de travail ouvertes dans le graphique doit inclure les prélèvements initiaux, les prélèvements par étapes ou à la fois les prélèvements initiaux et les prélèvements par étapes.</span><span class="sxs-lookup"><span data-stu-id="010e5-137">**Picking type** – If you set the **Display level** field to _Open lines_, select whether the count of open work lines in the chart should include initial picks, staged picks, or both initial picks and staged picks.</span></span>
    - <span data-ttu-id="010e5-138">**Site** – Sélectionnez le site pour lequel charger le graphique.</span><span class="sxs-lookup"><span data-stu-id="010e5-138">**Site** – Select the site to load the chart for.</span></span>
    - <span data-ttu-id="010e5-139">**Entrepôt** – Sélectionnez l'entrepôt pour lequel charger le graphique.</span><span class="sxs-lookup"><span data-stu-id="010e5-139">**Warehouse** – Select the warehouse to load the chart for.</span></span>
    - <span data-ttu-id="010e5-140">**Jours à inclure** – Entrez le nombre de jours dans le passé pour lesquels le graphique doit être généré.</span><span class="sxs-lookup"><span data-stu-id="010e5-140">**Days to include** – Enter the number of days in the past that the chart should be generated for.</span></span>
    - <span data-ttu-id="010e5-141">**Type d'ordre de travail** – Sélectionnez les types d'ordre de travail sortant sur lesquels filtrer.</span><span class="sxs-lookup"><span data-stu-id="010e5-141">**Work order type** – Select the outbound work order types to filter on.</span></span>

    <span data-ttu-id="010e5-142">![Configurer la page des filtres](media/work-viz-filters-1.png "Configurer la page des filtres")</span><span class="sxs-lookup"><span data-stu-id="010e5-142">![Configure filters page](media/work-viz-filters-1.png "Configure filters page")</span></span>

1. <span data-ttu-id="010e5-143">Fermez la page **Configurer les filtres** pour revenir à la page **Visualisations de la charge de travail sortante**.</span><span class="sxs-lookup"><span data-stu-id="010e5-143">Close the **Configure filters** page to return to the **Outbound workload visualizations** page.</span></span>

    <span data-ttu-id="010e5-144">La page **Visualisations de la charge de travail sortante** affiche désormais des données, basées sur vos nouveaux paramètres de filtre.</span><span class="sxs-lookup"><span data-stu-id="010e5-144">The **Outbound workload visualizations** page now shows data, based on your new filter settings.</span></span> <span data-ttu-id="010e5-145">Votre nouveau filtre est maintenant disponible et est sélectionné dans le champ **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="010e5-145">Your new filter is now available and is selected in the **Filter** field.</span></span> <span data-ttu-id="010e5-146">Les champs suivants sont disponibles en haut du graphique :</span><span class="sxs-lookup"><span data-stu-id="010e5-146">The following fields are available at the top of the chart:</span></span>

    - <span data-ttu-id="010e5-147">**Filtre** – Ce champ comprend tous les filtres que vous avez créés jusqu'à présent.</span><span class="sxs-lookup"><span data-stu-id="010e5-147">**Filter** – This field includes all the filters that you've created so far.</span></span> <span data-ttu-id="010e5-148">Sélectionnez un filtre pour afficher ses données dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="010e5-148">Select a filter to view its data in the chart.</span></span>
    - <span data-ttu-id="010e5-149">**Dernière actualisation** – Ce champ indique la date et l'heure de la dernière mise à jour des informations du graphique.</span><span class="sxs-lookup"><span data-stu-id="010e5-149">**Last refreshed** – This field shows the date and time when the information in the chart was last updated.</span></span>
    - <span data-ttu-id="010e5-150">**Temps estimé/réel** – Si des normes du travail sont définies dans votre système, définissez cette option sur *Oui* pour afficher les temps de prélèvement estimés cumulés en haut de chaque colonne du graphique.</span><span class="sxs-lookup"><span data-stu-id="010e5-150">**Estimated/actual time** – If labor standards are set up in your system, set this option to *Yes* to show accumulated estimated picking times at the top of each column in the chart.</span></span> <span data-ttu-id="010e5-151">Si vous n'utilisez pas les normes du travail, cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="010e5-151">If you aren't using labor standards, this option is unavailable.</span></span>

    <span data-ttu-id="010e5-152">![Exemple de visualisation](media/work-viz-chart.png "Exemple de visualisation")</span><span class="sxs-lookup"><span data-stu-id="010e5-152">![Example visualization](media/work-viz-chart.png "Example visualization")</span></span>

1. <span data-ttu-id="010e5-153">Sélectionnez n'importe quelle barre du graphique pour afficher les détails de la ligne de travail associée.</span><span class="sxs-lookup"><span data-stu-id="010e5-153">Select any bar in the chart to view the associated work line details.</span></span>

    <span data-ttu-id="010e5-154">![Détails de la ligne de travail](media/work-viz-work-details.png "Détails de la ligne de travail")</span><span class="sxs-lookup"><span data-stu-id="010e5-154">![Work line details](media/work-viz-work-details.png "Work line details")</span></span>

## <a name="example-outbound-workload-visualization-for-zones"></a><span data-ttu-id="010e5-155">Exemple : Visualisation de la charge de travail sortante pour les zones</span><span class="sxs-lookup"><span data-stu-id="010e5-155">Example: Outbound workload visualization for zones</span></span>

<span data-ttu-id="010e5-156">Pour cet exemple, vous souhaitez configurer une visualisation qui montre les lignes de travail pour chaque zone et le statut de chaque ligne de travail (_Ouvert_, _Fermé_ ou _Annulé_).</span><span class="sxs-lookup"><span data-stu-id="010e5-156">For this example, you want to set up a visualization that shows work lines for each zone, and the status of each work line (_Open_, _Closed_, or _Canceled_).</span></span> <span data-ttu-id="010e5-157">Dans ce cas, vous pouvez configurer un filtre avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="010e5-157">In this case, you can set up a filter that has the following settings:</span></span>

- <span data-ttu-id="010e5-158">**Nom du filtre** – Entrez un nom pour ce filtre (tel que _Zone et statut de travail_).</span><span class="sxs-lookup"><span data-stu-id="010e5-158">**Filter name** – Enter a name for this filter (such as _Zone vs. work status_).</span></span>
- <span data-ttu-id="010e5-159">**Description** – Entrez une brève description pour ce filtre (tel que _Zone et statut de travail_).</span><span class="sxs-lookup"><span data-stu-id="010e5-159">**Description** – Enter a short description for this filter (such as _Zone vs. work status_).</span></span>
- <span data-ttu-id="010e5-160">**Tableau des groupes de l'axe X** – Sélectionnez _Emplacements._</span><span class="sxs-lookup"><span data-stu-id="010e5-160">**X-axis group table** – Select _Locations._</span></span>
- <span data-ttu-id="010e5-161">**Groupe de l'axe X** – Sélectionnez _ID de zone_.</span><span class="sxs-lookup"><span data-stu-id="010e5-161">**X-axis group** – Select _Zone ID_.</span></span>
- <span data-ttu-id="010e5-162">**Tableau des valeurs de l'axe X** – Sélectionnez _Travail_, car vous souhaitez afficher le travail par zone.</span><span class="sxs-lookup"><span data-stu-id="010e5-162">**X-axis value table** – Select _Work_, because you want to view work per zone.</span></span>
- <span data-ttu-id="010e5-163">**Champ de valeur de l'axe X** – Sélectionnez _Statut du travail_, car vous souhaitez afficher le statut du travail.</span><span class="sxs-lookup"><span data-stu-id="010e5-163">**X-axis value field** – Select _Work status_, because you want to view work status.</span></span>
- <span data-ttu-id="010e5-164">**Actualisation automatique** – Sélectionnez si la visualisation doit être actualisée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="010e5-164">**Auto refresh** – Select whether the visualization should automatically be refreshed.</span></span>
- <span data-ttu-id="010e5-165">**Type de prélèvement** – Sélectionnez _Prélèvements initiaux et prélèvements par étapes_, car vous souhaitez inclure à la fois les sélections initiales et les sélections à partir des emplacements temporaires.</span><span class="sxs-lookup"><span data-stu-id="010e5-165">**Picking type** – Select _Initial picks and staged picks_, because you want to include both initial picks and picks from staging locations.</span></span> <span data-ttu-id="010e5-166">En d'autres termes, vous souhaitez essentiellement inclure toutes les lignes de travail de prélèvement dont vous disposez.</span><span class="sxs-lookup"><span data-stu-id="010e5-166">In other words, you essentially want to include all the pick work lines that you have.</span></span>
- <span data-ttu-id="010e5-167">**Niveau d'affichage** – Sélectionnez _Lignes ouvertes_, car vous souhaitez afficher les informations par ligne et non par en-tête de travail.</span><span class="sxs-lookup"><span data-stu-id="010e5-167">**Display level** – Select _Open lines_, because you want to view the information per line, not per work header.</span></span>

<span data-ttu-id="010e5-168">L'illustration suivante présente un exemple du graphique en résultant.</span><span class="sxs-lookup"><span data-stu-id="010e5-168">The following illustration shows an example of the resulting chart.</span></span>

<span data-ttu-id="010e5-169">![Visualisation du statut de la zone et du travail](media/work-viz-chart.png "Visualisation du statut de la zone et du travail")</span><span class="sxs-lookup"><span data-stu-id="010e5-169">![Zone vs. work status visualization](media/work-viz-chart.png "Zone vs. work status visualization")</span></span>

<span data-ttu-id="010e5-170">Ce graphique montre deux zones nommées **ATELIER** et **VRAC**, plus une zone nommée **Vide**.</span><span class="sxs-lookup"><span data-stu-id="010e5-170">This chart shows two zones that are named **FLOOR** and **BULK**, plus a zone that is named **Blank**.</span></span> <span data-ttu-id="010e5-171">La zone **Vide** représente toutes les lignes de travail qui ne sont membres d'aucune zone.</span><span class="sxs-lookup"><span data-stu-id="010e5-171">The **Blank** zone represents all work lines that aren't members of any zones.</span></span> <span data-ttu-id="010e5-172">Le graphique montre toujours toutes les données filtrées non liées comme **Vides**, pour offrir autant de visibilité que possible.</span><span class="sxs-lookup"><span data-stu-id="010e5-172">The chart always shows all unrelated filtered data as **Blank**, to provide as much visibility as possible.</span></span> <span data-ttu-id="010e5-173">Dans la zone **ATELIER**, le graphique montre trois lignes fermées et quatre lignes ouvertes.</span><span class="sxs-lookup"><span data-stu-id="010e5-173">In the **FLOOR** zone, the chart shows three closed lines and four open lines.</span></span> <span data-ttu-id="010e5-174">Dans la zone **VRAC**, le graphique montre quatre lignes fermées, une ligne ouverte et 24 lignes annulées.</span><span class="sxs-lookup"><span data-stu-id="010e5-174">In the **BULK** zone, the chart shows four closed lines, one open line, and 24 canceled lines.</span></span> <span data-ttu-id="010e5-175">Enfin, le graphique montre huit lignes fermées qui ne font partie d'aucune zone et sont donc répertoriées comme **Vides**.</span><span class="sxs-lookup"><span data-stu-id="010e5-175">Finally, the chart shows eight closed lines that aren't part of any zone and are therefore listed as **Blank**.</span></span>