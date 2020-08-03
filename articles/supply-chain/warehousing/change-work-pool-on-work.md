---
title: Modifier le pool de travail sur le travail
description: Cette rubrique explique comment utiliser le bouton Modifier le pool de travail pour les éléments de travail afin de modifier le pool de travail du travail existant.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 33238b114f0939711163b19ae7af98be7c8d0744
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597538"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="3a224-103">Modifier le pool de travail sur le travail</span><span class="sxs-lookup"><span data-stu-id="3a224-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a224-104">Vous pouvez utiliser des pools de travail pour organiser le travail en groupes.</span><span class="sxs-lookup"><span data-stu-id="3a224-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="3a224-105">Par exemple, vous pouvez créer un pool de travail pour classer le travail qui se produit dans un emplacement d'entrepôt spécifique.</span><span class="sxs-lookup"><span data-stu-id="3a224-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="3a224-106">La fonction *Modifier le pool de travail sur le travail* ajoute un bouton **Changer de pool de travail** sur le volet Actions pour les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="3a224-107">Par conséquent, les directeurs d'entrepôt peuvent facilement modifier le pool de travail du travail existant.</span><span class="sxs-lookup"><span data-stu-id="3a224-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="3a224-108">Cette fonctionnalité permet aux responsables de réagir rapidement aux changements dans l'entrepôt et contribue à améliorer leur capacité à s'adapter aux situations changeantes et au besoin de transférer du travail vers un autre pool de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="3a224-109">Activer la fonctionnalité Modifier le pool de travail sur le travail</span><span class="sxs-lookup"><span data-stu-id="3a224-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="3a224-110">Avant de commencer à configurer ou à utiliser cette fonction, vous devez vous assurer qu'elle est disponible dans votre système.</span><span class="sxs-lookup"><span data-stu-id="3a224-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="3a224-111">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3a224-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="3a224-112">Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a224-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3a224-113">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="3a224-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="3a224-114">**Nom de la fonctionnalité :** *Modifier le pool de travail sur le travail*</span><span class="sxs-lookup"><span data-stu-id="3a224-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="3a224-115">Configurer la fonctionnalité Modifier le pool de travail sur le travail</span><span class="sxs-lookup"><span data-stu-id="3a224-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="3a224-116">Pour utiliser cette fonctionnalité, vous devez avoir configuré des pools de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="3a224-117">Vous pouvez également configurer vos modèles de travail pour qu'ils attribuent automatiquement un pool.</span><span class="sxs-lookup"><span data-stu-id="3a224-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="3a224-118">Si vous souhaitez exécuter l'exemple de scénario fourni plus loin dans cette rubrique, configurez votre système comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="3a224-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="3a224-119">Paramétrer des pools de travail</span><span class="sxs-lookup"><span data-stu-id="3a224-119">Set up work pools</span></span>

<span data-ttu-id="3a224-120">Les pools de travail vous permettent d'organiser les éléments de travail par type.</span><span class="sxs-lookup"><span data-stu-id="3a224-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="3a224-121">Pour utiliser la fonctionnalité *Modifier le pool de travail sur le travail*, vous devez avoir au moins deux pools de travail disponibles.</span><span class="sxs-lookup"><span data-stu-id="3a224-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="3a224-122">Pour afficher et ajouter des pools de travail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3a224-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="3a224-123">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Pools de travail**.</span><span class="sxs-lookup"><span data-stu-id="3a224-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="3a224-124">Si vous travaillez avec des données de démonstration de la société **USMF** et étudierez l'exemple de scénario fourni plus loin dans cette rubrique, ajoutez deux pools de travail ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3a224-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="3a224-125">Pool de travail 1 :</span><span class="sxs-lookup"><span data-stu-id="3a224-125">Work pool 1:</span></span>

        - <span data-ttu-id="3a224-126">**ID du pool de travail :** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="3a224-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="3a224-127">**Description :** *Boutique en ligne*</span><span class="sxs-lookup"><span data-stu-id="3a224-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="3a224-128">Pool de travail 2 :</span><span class="sxs-lookup"><span data-stu-id="3a224-128">Work pool 2:</span></span>

        - <span data-ttu-id="3a224-129">**ID du pool de travail :** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="3a224-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="3a224-130">**Description :** *Centre d'appel*</span><span class="sxs-lookup"><span data-stu-id="3a224-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="3a224-131">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a224-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="3a224-132">Définir des modèles de travail</span><span class="sxs-lookup"><span data-stu-id="3a224-132">Set up work templates</span></span>

<span data-ttu-id="3a224-133">Pour chacun de vos modèles de travail, vous pouvez définir un pool de travail par défaut, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="3a224-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="3a224-134">Pour chaque modèle pertinent, vous attribuez un pool de travail dans la colonne **ID du pool de travail**.</span><span class="sxs-lookup"><span data-stu-id="3a224-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="3a224-135">Dans ce cas, tous les éléments de travail générés à l'aide d'un modèle donné héritent automatiquement du pool de travail attribué.</span><span class="sxs-lookup"><span data-stu-id="3a224-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="3a224-136">Si vous travaillez avec les données de démonstration de la société **USMF** et étudierez l'exemple de scénario fourni plus loin dans cette rubrique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a224-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="3a224-137">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="3a224-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="3a224-138">Dans le volet Actions, sélectionnez **Modifier** pour afficher la page en mode d'édition.</span><span class="sxs-lookup"><span data-stu-id="3a224-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="3a224-139">Modifiez le modèle en définissant les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a224-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="3a224-140">**Modèle de travail :** *62 Prélever pour emballage*</span><span class="sxs-lookup"><span data-stu-id="3a224-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="3a224-141">**ID du pool de travail :** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="3a224-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="3a224-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a224-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3a224-143">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="3a224-143">Example scenario</span></span>

<span data-ttu-id="3a224-144">Ce scénario montre comment modifier le flux de traitement d'un élément de travail existant en modifiant son pool de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="3a224-145">Il utilise les données de démonstration de la société **USMF** et les paramètres suggérés précédemment dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3a224-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="3a224-146">Créer une commande client et la lancer dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="3a224-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="3a224-147">Confirmez qu'il y a suffisamment de stock disponible pour les articles *A0001* et *A0002* dans l'entrepôt *62*.</span><span class="sxs-lookup"><span data-stu-id="3a224-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="3a224-148">Accédez à **Gestion des stocks \> Recherches et états \> Liste disponible**, et modifiez les filtres comme indiqué ici :</span><span class="sxs-lookup"><span data-stu-id="3a224-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="3a224-149">La valeur **Entrepôt** commence par *62*.</span><span class="sxs-lookup"><span data-stu-id="3a224-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="3a224-150">La valeur du **Numéro d'article** est *A001* ou *A002*.</span><span class="sxs-lookup"><span data-stu-id="3a224-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="3a224-151">Les données de démonstration doivent avoir une quantité de 10 chacune.</span><span class="sxs-lookup"><span data-stu-id="3a224-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="3a224-152">Ensuite, vous devez créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="3a224-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="3a224-153">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="3a224-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3a224-154">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="3a224-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3a224-155">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a224-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3a224-156">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="3a224-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="3a224-157">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="3a224-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="3a224-158">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3a224-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="3a224-159">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="3a224-159">The new sales order is opened.</span></span> <span data-ttu-id="3a224-160">Elle doit inclure une nouvelle ligne vide dans la grille de l'organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="3a224-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="3a224-161">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a224-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="3a224-162">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3a224-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3a224-163">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="3a224-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="3a224-164">Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="3a224-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="3a224-165">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="3a224-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="3a224-166">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3a224-166">Close the page.</span></span>
1. <span data-ttu-id="3a224-167">Dans l'organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour ajouter une autre ligne à votre commande client.</span><span class="sxs-lookup"><span data-stu-id="3a224-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="3a224-168">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a224-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="3a224-169">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="3a224-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="3a224-170">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="3a224-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="3a224-171">Dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="3a224-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="3a224-172">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="3a224-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="3a224-173">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3a224-173">Close the page.</span></span>
1. <span data-ttu-id="3a224-174">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="3a224-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="3a224-175">Vous recevez des messages d’information indiquant l’ID de vague et les ID d’expédition créés à partir du lancement.</span><span class="sxs-lookup"><span data-stu-id="3a224-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="3a224-176">Prenez note de l'ID de vague.</span><span class="sxs-lookup"><span data-stu-id="3a224-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="3a224-177">Examiner la vague sortante</span><span class="sxs-lookup"><span data-stu-id="3a224-177">Review the outbound wave</span></span>

1. <span data-ttu-id="3a224-178">Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.</span><span class="sxs-lookup"><span data-stu-id="3a224-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="3a224-179">Dans la grille, cherchez l'ID de vague qui a été créé à partir du lancement de la commande client.</span><span class="sxs-lookup"><span data-stu-id="3a224-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="3a224-180">Sélectionnez l'ID de vague pour afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="3a224-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="3a224-181">Dans l'organisateur **Lignes de vague**, assurez-vous qu'un ID d'expédition est affiché pour la commande client.</span><span class="sxs-lookup"><span data-stu-id="3a224-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="3a224-182">Si l'option **Traiter la vague à la libération dans l’entrepôt** est *Non* dans la configuration du modèle de vague d'expédition, vous devez traiter manuellement la vague en sélectionnant **Traiter** dans l'onglet **Vague** du volet Actions pour créer un travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="3a224-183">Assurez-vous que la vague a été traitée.</span><span class="sxs-lookup"><span data-stu-id="3a224-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="3a224-184">Ce traitement crée le travail requis.</span><span class="sxs-lookup"><span data-stu-id="3a224-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="3a224-185">Afficher les détails du travail et modifier le pool de travail</span><span class="sxs-lookup"><span data-stu-id="3a224-185">View work details and change the work pool</span></span>

<span data-ttu-id="3a224-186">Vous pouvez utiliser la page **Détails du travail** pour afficher le travail créé et gérer le pool de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="3a224-187">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="3a224-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="3a224-188">Sélectionnez la ligne du travail qui vient d'être créé.</span><span class="sxs-lookup"><span data-stu-id="3a224-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="3a224-189">La colonne **Numéro de commande** affiche le numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="3a224-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="3a224-190">Le champ **ID du pool de travail** est défini sur l'ID du pool de travail qui a été configuré dans le modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="3a224-191">Si vous ne voyez pas le champ **ID du pool de travail**, ajoutez la colonne à la grille, puis actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="3a224-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="3a224-192">Pour modifier le pool de travail associé à l'ID de travail, dans le volet Actions, dans l'onglet **Travail**, sélectionnez **Changer de pool de travail**.</span><span class="sxs-lookup"><span data-stu-id="3a224-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="3a224-193">Dans la boîte de dialogue **Changer de pool de travail**, dans l'organisateur **Paramètres**, dans le champ **ID du pool de travail**, sélectionnez *Centre d'appel*.</span><span class="sxs-lookup"><span data-stu-id="3a224-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="3a224-194">Sélectionner **OK** pour appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="3a224-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="3a224-195">Notez que la valeur du champ **ID du pool de travail** a maintenant été changée en *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="3a224-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a224-196">Quand la boîte de dialogue **Changer de pool de travail** s'affiche, le champ **ID du pool de travail** peut être vide par défaut.</span><span class="sxs-lookup"><span data-stu-id="3a224-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="3a224-197">Si le champ est vide lorsque vous sélectionnez **OK** pour appliquer les modifications, vous supprimerez complètement le pool de travail du travail.</span><span class="sxs-lookup"><span data-stu-id="3a224-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="3a224-198">En plus de changer de pool de travail, vous pouvez utiliser cette procédure pour ajouter un pool de travail à tout élément de travail qui n'en a pas, ou pour supprimer un pool de travail de tout élément de travail qui en a.</span><span class="sxs-lookup"><span data-stu-id="3a224-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>
