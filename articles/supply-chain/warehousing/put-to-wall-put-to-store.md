---
title: Mettre au mur - Mettre en magasin
description: Cette rubrique fournit des informations sur la fonctionnalité Mettre au mur - Mettre en magasin. Cette fonctionnalité vous permet de gérer des scénarios dans lesquels vous devez regrouper un produit dans une zone de préparation à l’emballage, en fonction de critères configurables. Elle accélère le prélèvement car elle permet de sélectionner un seul contenant cible et peut utiliser plus de positions de placement que le prélèvement de groupement.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e2dcfa18af457ea21618704bafa2ed81c615d952
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228511"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="e7714-105">Mettre au mur - Mettre en magasin</span><span class="sxs-lookup"><span data-stu-id="e7714-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7714-106">Le fonctionnalité *Mettre au mur - Mettre en magasin* vous permet de gérer des scénarios dans lesquels vous devez regrouper un produit dans une zone de préparation à l’emballage, en fonction de critères configurables.</span><span class="sxs-lookup"><span data-stu-id="e7714-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="e7714-107">Étant donné que cette fonctionnalité permet de sélectionner un seul contenant cible et peut utiliser plus de positions de placement que le prélèvement de groupement, les entreprises qui expédient vers des magasins ou manipulent de petits articles bénéficieront d’un temps de prélèvement réduit.</span><span class="sxs-lookup"><span data-stu-id="e7714-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="e7714-108">Le flux de travail de cette fonctionnalité dirige le produit prélevé vers un emplacement de tri pour le répartir dans différents types de conteneurs.</span><span class="sxs-lookup"><span data-stu-id="e7714-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="e7714-109">En règle générale, chaque emplacement de tri comprend plusieurs positions de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="e7714-110">Chaque position de tri est affectée selon les critères définis par le processus métier.</span><span class="sxs-lookup"><span data-stu-id="e7714-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="e7714-111">Les critères typiques sont la destination finale, l’expédition ou le chargement.</span><span class="sxs-lookup"><span data-stu-id="e7714-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="e7714-112">Après l’arrivée d’un produit, il est distribué à chaque position de tri, en fonction de la quantité associée à la commande, à la destination, à l’expédition ou au chargement.</span><span class="sxs-lookup"><span data-stu-id="e7714-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="e7714-113">Lorsqu’un conteneur est plein ou complet, il est déplacé vers un lieu de transit ou un lieu d’expédition en vue d’une manipulation ultérieure, en fonction du processus métier.</span><span class="sxs-lookup"><span data-stu-id="e7714-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="e7714-114">Cette fonctionnalité d’entreposage est également désignée par d’autres noms, tels que « put-to-light » et « break opens ».</span><span class="sxs-lookup"><span data-stu-id="e7714-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="e7714-115">Activer la fonction de tri sortant</span><span class="sxs-lookup"><span data-stu-id="e7714-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="e7714-116">Avant de pouvoir utiliser la fonctionnalité *Mettre au mur - Mettre en magasin*, la fonctionnalité *Tri sortant* doit être activée dans votre système.</span><span class="sxs-lookup"><span data-stu-id="e7714-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="e7714-117">Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e7714-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="e7714-118">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="e7714-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="e7714-119">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="e7714-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e7714-120">**Nom de la fonction :** *Tri sortant*</span><span class="sxs-lookup"><span data-stu-id="e7714-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="e7714-121">La fonctionnalité *Tri sortant* peut être utilisée en conjonction avec la fonctionnalité *Code étape de vague à l’échelle de l’organisation* si elle est activée.</span><span class="sxs-lookup"><span data-stu-id="e7714-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="e7714-122">Vous devez également activer cette fonction si vous comptez utiliser des codes prédéfinis qui sont configurés dans des codes d’étape de vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="e7714-123">Dans l’espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="e7714-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="e7714-124">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="e7714-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e7714-125">**Nom de la fonctionnalité :** *Code étape de vague à l’échelle de l’organisation*</span><span class="sxs-lookup"><span data-stu-id="e7714-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="e7714-126">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="e7714-126">Setup</span></span>

<span data-ttu-id="e7714-127">Pour cette démonstration, nous utilisons les données standard et l’entrepôt Contoso *62*.</span><span class="sxs-lookup"><span data-stu-id="e7714-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="e7714-128">Certains ajouts mentionnés plus loin sont également utilisés.</span><span class="sxs-lookup"><span data-stu-id="e7714-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="e7714-129">Type d’emplacement</span><span class="sxs-lookup"><span data-stu-id="e7714-129">Location type</span></span>

1. <span data-ttu-id="e7714-130">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Types d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="e7714-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="e7714-131">Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’emplacement pour le tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="e7714-132">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-132">Set the following values:</span></span>

    - <span data-ttu-id="e7714-133">**Type d’emplacement :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="e7714-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="e7714-134">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="e7714-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="e7714-136">Paramètres de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="e7714-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="e7714-137">Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="e7714-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="e7714-138">Dans l’onglet **Général**, dans l’organisateur **Types d’emplacement**, définissez le champ **Type d’emplacement de tri**, entrez *TRI*.</span><span class="sxs-lookup"><span data-stu-id="e7714-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="e7714-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="e7714-140">Profil d’emplacement</span><span class="sxs-lookup"><span data-stu-id="e7714-140">Location profile</span></span>

1. <span data-ttu-id="e7714-141">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="e7714-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="e7714-142">Dans le volet Actions, sélectionnez **Nouveau** pour créer un profil d’emplacement pour l’emplacement de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="e7714-143">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="e7714-144">**ID de profil d’emplacement :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="e7714-145">**Nom :** *Trie*</span><span class="sxs-lookup"><span data-stu-id="e7714-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="e7714-146">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e7714-147">**Format de l’emplacement :** *EMBALLER*</span><span class="sxs-lookup"><span data-stu-id="e7714-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="e7714-148">**Type d’emplacement :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="e7714-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="e7714-149">**Utiliser le suivi du contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="e7714-150">**Autoriser les articles mixtes :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="e7714-151">**Autoriser les statuts de stock mixtes :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="e7714-152">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="e7714-153">Emplacements</span><span class="sxs-lookup"><span data-stu-id="e7714-153">Locations</span></span>

1. <span data-ttu-id="e7714-154">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="e7714-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="e7714-155">Décochez la case **Générer des chiffres de contrôle pour l’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="e7714-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="e7714-156">Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="e7714-157">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="e7714-158">**Emplacement :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="e7714-159">**ID de profil d’emplacement :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="e7714-160">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="e7714-161">Profils d’emballage</span><span class="sxs-lookup"><span data-stu-id="e7714-161">Packing profiles</span></span>

1. <span data-ttu-id="e7714-162">Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Profils d’emballage**.</span><span class="sxs-lookup"><span data-stu-id="e7714-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="e7714-163">Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="e7714-164">**ID du profil d’emballage :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="e7714-165">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="e7714-166">**Stratégie d’emballage de conteneur :** laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="e7714-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="e7714-167">**Mode d’identification du conteneur :** *Auto*</span><span class="sxs-lookup"><span data-stu-id="e7714-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="e7714-168">**Type de conteneur :** *PALETTE 48X48*</span><span class="sxs-lookup"><span data-stu-id="e7714-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="e7714-169">**Créer automatiquement un conteneur à la clôture du conteneur :** laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="e7714-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="e7714-170">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="e7714-171">Codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="e7714-171">Wave step codes</span></span>

<span data-ttu-id="e7714-172">Si vous avez activé la fonction *Code étape de vague à l’échelle de l’organisation*, configurez le code suivant.</span><span class="sxs-lookup"><span data-stu-id="e7714-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="e7714-173">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**.</span><span class="sxs-lookup"><span data-stu-id="e7714-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="e7714-174">Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="e7714-175">**Code étape de vague :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="e7714-176">**Description étape de vague :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="e7714-177">**Type étape de vague :** *Modèle de tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="e7714-178">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="e7714-179">Modèle de tri sortant</span><span class="sxs-lookup"><span data-stu-id="e7714-179">Outbound sorting template</span></span>

<span data-ttu-id="e7714-180">Le modèle de tri contrôle si des positions de tri sont créées, quels critères sont utilisés et d’autres attributs du processus de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="e7714-181">Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Modèles de tri sortants**.</span><span class="sxs-lookup"><span data-stu-id="e7714-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="e7714-182">Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="e7714-183">Dans l’en-tête du nouveau modèle, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="e7714-184">**ID du modèle de tri sortant :** *Tri vague*</span><span class="sxs-lookup"><span data-stu-id="e7714-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="e7714-185">**Description :** *Tri vague*</span><span class="sxs-lookup"><span data-stu-id="e7714-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="e7714-186">**Type de modèle de tri :** *Demande de vague*</span><span class="sxs-lookup"><span data-stu-id="e7714-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="e7714-187">Ce champ définit le processus pour lequel le modèle de tri est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e7714-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="e7714-188">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-188">The following values are available:</span></span>

        - <span data-ttu-id="e7714-189">**Demande de vague** : le modèle de tri est utilisé pour le processus *Mettre au mur*.</span><span class="sxs-lookup"><span data-stu-id="e7714-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="e7714-190">Ce type de modèle est utilisé pour contourner la station de conditionnement et traiter directement le stock en dehors de la vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="e7714-191">Vous ne pouvez utiliser ce type que si la méthode de traitement de vague **tri** est incluse dans le modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="e7714-192">**Conteneur** : le modèle de tri est utilisé pour le processus *Composition de palette après emballage*.</span><span class="sxs-lookup"><span data-stu-id="e7714-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="e7714-193">Ce type de modèle est utilisé pour traiter les conteneurs qui sont fermés à cette station de conditionnement et qui doivent être triés vers des palettes.</span><span class="sxs-lookup"><span data-stu-id="e7714-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="e7714-194">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="e7714-195">**Emplacement :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="e7714-196">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e7714-197">**Vérification du tri :** *Analyse de position*</span><span class="sxs-lookup"><span data-stu-id="e7714-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="e7714-198">Ce champ définit la vérification requise lors du tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="e7714-199">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-199">The following values are available:</span></span>

        - <span data-ttu-id="e7714-200">None</span><span class="sxs-lookup"><span data-stu-id="e7714-200">None</span></span>
        - <span data-ttu-id="e7714-201">Analyse de contenant</span><span class="sxs-lookup"><span data-stu-id="e7714-201">License plate scan</span></span>
        - <span data-ttu-id="e7714-202">Analyse de position</span><span class="sxs-lookup"><span data-stu-id="e7714-202">Position scan</span></span>

    - <span data-ttu-id="e7714-203">**Créer un travail à la clôture de la position :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="e7714-204">Si cette option est définie sur *Oui*, un travail sera créé à la clôture de la position pour déplacer le stock vers l’emplacement d’expédition final.</span><span class="sxs-lookup"><span data-stu-id="e7714-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="e7714-205">Si cette option est définie sur *Non*, le stock sera immédiatement prélevé pour la commande au moment de la clôture de la position.</span><span class="sxs-lookup"><span data-stu-id="e7714-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="e7714-206">**Affectation de position :** *Manuelle*</span><span class="sxs-lookup"><span data-stu-id="e7714-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="e7714-207">Ce champ définit le type d’affectation de position.</span><span class="sxs-lookup"><span data-stu-id="e7714-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="e7714-208">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-208">The following values are available:</span></span>

        - <span data-ttu-id="e7714-209">**Manuelle** : l’utilisateur doit toujours indiquer la position de destination de tri du stock.</span><span class="sxs-lookup"><span data-stu-id="e7714-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="e7714-210">**Automatique** : le système guide automatiquement le stock vers une position chaque fois que cela est possible, selon les répartitions du modèle de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="e7714-211">**Critères d’affectation de position de tri :** *N’utiliser que des positions vides*</span><span class="sxs-lookup"><span data-stu-id="e7714-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="e7714-212">Ce champ contrôle si le stock déjà présent sur les positions de tri sera pris en compte lors de l’affectation d’une position pour la demande.</span><span class="sxs-lookup"><span data-stu-id="e7714-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="e7714-213">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-213">The following values are available:</span></span>

        - <span data-ttu-id="e7714-214">**N’utiliser que des positions vides** : les positions auxquelles un stock est déjà associé seront prises en compte</span><span class="sxs-lookup"><span data-stu-id="e7714-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="e7714-215">**Supposer les positions vides** : tout stock déjà présent à a position sera ignoré lors de l’affectation.</span><span class="sxs-lookup"><span data-stu-id="e7714-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="e7714-216">Toutes les positions disponibles seront utilisées.</span><span class="sxs-lookup"><span data-stu-id="e7714-216">All available positions will be used.</span></span>

    - <span data-ttu-id="e7714-217">**Code étape de vague :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="e7714-218">Si la fonction *Code étape de vague à l’échelle de l’organisation* est activée, le code étape de vague *Tri* doit également être configuré dans les codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="e7714-219">**Fermer automatiquement la position de tri :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="e7714-220">Si cette option est définie sur *Oui*, la position de tri sera automatiquement fermée une fois que tout le travail arrivant à la position aura été exécuté.</span><span class="sxs-lookup"><span data-stu-id="e7714-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="e7714-221">**Nombre de positions de tri :** *3*</span><span class="sxs-lookup"><span data-stu-id="e7714-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="e7714-222">Ce champ définit le nombre maximum de positions de tri que le système créera.</span><span class="sxs-lookup"><span data-stu-id="e7714-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="e7714-223">**Préfixe de position de tri :** *SP-*</span><span class="sxs-lookup"><span data-stu-id="e7714-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="e7714-224">Ce champ définit le préfixe que le système attribue avant le numéro de la position.</span><span class="sxs-lookup"><span data-stu-id="e7714-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="e7714-225">**Emballer automatiquement la position de tri :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e7714-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="e7714-226">Si cette option est définie sur *Oui*, le stock à la position de tri sera emballé dans un conteneur une fois la position fermée.</span><span class="sxs-lookup"><span data-stu-id="e7714-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="e7714-227">**ID du profil d’emballage :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="e7714-228">Ce champ définit le profil d’emballage qui sera utilisé lorsque la position de tri sera emballée dans un conteneur.</span><span class="sxs-lookup"><span data-stu-id="e7714-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="e7714-229">Dans le volet Actions, sélectionnez **Modifier la requête** pour spécifier les critères utilisés pour ce modèle de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="e7714-230">Dans la boîte de dialogue de la requête, dans l’onglet **Tri**, sélectionnez **Nouveau** pour ajouter une ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="e7714-231">**Table :** *Détails du chargement*</span><span class="sxs-lookup"><span data-stu-id="e7714-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="e7714-232">**Table dérivée :** *Détails du chargement*</span><span class="sxs-lookup"><span data-stu-id="e7714-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="e7714-233">**Champ :** *ID expédition*</span><span class="sxs-lookup"><span data-stu-id="e7714-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="e7714-234">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="e7714-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="e7714-235">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7714-235">Select **OK**.</span></span>
1. <span data-ttu-id="e7714-236">Le message suivant peut s’afficher : « Le regroupement sera réinitialisé, continuer ? »</span><span class="sxs-lookup"><span data-stu-id="e7714-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="e7714-237">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e7714-237">Select **Yes**.</span></span>

    <span data-ttu-id="e7714-238">Le bouton **Répartitions du modèle de tri sortant** du volet Actions devient disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="e7714-239">Dans le volet Actions, sélectionnez **Répartitions du modèle de tri sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="e7714-240">Cochez la case **Grouper par domaine** pour regrouper par ID d’expédition.</span><span class="sxs-lookup"><span data-stu-id="e7714-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="e7714-241">Ce paramètre créera une position de tri par expédition qui correspond à un conteneur dans la vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="e7714-242">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7714-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="e7714-243">Méthodes de traitement de la vague</span><span class="sxs-lookup"><span data-stu-id="e7714-243">Wave process methods</span></span>

1. <span data-ttu-id="e7714-244">Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**.</span><span class="sxs-lookup"><span data-stu-id="e7714-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="e7714-245">Dans le volet Actions, sélectionnez **Régénérer des méthodes**.</span><span class="sxs-lookup"><span data-stu-id="e7714-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="e7714-246">La méthode **tri** est ajoutée à la liste des méthodes disponibles, et le type de modèle de vague *livraison* est sélectionné pour elle.</span><span class="sxs-lookup"><span data-stu-id="e7714-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="e7714-247">Modèles de vague</span><span class="sxs-lookup"><span data-stu-id="e7714-247">Wave templates</span></span>

<span data-ttu-id="e7714-248">Modifiez le modèle de vague utilisé pour le tri de la demande de vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="e7714-249">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="e7714-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="e7714-250">Dans le champ **Type de modèle de vague**, sélectionnez *Expédition*.</span><span class="sxs-lookup"><span data-stu-id="e7714-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="e7714-251">Sélectionnez le modèle existant **Livraison 62 par défaut**.</span><span class="sxs-lookup"><span data-stu-id="e7714-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="e7714-252">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7714-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e7714-253">Dans l’organisateur **Général**, apportez les modifications suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="e7714-254">Définissez l’option **Traiter la vague à la sortie dans l’entrepôt** sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="e7714-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="e7714-255">Définissez l’option **Affecter à des vagues en cours** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="e7714-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="e7714-256">Dans l’organisateur **Méthodes**, configurez la méthode **tri** :</span><span class="sxs-lookup"><span data-stu-id="e7714-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="e7714-257">Dans la grille **Méthodes restantes**, sélectionnez **tri**.</span><span class="sxs-lookup"><span data-stu-id="e7714-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="e7714-258">Sélectionnez le bouton Flèche droite pour déplacer la méthode **tri** vers la grille **Méthodes sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="e7714-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="e7714-259">Dans la grille **Méthodes sélectionnées**, sélectionnez **tri**.</span><span class="sxs-lookup"><span data-stu-id="e7714-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="e7714-260">Définissez le champ **Code étape de vague** sur *Trier*.</span><span class="sxs-lookup"><span data-stu-id="e7714-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="e7714-261">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="e7714-262">Options de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="e7714-262">Mobile device menu items</span></span>

1. <span data-ttu-id="e7714-263">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="e7714-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="e7714-264">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e7714-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e7714-265">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="e7714-266">**Nom de l’option de menu :** *Trier*</span><span class="sxs-lookup"><span data-stu-id="e7714-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="e7714-267">**Titre :** *Trier*</span><span class="sxs-lookup"><span data-stu-id="e7714-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="e7714-268">**Mode :** *Indirect*</span><span class="sxs-lookup"><span data-stu-id="e7714-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="e7714-269">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="e7714-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="e7714-270">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e7714-271">**Code d’activité :** *Tri sortant*</span><span class="sxs-lookup"><span data-stu-id="e7714-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="e7714-272">**Utiliser le guide de processus :** *Oui* (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="e7714-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="e7714-273">**ID du modèle de tri sortant :** *Tri vague*</span><span class="sxs-lookup"><span data-stu-id="e7714-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="e7714-274">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="e7714-275">Menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="e7714-275">Mobile device menu</span></span>

1. <span data-ttu-id="e7714-276">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="e7714-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="e7714-277">Dans la liste des menus, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="e7714-278">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7714-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e7714-279">Dans la grille **Menus et éléments de menu disponibles**, recherchez et sélectionnez l’élément de menu **Trier** que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="e7714-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="e7714-280">Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Trier** vers la grille **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="e7714-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="e7714-281">De cette façon, vous ajoutez votre nouvel élément de menu au menu **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="e7714-282">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="e7714-283">Instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="e7714-283">Location directives</span></span>

<span data-ttu-id="e7714-284">Vous devez créer des directives d’emplacement pour guider le travail créé une fois le tri terminé.</span><span class="sxs-lookup"><span data-stu-id="e7714-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="e7714-285">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="e7714-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="e7714-286">Dans le champ **Type d’ordre de travail**, sélectionnez *Prélèvement de stock trié*.</span><span class="sxs-lookup"><span data-stu-id="e7714-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="e7714-287">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e7714-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e7714-288">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="e7714-289">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="e7714-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="e7714-290">**Nom :** *Placer à la porte baie*</span><span class="sxs-lookup"><span data-stu-id="e7714-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="e7714-291">Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="e7714-292">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="e7714-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="e7714-293">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="e7714-293">**Site:** *6*</span></span>
    - <span data-ttu-id="e7714-294">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="e7714-295">**Code directif :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="e7714-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="e7714-296">**Plusieurs SKU :** *Non*</span><span class="sxs-lookup"><span data-stu-id="e7714-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="e7714-297">Sélectionnez **Enregistrer** pour rendre l’organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="e7714-298">Dans l’organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="e7714-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="e7714-299">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="e7714-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="e7714-300">**Souche de N° :** *1*</span><span class="sxs-lookup"><span data-stu-id="e7714-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e7714-301">**Quantité de départ :** *0*</span><span class="sxs-lookup"><span data-stu-id="e7714-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="e7714-302">**Quantité d’arrivée :** *1000000*</span><span class="sxs-lookup"><span data-stu-id="e7714-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="e7714-303">Sélectionnez **Enregistrer** pour rendre l’organisateur **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="e7714-304">Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="e7714-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="e7714-305">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="e7714-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="e7714-306">**Souche de N° :** *1*</span><span class="sxs-lookup"><span data-stu-id="e7714-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e7714-307">**Nom :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="e7714-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="e7714-308">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de l’organisateur **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="e7714-309">Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="e7714-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="e7714-310">Dans la boîte de dialogue de la requête, dans l’onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*.</span><span class="sxs-lookup"><span data-stu-id="e7714-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="e7714-311">Définissez le champ **Critères** de cette ligne sur *Porte baie*.</span><span class="sxs-lookup"><span data-stu-id="e7714-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="e7714-312">Cliquez sur **OK** pour confirmer les modifications.</span><span class="sxs-lookup"><span data-stu-id="e7714-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="e7714-313">Classes de travail</span><span class="sxs-lookup"><span data-stu-id="e7714-313">Work classes</span></span>

1. <span data-ttu-id="e7714-314">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="e7714-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="e7714-315">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e7714-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e7714-316">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="e7714-317">**ID classe de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="e7714-318">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="e7714-319">**Type d’ordre de travail :** *Prélèvement de stock trié*</span><span class="sxs-lookup"><span data-stu-id="e7714-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="e7714-320">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="e7714-321">Modèles de travail</span><span class="sxs-lookup"><span data-stu-id="e7714-321">Work templates</span></span>

1. <span data-ttu-id="e7714-322">Accédez à **Gestion des entrepôts \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="e7714-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e7714-323">Dans le champ **Type d’ordre de travail**, sélectionnez *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="e7714-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="e7714-324">Dans la grille, sélectionnez le modèle de travail **62 Prélever pour emballage**.</span><span class="sxs-lookup"><span data-stu-id="e7714-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="e7714-325">Dans le volet Actions, sélectionnez **Décompositions de l’en-tête de travail**.</span><span class="sxs-lookup"><span data-stu-id="e7714-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="e7714-326">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e7714-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e7714-327">Sur la ligne où le champ **Nom de domaine** est défini sur *ID d’expédition*, décochez la case **Regrouper par ce champ**.</span><span class="sxs-lookup"><span data-stu-id="e7714-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="e7714-328">Sélectionnez **Enregistrer**, puis fermez la boîte de dialogue **Décompositions de l’en-tête de travail**.</span><span class="sxs-lookup"><span data-stu-id="e7714-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="e7714-329">Dans le champ **Type d’ordre de travail**, sélectionnez *Prélèvement de stock trié*.</span><span class="sxs-lookup"><span data-stu-id="e7714-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="e7714-330">Sélectionnez **Nouveau** pour créer un modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="e7714-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="e7714-331">Dans la section **Vue d’ensemble**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="e7714-332">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="e7714-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="e7714-333">**Modèle de travail :** *Prélèvement triés*</span><span class="sxs-lookup"><span data-stu-id="e7714-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="e7714-334">**Description du modèle de travail :** *Prélèvement triés*</span><span class="sxs-lookup"><span data-stu-id="e7714-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="e7714-335">Sélectionnez **Enregistrer** pour rendre la section **Détails du modèle de travail** disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="e7714-336">Dans la section **Détails du modèle de travail**, vous allez créer deux lignes.</span><span class="sxs-lookup"><span data-stu-id="e7714-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="e7714-337">Sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="e7714-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="e7714-338">**Type de travail :** *Choisir*</span><span class="sxs-lookup"><span data-stu-id="e7714-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="e7714-339">**Obligatoire :** Sélectionné (=*Oui*)</span><span class="sxs-lookup"><span data-stu-id="e7714-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="e7714-340">**ID classe de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="e7714-341">Sélectionnez **Nouveau** à nouveau, puis définissez les valeurs suivantes pour la ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="e7714-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="e7714-342">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="e7714-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="e7714-343">**Obligatoire :** Sélectionné (=*Oui*)</span><span class="sxs-lookup"><span data-stu-id="e7714-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="e7714-344">**ID classe de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="e7714-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="e7714-345">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e7714-346">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="e7714-346">Example scenario</span></span>

<span data-ttu-id="e7714-347">Ce scénario simule une situation où l’entrepôt stocke de petits articles dans des emplacements et doit les emballer dans des boîtes avant de les expédier, et où la fonctionnalité de station de conditionnement n’est pas vraiment adaptée.</span><span class="sxs-lookup"><span data-stu-id="e7714-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="e7714-348">Les travailleurs prélèvent les commandes pour plusieurs clients et différentes adresses en même temps pour augmenter la vitesse de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e7714-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="e7714-349">Une fois le prélèvement terminé, les employés arrivent à l’emplacement du tri, où les articles prélevés peuvent être triés dans la bonne boîte, en fonction des critères requis.</span><span class="sxs-lookup"><span data-stu-id="e7714-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="e7714-350">Dans cet exemple, l’ID d’expédition sera utilisé pour déterminer la boîte correcte, car chaque expédition a une adresse différente.</span><span class="sxs-lookup"><span data-stu-id="e7714-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="e7714-351">Une fois que tous les articles du chargement sont emballés et triés par expédition, les boîtes sont déplacées vers la zone de transit et sont finalement chargées sur un camion.</span><span class="sxs-lookup"><span data-stu-id="e7714-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="e7714-352">Avant de démarrer le scénario, assurez-vous que toutes les fonctionnalités d’entrepôt standard sont correctement configurées pour votre entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e7714-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="e7714-353">Nous utilisons l’entrepôt standard Contoso *62* à cet effet.</span><span class="sxs-lookup"><span data-stu-id="e7714-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="e7714-354">Les configurations standard n’ont pas été modifiées par rapport à ce qui est décrit dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="e7714-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="e7714-355">Créer une demande</span><span class="sxs-lookup"><span data-stu-id="e7714-355">Create demand</span></span>

<span data-ttu-id="e7714-356">Avant de pouvoir faire la démonstration de cette fonctionnalité, vous devez créer une demande.</span><span class="sxs-lookup"><span data-stu-id="e7714-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="e7714-357">Pour ce scénario, vous allez créer trois commandes client pour trois clients différents afin de simuler différentes adresses de livraison.</span><span class="sxs-lookup"><span data-stu-id="e7714-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="e7714-358">De cette manière, vous créerez trois expéditions distinctes.</span><span class="sxs-lookup"><span data-stu-id="e7714-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="e7714-359">Avant de créer des commandes client et des expéditions, assurez-vous que les emplacements de prélèvement disposent d’un stock suffisant pour tous les articles des commandes client.</span><span class="sxs-lookup"><span data-stu-id="e7714-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="e7714-360">Examinez les paramètres des instructions d’emplacement pour vérifier les emplacements de prélèvement utilisés pour le prélèvement des commandes client.</span><span class="sxs-lookup"><span data-stu-id="e7714-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="e7714-361">Si vous devez ajuster le stock, vous pouvez créer des mouvements manuels, utiliser le réapprovisionnement ou utiliser tout autre flux.</span><span class="sxs-lookup"><span data-stu-id="e7714-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="e7714-362">Réservez ensuite le stock.</span><span class="sxs-lookup"><span data-stu-id="e7714-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="e7714-363">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="e7714-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e7714-364">Sélectionnez **Nouveau** pour créer une commande client pour la commande 1.</span><span class="sxs-lookup"><span data-stu-id="e7714-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="e7714-365">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e7714-366">**Client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e7714-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="e7714-367">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="e7714-368">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7714-368">Select **OK**.</span></span>
1. <span data-ttu-id="e7714-369">Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="e7714-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e7714-370">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-370">Set the following values:</span></span>

    - <span data-ttu-id="e7714-371">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e7714-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e7714-372">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="e7714-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="e7714-373">Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="e7714-374">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e7714-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="e7714-375">**Quantité :** *10*</span><span class="sxs-lookup"><span data-stu-id="e7714-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="e7714-376">Répétez les étapes suivantes pour chaque ligne de la commande afin de réserver le stock qui y correspond :</span><span class="sxs-lookup"><span data-stu-id="e7714-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="e7714-377">Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e7714-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="e7714-378">Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e7714-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="e7714-379">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-379">Select **Save**.</span></span>

1. <span data-ttu-id="e7714-380">Sélectionnez **Nouveau** pour créer une commande client pour la commande 2.</span><span class="sxs-lookup"><span data-stu-id="e7714-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="e7714-381">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e7714-382">**Client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="e7714-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="e7714-383">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="e7714-384">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7714-384">Select **OK**.</span></span>
1. <span data-ttu-id="e7714-385">Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="e7714-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e7714-386">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-386">Set the following values:</span></span>

    - <span data-ttu-id="e7714-387">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e7714-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e7714-388">**Quantité :** *7*</span><span class="sxs-lookup"><span data-stu-id="e7714-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="e7714-389">Sélectionnez **Ajouter une ligne** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="e7714-390">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e7714-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="e7714-391">**Quantité :** *3*</span><span class="sxs-lookup"><span data-stu-id="e7714-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="e7714-392">Répétez les étapes suivantes pour chaque ligne de la commande afin de réserver le stock qui y correspond :</span><span class="sxs-lookup"><span data-stu-id="e7714-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="e7714-393">Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e7714-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="e7714-394">Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e7714-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="e7714-395">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-395">Select **Save**.</span></span>

1. <span data-ttu-id="e7714-396">Sélectionnez **Nouveau** pour créer une commande client pour la commande 3.</span><span class="sxs-lookup"><span data-stu-id="e7714-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="e7714-397">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e7714-398">**Client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="e7714-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="e7714-399">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="e7714-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="e7714-400">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7714-400">Select **OK**.</span></span>
1. <span data-ttu-id="e7714-401">Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="e7714-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e7714-402">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7714-402">Set the following values:</span></span>

    - <span data-ttu-id="e7714-403">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e7714-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e7714-404">**Quantité :** *8*</span><span class="sxs-lookup"><span data-stu-id="e7714-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="e7714-405">Procédez comme suit pour réserver le stock pour la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e7714-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="e7714-406">Sur l’organisateur **Lignes de commande client**, dans le menu **Stock**, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e7714-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="e7714-407">Dans la page **Réservation**, sélectionnez **Réserver un lot**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e7714-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="e7714-408">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7714-408">Select **Save**.</span></span>

<span data-ttu-id="e7714-409">Exécutez la procédure suivante pour libérer chaque commande client vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e7714-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="e7714-410">Trois expéditions différentes seront créées.</span><span class="sxs-lookup"><span data-stu-id="e7714-410">Three different shipments will be created.</span></span> <span data-ttu-id="e7714-411">Vous ajouterez ensuite les trois expéditions à une nouvelle vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="e7714-412">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="e7714-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e7714-413">Dans la grille, sélectionnez la première commande client que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="e7714-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="e7714-414">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e7714-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="e7714-415">Vous recevez un message d’information indiquant l’ID de vague et l’ID d’expédition ont été créés.</span><span class="sxs-lookup"><span data-stu-id="e7714-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="e7714-416">Répétez les étapes précédentes pour libérer les commandes client 2 et 3 vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e7714-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="e7714-417">Notez que le message d’information que vous recevez indique qu’une expédition a été ajoutée à la vague qui a été créée lorsque vous avez lancé la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="e7714-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="e7714-418">Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.</span><span class="sxs-lookup"><span data-stu-id="e7714-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="e7714-419">Sélectionnez l’ID de vague qui a été créé à partir du lancement des commandes client pour ouvrir la page **Vagues**.</span><span class="sxs-lookup"><span data-stu-id="e7714-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="e7714-420">Cette page affiche les détails de la vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-420">This page shows the wave details.</span></span> <span data-ttu-id="e7714-421">L’organisateur **Lignes de vague** affiche les expéditions qui ont été créées.</span><span class="sxs-lookup"><span data-stu-id="e7714-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="e7714-422">Vous devez maintenant créer un travail pour apporter les articles des lieux de prélèvement au lieu de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="e7714-423">Dans le volet Actions, sélectionnez **Processus**.</span><span class="sxs-lookup"><span data-stu-id="e7714-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="e7714-424">Pendant le traitement de la vague, la méthode de tri utilisera le modèle de tri pour affecter le stock aux positions de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="e7714-425">Une fois le traitement de la vague terminé, vous recevez un message d’information indiquant que le travail a été créé et que la vague a été validée.</span><span class="sxs-lookup"><span data-stu-id="e7714-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="e7714-426">Dans le volet Actions, dans l’onglet **Vague**, dans le groupe **Informations connexes**, sélectionnez **Travail** pour afficher le travail créé.</span><span class="sxs-lookup"><span data-stu-id="e7714-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="e7714-427">Prenez note de l’ID du travail.</span><span class="sxs-lookup"><span data-stu-id="e7714-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="e7714-428">Accédez à **Gestion d’entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="e7714-429">Dans la colonne de gauche, vous pouvez afficher la position de tri sortant qui a été créée pour chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="e7714-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="e7714-430">Dans l’organisateur **Critères de position de tri**, vous pouvez afficher l’ID d’expédition pour cette position.</span><span class="sxs-lookup"><span data-stu-id="e7714-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="e7714-431">Un ID de travail a été créé pour apporter le stock des lieux de prélèvement au lieu de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="e7714-432">Pour terminer le travail, vous aurez besoin de l’ID de travail qui aura été créé lors du traitement de la vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="e7714-433">Prélèvement de la commande client vers le lieu de tri</span><span class="sxs-lookup"><span data-stu-id="e7714-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="e7714-434">Connectez-vous à l’application mobile en tant qu’employé de l’entrepôt *62*.</span><span class="sxs-lookup"><span data-stu-id="e7714-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="e7714-435">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="e7714-436">Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.</span><span class="sxs-lookup"><span data-stu-id="e7714-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="e7714-437">Sélectionnez le champ **ID**, puis entrez l’ID de travail du traitement de la vague.</span><span class="sxs-lookup"><span data-stu-id="e7714-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="e7714-438">Confirmez votre entrée.</span><span class="sxs-lookup"><span data-stu-id="e7714-438">Confirm your entry.</span></span>

    <span data-ttu-id="e7714-439">Vous êtes ensuite invité à entrer un contenant cible (LP).</span><span class="sxs-lookup"><span data-stu-id="e7714-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="e7714-440">Notez que la ligne 1 de la commande client 1 correspond à ce qui doit être prélevé et ajouté au contenant cible.</span><span class="sxs-lookup"><span data-stu-id="e7714-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="e7714-441">Le numéro d’article, la quantité, la description de l’article et l’emplacement du prélèvement sont affichés.</span><span class="sxs-lookup"><span data-stu-id="e7714-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="e7714-442">Dans le champ **LP cible**, entrez un numéro de contenant cible.</span><span class="sxs-lookup"><span data-stu-id="e7714-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="e7714-443">Vous prélèverez toutes les lignes créées à partir de la vague traitée dans le même contenant cible.</span><span class="sxs-lookup"><span data-stu-id="e7714-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="e7714-444">Confirmez votre entrée.</span><span class="sxs-lookup"><span data-stu-id="e7714-444">Confirm your entry.</span></span>

    <span data-ttu-id="e7714-445">L’application mobile présente désormais une série de pages **Prélever** qui pointent vers le lieu de prélèvement et vers l’article et la quantité à prélever.</span><span class="sxs-lookup"><span data-stu-id="e7714-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="e7714-446">Une fois l’article prélevé ajouté au contenant, vous confirmez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e7714-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="e7714-447">La dernière page correspond au travail de placement des articles prélevés dans l’emplacement de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="e7714-448">Confirmez le premier travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e7714-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="e7714-449">Le travail de prélèvement suivant est affiché.</span><span class="sxs-lookup"><span data-stu-id="e7714-449">The next pick work is shown.</span></span> <span data-ttu-id="e7714-450">Confirmez le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e7714-450">Confirm the pick.</span></span>
1. <span data-ttu-id="e7714-451">Continuez à confirmer le travail de prélèvement restant.</span><span class="sxs-lookup"><span data-stu-id="e7714-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="e7714-452">La dernière étape consiste à terminer le travail de placement.</span><span class="sxs-lookup"><span data-stu-id="e7714-452">The last step is to complete the put work.</span></span> <span data-ttu-id="e7714-453">Confirmez le rangement dans l’emplacement de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="e7714-454">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="e7714-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="e7714-455">Quittez le **Prélèvement des ventes** dans l’application mobile.</span><span class="sxs-lookup"><span data-stu-id="e7714-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="e7714-456">Tri/Mettre au mur</span><span class="sxs-lookup"><span data-stu-id="e7714-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="e7714-457">Maintenant que tout le stock a été placé à l’emplacement de tri, il doit être trié dans la position de tri correcte.</span><span class="sxs-lookup"><span data-stu-id="e7714-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="e7714-458">Connectez-vous à l’application mobile.</span><span class="sxs-lookup"><span data-stu-id="e7714-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="e7714-459">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="e7714-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="e7714-460">Dans le menu **Sortant**, sélectionnez **Trier** pour commencer à trier les articles.</span><span class="sxs-lookup"><span data-stu-id="e7714-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="e7714-461">Dans le champ **LP/CONT**, entrez le contenant cible du travail de la commande client prélevée.</span><span class="sxs-lookup"><span data-stu-id="e7714-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="e7714-462">Confirmez votre entrée.</span><span class="sxs-lookup"><span data-stu-id="e7714-462">Confirm your entry.</span></span>
1. <span data-ttu-id="e7714-463">Entrez le numéro de l’article à trier en premier.</span><span class="sxs-lookup"><span data-stu-id="e7714-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="e7714-464">Le système détermine la première position de tri à afficher.</span><span class="sxs-lookup"><span data-stu-id="e7714-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="e7714-465">Confirmez la position de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="e7714-466">Vous êtes invité à attribuer un contenant à la position de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="e7714-467">Sélectionnez le champ **LP**, entrez un numéro de contenant, puis confirmez votre entrée.</span><span class="sxs-lookup"><span data-stu-id="e7714-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="e7714-468">Étant donné que la position de tri est liée à l’ID d’expédition, vous allez trier les articles prélevés dans un contenant spécifique à l’expédition sortante et à la commande client.</span><span class="sxs-lookup"><span data-stu-id="e7714-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="e7714-469">La page suivante affiche l’ID de l’article, la quantité, l’ID de position de tri et les ID de contenant « de » (prélèvement) et « à » (tri).</span><span class="sxs-lookup"><span data-stu-id="e7714-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="e7714-470">Les informations de cette page vous indiquent de trier l’article et les quantités spécifiés entre le contenant de prélèvement et le contenant de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="e7714-471">Confirmez la position de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="e7714-472">Triez les articles dans la première position de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="e7714-473">Lorsque vous avez terminé, le système vous dirige vers la position de tri suivante.</span><span class="sxs-lookup"><span data-stu-id="e7714-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="e7714-474">Répétez ce processus pour toutes les lignes sélectionnées sur l’ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="e7714-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="e7714-475">Vous devez également utiliser ce processus lorsque plusieurs lignes de prélèvement portent le même numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="e7714-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="e7714-476">Au fur et à mesure que vous répétez ce processus pour tous les articles, le système évalue les critères de l’article numérisé suivant (ligne de travail) et détermine à quelle position de tri il doit être placé.</span><span class="sxs-lookup"><span data-stu-id="e7714-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="e7714-477">Vous êtes automatiquement invité à placer l’article dans la bonne position de tri.</span><span class="sxs-lookup"><span data-stu-id="e7714-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="e7714-478">Selon la configuration de la confirmation, vous êtes également invité à confirmer cette action en entrant le numéro de la position ou l’ID du contenant.</span><span class="sxs-lookup"><span data-stu-id="e7714-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7714-479">Si le tri automatique est activé, le remplacement manuel n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e7714-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="e7714-480">Lorsque vous avez terminé, dans Microsoft Dynamics 365 Supply Chain Management, ouvrez la page **Affectations de position de tri sortante** pour consulter l’état des positions.</span><span class="sxs-lookup"><span data-stu-id="e7714-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="e7714-481">Si les positions sont fermées automatiquement, sélectionnez **Afficher fermées** pour afficher les positions fermées.</span><span class="sxs-lookup"><span data-stu-id="e7714-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="e7714-482">Notez que les transactions de position de tri sont affichées.</span><span class="sxs-lookup"><span data-stu-id="e7714-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="e7714-483">L’article et la quantité qui ont été traités au niveau de la position sont affichés.</span><span class="sxs-lookup"><span data-stu-id="e7714-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="e7714-484">Lorsque vous configurez le modèle de tri sortant, vous définissez l’option **Fermer automatiquement la position de tri** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="e7714-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="e7714-485">Par conséquent, la position est automatiquement fermée une fois que le dernier article de stock attendu y a été placé.</span><span class="sxs-lookup"><span data-stu-id="e7714-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="e7714-486">Les positions de tri ont le statut **Fermé**, et un travail a été créé pour déplacer le stock trié vers l’emplacement *Porte baie*.</span><span class="sxs-lookup"><span data-stu-id="e7714-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="e7714-487">Terminez le travail de prélèvement du stock trié pour déplacer le stock vers le lieu d’expédition.</span><span class="sxs-lookup"><span data-stu-id="e7714-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="e7714-488">Lorsque le stock est prêt, confirmez-le pour expédition.</span><span class="sxs-lookup"><span data-stu-id="e7714-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="e7714-489">Pour que le travail de prélèvement du stock trié soit traité correctement, il convient d’utiliser un élément de menu d’appareil mobile ayant un ID de classe de travail où le champ **Type d’ordre de travail** est défini sur *Prélèvement de stock trié* pour le processus de déplacement et de chargement.</span><span class="sxs-lookup"><span data-stu-id="e7714-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="e7714-490">Fermer manuellement une position (facultatif)</span><span class="sxs-lookup"><span data-stu-id="e7714-490">Manually close a position (optional)</span></span>

<span data-ttu-id="e7714-491">Si les positions de tri doivent être fermées manuellement, l’option **Fermer automatiquement la position de tri** pour le modèle de tri sortant doit être définie sur *Non*, et la fermeture doit être effectuée avant que le stock ne puisse être déplacé vers la zone de la porte de la baie.</span><span class="sxs-lookup"><span data-stu-id="e7714-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="e7714-492">Il est possible de fermer les positions de différentes manières :</span><span class="sxs-lookup"><span data-stu-id="e7714-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="e7714-493">Via l’application d’entrepôt :</span><span class="sxs-lookup"><span data-stu-id="e7714-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="e7714-494">L’utilisateur peut scanner l’un des articles qui sont déjà sur la position, puis sélectionner **Fermer** pour fermer la position.</span><span class="sxs-lookup"><span data-stu-id="e7714-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="e7714-495">Si l’utilisateur scanne un conteneur qui a déjà été trié, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e7714-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="e7714-496">Cependant, l’utilisateur peut continuer à fermer la position.</span><span class="sxs-lookup"><span data-stu-id="e7714-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="e7714-497">Depuis la page **Affectations de position de tri sortante** de Microsoft Dynamics 365 Supply Chain Management :</span><span class="sxs-lookup"><span data-stu-id="e7714-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="e7714-498">L’utilisateur peut sélectionner l’enregistrement de position de tri sortant, puis sélectionner **Fermer la position** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e7714-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="e7714-499">Conseils</span><span class="sxs-lookup"><span data-stu-id="e7714-499">Tips</span></span>

- <span data-ttu-id="e7714-500">Les articles ne peuvent pas être déplacés d’une position à une autre une fois qu’ils ont été affectés à une d’elles.</span><span class="sxs-lookup"><span data-stu-id="e7714-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="e7714-501">Le système évalue combien de chaque article doit aller à une position spécifique.</span><span class="sxs-lookup"><span data-stu-id="e7714-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="e7714-502">Le modèle de tri peut être configuré pour créer automatiquement des conteneurs lorsque les positions sont fermées.</span><span class="sxs-lookup"><span data-stu-id="e7714-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="e7714-503">Cette approche créera une structure d’ID de conteneur standard basée sur le profil d’emballage spécifié.</span><span class="sxs-lookup"><span data-stu-id="e7714-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7714-504">Une fois que le travail de déplacement a été créé à partir de l’emplacement de tri, vous ne devez pas annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="e7714-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="e7714-505">Sinon, la position et les conteneurs qu’elle contient seront supprimés du système et ne seront pas disponibles pour un traitement ultérieur.</span><span class="sxs-lookup"><span data-stu-id="e7714-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="e7714-506">Le stock sera également supprimé.</span><span class="sxs-lookup"><span data-stu-id="e7714-506">The inventory will also be removed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]