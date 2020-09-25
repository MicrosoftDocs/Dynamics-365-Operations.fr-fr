---
title: Poste de groupement complet
description: Cette rubrique fournit des informations sur la fonctionnalité Poste de groupement complet. Cette fonctionnalité offre une alternative à une application plus rigide des règles de pause de travail lorsque le prélèvement de groupement est utilisé, car elle permet une plus grande marge d’erreur dans les contraintes volumétriques des conteneurs ou des bacs.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8d030afb568b158e6caf48b0044d595d6ec024f6
ms.sourcegitcommit: 06f64550b2043582de4018bdd3924fcc1fd5d310
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802212"
---
# <a name="cluster-position-full"></a><span data-ttu-id="2169e-104">Poste de groupement complet</span><span class="sxs-lookup"><span data-stu-id="2169e-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2169e-105">La fonctionnalité *Poste de groupement complet* offre une alternative à une application plus rigide des règles de pause de travail lorsque le prélèvement de groupement est utilisé, car elle permet une plus grande marge d’erreur dans les contraintes volumétriques des conteneurs ou des bacs.</span><span class="sxs-lookup"><span data-stu-id="2169e-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="2169e-106">Dans un scénario courant, tous les éléments d’un ordre de travail ne rentrent pas dans un conteneur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2169e-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="2169e-107">Dans ce scénario, les manutentionnaires qui effectuent des prélèvements de groupement ont peu d’options : ils doivent soit passer à une taille de conteneur plus grande, soit travailler avec leur superviseur pour trouver une solution différente.</span><span class="sxs-lookup"><span data-stu-id="2169e-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="2169e-108">Cette fonctionnalité introduit la possibilité d’exécuter le bouton **Plein** sur l’une des unités de travail d’un groupement.</span><span class="sxs-lookup"><span data-stu-id="2169e-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="2169e-109">Dans les anciennes versions, cette option n’était disponible que pour la préparation de commandes standard, pas pour le prélèvement de groupement.</span><span class="sxs-lookup"><span data-stu-id="2169e-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="2169e-110">Cependant, cette fonctionnalité diffère du bouton **Plein** standard en ce qu’il annule le travail restant.</span><span class="sxs-lookup"><span data-stu-id="2169e-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="2169e-111">Cela ne suggère pas que l’utilisateur ajoute un autre bac au même groupement et ne crée pas automatiquement de travail.</span><span class="sxs-lookup"><span data-stu-id="2169e-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="2169e-112">Activer la fonctionnalité Poste de groupement complet</span><span class="sxs-lookup"><span data-stu-id="2169e-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="2169e-113">Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="2169e-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="2169e-114">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2169e-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="2169e-115">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="2169e-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="2169e-116">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="2169e-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="2169e-117">**Nom de la fonctionnalité :** *Poste de groupement complet*</span><span class="sxs-lookup"><span data-stu-id="2169e-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="2169e-118">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="2169e-118">Setup</span></span>

<span data-ttu-id="2169e-119">Cette section fournit des instructions et un exemple qui montre comment configurer et utiliser la fonctionnalité *Poste de groupement complet*.</span><span class="sxs-lookup"><span data-stu-id="2169e-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="2169e-120">Rendre les exemple de données disponibles</span><span class="sxs-lookup"><span data-stu-id="2169e-120">Make sample data available</span></span>

<span data-ttu-id="2169e-121">Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="2169e-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="2169e-122">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="2169e-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="2169e-123">Vous pouvez également utiliser cet exemple de scénario comme orientation pour utiliser cette fonctionnalité lorsque vous travaillez sur un système de production.</span><span class="sxs-lookup"><span data-stu-id="2169e-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="2169e-124">Cependant, dans ce cas, vous devez remplacer les valeurs des paramètres décrits ici par les vôtres.</span><span class="sxs-lookup"><span data-stu-id="2169e-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="2169e-125">Profils de groupement</span><span class="sxs-lookup"><span data-stu-id="2169e-125">Cluster profiles</span></span>

<span data-ttu-id="2169e-126">Vous devez spécifier si les ID de groupement sont générés automatiquement, combien de postes sont utilisés, quand les groupements sont interrompus et comment le travail de prélèvement est séquencé et vérifié.</span><span class="sxs-lookup"><span data-stu-id="2169e-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="2169e-127">Accédez à **Gestion des entrepôts \> Paramétrage \> Appareil mobile \> Profils de groupement**.</span><span class="sxs-lookup"><span data-stu-id="2169e-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="2169e-128">Dans le volet de liste, sélectionnez l’enregistrement **Créer un groupement**.</span><span class="sxs-lookup"><span data-stu-id="2169e-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="2169e-129">Dans l’organisateur **Général**, vérifiez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="2169e-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="2169e-130">**Générer un ID de groupement :** Sélectionnez *Oui*</span><span class="sxs-lookup"><span data-stu-id="2169e-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="2169e-131">**Activer des postes :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="2169e-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="2169e-132">**Nombre de postes :** *2*</span><span class="sxs-lookup"><span data-stu-id="2169e-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="2169e-133">**Nom du poste :** *Numérique*</span><span class="sxs-lookup"><span data-stu-id="2169e-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="2169e-134">**Rompre le groupement à :** *Rangement*</span><span class="sxs-lookup"><span data-stu-id="2169e-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="2169e-135">**Type de vérification du tri :** *Analyse de poste*</span><span class="sxs-lookup"><span data-stu-id="2169e-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="2169e-136">Dans le raccourci **Tri de groupement**.</span><span class="sxs-lookup"><span data-stu-id="2169e-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="2169e-137">La grille doit être vide (c’est-à-dire qu’elle ne doit contenir aucune ligne).</span><span class="sxs-lookup"><span data-stu-id="2169e-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="2169e-138">Modèles de travail</span><span class="sxs-lookup"><span data-stu-id="2169e-138">Work templates</span></span>

<span data-ttu-id="2169e-139">Vous devez définir comment créer le travail de prélèvement pour le prélèvement de groupement.</span><span class="sxs-lookup"><span data-stu-id="2169e-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="2169e-140">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="2169e-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="2169e-141">En haut de la page, définissez le champ **Type d’ordre de travail** sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="2169e-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="2169e-142">Assurez-vous que les modèles de travail suivants des données de démonstration sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="2169e-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="2169e-143">S’ils ne sont pas disponibles, vous ne pourrez pas terminer le scénario.</span><span class="sxs-lookup"><span data-stu-id="2169e-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="2169e-144">Phase CC 61</span><span class="sxs-lookup"><span data-stu-id="2169e-144">61 SO Stage</span></span>
    - <span data-ttu-id="2169e-145">Prélèvement de groupement CC 61</span><span class="sxs-lookup"><span data-stu-id="2169e-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="2169e-146">Instructions d’emplacement</span><span class="sxs-lookup"><span data-stu-id="2169e-146">Location directives</span></span>

<span data-ttu-id="2169e-147">Vous devez spécifier où les articles sont prélevés et où ils sont placés.</span><span class="sxs-lookup"><span data-stu-id="2169e-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="2169e-148">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="2169e-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="2169e-149">Dans l’en-tête de liste, définissez le champ **Type d’ordre de travail** sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="2169e-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="2169e-150">Assurez-vous que les directives de commande client suivantes des données de démonstration sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="2169e-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="2169e-151">S’ils ne sont pas disponibles, vous ne pourrez pas terminer le scénario.</span><span class="sxs-lookup"><span data-stu-id="2169e-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="2169e-152">Prélèvement de groupement 61</span><span class="sxs-lookup"><span data-stu-id="2169e-152">61 Cluster pick</span></span>
    - <span data-ttu-id="2169e-153">Ordre de prélèvement CC 61</span><span class="sxs-lookup"><span data-stu-id="2169e-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="2169e-154">Options de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="2169e-154">Mobile device menu items</span></span>

<span data-ttu-id="2169e-155">Vous devez configurer une option de menu d’appareil mobile pour utiliser le travail existant qui est dirigé par le prélèvement de groupement.</span><span class="sxs-lookup"><span data-stu-id="2169e-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="2169e-156">Dans l’élément de menu de l’appareil mobile pour la sélection de groupement, le paramètre **Autoriser le fractionnement du travail** doit être activé et le la classe de travail *Prélèvement CC* doit être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="2169e-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="2169e-157">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="2169e-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="2169e-158">Dans le volet de liste, sélectionnez l’enregistrement **Création de prélèvement de groupement**.</span><span class="sxs-lookup"><span data-stu-id="2169e-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="2169e-159">Sélectionnez **Modifier** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="2169e-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="2169e-160">Dans l’organisateur **Général**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="2169e-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2169e-161">**Dirigé par :** *Prélèvement de groupement*</span><span class="sxs-lookup"><span data-stu-id="2169e-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="2169e-162">**Générer un contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="2169e-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="2169e-163">**Autoriser le fractionnement du travail :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="2169e-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="2169e-164">**ID de profil de groupement :** *Créer un cluster*</span><span class="sxs-lookup"><span data-stu-id="2169e-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="2169e-165">Acceptez les valeurs par défaut pour tous les autres champs.</span><span class="sxs-lookup"><span data-stu-id="2169e-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="2169e-166">Sur le raccourci **Classes de travail**, ajoutez les deux lignes suivantes, si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="2169e-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="2169e-167">Ligne 1 (généralement présente dans les données de démonstration) :</span><span class="sxs-lookup"><span data-stu-id="2169e-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="2169e-168">**ID classe de travail :** *Ventes*</span><span class="sxs-lookup"><span data-stu-id="2169e-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="2169e-169">**Type d’ordre de travail :** *Commandes client*</span><span class="sxs-lookup"><span data-stu-id="2169e-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="2169e-170">Ligne 2 (probablement absente dans les données de démonstration) :</span><span class="sxs-lookup"><span data-stu-id="2169e-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="2169e-171">**ID classe de travail :** *Prélèvement CC*</span><span class="sxs-lookup"><span data-stu-id="2169e-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="2169e-172">**Type d’ordre de travail :** *Commandes client*</span><span class="sxs-lookup"><span data-stu-id="2169e-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="2169e-173">Allez à **Configuration de la confirmation de travail** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="2169e-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="2169e-174">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="2169e-174">Select **Edit**.</span></span>
1. <span data-ttu-id="2169e-175">Entrez l’une des valeurs suivantes sur la ligne de la grille.</span><span class="sxs-lookup"><span data-stu-id="2169e-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="2169e-176">**Type de travail** - *Prélèvement*</span><span class="sxs-lookup"><span data-stu-id="2169e-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="2169e-177">**Confirmation du produit** - *Cocher la case*</span><span class="sxs-lookup"><span data-stu-id="2169e-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="2169e-178">Sélectionnez **Enregistrer** dans le volet Action et fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2169e-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="2169e-179">Création de tâches de prélèvement</span><span class="sxs-lookup"><span data-stu-id="2169e-179">Create picking work</span></span>

<span data-ttu-id="2169e-180">Avant de pouvoir commencer la sélection de groupement, vous devez créer du travail sortant.</span><span class="sxs-lookup"><span data-stu-id="2169e-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="2169e-181">Le profil de groupement créé précédemment spécifie deux positions de groupement.</span><span class="sxs-lookup"><span data-stu-id="2169e-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="2169e-182">Par conséquent, au moins deux ID de travail doivent être créés pour la préparation des commandes client.</span><span class="sxs-lookup"><span data-stu-id="2169e-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="2169e-183">Pour ce scénario, les transactions se produiront dans l’entrepôt *61*, et ils utiliseront des éléments *L0101* et *T0100*.</span><span class="sxs-lookup"><span data-stu-id="2169e-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="2169e-184">Les données de démonstration doivent avoir un stock disponible de ces éléments suffisant.</span><span class="sxs-lookup"><span data-stu-id="2169e-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="2169e-185">Assurez-vous que vous disposez d’un stock suffisant pour effectuer les transactions.</span><span class="sxs-lookup"><span data-stu-id="2169e-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="2169e-186">Créer une commande client 1</span><span class="sxs-lookup"><span data-stu-id="2169e-186">Create sales order 1</span></span>

1. <span data-ttu-id="2169e-187">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="2169e-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2169e-188">Sélectionnez **Nouveau** pour créer une commande client 1.</span><span class="sxs-lookup"><span data-stu-id="2169e-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="2169e-189">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="2169e-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2169e-190">**Compte client :** *US-010*</span><span class="sxs-lookup"><span data-stu-id="2169e-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="2169e-191">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="2169e-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="2169e-192">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2169e-192">Select **OK**.</span></span>
1. <span data-ttu-id="2169e-193">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="2169e-193">The new sales order is opened.</span></span> <span data-ttu-id="2169e-194">Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2169e-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="2169e-195">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="2169e-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="2169e-196">**Quantité :** *5*</span><span class="sxs-lookup"><span data-stu-id="2169e-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="2169e-197">Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.</span><span class="sxs-lookup"><span data-stu-id="2169e-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="2169e-198">Dans l’organisateur **Lignes de commande client**, ajoutez une seconde ligne présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2169e-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="2169e-199">**Numéro d’article :** *L0101*</span><span class="sxs-lookup"><span data-stu-id="2169e-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="2169e-200">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="2169e-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="2169e-201">Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.</span><span class="sxs-lookup"><span data-stu-id="2169e-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="2169e-202">Pour chaque ligne que vous venez d’ajouter, procédez comme suit pour réserver le stock :</span><span class="sxs-lookup"><span data-stu-id="2169e-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="2169e-203">Sélectionnez la ligne à réserver.</span><span class="sxs-lookup"><span data-stu-id="2169e-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="2169e-204">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="2169e-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="2169e-205">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="2169e-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="2169e-206">Fermez la page **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="2169e-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="2169e-207">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="2169e-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="2169e-208">Une fois le lancement terminé, vous recevez des messages d’information indiquant les ID de vague et de chargement créés.</span><span class="sxs-lookup"><span data-stu-id="2169e-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="2169e-209">Créer une commande client 2</span><span class="sxs-lookup"><span data-stu-id="2169e-209">Create sales order 2</span></span>

1. <span data-ttu-id="2169e-210">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="2169e-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="2169e-211">Sélectionnez **Nouveau** pour créer une commande client 2.</span><span class="sxs-lookup"><span data-stu-id="2169e-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="2169e-212">Dans la boîte de dialogue **Créer une commande client**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="2169e-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2169e-213">**Compte client :** *US-011*</span><span class="sxs-lookup"><span data-stu-id="2169e-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="2169e-214">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="2169e-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="2169e-215">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2169e-215">Select **OK**.</span></span>
1. <span data-ttu-id="2169e-216">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="2169e-216">The new sales order is opened.</span></span> <span data-ttu-id="2169e-217">Dans l’organisateur **Lignes de commande client**, ajoutez une ligne présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2169e-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="2169e-218">**Numéro d’article :** *L0101*</span><span class="sxs-lookup"><span data-stu-id="2169e-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="2169e-219">**Quantité :** *20*</span><span class="sxs-lookup"><span data-stu-id="2169e-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="2169e-220">Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.</span><span class="sxs-lookup"><span data-stu-id="2169e-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="2169e-221">Dans l’organisateur **Lignes de commande client**, ajoutez une seconde ligne présentant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2169e-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="2169e-222">**Numéro d’article :** *T0100*</span><span class="sxs-lookup"><span data-stu-id="2169e-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="2169e-223">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="2169e-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="2169e-224">Sur le raccourci **Détails de ligne**,sur l’onglet **Livraison**, définissez le champ **Date d’expédition confirmée** sur la date du jour.</span><span class="sxs-lookup"><span data-stu-id="2169e-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="2169e-225">Pour chaque ligne que vous venez d’ajouter, procédez comme suit pour réserver le stock :</span><span class="sxs-lookup"><span data-stu-id="2169e-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="2169e-226">Sélectionnez la ligne à réserver.</span><span class="sxs-lookup"><span data-stu-id="2169e-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="2169e-227">Sur l’organisateur **Lignes de commande client**, sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="2169e-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="2169e-228">Sur la page **Réservation**, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver le stock.</span><span class="sxs-lookup"><span data-stu-id="2169e-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="2169e-229">Fermez la page **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="2169e-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="2169e-230">Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="2169e-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="2169e-231">Une fois le lancement terminé, vous recevez des messages d’information indiquant les ID de vague et de chargement créés.</span><span class="sxs-lookup"><span data-stu-id="2169e-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="2169e-232">Obtenez des identifiants de travail et des numéros de contenants</span><span class="sxs-lookup"><span data-stu-id="2169e-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="2169e-233">Deux ID de travail doivent avoir été créés, chacun ayant deux lignes de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="2169e-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="2169e-234">Suivez ces étapes pour trouver les ID de travail et les attributions de contenants.</span><span class="sxs-lookup"><span data-stu-id="2169e-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="2169e-235">Accédez à **Gestion des entrepôts \> Travail \> Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="2169e-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="2169e-236">Dans la grille **Vue d’ensemble**, recherchez la colonne **Numéro de commande** pour les deux commandes que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="2169e-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="2169e-237">Pour chaque commande client, notez l’ID de travail correspondant.</span><span class="sxs-lookup"><span data-stu-id="2169e-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="2169e-238">Sélectionnez la ligne de chaque commande client pour afficher les informations associées dans la grille **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="2169e-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="2169e-239">Notez l’emplacement à partir duquel chaque article sera prélevé.</span><span class="sxs-lookup"><span data-stu-id="2169e-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="2169e-240">Accédez à **Gestion des stocks \> Recherches et états \> Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="2169e-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="2169e-241">Dans le volet Actions, sélectionnez **Dimensions** pour ouvrir la boîte de dialogue **Affichage des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="2169e-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="2169e-242">Assurez-vous que les cases **Contenant**, **Entrepôt** et **Numéro d’article** sont cochées, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="2169e-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="2169e-243">Dans le volet **Filtre**, définissez les filtres suivants :</span><span class="sxs-lookup"><span data-stu-id="2169e-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="2169e-244">**Numéro d’article** – **fait partie de** – *L0101* et *T100*</span><span class="sxs-lookup"><span data-stu-id="2169e-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="2169e-245">**Entrepôt** – **commence par** – *61*</span><span class="sxs-lookup"><span data-stu-id="2169e-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="2169e-246">Notez les valeurs du **contenant** affichées.</span><span class="sxs-lookup"><span data-stu-id="2169e-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="2169e-247">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="2169e-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="2169e-248">Exécution du flux d’appareil mobile – Configuration de la confirmation de travail pour le produit</span><span class="sxs-lookup"><span data-stu-id="2169e-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="2169e-249">Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *61*.</span><span class="sxs-lookup"><span data-stu-id="2169e-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="2169e-250">Aller à **Sortant \> Création de prélèvement de groupement**.</span><span class="sxs-lookup"><span data-stu-id="2169e-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="2169e-251">La page **TÂCHE : Attribuer le travail au groupement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="2169e-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="2169e-252">Saisissez l’ID de travail de la commande client 1 pour l’affecter au poste de groupement 1.</span><span class="sxs-lookup"><span data-stu-id="2169e-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="2169e-253">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-254">Saisissez l’ID de travail de la commande client 2 pour l’affecter au poste de groupement 2.</span><span class="sxs-lookup"><span data-stu-id="2169e-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="2169e-255">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="2169e-256">La page **TÂCHE : Création de prélèvement de groupement : Prélèvement** apparaît et affiche *Article L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="2169e-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="2169e-257">Étant donné que le profil de groupement définit le nombre de postes sur 2, le système vous dirige automatiquement vers le premier prélèvement groupé : deux palettes (PL) d’article *L0101*.</span><span class="sxs-lookup"><span data-stu-id="2169e-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="2169e-258">A tout moment au cours des étapes suivantes, vous pouvez sélectionner l’onglet **Détails** pour afficher des informations supplémentaires sur la tâche, telles que le lieu de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="2169e-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="2169e-259">Définissez le champ **ARTICLE** sur *L0101*.</span><span class="sxs-lookup"><span data-stu-id="2169e-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="2169e-260">Cela confirme le numéro d’article, qui est requis pour cet élément de menu (vous l’avez configuré plus tôt en sélectionnant **Configuration de la confirmation de travail** sur la page **Élément de menu d’appareil mobile** lorsque vous avez créé cet élément de menu).</span><span class="sxs-lookup"><span data-stu-id="2169e-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="2169e-261">Saisissez le numéro de contenant associé à l’article à l’emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2169e-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="2169e-262">Vous choisirez deux palettes.</span><span class="sxs-lookup"><span data-stu-id="2169e-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="2169e-263">Définissez le champ **LP** sur *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="2169e-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="2169e-264">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="2169e-265">La page **TÂCHE : Tri : Création de prélèvement de groupement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="2169e-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="2169e-266">Ici, vous allez trier les deux palettes prélevées à un poste de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="2169e-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="2169e-267">Ce poste peut être un chariot ou un conteneur utilisé pour séparer le stock prélevé par la commande client.</span><span class="sxs-lookup"><span data-stu-id="2169e-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="2169e-268">Afficher les détails affichés pour l’élément (*L0101*) et la quantité (*20* unités) qui seront triés au poste 1 (pour la commande client 1).</span><span class="sxs-lookup"><span data-stu-id="2169e-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="2169e-269">Définissez le champ **POSTE S/O** sur *1*.</span><span class="sxs-lookup"><span data-stu-id="2169e-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="2169e-270">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-271">Afficher les détails affichés pour l’élément (*L0101*) et la quantité (*20* unités) qui seront triés au poste 2 (pour la commande client 2).</span><span class="sxs-lookup"><span data-stu-id="2169e-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="2169e-272">Définissez le champ **POSTE S/O** sur *2*.</span><span class="sxs-lookup"><span data-stu-id="2169e-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="2169e-273">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="2169e-274">La page **TÂCHE : Création de prélèvement de groupement : Prélèvement** apparaît et affiche *Article T0100 7 unités*.</span><span class="sxs-lookup"><span data-stu-id="2169e-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="2169e-275">Dans ce scénario, le poste 1 ne peut pas accepter la quantité totale d’articles qui doivent être prélevés pour exécuter la commande client 1.</span><span class="sxs-lookup"><span data-stu-id="2169e-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="2169e-276">Un poste doit être marqué comme plein.</span><span class="sxs-lookup"><span data-stu-id="2169e-276">A position must be marked as full.</span></span> <span data-ttu-id="2169e-277">Dans ce scénario, vous effectuerez un prélèvement partiel du deuxième article.</span><span class="sxs-lookup"><span data-stu-id="2169e-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="2169e-278">Le deuxième article sera partiellement sélectionné pour le poste 1, et un nouveau travail sera créé pour prélever la quantité restante pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="2169e-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="2169e-279">Sélectionnez le bouton Menu (parfois appelé hamburger ou bouton hamburger), puis sélectionnez **Poste complet**.</span><span class="sxs-lookup"><span data-stu-id="2169e-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="2169e-280">Identifiez le poste qui est plein et sélectionnez *1*.</span><span class="sxs-lookup"><span data-stu-id="2169e-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="2169e-281">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-282">Saisissez la quantité prélevée qui peut encore être prélevée au poste 1.</span><span class="sxs-lookup"><span data-stu-id="2169e-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="2169e-283">Le système peut déterminer quel numéro d’article est prélevé.</span><span class="sxs-lookup"><span data-stu-id="2169e-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="2169e-284">Entrez *2*.</span><span class="sxs-lookup"><span data-stu-id="2169e-284">Enter *2*.</span></span>
1. <span data-ttu-id="2169e-285">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-286">Confirmez le numéro d’article pour terminer le prélèvement de l’article restant au poste 2.</span><span class="sxs-lookup"><span data-stu-id="2169e-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="2169e-287">Définissez le champ **ARTICLE** sur *T0100*.</span><span class="sxs-lookup"><span data-stu-id="2169e-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="2169e-288">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-289">Entrez le contenant à partir duquel l’article est prélevé en définissant le champ **LP** sur *LPREPL04*.</span><span class="sxs-lookup"><span data-stu-id="2169e-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="2169e-290">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-291">Afficher les détails affichés pour l’élément (*T0100*) et la quantité (*2* unités) qui seront triés au poste 2 (pour la commande client 2).</span><span class="sxs-lookup"><span data-stu-id="2169e-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="2169e-292">Définissez le champ **POSTE S/O** sur *2*.</span><span class="sxs-lookup"><span data-stu-id="2169e-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="2169e-293">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="2169e-294">Afficher les détails affichés pour l’élément (*T0100*) et la quantité (*2* unités) qui seront triés au poste 1 (pour la commande client 1).</span><span class="sxs-lookup"><span data-stu-id="2169e-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="2169e-295">Définissez le champ **POSTE S/O** sur *1*.</span><span class="sxs-lookup"><span data-stu-id="2169e-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="2169e-296">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="2169e-297">La page **TÂCHE : Création de prélèvement de groupement : Rangement** apparaît.</span><span class="sxs-lookup"><span data-stu-id="2169e-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="2169e-298">Dans ce scénario, le prélèvement de groupement est terminé et l’utilisateur est invité à ranger les articles sélectionnés du poste 1 et du poste 2 à l’emplacement de préparation *STAGE01*.</span><span class="sxs-lookup"><span data-stu-id="2169e-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="2169e-299">Passez en revue les informations sur la page.</span><span class="sxs-lookup"><span data-stu-id="2169e-299">Review the information on the page.</span></span> <span data-ttu-id="2169e-300">Elle montre qu’une quantité totale de *44* sera placé à l’emplacement de préparation.</span><span class="sxs-lookup"><span data-stu-id="2169e-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="2169e-301">Sélectionnez **OK** (symbole de coche).</span><span class="sxs-lookup"><span data-stu-id="2169e-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="2169e-302">Vous recevez un message « Groupement terminé ».</span><span class="sxs-lookup"><span data-stu-id="2169e-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="2169e-303">Vous pouvez maintenant utiliser l’élément de menu **Prélèvement des ventes** pour prélever la quantité restante.</span><span class="sxs-lookup"><span data-stu-id="2169e-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="2169e-304">Vous pouvez ensuite utiliser l’élément de menu **Chargement des ventes** pour déplacer les éléments de l’emplacement de préparation vers le quai de chargement.</span><span class="sxs-lookup"><span data-stu-id="2169e-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>
