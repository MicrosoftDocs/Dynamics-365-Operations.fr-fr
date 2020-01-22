---
title: Regroupement des lignes de prélèvement
description: Cette rubrique fournit une vue d'ensemble du Regroupement des lignes de prélèvement.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906266"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="c0965-103">Regroupement des lignes de prélèvement</span><span class="sxs-lookup"><span data-stu-id="c0965-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0965-104">Dans le regroupement des lignes de prélèvement, plusieurs lignes de travail qui ont le même article et le même emplacement peuvent être combinées en un seul prélèvement présenté à l'utilisateur sur un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c0965-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="c0965-105">Par conséquent, les magasiniers peuvent recevoir les instructions les plus efficaces possibles, mais la séparation requise des lignes de travail dans le système est également maintenue (par exemple, pour différents conteneurs et commandes).</span><span class="sxs-lookup"><span data-stu-id="c0965-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="c0965-106">Configurer le regroupement des lignes de prélèvement</span><span class="sxs-lookup"><span data-stu-id="c0965-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="c0965-107">Créer une option de menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="c0965-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="c0965-108">Aller à **Gestion d'entrepôt \> Configurer \> Appareil mobile \> Options de menu d'appareil mobile** et créez une option de menu nommée **Prélèvement de ligne de groupe de vente - Dirigé par l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c0965-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="c0965-109">Sous **Options de menu pour l'appareil mobile**, définissez les valeur suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0965-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="c0965-110">Dans le champ **Nom de l'option de menu**, entrez **Prélèvement de vente - Ligne de groupe**.</span><span class="sxs-lookup"><span data-stu-id="c0965-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="c0965-111">Dans le champ **Titre**, entrez **Prélèvement de vente - Ligne de groupe**.</span><span class="sxs-lookup"><span data-stu-id="c0965-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="c0965-112">Dans le champ **Mode**, sélectionnez **Travail**.</span><span class="sxs-lookup"><span data-stu-id="c0965-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="c0965-113">Définissez l'option **Utiliser un travail existant** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c0965-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="c0965-114">Dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0965-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="c0965-115">Dans le champ **Dirigé par**, sélectionnez **Dirigé par l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="c0965-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="c0965-116">Définissez l'option **Générer un contenant** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c0965-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="c0965-117">Définissez l'option **Prélèvement de groupe** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c0965-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="c0965-118">Sur l'organisateur **Classes de travail**, procédez comme suit pour configurer les classes de travail valide pour cette option de menu d'appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="c0965-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="c0965-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c0965-119">Select **New**.</span></span>
    2. <span data-ttu-id="c0965-120">Dans le champ **ID de classe de travail**, sélectionnez **Ventes** ou **Prélèvement CC**, en fonction de l'entrepôt que vous utiliserez.</span><span class="sxs-lookup"><span data-stu-id="c0965-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="c0965-121">Dans le champ **Type d'ordre de travail**, sélectionnez **Commandes client**.</span><span class="sxs-lookup"><span data-stu-id="c0965-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="c0965-122">Configurer un menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="c0965-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="c0965-123">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="c0965-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="c0965-124">Ajoutez l'option de menu que vous venez de créer au menu souhaité.</span><span class="sxs-lookup"><span data-stu-id="c0965-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="c0965-125">Définir un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="c0965-125">Set up a work template</span></span>

1. <span data-ttu-id="c0965-126">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="c0965-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="c0965-127">Recherchez le modèle de travail à utiliser avec cette fonction.</span><span class="sxs-lookup"><span data-stu-id="c0965-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="c0965-128">Pour cet exemple, sélectionnez le modèle de travail Contoso **51 Prélever pour échelonner**.</span><span class="sxs-lookup"><span data-stu-id="c0965-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="c0965-129">Dans le menu, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="c0965-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="c0965-130">Sous l'onglet **Tri**, sélectionnez **Ajouter**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0965-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="c0965-131">Dans le champ **Table**, sélectionnez **Transactions de travail temporaire**.</span><span class="sxs-lookup"><span data-stu-id="c0965-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="c0965-132">Dans le champ **Table dérivée**, sélectionnez **Transactions de travail temporaire**.</span><span class="sxs-lookup"><span data-stu-id="c0965-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="c0965-133">Dans le champ **Champ**, sélectionnez **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="c0965-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="c0965-134">Dans le champ **Direction de recherche**, sélectionnez **Ascendant**.</span><span class="sxs-lookup"><span data-stu-id="c0965-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="c0965-135">Pour que la fonctionnalité de regroupement des lignes de prélèvement fonctionne, les lignes de travail doivent être triées par ID article.</span><span class="sxs-lookup"><span data-stu-id="c0965-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="c0965-136">Si les lignes qui ont les mêmes articles ne sont pas séquencées les unes après les autres, elles ne seront pas groupées.</span><span class="sxs-lookup"><span data-stu-id="c0965-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="c0965-137">Exemple</span><span class="sxs-lookup"><span data-stu-id="c0965-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="c0965-138">Création de tâches de prélèvement</span><span class="sxs-lookup"><span data-stu-id="c0965-138">Create picking work</span></span>

<span data-ttu-id="c0965-139">Avant de pouvoir configurer le regroupement des lignes de prélèvement, vous devez créer des travaux sortants éligibles.</span><span class="sxs-lookup"><span data-stu-id="c0965-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="c0965-140">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="c0965-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="c0965-141">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="c0965-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="c0965-142">Sélectionnez un client dans le champ **Compte client**.</span><span class="sxs-lookup"><span data-stu-id="c0965-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="c0965-143">Dans l'organisateur **Général**, dans le champ **Entrepôt**, sélectionnez **51**.</span><span class="sxs-lookup"><span data-stu-id="c0965-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="c0965-144">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0965-144">Then select **OK**.</span></span>
5. <span data-ttu-id="c0965-145">En dessous de **Lignes de commande client**, ajoutez les six lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0965-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="c0965-146">**Ligne 1 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**.</span><span class="sxs-lookup"><span data-stu-id="c0965-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="c0965-147">Dans le champ **Quantité**, entrez **3**.</span><span class="sxs-lookup"><span data-stu-id="c0965-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="c0965-148">**Ligne 2 :** Dans le champ **Numéro d'article**, sélectionnez **M9201**.</span><span class="sxs-lookup"><span data-stu-id="c0965-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="c0965-149">Dans le champ **Quantité**, entrez **3**.</span><span class="sxs-lookup"><span data-stu-id="c0965-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="c0965-150">**Ligne 3 :** Dans le champ **Numéro d'article**, sélectionnez **M9202**.</span><span class="sxs-lookup"><span data-stu-id="c0965-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="c0965-151">Dans le champ **Quantité**, entrez **2**.</span><span class="sxs-lookup"><span data-stu-id="c0965-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="c0965-152">**Ligne 4 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**.</span><span class="sxs-lookup"><span data-stu-id="c0965-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="c0965-153">Dans le champ **Quantité**, entrez **1**.</span><span class="sxs-lookup"><span data-stu-id="c0965-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="c0965-154">**Ligne 5 :** Dans le champ **Numéro d'article**, sélectionnez **M9200**.</span><span class="sxs-lookup"><span data-stu-id="c0965-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="c0965-155">Dans le champ **Quantité**, entrez **3**.</span><span class="sxs-lookup"><span data-stu-id="c0965-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="c0965-156">**Ligne 6 :** Dans le champ **Numéro d'article**, sélectionnez **M9202**.</span><span class="sxs-lookup"><span data-stu-id="c0965-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="c0965-157">Dans le champ **Quantité**, entrez **7**.</span><span class="sxs-lookup"><span data-stu-id="c0965-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="c0965-158">Voici un résumé des quantités totales pour chaque article :</span><span class="sxs-lookup"><span data-stu-id="c0965-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="c0965-159">**Article M9200 :** 7 chacun</span><span class="sxs-lookup"><span data-stu-id="c0965-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="c0965-160">**Article M9201 :** 3 chacun</span><span class="sxs-lookup"><span data-stu-id="c0965-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="c0965-161">**Article M9202 :** 9 chacun</span><span class="sxs-lookup"><span data-stu-id="c0965-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="c0965-162">Avant de lancer les commandes à l'entrepôt, vous devez vous assurer que les emplacements de prélèvement disposent d'un stock suffisant pour tous les articles de toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="c0965-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="c0965-163">Revoir le paramètre **Instruction d'emplacement** pour déterminer les emplacements de prélèvement utilisés pour le prélèvement des commandes client.</span><span class="sxs-lookup"><span data-stu-id="c0965-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="c0965-164">Réservez l'inventaire et remettez-le à l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="c0965-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="c0965-165">Un ID travail comportant six lignes est créé.</span><span class="sxs-lookup"><span data-stu-id="c0965-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="c0965-166">Les lignes sont triées par numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="c0965-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="c0965-167">Exécuter le flux de l'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="c0965-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="c0965-168">Sur l'appareil mobile, sélectionnez le menu qui inclut la nouvelle option de menu appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c0965-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="c0965-169">Sélectionnez l'option de menu **Prélèvement de vente - Ligne de groupe** et lancez le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c0965-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="c0965-170">Après avoir sélectionné le menu et saisi l'ID travail, vous voyez l'étape de prélèvement où toutes les lignes de prélèvement pour l'article M9200 sont regroupées.</span><span class="sxs-lookup"><span data-stu-id="c0965-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="c0965-171">Vous recevez une instruction pour choisir 7 de chaque article M9200.</span><span class="sxs-lookup"><span data-stu-id="c0965-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="c0965-172">Confirmez l'étape de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c0965-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="c0965-173">Accédez à l'écran client du travail en cours et notez que les trois lignes de prélèvement pour l'article M9200 ont été clôturées simultanément.</span><span class="sxs-lookup"><span data-stu-id="c0965-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="c0965-174">La ligne de travail 4 est présentée.</span><span class="sxs-lookup"><span data-stu-id="c0965-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="c0965-175">Confirmez l'étape de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c0965-175">Confirm the pick step.</span></span>

    <span data-ttu-id="c0965-176">La dernière étape de prélèvement sur l'appareil mobile regroupe les deux dernières lignes de prélèvement de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="c0965-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="c0965-177">Terminez l'étape de prélèvement pour 9 de chaque article M9202.</span><span class="sxs-lookup"><span data-stu-id="c0965-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="c0965-178">Confirmez l'étape de placement et toute autre paire prélèvement/placement pour terminer le travail.</span><span class="sxs-lookup"><span data-stu-id="c0965-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="c0965-179">Les lignes de travail ne peuvent être regroupées que si elles sont en séquence.</span><span class="sxs-lookup"><span data-stu-id="c0965-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="c0965-180">La fonctionnalité suivante n'est pas prise en charge :</span><span class="sxs-lookup"><span data-stu-id="c0965-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="c0965-181">Articles en poids variable.</span><span class="sxs-lookup"><span data-stu-id="c0965-181">Catch-weight items.</span></span> <span data-ttu-id="c0965-182">S'il y a des articles en poids variable sur le travail, vous recevez un message d'erreur avant de commencer le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c0965-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="c0965-183">Prélèvement de pièce.</span><span class="sxs-lookup"><span data-stu-id="c0965-183">Piece picking.</span></span>
>    - <span data-ttu-id="c0965-184">Lignes de travail qui ont des travaux de réapprovisionnement inachevés.</span><span class="sxs-lookup"><span data-stu-id="c0965-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="c0965-185">Sur-prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c0965-185">Over-picking.</span></span>
