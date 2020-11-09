---
title: Créneaux de l’entrepôt
description: Cette rubrique fournit des informations sur les créneaux de l’entrepôt. Les créneaux de l’entrepôt vous permettent de consolider la demande par article et unité de mesure à partir des commandes ayant le statut Commandé, Réservé ou Validé. Ils permettent aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ed9e6eae2ecc8de8d5eeef4699678e93dd74f193
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017412"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="b4d43-105">Créneaux de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="b4d43-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4d43-106">Les créneaux de l’entrepôt vous permettent de consolider la demande par article et unité de mesure à partir des commandes ayant le statut *Commandé* , *Réservé* ou *Validé*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered* , *Reserved* , or *Released*.</span></span> <span data-ttu-id="b4d43-107">La demande générée peut ensuite être appliquée aux emplacements qui seront utilisés pour le prélèvement, en fonction de la quantité, de l’unité, des dimensions physiques, des emplacements fixes, etc.</span><span class="sxs-lookup"><span data-stu-id="b4d43-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="b4d43-108">Une fois le plan des créneaux établi, le travail de réapprovisionnement peut être créé pour apporter la quantité appropriée de stock à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="b4d43-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="b4d43-109">Cette fonctionnalité permet aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="b4d43-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="b4d43-110">Activer la fonction de créneaux d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="b4d43-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="b4d43-111">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="b4d43-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="b4d43-112">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b4d43-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b4d43-113">Dans l'espace de travail **Gestion des fonctionnalités** , la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="b4d43-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b4d43-114">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="b4d43-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b4d43-115">**Nom de la fonctionnalité :** *Fonctionnalité de créneaux d’entrepôt*</span><span class="sxs-lookup"><span data-stu-id="b4d43-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="b4d43-116">Paramétrer les créneaux d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="b4d43-116">Set up warehouse slotting</span></span>

<span data-ttu-id="b4d43-117">Pour utiliser les créneaux d’entrepôt, configurez les éléments suivants dans votre système.</span><span class="sxs-lookup"><span data-stu-id="b4d43-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="b4d43-118">Créer des niveaux d’unité de mesure pour les créneaux</span><span class="sxs-lookup"><span data-stu-id="b4d43-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="b4d43-119">Les niveaux d’unité de mesure permettent de regrouper plusieurs unités de mesure à des fins de créneaux.</span><span class="sxs-lookup"><span data-stu-id="b4d43-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="b4d43-120">Par exemple, si plusieurs tailles de boîtes sont toutes prélevées dans la même zone de prélèvement de boîtes, un niveau peut être créé pour toutes les tailles.</span><span class="sxs-lookup"><span data-stu-id="b4d43-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="b4d43-121">**Une ligne doit être créée pour chaque unité de mesure qui doit faire partie du niveau.**</span><span class="sxs-lookup"><span data-stu-id="b4d43-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="b4d43-122">Allez à **Gestion des entrepôts \> Paramétrer \> Réapprovisionnement \> Unité de mesure des niveaux de créneaux**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="b4d43-123">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-123">Select **New**.</span></span>
1. <span data-ttu-id="b4d43-124">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="b4d43-125">**Niveau d’unité de mesure :** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="b4d43-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="b4d43-126">**Description :** *Chaque palette de boîte*</span><span class="sxs-lookup"><span data-stu-id="b4d43-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="b4d43-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-127">Select **Save**.</span></span>
1. <span data-ttu-id="b4d43-128">Sur l’organisateur **Unités de mesure** , sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b4d43-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4d43-129">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-130">**Unité :** *Boîte*</span><span class="sxs-lookup"><span data-stu-id="b4d43-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="b4d43-131">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b4d43-132">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="b4d43-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b4d43-133">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="b4d43-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b4d43-134">Cliquez sur **Nouveau** pour ajouter une seconde ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b4d43-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="b4d43-135">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-136">**Unité :** *ea*</span><span class="sxs-lookup"><span data-stu-id="b4d43-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="b4d43-137">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b4d43-138">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="b4d43-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b4d43-139">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="b4d43-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b4d43-140">Cliquez sur **Nouveau** pour ajouter une troisième ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b4d43-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="b4d43-141">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-142">**Unité :** *PL*</span><span class="sxs-lookup"><span data-stu-id="b4d43-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="b4d43-143">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="b4d43-144">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="b4d43-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="b4d43-145">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="b4d43-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="b4d43-146">Sélectionnez **Enregistrer** pour enregistrer le niveau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="b4d43-147">Créer un code directif pour le créneau</span><span class="sxs-lookup"><span data-stu-id="b4d43-147">Create a directive code for slotting</span></span>

<span data-ttu-id="b4d43-148">Vous devez sélectionner le code de directive à associer à un modèle.</span><span class="sxs-lookup"><span data-stu-id="b4d43-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="b4d43-149">Allez dans **Gestion des entrepôts \> Configuration \> Codes de directives**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="b4d43-150">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b4d43-151">Dans le champ **Code de directive** , entrez *Créneaux*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="b4d43-152">Dans le champ **Description de la directive** , entrez *Créneaux*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="b4d43-153">Paramétrer les modèles de créneaux</span><span class="sxs-lookup"><span data-stu-id="b4d43-153">Set up slotting templates</span></span>

<span data-ttu-id="b4d43-154">Chaque modèle de créneau contrôle la façon dont le stock est affecté aux emplacements pour un entrepôt spécifique.</span><span class="sxs-lookup"><span data-stu-id="b4d43-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="b4d43-155">Chaque modèle doit inclure une ligne pour chaque spécification de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="b4d43-156">Utilisez les procédures de cette section pour configurer des modèles de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="b4d43-157">Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de créneaux**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="b4d43-158">Sélectionnez **Nouveau** pour créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="b4d43-158">Select **New** to create a template.</span></span>

<span data-ttu-id="b4d43-159">Ensuite, vous devez configurer l’en-tête du modèle, les spécifications de créneau et les directives d’emplacement, comme expliqué dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="b4d43-160">Configurer un en-tête de modèle de créneau</span><span class="sxs-lookup"><span data-stu-id="b4d43-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="b4d43-161">Dans l’en-tête du modèle, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="b4d43-162">**Modèle de créneau :** _61_</span><span class="sxs-lookup"><span data-stu-id="b4d43-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="b4d43-163">**Description :** _61_</span><span class="sxs-lookup"><span data-stu-id="b4d43-163">**Description:** _61_</span></span>
    - <span data-ttu-id="b4d43-164">**Type de demande :** *Commande client*</span><span class="sxs-lookup"><span data-stu-id="b4d43-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="b4d43-165">Actuellement, *Commande client* est le seul type de demande pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b4d43-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="b4d43-166">**Stratégie de demande :** _Commandé_</span><span class="sxs-lookup"><span data-stu-id="b4d43-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="b4d43-167">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="b4d43-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="b4d43-168">**Commandé** - La quantité totale commandée sur la commande client doit être considérée comme une demande.</span><span class="sxs-lookup"><span data-stu-id="b4d43-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="b4d43-169">**Réservé** - Seules les quantités de ligne de commande client réservées (physiques et commandées) doivent être considérées comme une demande.</span><span class="sxs-lookup"><span data-stu-id="b4d43-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="b4d43-170">**Entrepôt :** _61_</span><span class="sxs-lookup"><span data-stu-id="b4d43-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="b4d43-171">**Autoriser la demande de vague à utiliser des quantités non réservées :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="b4d43-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="b4d43-172">Vous pouvez également spécifier une requête pour réduire l’étendue de la demande évaluée.</span><span class="sxs-lookup"><span data-stu-id="b4d43-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="b4d43-173">Paramétrer les spécifications de créneau pour chaque modèle</span><span class="sxs-lookup"><span data-stu-id="b4d43-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="b4d43-174">Pour chaque modèle que vous créez, procédez comme suit pour ajouter une ligne pour chaque spécification de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="b4d43-175">Sur l’organisateur **Détails du modèle de créneau** , sélectionnez **Nouveau** pour créer un modèle de ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="b4d43-176">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-177">**Séquence :** _1_</span><span class="sxs-lookup"><span data-stu-id="b4d43-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="b4d43-178">**Description :** _Emplacement fixe_</span><span class="sxs-lookup"><span data-stu-id="b4d43-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="b4d43-179">**Quantité minimale :** _1_</span><span class="sxs-lookup"><span data-stu-id="b4d43-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="b4d43-180">Ce champ définit la quantité minimale de demande requise pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="b4d43-181">**Quantité maximale :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b4d43-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="b4d43-182">Ce champ définit la quantité maximale de demande valide pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="b4d43-183">**Unité :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="b4d43-184">Ce champ définit l’unité de mesure à laquelle les quantités minimale et maximale se réfèrent.</span><span class="sxs-lookup"><span data-stu-id="b4d43-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="b4d43-185">**Niveau d’unité de mesure :** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="b4d43-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="b4d43-186">Ce champ définit les unités de mesure de demande valides pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="b4d43-187">(Pour plus d’informations, voir la section [Paramétrer les niveaux d’unités de mesure des créneaux](#unit-tiers) plus haut dans cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="b4d43-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="b4d43-188">**Attribuer des critères de créneau :** _Tenir compte de la quantité_</span><span class="sxs-lookup"><span data-stu-id="b4d43-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="b4d43-189">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="b4d43-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="b4d43-190">**Supposer un emplacement vide** - Ce système doit supposer que tous les emplacements dans la zone de prélèvement sont vides et ne doit pas vérifier ces emplacements pour le stock.</span><span class="sxs-lookup"><span data-stu-id="b4d43-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="b4d43-191">**Tenir compte de la quantité** - Le système doit vérifier le stock des emplacements dans la zone de prélèvement et doit ignorer les emplacements non vides.</span><span class="sxs-lookup"><span data-stu-id="b4d43-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="b4d43-192">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="b4d43-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="b4d43-193">Ce champ définit la directive d’emplacement utilisée pour trouver l’emplacement de prélèvement du travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="b4d43-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="b4d43-194">**Emplacement de débordement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="b4d43-195">Ce champ définit l’emplacement dans lequel le stock est rangé si aucun emplacement ne peut être trouvé pour la quantité lorsque la ligne est traitée.</span><span class="sxs-lookup"><span data-stu-id="b4d43-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="b4d43-196">**Autoriser un creux :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="b4d43-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="b4d43-197">Lorsque cette option est définie sur *Oui* , si aucune demande ne peut être établie en créneau, un travail de mouvement sera créé pour retirer le stock des emplacements où il y en a, mais où rien n’a été réparti en créneaux.</span><span class="sxs-lookup"><span data-stu-id="b4d43-197">When this option is set to *Yes* , if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="b4d43-198">Le modèle est ensuite réexécuté.</span><span class="sxs-lookup"><span data-stu-id="b4d43-198">The template is then run again.</span></span> <span data-ttu-id="b4d43-199">Cette fois, il ignore le stock des emplacements.</span><span class="sxs-lookup"><span data-stu-id="b4d43-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="b4d43-200">Cette fonctionnalité fonctionne mieux lorsque le champ **Attribuer des critères de créneau** est défini sur _Tenir compte de la quantité_.</span><span class="sxs-lookup"><span data-stu-id="b4d43-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="b4d43-201">**Utilisation d’emplacement fixe :** _N’utiliser des emplacements fixes que pour le produit_</span><span class="sxs-lookup"><span data-stu-id="b4d43-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="b4d43-202">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="b4d43-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="b4d43-203">**Emplacements fixes et non fixes** - Le système ne doit pas se limiter à n’utiliser que des emplacements fixes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="b4d43-204">**N’utiliser des emplacements fixes que pour le produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour le produit.</span><span class="sxs-lookup"><span data-stu-id="b4d43-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="b4d43-205">**N’utiliser des emplacements fixes que pour la variante de produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour la variante de produit.</span><span class="sxs-lookup"><span data-stu-id="b4d43-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="b4d43-206">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-206">Select **Save**.</span></span>
1. <span data-ttu-id="b4d43-207">Cliquez sur **Nouveau** pour créer une seconde ligne de modèle.</span><span class="sxs-lookup"><span data-stu-id="b4d43-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="b4d43-208">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-209">**Séquence :** _2_</span><span class="sxs-lookup"><span data-stu-id="b4d43-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="b4d43-210">**Description :** _Autre_</span><span class="sxs-lookup"><span data-stu-id="b4d43-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="b4d43-211">**Quantité minimale :** _1_</span><span class="sxs-lookup"><span data-stu-id="b4d43-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="b4d43-212">**Quantité maximale :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b4d43-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="b4d43-213">**Unité :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="b4d43-214">**Niveau d’unité de mesure :** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="b4d43-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="b4d43-215">**Attribuer des critères de créneau :** _Tenir compte de la quantité_</span><span class="sxs-lookup"><span data-stu-id="b4d43-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="b4d43-216">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="b4d43-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="b4d43-217">**Emplacement de débordement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="b4d43-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="b4d43-218">**Autoriser un creux :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="b4d43-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="b4d43-219">**Utiliser des emplacements fixes :** _Emplacements fixes et non fixes_</span><span class="sxs-lookup"><span data-stu-id="b4d43-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="b4d43-220">Dans la requête pour la deuxième ligne, vous allez maintenant spécifier les critères utilisés pour déterminer vers quels emplacements la demande pour cette ligne peut être insérée en créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="b4d43-221">Sélectionnez la ligne où le champ **Séquence** est défini sur *2*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="b4d43-222">Sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="b4d43-223">Sous l'onglet **Plage** , sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b4d43-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4d43-224">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-225">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="b4d43-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="b4d43-226">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="b4d43-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="b4d43-227">**Champ :** *Location profile ID*</span><span class="sxs-lookup"><span data-stu-id="b4d43-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="b4d43-228">**Critères :** *Prélever-06* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Prélever-06* - *Site de prélèvement 6*.)</span><span class="sxs-lookup"><span data-stu-id="b4d43-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="b4d43-229">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="b4d43-230">Définir des instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="b4d43-230">Set up location directives</span></span>

<span data-ttu-id="b4d43-231">Au moins une directive d’emplacement doit être configurée pour prendre en charge les choix de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="b4d43-232">Utilisez les procédures de cette section pour configurer une nouvelle *directive sur l’emplacement de réapprovisionnement* pour les pics de créneaux.</span><span class="sxs-lookup"><span data-stu-id="b4d43-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="b4d43-233">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b4d43-234">Dans le volet gauche, dans le champ **Type d’ordre de travail** , cliquez sur *Réapprovisionnement*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="b4d43-235">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b4d43-236">Dans l’en-tête de la nouvelle directive d’emplacement, dans le champ **Nom** , entrez *Prélèvement de créneau 61*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="b4d43-237">Configurer l’organisateur Directives d’emplacement</span><span class="sxs-lookup"><span data-stu-id="b4d43-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="b4d43-238">Dans l’organisateur **Directives d’emplacement** , définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="b4d43-239">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="b4d43-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="b4d43-240">**Type de travail :** _Choisir_</span><span class="sxs-lookup"><span data-stu-id="b4d43-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="b4d43-241">**Site :** _6_</span><span class="sxs-lookup"><span data-stu-id="b4d43-241">**Site:** _6_</span></span>
    - <span data-ttu-id="b4d43-242">**Entrepôt :** _61_</span><span class="sxs-lookup"><span data-stu-id="b4d43-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="b4d43-243">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="b4d43-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="b4d43-244">Sélectionnez **Enregistrer** pour rendre l'organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="b4d43-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="b4d43-245">Configurer l’organisateur Lignes</span><span class="sxs-lookup"><span data-stu-id="b4d43-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="b4d43-246">Dans l’organisateur **Lignes** , cliquez sur **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="b4d43-247">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-247">On the new line, set the following values.</span></span> <span data-ttu-id="b4d43-248">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="b4d43-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="b4d43-249">**Quantité de départ :** _0_</span><span class="sxs-lookup"><span data-stu-id="b4d43-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="b4d43-250">**Quantité d’arrivée :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="b4d43-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="b4d43-251">Sélectionnez **Enregistrer** pour rendre l'organisateur **Actions d'instruction d'emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="b4d43-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="b4d43-252">Configurer l’organisateur Actions des directives d’emplacement</span><span class="sxs-lookup"><span data-stu-id="b4d43-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="b4d43-253">Dans l’organisateur **Actions des directives d’emplacement** , cliquez sur **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="b4d43-254">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-254">On the new line, set the following values.</span></span> <span data-ttu-id="b4d43-255">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="b4d43-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="b4d43-256">**Nom :** _Vrac_</span><span class="sxs-lookup"><span data-stu-id="b4d43-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="b4d43-257">**Stratégie :** _Aucun_</span><span class="sxs-lookup"><span data-stu-id="b4d43-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="b4d43-258">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** disponible.</span><span class="sxs-lookup"><span data-stu-id="b4d43-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="b4d43-259">Modifier la requête</span><span class="sxs-lookup"><span data-stu-id="b4d43-259">Edit the query</span></span>

1. <span data-ttu-id="b4d43-260">Dans l’organisateur **Actions de directive d’emplacement** , sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="b4d43-261">Sous l'onglet **Plage** , sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="b4d43-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4d43-262">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-263">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="b4d43-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="b4d43-264">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="b4d43-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="b4d43-265">**Champ :** *ID zone*</span><span class="sxs-lookup"><span data-stu-id="b4d43-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="b4d43-266">**Critères :** *Vrac* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Vrac*.)</span><span class="sxs-lookup"><span data-stu-id="b4d43-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="b4d43-267">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b4d43-268">Scénario</span><span class="sxs-lookup"><span data-stu-id="b4d43-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="b4d43-269">Paramétrage du scénario</span><span class="sxs-lookup"><span data-stu-id="b4d43-269">Set up the scenario</span></span>

<span data-ttu-id="b4d43-270">Pour ce scénario, utilisez les exemples de données intégrés et créez les enregistrements décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="b4d43-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="b4d43-271">Utiliser les exemples de données USMF</span><span class="sxs-lookup"><span data-stu-id="b4d43-271">Use the USMF sample data</span></span>

<span data-ttu-id="b4d43-272">Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="b4d43-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="b4d43-273">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="b4d43-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="b4d43-274">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="b4d43-274">Create demand</span></span>

<span data-ttu-id="b4d43-275">Suivez ces étapes pour créer la demande à laquelle vous allez appliquer le créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="b4d43-276">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="b4d43-277">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="b4d43-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="b4d43-278">Dans la boîte de dialogue **Créer une commande client** , dans le champ **Compte client** , sélectionnez _US-007_.</span><span class="sxs-lookup"><span data-stu-id="b4d43-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="b4d43-279">Dans le champ **Entrepôt** , sélectionnez _61_.</span><span class="sxs-lookup"><span data-stu-id="b4d43-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="b4d43-280">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-280">Select **OK**.</span></span>
1. <span data-ttu-id="b4d43-281">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="b4d43-281">The new sales order is opened.</span></span> <span data-ttu-id="b4d43-282">Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b4d43-283">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-284">**Article :** _L0101_</span><span class="sxs-lookup"><span data-stu-id="b4d43-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="b4d43-285">**Quantité :** _20_</span><span class="sxs-lookup"><span data-stu-id="b4d43-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="b4d43-286">Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="b4d43-287">**Article :** _T0100_</span><span class="sxs-lookup"><span data-stu-id="b4d43-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="b4d43-288">**Quantité :** _8_</span><span class="sxs-lookup"><span data-stu-id="b4d43-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="b4d43-289">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-289">Select **Save**.</span></span>
1. <span data-ttu-id="b4d43-290">Sélectionnez **Nouveau** pour créer une deuxième commande client.</span><span class="sxs-lookup"><span data-stu-id="b4d43-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="b4d43-291">Dans la boîte de dialogue **Créer une commande client** , dans le champ **Compte client** , sélectionnez _US-008_.</span><span class="sxs-lookup"><span data-stu-id="b4d43-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="b4d43-292">Dans le champ **Entrepôt** , sélectionnez _61_.</span><span class="sxs-lookup"><span data-stu-id="b4d43-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="b4d43-293">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="b4d43-293">The new sales order is opened.</span></span> <span data-ttu-id="b4d43-294">Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b4d43-295">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="b4d43-296">**Article :** _T0100_</span><span class="sxs-lookup"><span data-stu-id="b4d43-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="b4d43-297">**Quantité :** _1_</span><span class="sxs-lookup"><span data-stu-id="b4d43-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="b4d43-298">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="b4d43-299">Exécuter un scénario de créneau typique</span><span class="sxs-lookup"><span data-stu-id="b4d43-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="b4d43-300">Une fois que tous les éléments prérequis sont en place, comme décrit dans la section précédente, vous êtes prêt à essayer la fonctionnalité en effectuant chaque exercice de cette section.</span><span class="sxs-lookup"><span data-stu-id="b4d43-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="b4d43-301">Générer une demande</span><span class="sxs-lookup"><span data-stu-id="b4d43-301">Generate demand</span></span>

1. <span data-ttu-id="b4d43-302">Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de créneaux** , puis sélectionnez le modèle de créneau créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="b4d43-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates** , and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="b4d43-303">Dans le volet Actions, sélectionnez **Générer la demande**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="b4d43-304">Cette commande évalue toute la demande qui se trouve dans le système et qui correspond à la requête de modèle de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="b4d43-305">La demande totale de toutes les commandes est ensuite consolidée sur une ligne par quantité/unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="b4d43-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="b4d43-306">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="b4d43-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="b4d43-307">Demande de créneaux</span><span class="sxs-lookup"><span data-stu-id="b4d43-307">Slotting demand</span></span>

<span data-ttu-id="b4d43-308">La *demande de créneau* affiche les résultats de la génération de la demande, en fonction de la configuration du modèle de créneau.</span><span class="sxs-lookup"><span data-stu-id="b4d43-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="b4d43-309">Dans le volet Actions, sélectionnez **Demande de créneau** pour afficher les résultats de la commande **Générer une demande**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="b4d43-310">Les lignes de la demande de créneau peuvent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="b4d43-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="b4d43-311">Vous pouvez supprimer une ligne, ajouter une nouvelle ligne ou modifier les détails de la ligne.</span><span class="sxs-lookup"><span data-stu-id="b4d43-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="b4d43-312">Vous pouvez modifier la demande manuellement ou l’importer à partir d’un système externe à l’aide de la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="b4d43-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="b4d43-313">Tout ce qui se trouve dans le créneau sera utilisé à l’étape suivante, peu importe d’où il vient.</span><span class="sxs-lookup"><span data-stu-id="b4d43-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="b4d43-314">Localiser la demande</span><span class="sxs-lookup"><span data-stu-id="b4d43-314">Locate demand</span></span>

<span data-ttu-id="b4d43-315">Une fois la demande générée, vous devez utiliser la commande **Localiser la demande** pour générer le *plan de créneau*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="b4d43-316">Dans le volet Actions, sélectionnez **Localiser la demande**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="b4d43-317">Le processus de créneau s’exécute.</span><span class="sxs-lookup"><span data-stu-id="b4d43-317">The slotting process runs.</span></span> <span data-ttu-id="b4d43-318">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="b4d43-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="b4d43-319">Plan de créneaux</span><span class="sxs-lookup"><span data-stu-id="b4d43-319">Slotting plan</span></span>

<span data-ttu-id="b4d43-320">Le plan de créneau indique l’emplacement auquel chaque article/quantité a été affecté(e), si un débordement a été utilisé, si un travail de creux a été créé et la ligne de modèle utilisée.</span><span class="sxs-lookup"><span data-stu-id="b4d43-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="b4d43-321">**Toute demande qui n’a pas pu être insérée dans un créneau est surlignée en rouge.**</span><span class="sxs-lookup"><span data-stu-id="b4d43-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="b4d43-322">Dans le volet Actions, sélectionnez **Plan de créneau** pour voir les résultats.</span><span class="sxs-lookup"><span data-stu-id="b4d43-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="b4d43-323">Créer un réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="b4d43-323">Create replenishment</span></span>

<span data-ttu-id="b4d43-324">Une fois le plan de créneau créé, vous devez créer un *travail de réapprovisionnement* , sur la base du plan.</span><span class="sxs-lookup"><span data-stu-id="b4d43-324">After the slotting plan has been created, you must create *replenishment work* , based on the plan.</span></span>

- <span data-ttu-id="b4d43-325">Dans le volet Actions, sélectionnez **Exécuter le réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="b4d43-326">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="b4d43-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="b4d43-327">Ce message indique le nombre d’en-têtes créés pour l’ID de build de travail.</span><span class="sxs-lookup"><span data-stu-id="b4d43-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="b4d43-328">Les directives d’emplacement qui seront utilisées sont identifiées en fonction du code de directive spécifié sur chaque ligne de modèle.</span><span class="sxs-lookup"><span data-stu-id="b4d43-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="b4d43-329">Conseils</span><span class="sxs-lookup"><span data-stu-id="b4d43-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="b4d43-330">Paramétrer les créneaux automatiques</span><span class="sxs-lookup"><span data-stu-id="b4d43-330">Set up automatic slotting</span></span>

<span data-ttu-id="b4d43-331">Une fois que tous les éléments requis sont en place, vous pouvez configurer l’exécution automatique des créneaux en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="b4d43-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="b4d43-332">Allez dans **Gestion des entrepôts \> Réapprovisionnement \> Exécuter le créneau**.</span><span class="sxs-lookup"><span data-stu-id="b4d43-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="b4d43-333">Spécifiez les étapes de création de créneaux à exécuter.</span><span class="sxs-lookup"><span data-stu-id="b4d43-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="b4d43-334">Sélectionnez une ou plusieurs des étapes de création de créneau suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4d43-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="b4d43-335">Générer une demande</span><span class="sxs-lookup"><span data-stu-id="b4d43-335">Generate demand</span></span>
    - <span data-ttu-id="b4d43-336">Localiser la demande</span><span class="sxs-lookup"><span data-stu-id="b4d43-336">Locate demand</span></span>
    - <span data-ttu-id="b4d43-337">Créer un travail de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="b4d43-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4d43-338">Les étapes de création de créneau sont progressives.</span><span class="sxs-lookup"><span data-stu-id="b4d43-338">The slotting steps are progressive.</span></span> <span data-ttu-id="b4d43-339">Si vous souhaitez sélectionner *Localiser la demande* , vous devez d’abord sélectionner *Générer une demande*.</span><span class="sxs-lookup"><span data-stu-id="b4d43-339">If you want to select *Locate demand* , you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="b4d43-340">Spécifiez le modèle de créneau à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b4d43-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="b4d43-341">Définissez la récurrence d’exécution automatique, si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="b4d43-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="b4d43-342">Pour les exercices du scénario, **ne paramétrez pas** la création de créneau automatique.</span><span class="sxs-lookup"><span data-stu-id="b4d43-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
