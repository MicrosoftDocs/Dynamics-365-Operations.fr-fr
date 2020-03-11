---
title: Rapport Comparer le stockage du prix des articles
description: Découvrez comment générer un rapport Comparer le stockage du prix des articles, puis parcourir et/ou exporter le résultat.
author: AndersGirke
manager: AnnBe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 80e376db3616af27d94ee55480cd2f56441db93b
ms.sourcegitcommit: 0dace221e8874021dd212271567666f717d39793
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "3072113"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="30e47-103">Rapport Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30e47-104">Cette rubrique explique comment exécuter un rapport **Comparer le stockage du prix des articles** et rendre la sortie disponible au format numérique, soit en tant que page interactive dans Dynamics 365 Supply Chain Management ou en tant que document exporté dans l'un des différents formats.</span><span class="sxs-lookup"><span data-stu-id="30e47-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="30e47-105">Lorsque vous affichez le rapport dans votre navigateur, les colonnes et les soldes globaux sont ajustés de façon dynamique, selon la disposition que vous avez configurée.</span><span class="sxs-lookup"><span data-stu-id="30e47-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="30e47-106">Vous pouvez trier les résultats, les filtrer, explorer les données, etc.</span><span class="sxs-lookup"><span data-stu-id="30e47-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="30e47-107">Les résultats du rapport sont stockés dans l'entité de données **Comparer le prix des articles**, qui vous permet de filtrer et d'exporter les résultats dans un format tel que CSV ou Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="30e47-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="30e47-108">Le rapport **Comparer le stockage du prix des articles** est utile dans les cas où la sortie contient plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="30e47-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="30e47-109">Par exemple, la sortie contiendra plusieurs lignes si plus de 40 000 articles ont un prix d'article en attente dans la version d'évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="30e47-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="30e47-110">Activer la fonctionnalité Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-110">Enable compare item prices storage</span></span>

<span data-ttu-id="30e47-111">Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="30e47-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="30e47-112">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="30e47-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="30e47-113">La fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="30e47-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="30e47-114">**Module** : Gestion des coûts</span><span class="sxs-lookup"><span data-stu-id="30e47-114">**Module** - Cost management</span></span>
- <span data-ttu-id="30e47-115">**Nom de la fonctionnalité** : Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="30e47-116">Générer un rapport Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="30e47-117">Procédez comme suit pour générer et stocker un rapport **Comparer le stockage du prix des articles** :</span><span class="sxs-lookup"><span data-stu-id="30e47-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="30e47-118">Accédez à **Gestion des coûts > Recherches et états > Rapports de coûts prédéterminés > Comparer le stockage du prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="30e47-119">Sélectionnez **Nouveau** pour ouvrir le volet **Comparer le prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="30e47-120">Définissez les options suivantes pour définir les prix à comparer dans votre rapport :</span><span class="sxs-lookup"><span data-stu-id="30e47-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="30e47-121">Dans le raccourci **Paramètres**, attribuez un **Nom** unique au rapport et utilisez les champs des sections **Prix en attente à comparer** et **Prix utilisés pour la comparaison** pour définir les prix et les dates à comparer.</span><span class="sxs-lookup"><span data-stu-id="30e47-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="30e47-122">Dans le raccourci **Enregistrements à inclure**, configurez des filtres et des contraintes pour définir les données à inclure dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="30e47-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="30e47-123">Dans le raccourci **Exécuter en arrière-plan**, définissez comment, quand et à quelle fréquence vous souhaitez générer le rapport.</span><span class="sxs-lookup"><span data-stu-id="30e47-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="30e47-124">Ce rapport est toujours exécuté dans le cadre d'un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="30e47-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="30e47-125">Sélectionnez **OK** pour appliquer vos paramètres et fermer le volet.</span><span class="sxs-lookup"><span data-stu-id="30e47-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="30e47-126">Une fois le traitement par lots terminé, il sera répertorié sur la page **Comparer le stockage du prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="30e47-127">Vous devrez peut-être actualiser la page pour voir le rapport.</span><span class="sxs-lookup"><span data-stu-id="30e47-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="30e47-128">Explorer le rapport Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="30e47-129">Après avoir généré un rapport, vous pouvez l'afficher et l'explorer à tout moment comme suit :</span><span class="sxs-lookup"><span data-stu-id="30e47-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="30e47-130">Accédez à **Gestion des coûts > Recherches et états > Rapports de coûts prédéterminés > Comparer le stockage du prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="30e47-131">Sélectionnez un rapport dans la liste.</span><span class="sxs-lookup"><span data-stu-id="30e47-131">Select a report from the list.</span></span>

1. <span data-ttu-id="30e47-132">Effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="30e47-132">Do one of the following:</span></span>

    - <span data-ttu-id="30e47-133">Sélectionnez **Vue d'ensemble** pour obtenir une vue d'ensemble des résultats de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="30e47-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="30e47-134">Sélectionnez **Afficher les détails** pour obtenir une vue plus détaillée de votre rapport</span><span class="sxs-lookup"><span data-stu-id="30e47-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="30e47-135">Une fois que la vue sélectionnée s'ouvre, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="30e47-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="30e47-136">Sélectionner presque tous les en-têtes de colonne pour trier ou filtrer la table selon les valeurs de cette colonne, comme avec la plupart des formulaires standard dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30e47-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="30e47-137">Notez qu'il n'est pas possible de trier ou de filtrer la colonne **% prix modification nette**, car il s'agit d'un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="30e47-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="30e47-138">Sélectionner **Affichage des dimensions** pour ouvrir un volet dans lequel vous pouvez choisir la colonne de dimension à inclure dans le formulaire.</span><span class="sxs-lookup"><span data-stu-id="30e47-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="30e47-139">Définissez **Enregistrer le paramétrage** sur **Oui** si vous souhaitez enregistrer ces paramètres afin qu'ils soient conservés lors de la prochaine ouverture du rapport.</span><span class="sxs-lookup"><span data-stu-id="30e47-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="30e47-140">Sélectionnez **OK** pour appliquer vos paramètres et fermer.</span><span class="sxs-lookup"><span data-stu-id="30e47-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="30e47-141">Sélectionner une ligne du formulaire, puis sélectionner **Afficher les détails** pour afficher plus d'informations sur l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="30e47-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="30e47-142">Vous pourrez ensuite explorer les données.</span><span class="sxs-lookup"><span data-stu-id="30e47-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="30e47-143">Sélectionner une ligne du formulaire, puis sélectionner **Afficher le graphique de comparaison** pour afficher une représentation graphique interactive de vos résultats en relation avec l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="30e47-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="30e47-144">Vous pouvez explorer ces résultats en sélectionnant divers éléments graphiques dans le graphique et sa légende.</span><span class="sxs-lookup"><span data-stu-id="30e47-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="30e47-145">Sélectionner une ligne du formulaire, puis sélectionner **Afficher les détails du calcul** pour afficher plus d'informations sur les calculs associés à l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="30e47-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="30e47-146">Vous pourrez ensuite explorer les données.</span><span class="sxs-lookup"><span data-stu-id="30e47-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="30e47-147">Exporter le rapport Comparer le stockage du prix des articles</span><span class="sxs-lookup"><span data-stu-id="30e47-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="30e47-148">Chaque rapport que vous générez est stocké dans l'entité de données **Comparer le prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="30e47-149">Vous pouvez utiliser les fonctionnalités de gestion des données standard de Supply Chain Management pour exporter les données de cette entité dans un format de données pris en charge, y compris CSV ou Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="30e47-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="30e47-150">L'exemple suivant montre comment exporter un rapport **Comparer le stockage du prix des articles** :</span><span class="sxs-lookup"><span data-stu-id="30e47-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="30e47-151">Accédez à **Administration système > Espaces de travail > Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="30e47-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="30e47-152">Sélectionnez le bouton **Exporter** dans la section **Gestion des données**.</span><span class="sxs-lookup"><span data-stu-id="30e47-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="30e47-153">La page **Exporter** s'ouvre pour vous permettre de configurer votre tâche d'exportation.</span><span class="sxs-lookup"><span data-stu-id="30e47-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="30e47-154">Commencez par attribuer un **Nom de groupe** à votre tâche.</span><span class="sxs-lookup"><span data-stu-id="30e47-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="30e47-155">Dans la section **Entités sélectionnées**, sélectionnez **Ajouter une entité** pour ouvrir une boîte de dialogue dans laquelle vous pouvez définir les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="30e47-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="30e47-156">**Nom de l'entité** : sélectionnez **Comparer le prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="30e47-157">**Format des données cibles** : choisissez le format d'exportation.</span><span class="sxs-lookup"><span data-stu-id="30e47-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="30e47-158">Sélectionnez **Ajouter** pour ajouter la nouvelle ligne, puis sélectionnez **Fermer** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="30e47-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="30e47-159">Généralement, vous exporterez un rapport à la fois.</span><span class="sxs-lookup"><span data-stu-id="30e47-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="30e47-160">Pour ce faire, définissez un **Filtre** pour la ligne que vous venez d'ajouter au volet **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="30e47-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="30e47-161">Cela vous permettra de définir les rapports de l'entité **Comparer le prix des articles** que vous souhaitez inclure dans votre exportation.</span><span class="sxs-lookup"><span data-stu-id="30e47-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="30e47-162">Définissez les options de filtre suivantes pour exporter un rapport :</span><span class="sxs-lookup"><span data-stu-id="30e47-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="30e47-163">Sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="30e47-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="30e47-164">Définissez **Table** sur **Comparer le prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="30e47-165">Définissez **Table dérivée** sur **Comparer le prix des articles**.</span><span class="sxs-lookup"><span data-stu-id="30e47-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="30e47-166">Définissez **Champ** sur le champ que vous souhaitez filtrer.</span><span class="sxs-lookup"><span data-stu-id="30e47-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="30e47-167">Généralement, vous utiliserez **Nom d'exécution** ou **Temps d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="30e47-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="30e47-168">Définissez **Critères** sur la valeur du champ sélectionné que vous souhaitez rechercher (soit le nom du rapport, soit l'heure de génération du rapport).</span><span class="sxs-lookup"><span data-stu-id="30e47-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="30e47-169">Si nécessaire, ajoutez d'autres lignes à la table **Plage** jusqu'à ce que vous ayez identifié de manière unique le rapport que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="30e47-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="30e47-170">Sélectionnez **OK** pour enregistrer vos paramètres et fermer.</span><span class="sxs-lookup"><span data-stu-id="30e47-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="30e47-171">Sélectionnez **Enregistrer** pour enregistrer vos paramètres d'exportation.</span><span class="sxs-lookup"><span data-stu-id="30e47-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="30e47-172">Ouvrez l'onglet **Options d'exportation** et sélectionnez **Exporter maintenant** pour générer le fichier d'exportation.</span><span class="sxs-lookup"><span data-stu-id="30e47-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="30e47-173">La page **Résumé de l'exécution** s'ouvre pour vous permettre d'afficher le statut de votre tâche d'exportation et la liste des entités exportées.</span><span class="sxs-lookup"><span data-stu-id="30e47-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="30e47-174">Sélectionnez l'entité **Comparer le prix des articles** répertoriée dans la zone **Statut de traitement de l'entité**, puis sélectionnez **Télécharger le fichier** pour télécharger les données exportées depuis cette entité.</span><span class="sxs-lookup"><span data-stu-id="30e47-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="30e47-175">Pour plus d'informations sur l'utilisation de la gestion des données pour exporter des données, voir [Vue d'ensemble des tâches d'importation et d'exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="30e47-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
