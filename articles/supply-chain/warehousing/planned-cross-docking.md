---
title: Cross-docking planifié
description: Cette rubrique décrit le cross-docking planifié avancé, où la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d’expédition ou la zone de transit correct. L’ensemble du stock restant de la source entrante est envoyé vers l’emplacement de stockage correct via le processus de rangement normal.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 722b004e607cb2e6b7de292d92b67b18c2024696
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556264"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="6003e-104">Cross-docking planifié</span><span class="sxs-lookup"><span data-stu-id="6003e-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6003e-105">Cette rubrique décrit le cross-docking planifié avancé.</span><span class="sxs-lookup"><span data-stu-id="6003e-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="6003e-106">Le cross-docking est un processus d’entrepôt dans lequel la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d’expédition ou la zone de transit correct.</span><span class="sxs-lookup"><span data-stu-id="6003e-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="6003e-107">L’ensemble du stock restant de la source entrante est envoyé vers l’emplacement de stockage correct via le processus de rangement normal.</span><span class="sxs-lookup"><span data-stu-id="6003e-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="6003e-108">Le cross-docking permet aux employés d’ignorer le rangement entrant et le prélèvement de stock sortant qui est déjà marqué pour une commande sortante.</span><span class="sxs-lookup"><span data-stu-id="6003e-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="6003e-109">Par conséquent, la fréquence d’utilisation du stock est limitée, si possible.</span><span class="sxs-lookup"><span data-stu-id="6003e-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="6003e-110">De plus, comme il y a moins d’interaction avec le système, les gains de temps et d’espace dans l’atelier sont augmentés.</span><span class="sxs-lookup"><span data-stu-id="6003e-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="6003e-111">Avant de pouvoir exécuter le cross-docking, l’utilisateur doit configurer un nouveau modèle de cross-docking dans lequel la source d’approvisionnement et d’autres exigences de cross-docking sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="6003e-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="6003e-112">Lorsque la commande sortante est créée, la ligne doit être marquée par rapport à une commande entrante contenant le même article.</span><span class="sxs-lookup"><span data-stu-id="6003e-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="6003e-113">Au moment de la réception de la commande entrante, la configuration du cross-docking identifie automatiquement la nécessité de cross-docking et crée le travail de mouvement pour la quantité requise en fonction de la configuration de l’instruction d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6003e-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="6003e-114">L’enregistrement des transactions de stock **n’est pas** annulé lorsque le travail de cross-docking est annulé, même si le paramètre de cette fonctionnalité est activé dans les paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="6003e-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="6003e-115">Activer les fonctionnalités Cross-docking planifiées</span><span class="sxs-lookup"><span data-stu-id="6003e-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="6003e-116">Si votre système n’inclut pas déjà les fonctionnalités décrites dans cette rubrique, accédez à [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez les fonctionnalités suivantes dans l’ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="6003e-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="6003e-117">*Cross-docking planifié*</span><span class="sxs-lookup"><span data-stu-id="6003e-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="6003e-118">*Modèles de cross-docking avec instructions d’emplacement*</span><span class="sxs-lookup"><span data-stu-id="6003e-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="6003e-119">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="6003e-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="6003e-120">Régénérer les méthodes de validation du chargement</span><span class="sxs-lookup"><span data-stu-id="6003e-120">Regenerate load posting methods</span></span>

<span data-ttu-id="6003e-121">Le cross-docking planifié est implémenté en tant que méthode de validation du chargement.</span><span class="sxs-lookup"><span data-stu-id="6003e-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="6003e-122">Après avoir activé la fonctionnalité, vous devez régénérer les méthodes.</span><span class="sxs-lookup"><span data-stu-id="6003e-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="6003e-123">Allez dans **Gestion des entrepôts \> Paramétrage \> Méthode de validation du chargement**.</span><span class="sxs-lookup"><span data-stu-id="6003e-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="6003e-124">Dans le volet Actions, sélectionnez **Régénérer des méthodes**.</span><span class="sxs-lookup"><span data-stu-id="6003e-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="6003e-125">Une fois la régénération terminée, vous devriez voir une méthode dont la valeur **Nom de la méthode** est *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="6003e-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="6003e-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6003e-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="6003e-127">Créer une modèle de cross-docking</span><span class="sxs-lookup"><span data-stu-id="6003e-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="6003e-128">Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de cross-docking**.</span><span class="sxs-lookup"><span data-stu-id="6003e-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="6003e-129">Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="6003e-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="6003e-130">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="6003e-131">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="6003e-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="6003e-132">Ce champ définit l’ordre d’évaluation des modèles.</span><span class="sxs-lookup"><span data-stu-id="6003e-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="6003e-133">**ID du modèle de cross-docking :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="6003e-134">**Description :** *Entrepôt 51*</span><span class="sxs-lookup"><span data-stu-id="6003e-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="6003e-135">**Stratégie de libération de la demande :** *Avant la réception de l’approvisionnement*</span><span class="sxs-lookup"><span data-stu-id="6003e-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="6003e-136">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6003e-137">La configuration de l’organisateur **Planification** contrôle le fonctionnement du modèle.</span><span class="sxs-lookup"><span data-stu-id="6003e-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="6003e-138">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-138">Set the following values:</span></span>

    - <span data-ttu-id="6003e-139">**Exigences de la demande :** *Aucun*</span><span class="sxs-lookup"><span data-stu-id="6003e-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="6003e-140">Ce champ définit les exigences de l’inventaire de la demande.</span><span class="sxs-lookup"><span data-stu-id="6003e-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="6003e-141">Si la demande doit être liée à l’approvisionnement avant la libération, sélectionnez *Marquage*.</span><span class="sxs-lookup"><span data-stu-id="6003e-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="6003e-142">Si la demande doit être réservée sur commande par rapport à l’approvisionnement avant la libération, sélectionnez *Réservation de commande*.</span><span class="sxs-lookup"><span data-stu-id="6003e-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="6003e-143">**Type d’emplacement :** *Emplacements d’expédition*</span><span class="sxs-lookup"><span data-stu-id="6003e-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="6003e-144">Ce champ définit si le travail de cross-docking doit utiliser les emplacements intermédiaires/de chargement de l’expédition ou s’il doit utiliser les instructions d’emplacement pour trouver ses propres emplacements intermédiaires/de chargement.</span><span class="sxs-lookup"><span data-stu-id="6003e-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="6003e-145">**Modèle de travail :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="6003e-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="6003e-146">Ce champ définit le modèle de travail à utiliser lors de la création d’un travail de cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6003e-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="6003e-147">**Revalider à la réception de l’approvisionnement :** *Non*</span><span class="sxs-lookup"><span data-stu-id="6003e-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="6003e-148">Cette option définit si l’approvisionnement doit être revalidé à la réception.</span><span class="sxs-lookup"><span data-stu-id="6003e-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="6003e-149">Si cette option est définie sur *Oui*, l’intervalle de temps maximum et la plage de jours d’expiration sont cochés.</span><span class="sxs-lookup"><span data-stu-id="6003e-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="6003e-150">**Code directif** Laissez ce champ vide</span><span class="sxs-lookup"><span data-stu-id="6003e-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="6003e-151">Cette option permet au système d’utiliser des directives d’emplacement pour aider à déterminer le meilleur emplacement vers lequel déplacer l’inventaire de cross-docking.</span><span class="sxs-lookup"><span data-stu-id="6003e-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="6003e-152">Vous pouvez le configurer en attribuant un code de directive à chaque modèle de cross-docking pertinent.</span><span class="sxs-lookup"><span data-stu-id="6003e-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="6003e-153">Chaque code de directive identifie une directive d’emplacement unique.</span><span class="sxs-lookup"><span data-stu-id="6003e-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="6003e-154">**Valider l’intervalle de temps :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="6003e-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="6003e-155">Cette option définit si l’intervalle de temps maximum doit être évalué lorsqu’une source d’approvisionnement est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6003e-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="6003e-156">Si cette option est définie sur *Oui*, les champs liés aux intervalles de temps maximum et minimum deviennent disponibles.</span><span class="sxs-lookup"><span data-stu-id="6003e-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="6003e-157">**Intervalle de temps maximum :** *5*</span><span class="sxs-lookup"><span data-stu-id="6003e-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="6003e-158">Ce champ définit la période maximum autorisée entre l’arrivée de l’approvisionnement et le départ de la demande.</span><span class="sxs-lookup"><span data-stu-id="6003e-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="6003e-159">**Unité d’intervalle de temps maximum :** *Jours*</span><span class="sxs-lookup"><span data-stu-id="6003e-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="6003e-160">**Intervalle de temps minimum :** *0*</span><span class="sxs-lookup"><span data-stu-id="6003e-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="6003e-161">Ce champ définit la période minimum autorisée entre l’arrivée de l’approvisionnement et le départ de la demande.</span><span class="sxs-lookup"><span data-stu-id="6003e-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="6003e-162">**Unité d’intervalle de temps minimum :** *Jours*</span><span class="sxs-lookup"><span data-stu-id="6003e-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="6003e-163">**Plage de jours d’expiration :** *0*</span><span class="sxs-lookup"><span data-stu-id="6003e-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="6003e-164">*Critères FEFO :* Ce champ définit le nombre maximum de jours entre la date d’expiration du traitement par lots arrivant le premier à expiration actuellement dans l’entrepôt et le traitement par lots en cours de réception.</span><span class="sxs-lookup"><span data-stu-id="6003e-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="6003e-165">Dans l’organisateur **Sources d’approvisionnement**, vous spécifiez les types d’approvisionnement valides pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="6003e-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="6003e-166">Sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="6003e-167">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="6003e-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6003e-168">**Source d’approvisionnement :** *Commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="6003e-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="6003e-169">Créer une classe de travail</span><span class="sxs-lookup"><span data-stu-id="6003e-169">Create a work class</span></span>

1. <span data-ttu-id="6003e-170">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="6003e-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="6003e-171">Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe de travail.</span><span class="sxs-lookup"><span data-stu-id="6003e-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="6003e-172">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-172">Set the following values:</span></span>

    - <span data-ttu-id="6003e-173">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6003e-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="6003e-174">**Description :** *Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="6003e-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="6003e-175">**Type d’ordre de travail :** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="6003e-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="6003e-176">Créer un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="6003e-176">Create a work template</span></span>

1. <span data-ttu-id="6003e-177">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="6003e-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="6003e-178">Définissez le champ **Type d’ordre de travail** sur *Cross docking*.</span><span class="sxs-lookup"><span data-stu-id="6003e-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="6003e-179">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à l’onglet **Vue d’ensemble**.</span><span class="sxs-lookup"><span data-stu-id="6003e-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="6003e-180">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6003e-181">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="6003e-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6003e-182">**Modèle de travail :** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="6003e-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="6003e-183">**Description du modèle de travail :** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="6003e-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="6003e-184">Sélectionnez **Enregistrer** pour rendre l’organisateur **Détails du modèle de travail** disponible.</span><span class="sxs-lookup"><span data-stu-id="6003e-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="6003e-185">Dans l’organisateur **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="6003e-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6003e-186">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6003e-187">**Type de travail :** *Choisir*</span><span class="sxs-lookup"><span data-stu-id="6003e-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="6003e-188">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6003e-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="6003e-189">Sélectionnez **Nouveau** pour ajouter une autre ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="6003e-190">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="6003e-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6003e-191">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6003e-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="6003e-192">Sélectionnez **Enregistrer** et confirmez que la case **Valide** est cochée pour le modèle *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="6003e-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="6003e-193">Les ID de classe de travail pour les types de travail *Prélever* et *Placer* doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="6003e-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="6003e-194">Créer des instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="6003e-194">Create location directives</span></span>

1. <span data-ttu-id="6003e-195">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="6003e-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6003e-196">Dans le volet gauche, définissez le champ **Type d’ordre de travail** sur *Cross docking*.</span><span class="sxs-lookup"><span data-stu-id="6003e-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="6003e-197">Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="6003e-198">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="6003e-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6003e-199">**Nom :** *51 Cross Dock Put*</span><span class="sxs-lookup"><span data-stu-id="6003e-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="6003e-200">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="6003e-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="6003e-201">**Site :** *5*</span><span class="sxs-lookup"><span data-stu-id="6003e-201">**Site:** *5*</span></span>
    - <span data-ttu-id="6003e-202">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6003e-203">Sélectionnez **Enregistrer** pour rendre l’organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="6003e-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="6003e-204">Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="6003e-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6003e-205">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6003e-206">**Quantité de départ :** *1*</span><span class="sxs-lookup"><span data-stu-id="6003e-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="6003e-207">**Quantité d’arrivée :** *1000000*</span><span class="sxs-lookup"><span data-stu-id="6003e-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="6003e-208">Sélectionnez **Enregistrer** pour rendre l’organisateur **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="6003e-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="6003e-209">Dans l’organisateur **Actions d’instruction d’emplacement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="6003e-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6003e-210">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6003e-211">**Nom :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="6003e-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="6003e-212">**Utilisation d’un emplacement fixe :** *Emplacements fixes et non fixes*</span><span class="sxs-lookup"><span data-stu-id="6003e-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="6003e-213">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de la barre d’outils **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="6003e-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="6003e-214">Sélectionnez **Modifier la requête** pour ouvrir l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6003e-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="6003e-215">Sous l’onglet **Plage**, assurez-vous que les deux lignes suivantes sont configurées :</span><span class="sxs-lookup"><span data-stu-id="6003e-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="6003e-216">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="6003e-216">Line 1:</span></span>

        - <span data-ttu-id="6003e-217">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="6003e-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="6003e-218">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="6003e-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="6003e-219">**Champ :** *Entrepôt*</span><span class="sxs-lookup"><span data-stu-id="6003e-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="6003e-220">**Critères :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="6003e-221">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="6003e-221">Line 2:</span></span>

        - <span data-ttu-id="6003e-222">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="6003e-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="6003e-223">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="6003e-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="6003e-224">**Champ :** *Emplacement*</span><span class="sxs-lookup"><span data-stu-id="6003e-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="6003e-225">**Critères :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="6003e-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="6003e-226">Cliquez sur **OK** pour fermer l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="6003e-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="6003e-227">Créer une option de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="6003e-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="6003e-228">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="6003e-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6003e-229">Dans la liste des éléments de menu du volet gauche, sélectionnez **Rangement d’achat**.</span><span class="sxs-lookup"><span data-stu-id="6003e-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="6003e-230">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6003e-230">Select **Edit**.</span></span>
1. <span data-ttu-id="6003e-231">Dans l’organisateur **Classes de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="6003e-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6003e-232">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6003e-233">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="6003e-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="6003e-234">**Type d’ordre de travail :** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="6003e-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="6003e-235">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6003e-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="6003e-236">Scénario</span><span class="sxs-lookup"><span data-stu-id="6003e-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="6003e-237">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="6003e-237">Create a purchase order</span></span>

<span data-ttu-id="6003e-238">Suivez les étapes ci-après pour créer une commande fournisseur comme source d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="6003e-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="6003e-239">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6003e-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="6003e-240">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6003e-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6003e-241">Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6003e-242">**Compte fournisseur :** *104*</span><span class="sxs-lookup"><span data-stu-id="6003e-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="6003e-243">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6003e-244">Cliquez sur **OK** et prenez note du numéro de commande.</span><span class="sxs-lookup"><span data-stu-id="6003e-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="6003e-245">Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="6003e-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="6003e-246">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="6003e-247">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6003e-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6003e-248">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="6003e-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="6003e-249">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="6003e-249">Create a sales order</span></span>

<span data-ttu-id="6003e-250">Suivez les étapes ci-après pour créer une commande client comme source de demande.</span><span class="sxs-lookup"><span data-stu-id="6003e-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="6003e-251">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="6003e-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6003e-252">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6003e-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6003e-253">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6003e-254">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="6003e-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="6003e-255">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="6003e-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6003e-256">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-256">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-257">Une nouvelle ligne est ajoutée à l’organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="6003e-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6003e-258">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="6003e-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="6003e-259">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6003e-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6003e-260">**Quantité :** *3*</span><span class="sxs-lookup"><span data-stu-id="6003e-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="6003e-261">Créer le cross-docking planifié</span><span class="sxs-lookup"><span data-stu-id="6003e-261">Create planned cross-docking</span></span>

<span data-ttu-id="6003e-262">Suivez les étapes ci-après pour créer le cross-docking planifié à partir de la commande client.</span><span class="sxs-lookup"><span data-stu-id="6003e-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="6003e-263">Dans la page **Détails de la commande client** de la commande client que vous venez de créer, dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="6003e-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="6003e-264">L’action de libération dans l’entrepôt crée une ligne d’expédition et de chargement pour la ligne de commande client et tente d’allouer le stock.</span><span class="sxs-lookup"><span data-stu-id="6003e-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="6003e-265">Vous recevez un message d’information.</span><span class="sxs-lookup"><span data-stu-id="6003e-265">You receive an informational message.</span></span> <span data-ttu-id="6003e-266">Vous recevez également le message d’avertissement suivant : « Aucun travail n’a été créé pour la vague XXXX.</span><span class="sxs-lookup"><span data-stu-id="6003e-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="6003e-267">Pour plus de détails, consultez le journal historique de création de travail. »</span><span class="sxs-lookup"><span data-stu-id="6003e-267">See the work creation history log for details."</span></span> <span data-ttu-id="6003e-268">Ce comportement est attendu, car il n’y a pas de stock dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="6003e-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="6003e-269">Dans l’organisateur **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails de l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="6003e-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="6003e-270">La page **Détails de l’expédition** apparaît et affiche l’expédition créée pour la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="6003e-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="6003e-271">Dans l’organisateur **Lignes de chargement**, notez que le champ **Quantité de cross docking planifié** est défini sur *3*.</span><span class="sxs-lookup"><span data-stu-id="6003e-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="6003e-272">Étant donné qu’aucun stock n’était disponible dans l’entrepôt, mais une source d’approvisionnement valide arrivera dans l’intervalle de temps défini dans le modèle de cross-docking, la quantité de cross-docking a été créée.</span><span class="sxs-lookup"><span data-stu-id="6003e-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="6003e-273">Dans l’organisateur **Lignes de chargement**, sélectionnez **Cross docking planifié** pour afficher les détails du cross-docking créé.</span><span class="sxs-lookup"><span data-stu-id="6003e-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="6003e-274">Traiter le cross-docking</span><span class="sxs-lookup"><span data-stu-id="6003e-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="6003e-275">Réception de commande fournisseur sur l’application mobile d’entreposage</span><span class="sxs-lookup"><span data-stu-id="6003e-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="6003e-276">Le système recevra la quantité de 5 de la commande fournisseur dans l’emplacement de réception et créera deux travaux.</span><span class="sxs-lookup"><span data-stu-id="6003e-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="6003e-277">Le premier ID de travail créé a une valeur **Type d’ordre de travail** de *Cross docking* et est lié à la commande client.</span><span class="sxs-lookup"><span data-stu-id="6003e-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="6003e-278">Sa quantité est 3 et il est envoyé vers l’emplacement d’expédition finale afin de pouvoir être expédié immédiatement.</span><span class="sxs-lookup"><span data-stu-id="6003e-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="6003e-279">Le deuxième ID de travail créé a une valeur **Type d’ordre de travail** de *Commandes fournisseur* et est lié à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6003e-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="6003e-280">Sa quantité restante est 2 et n’a pas fait l’objet d’un cross docking. Il est envoyé pour rangement dans l’emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="6003e-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="6003e-281">Connectez-vous à l’appareil mobile en tant qu’utilisateur dans l’entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="6003e-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="6003e-282">Allez à **Entrant \> Réception d’achat**.</span><span class="sxs-lookup"><span data-stu-id="6003e-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="6003e-283">Dans le champ **PONum**, entrez votre numéro de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6003e-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="6003e-284">Dans le champ **Qté**, entrez *5*.</span><span class="sxs-lookup"><span data-stu-id="6003e-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="6003e-285">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-285">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-286">Dans la page suivante, définissez le champ **Article** sur *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6003e-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="6003e-287">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-287">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-288">Dans la page suivante, confirmez les valeurs **PONum**, **Article** et **Qté** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="6003e-289">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="6003e-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="6003e-290">Sélectionnez **Annuler** pour quitter.</span><span class="sxs-lookup"><span data-stu-id="6003e-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="6003e-291">Ranger dans le cross-docking et en bloc</span><span class="sxs-lookup"><span data-stu-id="6003e-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="6003e-292">Actuellement, les deux ID de travail ont le même contenant cible.</span><span class="sxs-lookup"><span data-stu-id="6003e-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="6003e-293">Pour effectuer les étapes suivantes, vous devez obtenir l’ID de travail et l’ID de contenant cible.</span><span class="sxs-lookup"><span data-stu-id="6003e-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="6003e-294">Vous pouvez obtenir ces informations à partir des détails du travail de la ligne de commande fournisseur et de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="6003e-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="6003e-295">Vous pouvez également aller dans **Gestion des entrepôts \> Travail \> Détails du travail** et filtrer le travail où la valeur **Entrepôt** est *51*.</span><span class="sxs-lookup"><span data-stu-id="6003e-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="6003e-296">Sur l’appareil mobile, accédez à **Entrant \> Rangement d’achat** et entrez le contenant cible à partir du travail.</span><span class="sxs-lookup"><span data-stu-id="6003e-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="6003e-297">Dans le champ **ID**, entrez l’ID de contenant cible à partir des détails du travail.</span><span class="sxs-lookup"><span data-stu-id="6003e-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="6003e-298">La page de prélèvement du cross-docking indique l’emplacement de prélèvement (*RECV*), le contenant cible (*contenant*), l’article (*A0001*) et la quantité (*3*).</span><span class="sxs-lookup"><span data-stu-id="6003e-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="6003e-299">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-299">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-300">Dans le champ **Contenant cible**, entrez un contenant cible pour l’ID de contenant qui doit être placé (faire l’objet d’un cross-docking) dans l’emplacement d’expédition.</span><span class="sxs-lookup"><span data-stu-id="6003e-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="6003e-301">Vous pouvez sélectionner n’importe quel ID de contenant de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6003e-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="6003e-302">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-302">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-303">Dans la page suivante, dans le champ **ID**, entrez l’ID de contenant cible.</span><span class="sxs-lookup"><span data-stu-id="6003e-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="6003e-304">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-304">Select **OK**.</span></span>
1. <span data-ttu-id="6003e-305">Confirmez le travail de prélèvement de la quantité restante de 2, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="6003e-306">Dans la page suivante, sélectionnez **Terminé** pour terminer le processus de prélèvement et commencer le processus de rangement.</span><span class="sxs-lookup"><span data-stu-id="6003e-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="6003e-307">L’application mobile vous présente l’emplacement et le contenant dans lesquels placer l’article.</span><span class="sxs-lookup"><span data-stu-id="6003e-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="6003e-308">Confirmez le stockage en bloc **Placer** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="6003e-309">Dans la page suivante, confirmez le cross-docking **Placer** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6003e-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="6003e-310">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="6003e-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="6003e-311">Sélectionnez **Annuler** pour quitter.</span><span class="sxs-lookup"><span data-stu-id="6003e-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="6003e-312">L’illustration suivante montre comment le travail de cross-docking terminé peut apparaître dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6003e-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="6003e-313">![Travail de cross-docking terminé](media/PlannedCrossDockingWork.png "Travail de cross-docking terminé")</span><span class="sxs-lookup"><span data-stu-id="6003e-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]