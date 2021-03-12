---
title: Clusters de rangement
description: Les cluster de rangement offrent un moyen de choisir plusieurs contenants en même temps, puis de les transférer pour les ranger à différents emplacements. Ils peuvent être très utiles pour les commerces de détail, où les contenants ne sont généralement pas des palettes complètes de stock.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 297792e90b3d2da0d738f5cbaa14779bc17ea3c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996196"
---
# <a name="putaway-clusters"></a><span data-ttu-id="fb1a7-104">Clusters de rangement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb1a7-105">Les cluster de rangement offrent un moyen de choisir plusieurs contenants en même temps, puis de les transférer pour les ranger à différents emplacements.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="fb1a7-106">Ce processus est souvent nommé *tournée du laitier*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="fb1a7-107">Les clusters de rangement peuvent être très utiles pour les commerces de détail, où les contenants ne sont généralement pas des palettes complètes de stock.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="fb1a7-108">Activer la fonctionnalité de rangement de cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="fb1a7-109">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="fb1a7-110">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fb1a7-111">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fb1a7-112">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fb1a7-113">**Nom de la fonctionnalité :** *Fonctionnalité de rangement de cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="fb1a7-114">Configurer l'exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="fb1a7-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="fb1a7-115">Profils de groupement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-115">Cluster profiles</span></span>

<span data-ttu-id="fb1a7-116">Le profil de cluster de rangement détermine où un article ira, en fonction de l'emplacement qui est attribué à l'article au moment de la réception.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="fb1a7-117">Si différents groupements sont requis, différents clusters de rangement doivent être créés pour chaque élément de menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="fb1a7-118">Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="fb1a7-119">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fb1a7-120">Dans la vue **En-tête**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-121">**ID profil de cluster de stockage :** *Rangement du cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="fb1a7-122">**Nom de l'ID profil de cluster de stockage :** *Rangement du cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="fb1a7-123">**Type de cluster :** *Rangement*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="fb1a7-124">**Souche de N° :** Acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="fb1a7-125">Sélectionnez **Enregistrer** pour rendre les champs obligatoires sur l'organisateur **Général** disponibles.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="fb1a7-126">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-127">**Calendrier d'attribution de cluster :** *À la réception*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="fb1a7-128">Ce champ définit si le cluster de stockage doit être affecté immédiatement à la réception du stock ou s'il doit être trié ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="fb1a7-129">**Règle d'attribution de cluster :** *Manuel*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="fb1a7-130">Ce champ définit si l'affectation du groupement doit être déterminé automatiquement par le système ou manuellement par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="fb1a7-131">**Code directif :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="fb1a7-132">**Localisation du cluster de stockage :** *Accusé de réception*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="fb1a7-133">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-133">The following values are available:</span></span>

        - <span data-ttu-id="fb1a7-134">**Accusé de réception** – Un emplacement est trouvé immédiatement lors de la réception.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="fb1a7-135">**Fermeture du groupement** – Un emplacement est trouvé à la fermeture du groupement.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="fb1a7-136">**Dirigé par l'utilisateur** – Un emplacement est trouvé lorsque le contenant est prélevé dans le groupe pour mise en stock.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="fb1a7-137">Dans ce cas, aucun emplacement n'est spécifié lors de la création du travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="fb1a7-138">Au cours de la mise en stock elle-même, l'utilisateur doit scanner l'ID de contenant ou de travail pour lancer l'étape de rangement.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="fb1a7-139">Le système trouve ensuite à nouveau l'emplacement de rangement et indique à l'utilisateur où ranger la quantité prélevée.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="fb1a7-140">**Cluster de rangement par utilisateur :** *Non*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="fb1a7-141">Ce champ définit si chaque cluster doit être unique par utilisateur lorsque les clusters sont automatiquement attribués.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="fb1a7-142">Il est disponible uniquement lorsque le champ **Règle d'attribution de cluster** est défini sur *Automatique*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="fb1a7-143">**Restriction d'unité :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="fb1a7-144">Ce champ définit l'unité qui doit être reçue pour que le profil soit valide.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="fb1a7-145">Si ce champ est vide, toutes les unités sont valides.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="fb1a7-146">**Répartition de l'unité de travail :** *Individuel*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="fb1a7-147">Ce champ définit si tout le stock doit être consolidé (en utilisant l'ID de cluster et de contenant) sur un contenant lorsqu'un cluster est fermé, et s'il doit être rangé comme un seul contenant ou séparément sur les contenants qui ont été reçus.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="fb1a7-148">Ce champ n'est pas disponible lorsque le champ **Localisation du cluster de stockage** est défini sur *Accusé de réception*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="fb1a7-149">**Le cluster persiste en tant que contenant parent :** *Non*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="fb1a7-150">Si cette option est définie sur *Oui*, une fois l'étape de mise en place terminée, l'ID du cluster deviendra un contenant parent, et tous les éléments de l'ID du cluster seront liés à ce contenant parent.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="fb1a7-151">Sur le raccourci **Tri de cluster**, vous pouvez définir des critères de tri de rangement.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="fb1a7-152">Sélectionnez **Nouveau** sur la barre d'outil pour ajouter une deuxième ligne, puis définissez les valeurs suivantes pour elle :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="fb1a7-153">**Souche de N° :** Acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="fb1a7-154">**Nom du champ :** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="fb1a7-155">Ce champ définit le champ que cette ligne doit utiliser comme critère de tri.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="fb1a7-156">**Tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="fb1a7-157">Ce champ définit si le tri doit être effectué par ordre croissant ou décroissant.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="fb1a7-158">Dans l'organisateur **Modèle de travail en cluster**, sélectionnez **Nouveau** sur la barre d'outil pour ajouter une ligne, puis définissez les valeurs suivantes pour celle-ci :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="fb1a7-159">**Type d’ordre de travail :** *Commandes fournisseur*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="fb1a7-160">**Modèle de travail :** *61 CF Direct*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="fb1a7-161">Sur le volet Actions, sélectionnez **Enregistrer**, puis cliquez sur **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="fb1a7-162">Dans la boîte de dialogue **Rangement de cluster**, sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une seconde ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="fb1a7-163">Mettez ensuite à jour les lignes de requête comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="fb1a7-164">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-164">Table</span></span> | <span data-ttu-id="fb1a7-165">Table dérivée</span><span class="sxs-lookup"><span data-stu-id="fb1a7-165">Derived table</span></span> | <span data-ttu-id="fb1a7-166">Champ</span><span class="sxs-lookup"><span data-stu-id="fb1a7-166">Field</span></span> | <span data-ttu-id="fb1a7-167">Critères</span><span class="sxs-lookup"><span data-stu-id="fb1a7-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="fb1a7-168">Travail</span><span class="sxs-lookup"><span data-stu-id="fb1a7-168">Work</span></span> | <span data-ttu-id="fb1a7-169">Travail</span><span class="sxs-lookup"><span data-stu-id="fb1a7-169">Work</span></span> | <span data-ttu-id="fb1a7-170">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="fb1a7-170">Warehouse</span></span> | <span data-ttu-id="fb1a7-171">*61*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-171">*61*</span></span> |
    | <span data-ttu-id="fb1a7-172">Travail</span><span class="sxs-lookup"><span data-stu-id="fb1a7-172">Work</span></span> | <span data-ttu-id="fb1a7-173">Travail</span><span class="sxs-lookup"><span data-stu-id="fb1a7-173">Work</span></span> | <span data-ttu-id="fb1a7-174">ID travail</span><span class="sxs-lookup"><span data-stu-id="fb1a7-174">Work ID</span></span> | <span data-ttu-id="fb1a7-175">Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="fb1a7-176">Sélectionnez **OK** pour enregistrer la requête et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="fb1a7-177">Sur le volet Action, sélectionnez **Enregistrer** et fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb1a7-178">Les champs du profil de cluster qui apparaissent estompés lorsque **Générer un ID de cluster** est défini sur *Oui* ne sont pas disponibles et ne seront pas pris en compte lorsque cette fonctionnalité est utilisée.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="fb1a7-179">Options de menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fb1a7-179">Mobile device menu items</span></span>

<span data-ttu-id="fb1a7-180">Deux nouveaux éléments de menu de l'appareil mobile sont disponibles pour cette fonction.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="fb1a7-181">L'élément de menu **Recevoir et trier le cluster** est utilisé pour trier le stock reçu dans un groupe de stockage à la réception.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="fb1a7-182">L'élément de menu **Rangement du cluster** est utilisé pour ranger le cluster après son affectation.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="fb1a7-183">Recevoir et trier le cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-183">Receive and sort cluster</span></span>

<span data-ttu-id="fb1a7-184">Créez un élément de menu d'appareil mobile pour recevoir le stock et le trier dans un cluster.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="fb1a7-185">Cet élément de menu créera du travail entrant après la réception du stock, ce qui indique que l'élément de menu de réception sera utilisé pour les clusters de stockage.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="fb1a7-186">L'élément de menu **Recevoir et trier le cluster** peut être utilisé avec les éléments de menu de réception suivants :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="fb1a7-187">Réception de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="fb1a7-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="fb1a7-188">Réception d'article de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="fb1a7-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="fb1a7-189">Réception des articles du chargement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-189">Load item receiving</span></span>

1. <span data-ttu-id="fb1a7-190">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fb1a7-191">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fb1a7-192">Dans la vue **En-tête**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-193">**Nom de l'élément de menu :** *Recevoir et trier le cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="fb1a7-194">**Titre :** *Recevoir et trier le cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="fb1a7-195">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="fb1a7-196">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="fb1a7-197">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-198">**Processus de création de travail :** *Réception de l’article de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="fb1a7-199">**Générer un contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="fb1a7-200">**Attribuer un cluster de stockage :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="fb1a7-201">L'option **Attribuer un cluster de stockage** est disponible uniquement pour l'activité *Processus de création de travail* pour recevoir.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="fb1a7-202">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="fb1a7-203">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="fb1a7-204">Rangement de groupement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-204">Cluster putaway</span></span>

<span data-ttu-id="fb1a7-205">Créez un élément de menu d'appareil mobile pour ranger le cluster une fois qu'il a été attribué.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="fb1a7-206">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fb1a7-207">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fb1a7-208">Dans la vue **En-tête**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-209">**Nom de l'option de menu :** *Rangement de groupement*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="fb1a7-210">**Titre :** *Mise en stock du cluster*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="fb1a7-211">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="fb1a7-212">**Utiliser un travail existant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="fb1a7-213">Sur l’organisateur **Général**, définissez le champ **Dirigé par** sur *Rangement de cluster*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="fb1a7-214">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="fb1a7-215">Sur le raccourci **Classes de travail**, configurez la classe de travail valide pour cet élément de menu d'appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="fb1a7-216">**ID classe de travail :** *Achat*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="fb1a7-217">**Type d’ordre de travail :** *Commandes fournisseur*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="fb1a7-218">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="fb1a7-219">Menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fb1a7-219">Mobile device menu</span></span>

<span data-ttu-id="fb1a7-220">Ajoutez les éléments de menu que vous venez de créer au menu entrant de l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="fb1a7-221">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="fb1a7-222">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fb1a7-223">Dans la liste des menus, sélectionnez **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="fb1a7-224">Dans la liste **Menus et éléments de menus disponibles**, recherchez et sélectionnez **Recevoir et trier le cluster**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="fb1a7-225">Sélectionnez le bouton Flèche droite pour déplacer l'élément de menu sélectionné vers la liste **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="fb1a7-226">Utilisez la flèche vers le haut ou la flèche vers le bas pour déplacer l'élément de menu dans la position souhaitée dans le menu.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="fb1a7-227">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fb1a7-228">Répétez les étapes 4 à 7 pour ajouter les éléments de menu restants :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="fb1a7-229">Attribuer un cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-229">Assign cluster</span></span>
    - <span data-ttu-id="fb1a7-230">Rangement de groupement</span><span class="sxs-lookup"><span data-stu-id="fb1a7-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="fb1a7-231">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="fb1a7-231">Example scenario</span></span>

<span data-ttu-id="fb1a7-232">Ce scénario simule le traitement de cluster rangé.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="fb1a7-233">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="fb1a7-233">Create a purchase order</span></span>

1. <span data-ttu-id="fb1a7-234">Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="fb1a7-235">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fb1a7-236">Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fb1a7-237">**Compte fournisseur :** *1001*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="fb1a7-238">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="fb1a7-239">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-239">Select **OK**.</span></span>

    <span data-ttu-id="fb1a7-240">La page **Toutes les commandes fournisseur** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="fb1a7-241">Sur la page **Toutes les commandes fournisseur**, sur le raccourci **Lignes de commande fournisseur**, utilisez le bouton **Ajouter une ligne** pour ajouter les lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="fb1a7-242">Ligne de commande fournisseur 1 :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="fb1a7-243">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="fb1a7-244">**Quantité :** *10*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="fb1a7-245">Ligne de commande fournisseur 2 :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="fb1a7-246">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="fb1a7-247">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="fb1a7-248">Ligne de commande fournisseur 3 :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="fb1a7-249">**Numéro d’article :** *M9215*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="fb1a7-250">**Quantité :** *30*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="fb1a7-251">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="fb1a7-252">Prenez note du numéro de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="fb1a7-253">Recevoir le stock et le ranger de l'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="fb1a7-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="fb1a7-254">Recevoir et trier le stock dans un cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="fb1a7-255">Connectez-vous à l'application d'entrepôt en tant qu'utilisateur configuré pour l'entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="fb1a7-256">Dans le menu principal, sélectionnez **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="fb1a7-257">Sur le menu **Entrant**, sélectionnez **Recevoir et trier le cluster**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="fb1a7-258">Dans le champ **Ponum**, entrez le numéro de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="fb1a7-259">Cliquez sur **OK** (bouton de coche).</span><span class="sxs-lookup"><span data-stu-id="fb1a7-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="fb1a7-260">Sélectionnez le champ **Article**, entrez le numéro d’article *A0001* et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="fb1a7-261">Sélectionnez le champ **Qté**, entrez *10* à l'aide du pavé numérique, puis sélectionnez le bouton de coche.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="fb1a7-262">Sur la page de tâches **Qté**, sélectionnez **OK** (le bouton de coche) pour confirmer la quantité que vous avez entrée.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="fb1a7-263">Sur la page de tâche **Article**, sélectionnez **OK** pour confirmer que l'article *A0001* a été entré.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="fb1a7-264">Sélectionnez le champ **ID de cluster** et entrez une valeur pour attribuer un ID au cluster que vous créez.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="fb1a7-265">L'ID que vous entrez ici sera utilisé lors de la réception des deux articles restants sur la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="fb1a7-266">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-266">Select **OK**.</span></span>

    <span data-ttu-id="fb1a7-267">La page des tâches **Ponum** apparaît et affiche un message "Travail terminé".</span><span class="sxs-lookup"><span data-stu-id="fb1a7-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="fb1a7-268">L'article *A0001* a maintenant été reçu à l'emplacement *RECV* et attribué à l'ID de cluster que vous avez entré à l'étape 10.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="fb1a7-269">Répétez les étapes 4 à 11 pour recevoir les deux articles restants de la commande fournisseur et les affecter à l'ID de cluster :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="fb1a7-270">Une quantité de *20* d'un article *A0002*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="fb1a7-271">Une quantité de *30* d'un article *M9215*</span><span class="sxs-lookup"><span data-stu-id="fb1a7-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="fb1a7-272">Fermer le cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-272">Close the cluster</span></span>

<span data-ttu-id="fb1a7-273">Avant de pouvoir ranger les éléments du cluster, le cluster doit être fermé.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="fb1a7-274">Dans Supply Chain Management, accédez à **Gestion d'entrepôt \> Travail \> Sortant \> Clusters de travail**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="fb1a7-275">Sur la page **Clusters de travail**, dans la section **Groupe de travail**, recherchez le champ **ID de cluster** pour l'ID de cluster que vous avez entré précédemment.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="fb1a7-276">Si le cluster n'est pas affiché, il est peut-être déjà fermé.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="fb1a7-277">Pour déterminer si le cluster a été fermé, cochez la case **Afficher le travail fermé** et recherchez l'ID de cluster que vous avez entré précédemment.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="fb1a7-278">Suivez ensuite l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb1a7-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="fb1a7-279">Si le cluster a été fermé, ignorez les étapes restantes de cette procédure et passez à la procédure suivante, [Ranger le cluster](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="fb1a7-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="fb1a7-280">Si le cluster n'a pas été fermé, suivez les étapes restantes de cette procédure pour fermer manuellement le cluster.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="fb1a7-281">Ensuite, passez à la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="fb1a7-282">Dans la section **Cluster de travail**, sélectionnez l'ID de cluster que vous avez entré précédemment.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="fb1a7-283">Dans le volet Actions, sélectionnez **Fermer le cluster**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="fb1a7-284">Une fois le cluster fermé, il n'est plus affiché dans la section **Groupe de travail** (sauf si **Afficher le travail fermé** est coché).</span><span class="sxs-lookup"><span data-stu-id="fb1a7-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="fb1a7-285">Ranger le cluster</span><span class="sxs-lookup"><span data-stu-id="fb1a7-285">Put the cluster away</span></span>

1. <span data-ttu-id="fb1a7-286">Connectez-vous à l'application d'entrepôt en tant qu'utilisateur configuré pour l'entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="fb1a7-287">Dans le menu principal, sélectionnez **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="fb1a7-288">Dans le menu **Entrant**, sélectionnez **Rangement du cluster**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="fb1a7-289">Sélectionnez **ID de cluster** et entrez l'ID de cluster que vous avez entré précédemment pour le cluster fermé.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="fb1a7-290">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-290">Select **OK**.</span></span>

    <span data-ttu-id="fb1a7-291">La page **Rangement du cluster : prélèvement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="fb1a7-292">Elle montre l'ID du cluster, l'emplacement de prélèvement, les articles (la valeur *Plusieurs* sera affichée) et la quantité totale dans le cluster qui doit être prélevée.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="fb1a7-293">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-293">Select **OK**.</span></span>

    <span data-ttu-id="fb1a7-294">La page **Rangement du cluster : rangement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="fb1a7-295">Les instructions **Rangement** identifient l'ID de cluster, l'emplacement de rangement, les articles, la quantité totale et les ID de contenant pour les articles qui ont été reçus sur le cluster.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="fb1a7-296">Vous disposez des options standard pour remplacer ou passer cette étape.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="fb1a7-297">![Rangement du cluster : page Rangement](media/Cluster_putaway-Put.png "Rangement du cluster : page Rangement")</span><span class="sxs-lookup"><span data-stu-id="fb1a7-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="fb1a7-298">Cliquez sur **OK** pour confirmer le rangement du cluster.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="fb1a7-299">Un message « Groupement terminé » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="fb1a7-300">Remarques et conseils</span><span class="sxs-lookup"><span data-stu-id="fb1a7-300">Notes and tips</span></span>

<span data-ttu-id="fb1a7-301">Dans les cas où l'ID de cluster devient le contenant parent d'une palette imbriquée, la position de rangement est automatiquement donnée lorsque l'ID de cluster est scanné.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="fb1a7-302">Aucun autre contenant ne doit être scanné, même si la génération de contenant est définie sur manuelle.</span><span class="sxs-lookup"><span data-stu-id="fb1a7-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>
