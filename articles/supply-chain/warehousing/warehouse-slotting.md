---
title: Créneaux de l’entrepôt
description: Cette rubrique fournit des informations sur les créneaux de l’entrepôt. Les créneaux de l’entrepôt vous permettent de consolider la demande par article et unité de mesure à partir des commandes ayant le statut Commandé, Réservé ou Validé. Ils permettent aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0851af976dd73b7f13372880587187f546091bec
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248593"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="ccc8f-105">Créneaux de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="ccc8f-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccc8f-106">Plusieurs fonctionnalités de créneaux d’entrepôt sont disponibles pour permettre aux gestionnaires d’entrepôt de planifier intelligemment les emplacements de prélèvement avant de passer des commandes à l’entrepôt et de créer des travaux de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="ccc8f-107">La *fonctionnalité de créneaux de l’entrepôt* vous permet de consolider la demande par article et unité de mesure à partir des commandes ayant le statut *Commandé*, *Réservé* ou *Validé*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="ccc8f-108">La demande générée peut ensuite être appliquée aux emplacements qui seront utilisés pour le prélèvement, en fonction de la quantité, de l’unité, des dimensions physiques, des emplacements fixes, etc.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="ccc8f-109">Une fois le plan des créneaux établi, le travail de réapprovisionnement peut être créé pour apporter la quantité appropriée de stock à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="ccc8f-110">La fonctionnalité *Créneaux d’entrepôt pour les ordres de transfert* permet aux responsables d’entrepôt de réapprovisionner les emplacements de prélèvement, en fonction de la demande des ordres de transfert qui ne sont pas encore validés vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="ccc8f-111">Cela garantit que les lieux de prélèvement incluront tous les articles requis pour les ordres de transfert après leur sortie dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="ccc8f-112">Cette fonctionnalité nécessite que vous activiez également la fonctionnalité *Fonctionnalité de créneaux d’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="ccc8f-113">La fonctionnalité *Améliorations de l’allocation des créneaux d’entrepôt* ajoute une option pour les exemples de lignes utilisées par la fonctionnalité *Fonctionnalité de créneaux d’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="ccc8f-114">L’option permet au système de prendre en compte le stock disponible existant à un emplacement cible.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="ccc8f-115">Par conséquent, moins de réapprovisionnements peuvent être générés pour les créneaux.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="ccc8f-116">La fonctionnalité *Améliorations de l’allocation des créneaux d’entrepôt* nécessite que vous activiez la fonctionnalité *Fonctionnalité de créneaux d’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="ccc8f-117">Il peut éventuellement être utilisé avec la fonctionnalité *Créneaux d’entrepôt pour les ordres de transfert*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="ccc8f-118">Activer les fonctionnalités de créneaux d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="ccc8f-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="ccc8f-119">Avant de pouvoir utiliser ces fonctionnalités, vous devez les activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="ccc8f-120">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut des fonctionnalités et les activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="ccc8f-121">Activez les fonctionnalités suivantes selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="ccc8f-122">Fonction Entreposage</span><span class="sxs-lookup"><span data-stu-id="ccc8f-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="ccc8f-123">Créneaux d’entrepôt pour les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="ccc8f-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccc8f-124">La fonctionnalité *Fonctionnalité de créneaux d’entrepôt* doit être activée avant cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="ccc8f-125">Améliorations de la répartition des créneaux d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="ccc8f-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ccc8f-126">La fonctionnalité *Fonctionnalité de créneaux d’entrepôt* doit être activée avant cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="ccc8f-127">Paramétrer les créneaux d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="ccc8f-127">Set up warehouse slotting</span></span>

<span data-ttu-id="ccc8f-128">Pour utiliser les créneaux d’entrepôt, configurez les éléments suivants dans votre système :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="ccc8f-129">Barèmes d’unité de mesure des créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="ccc8f-130">Codes instructions</span><span class="sxs-lookup"><span data-stu-id="ccc8f-130">Directive codes</span></span>
- <span data-ttu-id="ccc8f-131">Modèles de créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-131">Slotting templates</span></span>
- <span data-ttu-id="ccc8f-132">Instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="ccc8f-133">Créer des niveaux d’unité de mesure pour les créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="ccc8f-134">Les niveaux d’unité de mesure permettent de regrouper plusieurs unités de mesure à des fins de créneaux.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="ccc8f-135">Par exemple, si plusieurs tailles de boîtes sont toutes prélevées dans la même zone de prélèvement de boîtes, un niveau peut être créé pour toutes les tailles.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="ccc8f-136">**Une ligne doit être créée pour chaque unité de mesure qui doit faire partie du niveau.**</span><span class="sxs-lookup"><span data-stu-id="ccc8f-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="ccc8f-137">Allez à **Gestion des entrepôts \> Paramétrer \> Réapprovisionnement \> Unité de mesure des niveaux de créneaux**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="ccc8f-138">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-138">Select **New**.</span></span>
1. <span data-ttu-id="ccc8f-139">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-140">**Niveau d’unité de mesure :** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="ccc8f-141">**Description :** *Chaque palette de boîte*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="ccc8f-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-142">Select **Save**.</span></span>
1. <span data-ttu-id="ccc8f-143">Sur l’organisateur **Unités de mesure**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="ccc8f-144">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-145">**Unité :** *Boîte*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="ccc8f-146">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="ccc8f-147">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="ccc8f-148">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="ccc8f-149">Cliquez sur **Nouveau** pour ajouter une seconde ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="ccc8f-150">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-151">**Unité :** *ea*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="ccc8f-152">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="ccc8f-153">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="ccc8f-154">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="ccc8f-155">Cliquez sur **Nouveau** pour ajouter une troisième ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="ccc8f-156">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-157">**Unité :** *PL*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="ccc8f-158">**Description :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="ccc8f-159">Il sera rempli automatiquement lorsque vous enregistrerez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="ccc8f-160">**Classe d’unité :** *Quantité*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="ccc8f-161">Sélectionnez **Enregistrer** pour enregistrer le niveau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="ccc8f-162">Créer un code directif pour le créneau</span><span class="sxs-lookup"><span data-stu-id="ccc8f-162">Create a directive code for slotting</span></span>

<span data-ttu-id="ccc8f-163">Vous devez sélectionner le code de directive à associer à un modèle.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="ccc8f-164">Allez dans **Gestion des entrepôts \> Configuration \> Codes de directives**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="ccc8f-165">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ccc8f-166">Dans le champ **Code de directive**, entrez *Créneaux*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="ccc8f-167">Dans le champ **Description de la directive**, entrez *Créneaux*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="ccc8f-168">Paramétrer les modèles de créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-168">Set up slotting templates</span></span>

<span data-ttu-id="ccc8f-169">Chaque modèle de créneau contrôle la façon dont le stock est affecté aux emplacements pour un entrepôt spécifique.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="ccc8f-170">Chaque modèle doit inclure une ligne pour chaque spécification de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="ccc8f-171">Utilisez les procédures de cette section pour configurer des modèles de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="ccc8f-172">Allez dans **Gestion des entrepôts \> Paramétrage \> Réapprovisionnement \> Modèles de créneaux**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="ccc8f-173">Sélectionnez **Nouveau** pour créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-173">Select **New** to create a template.</span></span>

<span data-ttu-id="ccc8f-174">Ensuite, vous devez configurer l’en-tête du modèle, les spécifications de créneau et les directives d’emplacement, comme expliqué dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="ccc8f-175">La configuration des créneaux des ordres de transfert ressemble à la configuration des créneaux des commandes client, mais le champ **Type de demande** est défini sur *Ordres de transfert* au lieu de *Commande client*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="ccc8f-176">Configurer l’en-tête d’un modèle de créneau de commande client</span><span class="sxs-lookup"><span data-stu-id="ccc8f-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="ccc8f-177">Dans l’en-tête du modèle, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-178">**Modèle de créneau :** _61_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="ccc8f-179">**Description :** _61_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-179">**Description:** _61_</span></span>
    - <span data-ttu-id="ccc8f-180">**Type de demande :** *Commande client*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="ccc8f-181">Actuellement, les *Commandes client* et les *Ordres de transfert* sont les seuls types de demandes pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="ccc8f-182">Vous pouvez sélectionner *Ordres de transfert* seulement si la fonctionnalité *Créneaux d’entrepôt pour les ordres de transfert* est activée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="ccc8f-183">**Stratégie de demande :** _Commandé_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="ccc8f-184">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="ccc8f-185">**Commandé** - La quantité totale commandée sur la commande client doit être considérée comme une demande.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="ccc8f-186">**Réservé** - Seules les quantités de ligne de commande client réservées (physiques et commandées) doivent être considérées comme une demande.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="ccc8f-187">**Lancé** – La quantité lancée doit être considérée comme une demande.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="ccc8f-188">**Entrepôt :** _61_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="ccc8f-189">**Autoriser la demande de vague à utiliser des quantités non réservées :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="ccc8f-190">Vous pouvez également spécifier une requête pour réduire l’étendue de la demande évaluée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="ccc8f-191">Paramétrer les spécifications de créneau pour chaque modèle</span><span class="sxs-lookup"><span data-stu-id="ccc8f-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="ccc8f-192">Pour chaque modèle de commande client que vous créez, procédez comme suit pour ajouter une ligne pour chaque spécification de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="ccc8f-193">Sur l’organisateur **Détails du modèle de créneau**, sélectionnez **Nouveau** pour créer un modèle de ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="ccc8f-194">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-195">**Séquence :** _1_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="ccc8f-196">**Description :** _Emplacement fixe_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="ccc8f-197">**Quantité minimale :** _1_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="ccc8f-198">Ce champ définit la quantité minimale de demande requise pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="ccc8f-199">**Quantité maximale :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="ccc8f-200">Ce champ définit la quantité maximale de demande valide pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="ccc8f-201">**Unité :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="ccc8f-202">Ce champ définit l’unité de mesure à laquelle les quantités minimale et maximale se réfèrent.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="ccc8f-203">**Niveau d’unité de mesure :** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="ccc8f-204">Ce champ définit les unités de mesure de demande valides pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="ccc8f-205">(Pour plus d’informations, voir la section [Paramétrer les niveaux d’unités de mesure des créneaux](#unit-tiers) plus haut dans cette rubrique.)</span><span class="sxs-lookup"><span data-stu-id="ccc8f-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="ccc8f-206">**Attribuer des critères de créneau :** _Tenir compte de la quantité_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="ccc8f-207">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="ccc8f-208">**Supposer un emplacement vide** - Ce système doit supposer que tous les emplacements dans la zone de prélèvement sont vides et ne doit pas vérifier ces emplacements pour le stock.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="ccc8f-209">**Tenir compte de la quantité** - Le système doit vérifier le stock des emplacements dans la zone de prélèvement et doit ignorer les emplacements non vides.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="ccc8f-210">**Considérer comme disponible** – Le système doit vérifier si un emplacement cible contient des quantités non réservées pour l’article sur la ligne de demande.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="ccc8f-211">Si la quantité est suffisamment grande pour satisfaire au moins une unité de la ligne de demande, l’enregistrement de plan de créneau généré est réduit du montant disponible.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="ccc8f-212">Par exemple, si la demande est de 10 cartons et qu’un carton est disponible, la demande localisée sera de neuf cartons.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="ccc8f-213">Si la demande est de 10 cartons et qu’un de chaque est disponible, la demande localisée sera de 10 cartons.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="ccc8f-214">Cette valeur n’est disponible que lorsque la fonctionnalité *Améliorations de la répartition des créneaux d’entrepôt* est activée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="ccc8f-215">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="ccc8f-216">Ce champ définit la directive d’emplacement utilisée pour trouver l’emplacement de prélèvement du travail de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="ccc8f-217">**Emplacement de débordement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="ccc8f-218">Ce champ définit l’emplacement dans lequel le stock est rangé si aucun emplacement ne peut être trouvé pour la quantité lorsque la ligne est traitée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="ccc8f-219">**Autoriser un creux :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="ccc8f-220">Lorsque cette option est définie sur *Oui*, si aucune demande ne peut être établie en créneau, un travail de mouvement sera créé pour retirer le stock des emplacements où il y en a, mais où rien n’a été réparti en créneaux.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="ccc8f-221">Le modèle est ensuite réexécuté.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-221">The template is then run again.</span></span> <span data-ttu-id="ccc8f-222">Cette fois, il ignore le stock des emplacements.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="ccc8f-223">Cette fonctionnalité fonctionne mieux lorsque le champ **Attribuer des critères de créneau** est défini sur _Tenir compte de la quantité_.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="ccc8f-224">**Utilisation d’emplacement fixe :** _N’utiliser des emplacements fixes que pour le produit_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="ccc8f-225">Les valeurs suivantes sont disponibles dans ce champ :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="ccc8f-226">**Emplacements fixes et non fixes** - Le système ne doit pas se limiter à n’utiliser que des emplacements fixes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="ccc8f-227">**N’utiliser des emplacements fixes que pour le produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour le produit.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="ccc8f-228">**N’utiliser des emplacements fixes que pour la variante de produit** - Le système ne doit créer des créneaux qu’aux emplacements qui sont fixes pour la variante de produit.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="ccc8f-229">Si l’exemple de créneau contient au moins une ligne où le champ **Attribuer des critères de créneau** est défini sur *Considérer comme disponible*, les creux ne sont plus autorisés pour aucune ligne du modèle.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="ccc8f-230">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-230">Select **Save**.</span></span>
1. <span data-ttu-id="ccc8f-231">Cliquez sur **Nouveau** pour créer une seconde ligne de modèle.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="ccc8f-232">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-233">**Séquence :** _2_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="ccc8f-234">**Description :** _Autre_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="ccc8f-235">**Quantité minimale :** _1_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="ccc8f-236">**Quantité maximale :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="ccc8f-237">**Unité :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="ccc8f-238">**Niveau d’unité de mesure :** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="ccc8f-239">**Attribuer des critères de créneau :** _Tenir compte de la quantité_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="ccc8f-240">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="ccc8f-241">**Emplacement de débordement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="ccc8f-242">**Autoriser un creux :** _Oui_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="ccc8f-243">**Utiliser des emplacements fixes :** _Emplacements fixes et non fixes_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="ccc8f-244">Dans la requête pour la deuxième ligne, vous allez maintenant spécifier les critères utilisés pour déterminer vers quels emplacements la demande pour cette ligne peut être insérée en créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="ccc8f-245">Sélectionnez la ligne où le champ **Séquence** est défini sur *2*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="ccc8f-246">Sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="ccc8f-247">Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="ccc8f-248">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-249">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="ccc8f-250">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="ccc8f-251">**Champ :** *Location profile ID*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="ccc8f-252">**Critères :** *Prélever-06* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Prélever-06* - *Site de prélèvement 6*.)</span><span class="sxs-lookup"><span data-stu-id="ccc8f-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="ccc8f-253">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="ccc8f-254">Définir des instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-254">Set up location directives</span></span>

<span data-ttu-id="ccc8f-255">Au moins une directive d’emplacement doit être configurée pour prendre en charge les choix de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="ccc8f-256">Utilisez les procédures de cette section pour configurer une nouvelle *directive sur l’emplacement de réapprovisionnement* pour les pics de créneaux.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="ccc8f-257">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="ccc8f-258">Dans le volet gauche, dans le champ **Type d’ordre de travail**, cliquez sur *Réapprovisionnement*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="ccc8f-259">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ccc8f-260">Dans l’en-tête de la nouvelle directive d’emplacement, dans le champ **Nom**, entrez *Prélèvement de créneau 61*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="ccc8f-261">Dans le champ **Souche de N°**, acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="ccc8f-262">Configurer l’organisateur Directives d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="ccc8f-263">Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="ccc8f-264">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="ccc8f-265">**Type de travail :** _Choisir_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="ccc8f-266">**Site :** _6_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-266">**Site:** _6_</span></span>
    - <span data-ttu-id="ccc8f-267">**Entrepôt :** _61_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="ccc8f-268">**Code de directive :** _Créneau_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="ccc8f-269">Sélectionnez **Enregistrer** pour rendre l’organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="ccc8f-270">Configurer l’organisateur Lignes</span><span class="sxs-lookup"><span data-stu-id="ccc8f-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="ccc8f-271">Dans l’organisateur **Lignes**, cliquez sur **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="ccc8f-272">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="ccc8f-273">**Quantité de départ :** _0_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="ccc8f-274">**Quantité d’arrivée :** _1000000_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="ccc8f-275">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="ccc8f-276">Sélectionnez **Enregistrer** pour rendre l’organisateur **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="ccc8f-277">Configurer l’organisateur Actions des directives d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="ccc8f-278">Dans l’organisateur **Actions des directives d’emplacement**, cliquez sur **Nouveau** pour créer une ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="ccc8f-279">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-279">On the new line, set the following values.</span></span> <span data-ttu-id="ccc8f-280">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="ccc8f-281">**Souche de N° :** Acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="ccc8f-282">**Nom :** _Vrac_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="ccc8f-283">**Stratégie :** _Aucun_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="ccc8f-284">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="ccc8f-285">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** disponible.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="ccc8f-286">Modifier la requête</span><span class="sxs-lookup"><span data-stu-id="ccc8f-286">Edit the query</span></span>

1. <span data-ttu-id="ccc8f-287">Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="ccc8f-288">Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="ccc8f-289">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-290">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="ccc8f-291">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="ccc8f-292">**Champ :** *ID zone*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="ccc8f-293">**Critères :** *Vrac* (Sélectionnez le double signe plus \[**++**\] dans le champ pour développer la liste, puis sélectionnez *Vrac*.)</span><span class="sxs-lookup"><span data-stu-id="ccc8f-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="ccc8f-294">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="ccc8f-295">Scénario</span><span class="sxs-lookup"><span data-stu-id="ccc8f-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="ccc8f-296">Paramétrage du scénario</span><span class="sxs-lookup"><span data-stu-id="ccc8f-296">Set up the scenario</span></span>

<span data-ttu-id="ccc8f-297">Pour ce scénario, utilisez les exemples de données intégrés et créez les enregistrements décrits dans cette section.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="ccc8f-298">Utiliser les exemples de données USMF</span><span class="sxs-lookup"><span data-stu-id="ccc8f-298">Use the USMF sample data</span></span>

<span data-ttu-id="ccc8f-299">Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="ccc8f-300">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="ccc8f-301">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="ccc8f-301">Create demand</span></span>

<span data-ttu-id="ccc8f-302">Suivez ces étapes pour créer la demande à laquelle vous allez appliquer le créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="ccc8f-303">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="ccc8f-304">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="ccc8f-305">Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez _US-007_.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="ccc8f-306">Dans le champ **Entrepôt**, sélectionnez _61_.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="ccc8f-307">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-307">Select **OK**.</span></span>
1. <span data-ttu-id="ccc8f-308">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-308">The new sales order is opened.</span></span> <span data-ttu-id="ccc8f-309">Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ccc8f-310">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-311">**Article :** _L0101_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="ccc8f-312">**Quantité :** _20_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="ccc8f-313">Sélectionnez **Ajouter une ligne** pour ajouter une nouvelle ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="ccc8f-314">**Article :** _T0100_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="ccc8f-315">**Quantité :** _8_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="ccc8f-316">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-316">Select **Save**.</span></span>
1. <span data-ttu-id="ccc8f-317">Sélectionnez **Nouveau** pour créer une deuxième commande client.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="ccc8f-318">Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez _US-008_.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="ccc8f-319">Dans le champ **Entrepôt**, sélectionnez _61_.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="ccc8f-320">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-320">The new sales order is opened.</span></span> <span data-ttu-id="ccc8f-321">Elle comprend une ligne vide sur l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ccc8f-322">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="ccc8f-323">**Article :** _T0100_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="ccc8f-324">**Quantité :** _1_</span><span class="sxs-lookup"><span data-stu-id="ccc8f-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="ccc8f-325">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="ccc8f-326">Exécuter un scénario de créneau typique</span><span class="sxs-lookup"><span data-stu-id="ccc8f-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="ccc8f-327">Une fois que tous les éléments prérequis sont en place, comme décrit dans la section précédente, vous êtes prêt à essayer la fonctionnalité en effectuant chaque exercice de cette section.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="ccc8f-328">Générer une demande</span><span class="sxs-lookup"><span data-stu-id="ccc8f-328">Generate demand</span></span>

1. <span data-ttu-id="ccc8f-329">Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de créneaux**, puis sélectionnez le modèle de créneau créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="ccc8f-330">Dans le volet Actions, sélectionnez **Générer la demande**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="ccc8f-331">Cette commande évalue toute la demande qui se trouve dans le système et qui correspond à la requête de modèle de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="ccc8f-332">La demande totale de toutes les commandes est ensuite consolidée sur une ligne par quantité/unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="ccc8f-333">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="ccc8f-334">Demande de créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-334">Slotting demand</span></span>

<span data-ttu-id="ccc8f-335">La *demande de créneau* affiche les résultats de la génération de la demande, en fonction de la configuration du modèle de créneau.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="ccc8f-336">Dans le volet Actions, sélectionnez **Demande de créneau** pour afficher les résultats de la commande **Générer une demande**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="ccc8f-337">Les lignes de la demande de créneau peuvent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="ccc8f-338">Vous pouvez supprimer une ligne, ajouter une nouvelle ligne ou modifier les détails de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="ccc8f-339">Vous pouvez modifier la demande manuellement ou l’importer à partir d’un système externe à l’aide de la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="ccc8f-340">Tout ce qui se trouve dans le créneau sera utilisé à l’étape suivante, peu importe d’où il vient.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="ccc8f-341">Localiser la demande</span><span class="sxs-lookup"><span data-stu-id="ccc8f-341">Locate demand</span></span>

<span data-ttu-id="ccc8f-342">Une fois la demande générée, vous devez utiliser la commande **Localiser la demande** pour générer le *plan de créneau*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="ccc8f-343">Dans le volet Actions, sélectionnez **Localiser la demande**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="ccc8f-344">Le processus de créneau s’exécute.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-344">The slotting process runs.</span></span> <span data-ttu-id="ccc8f-345">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="ccc8f-346">Plan de créneaux</span><span class="sxs-lookup"><span data-stu-id="ccc8f-346">Slotting plan</span></span>

<span data-ttu-id="ccc8f-347">Le plan de créneau indique l’emplacement auquel chaque article/quantité a été affecté(e), si un débordement a été utilisé, si un travail de creux a été créé et la ligne de modèle utilisée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="ccc8f-348">*Toute demande qui n’a pas pu être insérée dans un créneau est surlignée en rouge.*</span><span class="sxs-lookup"><span data-stu-id="ccc8f-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="ccc8f-349">Dans le volet Actions, sélectionnez **Plan de créneau** pour voir les résultats.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="ccc8f-350">Les processus **Générer une demande**, **Localiser une demande**, et **Exécuter le réapprovisionnement** sont maintenant exécutés dans un bac à sable.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="ccc8f-351">(Ces processus sont disponibles dans le volet Actions sur la page **Exemples de créneaux**.)</span><span class="sxs-lookup"><span data-stu-id="ccc8f-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="ccc8f-352">Les processus **Générer une demande**, **Localiser une demande**, et **Exécuter le réapprovisionnement** ont un verrou pour s’assurer qu’ils ne peuvent pas être déclenchés en même temps.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="ccc8f-353">Sinon, les données utilisées pourraient être supprimées.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="ccc8f-354">Les processus **Générer une demande** et **Localiser une demande** affichent un avertissement si l’exécution n’a pas généré d’enregistrements ou si les enregistrements ne contiennent pas d’informations.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="ccc8f-355">Lorsque vous sélectionnez **Plan de créneaux**, la page n’a pas les boutons **Nouveau**, **Modifier** ou **Supprimer** du volet Actions, car la source de données ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="ccc8f-356">Lorsque vous sélectionnez **Exécuter le réapprovisionnement**, le système valide le modèle de créneau sélectionné et traite.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="ccc8f-357">Créer un réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-357">Create replenishment</span></span>

<span data-ttu-id="ccc8f-358">Une fois le plan de créneau créé, vous devez créer un *travail de réapprovisionnement*, sur la base du plan.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="ccc8f-359">Dans le volet Actions, sélectionnez **Exécuter le réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="ccc8f-360">Un message d’information apparaît lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="ccc8f-361">Ce message indique le nombre d’en-têtes créés pour l’ID de build de travail.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="ccc8f-362">Les directives d’emplacement qui seront utilisées sont identifiées en fonction du code de directive spécifié sur chaque ligne de modèle.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="ccc8f-363">Conseils</span><span class="sxs-lookup"><span data-stu-id="ccc8f-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="ccc8f-364">Paramétrer les créneaux automatiques</span><span class="sxs-lookup"><span data-stu-id="ccc8f-364">Set up automatic slotting</span></span>

<span data-ttu-id="ccc8f-365">Une fois que tous les éléments requis sont en place, vous pouvez configurer l’exécution automatique des créneaux en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="ccc8f-366">Allez dans **Gestion des entrepôts \> Réapprovisionnement \> Exécuter le créneau**.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="ccc8f-367">Spécifiez les étapes de création de créneaux à exécuter.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="ccc8f-368">Sélectionnez une ou plusieurs des étapes de création de créneau suivantes :</span><span class="sxs-lookup"><span data-stu-id="ccc8f-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="ccc8f-369">Générer une demande</span><span class="sxs-lookup"><span data-stu-id="ccc8f-369">Generate demand</span></span>
    - <span data-ttu-id="ccc8f-370">Localiser la demande</span><span class="sxs-lookup"><span data-stu-id="ccc8f-370">Locate demand</span></span>
    - <span data-ttu-id="ccc8f-371">Créer un travail de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="ccc8f-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccc8f-372">Les étapes de création de créneau sont progressives.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-372">The slotting steps are progressive.</span></span> <span data-ttu-id="ccc8f-373">Si vous souhaitez sélectionner *Localiser la demande*, vous devez d’abord sélectionner *Générer une demande*.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="ccc8f-374">Spécifiez le modèle de créneau à utiliser.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="ccc8f-375">Définissez la récurrence d’exécution automatique, si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="ccc8f-376">Pour les exercices du scénario, **ne paramétrez pas** la création de créneau automatique.</span><span class="sxs-lookup"><span data-stu-id="ccc8f-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]