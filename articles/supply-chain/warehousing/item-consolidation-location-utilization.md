---
title: Consolidation des articles - Utilisation de l'emplacement
description: Cette rubrique fournit des informations sur les fonctionnalités qui permettent aux responsables d'entrepôt d'afficher et de filtrer facilement l'utilisation volumétrique des emplacements dans l'entrepôt. Les responsables peuvent sélectionner des emplacements et créer un travail de mouvement des stocks directement à partir de la page Consolidation des articles afin de regrouper des articles et ainsi mieux utiliser l'espace de l'entrepôt.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017182"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="35c86-104">Consolidation des articles - Utilisation de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35c86-105">Cette rubrique fournit des informations sur les fonctionnalités qui permettent aux responsables d'entrepôt d'afficher et de filtrer facilement l'utilisation volumétrique des emplacements dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="35c86-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="35c86-106">Les responsables peuvent sélectionner des emplacements et créer un travail de mouvement des stocks directement à partir de la page **Consolidation des articles** afin de regrouper des articles et ainsi mieux utiliser l'espace de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="35c86-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="35c86-107">Activer les fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="35c86-107">Turn on the features</span></span>

<span data-ttu-id="35c86-108">Avant de pouvoir utiliser les fonctionnalités décrites dans cette rubrique, vous devez les activer dans votre système.</span><span class="sxs-lookup"><span data-stu-id="35c86-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="35c86-109">Les administrateurs peuvent utiliser l'espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de ces fonctionnalités et les activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="35c86-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="35c86-110">Activez les deux fonctionnalités, dans l'ordre dans lequel elles sont mentionnées.</span><span class="sxs-lookup"><span data-stu-id="35c86-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="35c86-111">(Les deux fonctionnalités sont destinées au module **Gestion des entrepôts**.)</span><span class="sxs-lookup"><span data-stu-id="35c86-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="35c86-112">Statut de l'emplacement de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="35c86-112">Warehouse location status</span></span>
2. <span data-ttu-id="35c86-113">Utilisation de l'emplacement de consolidation des articles</span><span class="sxs-lookup"><span data-stu-id="35c86-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="35c86-114">Statut de l'emplacement de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="35c86-114">Warehouse location status</span></span>

<span data-ttu-id="35c86-115">La fonctionnalité *Statut de l'emplacement de l'entrepôt* ajoute quatre nouveaux champs à la page **Emplacements** pour suivre des informations supplémentaires sur l'état actuel de l'emplacement :</span><span class="sxs-lookup"><span data-stu-id="35c86-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="35c86-116">**Numéro d’article** - Article qui se trouve actuellement à l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="35c86-117">Si l’emplacement contient plusieurs articles, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="35c86-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="35c86-118">**Date et heure de la dernière activité** - Horodatage de la dernière transaction d’entrepôt effectuée à l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="35c86-119">**Date âgée** - Date à laquelle le stock de l’emplacement a été introduit dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="35c86-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="35c86-120">Cette date est calculée en fonction de la date de vieillissement du contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="35c86-121">Bien que cette date soit précise pour les emplacements suivis par contenant, elle peut ne pas être précise pour les emplacements qui ne font pas l’objet d’un suivi par contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="35c86-122">**Statut de l’emplacement** - Statut de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="35c86-123">Les quatre valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-123">Four values are available:</span></span>

    - <span data-ttu-id="35c86-124">**Indéterminé** - Le profil d’emplacement ne peut pas effectuer le suivi du statut.</span><span class="sxs-lookup"><span data-stu-id="35c86-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="35c86-125">Par conséquent, le statut actuel est inconnu.</span><span class="sxs-lookup"><span data-stu-id="35c86-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="35c86-126">**Vide** - Il n’y a actuellement aucun stock à l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="35c86-127">**Prélèvement** - Des transactions sortantes ont été effectuées à l’emplacement après qu’il a été vide pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="35c86-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="35c86-128">**Stockage** - Seules des transactions sortantes ont été effectuées à l’emplacement depuis qu'il a été vide pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="35c86-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="35c86-129">Ces champs permettent aux responsables d’entrepôt d’avoir une meilleure vue d'ensemble du statut des emplacements de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="35c86-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="35c86-130">Ils permettent également de générer des rapports et un filtrage plus avancés.</span><span class="sxs-lookup"><span data-stu-id="35c86-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="35c86-131">Paramétrage de la consolidation des articles et de l'utilisation de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="35c86-132">Cette section décrit comment préparer votre système à utiliser la consolidation des articles et l'utilisation de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="35c86-133">Les procédures utilisent des exemples de valeurs provenant des données de démonstration standard.</span><span class="sxs-lookup"><span data-stu-id="35c86-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="35c86-134">Si vous envisagez de suivre l'exemple de scénario fourni plus loin dans cette rubrique, sélectionnez l'entité juridique **USMF** (qui contient les données de démonstration standard) et créez chaque enregistrement décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="35c86-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="35c86-135">Si vous ne prévoyez pas de suivre l'exemple de scénario, les valeurs fournies ici peuvent être considérées comme des exemples des types de paramètres à employer pour utiliser les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="35c86-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="35c86-136">Produit lancé</span><span class="sxs-lookup"><span data-stu-id="35c86-136">Released product</span></span>

1. <span data-ttu-id="35c86-137">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="35c86-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="35c86-138">Dans le champ **Numéro d'article** , sélectionnez *M9201* et ouvrez la page des détails.</span><span class="sxs-lookup"><span data-stu-id="35c86-138">In the **Item number** field, select *M9201* , and open the details page.</span></span>
1. <span data-ttu-id="35c86-139">Dans le volet Action,s dans l'onglet **Gérer le stock** , dans le groupe **Entrepôt** , sélectionnez **Dimensions physiques**.</span><span class="sxs-lookup"><span data-stu-id="35c86-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="35c86-140">Sur la page **Dimension physique** , dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="35c86-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="35c86-141">Une nouvelle ligne est ajoutée à la grille.</span><span class="sxs-lookup"><span data-stu-id="35c86-141">A new line is added to the grid.</span></span> <span data-ttu-id="35c86-142">Le champ **Numéro d'article** est prédéfini.</span><span class="sxs-lookup"><span data-stu-id="35c86-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="35c86-143">Dans le champ **Unité** , sélectionnez *Unités*.</span><span class="sxs-lookup"><span data-stu-id="35c86-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="35c86-144">Les champs restants de la ligne sont automatiquement définis.</span><span class="sxs-lookup"><span data-stu-id="35c86-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="35c86-145">Cliquez sur **Enregistrer** , puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="35c86-145">Select **Save** , and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="35c86-146">Profil d'emplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-146">Location profile</span></span>

1. <span data-ttu-id="35c86-147">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="35c86-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="35c86-148">Dans la liste des profils d'emplacement, sélectionnez **FLOOR-05**.</span><span class="sxs-lookup"><span data-stu-id="35c86-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="35c86-149">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="35c86-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="35c86-150">Dans l'organisateur **Général** , assurez-vous que les deux options suivantes sont définies sur *Oui*  :</span><span class="sxs-lookup"><span data-stu-id="35c86-150">On the **General** FastTab, make sure that both the following options are set to *Yes* :</span></span>

    - <span data-ttu-id="35c86-151">Activer l'article à l'emplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-151">Enable item in location</span></span>
    - <span data-ttu-id="35c86-152">Activer le statut de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-152">Enable location status</span></span>

1. <span data-ttu-id="35c86-153">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="35c86-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35c86-154">Si les options **Activer l’article à l’emplacement** et **Activer le statut de l’emplacement** étaient déjà définies sur *Oui* , passez directement aux instructions de configuration de l'organisateur **Dimensions** à l'étape 10.</span><span class="sxs-lookup"><span data-stu-id="35c86-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes* , skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="35c86-155">Si les options n'étaient pas déjà définies sur *Oui* , vous devez exécuter une vérification de cohérence pour le module **Gestion des entrepôts** après les avoir définies manuellement.</span><span class="sxs-lookup"><span data-stu-id="35c86-155">If the options weren't already set to *Yes* , you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="35c86-156">Dans ce cas, passez à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="35c86-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="35c86-157">Pour exécuter le contrôle de cohérence, accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence**.</span><span class="sxs-lookup"><span data-stu-id="35c86-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="35c86-158">Dans la boîte de dialogue **Contrôle de cohérence** , définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="35c86-159">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="35c86-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="35c86-160">**Vérifier/réparer :** *Vérifier*</span><span class="sxs-lookup"><span data-stu-id="35c86-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="35c86-161">**Date de début :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="35c86-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="35c86-162">**Vérification de la cohérence du statut des emplacements de l'entrepôt :** Cochez cette case.</span><span class="sxs-lookup"><span data-stu-id="35c86-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="35c86-163">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="35c86-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="35c86-164">Vous recevez une notification lorsque le contrôle de cohérence est terminé.</span><span class="sxs-lookup"><span data-stu-id="35c86-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="35c86-165">Ouvrez le [Centre d'action](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) pour afficher le message.</span><span class="sxs-lookup"><span data-stu-id="35c86-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="35c86-166">Sélectionnez **Détails du message** pour afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="35c86-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="35c86-167">Si le message pour le contrôle de cohérence indique «Informations de statut d'emplacement incorrectes trouvées pour l'emplacement XXXX dans l'entrepôt XX », vous devez réexécuter le contrôle de cohérence.</span><span class="sxs-lookup"><span data-stu-id="35c86-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="35c86-168">Cette fois, définissez le champ **Vérifier/réparer** sur *Corriger les erreurs*.</span><span class="sxs-lookup"><span data-stu-id="35c86-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="35c86-169">Affichez les messages pour vous assurer qu'aucune erreur n'a été trouvée.</span><span class="sxs-lookup"><span data-stu-id="35c86-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="35c86-170">Vous devez maintenant terminer la configuration du profil d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="35c86-171">Revenez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement** , sélectionnez le profil d'emplacement **FLOOR-05** puis, dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="35c86-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles** , select location profile **FLOOR-05** , and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="35c86-172">Dans l'organisateur **Dimensions** , définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="35c86-173">**Pourcentage d'utilisation du volume :** *100*</span><span class="sxs-lookup"><span data-stu-id="35c86-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="35c86-174">**Méthode volumétrique utilisée pour l'emplacement du stock :** *Utiliser le volume de l'emplacement*</span><span class="sxs-lookup"><span data-stu-id="35c86-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="35c86-175">**Hauteur réelle de l'emplacement :** *10*</span><span class="sxs-lookup"><span data-stu-id="35c86-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="35c86-176">**Largeur réelle de l'emplacement :** *10*</span><span class="sxs-lookup"><span data-stu-id="35c86-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="35c86-177">**Profondeur réelle de l'emplacement :** *10*</span><span class="sxs-lookup"><span data-stu-id="35c86-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="35c86-178">**Poids maximal :** *100*</span><span class="sxs-lookup"><span data-stu-id="35c86-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="35c86-179">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="35c86-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="35c86-180">Options de menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="35c86-180">Mobile device menu items</span></span>

1. <span data-ttu-id="35c86-181">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="35c86-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="35c86-182">Dans le volet Actions, sélectionnez **Nouveau** pour créer un élément de menu pour le tri.</span><span class="sxs-lookup"><span data-stu-id="35c86-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="35c86-183">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="35c86-184">**Nom de l'élément de menu :** *Ajuster à l'intérieur*</span><span class="sxs-lookup"><span data-stu-id="35c86-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="35c86-185">**Titre :** *Ajuster à l'intérieur*</span><span class="sxs-lookup"><span data-stu-id="35c86-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="35c86-186">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="35c86-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="35c86-187">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="35c86-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="35c86-188">Dans l'organisateur **Général** , définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="35c86-189">**Processus de création de travail :** *Ajustement à l'intérieur*</span><span class="sxs-lookup"><span data-stu-id="35c86-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="35c86-190">**Types d'ajustements de stock :** *Ajuster à l'intérieur*</span><span class="sxs-lookup"><span data-stu-id="35c86-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="35c86-191">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="35c86-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="35c86-192">Menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="35c86-192">Mobile device menu</span></span>

1. <span data-ttu-id="35c86-193">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="35c86-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="35c86-194">Dans la liste des menus, sélectionnez **Stock**.</span><span class="sxs-lookup"><span data-stu-id="35c86-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="35c86-195">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="35c86-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="35c86-196">Dans la liste **Menus et éléments de menus disponibles** , recherchez et sélectionnez l'élément de menu **Ajuster à l'intérieur**.</span><span class="sxs-lookup"><span data-stu-id="35c86-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="35c86-197">Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Ajuster à l'intérieur** vers la liste **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="35c86-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="35c86-198">De cette façon, vous ajoutez le nouvel élément de menu au menu sélectionné.</span><span class="sxs-lookup"><span data-stu-id="35c86-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="35c86-199">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="35c86-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="35c86-200">Types de mouvements</span><span class="sxs-lookup"><span data-stu-id="35c86-200">Movement types</span></span>

1. <span data-ttu-id="35c86-201">Accédez à **Gestion des entrepôts \> Paramétrage \> Stock \> Types de mouvements**.</span><span class="sxs-lookup"><span data-stu-id="35c86-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="35c86-202">Dans le volet Actions, sélectionnez **Nouveau** , puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-202">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="35c86-203">**Code de type de mouvement :** *CONSOLIDER*</span><span class="sxs-lookup"><span data-stu-id="35c86-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="35c86-204">**Description :** *Regrouper les emplacements*</span><span class="sxs-lookup"><span data-stu-id="35c86-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="35c86-205">**ID classe de travail :** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="35c86-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="35c86-206">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="35c86-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="35c86-207">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="35c86-207">Example scenario</span></span>

<span data-ttu-id="35c86-208">Le scénario suivant utilise l'application d'entreposage sur un appareil mobile pour faire un *ajustement intérieur* le stock à deux emplacements dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="35c86-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="35c86-209">Ajouter du stock dans des emplacements</span><span class="sxs-lookup"><span data-stu-id="35c86-209">Add inventory to locations</span></span>

1. <span data-ttu-id="35c86-210">Connectez-vous à l'appareil mobile en tant qu'utilisateur activé pour l'entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="35c86-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="35c86-211">Accédez à **Stock \> Ajuster à l'intérieur**.</span><span class="sxs-lookup"><span data-stu-id="35c86-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="35c86-212">Vous allez maintenant entrer le premier ajustement d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="35c86-213">Dans la tâche **Ajustement à l'intérieur** , sélectionnez l'emplacement pour lequel effectuer l'ajustement de stock.</span><span class="sxs-lookup"><span data-stu-id="35c86-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="35c86-214">Dans le champ **LOC** , sélectionnez *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="35c86-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="35c86-215">Confirmez l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-215">Confirm the location.</span></span>
1. <span data-ttu-id="35c86-216">Créez un ID de contenant pour l'article qui sera ajouté à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="35c86-217">Dans le champ **LP** , entrez *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="35c86-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="35c86-218">Confirmez le contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="35c86-219">Entrez l'article qui sera ajouté au contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="35c86-220">Dans le champ **ITEM** , entrez *M9201*.</span><span class="sxs-lookup"><span data-stu-id="35c86-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="35c86-221">Confirmez l'article.</span><span class="sxs-lookup"><span data-stu-id="35c86-221">Confirm the item.</span></span>
1. <span data-ttu-id="35c86-222">Entrez la quantité de l'article qui sera ajoutée.</span><span class="sxs-lookup"><span data-stu-id="35c86-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="35c86-223">Dans le champ **QTÉ** , entrez *10*.</span><span class="sxs-lookup"><span data-stu-id="35c86-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="35c86-224">Confirmez la quantité.</span><span class="sxs-lookup"><span data-stu-id="35c86-224">Confirm the quantity.</span></span>

    <span data-ttu-id="35c86-225">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="35c86-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="35c86-226">Vous allez maintenant entrer le deuxième ajustement d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="35c86-227">Dans la tâche **Ajustement à l'intérieur** , sélectionnez l'emplacement pour lequel effectuer l'ajustement de stock.</span><span class="sxs-lookup"><span data-stu-id="35c86-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="35c86-228">Dans le champ **LOC** , sélectionnez *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="35c86-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="35c86-229">Confirmez l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-229">Confirm the location.</span></span>
1. <span data-ttu-id="35c86-230">Créez un ID de contenant pour l'article qui sera ajouté à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="35c86-231">Dans le champ **LP** , entrez *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="35c86-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="35c86-232">Confirmez le contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="35c86-233">Entrez l'article qui sera ajouté au contenant.</span><span class="sxs-lookup"><span data-stu-id="35c86-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="35c86-234">Dans le champ **ITEM** , entrez *M9201*.</span><span class="sxs-lookup"><span data-stu-id="35c86-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="35c86-235">Confirmez l'article.</span><span class="sxs-lookup"><span data-stu-id="35c86-235">Confirm the item.</span></span>
1. <span data-ttu-id="35c86-236">Entrez la quantité de l'article qui sera ajoutée.</span><span class="sxs-lookup"><span data-stu-id="35c86-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="35c86-237">Dans le champ **QTÉ** , entrez *15*.</span><span class="sxs-lookup"><span data-stu-id="35c86-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="35c86-238">Confirmez la quantité.</span><span class="sxs-lookup"><span data-stu-id="35c86-238">Confirm the quantity.</span></span>

    <span data-ttu-id="35c86-239">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="35c86-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="35c86-240">Sélectionnez le bouton Menu (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Annuler** pour quitter la tâche **Ajustement à l'intérieur**.</span><span class="sxs-lookup"><span data-stu-id="35c86-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="35c86-241">Regrouper les emplacements</span><span class="sxs-lookup"><span data-stu-id="35c86-241">Consolidate locations</span></span>

1. <span data-ttu-id="35c86-242">Accédez à **Gestion des entrepôts \> Tâches périodiques \> Consolidation des articles**.</span><span class="sxs-lookup"><span data-stu-id="35c86-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="35c86-243">Dans l'en-tête, sélectionnez un entrepôt pour lequel effectuer la consolidation.</span><span class="sxs-lookup"><span data-stu-id="35c86-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="35c86-244">Dans le champ **Entrepôt** , entrez *51*.</span><span class="sxs-lookup"><span data-stu-id="35c86-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="35c86-245">Un enregistrement est affiché pour chaque emplacement où l'article *M9201* a été ajusté.</span><span class="sxs-lookup"><span data-stu-id="35c86-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="35c86-246">La colonne **Pourcentage d'utilisation** montre l'utilisation volumétrique de chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="35c86-247">Pour consolider le stock, sélectionnez tous les emplacements qui doivent être regroupés puis, dans le volet Actions, sélectionnez **Regrouper le stock**.</span><span class="sxs-lookup"><span data-stu-id="35c86-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="35c86-248">Dans la boîte de dialogue **Regrouper le stock** , spécifiez l'emplacement et le type de mouvement à utiliser pour créer le travail pour le mouvement de stock.</span><span class="sxs-lookup"><span data-stu-id="35c86-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="35c86-249">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="35c86-249">Set the following values:</span></span>

    - <span data-ttu-id="35c86-250">**Emplacement :** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="35c86-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="35c86-251">**Code de type de mouvement :** *CONSOLIDER*</span><span class="sxs-lookup"><span data-stu-id="35c86-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="35c86-252">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="35c86-252">Select **OK**.</span></span>
1. <span data-ttu-id="35c86-253">Vous recevez un message d'information présentant le travail de déplacement qui a été créé.</span><span class="sxs-lookup"><span data-stu-id="35c86-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="35c86-254">Prenez note de l'ID du travail de déplacement.</span><span class="sxs-lookup"><span data-stu-id="35c86-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="35c86-255">Afficher le travail de déplacement</span><span class="sxs-lookup"><span data-stu-id="35c86-255">View movement work</span></span>

1. <span data-ttu-id="35c86-256">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="35c86-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="35c86-257">Affichez le travail qui a été créé.</span><span class="sxs-lookup"><span data-stu-id="35c86-257">View the work that was created.</span></span> <span data-ttu-id="35c86-258">Utilisez l'ID de travail de déplacement issu du regroupement de stock pour filtrer ou la grille de travail ou y faire une recherche.</span><span class="sxs-lookup"><span data-stu-id="35c86-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="35c86-259">Dans ce scénario, un emplacement existant contenant du stock a été utilisé comme emplacement de regroupement du stock.</span><span class="sxs-lookup"><span data-stu-id="35c86-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="35c86-260">Par conséquent, un seul ID de travail a été créé.</span><span class="sxs-lookup"><span data-stu-id="35c86-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="35c86-261">Le système crée un ID de travail pour chaque déplacement qui doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="35c86-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="35c86-262">Si vous spécifiez un emplacement qui contient déjà du stock, un seul ID de travail est créé.</span><span class="sxs-lookup"><span data-stu-id="35c86-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="35c86-263">Si vous spécifiez un nouvel emplacement, deux ID de travail sont créés.</span><span class="sxs-lookup"><span data-stu-id="35c86-263">If you specify a new location, two work IDs are created.</span></span>
