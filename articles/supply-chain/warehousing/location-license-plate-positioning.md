---
title: Positionnement des contenants dans un emplacement
description: Le positionnement des contenants dans un emplacement vous permet de voir où se trouve un contenant dans un emplacement à palettes multiples, comme un emplacement qui utilise un rayonnage à palettes à double profondeur.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: e5fd7a9a9703f9ab6802def0aac096e29aa04f1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831383"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="6dc07-103">Positionnement des contenants dans un emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6dc07-104">Le positionnement des contenants dans un emplacement vous permet de voir où se trouve un contenant dans un emplacement à palettes multiples, comme un emplacement qui utilise un rayonnage à palettes à double profondeur.</span><span class="sxs-lookup"><span data-stu-id="6dc07-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="6dc07-105">La fonctionnalité ajoute un numéro de souche à chaque contenant placé dans un emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="6dc07-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="6dc07-106">Ce numéro de souche permet de classer les contenants dans l’emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="6dc07-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="6dc07-107">Par conséquent, la fonctionnalité prend en charge de manière intelligente les scénarios où les clients utilisent un système de rayonnage par gravité et doivent savoir, à des fins de prélèvement, quel contenant est orienté vers l’avant.</span><span class="sxs-lookup"><span data-stu-id="6dc07-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="6dc07-108">Cette rubrique présente un scénario qui montre comment configurer et utiliser la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6dc07-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="6dc07-109">Activer la fonctionnalité Positionnement des contenants dans un emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="6dc07-110">Avant de pouvoir utiliser le positionnement des contenants dans un emplacement, la fonctionnalité doit être activée dans votre système.</span><span class="sxs-lookup"><span data-stu-id="6dc07-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="6dc07-111">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6dc07-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6dc07-112">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="6dc07-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6dc07-113">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="6dc07-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6dc07-114">**Nom de la fonctionnalité :** *Positionnement des contenants dans un emplacement*</span><span class="sxs-lookup"><span data-stu-id="6dc07-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6dc07-115">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="6dc07-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="6dc07-116">Rendre les exemple de données disponibles</span><span class="sxs-lookup"><span data-stu-id="6dc07-116">Make sample data available</span></span>

<span data-ttu-id="6dc07-117">Pour exécuter ce scénario en utilisant les valeurs suggérées ici, vous devez utiliser un système dans lequel les exemples de données sont installées.</span><span class="sxs-lookup"><span data-stu-id="6dc07-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="6dc07-118">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="6dc07-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="6dc07-119">Configurer la fonctionnalité pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="6dc07-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="6dc07-120">Exécutez les procédures suivantes pour configurer la fonctionnalité *Positionnement des contenants dans un emplacement* pour le scénario présenté dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6dc07-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="6dc07-121">Profils d’emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-121">Location profiles</span></span>

<span data-ttu-id="6dc07-122">La fonctionnalité doit être activée dans le profil d’emplacement pour chaque emplacement où elle sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="6dc07-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="6dc07-123">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="6dc07-124">Dans la liste des profils d’emplacement du volet gauche, sélectionnez **VRAC-06**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="6dc07-125">Dans l’organisateur **Général**, deux nouvelles options ont été ajoutées par la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6dc07-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="6dc07-126">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-126">Set the following values:</span></span>

    - <span data-ttu-id="6dc07-127">**Activer le positionnement du contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="6dc07-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="6dc07-128">Lorsque cette option est définie sur *Oui*, le positionnement du contenant sera conservé pour les contenants dans l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="6dc07-129">**Afficher le positionnement du contenant sur l’appareil mobile :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="6dc07-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="6dc07-130">Lorsque cette option est définie sur *Oui*, le positionnement du contenant sera visible par les utilisateurs sur l’appareil mobile pendant l’ajustement et l’inventaire.</span><span class="sxs-lookup"><span data-stu-id="6dc07-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="6dc07-131">Vous ne pouvez modifier le paramètre de cette option que lorsque la fonctionnalité est activée.</span><span class="sxs-lookup"><span data-stu-id="6dc07-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="6dc07-132">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="6dc07-133">Instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-133">Location directives</span></span>

1. <span data-ttu-id="6dc07-134">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6dc07-135">Dans le volet gauche, assurez-vous que le champ **Type d’ordre de travail** est défini sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="6dc07-136">Dans la liste des instructions d’emplacement, sélectionnez **61 Ordre de prélèvement de commande client**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="6dc07-137">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6dc07-138">Dans l’organisateur **Lignes**, sélectionnez la ligne dont la valeur **Numéro de souche** est *2*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="6dc07-139">Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez la ligne dont la valeur **Nom** est *Prélever pour moins que la palette* (ce devrait être la seule ligne) et modifiez sa valeur **Numéro de souche** sur *2*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="6dc07-140">Sélectionnez **Nouveau** au-dessus de la grille pour ajouter une ligne pour une nouvelle action d’instruction d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="6dc07-141">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc07-142">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6dc07-143">**Nom :** *Choisir la position 1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="6dc07-144">Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Modifier la requête** au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="6dc07-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="6dc07-145">Dans l’éditeur de requêtes, sélectionnez l’onglet **Jointures**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="6dc07-146">Développez la jointure de table **Emplacements** pour afficher la jointure à la table **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="6dc07-147">Développez la jointure de table **Dimensions de stock** pour afficher la jointure à la table **Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="6dc07-148">Sélectionnez **Dimensions de stock**, puis sélectionnez **Ajouter une jointure de table**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="6dc07-149">Dans la liste des tables qui s’affiche, dans la colonne **Relation**, sélectionnez **Contenant (contenant)**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="6dc07-150">Sélectionnez ensuite **Sélectionner** pour ajouter **Contenant** à la jointure de table **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="6dc07-151">Alors que **Contenant** est toujours sélectionné, sélectionnez **Ajouter une jointure de table**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="6dc07-152">Dans la liste des tables qui s’affiche, dans la colonne **Relation**, sélectionnez **Positionnement des contenants dans un emplacement (contenant)**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="6dc07-153">Sélectionnez ensuite **Sélectionner** pour ajouter **Positionnement des contenants dans un emplacement** à la jointure de table **Dimensions de stock**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="6dc07-154">![Jointures de table](media/LpTableJoin.png "Jointures de table")</span><span class="sxs-lookup"><span data-stu-id="6dc07-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="6dc07-155">Cliquez sur **OK** pour confirmer les tables jointes mises à jour et fermer l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6dc07-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="6dc07-156">Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez à nouveau **Modifier la requête** pour rouvrir l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6dc07-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="6dc07-157">Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="6dc07-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="6dc07-158">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6dc07-159">**Table :** *Positionnement des contenants dans un emplacement*</span><span class="sxs-lookup"><span data-stu-id="6dc07-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="6dc07-160">**Table dérivée :** *Positionnement des contenants dans un emplacement*</span><span class="sxs-lookup"><span data-stu-id="6dc07-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="6dc07-161">**Champ :** *Position du contenant*</span><span class="sxs-lookup"><span data-stu-id="6dc07-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="6dc07-162">**Critères :** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="6dc07-163">![Nouvelle plage](media/LpPositionCriteria.png "Nouvelle plage")</span><span class="sxs-lookup"><span data-stu-id="6dc07-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="6dc07-164">Cliquez sur **OK** pour confirmer vos modifications et fermer l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6dc07-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="6dc07-165">Configurer les exemples de données pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="6dc07-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="6dc07-166">Pour ce scénario, l’utilisateur doit se connecter à l’application mobile d’entreposage en utilisant un collaborateur configuré pour l’entrepôt *61* pour effectuer le travail.</span><span class="sxs-lookup"><span data-stu-id="6dc07-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="6dc07-167">L’utilisateur doit également exécuter les transactions.</span><span class="sxs-lookup"><span data-stu-id="6dc07-167">The user must also complete transactions.</span></span>

<span data-ttu-id="6dc07-168">Étant donné que la fonctionnalité *Positionnement des contenants dans un emplacement* ajoute un nouvel identifiant pour les positions de contenant dans un emplacement, vous devez commencer par créer des données pour prendre en charge le scénario.</span><span class="sxs-lookup"><span data-stu-id="6dc07-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="6dc07-169">Inventaire ponctuel du premier emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-169">Spot-count the first location</span></span>

1. <span data-ttu-id="6dc07-170">Ouvrez l’application mobile d’entreposage et connectez-vous à l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="6dc07-171">Allez dans **Stock \> Inventaire ponctuel**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="6dc07-172">Sur la page **Inventaire ponctuel**, définissez le champ **Emplacement** sur *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="6dc07-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-173">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-174">La page affiche l’emplacement que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="6dc07-174">The page shows the location that you entered.</span></span> <span data-ttu-id="6dc07-175">Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »</span><span class="sxs-lookup"><span data-stu-id="6dc07-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="6dc07-176">Sélectionnez **Actualiser** pour ajouter un inventaire dans l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="6dc07-177">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="6dc07-178">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-178">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-179">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1001* (ou tout autre numéro de contenant de votre choix).</span><span class="sxs-lookup"><span data-stu-id="6dc07-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="6dc07-180">La page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article** affiche **Position 1 du contenant**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="6dc07-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-181">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-182">Vous devez maintenant spécifier la quantité de l’article inventorié sur le contenant.</span><span class="sxs-lookup"><span data-stu-id="6dc07-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="6dc07-183">Définissez le champ **Qté** sur *10*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="6dc07-184">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-184">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-185">La page affiche l’emplacement que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="6dc07-185">The page shows the location that you entered.</span></span> <span data-ttu-id="6dc07-186">Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »</span><span class="sxs-lookup"><span data-stu-id="6dc07-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="6dc07-187">Sélectionnez **Actualiser** pour ajouter un autre inventaire dans l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="6dc07-188">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0002*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="6dc07-189">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-189">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-190">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1002* (ou tout autre numéro de contenant de votre choix, à condition qu’il diffère du numéro de contenant que vous avez spécifié précédemment).</span><span class="sxs-lookup"><span data-stu-id="6dc07-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="6dc07-191">Modifiez la position du contenant en définissant le champ **Position du contenant** sur *2*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="6dc07-192">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-192">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-193">Spécifiez la quantité de l’article inventorié sur le contenant en définissant le champ **Qté** sur *10*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="6dc07-194">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-194">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-195">La page affiche l’emplacement que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="6dc07-195">The page shows the location that you entered.</span></span> <span data-ttu-id="6dc07-196">Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »</span><span class="sxs-lookup"><span data-stu-id="6dc07-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="6dc07-197">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-197">Select **OK**.</span></span>

<span data-ttu-id="6dc07-198">Le travail est maintenant terminé.</span><span class="sxs-lookup"><span data-stu-id="6dc07-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="6dc07-199">Inventaire ponctuel du deuxième emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-199">Spot-count the second location</span></span>

1. <span data-ttu-id="6dc07-200">Sur la page **Inventaire ponctuel**, définissez le champ **Emplacement** sur *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="6dc07-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-201">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-202">La page affiche l’emplacement que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="6dc07-202">The page shows the location that you entered.</span></span> <span data-ttu-id="6dc07-203">Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »</span><span class="sxs-lookup"><span data-stu-id="6dc07-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="6dc07-204">Sélectionnez **Actualiser** pour ajouter un inventaire dans l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="6dc07-205">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Article**, puis entrez la valeur *A0002*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="6dc07-206">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-206">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-207">Sur la page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article**, sélectionnez le champ **Contenant**, puis entrez la valeur *LP1003* (ou tout autre numéro de contenant de votre choix, à condition qu’il diffère des deux numéros de contenant que vous avez spécifiés dans la procédure précédente).</span><span class="sxs-lookup"><span data-stu-id="6dc07-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="6dc07-208">La page **Inventaire tournant : ajouter un nouveau contenant ou un nouvel article** affiche **Position 1 du contenant**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="6dc07-209">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-209">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-210">Spécifiez la quantité de l’article inventorié sur le contenant en définissant le champ **Qté** sur *10*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="6dc07-211">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-211">Select **OK**.</span></span>

    <span data-ttu-id="6dc07-212">La page affiche l’emplacement que vous avez entré.</span><span class="sxs-lookup"><span data-stu-id="6dc07-212">The page shows the location that you entered.</span></span> <span data-ttu-id="6dc07-213">Elle affiche également le message suivant : "Emplacement complet, ajouter un nouveau contenant ou un nouvel article ? »</span><span class="sxs-lookup"><span data-stu-id="6dc07-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="6dc07-214">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-214">Select **OK**.</span></span>

<span data-ttu-id="6dc07-215">Le travail est maintenant terminé.</span><span class="sxs-lookup"><span data-stu-id="6dc07-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="6dc07-216">Détails du travail</span><span class="sxs-lookup"><span data-stu-id="6dc07-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="6dc07-217">Les inventaires ponctuels à partir de l’application mobile créent un travail d’inventaire tournant dans Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6dc07-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="6dc07-218">Le travail nécessite que les inventaires soient acceptés avant d’être validés en stock.</span><span class="sxs-lookup"><span data-stu-id="6dc07-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="6dc07-219">Connectez-vous à Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6dc07-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="6dc07-220">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="6dc07-221">Sous l’onglet **Vue d’ensemble**, recherchez les lignes présentant les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="6dc07-222">**Type d’ordre de travail :** *Inventaire tournant*</span><span class="sxs-lookup"><span data-stu-id="6dc07-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="6dc07-223">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="6dc07-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="6dc07-224">**Statut du travail :** *Révision en attente*</span><span class="sxs-lookup"><span data-stu-id="6dc07-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="6dc07-225">Deux ID de travail devraient avoir été créés pour ces lignes.</span><span class="sxs-lookup"><span data-stu-id="6dc07-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="6dc07-226">Les inventaires de ces deux ID de travail doivent être acceptés.</span><span class="sxs-lookup"><span data-stu-id="6dc07-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="6dc07-227">Dans la grille, sélectionnez le premier ID de travail pour le type d’ordre de travail *Inventaire tournant*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="6dc07-228">Dans le volet Actions, sous l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="6dc07-229">Deux lignes sont affichées, une pour chaque article et contenant.</span><span class="sxs-lookup"><span data-stu-id="6dc07-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="6dc07-230">Les valeurs des champs **Quantité comptée**, **Emplacement**, **Contenant** et **Article** doivent correspondre aux entrées d’inventaire que vous avez créées sur l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6dc07-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="6dc07-231">Si l’un de ces champs n’est pas visible, sélectionnez **Afficher les dimensions** dans le volet Actions pour les ajouter à la grille.</span><span class="sxs-lookup"><span data-stu-id="6dc07-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="6dc07-232">Sélectionnez les deux lignes.</span><span class="sxs-lookup"><span data-stu-id="6dc07-232">Select both lines.</span></span>
1. <span data-ttu-id="6dc07-233">Dans le volet Actions, sélectionnez **Accepter l’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="6dc07-234">Vous recevez un message « Validation - Journal ».</span><span class="sxs-lookup"><span data-stu-id="6dc07-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="6dc07-235">Sélectionnez **Détails du message** pour afficher le numéro de journal validé.</span><span class="sxs-lookup"><span data-stu-id="6dc07-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="6dc07-236">Fermez les détails du message.</span><span class="sxs-lookup"><span data-stu-id="6dc07-236">Close the message details.</span></span>
1. <span data-ttu-id="6dc07-237">Actualisez la page **Travail**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="6dc07-238">Le premier ID de travail a été fermé et n’est plus affiché.</span><span class="sxs-lookup"><span data-stu-id="6dc07-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="6dc07-239">Pour afficher le travail fermé, cochez la case **Afficher fermé** au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="6dc07-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="6dc07-240">Vous allez maintenant accepter le travail pour le contenant dans l’emplacement *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="6dc07-241">Sous l’onglet **Vue d’ensemble**, sélectionnez le deuxième ID de travail pour le type d’ordre de travail *Inventaire tournant*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="6dc07-242">Dans le volet Actions, sous l’onglet **Travail**, dans le groupe **Travail**, sélectionnez **Inventaire tournant**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="6dc07-243">Une ligne est affichée, pour l’article et le contenant.</span><span class="sxs-lookup"><span data-stu-id="6dc07-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="6dc07-244">Les valeurs des champs **Quantité comptée**, **Emplacement**, **Contenant** et **Article** doivent correspondre aux entrées d’inventaire que vous avez créées sur l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="6dc07-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="6dc07-245">Sélectionnez la ligne.</span><span class="sxs-lookup"><span data-stu-id="6dc07-245">Select the line.</span></span>
1. <span data-ttu-id="6dc07-246">Dans le volet Actions, sélectionnez **Accepter l’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="6dc07-247">Vous recevez un message « Validation - Journal ».</span><span class="sxs-lookup"><span data-stu-id="6dc07-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="6dc07-248">Sélectionnez **Détails du message** pour afficher le numéro de journal validé.</span><span class="sxs-lookup"><span data-stu-id="6dc07-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="6dc07-249">Fermez les détails du message.</span><span class="sxs-lookup"><span data-stu-id="6dc07-249">Close the message details.</span></span>
1. <span data-ttu-id="6dc07-250">Actualisez la page **Travail**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="6dc07-251">Le deuxième ID de travail a été fermé et n’est plus affiché.</span><span class="sxs-lookup"><span data-stu-id="6dc07-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="6dc07-252">Pour afficher le travail fermé, cochez la case **Afficher fermé** au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="6dc07-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="6dc07-253">Disponible par emplacement</span><span class="sxs-lookup"><span data-stu-id="6dc07-253">On-hand by location</span></span>

1. <span data-ttu-id="6dc07-254">Allez dans **Gestion des entrepôts \> Recherches et états \> Disponible par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="6dc07-255">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-255">Set the following values:</span></span>

    - <span data-ttu-id="6dc07-256">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="6dc07-256">**Site:** *6*</span></span>
    - <span data-ttu-id="6dc07-257">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="6dc07-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="6dc07-258">**Actualiser dans plusieurs emplacements :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="6dc07-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="6dc07-259">Notez que l’emplacement *01A01R1S1B* a deux contenants :</span><span class="sxs-lookup"><span data-stu-id="6dc07-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="6dc07-260">**A0001**, où le champ **Position du contenant** est défini sur *1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="6dc07-261">**A0002**, où le champ **Position du contenant** est défini sur *2*</span><span class="sxs-lookup"><span data-stu-id="6dc07-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="6dc07-262">Notez que l’emplacement *01A01R1S2B* a un contenant :</span><span class="sxs-lookup"><span data-stu-id="6dc07-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="6dc07-263">**A0002**, où le champ **Position du contenant** est défini sur *1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="6dc07-264">Scénario de commande client</span><span class="sxs-lookup"><span data-stu-id="6dc07-264">Sales order scenario</span></span>

<span data-ttu-id="6dc07-265">Maintenant que la fonctionnalité *Positionnement des contenants dans un emplacement* a été configurée et que le stock a été placé, vous devez créer une commande client pour générer un travail de prélèvement qui va demander au magasinier de sélectionner l’article *A0002* dans l’emplacement de stock où l’ID de palette est en position *1*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="6dc07-266">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6dc07-267">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6dc07-268">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6dc07-269">**Compte client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="6dc07-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="6dc07-270">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="6dc07-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="6dc07-271">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-271">Select **OK**.</span></span>
1. <span data-ttu-id="6dc07-272">Une nouvelle ligne est ajoutée à la grille dans l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6dc07-273">Sur cette nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc07-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="6dc07-274">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6dc07-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="6dc07-275">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="6dc07-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="6dc07-276">Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="6dc07-277">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock pour la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="6dc07-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="6dc07-278">Fermez la page **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="6dc07-279">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6dc07-280">Vous recevez un message d’information indiquant l’ID de vague et l’ID d’expédition créés pour la commande.</span><span class="sxs-lookup"><span data-stu-id="6dc07-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="6dc07-281">Dans l’organisateur **Lignes de commande client**, dans le menu **Entrepôt** au-dessus de la grille, sélectionnez **Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="6dc07-282">La page **Travail** apparaît et affiche le travail créé pour la ligne de vente.</span><span class="sxs-lookup"><span data-stu-id="6dc07-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="6dc07-283">Prenez note de l’ID de travail affiché.</span><span class="sxs-lookup"><span data-stu-id="6dc07-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="6dc07-284">Scénario de prélévement des ventes</span><span class="sxs-lookup"><span data-stu-id="6dc07-284">Sales picking scenario</span></span>

1. <span data-ttu-id="6dc07-285">Ouvrez l’application mobile et connectez-vous à l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="6dc07-286">Allez à **Sortant \> Prélèvement des ventes**.</span><span class="sxs-lookup"><span data-stu-id="6dc07-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="6dc07-287">Sur la page **Analyser un ID travail/ID contenant**, sélectionnez le champ **ID**, puis entrez l’ID de travail à partir de la ligne de vente.</span><span class="sxs-lookup"><span data-stu-id="6dc07-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="6dc07-288">Notez que le travail de prélèvement vous demande de sélectionner l’article *A0002* dans l’emplacement *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="6dc07-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="6dc07-289">Vous recevez cette instruction car l’article *A0002* se trouve sur un contenant en position *1* dans cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="6dc07-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="6dc07-290">![Emplacement en position 1](media/LocationLicensePlatePositioning.png "Emplacement en position 1")</span><span class="sxs-lookup"><span data-stu-id="6dc07-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="6dc07-291">Entrez l’ID de contenant que vous avez créé pour l’emplacement, puis suivez les invites pour sélectionner la commande client.</span><span class="sxs-lookup"><span data-stu-id="6dc07-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]