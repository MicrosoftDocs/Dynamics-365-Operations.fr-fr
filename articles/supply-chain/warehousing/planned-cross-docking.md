---
title: Cross-docking planifié
description: Cette rubrique décrit le cross-docking planifié avancé, où la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d'expédition ou la zone de transit correct. L'ensemble du stock restant de la source entrante est envoyé vers l'emplacement de stockage correct via le processus de rangement normal.
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
ms.openlocfilehash: fb598b3ac7dd72e8c500f0c2eaf07462009c67f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970304"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="0e6e1-104">Cross-docking planifié</span><span class="sxs-lookup"><span data-stu-id="0e6e1-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e6e1-105">Cette rubrique décrit le cross-docking planifié avancé.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="0e6e1-106">Le cross-docking est un processus d'entrepôt dans lequel la quantité de stock requise pour une commande est envoyée directement de la réception ou la création vers le quai d'expédition ou la zone de transit correct.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="0e6e1-107">L'ensemble du stock restant de la source entrante est envoyé vers l'emplacement de stockage correct via le processus de rangement normal.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="0e6e1-108">Le cross-docking permet aux employés d'ignorer le rangement entrant et le prélèvement de stock sortant qui est déjà marqué pour une commande sortante.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="0e6e1-109">Par conséquent, la fréquence d'utilisation du stock est limitée, si possible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="0e6e1-110">De plus, comme il y a moins d'interaction avec le système, les gains de temps et d'espace dans l'atelier sont augmentés.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="0e6e1-111">Avant de pouvoir exécuter le cross-docking, l'utilisateur doit configurer un nouveau modèle de cross-docking dans lequel la source d'approvisionnement et d'autres exigences de cross-docking sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="0e6e1-112">Lorsque la commande sortante est créée, la ligne doit être marquée par rapport à une commande entrante contenant le même article.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="0e6e1-113">Au moment de la réception de la commande entrante, la configuration du cross-docking identifie automatiquement la nécessité de cross-docking et crée le travail de mouvement pour la quantité requise en fonction de la configuration de l'instruction d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="0e6e1-114">L'enregistrement des transactions de stock **n'est pas** annulé lorsque le travail de cross-docking est annulé, même si le paramètre de cette fonctionnalité est activé dans les paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-feature"></a><span data-ttu-id="0e6e1-115">Activer la fonctionnalité Cross-docking planifié</span><span class="sxs-lookup"><span data-stu-id="0e6e1-115">Turn on the Planned cross docking feature</span></span>

<span data-ttu-id="0e6e1-116">Avant de pouvoir utiliser le cross-docking planifié avancé, la fonctionnalité doit être activée dans votre système.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-116">Before you can use advanced planned cross-docking, the feature must be turned on in your system.</span></span> <span data-ttu-id="0e6e1-117">Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="0e6e1-118">Là, la fonctionnalité est répertoriée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="0e6e1-119">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="0e6e1-120">**Nom de la fonctionnalité :** *Cross-docking planifié*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-120">**Feature name:** *Planned cross docking*</span></span>

## <a name="setup"></a><span data-ttu-id="0e6e1-121">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="0e6e1-121">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="0e6e1-122">Régénérer les méthodes de validation du chargement</span><span class="sxs-lookup"><span data-stu-id="0e6e1-122">Regenerate load posting methods</span></span>

<span data-ttu-id="0e6e1-123">Le cross-docking planifié est implémenté en tant que méthode de validation du chargement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-123">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="0e6e1-124">Après avoir activé la fonctionnalité, vous devez régénérer les méthodes.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-124">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="0e6e1-125">Allez dans **Gestion des entrepôts \> Paramétrage \> Méthode de validation du chargement**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-125">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="0e6e1-126">Dans le volet Actions, sélectionnez **Régénérer des méthodes**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-126">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="0e6e1-127">Une fois la régénération terminée, vous devriez voir une méthode dont la valeur **Nom de la méthode** est *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-127">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="0e6e1-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-128">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="0e6e1-129">Créer une modèle de cross-docking</span><span class="sxs-lookup"><span data-stu-id="0e6e1-129">Create a cross-docking template</span></span>

1. <span data-ttu-id="0e6e1-130">Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de cross-docking**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-130">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="0e6e1-131">Dans le volet Actions, sélectionnez **Nouveau** pour créer un modèle.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-131">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="0e6e1-132">Dans l'en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-132">In the header, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-133">**Séquence :** *1*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-133">**Sequence:** *1*</span></span>

        <span data-ttu-id="0e6e1-134">Ce champ définit l'ordre d'évaluation des modèles.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-134">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="0e6e1-135">**ID du modèle de cross-docking :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-135">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="0e6e1-136">**Description :** *Entrepôt 51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-136">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="0e6e1-137">**Stratégie de libération de la demande :** *Avant la réception de l'approvisionnement*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-137">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="0e6e1-138">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-138">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="0e6e1-139">La configuration de l'organisateur **Planification** contrôle le fonctionnement du modèle.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-139">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="0e6e1-140">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-140">Set the following values:</span></span>

    - <span data-ttu-id="0e6e1-141">**Exigences de la demande :** *Aucun*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-141">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="0e6e1-142">Ce champ définit les exigences de l'inventaire de la demande.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-142">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="0e6e1-143">Si la demande doit être liée à l'approvisionnement avant la libération, sélectionnez *Marquage*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-143">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="0e6e1-144">Si la demande doit être réservée sur commande par rapport à l'approvisionnement avant la libération, sélectionnez *Réservation de commande*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-144">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="0e6e1-145">**Type d'emplacement :** *Emplacements d'expédition*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-145">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="0e6e1-146">Ce champ définit si le travail de cross-docking doit utiliser les emplacements intermédiaires/de chargement de l'expédition ou s'il doit utiliser les instructions d'emplacement pour trouver ses propres emplacements intermédiaires/de chargement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-146">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="0e6e1-147">**Modèle de travail :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-147">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="0e6e1-148">Ce champ définit le modèle de travail à utiliser lors de la création d'un travail de cross-docking.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-148">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="0e6e1-149">**Revalider à la réception de l'approvisionnement :** *Non*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-149">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="0e6e1-150">Cette option définit si l'approvisionnement doit être revalidé à la réception.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-150">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="0e6e1-151">Si cette option est définie sur *Oui*, l'intervalle de temps maximum et la plage de jours d'expiration sont cochés.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-151">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="0e6e1-152">**Valider l'intervalle de temps :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-152">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="0e6e1-153">Cette option définit si l'intervalle de temps maximum doit être évalué lorsqu'une source d'approvisionnement est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-153">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="0e6e1-154">Si cette option est définie sur *Oui*, les champs liés aux intervalles de temps maximum et minimum deviennent disponibles.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-154">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="0e6e1-155">**Intervalle de temps maximum :** *5*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-155">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="0e6e1-156">Ce champ définit la période maximum autorisée entre l'arrivée de l'approvisionnement et le départ de la demande.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-156">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="0e6e1-157">**Unité d'intervalle de temps maximum :** *Jours*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-157">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="0e6e1-158">**Intervalle de temps minimum :** *0*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-158">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="0e6e1-159">Ce champ définit la période minimum autorisée entre l'arrivée de l'approvisionnement et le départ de la demande.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-159">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="0e6e1-160">**Unité d'intervalle de temps minimum :** *Jours*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-160">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="0e6e1-161">**Plage de jours d'expiration :** *0*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-161">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="0e6e1-162">*Critères FEFO :* Ce champ définit le nombre maximum de jours entre la date d'expiration du traitement par lots arrivant le premier à expiration actuellement dans l'entrepôt et le traitement par lots en cours de réception.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-162">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="0e6e1-163">Dans l'organisateur **Sources d'approvisionnement**, vous spécifiez les types d'approvisionnement valides pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-163">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="0e6e1-164">Sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-164">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="0e6e1-165">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-165">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="0e6e1-166">**Source d'approvisionnement :** *Commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-166">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="0e6e1-167">Créer une classe de travail</span><span class="sxs-lookup"><span data-stu-id="0e6e1-167">Create a work class</span></span>

1. <span data-ttu-id="0e6e1-168">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-168">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="0e6e1-169">Dans le volet Actions, sélectionnez **Nouveau** pour créer une classe de travail.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-169">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="0e6e1-170">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-170">Set the following values:</span></span>

    - <span data-ttu-id="0e6e1-171">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-171">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="0e6e1-172">**Description :** *Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-172">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="0e6e1-173">**Type d'ordre de travail :** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-173">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="0e6e1-174">Créer un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="0e6e1-174">Create a work template</span></span>

1. <span data-ttu-id="0e6e1-175">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-175">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="0e6e1-176">Définissez le champ **Type d'ordre de travail** sur *Cross docking*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-176">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="0e6e1-177">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à l'onglet **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-177">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="0e6e1-178">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-178">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-179">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-179">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="0e6e1-180">**Modèle de travail :** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-180">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="0e6e1-181">**Description du modèle de travail :** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-181">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="0e6e1-182">Sélectionnez **Enregistrer** pour rendre l'organisateur **Détails du modèle de travail** disponible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-182">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="0e6e1-183">Dans l'organisateur **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-183">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="0e6e1-184">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-184">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-185">**Type de travail :** *Choisir*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-185">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="0e6e1-186">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-186">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="0e6e1-187">Sélectionnez **Nouveau** pour ajouter une autre ligne, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-187">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="0e6e1-188">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-188">**Work type:** *Put*</span></span>
    - <span data-ttu-id="0e6e1-189">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-189">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="0e6e1-190">Sélectionnez **Enregistrer** et confirmez que la case **Valide** est cochée pour le modèle *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-190">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="0e6e1-191">Les ID de classe de travail pour les types de travail *Prélever* et *Placer* doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-191">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="0e6e1-192">Créer des instructions d'emplacement</span><span class="sxs-lookup"><span data-stu-id="0e6e1-192">Create location directives</span></span>

1. <span data-ttu-id="0e6e1-193">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d'emplacements**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-193">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="0e6e1-194">Dans le volet gauche, définissez le champ **Type d'ordre de travail** sur *Cross docking*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-194">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="0e6e1-195">Dans le volet Actions, sélectionnez **Nouveau**, puis définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-195">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="0e6e1-196">**Numéro de souche :** *1*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-196">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="0e6e1-197">**Nom :** *51 Cross Dock Put*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-197">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="0e6e1-198">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-198">**Work type:** *Put*</span></span>
    - <span data-ttu-id="0e6e1-199">**Site :** *5*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-199">**Site:** *5*</span></span>
    - <span data-ttu-id="0e6e1-200">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-200">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="0e6e1-201">Sélectionnez **Enregistrer** pour rendre l'organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-201">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="0e6e1-202">Dans l'organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-202">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="0e6e1-203">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-203">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-204">**Quantité de départ :** *1*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-204">**From quantity:** *1*</span></span>
    - <span data-ttu-id="0e6e1-205">**Quantité d'arrivée :** *1000000*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-205">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="0e6e1-206">Sélectionnez **Enregistrer** pour rendre l'organisateur **Actions d'instruction d'emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-206">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="0e6e1-207">Dans l'organisateur **Actions d'instruction d'emplacement**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-207">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="0e6e1-208">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-209">**Nom :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-209">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="0e6e1-210">**Utilisation d'un emplacement fixe :** *Emplacements fixes et non fixes*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-210">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="0e6e1-211">Sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de la barre d'outils **Actions d'instruction d'emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-211">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="0e6e1-212">Sélectionnez **Modifier la requête** pour ouvrir l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-212">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="0e6e1-213">Sous l'onglet **Plage**, assurez-vous que les deux lignes suivantes sont configurées :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-213">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="0e6e1-214">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-214">Line 1:</span></span>

        - <span data-ttu-id="0e6e1-215">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-215">**Table:** *Locations*</span></span>
        - <span data-ttu-id="0e6e1-216">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-216">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="0e6e1-217">**Champ :** *Entrepôt*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-217">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="0e6e1-218">**Critères :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-218">**Criteria:** *51*</span></span>

    - <span data-ttu-id="0e6e1-219">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-219">Line 2:</span></span>

        - <span data-ttu-id="0e6e1-220">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-220">**Table:** *Locations*</span></span>
        - <span data-ttu-id="0e6e1-221">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-221">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="0e6e1-222">**Champ :** *Emplacement*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-222">**Field:** *Location*</span></span>
        - <span data-ttu-id="0e6e1-223">**Critères :** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-223">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="0e6e1-224">Cliquez sur **OK** pour fermer l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-224">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="0e6e1-225">Créer une option de menu d'appareil mobile</span><span class="sxs-lookup"><span data-stu-id="0e6e1-225">Create a mobile device menu item</span></span>

1. <span data-ttu-id="0e6e1-226">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-226">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="0e6e1-227">Dans la liste des éléments de menu du volet gauche, sélectionnez **Rangement d'achat**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-227">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="0e6e1-228">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-228">Select **Edit**.</span></span>
1. <span data-ttu-id="0e6e1-229">Dans l'organisateur **Classes de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-229">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="0e6e1-230">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-230">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-231">**ID classe de travail :** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-231">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="0e6e1-232">**Type d'ordre de travail :** *Cross docking*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-232">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="0e6e1-233">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-233">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="0e6e1-234">Scénario</span><span class="sxs-lookup"><span data-stu-id="0e6e1-234">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="0e6e1-235">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="0e6e1-235">Create a purchase order</span></span>

<span data-ttu-id="0e6e1-236">Suivez les étapes ci-après pour créer une commande fournisseur comme source d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-236">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="0e6e1-237">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-237">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="0e6e1-238">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-238">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0e6e1-239">Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-239">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-240">**Compte fournisseur :** *104*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-240">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="0e6e1-241">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-241">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="0e6e1-242">Cliquez sur **OK** et prenez note du numéro de commande.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-242">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="0e6e1-243">Une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-243">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="0e6e1-244">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-244">On this line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-245">**Numéro d'article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-245">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="0e6e1-246">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-246">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="0e6e1-247">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="0e6e1-247">Create a sales order</span></span>

<span data-ttu-id="0e6e1-248">Suivez les étapes ci-après pour créer une commande client comme source de demande.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-248">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="0e6e1-249">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-249">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="0e6e1-250">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-250">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0e6e1-251">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-251">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-252">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-252">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="0e6e1-253">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-253">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="0e6e1-254">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-254">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-255">Une nouvelle ligne est ajoutée à l'organisateur **Lignes de commande client**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-255">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="0e6e1-256">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e6e1-256">On this line, set the following values:</span></span>

    - <span data-ttu-id="0e6e1-257">**Numéro d'article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-257">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="0e6e1-258">**Quantité :** *3*</span><span class="sxs-lookup"><span data-stu-id="0e6e1-258">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="0e6e1-259">Créer le cross-docking planifié</span><span class="sxs-lookup"><span data-stu-id="0e6e1-259">Create planned cross-docking</span></span>

<span data-ttu-id="0e6e1-260">Suivez les étapes ci-après pour créer le cross-docking planifié à partir de la commande client.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-260">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="0e6e1-261">Dans la page **Détails de la commande client** de la commande client que vous venez de créer, dans le volet Actions, sous l'onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-261">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="0e6e1-262">L'action de libération dans l'entrepôt crée une ligne d'expédition et de chargement pour la ligne de commande client et tente d'allouer le stock.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-262">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="0e6e1-263">Vous recevez un message d'information.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-263">You receive an informational message.</span></span> <span data-ttu-id="0e6e1-264">Vous recevez également le message d'avertissement suivant : « Aucun travail n'a été créé pour la vague XXXX.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-264">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="0e6e1-265">Pour plus de détails, consultez le journal historique de création de travail. »</span><span class="sxs-lookup"><span data-stu-id="0e6e1-265">See the work creation history log for details."</span></span> <span data-ttu-id="0e6e1-266">Ce comportement est attendu, car il n'y a pas de stock dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-266">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="0e6e1-267">Dans l'organisateur **Lignes de commande client**, dans le menu **Entrepôt**, sélectionnez **Détails de l'expédition**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-267">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="0e6e1-268">La page **Détails de l'expédition** apparaît et affiche l'expédition créée pour la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-268">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="0e6e1-269">Dans l'organisateur **Lignes de chargement**, notez que le champ **Quantité de cross docking planifié** est défini sur *3*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-269">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="0e6e1-270">Étant donné qu'aucun stock n'était disponible dans l'entrepôt, mais une source d'approvisionnement valide arrivera dans l'intervalle de temps défini dans le modèle de cross-docking, la quantité de cross-docking a été créée.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-270">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="0e6e1-271">Dans l'organisateur **Lignes de chargement**, sélectionnez **Cross docking planifié** pour afficher les détails du cross-docking créé.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-271">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="0e6e1-272">Traiter le cross-docking</span><span class="sxs-lookup"><span data-stu-id="0e6e1-272">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="0e6e1-273">Réception de commande fournisseur sur l'application mobile d'entreposage</span><span class="sxs-lookup"><span data-stu-id="0e6e1-273">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="0e6e1-274">Le système recevra la quantité de 5 de la commande fournisseur dans l'emplacement de réception et créera deux travaux.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-274">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="0e6e1-275">Le premier ID de travail créé a une valeur **Type d'ordre de travail** de *Cross docking* et est lié à la commande client.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-275">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="0e6e1-276">Sa quantité est 3 et il est envoyé vers l'emplacement d'expédition finale afin de pouvoir être expédié immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-276">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="0e6e1-277">Le deuxième ID de travail créé a une valeur **Type d'ordre de travail** de *Commandes fournisseur* et est lié à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-277">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="0e6e1-278">Sa quantité restante est 2 et n'a pas fait l'objet d'un cross docking. Il est envoyé pour rangement dans l'emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-278">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="0e6e1-279">Connectez-vous à l'appareil mobile en tant qu'utilisateur dans l'entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-279">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="0e6e1-280">Allez à **Entrant \> Réception d'achat**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-280">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="0e6e1-281">Dans le champ **PONum**, entrez votre numéro de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-281">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="0e6e1-282">Dans le champ **Qté**, entrez *5*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-282">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="0e6e1-283">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-283">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-284">Dans la page suivante, définissez le champ **Article** sur *A0001*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-284">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="0e6e1-285">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-285">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-286">Dans la page suivante, confirmez les valeurs **PONum**, **Article** et **Qté** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-286">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="0e6e1-287">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="0e6e1-287">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="0e6e1-288">Sélectionnez **Annuler** pour quitter.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-288">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="0e6e1-289">Ranger dans le cross-docking et en bloc</span><span class="sxs-lookup"><span data-stu-id="0e6e1-289">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="0e6e1-290">Actuellement, les deux ID de travail ont le même contenant cible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-290">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="0e6e1-291">Pour effectuer les étapes suivantes, vous devez obtenir l'ID de travail et l'ID de contenant cible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-291">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="0e6e1-292">Vous pouvez obtenir ces informations à partir des détails du travail de la ligne de commande fournisseur et de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-292">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="0e6e1-293">Vous pouvez également aller dans **Gestion des entrepôts \> Travail \> Détails du travail** et filtrer le travail où la valeur **Entrepôt** est *51*.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-293">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="0e6e1-294">Sur l'appareil mobile, accédez à **Entrant \> Rangement d'achat** et entrez le contenant cible à partir du travail.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-294">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="0e6e1-295">Dans le champ **ID**, entrez l'ID de contenant cible à partir des détails du travail.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-295">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="0e6e1-296">La page de prélèvement du cross-docking indique l'emplacement de prélèvement (*RECV*), le contenant cible (*contenant*), l'article (*A0001*) et la quantité (*3*).</span><span class="sxs-lookup"><span data-stu-id="0e6e1-296">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="0e6e1-297">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-297">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-298">Dans le champ **Contenant cible**, entrez un contenant cible pour l'ID de contenant qui doit être placé (faire l'objet d'un cross-docking) dans l'emplacement d'expédition.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-298">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="0e6e1-299">Vous pouvez sélectionner n'importe quel ID de contenant de votre choix.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-299">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="0e6e1-300">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-300">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-301">Dans la page suivante, dans le champ **ID**, entrez l'ID de contenant cible.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-301">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="0e6e1-302">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-302">Select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-303">Confirmez le travail de prélèvement de la quantité restante de 2, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-303">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="0e6e1-304">Dans la page suivante, sélectionnez **Terminé** pour terminer le processus de prélèvement et commencer le processus de rangement.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-304">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="0e6e1-305">L'application mobile vous présente l'emplacement et le contenant dans lesquels placer l'article.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-305">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="0e6e1-306">Confirmez le stockage en bloc **Placer** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-306">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="0e6e1-307">Dans la page suivante, confirmez le cross-docking **Placer** en cliquant sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-307">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="0e6e1-308">Vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="0e6e1-308">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="0e6e1-309">Sélectionnez **Annuler** pour quitter.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-309">Select **Cancel** to exit.</span></span>

<span data-ttu-id="0e6e1-310">L'illustration suivante montre comment le travail de cross-docking terminé peut apparaître dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0e6e1-310">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="0e6e1-311">![Travail de cross-docking terminé](media/PlannedCrossDockingWork.png "Travail de cross-docking terminé")</span><span class="sxs-lookup"><span data-stu-id="0e6e1-311">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>
