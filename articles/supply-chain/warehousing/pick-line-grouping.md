---
title: Regroupement des lignes de prélèvement
description: Cette rubrique fournit une vue d’ensemble du Regroupement des lignes de prélèvement.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ab8cdd7cad5420aca0de53e59220da9e230d411
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234631"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="df67c-103">Regroupement des lignes de prélèvement</span><span class="sxs-lookup"><span data-stu-id="df67c-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df67c-104">Le regroupement des lignes de prélèvement permet de combiner plusieurs lignes de travail qui ont le même article et le même emplacement en un seul prélèvement qui est présenté à l’utilisateur sur l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="df67c-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="df67c-105">Par conséquent, les magasiniers peuvent recevoir les instructions les plus efficaces, mais la séparation des lignes de travail requises (pour différents conteneurs, commandes, etc) peut toujours être maintenue dans le système.</span><span class="sxs-lookup"><span data-stu-id="df67c-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="df67c-106">Activer la fonctionnalité de regroupement des lignes de prélèvement</span><span class="sxs-lookup"><span data-stu-id="df67c-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="df67c-107">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="df67c-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="df67c-108">Les administrateurs peuvent utiliser l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="df67c-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="df67c-109">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="df67c-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="df67c-110">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="df67c-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="df67c-111">**Nom de la fonctionnalité :** *Regroupement des lignes de prélèvement*</span><span class="sxs-lookup"><span data-stu-id="df67c-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="df67c-112">Configurer le regroupement des lignes de prélèvement</span><span class="sxs-lookup"><span data-stu-id="df67c-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="df67c-113">Créer une option de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="df67c-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="df67c-114">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="df67c-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="df67c-115">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df67c-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="df67c-116">Dans le champ **Nom de l’élément de menu**, entrez *Prélèvement des lignes de groupe de vente*.</span><span class="sxs-lookup"><span data-stu-id="df67c-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="df67c-117">Dans le champ **Titre**, entrez *Prélèvement des lignes de groupe de vente*.</span><span class="sxs-lookup"><span data-stu-id="df67c-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="df67c-118">Ce titre sera affiché sur le menu de l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="df67c-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="df67c-119">Dans le champ **Mode**, sélectionnez *Travail*.</span><span class="sxs-lookup"><span data-stu-id="df67c-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="df67c-120">Définissez l’option **Utiliser un travail existant** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="df67c-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="df67c-121">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="df67c-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="df67c-122">Dans le champ **Dirigé par**, sélectionnez *Dirigé par l’utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="df67c-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="df67c-123">Définissez l’option **Générer un contenant** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="df67c-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="df67c-124">Définissez l’option **Prélèvement de groupe** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="df67c-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="df67c-125">Acceptez les valeurs par défaut pour les options restantes.</span><span class="sxs-lookup"><span data-stu-id="df67c-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="df67c-126">Procédez comme suit pour configurer les classes de travail valides pour l’élément de menu de l’appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="df67c-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="df67c-127">Dans le raccourci **Classes de travail**, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="df67c-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="df67c-128">Dans le champ **ID de classe de travail**, vous pouvez sélectionner *Ventes* ou *Prélèvement CC*, en fonction de l’entrepôt que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="df67c-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="df67c-129">Pour ce scénario, sélectionnez *Prélèvement CC*.</span><span class="sxs-lookup"><span data-stu-id="df67c-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="df67c-130">Le champ **Type d’ordre de travail** est automatiquement défini sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="df67c-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="df67c-131">Configurer un menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="df67c-131">Set up a mobile device menu</span></span>

<span data-ttu-id="df67c-132">Procédez comme suit pour ajouter l’élément de menu que vous venez de créer au menu **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="df67c-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="df67c-133">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="df67c-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="df67c-134">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="df67c-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="df67c-135">Le volet de liste affiche tous les menus existants de l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="df67c-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="df67c-136">Sélectionnez *Sortant* dans la liste.</span><span class="sxs-lookup"><span data-stu-id="df67c-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="df67c-137">Dans la liste **Menus et éléments de menu disponibles**, recherchez et sélectionnez l’élément de menu *Prélèvement de lignes de groupe de vente* que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="df67c-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="df67c-138">Sélectionnez le bouton Flèche droite pour déplacer l’élément de menu *Prélèvement de lignes de groupe de vente* vers la liste **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="df67c-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="df67c-139">Utilisez les boutons Flèche haut et Flèche bas pour déplacer l’élément de menu dans la position souhaitée de la structure du menu.</span><span class="sxs-lookup"><span data-stu-id="df67c-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="df67c-140">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="df67c-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="df67c-141">Définir un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="df67c-141">Set up a work template</span></span>

1. <span data-ttu-id="df67c-142">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="df67c-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="df67c-143">Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="df67c-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="df67c-144">Dans la grille **Vue d’ensemble**, recherchez et sélectionnez le modèle de travail à utiliser avec cette fonction.</span><span class="sxs-lookup"><span data-stu-id="df67c-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="df67c-145">Pour ce scénario, sélectionnez le modèle *51 Prélever pour échelonner*.</span><span class="sxs-lookup"><span data-stu-id="df67c-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="df67c-146">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="df67c-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="df67c-147">Dans la boîte de dialogue de l’éditeur de requêtes, dans l’onglet **Tri**, sélectionnez **Ajouter**, puis définissez les valeurs suivantes pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="df67c-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="df67c-148">Dans la colonne **Table**, sélectionnez *Transactions de travail temporaire*.</span><span class="sxs-lookup"><span data-stu-id="df67c-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="df67c-149">Dans la colonne **Table dérivée**, sélectionnez *Transactions de travail temporaire*.</span><span class="sxs-lookup"><span data-stu-id="df67c-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="df67c-150">Dans la colonne **Champ**, sélectionnez *Numéro d’article*.</span><span class="sxs-lookup"><span data-stu-id="df67c-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="df67c-151">Dans la colonne **Direction de recherche**, sélectionnez *Ascendant*.</span><span class="sxs-lookup"><span data-stu-id="df67c-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="df67c-152">Sélectionnez **OK** pour fermer la boîte de dialogue et enregistrer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="df67c-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="df67c-153">Le message suivant s’affiche : « Le regroupement sera réinitialisé, continuer ? »</span><span class="sxs-lookup"><span data-stu-id="df67c-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="df67c-154">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="df67c-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df67c-155">Pour que la fonctionnalité de regroupement des lignes de prélèvement fonctionne, les lignes de travail doivent être triées par ID article.</span><span class="sxs-lookup"><span data-stu-id="df67c-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="df67c-156">Si les lignes qui ont les mêmes articles ne sont pas séquencées les unes après les autres, elles ne seront pas groupées.</span><span class="sxs-lookup"><span data-stu-id="df67c-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="df67c-157">Exemple</span><span class="sxs-lookup"><span data-stu-id="df67c-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="df67c-158">Création de tâches de prélèvement</span><span class="sxs-lookup"><span data-stu-id="df67c-158">Create picking work</span></span>

<span data-ttu-id="df67c-159">Avant de pouvoir configurer le regroupement des lignes de prélèvement, vous devez créer des travaux sortants éligibles.</span><span class="sxs-lookup"><span data-stu-id="df67c-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="df67c-160">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="df67c-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="df67c-161">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="df67c-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="df67c-162">Dans le champ **Compte client**, sélectionnez *US-004*.</span><span class="sxs-lookup"><span data-stu-id="df67c-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="df67c-163">Dans l’organisateur **Général**, dans le champ **Entrepôt**, sélectionnez *51*.</span><span class="sxs-lookup"><span data-stu-id="df67c-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="df67c-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="df67c-164">Select **OK**.</span></span>
1. <span data-ttu-id="df67c-165">Dans le raccourci **Lignes de commande client**, ajoutez les six lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="df67c-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="df67c-166">**Ligne 1 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*.</span><span class="sxs-lookup"><span data-stu-id="df67c-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="df67c-167">Dans le champ **Quantité**, entrez *3*.</span><span class="sxs-lookup"><span data-stu-id="df67c-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="df67c-168">**Ligne 2 :** Dans le champ **Numéro d’article**, sélectionnez *M9201*.</span><span class="sxs-lookup"><span data-stu-id="df67c-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="df67c-169">Dans le champ **Quantité**, entrez *3*.</span><span class="sxs-lookup"><span data-stu-id="df67c-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="df67c-170">**Ligne 3 :** Dans le champ **Numéro d’article**, sélectionnez *M9202*.</span><span class="sxs-lookup"><span data-stu-id="df67c-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="df67c-171">Dans le champ **Quantité**, entrez *2*.</span><span class="sxs-lookup"><span data-stu-id="df67c-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="df67c-172">**Ligne 4 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*.</span><span class="sxs-lookup"><span data-stu-id="df67c-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="df67c-173">Dans le champ **Quantité**, entrez *1*.</span><span class="sxs-lookup"><span data-stu-id="df67c-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="df67c-174">**Ligne 5 :** Dans le champ **Numéro d’article**, sélectionnez *M9200*.</span><span class="sxs-lookup"><span data-stu-id="df67c-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="df67c-175">Dans le champ **Quantité**, entrez *3*.</span><span class="sxs-lookup"><span data-stu-id="df67c-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="df67c-176">**Ligne 6 :** Dans le champ **Numéro d’article**, sélectionnez *M9202*.</span><span class="sxs-lookup"><span data-stu-id="df67c-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="df67c-177">Dans le champ **Quantité**, entrez *7*.</span><span class="sxs-lookup"><span data-stu-id="df67c-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="df67c-178">Voici un résumé des quantités totales pour chaque article :</span><span class="sxs-lookup"><span data-stu-id="df67c-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="df67c-179">**Article M9200 :** *7* chacun</span><span class="sxs-lookup"><span data-stu-id="df67c-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="df67c-180">**Article M9201 :** *3* chacun</span><span class="sxs-lookup"><span data-stu-id="df67c-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="df67c-181">**Article M9202 :** *9* chacun</span><span class="sxs-lookup"><span data-stu-id="df67c-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="df67c-182">Avant de lancer les commandes à l’entrepôt, vous devez vous assurer que les emplacements de prélèvement disposent d’un stock suffisant pour tous les articles de toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="df67c-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="df67c-183">Revoir le paramètre **Instruction d’emplacement** pour déterminer les emplacements de prélèvement utilisés pour le prélèvement des commandes client.</span><span class="sxs-lookup"><span data-stu-id="df67c-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="df67c-184">Si vous utilisez l’environnement de données de démonstration de Contoso pour l’entrepôt *51*, confirmez que le stock est disponible.</span><span class="sxs-lookup"><span data-stu-id="df67c-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="df67c-185">Vous devez maintenant réserver le stock pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="df67c-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="df67c-186">Dans le raccourci **Lignes de commande client**, sélectionnez l’une des lignes à réserver.</span><span class="sxs-lookup"><span data-stu-id="df67c-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="df67c-187">Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="df67c-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="df67c-188">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour appliquer la réservation.</span><span class="sxs-lookup"><span data-stu-id="df67c-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="df67c-189">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="df67c-189">Then close the page.</span></span>
1. <span data-ttu-id="df67c-190">Répétez les étapes 8 à 10 pour les lignes restantes qui doivent être réservées.</span><span class="sxs-lookup"><span data-stu-id="df67c-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="df67c-191">Vous devez maintenant lancer la commande client dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="df67c-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="df67c-192">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="df67c-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="df67c-193">Vous recevez un message indiquant qu’une expédition et une vague ont été créées et que la vague a été envoyée pour exécution dans un lot.</span><span class="sxs-lookup"><span data-stu-id="df67c-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="df67c-194">Lorsque la vague et toutes les tâches en aval sont terminées, un ID de travail est créé pour le travail contenant six lignes.</span><span class="sxs-lookup"><span data-stu-id="df67c-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="df67c-195">Les lignes sont triées par numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="df67c-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="df67c-196">Accédez à **Gestion des entrepôts \> Travail \> Tout le travail** pour afficher le travail créé.</span><span class="sxs-lookup"><span data-stu-id="df67c-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="df67c-197">Prenez note de la valeur **ID de travail**, car vous en aurez besoin dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="df67c-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="df67c-198">Lancer le prélèvement à partir de l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="df67c-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="df67c-199">Connectez-vous à l’appareil mobile en tant qu’utilisateur activé pour l’entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="df67c-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="df67c-200">Sur l’appareil mobile, sélectionnez le menu qui inclut la nouvelle option de menu appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="df67c-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="df67c-201">Pour ce scénario, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="df67c-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="df67c-202">Sélectionnez l’élément de menu **Prélèvement de lignes de groupe de vente** pour lancer le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="df67c-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="df67c-203">Entrez la valeur **ID de travail** que vous avez notée dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="df67c-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="df67c-204">Vous devriez voir une étape de prélèvement où toutes les lignes de prélèvement de l’article *M9200* sont regroupées, et vous devriez recevoir une instruction pour prélever *7* de chaque article *M9200*.</span><span class="sxs-lookup"><span data-stu-id="df67c-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="df67c-205">Sur l’appareil mobile, le travail de prélèvement pour les trois lignes de travail de prélèvement a été regroupé en une seule étape de prélèvement pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df67c-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="df67c-206">Confirmez l’étape de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="df67c-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="df67c-207">Accédez à la page de travail de l’ID de travail et notez que les trois lignes de prélèvement de l’article *M9200* ont été clôturées simultanément.</span><span class="sxs-lookup"><span data-stu-id="df67c-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="df67c-208">Revenez à l’appareil mobile et continuez le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="df67c-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="df67c-209">La ligne de travail 4 de l’article *M9201* doit être présentée.</span><span class="sxs-lookup"><span data-stu-id="df67c-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="df67c-210">Comme il n’y avait qu’une seule ligne de travail sur la commande, il n’y a rien à regrouper.</span><span class="sxs-lookup"><span data-stu-id="df67c-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="df67c-211">Confirmez l’étape de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="df67c-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="df67c-212">La dernière étape de prélèvement sur l’appareil mobile regroupe les deux dernières lignes de prélèvement de l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="df67c-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="df67c-213">Terminez l’étape de prélèvement pour *9* de chaque article *M9202*.</span><span class="sxs-lookup"><span data-stu-id="df67c-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="df67c-214">Confirmez l’étape de placement et toute autre paire prélèvement/placement pour terminer le travail.</span><span class="sxs-lookup"><span data-stu-id="df67c-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="df67c-215">Les lignes de travail ne peuvent être regroupées que si elles sont en séquence.</span><span class="sxs-lookup"><span data-stu-id="df67c-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="df67c-216">La fonctionnalité suivante n’est pas prise en charge :</span><span class="sxs-lookup"><span data-stu-id="df67c-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="df67c-217">Articles en poids variable</span><span class="sxs-lookup"><span data-stu-id="df67c-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="df67c-218">S’il y a des articles en poids variable sur le travail, vous recevez un message d’erreur avant de commencer le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="df67c-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="df67c-219">Prélèvement de pièces</span><span class="sxs-lookup"><span data-stu-id="df67c-219">Piece picking</span></span>
>   - <span data-ttu-id="df67c-220">Lignes de travail qui ont un travail de réapprovisionnement inachevé</span><span class="sxs-lookup"><span data-stu-id="df67c-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="df67c-221">Prélèvement excessif</span><span class="sxs-lookup"><span data-stu-id="df67c-221">Over-picking</span></span>
>   - <span data-ttu-id="df67c-222">Prélèvement partiel avec réaffectation des articles</span><span class="sxs-lookup"><span data-stu-id="df67c-222">Short picking with item reallocation</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]