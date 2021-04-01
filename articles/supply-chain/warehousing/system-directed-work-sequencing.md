---
title: Classement des travaux dirigés par le système
description: Cette rubrique fournit des informations sur le classement des travaux dirigés par le système. Cette fonctionnalité vous permet de trier et de filtrer les ordres de travail que le système présente aux utilisateurs pour exécution. Elle est utile dans les scénarios où des critères supplémentaires sont nécessaires pour piloter le processus de prélèvement de l’entrepôt.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 7db884a5cd62e1f44a2a86316fde6bf2d11a3376
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239132"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="fef02-105">Classement des travaux dirigés par le système</span><span class="sxs-lookup"><span data-stu-id="fef02-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fef02-106">Le classement des travaux dirigés par le système vous permet de trier et de filtrer les ordres de travail que le système présente aux utilisateurs pour exécution.</span><span class="sxs-lookup"><span data-stu-id="fef02-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="fef02-107">Elles est utile dans les scénarios où des critères supplémentaires (tels que l’heure de l’expédition, la zone de prélèvement, le profil d’emplacement ou une combinaison de divers critères) sont nécessaires pour piloter le processus de prélèvement de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fef02-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="fef02-108">Cette fonctionnalité étend la fonctionnalité de prélèvement pilotée par le système en ajoutant un ordre de requête piloté par le système, dans lequel les utilisateurs peuvent configurer un classement et une ou plusieurs requêtes qui évalueront tous les ordres de travail créés.</span><span class="sxs-lookup"><span data-stu-id="fef02-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="fef02-109">Seuls les ordres de travail qui répondent aux critères spécifiés dans la configuration de l’élément de menu de l’appareil mobile seront capturés et présentés.</span><span class="sxs-lookup"><span data-stu-id="fef02-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="fef02-110">Par conséquent, cette fonctionnalité permet d’optimiser davantage les processus de prélèvement de l’entrepôt, car elle identifie les ordres de travail qui correspondent aux critères spécifiés, les affecte au bon élément de menu de l’appareil mobile, puis les présente à un collaborateur, en fonction d’un ensemble de qualifications spécifiques, de l’équipement de prélèvement ou de toute autre exigence.</span><span class="sxs-lookup"><span data-stu-id="fef02-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="fef02-111">Si différents critères sont nécessaires, plusieurs éléments de menu de l’appareil mobile doivent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="fef02-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="fef02-112">Activer la fonctionnalité de classement des travaux dirigés par le système à l’échelle de l’organisation</span><span class="sxs-lookup"><span data-stu-id="fef02-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="fef02-113">Avant de pouvoir utiliser le classement des travaux dirigés par le système, la fonctionnalité doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="fef02-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="fef02-114">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fef02-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fef02-115">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="fef02-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fef02-116">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="fef02-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fef02-117">**Nom de la fonctionnalité :** *Classement des travaux dirigés par le système à l’échelle de l’organisation*</span><span class="sxs-lookup"><span data-stu-id="fef02-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="fef02-118">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="fef02-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="fef02-119">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="fef02-119">Make demo data available</span></span>

<span data-ttu-id="fef02-120">Pour utiliser le scénario à l’aide des valeurs présentées dans cette rubrique, vous devez utiliser un système sous lequel les données de démonstration standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="fef02-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="fef02-121">De plus, vous devez sélectionner l’entité juridique **USMF**.</span><span class="sxs-lookup"><span data-stu-id="fef02-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="fef02-122">Le scénario utilise l’entrepôt *51* à partir des données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="fef02-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fef02-123">Avant de lancer les commandes à l’entrepôt, assurez-vous que les emplacements de prélèvement disposent d’un stock suffisant pour tous les articles des commandes.</span><span class="sxs-lookup"><span data-stu-id="fef02-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="fef02-124">Les données USMF par défaut doivent prendre en charge ce scénario.</span><span class="sxs-lookup"><span data-stu-id="fef02-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="fef02-125">Si vous n’utilisez pas les données de démonstration, vérifiez le paramètre **Instruction d’emplacement** pour connaître les emplacements de prélèvement utilisés pour le prélèvement des commandes client.</span><span class="sxs-lookup"><span data-stu-id="fef02-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="fef02-126">Si vous devez ajuster le stock, vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou utiliser tout autre flux.</span><span class="sxs-lookup"><span data-stu-id="fef02-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="fef02-127">Configurer un élément de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fef02-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="fef02-128">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="fef02-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fef02-129">Dans la liste des éléments de menu d’appareil mobile, sélectionnez **Prélèvement des ventes - Système**.</span><span class="sxs-lookup"><span data-stu-id="fef02-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="fef02-130">L’élément de menu requis doit déjà exister.</span><span class="sxs-lookup"><span data-stu-id="fef02-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="fef02-131">Confirmez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fef02-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="fef02-132">Sur l’organisateur **Général**, le champ **Dirigé par** doit être défini sur *Dirigé par le système*.</span><span class="sxs-lookup"><span data-stu-id="fef02-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="fef02-133">L’organisateur **Classes de travail** doit afficher les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="fef02-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="fef02-134">ID classe de travail</span><span class="sxs-lookup"><span data-stu-id="fef02-134">Work class ID</span></span> | <span data-ttu-id="fef02-135">Type d’ordre d’exécution</span><span class="sxs-lookup"><span data-stu-id="fef02-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="fef02-136">Vente</span><span class="sxs-lookup"><span data-stu-id="fef02-136">Sales</span></span> | <span data-ttu-id="fef02-137">Commandes client</span><span class="sxs-lookup"><span data-stu-id="fef02-137">Sales orders</span></span> |
        | <span data-ttu-id="fef02-138">Prélèvement CC</span><span class="sxs-lookup"><span data-stu-id="fef02-138">SO Pick</span></span> | <span data-ttu-id="fef02-139">Commandes client</span><span class="sxs-lookup"><span data-stu-id="fef02-139">Sales orders</span></span> |

1. <span data-ttu-id="fef02-140">Dans le volet Actions, sélectionnez **Requêtes de classement des travaux dirigés par le système**.</span><span class="sxs-lookup"><span data-stu-id="fef02-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="fef02-141">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fef02-141">Select **Edit**.</span></span>
1. <span data-ttu-id="fef02-142">Supprimez la ligne existante, puis confirmez l’action en sélectionnant **Oui**.</span><span class="sxs-lookup"><span data-stu-id="fef02-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="fef02-143">Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="fef02-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="fef02-144">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fef02-145">**Souche de N° :** *1*</span><span class="sxs-lookup"><span data-stu-id="fef02-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="fef02-146">**Champ Description :** *Quantité de travail inférieure à 20 et décroissante*</span><span class="sxs-lookup"><span data-stu-id="fef02-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="fef02-147">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fef02-147">Select **Save**.</span></span>
1. <span data-ttu-id="fef02-148">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="fef02-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="fef02-149">Sur l’onglet **Jointures**, développez la hiérarchie de la jointure pour afficher la table **Lignes de travail**.</span><span class="sxs-lookup"><span data-stu-id="fef02-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="fef02-150">Sélectionnez la jointure de table **Lignes de travail**.</span><span class="sxs-lookup"><span data-stu-id="fef02-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="fef02-151">Sélectionnez **Ajouter une jointure de table**.</span><span class="sxs-lookup"><span data-stu-id="fef02-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="fef02-152">Dans la liste qui apparaît, recherchez et sélectionnez la ligne contenant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="fef02-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="fef02-153">**Mode de jointure :** *n à 1*</span><span class="sxs-lookup"><span data-stu-id="fef02-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="fef02-154">**Relation :** *Emplacements (emplacement)*</span><span class="sxs-lookup"><span data-stu-id="fef02-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="fef02-155">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="fef02-155">Select **Select**.</span></span>

    <span data-ttu-id="fef02-156">Les emplacements sont ajoutés à la jointure de table.</span><span class="sxs-lookup"><span data-stu-id="fef02-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="fef02-157">Sous l’onglet **Tri**, sélectionnez **Ajouter** pour ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="fef02-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="fef02-158">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fef02-159">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-160">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-161">**Champ :** *Quantité de travail* (Dans la zone de message qui apparaît, sélectionnez **Oui** pour ajouter un tri à ce champ.)</span><span class="sxs-lookup"><span data-stu-id="fef02-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="fef02-162">**Direction de recherche :** *Décroissant*</span><span class="sxs-lookup"><span data-stu-id="fef02-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="fef02-163">Sélectionnez l’onglet **Plage**.</span><span class="sxs-lookup"><span data-stu-id="fef02-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="fef02-164">Si seuls des critères de travail spécifiques doivent être inclus dans le classement, vous pouvez les spécifier sur l’onglet **Plage**. Dans cet exemple, vous souhaitez inclure uniquement les travaux dont la quantité est inférieure à 20 unités (l’unité de mesure la plus petite).</span><span class="sxs-lookup"><span data-stu-id="fef02-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="fef02-165">Notez que certaines lignes sont déjà incluses.</span><span class="sxs-lookup"><span data-stu-id="fef02-165">Notice that some lines are already included.</span></span> <span data-ttu-id="fef02-166">Ces lignes ne doivent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="fef02-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="fef02-167">Sélectionnez **Ajouter** pour ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="fef02-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="fef02-168">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fef02-169">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-170">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-171">**Champ :** *Quantité de travail en stock*</span><span class="sxs-lookup"><span data-stu-id="fef02-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="fef02-172">**Critères :** *\<20* (moins de 20)</span><span class="sxs-lookup"><span data-stu-id="fef02-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="fef02-173">Sélectionnez **Ajouter** pour ajouter une autre ligne.</span><span class="sxs-lookup"><span data-stu-id="fef02-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="fef02-174">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fef02-175">**Table :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-176">**Table dérivée :** *Lignes de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="fef02-177">**Champ :** *Type de travail*</span><span class="sxs-lookup"><span data-stu-id="fef02-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="fef02-178">**Critères :** *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="fef02-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="fef02-179">Sélectionnez **Ajouter** pour ajouter une autre ligne.</span><span class="sxs-lookup"><span data-stu-id="fef02-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="fef02-180">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fef02-181">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="fef02-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="fef02-182">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="fef02-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="fef02-183">**Champ :** *Location profile ID*</span><span class="sxs-lookup"><span data-stu-id="fef02-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="fef02-184">**Critères :** *!PHASE*</span><span class="sxs-lookup"><span data-stu-id="fef02-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="fef02-185">Assurez-vous d’inclure le point d’exclamation (*!*) devant *PHASE*.</span><span class="sxs-lookup"><span data-stu-id="fef02-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="fef02-186">Sélectionnez **OK** pour enregistrer et fermer la requête.</span><span class="sxs-lookup"><span data-stu-id="fef02-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="fef02-187">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fef02-187">Select **Save**.</span></span>
1. <span data-ttu-id="fef02-188">Fermez la page pour revenir à la page **Éléments de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="fef02-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="fef02-189">Cette configuration définit les critères qui seront utilisés pour alimenter le travail éligible vers l’élément de menu de l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="fef02-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="fef02-190">Si vous ajoutez plus de lignes de critères à la requête, le système utilisera d’abord la ligne de requête avec le numéro de classement le plus petit.</span><span class="sxs-lookup"><span data-stu-id="fef02-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="fef02-191">En d’autres termes, tous les travaux éligibles pour le numéro de classement 1 seront d’abord présentés à l’utilisateur, puis tous les travaux pour le numéro de classement 2.</span><span class="sxs-lookup"><span data-stu-id="fef02-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="fef02-192">Par conséquent, si une plage et un tri spécifiques doivent être utilisés ensemble, ils doivent être spécifiés dans la même requête de classement de travaux dirigés par le système.</span><span class="sxs-lookup"><span data-stu-id="fef02-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="fef02-193">Cette configuration capturera tout travail comportant au moins une ligne dont la quantité est inférieure à 20 untés.</span><span class="sxs-lookup"><span data-stu-id="fef02-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="fef02-194">Par conséquent, si le travail a une ligne où la quantité est exactement de 20 unités ou supérieure à 20 unités, il sera valide, à condition qu’il ait également au moins une ligne où la quantité est inférieure à 20 unités.</span><span class="sxs-lookup"><span data-stu-id="fef02-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="fef02-195">Instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="fef02-195">Location directives</span></span>

<span data-ttu-id="fef02-196">Si vous utilisez les données Contoso par défaut, la requête pour l’action de directive d’emplacement ne nécessitera pas de modifications.</span><span class="sxs-lookup"><span data-stu-id="fef02-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="fef02-197">Toutefois, pour vous assurer que les directives d’emplacement captureront les articles des commandes client lorsque vous appliquez la fonctionnalité dans un environnement non Contoso, créez une directive d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="fef02-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="fef02-198">Pour vérifier les paramètres dans l’environnement de démonstration, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="fef02-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="fef02-199">Allez dans **Gestion des entrepôts** \> **Configuration** \> **Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="fef02-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="fef02-200">Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="fef02-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="fef02-201">Sélectionnez la directive d’emplacement nommée *51 Prélever*.</span><span class="sxs-lookup"><span data-stu-id="fef02-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="fef02-202">Sur l’organisateur **Actions de la directive d’emplacement**, sélectionnez la ligne de l’action **Prélever**.</span><span class="sxs-lookup"><span data-stu-id="fef02-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="fef02-203">Sélectionnez **Modifier la requête** au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="fef02-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="fef02-204">Vérifiez la requête **Plage**.</span><span class="sxs-lookup"><span data-stu-id="fef02-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="fef02-205">Recherchez la ligne où le champ **Champ** est défini sur *Emplacement*.</span><span class="sxs-lookup"><span data-stu-id="fef02-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="fef02-206">Assurez-vous que le champ **Critères** est vide (c’est-à-dire qu’il n’y a aucune restriction).</span><span class="sxs-lookup"><span data-stu-id="fef02-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="fef02-207">Scénario</span><span class="sxs-lookup"><span data-stu-id="fef02-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="fef02-208">Créer un travail de prélèvement de commande client</span><span class="sxs-lookup"><span data-stu-id="fef02-208">Create sales order picking work</span></span>

<span data-ttu-id="fef02-209">Avant d’exécuter le prélèvement dirigé par le système, certains travaux sortants doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="fef02-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="fef02-210">Pour ce scénario, vous allez créer quatre commandes client basées sur les requêtes de classement de travaux dirigés par le système spécifiées.</span><span class="sxs-lookup"><span data-stu-id="fef02-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="fef02-211">Vous réserverez des quantités en stock pour chaque commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="fef02-212">Par conséquent, le stock réservé ne peut pas être retiré de l’entrepôt pour les autres commandes, à moins que la réservation de stock ou une partie de celle-ci soit annulée.</span><span class="sxs-lookup"><span data-stu-id="fef02-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="fef02-213">Vous libérerez ensuite chaque commande client dans l’entrepôt pour créer le travail sortant.</span><span class="sxs-lookup"><span data-stu-id="fef02-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="fef02-214">Commande client 1</span><span class="sxs-lookup"><span data-stu-id="fef02-214">Sales order 1</span></span>

1. <span data-ttu-id="fef02-215">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="fef02-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fef02-216">Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="fef02-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="fef02-217">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fef02-218">Dans la section **Client**, définissez le champ **Compte client** sur *US-004*.</span><span class="sxs-lookup"><span data-stu-id="fef02-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="fef02-219">Dans la section **Général**, définissez le champ **Entrepôt** sur *51*.</span><span class="sxs-lookup"><span data-stu-id="fef02-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="fef02-220">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fef02-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="fef02-221">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="fef02-222">Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="fef02-223">**Numéro d’article :** *M9200*</span><span class="sxs-lookup"><span data-stu-id="fef02-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="fef02-224">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="fef02-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="fef02-225">Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="fef02-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="fef02-226">Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="fef02-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="fef02-227">Fermez la page **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="fef02-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="fef02-228">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt** pour créer un travail pour l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fef02-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="fef02-229">Vous recevez des messages d’information indiquant l’ID de vague, et les ID d’expédition créés pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="fef02-230">Commande client 2</span><span class="sxs-lookup"><span data-stu-id="fef02-230">Sales order 2</span></span>

1. <span data-ttu-id="fef02-231">Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="fef02-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="fef02-232">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fef02-233">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="fef02-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="fef02-234">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="fef02-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="fef02-235">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fef02-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="fef02-236">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="fef02-237">Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="fef02-238">**Numéro d’article :** *M9200*</span><span class="sxs-lookup"><span data-stu-id="fef02-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="fef02-239">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="fef02-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="fef02-240">Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="fef02-241">**Numéro d’article :** *M9201*</span><span class="sxs-lookup"><span data-stu-id="fef02-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="fef02-242">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="fef02-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="fef02-243">Réservez le stock pour les deux lignes.</span><span class="sxs-lookup"><span data-stu-id="fef02-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="fef02-244">Libérez la commande dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fef02-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="fef02-245">Commande client 3</span><span class="sxs-lookup"><span data-stu-id="fef02-245">Sales order 3</span></span>

1. <span data-ttu-id="fef02-246">Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 3.</span><span class="sxs-lookup"><span data-stu-id="fef02-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="fef02-247">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fef02-248">**Compte client :** *US-009*</span><span class="sxs-lookup"><span data-stu-id="fef02-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="fef02-249">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="fef02-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="fef02-250">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fef02-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="fef02-251">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="fef02-252">Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="fef02-253">**Numéro d’article :** *M9200*</span><span class="sxs-lookup"><span data-stu-id="fef02-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="fef02-254">**Quantité :** *7*</span><span class="sxs-lookup"><span data-stu-id="fef02-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="fef02-255">Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="fef02-256">**Numéro d’article :** *M9202*</span><span class="sxs-lookup"><span data-stu-id="fef02-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="fef02-257">**Quantité :** *8*</span><span class="sxs-lookup"><span data-stu-id="fef02-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="fef02-258">Réservez le stock pour les deux lignes.</span><span class="sxs-lookup"><span data-stu-id="fef02-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="fef02-259">Libérez la commande dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fef02-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="fef02-260">Commande client 4</span><span class="sxs-lookup"><span data-stu-id="fef02-260">Sales order 4</span></span>

1. <span data-ttu-id="fef02-261">Dans le volet Actions, sélectionnez **Nouveau** pour créer la commande client 4.</span><span class="sxs-lookup"><span data-stu-id="fef02-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="fef02-262">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fef02-263">**Compte client :** *US-010*</span><span class="sxs-lookup"><span data-stu-id="fef02-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="fef02-264">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="fef02-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="fef02-265">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fef02-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="fef02-266">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="fef02-267">Ajoutez une ligne à la nouvelle commande client et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="fef02-268">**Numéro d’article :** *M9200*</span><span class="sxs-lookup"><span data-stu-id="fef02-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="fef02-269">**Quantité :** *25*</span><span class="sxs-lookup"><span data-stu-id="fef02-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="fef02-270">Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fef02-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="fef02-271">**Numéro d’article :** *M9202*</span><span class="sxs-lookup"><span data-stu-id="fef02-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="fef02-272">**Quantité :** *10*</span><span class="sxs-lookup"><span data-stu-id="fef02-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="fef02-273">Réservez le stock pour les deux lignes.</span><span class="sxs-lookup"><span data-stu-id="fef02-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="fef02-274">Libérez la commande dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="fef02-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="fef02-275">Obtenir des ID de travail pour le travail créé</span><span class="sxs-lookup"><span data-stu-id="fef02-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="fef02-276">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="fef02-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="fef02-277">Filtrez le champ **Entrepôt** de sorte que seul le travail de l’entrepôt *51* soit montré.</span><span class="sxs-lookup"><span data-stu-id="fef02-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="fef02-278">Quatre ID de travaux ont été créés.</span><span class="sxs-lookup"><span data-stu-id="fef02-278">Four work IDs should have been created.</span></span> <span data-ttu-id="fef02-279">Notez l’ID de travail de chaque commande client.</span><span class="sxs-lookup"><span data-stu-id="fef02-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="fef02-280">ID commande client</span><span class="sxs-lookup"><span data-stu-id="fef02-280">Sales order ID</span></span> | <span data-ttu-id="fef02-281">ID travail</span><span class="sxs-lookup"><span data-stu-id="fef02-281">Work ID</span></span> | <span data-ttu-id="fef02-282">Quantité de travail</span><span class="sxs-lookup"><span data-stu-id="fef02-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="fef02-283">Commande client 1</span><span class="sxs-lookup"><span data-stu-id="fef02-283">Sales Order 1</span></span> | <span data-ttu-id="fef02-284">ID travail 1</span><span class="sxs-lookup"><span data-stu-id="fef02-284">Work ID 1</span></span> | <span data-ttu-id="fef02-285">20 unités</span><span class="sxs-lookup"><span data-stu-id="fef02-285">20 ea</span></span> |
    | <span data-ttu-id="fef02-286">Commande client 2</span><span class="sxs-lookup"><span data-stu-id="fef02-286">Sales Order 2</span></span> | <span data-ttu-id="fef02-287">ID travail 2</span><span class="sxs-lookup"><span data-stu-id="fef02-287">Work ID 2</span></span> | <span data-ttu-id="fef02-288">6 unités (somme des deux lignes)</span><span class="sxs-lookup"><span data-stu-id="fef02-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="fef02-289">Commande client 3</span><span class="sxs-lookup"><span data-stu-id="fef02-289">Sales Order 3</span></span> | <span data-ttu-id="fef02-290">ID travail 3</span><span class="sxs-lookup"><span data-stu-id="fef02-290">Work ID 3</span></span> | <span data-ttu-id="fef02-291">15 unités (somme des deux lignes)</span><span class="sxs-lookup"><span data-stu-id="fef02-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="fef02-292">Commande client 4</span><span class="sxs-lookup"><span data-stu-id="fef02-292">Sales Order 4</span></span> | <span data-ttu-id="fef02-293">ID travail 4</span><span class="sxs-lookup"><span data-stu-id="fef02-293">Work ID 4</span></span> | <span data-ttu-id="fef02-294">35 unités (somme des deux lignes)</span><span class="sxs-lookup"><span data-stu-id="fef02-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="fef02-295">Avant d’exécuter le flux sur l’appareil mobile, assurez-vous que seul le travail que vous venez de créer a le statut *Ouvert* pour l’entrepôt *51* et le type d’ordre de travail *Commande client*.</span><span class="sxs-lookup"><span data-stu-id="fef02-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="fef02-296">Sinon, les résultats du test peuvent varier, car le prélèvement dirigé par le système comprendra tous les travaux éligibles.</span><span class="sxs-lookup"><span data-stu-id="fef02-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="fef02-297">Allez à **Gestion des entrepôts \> Travail \> Sortant \> Travaux sortants ouverts**.</span><span class="sxs-lookup"><span data-stu-id="fef02-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="fef02-298">Dans la grille **Travaux de vente ouverts**, filtrez le champ **Entrepôt** de sorte que seul le travail de l’entrepôt *51* soit affiché.</span><span class="sxs-lookup"><span data-stu-id="fef02-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="fef02-299">Confirmez que seuls les quatre ID de travaux créés précédemment sont affichés.</span><span class="sxs-lookup"><span data-stu-id="fef02-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="fef02-300">Fermez la page **Travail**.</span><span class="sxs-lookup"><span data-stu-id="fef02-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="fef02-301">Exécution du flux de l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fef02-301">Mobile device flow execution</span></span>

<span data-ttu-id="fef02-302">En fonction de la configuration, le système alimentera le travail de l’utilisateur trié à partir de la quantité de ligne de travail la plus élevée à la plus faible.</span><span class="sxs-lookup"><span data-stu-id="fef02-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="fef02-303">La quantité sur chaque ligne sera inférieure à 20 unités.</span><span class="sxs-lookup"><span data-stu-id="fef02-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="fef02-304">N’oubliez pas que cette configuration capturera tout travail comportant au moins une ligne dont la quantité est inférieure à 20 untés.</span><span class="sxs-lookup"><span data-stu-id="fef02-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="fef02-305">Par conséquent, si le travail comporte une autre ligne dont la quantité est exactement de 20 unités ou supérieure à 20 unités, il sera également valide.</span><span class="sxs-lookup"><span data-stu-id="fef02-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="fef02-306">Application mobile</span><span class="sxs-lookup"><span data-stu-id="fef02-306">Mobile app</span></span>

1. <span data-ttu-id="fef02-307">Connectez-vous à l’application d’entreposage en tant qu’utilisateur de l’entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="fef02-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="fef02-308">Allez à **Sortant \> Prélèvement des ventes - Système**.</span><span class="sxs-lookup"><span data-stu-id="fef02-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="fef02-309">L’étape de prélèvement de l’ID de travail *4* est indiquée.</span><span class="sxs-lookup"><span data-stu-id="fef02-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="fef02-310">Cet ID de travail est présenté en premier en raison de la configuration de l’ordre de requête dirigé par le système, où vous avez spécifié que le travail doit être classé en fonction de la quantité de ligne de travail décroissante.</span><span class="sxs-lookup"><span data-stu-id="fef02-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="fef02-311">Effectuez le prélèvement et le rangement nécessaires pour fermer l’ID de travail.</span><span class="sxs-lookup"><span data-stu-id="fef02-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="fef02-312">Ensuite, l’ID de travail *3* est présenté.</span><span class="sxs-lookup"><span data-stu-id="fef02-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="fef02-313">L’une de ses lignes de travail est la suivante dans le classement, en fonction de la quantité de la ligne de travail.</span><span class="sxs-lookup"><span data-stu-id="fef02-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="fef02-314">Effectuez le prélèvement et le rangement pour fermer l’ID de travail.</span><span class="sxs-lookup"><span data-stu-id="fef02-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="fef02-315">Ensuite, l’ID de travail *2* est présenté.</span><span class="sxs-lookup"><span data-stu-id="fef02-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="fef02-316">La ligne de prélèvement de ce travail est la suivante dans le classement.</span><span class="sxs-lookup"><span data-stu-id="fef02-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="fef02-317">Effectuez le prélèvement et le rangement pour fermer l’ID de travail.</span><span class="sxs-lookup"><span data-stu-id="fef02-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="fef02-318">Aucun autre travail ne doit vous être présenté.</span><span class="sxs-lookup"><span data-stu-id="fef02-318">No further work should be presented to you.</span></span> <span data-ttu-id="fef02-319">L’ID de travail *1* n’est pas éligible pour cet élément de menu de l’appareil mobile, car la requête spécifie que les en-têtes de travail ne sont pris en compte que si la quantité sur les lignes de travail est inférieure à 20 unités.</span><span class="sxs-lookup"><span data-stu-id="fef02-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="fef02-320">Conseils</span><span class="sxs-lookup"><span data-stu-id="fef02-320">Tips</span></span>

<span data-ttu-id="fef02-321">Les requêtes de classement des travaux dirigés par le système sont *inclusives*.</span><span class="sxs-lookup"><span data-stu-id="fef02-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="fef02-322">Il est important que vous vous souveniez de ce fait pour certaines configurations.</span><span class="sxs-lookup"><span data-stu-id="fef02-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="fef02-323">Par exemple, vous souhaitez qu’un élément de menu spécifique traite uniquement le travail dans lequel l’unité de travail est *unité* et vous spécifiez cette restriction sur l’onglet **Plage** de la requête.</span><span class="sxs-lookup"><span data-stu-id="fef02-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="fef02-324">Dans ce cas, tous les travaux où au moins une ligne de travail a l’unité de travail définie sur *unité* seront fournis au collaborateur.</span><span class="sxs-lookup"><span data-stu-id="fef02-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="fef02-325">Par conséquent, ce travail peut également inclure le travail dans lequel les lignes de travail ont une unité de travail autre que *unité* (telle que *boîte* ou *palette*).</span><span class="sxs-lookup"><span data-stu-id="fef02-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="fef02-326">La requête exclura uniquement le travail où aucune ligne de travail n’a l’unité de travail définie sur *unité*.</span><span class="sxs-lookup"><span data-stu-id="fef02-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="fef02-327">Par conséquent, dans l’exemple de ce scénario, l’ID de travail *4* a également été capturé par la requête.</span><span class="sxs-lookup"><span data-stu-id="fef02-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="fef02-328">Lors de sa création, deux lignes ont été ajoutées : une pour 25 unités et une autre pour 10 unités.</span><span class="sxs-lookup"><span data-stu-id="fef02-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="fef02-329">Le travail était toujours présenté à l’utilisateur, car au moins une ligne de travail a une quantité inférieure à 20 unités.</span><span class="sxs-lookup"><span data-stu-id="fef02-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="fef02-330">Selon le scénario, vous pouvez empêcher ce comportement en utilisant des répartitions du travail.</span><span class="sxs-lookup"><span data-stu-id="fef02-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]