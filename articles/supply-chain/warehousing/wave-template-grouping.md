---
title: Regroupement de modèles de vague
description: Le regroupement de modèles de vagues permet au système d’utiliser des configurations de modèles de vagues afin de déterminer, en fonction des critères que vous définissez, comment il doit fractionner les lignes libérées et les affecter à des vagues nouvelles ou existantes. Cette fonctionnalité peut être utile dans les entrepôts où des vagues sont créées en fonction de critères spécifiques, mais où les gestionnaires préfèrent créer des vagues automatiquement plutôt que manuellement.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 520338683443105ffd1df7fc2569cd95a5f50879
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245128"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="3e2b7-104">Regroupement de modèles de vague</span><span class="sxs-lookup"><span data-stu-id="3e2b7-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e2b7-105">Le regroupement de modèles de vagues permet au système d’utiliser des configurations de [modèles de vagues](tasks/configure-wave-processing.md) afin de déterminer, en fonction des critères que vous définissez, comment il doit fractionner les lignes libérées et les affecter à des vagues nouvelles ou existantes.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="3e2b7-106">Cette fonctionnalité peut être utile dans les entrepôts où des vagues sont créées en fonction de critères spécifiques, mais où les gestionnaires préfèrent créer des vagues automatiquement plutôt que manuellement.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="3e2b7-107">Elle permet au système d’ajouter chaque nouvelle expédition validée à la première vague qu’il trouve et ayant des valeurs de champ de regroupement correspondantes.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="3e2b7-108">Si aucune correspondance n’est trouvée, le système crée une vague pour la nouvelle expédition.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e2b7-109">Le regroupement de modèles de vagues n’est pas pris en charge pour les types de travail de *prélèvement de matières premières de production* ou de *prélèvement Kanban*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="3e2b7-110">En effet, le regroupement de vagues est basé sur les expéditions et ces types de travaux n’utilisent pas les expéditions.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="3e2b7-111">Activer la fonctionnalité de regroupement de modèles de vagues</span><span class="sxs-lookup"><span data-stu-id="3e2b7-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="3e2b7-112">Avant de pouvoir utiliser la fonctionnalité *Regroupement de modèles de vagues*, celle-ci doit être activée sur votre système.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="3e2b7-113">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="3e2b7-114">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3e2b7-115">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="3e2b7-116">**Nom de la fonctionnalité :** *Regroupement de modèles de vagues*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="3e2b7-117">Définir un modèle de vague pour utiliser le regroupement de modèles de vagues</span><span class="sxs-lookup"><span data-stu-id="3e2b7-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="3e2b7-118">Pour rendre le regroupement de modèles de vagues disponible, procédez comme suit pour configurer votre [modèle de vague](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="3e2b7-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="3e2b7-119">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="3e2b7-120">Dans le volet gauche, sélectionnez le modèle de vague à configurer.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="3e2b7-121">Si vous vous apprêtez à exécuter le scénario plus loin dans cette rubrique à l’aide de données de démonstration, sélectionnez le modèle **62 Expédition par défaut**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="3e2b7-122">Sélectionnez **Modifier** pour afficher la page en mode d’édition.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="3e2b7-123">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-124">**Automatiser la création de vague :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="3e2b7-125">**Attribuer aux vagues ouvertes :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="3e2b7-126">**Traiter la vague à la libération dans l’entrepôt :** *Non*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="3e2b7-127">Dans le volet Actions, sélectionnez **Modifier la requête** pour ouvrir la boîte de dialogue de requête.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="3e2b7-128">Dans la boîte de dialogue de requête, sur l’onglet **Tri**, passez en revue les critères de tri et assurez-vous qu’il existe une règle qui inclut le champ que vous souhaitez utiliser pour regrouper vos vagues.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="3e2b7-129">Si vous vous préparez à exécuter le scénario à l’aide des données de démonstration, ajoutez une ligne avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="3e2b7-130">**Table :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="3e2b7-131">**Table dérivée :** *Expéditions*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="3e2b7-132">**Champ :** *Service de transporteur*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="3e2b7-133">Une fois que vous avez sélectionné cette valeur, le message suivant peut s’afficher : « Le champ Service de transporteur n’est pas un champ d’index.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="3e2b7-134">Voulez-vous ajouter un tri à ce sujet ? »</span><span class="sxs-lookup"><span data-stu-id="3e2b7-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="3e2b7-135">Sélectionnez **Oui** pour ajouter le tri.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="3e2b7-136">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="3e2b7-137">Sélectionnez **OK** pour enregistrer vos modifications et fermer la boîte de dialogue de requête.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="3e2b7-138">Dans le volet Actions, sélectionnez **Regroupement de modèles de vagues**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="3e2b7-139">Sur la page **Regroupement de modèles de vagues**, cochez la case **Grouper par** pour chaque ligne à utiliser pour regrouper vos lignes de commande par vagues, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="3e2b7-140">Si vous vous apprêtez à exécuter le scénario à l’aide des données de démonstration, cochez la case **Grouper par** pour la ligne *Service de transporteur*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="3e2b7-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-141">Select **Save**.</span></span>
1. <span data-ttu-id="3e2b7-142">Fermez la page **Regroupement de modèles de vagues**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="3e2b7-143">Sélectionnez **Enregistrer** pour enregistrer le modèle.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="3e2b7-144">Scénario</span><span class="sxs-lookup"><span data-stu-id="3e2b7-144">Scenario</span></span>

<span data-ttu-id="3e2b7-145">Cette section fournit un script que vous pouvez exécuter pour découvrir ce que fait cette fonctionnalité et comment l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="3e2b7-146">Rendre les exemple de données disponibles</span><span class="sxs-lookup"><span data-stu-id="3e2b7-146">Make sample data available</span></span>

<span data-ttu-id="3e2b7-147">Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="3e2b7-148">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="3e2b7-149">Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité lorsque vous travaillez sur un système de production.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="3e2b7-150">Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="3e2b7-151">Scénario : Regroupement de modèles de vagues</span><span class="sxs-lookup"><span data-stu-id="3e2b7-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="3e2b7-152">Ce scénario montre comment utiliser le regroupement de modèles de vagues pour créer automatiquement plusieurs vagues, en fonction de critères de regroupement définis dans un modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="3e2b7-153">Dans ce scénario, le modèle de vague est configuré dans le système pour créer une vague par service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="3e2b7-154">Avant de commencer, préparez votre modèle de vague comme décrit dans la section [Définir un modèle de vague pour utiliser le regroupement de modèles de vagues](#set-up-template) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="3e2b7-155">Si vous utiliser des données de démonstration pour ce scénario, veillez à utiliser les valeurs de données de démonstration suggérées dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="3e2b7-156">Cette configuration regroupera vos vagues en fonction du service de transporteur défini pour chaque commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="3e2b7-157">Créer une commande client 1</span><span class="sxs-lookup"><span data-stu-id="3e2b7-157">Create sales order 1</span></span>

1. <span data-ttu-id="3e2b7-158">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3e2b7-159">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="3e2b7-160">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-161">Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-004*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="3e2b7-162">Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="3e2b7-163">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="3e2b7-164">La nouvelle commande client est ouverte dans la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="3e2b7-165">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="3e2b7-166">Basculez sur la vue **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="3e2b7-167">Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-168">**Transporteur :** *Fret aérien*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="3e2b7-169">**Service de transporteur :** *Air*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="3e2b7-170">Revenez à la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="3e2b7-171">Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="3e2b7-172">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-173">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="3e2b7-174">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="3e2b7-175">Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="3e2b7-176">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="3e2b7-177">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="3e2b7-178">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="3e2b7-179">Vous recevez un message d’information indiquant l’expédition et la vague de cette commande.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="3e2b7-180">Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="3e2b7-181">Afficher la vague créée à partir de la commande client 1</span><span class="sxs-lookup"><span data-stu-id="3e2b7-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="3e2b7-182">Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="3e2b7-183">Sélectionnez l’ID de vague à partir duquel la commande client a été créée.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="3e2b7-184">Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="3e2b7-185">Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="3e2b7-186">Créer une commande client 2</span><span class="sxs-lookup"><span data-stu-id="3e2b7-186">Create sales order 2</span></span>

1. <span data-ttu-id="3e2b7-187">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3e2b7-188">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="3e2b7-189">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-190">Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-005*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="3e2b7-191">Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="3e2b7-192">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="3e2b7-193">La nouvelle commande client est ouverte dans la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="3e2b7-194">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="3e2b7-195">Basculez sur la vue **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="3e2b7-196">Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-197">**Transporteur :** *Farine en mouvement*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="3e2b7-198">**Service de transporteur :** *Standard*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="3e2b7-199">Revenez à la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="3e2b7-200">Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="3e2b7-201">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-202">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3e2b7-203">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="3e2b7-204">Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="3e2b7-205">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="3e2b7-206">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="3e2b7-207">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="3e2b7-208">Vous recevez un message d’information indiquant l’expédition et la vague de cette commande.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="3e2b7-209">Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="3e2b7-210">Notez que l’ID de vague diffère de l’ID de vague de la première commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="3e2b7-211">Afficher la vague créée à partir de la commande client 2</span><span class="sxs-lookup"><span data-stu-id="3e2b7-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="3e2b7-212">Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="3e2b7-213">Sélectionnez l’ID de vague à partir duquel la seconde commande client a été créée.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="3e2b7-214">Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="3e2b7-215">Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="3e2b7-216">Une vague a été créée pour cette expédition, car elle utilise un service de transporteur différent de la première commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="3e2b7-217">Créer une commande client 3</span><span class="sxs-lookup"><span data-stu-id="3e2b7-217">Create sales order 3</span></span>

1. <span data-ttu-id="3e2b7-218">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="3e2b7-219">Sélectionnez **Nouveau** pour créer une commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="3e2b7-220">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-221">Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-006*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="3e2b7-222">Dans l’organisateur **Général**, définissez le champ **Entrepôt** sur *62*.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="3e2b7-223">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue **Créer une commande client**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="3e2b7-224">La nouvelle commande client est ouverte dans la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="3e2b7-225">Prenez note du numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="3e2b7-226">Basculez sur la vue **En-tête**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="3e2b7-227">Sur l’organisateur **Livraison**, dans la section **Transport**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-228">**Transporteur :** *Fret aérien*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="3e2b7-229">**Service de transporteur :** *Air*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="3e2b7-230">Revenez à la vue **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="3e2b7-231">Dans la section **Lignes de la commande client**, cliquez sur **Ajouter une ligne** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="3e2b7-232">Sur la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e2b7-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="3e2b7-233">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="3e2b7-234">**Quantité :** *1*</span><span class="sxs-lookup"><span data-stu-id="3e2b7-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="3e2b7-235">Sélectionnez la nouvelle ligne de commande, puis, sur le menu **Stock** au-dessus de la grille, sélectionnez **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="3e2b7-236">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la quantité totale de la ligne sélectionnée dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="3e2b7-237">Fermez la page **Réservation** pour revenir à la commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="3e2b7-238">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="3e2b7-239">Vous recevez un message d’information indiquant l’expédition et la vague de cette commande.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="3e2b7-240">Notez le numéro d’identification de la vague et les numéros d’identification d’expédition.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="3e2b7-241">L’expédition a été affectée à la vague existante à partir de la première commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="3e2b7-242">Afficher la vague des commandes client 1 et 3</span><span class="sxs-lookup"><span data-stu-id="3e2b7-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="3e2b7-243">Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="3e2b7-244">Sélectionnez l’ID de vague à partir duquel la troisième commande client a été créée.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="3e2b7-245">Sélectionnez le lien d’ID de vague pour ouvrir la page de détails de la vague.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="3e2b7-246">Notez que l’expédition a été ajoutée à l’organisateur **Lignes de la vague**, ainsi que l’expédition de la première commande client.</span><span class="sxs-lookup"><span data-stu-id="3e2b7-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]