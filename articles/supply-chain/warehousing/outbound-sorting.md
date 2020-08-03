---
title: Tri sortant
description: Cette rubrique fournit des informations sur le tri sortant. Cette fonctionnalité facilite la manipulation des petits conteneurs et aide les employés d'entrepôt à mieux planifier et organiser la capacité des palettes dans le camion.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e72249e26fb8f291f804cf5f2e4ce98bf88cd5bf
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596228"
---
# <a name="outbound-sorting"></a><span data-ttu-id="01d6c-104">Tri sortant</span><span class="sxs-lookup"><span data-stu-id="01d6c-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01d6c-105">Cette fonctionnalité facilite la manipulation des petits conteneurs et aide les employés d'entrepôt à mieux planifier et organiser la capacité des palettes dans le camion.</span><span class="sxs-lookup"><span data-stu-id="01d6c-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="01d6c-106">Lorsque vous utilisez le tri sortant, vous pouvez trier les conteneurs emballés sur la palette appropriée après leur arrivée dans une station de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="01d6c-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="01d6c-107">Vous pouvez également créer une hiérarchie de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="01d6c-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="01d6c-108">Cette fonctionnalité vous permet de créer des palettes à partir de conteneurs emballés via la fonctionnalité d'emballage.</span><span class="sxs-lookup"><span data-stu-id="01d6c-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="01d6c-109">Le conteneur n'est pas envoyé au lieu d'expédition final car il se trouve dans le flux d'emballage d'origine.</span><span class="sxs-lookup"><span data-stu-id="01d6c-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="01d6c-110">Au lieu de cela, les employés peuvent fermer le conteneur et le déplacer vers un emplacement de type de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="01d6c-111">Ils peuvent ensuite trier les conteneurs dans des emplacements, chacun ayant un contenant (LP, License Plate).</span><span class="sxs-lookup"><span data-stu-id="01d6c-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="01d6c-112">Une fois que les conteneurs ont été triés, un travail peut être créé pour envoyer l'ensemble de la LP au quai d'expédition final ou aux emplacements intermédiaires, en fonction des directives d'emplacement ou de vos propres besoins.</span><span class="sxs-lookup"><span data-stu-id="01d6c-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="01d6c-113">De plus, l'action de fermer la position de tri peut immédiatement déplacer le stock vers le lieu d'expédition final et le prélever pour la commande.</span><span class="sxs-lookup"><span data-stu-id="01d6c-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="01d6c-114">Activer la fonction de tri sortant</span><span class="sxs-lookup"><span data-stu-id="01d6c-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="01d6c-115">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="01d6c-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="01d6c-116">Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="01d6c-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="01d6c-117">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="01d6c-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="01d6c-118">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="01d6c-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="01d6c-119">**Nom de la fonction :** *Tri sortant*</span><span class="sxs-lookup"><span data-stu-id="01d6c-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="01d6c-120">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="01d6c-120">Setup</span></span>

<span data-ttu-id="01d6c-121">Pour ce scénario, vous devez utiliser les données de démonstration **USMF** standard et l'entrepôt *62*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="01d6c-122">Vous devez également mener à bien la configuration décrite dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="01d6c-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="01d6c-123">Paramétrage d'un modèle de vague</span><span class="sxs-lookup"><span data-stu-id="01d6c-123">Set up a wave template</span></span>

<span data-ttu-id="01d6c-124">Cette configuration traite automatiquement la vague et crée le travail lorsqu'une ligne est libérée pour l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="01d6c-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="01d6c-125">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="01d6c-126">Dans la liste des modèles, sélectionnez **Entrepôt 62**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="01d6c-127">Dans l'organisateur **Général**, assurez-vous que l'option **Traiter la vague à la libération dans l’entrepôt** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="01d6c-128">Paramétrer un employé</span><span class="sxs-lookup"><span data-stu-id="01d6c-128">Set up a worker</span></span>

<span data-ttu-id="01d6c-129">La station d'emballage est considérée comme un emplacement.</span><span class="sxs-lookup"><span data-stu-id="01d6c-129">The packing station is considered a location.</span></span> <span data-ttu-id="01d6c-130">Les employés de l'entrepôt qui se connectent à la station d'emballage ne voient et ne travaillent que sur les expéditions et les conteneurs prévus à cet emplacement de conditionnement spécifique.</span><span class="sxs-lookup"><span data-stu-id="01d6c-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="01d6c-131">Un utilisateur qui se connecte à Microsoft Dynamics 365 doit être configuré en tant qu'employé dans la gestion d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="01d6c-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="01d6c-132">Si le nom de l'utilisateur n'apparaît pas dans la liste des utilisateurs employés, appliquez la procédure suivante pour l'ajouter.</span><span class="sxs-lookup"><span data-stu-id="01d6c-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="01d6c-133">Ces étapes supposent que l'utilisateur existe déjà dans le système et a été associé en tant qu'employé ou travailleur dans le module **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="01d6c-134">Accédez à **Gestion des entrepôts \> Paramétrage \> Employé**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="01d6c-135">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-135">Select **New**.</span></span>
1. <span data-ttu-id="01d6c-136">Dans le champ **Employé**, sélectionnez l'utilisateur cible dans la liste des employés.</span><span class="sxs-lookup"><span data-stu-id="01d6c-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="01d6c-137">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-137">Select **Select**.</span></span>
1. <span data-ttu-id="01d6c-138">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="01d6c-139">Dans l'organisateur **Utilisateurs**, sélectionnez **Nouveau** pour créer un compte d'appareil mobile et définissez pour lui les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-140">**ID utilisateur :** entrez un ID unique.</span><span class="sxs-lookup"><span data-stu-id="01d6c-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="01d6c-141">**Nom d'utilisateur :** entrez un nom pour l'ID.</span><span class="sxs-lookup"><span data-stu-id="01d6c-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="01d6c-142">**Entrepôt par défaut :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-143">**Nom du menu :** *Principal*</span><span class="sxs-lookup"><span data-stu-id="01d6c-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="01d6c-144">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="01d6c-145">La boîte de dialogue **Définir le mot de passe** s'affiche ; vous pouvez y créer un mot de passe simple que l'utilisateur utilisera pour se connecter à l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="01d6c-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="01d6c-146">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-146">Set the following values:</span></span>

    - <span data-ttu-id="01d6c-147">**Mot de passe :** entrez un mot de passe simple.</span><span class="sxs-lookup"><span data-stu-id="01d6c-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="01d6c-148">**Confirmer le mot de passe :** saisissez à nouveau le même mot de passe.</span><span class="sxs-lookup"><span data-stu-id="01d6c-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="01d6c-149">Sélectionnez **Définir le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-149">Select **Set password**.</span></span>

    <span data-ttu-id="01d6c-150">Une notification dans le centre d'action vous informe que le mot de passe a été défini pour l'utilisateur que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="01d6c-151">Créer un type d'emplacement</span><span class="sxs-lookup"><span data-stu-id="01d6c-151">Create a location type</span></span>

1. <span data-ttu-id="01d6c-152">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Types d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="01d6c-153">Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d'emplacement et définissez-lui les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-154">**Type d’emplacement :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="01d6c-155">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="01d6c-156">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="01d6c-157">Définir les paramètres de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="01d6c-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="01d6c-158">Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="01d6c-159">Dans l'onglet **Général**, dans l'organisateur **Types d'emplacement**, définissez le champ **Type d'emplacement de tri** sur *TRI*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="01d6c-160">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="01d6c-161">Définir un profil d’emplacement</span><span class="sxs-lookup"><span data-stu-id="01d6c-161">Set up a location profile</span></span>

1. <span data-ttu-id="01d6c-162">Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Profils d'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="01d6c-163">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-164">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="01d6c-165">**ID de profil d'emplacement :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="01d6c-166">**Nom :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="01d6c-167">Dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-168">**Format de l'emplacement :** *ASRB* (Aisle-Rack-Shelf-Bin [Allée, Rayon, Étagère, Casier])</span><span class="sxs-lookup"><span data-stu-id="01d6c-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="01d6c-169">**Type d’emplacement :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="01d6c-170">**Utiliser le suivi du contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="01d6c-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="01d6c-171">**Autoriser les articles mixtes :** *Oui* (Lorsque vous définissez cette option sur *Oui*, l'option **Autoriser les traitement par lots de stock mixtes** est automatiquement définie sur *Oui* et ne peut pas être modifiée indépendamment.)</span><span class="sxs-lookup"><span data-stu-id="01d6c-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="01d6c-172">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="01d6c-173">Définir un emplacement</span><span class="sxs-lookup"><span data-stu-id="01d6c-173">Set up a location</span></span>

1. <span data-ttu-id="01d6c-174">Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="01d6c-175">Dans l'en-tête, décochez la case **Générer des chiffres de contrôle pour l'emplacement**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="01d6c-176">Dans le volet Actions, sélectionnez **Nouveau** pour créer un emplacement et définissez-lui les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-177">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-178">**Emplacement :** *SORT*</span><span class="sxs-lookup"><span data-stu-id="01d6c-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="01d6c-179">**ID de profil d'emplacement :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="01d6c-180">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="01d6c-181">Configurer un modèle de tri sortant</span><span class="sxs-lookup"><span data-stu-id="01d6c-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="01d6c-182">Le modèle de tri sortant détermine si le travail est créé à partir de l'emplacement de tri et si le tri est effectué manuellement ou automatiquement.</span><span class="sxs-lookup"><span data-stu-id="01d6c-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="01d6c-183">Pour ce scénario, vous allez créer un modèle de tri sortant pour composer des palettes après la station de conditionnement.</span><span class="sxs-lookup"><span data-stu-id="01d6c-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="01d6c-184">Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Modèles de tri sortants**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="01d6c-185">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-186">Dans l’en-tête du nouveau modèle, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="01d6c-187">**ID du modèle de tri sortant :** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="01d6c-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="01d6c-188">**Description :** *Création de travail automatique*</span><span class="sxs-lookup"><span data-stu-id="01d6c-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="01d6c-189">**Type de modèle de tri sortant :** *Conteneur*</span><span class="sxs-lookup"><span data-stu-id="01d6c-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="01d6c-190">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-191">**Emplacement :** *SORT*</span><span class="sxs-lookup"><span data-stu-id="01d6c-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="01d6c-192">Dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-193">**Vérification du tri :** *Analyse de position*</span><span class="sxs-lookup"><span data-stu-id="01d6c-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="01d6c-194">**Créer un travail à la clôture de la position :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="01d6c-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="01d6c-195">Si cette option est définie sur *Oui*, un travail sera créé à la clôture de la position pour déplacer le stock vers l'emplacement d'expédition final.</span><span class="sxs-lookup"><span data-stu-id="01d6c-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="01d6c-196">Si cette option est définie sur *Non*, le stock sera immédiatement prélevé pour la commande au moment de la clôture de la position.</span><span class="sxs-lookup"><span data-stu-id="01d6c-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="01d6c-197">**Affectation de position :** *Automatique*</span><span class="sxs-lookup"><span data-stu-id="01d6c-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="01d6c-198">Si ce champ est défini sur *Manuel*, l'utilisateur doit toujours indiquer la position de destination de tri du stock.</span><span class="sxs-lookup"><span data-stu-id="01d6c-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="01d6c-199">S'il est défini sur *Automatique*, le système guidera automatiquement le stock vers une position chaque fois que cela est possible, selon les répartitions du modèle de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="01d6c-200">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** disponible dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="01d6c-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="01d6c-201">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="01d6c-202">Dans l'éditeur de requêtes, dans l'onglet **Tri**, ajoutez une ligne comportant les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="01d6c-203">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="01d6c-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="01d6c-204">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="01d6c-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="01d6c-205">**Champ :** *Service de transporteur*</span><span class="sxs-lookup"><span data-stu-id="01d6c-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="01d6c-206">Quand vous sélectionnez cette valeur, le message suivant peut s’afficher : « Le champ Service de transporteur n’est pas un champ d’index.</span><span class="sxs-lookup"><span data-stu-id="01d6c-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="01d6c-207">Voulez-vous ajouter un tri à ce sujet ? »</span><span class="sxs-lookup"><span data-stu-id="01d6c-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="01d6c-208">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-208">Select **Yes**.</span></span>

    - <span data-ttu-id="01d6c-209">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="01d6c-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="01d6c-210">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-210">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-211">Le message suivant peut s'afficher : « Le regroupement sera réinitialisé, continuer ? »</span><span class="sxs-lookup"><span data-stu-id="01d6c-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="01d6c-212">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-212">Select **Yes**.</span></span>

    <span data-ttu-id="01d6c-213">Le bouton **Répartitions du modèle de tri sortant** du volet Actions devient disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="01d6c-214">Dans le volet Actions, sélectionnez **Répartitions du modèle de tri sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="01d6c-215">Dans la boîte de dialogue **Critères du tri sortant**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="01d6c-216">**Nom de la table de référence :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="01d6c-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="01d6c-217">**Nom du champ de référence :** *Service de transporteur*</span><span class="sxs-lookup"><span data-stu-id="01d6c-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="01d6c-218">**Grouper par domaine :** cochez cette case pour regrouper les envois par service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="01d6c-219">Sélectionnez **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01d6c-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="01d6c-220">Définir des stratégies d'emballage de conteneurs</span><span class="sxs-lookup"><span data-stu-id="01d6c-220">Set up container packing policies</span></span>

1. <span data-ttu-id="01d6c-221">Accédez à **Gestion des entrepôts \> Paramétrage \> Conteneurs \> Stratégies d'emballage de conteneurs**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="01d6c-222">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-223">Dans l’en-tête de la nouvelle stratégie, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="01d6c-224">**Stratégie d'emballage de conteneur :** *Trier*</span><span class="sxs-lookup"><span data-stu-id="01d6c-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-225">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="01d6c-226">Dans l'organisateur **Vue d'ensemble**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-227">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-228">**Emplacement de tri par défaut :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="01d6c-229">**Unité de poids :** *kg*</span><span class="sxs-lookup"><span data-stu-id="01d6c-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="01d6c-230">**Stratégie de fermeture des conteneurs :** *Libération automatique*</span><span class="sxs-lookup"><span data-stu-id="01d6c-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="01d6c-231">**Stratégie de libération des conteneurs :** *Attribuer le conteneur à une position de tri sortant*</span><span class="sxs-lookup"><span data-stu-id="01d6c-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="01d6c-232">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="01d6c-233">Paramétrer les profils de conditionnement</span><span class="sxs-lookup"><span data-stu-id="01d6c-233">Set up packing profiles</span></span>

<span data-ttu-id="01d6c-234">Créez un nouveau profil d'emballage qui sera utilisé avec la fonctionnalité de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="01d6c-235">Accédez à **Gestion des entrepôts \> Paramétrage \> Emballage \> Profils d'emballage**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="01d6c-236">Dans le volet Actions, sélectionnez **Nouveau** pour créer une ligne et définissez-lui les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-237">**ID du profil d'emballage :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-238">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-239">**Stratégie d'emballage de conteneur :** *Trier*</span><span class="sxs-lookup"><span data-stu-id="01d6c-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-240">**Mode d'identification du conteneur :** *Auto*</span><span class="sxs-lookup"><span data-stu-id="01d6c-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="01d6c-241">**Type de conteneur :** *Boîte-Large*</span><span class="sxs-lookup"><span data-stu-id="01d6c-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="01d6c-242">**Créer automatiquement un conteneur à la fermeture du conteneur :** Décoché (= *Non*)</span><span class="sxs-lookup"><span data-stu-id="01d6c-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="01d6c-243">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="01d6c-244">Définir des classes de travail</span><span class="sxs-lookup"><span data-stu-id="01d6c-244">Set up work classes</span></span>

<span data-ttu-id="01d6c-245">Définissez une classe de travail qui sera utilisée avec le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="01d6c-246">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="01d6c-247">Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe de travail pour le tri et définissez-lui les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-248">**ID classe de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-249">**Description :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-250">**Type d'ordre de travail :** *Prélèvement de stock trié*</span><span class="sxs-lookup"><span data-stu-id="01d6c-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="01d6c-251">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="01d6c-252">Configurer des éléments de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="01d6c-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="01d6c-253">Configurer un nouvel élément de menu de palette</span><span class="sxs-lookup"><span data-stu-id="01d6c-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="01d6c-254">Créez un élément de menu d'appareil mobile pour composer des palettes pendant le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="01d6c-255">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="01d6c-256">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-257">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="01d6c-258">**Nom de l'élément de menu :** *Composition de palette*</span><span class="sxs-lookup"><span data-stu-id="01d6c-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="01d6c-259">**Titre :** *Composition de palette*</span><span class="sxs-lookup"><span data-stu-id="01d6c-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="01d6c-260">**Mode :** *Indirect*</span><span class="sxs-lookup"><span data-stu-id="01d6c-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="01d6c-261">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="01d6c-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="01d6c-262">Dans l'organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-263">**Code d'activité :** *Tri sortant*</span><span class="sxs-lookup"><span data-stu-id="01d6c-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="01d6c-264">Lorsque ce champ est défini sur *Tri sortant*, le champ **ID du modèle de tri sortant** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="01d6c-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="01d6c-265">**Utiliser le guide de processus :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="01d6c-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="01d6c-266">Quand le champ **Code d'activité** est défini sur *Tri sortant*, cette option est automatiquement définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="01d6c-267">**ID du modèle de tri sortant :** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="01d6c-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="01d6c-268">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="01d6c-269">Configurer un nouvel élément de menu de chargement</span><span class="sxs-lookup"><span data-stu-id="01d6c-269">Set up a new loading menu item</span></span>

<span data-ttu-id="01d6c-270">Ensuite, créez un élément de menu qui permet aux utilisateurs de déplacer les articles en stock triés vers le lieu d'expédition.</span><span class="sxs-lookup"><span data-stu-id="01d6c-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="01d6c-271">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="01d6c-272">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-273">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="01d6c-274">**Nom de l'élément de menu :** *Charger à partir du tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="01d6c-275">**Titre :** *Charger à partir du tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="01d6c-276">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="01d6c-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="01d6c-277">**Utiliser un travail existant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="01d6c-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="01d6c-278">Sur l’organisateur **Général**, définissez le champ **Dirigé par** sur *Dirigé par l'utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="01d6c-279">Dans l'organisateur **Classes de travail**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="01d6c-280">**ID classe de travail :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="01d6c-281">**Type d'ordre de travail :** *Prélèvement de stock trié*</span><span class="sxs-lookup"><span data-stu-id="01d6c-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="01d6c-282">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="01d6c-283">Configurer le menu de l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="01d6c-283">Set up the mobile device menu</span></span>

<span data-ttu-id="01d6c-284">Vous devez maintenant ajouter les nouveaux éléments de menu au menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="01d6c-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="01d6c-285">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="01d6c-286">Sélectionnez le menu **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="01d6c-287">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="01d6c-288">Dans la colonne **Menus et éléments de menu disponibles**, recherchez et sélectionnez **Composition de palette**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="01d6c-289">Sélectionnez le bouton en forme de flèche vers la droite pour déplacer **Composition de palette** vers la colonne **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="01d6c-290">Utilisez les boutons en forme de flèche vers le haut et le bas pour placer l'élément de menu **Composition de palette** à la position souhaitée dans le menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="01d6c-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="01d6c-291">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-291">Select **Save**.</span></span>
1. <span data-ttu-id="01d6c-292">Répétez cette procédure pour ajouter l'élément de menu **Charger à partir du tri** au menu **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="01d6c-293">Définir des instructions d'emplacement</span><span class="sxs-lookup"><span data-stu-id="01d6c-293">Set up location directives</span></span>

<span data-ttu-id="01d6c-294">Les *Instructions d'emplacement* sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock.</span><span class="sxs-lookup"><span data-stu-id="01d6c-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="01d6c-295">Vous devez maintenant créer une règle pour gérer le travail de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="01d6c-296">Paramétrer une instruction relative à une seule SKU</span><span class="sxs-lookup"><span data-stu-id="01d6c-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="01d6c-297">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="01d6c-298">Dans le volet de gauche, modifiez la valeur du champ **Type d'ordre de travail** sur *Prélèvement de stock trié*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="01d6c-299">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-300">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="01d6c-301">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-302">**Nom :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="01d6c-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="01d6c-303">Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-304">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="01d6c-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="01d6c-305">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="01d6c-305">**Site:** *6*</span></span>
    - <span data-ttu-id="01d6c-306">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-307">**Plusieurs SKU :** *Non*</span><span class="sxs-lookup"><span data-stu-id="01d6c-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="01d6c-308">Sélectionnez **Enregistrer** pour rendre la barre d'outils dans l'organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="01d6c-309">Dans l'organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="01d6c-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="01d6c-310">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="01d6c-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="01d6c-311">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-312">**De :** *0*</span><span class="sxs-lookup"><span data-stu-id="01d6c-312">**From:** *0*</span></span>
    - <span data-ttu-id="01d6c-313">**À :** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="01d6c-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="01d6c-314">Sélectionnez **Enregistrer** pour rendre la barre d'outils dans l'organisateur **Actions d'instruction d'emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="01d6c-315">Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="01d6c-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="01d6c-316">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="01d6c-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="01d6c-317">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-318">**Nom :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="01d6c-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="01d6c-319">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-319">Select **Save**.</span></span>
1. <span data-ttu-id="01d6c-320">Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="01d6c-321">Dans l'éditeur de requêtes, dans l'onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="01d6c-322">Définissez le champ **Critères** de cette ligne sur *Porte baie*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="01d6c-323">Sélectionnez **OK** pour enregistrer vos paramètres et fermer l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="01d6c-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="01d6c-324">Paramétrer une instruction relative à plusieurs SKU</span><span class="sxs-lookup"><span data-stu-id="01d6c-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="01d6c-325">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="01d6c-326">Dans le volet de gauche, modifiez la valeur du champ **Type d'ordre de travail** sur *Prélèvement de stock trié*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="01d6c-327">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-328">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="01d6c-329">**Séquence :** *2*</span><span class="sxs-lookup"><span data-stu-id="01d6c-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="01d6c-330">**Nom :** *Porte baie Multi*</span><span class="sxs-lookup"><span data-stu-id="01d6c-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="01d6c-331">Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-332">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="01d6c-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="01d6c-333">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="01d6c-333">**Site:** *6*</span></span>
    - <span data-ttu-id="01d6c-334">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-335">**Plusieurs SKU :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="01d6c-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="01d6c-336">Sélectionnez **Enregistrer** pour rendre la barre d'outils dans l'organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="01d6c-337">Dans l'organisateur **Lignes**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="01d6c-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="01d6c-338">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="01d6c-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="01d6c-339">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-340">**De :** *0*</span><span class="sxs-lookup"><span data-stu-id="01d6c-340">**From:** *0*</span></span>
    - <span data-ttu-id="01d6c-341">**À :** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="01d6c-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="01d6c-342">Sélectionnez **Enregistrer** pour rendre la barre d'outils dans l'organisateur **Actions d'instruction d'emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="01d6c-343">Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau**, puis définissez les valeurs suivantes pour la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="01d6c-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="01d6c-344">Acceptez les valeurs par défaut dans tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="01d6c-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="01d6c-345">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-346">**Nom :** *Porte baie Multi*</span><span class="sxs-lookup"><span data-stu-id="01d6c-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="01d6c-347">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-347">Select **Save**.</span></span>
1. <span data-ttu-id="01d6c-348">Dans l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="01d6c-349">Dans l'éditeur de requêtes, dans l'onglet **Plage**, recherchez la ligne où le champ **Domaine** est défini sur *Emplacement*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="01d6c-350">Définissez le champ **Critères** de cette ligne sur *Porte baie*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="01d6c-351">Sélectionnez **OK** pour enregistrer vos paramètres et fermer l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="01d6c-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="01d6c-352">Définir des modèles de travail</span><span class="sxs-lookup"><span data-stu-id="01d6c-352">Set up work templates</span></span>

1. <span data-ttu-id="01d6c-353">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="01d6c-354">Modifiez la valeur du champ **Type d'ordre de travail** sur *Prélèvement de stock trié*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="01d6c-355">Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="01d6c-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="01d6c-356">Dans l'onglet **Vue d'ensemble**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-357">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="01d6c-358">**Modèle de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="01d6c-359">**Description du modèle de travail :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="01d6c-360">Sélectionnez **Enregistrer** pour rendre l'organisateur **Détails du modèle de travail** disponible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="01d6c-361">Dans l'organisateur **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne, puis définissez les valeurs suivantes pour celle-ci :</span><span class="sxs-lookup"><span data-stu-id="01d6c-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-362">**Type de travail :** *Choisir*</span><span class="sxs-lookup"><span data-stu-id="01d6c-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="01d6c-363">**ID classe de travail :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="01d6c-364">Sélectionnez à nouveau **Nouveau** pour ajouter une deuxième ligne, puis définissez les valeurs suivantes pour elle :</span><span class="sxs-lookup"><span data-stu-id="01d6c-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="01d6c-365">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="01d6c-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="01d6c-366">**ID classe de travail :** *TRI*</span><span class="sxs-lookup"><span data-stu-id="01d6c-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="01d6c-367">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="01d6c-368">Scénario</span><span class="sxs-lookup"><span data-stu-id="01d6c-368">Scenario</span></span>

<span data-ttu-id="01d6c-369">Ce scénario simule une situation dans laquelle les conteneurs emballés doivent être automatiquement triés vers différentes positions (palettes) après la station d'emballage, en fonction du service du transporteur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="01d6c-370">Une fois que tous les articles du chargement sont emballés et triés par adresse, les palettes seront déplacées vers la porte de la baie.</span><span class="sxs-lookup"><span data-stu-id="01d6c-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="01d6c-371">Créer des commandes client et des travaux de prélèvement</span><span class="sxs-lookup"><span data-stu-id="01d6c-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="01d6c-372">Créer une commande client 1</span><span class="sxs-lookup"><span data-stu-id="01d6c-372">Create sales order 1</span></span>

1. <span data-ttu-id="01d6c-373">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="01d6c-374">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-375">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="01d6c-376">**Compte client :** *US-005*</span><span class="sxs-lookup"><span data-stu-id="01d6c-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="01d6c-377">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="01d6c-378">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01d6c-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="01d6c-379">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="01d6c-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="01d6c-380">Basculez sur la vue **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="01d6c-381">Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="01d6c-382">**Transporteur :** *Fret aérien*</span><span class="sxs-lookup"><span data-stu-id="01d6c-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="01d6c-383">**Service de transporteur :** *Air*</span><span class="sxs-lookup"><span data-stu-id="01d6c-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="01d6c-384">Revenez à la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="01d6c-385">Si aucune nouvelle ligne n'est ajoutée automatiquement à la grille dans l'organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne** pour en ajouter une.</span><span class="sxs-lookup"><span data-stu-id="01d6c-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="01d6c-386">Dans la nouvelle ligne de commande, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="01d6c-387">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="01d6c-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="01d6c-388">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="01d6c-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="01d6c-389">Alors que la nouvelle ligne de commande est toujours sélectionnée dans l'organisateur **Lignes de commande client**, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="01d6c-390">Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="01d6c-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="01d6c-391">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="01d6c-392">Dans le volet Actions, sous l'onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="01d6c-393">Vous recevez un message d’information indiquant l’expédition et la vague de cette commande.</span><span class="sxs-lookup"><span data-stu-id="01d6c-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="01d6c-394">Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.</span><span class="sxs-lookup"><span data-stu-id="01d6c-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="01d6c-395">Commande client 2</span><span class="sxs-lookup"><span data-stu-id="01d6c-395">Sales order 2</span></span>

1. <span data-ttu-id="01d6c-396">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="01d6c-397">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="01d6c-398">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="01d6c-399">**Compte client :** *US-006*</span><span class="sxs-lookup"><span data-stu-id="01d6c-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="01d6c-400">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="01d6c-401">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01d6c-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="01d6c-402">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="01d6c-402">The new sales order is opened.</span></span> <span data-ttu-id="01d6c-403">Elle doit inclure une nouvelle ligne vide dans la grille de l'organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="01d6c-404">Sur cette ligne de commande, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="01d6c-405">**Article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="01d6c-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="01d6c-406">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="01d6c-407">Dans le raccourci **Détails de ligne**, sur l'onglet **Livraison**, définissez le champ **Mode de livraison** sur *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="01d6c-408">Dans l'organisateur **Lignes de commande client**, sélectionnez **Ajouter une ligne**, puis définissez les valeurs suivantes pour la deuxième ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="01d6c-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="01d6c-409">**Article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="01d6c-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="01d6c-410">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="01d6c-411">Dans le raccourci **Détails de ligne**, sur l'onglet **Livraison**, changez la valeur du champ **Mode de livraison** en *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="01d6c-412">Dans l'organisateur **Lignes de commande client**, sélectionnez la première ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="01d6c-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="01d6c-413">Ensuite, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="01d6c-414">Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="01d6c-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="01d6c-415">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="01d6c-416">Dans l'organisateur **Lignes de commande client**, sélectionnez la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="01d6c-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="01d6c-417">Ensuite, dans le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="01d6c-418">Sur la page **Réservation**, sélectionnez **Réserver un lot** pour réserver la quantité complète de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="01d6c-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="01d6c-419">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="01d6c-420">Dans le volet Actions, sous l'onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="01d6c-421">Vous recevez un message d’information indiquant l’expédition et la vague de cette commande.</span><span class="sxs-lookup"><span data-stu-id="01d6c-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="01d6c-422">Notez que deux numéros d'identification de vague et deux numéros d'identification d'expédition ont été créés, un pour chaque mode de livraison des lignes de commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="01d6c-423">Obtenir les ID de travail à partir des détails du travail</span><span class="sxs-lookup"><span data-stu-id="01d6c-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="01d6c-424">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="01d6c-425">La page affiche les ID de travail créés à partir des commandes client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="01d6c-426">Utilisez les ID de vague et les ID d'expédition des commandes client que vous avez créées pour trouver l'ID de travail de chaque vague et expédition.</span><span class="sxs-lookup"><span data-stu-id="01d6c-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="01d6c-427">Notez ces identificateurs de travail, car vous en aurez besoin dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="01d6c-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="01d6c-428">Notez que deux ID de travail ont été créés pour la deuxième commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="01d6c-429">Si différents articles sont sélectionnés à différents endroits, des ID sont générés avec des mots distincts.</span><span class="sxs-lookup"><span data-stu-id="01d6c-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="01d6c-430">Prélever des articles pour les commandes client</span><span class="sxs-lookup"><span data-stu-id="01d6c-430">Pick items for the sales orders</span></span>

<span data-ttu-id="01d6c-431">Terminez le travail créé en utilisant l'appareil mobile pour déplacer les articles vers la station d'emballage.</span><span class="sxs-lookup"><span data-stu-id="01d6c-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="01d6c-432">Sur l'appareil mobile, connectez-vous à l'entrepôt *62* en utilisant l'ID utilisateur que vous avez créé pour ce scénario (ou l'ID utilisateur d'un utilisateur de démonstration existant).</span><span class="sxs-lookup"><span data-stu-id="01d6c-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="01d6c-433">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="01d6c-434">Dans le menu **Sortant**, sélectionnez **Prélèvement des ventes**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="01d6c-435">Dans le champ **ID**, saisissez l'ID de travail qui a été créé pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="01d6c-436">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-436">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-437">Dans la page **Commandes client - Prélever**, entrez une LP cible qui a été créé pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="01d6c-438">Notez que l'emplacement du prélèvement (*bulk-001*), l'article (*A0001*) et la quantité (*2 pièces*) sont indiqués.</span><span class="sxs-lookup"><span data-stu-id="01d6c-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="01d6c-439">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-439">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-440">Examinez les informations sur la page **Commandes client - Placer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="01d6c-441">Le champ **Loc** doit indiquer que les articles sélectionnés vont à l'emplacement *Emballer*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="01d6c-442">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-442">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-443">Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ׃, qui indique que l'ID de travail de la commande client 1 est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="01d6c-444">Vous allez maintenant prélever la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="01d6c-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="01d6c-445">Dans le champ **ID**, saisissez l'ID de travail qui a été créé pour la commande client 2, où la ligne 1 comporte l'article *A0001*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="01d6c-446">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-446">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-447">Dans la page **Commandes client - Prélever**, entrez une LP cible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="01d6c-448">Notez que l'emplacement du prélèvement (*bulk-001*), l'article (*A0001*) et la quantité (*1 pièces*) sont indiqués.</span><span class="sxs-lookup"><span data-stu-id="01d6c-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="01d6c-449">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-449">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-450">Examinez les informations sur la page **Commandes client - Placer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="01d6c-451">Le champ **Loc** doit indiquer que les articles sélectionnés vont à l'emplacement *Emballer*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="01d6c-452">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-452">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-453">Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="01d6c-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="01d6c-454">Ce message indique que l'ID de travail de la ligne 1 de la commande client 2 est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="01d6c-455">Dans le champ **ID**, saisissez l'ID de travail qui a été créé pour la commande client 2, où la ligne 2 comporte l'article *A0002*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="01d6c-456">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-456">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-457">Dans la page **Commandes client - Prélever**, entrez une LP cible.</span><span class="sxs-lookup"><span data-stu-id="01d6c-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="01d6c-458">Notez que l'emplacement du prélèvement (*bulk-002*), l'article (*A0001*) et la quantité (*1 pièces*) sont indiqués.</span><span class="sxs-lookup"><span data-stu-id="01d6c-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="01d6c-459">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-459">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-460">Examinez les informations sur la page **Commandes client - Placer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="01d6c-461">Le champ **Loc** doit indiquer que les articles sélectionnés vont à l'emplacement *Emballer*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="01d6c-462">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-462">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-463">Dans la page **Scanner un ID de travail/ID de LP**, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="01d6c-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="01d6c-464">Ce message indique que l'ID de travail de la ligne 2 de la commande client 2 est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="01d6c-465">Emballer des commandes client dans des conteneurs</span><span class="sxs-lookup"><span data-stu-id="01d6c-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="01d6c-466">Emballer la commande client 1 dans des conteneurs</span><span class="sxs-lookup"><span data-stu-id="01d6c-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="01d6c-467">Accédez à **Gestion d'entrepôt \> Emballage et conteneurisation \> Emballer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="01d6c-468">La boîte de dialogue **Sélectionner une station de conditionnement** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="01d6c-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="01d6c-469">Par défaut, le champ **Employé** doit être défini sur le nom du travailleur que vous avez configuré précédemment.</span><span class="sxs-lookup"><span data-stu-id="01d6c-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="01d6c-470">Définissez les valeurs suivantes pour afficher et travailler sur les expéditions et les conteneurs qui sont planifiés à l'emplacement d'emballage concerné :</span><span class="sxs-lookup"><span data-stu-id="01d6c-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="01d6c-471">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="01d6c-471">**Site:** *6*</span></span>
    - <span data-ttu-id="01d6c-472">**Entrepôt :** *62*</span><span class="sxs-lookup"><span data-stu-id="01d6c-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="01d6c-473">**Emplacement :** *Emballer*</span><span class="sxs-lookup"><span data-stu-id="01d6c-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="01d6c-474">**ID du profil d'emballage :** *Tri*</span><span class="sxs-lookup"><span data-stu-id="01d6c-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="01d6c-475">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01d6c-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="01d6c-476">Dans la page **Emballer**, dans le champ **Contenant ou expédition**, saisissez la LP cible pour la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="01d6c-477">Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="01d6c-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="01d6c-478">Dans le volet Actions, sélectionnez **Nouveau conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="01d6c-479">Acceptez tous les paramètres par défaut et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="01d6c-480">Prenez note de l'ID du conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="01d6c-481">Dans l'organisateur **Emballage de l'article**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-482">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="01d6c-483">**Identificateur :** Article *A0001*</span><span class="sxs-lookup"><span data-stu-id="01d6c-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="01d6c-484">Dans le volet Actions, sélectionnez **Fermer le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="01d6c-485">Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="01d6c-486">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-486">Select **OK**.</span></span> <span data-ttu-id="01d6c-487">Le conteneur est déplacé vers l'emplacement *TRIER* et est prêt pour le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="01d6c-488">Créez un deuxième conteneur pour ajouter le deuxième article à partir de la LP de la commande client 1 à un nouveau conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="01d6c-489">Dans le volet Actions, sélectionnez **Nouveau conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="01d6c-490">Acceptez tous les paramètres par défaut et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="01d6c-491">Prenez note de l'ID du conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="01d6c-492">Dans l'organisateur **Emballage de l'article**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-493">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="01d6c-494">**Identificateur :** Article *A0001*</span><span class="sxs-lookup"><span data-stu-id="01d6c-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="01d6c-495">Dans le volet Actions, sélectionnez **Fermer le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="01d6c-496">Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="01d6c-497">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-497">Select **OK**.</span></span> <span data-ttu-id="01d6c-498">Le conteneur est déplacé vers l'emplacement *TRIER* et est prêt pour le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="01d6c-499">Emballer la commande client 2 dans des conteneurs</span><span class="sxs-lookup"><span data-stu-id="01d6c-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="01d6c-500">Dans la page **Emballer**, dans le champ **Contenant ou expédition**, saisissez la LP cible pour la ligne 1 de la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="01d6c-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="01d6c-501">Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="01d6c-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="01d6c-502">Dans le volet Actions, sélectionnez **Nouveau conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="01d6c-503">Acceptez tous les paramètres par défaut et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="01d6c-504">Prenez note de l'ID du conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="01d6c-505">Dans l'organisateur **Emballage de l'article**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-506">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="01d6c-507">**Identificateur :** Article *A0001*</span><span class="sxs-lookup"><span data-stu-id="01d6c-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="01d6c-508">Dans le volet Actions, sélectionnez **Fermer le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="01d6c-509">Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="01d6c-510">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-510">Select **OK**.</span></span> <span data-ttu-id="01d6c-511">Le conteneur est déplacé vers l'emplacement *TRIER* et est prêt pour le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="01d6c-512">Dans le champ **Contenant ou expédition**, saisissez la LP cible pour la ligne 2 de la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="01d6c-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="01d6c-513">Sélectionnez ensuite la touche **Tab** ou **Entrée** de votre clavier pour quitter le champ.</span><span class="sxs-lookup"><span data-stu-id="01d6c-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="01d6c-514">Dans le volet Actions, sélectionnez **Nouveau conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="01d6c-515">Acceptez tous les paramètres par défaut et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="01d6c-516">Prenez note de l'ID du conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="01d6c-517">Dans l'organisateur **Emballage de l'article**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="01d6c-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="01d6c-518">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="01d6c-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="01d6c-519">**Champ identificateur :** Article *A0002*</span><span class="sxs-lookup"><span data-stu-id="01d6c-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="01d6c-520">Dans le volet Actions, sélectionnez **Fermer le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="01d6c-521">Dans la boîte de dialogue **Fermer le conteneur**, sélectionnez **Obtenir le poids système** pour que le système mette à jour le champ **Poids brut**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="01d6c-522">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-522">Select **OK**.</span></span> <span data-ttu-id="01d6c-523">Le conteneur est déplacé vers l'emplacement *TRIER* et est prêt pour le tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="01d6c-524">Pour afficher les détails du conteneur, accédez à **Gestion d'entrepôt \> Emballage et conteneurisation \> Conteneurs** et recherchez les ID de conteneur créés lors de l'emballage.</span><span class="sxs-lookup"><span data-stu-id="01d6c-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="01d6c-525">Trier les conteneurs</span><span class="sxs-lookup"><span data-stu-id="01d6c-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01d6c-526">Lorsque vous accédez à l'élément de menu **Composition de palette** sur l'application mobile pour effectuer le tri sortant, vous voyez un bouton étiqueté **Complet**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="01d6c-527">*N'utilisez pas le bouton **Complet** pour trier ou fermer la position.*</span><span class="sxs-lookup"><span data-stu-id="01d6c-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="01d6c-528">Le bouton **Complet** est fourni par défaut et ne peut pas être désactivé ou supprimé de la page.</span><span class="sxs-lookup"><span data-stu-id="01d6c-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="01d6c-529">Il n'est pas utilisé pour la fonction *Tri sortant*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="01d6c-530">Trier le premier conteneur</span><span class="sxs-lookup"><span data-stu-id="01d6c-530">Sort the first container</span></span>

1. <span data-ttu-id="01d6c-531">Sur l'appareil mobile, connectez-vous à l'entrepôt *62* en utilisant l'ID utilisateur que vous avez créé pour ce scénario (ou l'ID utilisateur d'un utilisateur de démonstration existant).</span><span class="sxs-lookup"><span data-stu-id="01d6c-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="01d6c-532">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="01d6c-533">Dans le menu **Sortant**, sélectionnez **Composition de palette**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="01d6c-534">Dans le champ **LP/Cont**, entrez le premier ID de conteneur associé à la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="01d6c-535">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-535">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-536">Étant donné qu'aucune position de tri n'existe actuellement, vous devez en spécifier une.</span><span class="sxs-lookup"><span data-stu-id="01d6c-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="01d6c-537">Dans le champ **ID de position de tri**, entrez *SP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="01d6c-538">Comme aucune LP n'est actuellement associée à la position de tri *SP01*, vous devez en spécifier une.</span><span class="sxs-lookup"><span data-stu-id="01d6c-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="01d6c-539">Dans le champ **LP**, entrez *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="01d6c-540">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-540">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-541">La validation de la position de tri étant activée, vous devez saisir à nouveau l'ID de position de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="01d6c-542">Dans le champ **ID de position de tri**, entrez *SP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="01d6c-543">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-543">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-544">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="01d6c-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="01d6c-545">Pour afficher la position de tri et la LP qu'elle contient, accédez à **Gestion d'entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="01d6c-546">La page **Affectations de position de tri sortant** affiche toutes les positions de tri actuellement actives.</span><span class="sxs-lookup"><span data-stu-id="01d6c-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="01d6c-547">Le champ **Transactions de positions de tri** affiche la LP associée à chaque position de tri et les conteneurs qui se trouvent à la position de tri.</span><span class="sxs-lookup"><span data-stu-id="01d6c-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="01d6c-548">Notez qu'une position de tri existe actuellement et que l'organisateur **Critères de position de tri** affiche un critère **Expédition - Service de transporteur - Aérien**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="01d6c-549">Trier les conteneurs restants</span><span class="sxs-lookup"><span data-stu-id="01d6c-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="01d6c-550">Sur l'appareil mobile, connectez-vous à l'entrepôt *62* en utilisant l'ID utilisateur que vous avez créé pour ce scénario (ou l'ID utilisateur d'un utilisateur de démonstration existant).</span><span class="sxs-lookup"><span data-stu-id="01d6c-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="01d6c-551">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="01d6c-552">Dans le menu **Sortant**, sélectionnez **Composition de palette**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="01d6c-553">Dans le champ **LP/Cont**, entrez le deuxième ID de conteneur associé à la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="01d6c-554">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-554">Select **OK**.</span></span> <span data-ttu-id="01d6c-555">Étant donné que le modèle de tri est configuré pour trier automatiquement et qu'une position de tri comportant des critères correspondants existe déjà, vous êtes automatiquement dirigé vers la position de tri correcte.</span><span class="sxs-lookup"><span data-stu-id="01d6c-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="01d6c-556">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-556">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-557">Confirmez l'ID de la position de tri pour indiquer que le stock est au bon endroit.</span><span class="sxs-lookup"><span data-stu-id="01d6c-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="01d6c-558">Dans le champ **ID de position de tri**, entrez *SP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="01d6c-559">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-559">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-560">Le travail est terminé sur le deuxième conteneur de la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="01d6c-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="01d6c-561">Vous allez maintenant trier les conteneurs restants de la commande client 2.</span><span class="sxs-lookup"><span data-stu-id="01d6c-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="01d6c-562">Dans le champ **LP/Cont**, saisissez l'ID de conteneur du conteneur de la commande client 2 qui contient l'article *A0001*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="01d6c-563">Étant donné que le service de transporteur diffère, vous êtes invité à entrer une nouvelle position de tri et à affecter une LP à cette position.</span><span class="sxs-lookup"><span data-stu-id="01d6c-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="01d6c-564">Utilisez la position de tri *SP02* et la LP *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="01d6c-565">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-565">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-566">Confirmez la position de tri en saisissant *SP02* dans le champ **ID de position de tri**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="01d6c-567">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-567">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-568">Le travail est terminé sur le conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="01d6c-569">Dans le champ **LP/Cont**, saisissez l'ID de conteneur pour le conteneur restant de la commande client 2 qui contient l'article *A0002*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="01d6c-570">Étant donné que le service de transporteur est le même que pour la commande client 1, le système affiche la position de tri existante qui a des critères correspondants.</span><span class="sxs-lookup"><span data-stu-id="01d6c-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="01d6c-571">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-571">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-572">Confirmez la position de tri en saisissant *SP01* dans le champ **ID de position de tri**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="01d6c-573">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-573">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-574">Le travail est terminé sur le conteneur.</span><span class="sxs-lookup"><span data-stu-id="01d6c-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="01d6c-575">Fermer les positions de tri sortant</span><span class="sxs-lookup"><span data-stu-id="01d6c-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="01d6c-576">Lorsque tout le stock a été trié, la position doit être fermée avant que le travail ne puisse être créé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="01d6c-577">Un travail de prélèvement du stock trié sera créé pour apporter le stock à la porte de la baie.</span><span class="sxs-lookup"><span data-stu-id="01d6c-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="01d6c-578">Fermer une position depuis l'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="01d6c-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="01d6c-579">Sur l'appareil mobile, connectez-vous à l'entrepôt *62* en utilisant l'ID utilisateur que vous avez créé pour ce scénario (ou l'ID utilisateur d'un utilisateur de démonstration existant).</span><span class="sxs-lookup"><span data-stu-id="01d6c-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="01d6c-580">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="01d6c-581">Dans le menu **Sortant**, sélectionnez **Composition de palette**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="01d6c-582">Dans le champ **LP/Cont**, entrez un ID de conteneur qui a été trié pour trier la position *SP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="01d6c-583">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-583">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-584">Le message suivant s'affiche : « Le conteneur est déjà trié à la position SP01.</span><span class="sxs-lookup"><span data-stu-id="01d6c-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="01d6c-585">Fermer la position ? »</span><span class="sxs-lookup"><span data-stu-id="01d6c-585">Close the position?"</span></span> <span data-ttu-id="01d6c-586">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-586">Select **Close**.</span></span>

    <span data-ttu-id="01d6c-587">Le travail est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="01d6c-588">Fermer une position à partir des affectations de position de tri sortant</span><span class="sxs-lookup"><span data-stu-id="01d6c-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="01d6c-589">Accédez à **Gestion d'entrepôt \> Emballage et conteneurisation \> Affectations de position de tri sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="01d6c-590">Dans la colonne de gauche, sélectionnez **SP02**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="01d6c-591">Cette ligne de position de tri sortant est celle que vous fermerez.</span><span class="sxs-lookup"><span data-stu-id="01d6c-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="01d6c-592">Dans le volet Actions, sélectionnez **Fermer la position**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="01d6c-593">L'enregistrement de position de tri est fermé et n'est plus affiché.</span><span class="sxs-lookup"><span data-stu-id="01d6c-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="01d6c-594">Pour afficher tous les enregistrements de positions fermées, cochez la case **Afficher fermées**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="01d6c-595">Prélèvement du stock trié</span><span class="sxs-lookup"><span data-stu-id="01d6c-595">Sorted inventory picking</span></span>

<span data-ttu-id="01d6c-596">Vous devez terminer le travail de prélèvement du stock trié.</span><span class="sxs-lookup"><span data-stu-id="01d6c-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="01d6c-597">Une fois terminé, le stock sera prélevé vers la commande client.</span><span class="sxs-lookup"><span data-stu-id="01d6c-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="01d6c-598">À ce stade, tous les autres processus d'entrepôt s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="01d6c-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="01d6c-599">Sur l'appareil mobile, connectez-vous à l'entrepôt *62* en utilisant l'ID utilisateur que vous avez créé pour ce scénario (ou l'ID utilisateur d'un utilisateur de démonstration existant).</span><span class="sxs-lookup"><span data-stu-id="01d6c-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="01d6c-600">Dans le menu principal, sélectionnez **Sortant**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="01d6c-601">Dans le menu **Sortant**, sélectionnez **Charger à partir du tri**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="01d6c-602">Entrez l'ID de la LP cible à partir de la première position de tri, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="01d6c-603">Définissez le champ **ID** sur *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="01d6c-604">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-604">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-605">La page **Prélèvement de stock trié : Prélever** affiche le travail de prélèvement qui doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="01d6c-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="01d6c-606">Choisissez l'emplacement *TRIER* et la LP cible *PLP01*, qui comporte plusieurs articles et une quantité de *3*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="01d6c-607">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-607">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-608">La page **Prélèvement de stock trié : Placer** affiche le travail de placement qui doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="01d6c-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="01d6c-609">Choisissez l'emplacement *Porte baie* et la LP cible *PLP01*, qui comporte plusieurs articles et une quantité de *3*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="01d6c-610">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-610">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-611">Le travail est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-611">Work is completed.</span></span>

1. <span data-ttu-id="01d6c-612">Entrez l'ID du contenant cible à partir de la deuxième position de tri, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="01d6c-613">Définissez le champ **ID** sur *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="01d6c-614">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-614">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-615">La page **Prélèvement de stock trié : Prélever** affiche le travail de prélèvement qui doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="01d6c-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="01d6c-616">Choisissez l'emplacement *TRIER* et la LP cible *PLP02*, qui comporte plusieurs articles et une quantité de *1*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="01d6c-617">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-617">Select **OK**.</span></span>
1. <span data-ttu-id="01d6c-618">La page **Prélèvement de stock trié : Placer** affiche le travail de placement qui doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="01d6c-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="01d6c-619">Choisissez l'emplacement *Porte baie* et la LP cible *PLP02*, qui comporte plusieurs articles et une quantité de *1*.</span><span class="sxs-lookup"><span data-stu-id="01d6c-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="01d6c-620">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="01d6c-620">Select **OK**.</span></span>

    <span data-ttu-id="01d6c-621">Le travail est terminé.</span><span class="sxs-lookup"><span data-stu-id="01d6c-621">Work is completed.</span></span>

<span data-ttu-id="01d6c-622">À partir de ce stade, tous les autres processus d'entrepôt s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="01d6c-622">From this point forward, all other warehouse processes apply.</span></span>