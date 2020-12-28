---
title: Association de dimensions de produit dans un emplacement
description: Cette rubrique donne des informations sur l'association de dimensions de produit dans un emplacement. Cette fonctionnalité de profil d'emplacement aide à améliorer la gestion des emplacements lorsque des variantes de produit ou des produits contenant des dimensions sont utilisés, comme dans le secteur de la mode. Elle vous permet de décider si des configurations, couleurs, styles et tailles peuvent être associés pour un profil d'emplacement spécifique, ou si une seule de ces dimensions ou une combinaison d'entre elles peut être placée au même emplacement.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428211"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="a1fef-105">Association de dimensions de produit dans un emplacement</span><span class="sxs-lookup"><span data-stu-id="a1fef-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1fef-106">L'association de dimensions de produit dans un emplacement est une fonctionnalité de profil d'emplacement qui aide à améliorer la gestion des emplacements lorsque des variantes de produit ou des produits contenant des dimensions sont utilisés, comme dans le secteur de la mode.</span><span class="sxs-lookup"><span data-stu-id="a1fef-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="a1fef-107">Elle vous permet de décider si des configurations, couleurs, styles et tailles peuvent être associés pour un profil d'emplacement spécifique, ou si une seule de ces dimensions ou une combinaison d'entre elles peut être placée au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="a1fef-108">Activer la fonctionnalité Association de dimensions de produit dans un emplacement</span><span class="sxs-lookup"><span data-stu-id="a1fef-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="a1fef-109">Avant de pouvoir utiliser l'association de dimensions de produit dans un emplacement, la fonctionnalité doit être activée dans votre système.</span><span class="sxs-lookup"><span data-stu-id="a1fef-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="a1fef-110">Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a1fef-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a1fef-111">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="a1fef-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a1fef-112">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="a1fef-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a1fef-113">**Nom de la fonctionnalité :** *Association de dimensions de produit dans un emplacement*</span><span class="sxs-lookup"><span data-stu-id="a1fef-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="a1fef-114">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="a1fef-114">Setup</span></span>

<span data-ttu-id="a1fef-115">Chaque emplacement de l'entrepôt doit avoir un profil d'emplacement qui lui est associé et qui décrit les propriétés de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="a1fef-116">Par conséquent, tous les emplacements qui utilisent le même profil d'emplacement pourront autoriser l'association de dimensions de produit une fois la configuration effectuée.</span><span class="sxs-lookup"><span data-stu-id="a1fef-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="a1fef-117">Configurer les profils d'emplacement pour autoriser l'association de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="a1fef-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="a1fef-118">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="a1fef-119">Dans la liste des profils d'emplacement, sélectionnez **BULK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="a1fef-120">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a1fef-121">Dans l'organisateur **Général**, définissez l'option **Activer l'association spécifique de dimensions de produit dans un emplacement** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1fef-122">Vous pouvez définir cette option sur *Oui* uniquement si l'option **Autoriser les articles mixtes** est définie sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="a1fef-123">Dans l'organisateur **Association de dimensions de produit autorisée**, définissez l'option **Taille** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="a1fef-124">Dans le scénario décrit dans cette rubrique, l'association ne peut être effectuée que pour les produits dont les dimensions **Taille** sont différentes.</span><span class="sxs-lookup"><span data-stu-id="a1fef-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="a1fef-125">Cependant, d'autres options sont également disponibles.</span><span class="sxs-lookup"><span data-stu-id="a1fef-125">However, other options are also available.</span></span>
1. <span data-ttu-id="a1fef-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="a1fef-127">Créer un produit générique et des variantes de produit</span><span class="sxs-lookup"><span data-stu-id="a1fef-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="a1fef-128">Allez dans **Gestion des informations sur les produits \> Produits \> Produits génériques**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="a1fef-129">Dans le volet Actions, sélectionnez **Nouveau** pour créer un produit générique.</span><span class="sxs-lookup"><span data-stu-id="a1fef-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="a1fef-130">Dans la boîte de dialogue **Nouveau produit**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a1fef-131">**Type de produit :** *Article*</span><span class="sxs-lookup"><span data-stu-id="a1fef-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="a1fef-132">**Sous-type de produit :** *Produit générique*</span><span class="sxs-lookup"><span data-stu-id="a1fef-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="a1fef-133">**Numéro de produit :** *B0001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="a1fef-134">**Nom du produit :** *Taille B0001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="a1fef-135">**Groupe de dimensions de produit :** *Taille*</span><span class="sxs-lookup"><span data-stu-id="a1fef-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="a1fef-136">**Technologie de configuration :** *Variante prédéfinie*</span><span class="sxs-lookup"><span data-stu-id="a1fef-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="a1fef-137">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-137">Select **OK**.</span></span>
1. <span data-ttu-id="a1fef-138">Sur la page **Détails du produit**, dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a1fef-139">**Générer les variantes automatiquement :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="a1fef-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="a1fef-140">**Groupe de tailles :** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="a1fef-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="a1fef-141">Pour afficher les variantes prédéfinies, dans le volet Actions, sélectionnez **Variantes de produit**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="a1fef-142">La page **Variantes de produit** apparaît et affiche une liste de variantes à partir de la configuration du groupe de tailles.</span><span class="sxs-lookup"><span data-stu-id="a1fef-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="a1fef-143">Lancer des produits dans la société USMF</span><span class="sxs-lookup"><span data-stu-id="a1fef-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="a1fef-144">Dans le volet Actions, sélectionnez **Lancer des produits**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="a1fef-145">Sur la page **Sélectionner des produits à lancer**, confirmez que le numéro de produit *B0001* est présent dans la liste, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="a1fef-146">Sélectionnez **Suivant** pour confirmer les variantes de produit à lancer.</span><span class="sxs-lookup"><span data-stu-id="a1fef-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="a1fef-147">Sur la page **Sélectionner les sociétés vers lesquelles lancer**, sélectionnez *USMF*, puis sélectionnez **Suivant** pour confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="a1fef-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="a1fef-148">Sur la page **Confirmer la sélection**, sélectionnez **Terminer** pour terminer le lancement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="a1fef-149">Vous recevez un message « Opération terminée ».</span><span class="sxs-lookup"><span data-stu-id="a1fef-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="a1fef-150">Mettre à jour un produit lancé dans la société USMF</span><span class="sxs-lookup"><span data-stu-id="a1fef-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="a1fef-151">Assurez-vous d'être connecté à la société **USMF**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="a1fef-152">Allez dans **Gestion des informations sur les produits \> Produits \> Produits lancés** pour terminer la création du produit lancé.</span><span class="sxs-lookup"><span data-stu-id="a1fef-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="a1fef-153">Recherchez et sélectionnez le numéro d'article *B0001* pour ouvrir la page **Détails des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="a1fef-154">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a1fef-155">Dans l'organisateur **Général**, assurez-vous que le champ **Groupe de modèles d'article** est défini sur *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="a1fef-156">Dans le volet Actions, sous l'onglet **Produit**, dans le groupe **Paramétrer**, sélectionnez **Groupes de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="a1fef-157">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-157">Set the following values:</span></span>

    - <span data-ttu-id="a1fef-158">**Groupe de dimension de stockage :** *Entrepôt*</span><span class="sxs-lookup"><span data-stu-id="a1fef-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="a1fef-159">**Groupe de dimension de suivi :** *Aucun*</span><span class="sxs-lookup"><span data-stu-id="a1fef-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="a1fef-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-160">Select **OK**.</span></span>
1. <span data-ttu-id="a1fef-161">Dans le volet Actions, sous l'onglet **Produit**, dans le groupe **Paramétrer**, sélectionnez **Hiérarchie de réservation**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="a1fef-162">Définissez le champ **Hiérarchie de réservation** sur *Valeur par défaut*, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="a1fef-163">Dans l'organisateur **Général**, dans la section **Administration**, notez que vos sélections ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a1fef-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="a1fef-164">Dans l'organisateur **Achats**, dans le champ **Prix**, entrez *10*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="a1fef-165">Dans l'organisateur **Gérer les coûts**, dans le champ **Groupe d'articles**, entrez *Audio*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="a1fef-166">Dans l'organisateur **Achats**, dans le champ **Prix**, entrez *10*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="a1fef-167">Dans l'organisateur **Entrepôt**, dans le champ **ID groupe de séquences d'unités**, entrez *ea*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="a1fef-168">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="a1fef-169">Créer une instruction d'emplacement</span><span class="sxs-lookup"><span data-stu-id="a1fef-169">Create a location directive</span></span>

1. <span data-ttu-id="a1fef-170">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a1fef-171">Dans le volet gauche, dans le champ **Type d'ordre de travail**, sélectionnez *Commandes fournisseur*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="a1fef-172">Dans la liste, sélectionnez l'instruction d'emplacement nommée *24 PO Direct*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="a1fef-173">Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="a1fef-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a1fef-174">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a1fef-175">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="a1fef-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="a1fef-176">La nouvelle ligne doit être en face de la ligne précédemment existante.</span><span class="sxs-lookup"><span data-stu-id="a1fef-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="a1fef-177">Pour effectuer la modification, utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d'outils ou modifiez la valeur **Numéro de souche** de la ligne existante sur *2*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="a1fef-178">**Nom :** *Placer dans le profil d'emplacement BULK*</span><span class="sxs-lookup"><span data-stu-id="a1fef-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="a1fef-179">**Utilisation d'un emplacement fixe :** *Emplacements fixes et non fixes*</span><span class="sxs-lookup"><span data-stu-id="a1fef-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="a1fef-180">**Autoriser le stock négatif :** *Décochez cette case (=Non)*</span><span class="sxs-lookup"><span data-stu-id="a1fef-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="a1fef-181">**Traitement par lots activé :** *Décochez cette case (=Non)*</span><span class="sxs-lookup"><span data-stu-id="a1fef-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="a1fef-182">**Stratégie :** *Aucun*</span><span class="sxs-lookup"><span data-stu-id="a1fef-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="a1fef-183">Alors que la nouvelle ligne est toujours sélectionnée, sélectionnez **Modifier la requête** au-dessus de la grille.</span><span class="sxs-lookup"><span data-stu-id="a1fef-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="a1fef-184">Dans la boîte de dialogue de requête, sous l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="a1fef-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="a1fef-185">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a1fef-186">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="a1fef-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a1fef-187">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="a1fef-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a1fef-188">**Champ :** *Location profile ID*</span><span class="sxs-lookup"><span data-stu-id="a1fef-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="a1fef-189">**Critères :** *BULK*</span><span class="sxs-lookup"><span data-stu-id="a1fef-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="a1fef-190">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-190">Select **OK**.</span></span>
1. <span data-ttu-id="a1fef-191">Sur la page **Instructions d'emplacement**, dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a1fef-192">Dans l'organisateur **Actions d'instruction d'emplacement**, dans le champ **Stratégie**, si vous utilisez la stratégie d'emplacement *Consolider*, la configuration de l'organisateur **Association de dimensions de produit autorisée** dans **Profils d'emplacement** sera remplacée et les articles seront placés au même emplacement même si ce comportement n'est pas autorisé par la configuration.</span><span class="sxs-lookup"><span data-stu-id="a1fef-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="a1fef-193">Créer une option de menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="a1fef-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="a1fef-194">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a1fef-195">Dans le volet Actions, sélectionnez **Nouveau** pour créer un élément de menu à utiliser pour le tri.</span><span class="sxs-lookup"><span data-stu-id="a1fef-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="a1fef-196">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="a1fef-197">**Nom de l'option de menu :** *Réception de ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="a1fef-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="a1fef-198">**Titre :** *Réception de ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="a1fef-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="a1fef-199">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="a1fef-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="a1fef-200">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="a1fef-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="a1fef-201">Dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a1fef-202">**Processus de création du travail :** *Réception et rangement de la ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="a1fef-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="a1fef-203">**Générer un contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="a1fef-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="a1fef-204">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="a1fef-205">Configurer le menu sur l'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="a1fef-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="a1fef-206">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="a1fef-207">Dans la liste des menus, sélectionnez **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="a1fef-208">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a1fef-209">Dans la liste **Menus et éléments de menus disponibles**, recherchez et sélectionnez l'élément de menu **Réception de ligne de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="a1fef-210">Sélectionnez le bouton Flèche droite pour déplacer l'élément de menu **Réception de ligne de commande fournisseur** vers la liste **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="a1fef-211">De cette façon, vous ajoutez votre nouvel élément de menu au menu sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a1fef-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="a1fef-212">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="a1fef-213">Scénario</span><span class="sxs-lookup"><span data-stu-id="a1fef-213">Scenario</span></span>

<span data-ttu-id="a1fef-214">Ce scénario de démonstration montre comment deux variantes de produit différentes peuvent être placées au même emplacement lorsque le profil d'emplacement n'autorise pas les articles mixtes, mais la fonctionnalité *Association de dimensions de produit dans un emplacement* est activée.</span><span class="sxs-lookup"><span data-stu-id="a1fef-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="a1fef-215">Dans ce cas, vous utiliserez la variante **Taille** comme critère.</span><span class="sxs-lookup"><span data-stu-id="a1fef-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="a1fef-216">Avant de commencer, assurez-vous que des emplacements vides dans l'entrepôt *24* utilisent le profil d'emplacement *BULK*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="a1fef-217">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="a1fef-217">Create a purchase order</span></span>

<span data-ttu-id="a1fef-218">Vous allez créer une commande fournisseur comprenant trois lignes : deux lignes pour le même numéro de produit mais des variantes **Taille** différentes, et une troisième ligne pour un produit différent qui ne contient pas de variantes.</span><span class="sxs-lookup"><span data-stu-id="a1fef-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="a1fef-219">Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="a1fef-220">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a1fef-221">Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a1fef-222">**Compte fournisseur :** *1001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="a1fef-223">**Entrepôt :** *24*</span><span class="sxs-lookup"><span data-stu-id="a1fef-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="a1fef-224">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-224">Select **OK**.</span></span>
1. <span data-ttu-id="a1fef-225">La commande fournisseur est créée et une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="a1fef-226">Prenez note du numéro de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a1fef-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="a1fef-227">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a1fef-228">**Numéro d'article :** *B0001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="a1fef-229">**Taille** *L*</span><span class="sxs-lookup"><span data-stu-id="a1fef-229">**Size** *L*</span></span>
    - <span data-ttu-id="a1fef-230">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="a1fef-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a1fef-231">Sélectionnez **Ajouter une ligne** au-dessus de la grille pour ajouter une deuxième ligne de commande et définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="a1fef-232">**Numéro d'article :** *B0001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="a1fef-233">**Taille** *XL*</span><span class="sxs-lookup"><span data-stu-id="a1fef-233">**Size** *XL*</span></span>
    - <span data-ttu-id="a1fef-234">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="a1fef-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a1fef-235">Sélectionnez **Ajouter une ligne** pour ajouter une troisième ligne de commande fournisseur, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fef-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="a1fef-236">**Numéro d'article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a1fef-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="a1fef-237">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="a1fef-237">**Quantity:** *1*</span></span>

<span data-ttu-id="a1fef-238">1.Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a><span data-ttu-id="a1fef-239">Recevoir des lignes de commande fournisseur dans l'application d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="a1fef-239">Receive purchase order lines in the warehouse app</span></span>

1. <span data-ttu-id="a1fef-240">Connectez-vous à l'application d'entrepôt en tant qu'utilisateur activé pour l'entrepôt *24*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-240">Sign in to the warehouse app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="a1fef-241">Sélectionnez le menu **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="a1fef-242">Sélectionnez **Réception de ligne de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="a1fef-243">Sélectionnez le champ **PONUM**, puis entrez le numéro de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a1fef-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="a1fef-244">Confirmez votre entrée en sélectionnant le bouton de confirmation ( ✔ ) en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="a1fef-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="a1fef-245">Entrez le numéro de ligne à partir de la commande fournisseur reçue.</span><span class="sxs-lookup"><span data-stu-id="a1fef-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="a1fef-246">Sélectionnez le champ **LINENUM**, puis utilisez le pavé numérique pour entrer *1*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="a1fef-247">Confirmez votre entrée.</span><span class="sxs-lookup"><span data-stu-id="a1fef-247">Confirm your entry.</span></span>
1. <span data-ttu-id="a1fef-248">Entrez la quantité à recevoir.</span><span class="sxs-lookup"><span data-stu-id="a1fef-248">Enter the quantity to receive.</span></span> <span data-ttu-id="a1fef-249">Cliquez deux fois sur le bouton signe plus (**+**) pour augmenter la valeur du champ **Qté** à *2*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="a1fef-250">Enregistrez votre entrée en sélectionnant le bouton ( ✔ ) en bas de la page, puis confirmez votre entrée en sélectionnant à nouveau le bouton ( ✔ ).</span><span class="sxs-lookup"><span data-stu-id="a1fef-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="a1fef-251">Affichez les informations sur la page **Commandes fournisseur : Placer**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="a1fef-252">Cette page montre le travail qui a été créé pour le rangement (travail 1).</span><span class="sxs-lookup"><span data-stu-id="a1fef-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="a1fef-253">L'emplacement de rangement de l'article reçu, le contenant, l'article, la taille et la quantité de la tâche **Réception de ligne de commande fournisseur** que vous venez de terminer s'affichent.</span><span class="sxs-lookup"><span data-stu-id="a1fef-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="a1fef-254">Confirmez le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="a1fef-255">Répétez les étapes 4 à 11 pour la ligne de commande fournisseur 2.</span><span class="sxs-lookup"><span data-stu-id="a1fef-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="a1fef-256">Cependant, à l'étape 8, spécifiez une quantité de *1*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="a1fef-257">Un nouveau travail de rangement (travail 2) est créé pour le même emplacement que le travail 1.</span><span class="sxs-lookup"><span data-stu-id="a1fef-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="a1fef-258">Répétez à nouveau les étapes 4 à 11 pour la ligne de commande fournisseur 2.</span><span class="sxs-lookup"><span data-stu-id="a1fef-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="a1fef-259">À l'étape 8, spécifiez une quantité restante de *1*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="a1fef-260">Un nouveau travail de rangement (travail 3) est créé pour le même emplacement que le travail 1 et le travail 2.</span><span class="sxs-lookup"><span data-stu-id="a1fef-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="a1fef-261">Ce comportement se produit car la stratégie de l'instruction d'emplacement *Consolider* est utilisée, et l'organisateur **Association de dimensions de produit autorisée** dans la configuration **Profils d'emplacement** *BULK* autorise l'association de la variante **Taille** dans un emplacement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="a1fef-262">Répétez les étapes 4 à 11 pour la ligne de commande fournisseur 3.</span><span class="sxs-lookup"><span data-stu-id="a1fef-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="a1fef-263">À l'étape 8, spécifiez une quantité de *1* pour le numéro d'article *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a1fef-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="a1fef-264">Un nouveau travail de rangement (travail 4) est créé pour un emplacement différent de celui utilisé pour les lignes de commande fournisseur 1 et 2.</span><span class="sxs-lookup"><span data-stu-id="a1fef-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="a1fef-265">Ce comportement se produit car le profil d'emplacement n'autorise pas les produits mixtes, mais il autorise les dimensions mixtes du même produit générique.</span><span class="sxs-lookup"><span data-stu-id="a1fef-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="a1fef-266">Sélectionnez le bouton Menu en haut de la page (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Annuler** pour quitter **Réception de ligne de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="a1fef-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="a1fef-267">Vous pouvez répéter ce scénario, mais cette fois-ci, définissez **Taille** - *Non* dans l'organisateur **Autoriser l'association de dimensions de produit** de la configuration **Profils d'emplacement** *BULK*, afin qu'aucune des dimensions de produit ne puisse être associée.</span><span class="sxs-lookup"><span data-stu-id="a1fef-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="a1fef-268">Dans ce cas, lorsque vous recevez la commande fournisseur, chaque variante de produit est placée dans un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="a1fef-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>