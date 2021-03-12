---
title: Contrôle qualité
description: Cette rubrique fournit des informations sur la fonctionnalité de Contrôle qualité. Cette fonctionnalité permet aux magasiniers d’effectuer des contrôles ponctuels rapides de la qualité lorsqu’ils reçoivent des articles dans la zone du quai d’arrivée.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 585ca933726cb932290f8abf8504aeb13848a0e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996249"
---
# <a name="quality-check"></a><span data-ttu-id="9f93f-104">Contrôle qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f93f-105">La fonctionnalité *Contrôle qualité* permet aux manutentionnaires d’effectuer des contrôles ponctuels rapides de la qualité lorsqu’ils reçoivent des articles dans la zone du quai d’arrivée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="9f93f-106">Ces contrôles ponctuels sont utiles lorsque les collaborateurs inspectent l’emballage ou d’autres parties facilement reconnaissables d’un article.</span><span class="sxs-lookup"><span data-stu-id="9f93f-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="9f93f-107">La fonctionnalité guide les collaborateurs pour qu’ils examinent rapidement si quelque chose est manifestement défectueux ou endommagé avant de ranger le stock à son emplacement de stockage.</span><span class="sxs-lookup"><span data-stu-id="9f93f-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="9f93f-108">Cette fonctionnalité est une alternative au processus de contrôle de qualité standard.</span><span class="sxs-lookup"><span data-stu-id="9f93f-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="9f93f-109">Elle offre plus de flexibilité et un traitement plus rapide.</span><span class="sxs-lookup"><span data-stu-id="9f93f-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="9f93f-110">Lorsque vous utilisez cette fonctionnalité, l’arrivée et le contrôle de qualité se déroulent de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="9f93f-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="9f93f-111">Lorsqu’une livraison arrive, un magasinier enregistre l’arrivée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="9f93f-112">Le collaborateur scanne également un contenant pour enregistrer l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="9f93f-113">Le collaborateur effectue un contrôle qualité rapide et enregistre le résultat (réussite ou échec) pour ce contenant.</span><span class="sxs-lookup"><span data-stu-id="9f93f-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="9f93f-114">Une des actions suivantes se produit :</span><span class="sxs-lookup"><span data-stu-id="9f93f-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="9f93f-115">Si le contrôle qualité est réussi, le contenant est accepté et guidé vers un emplacement de réception, comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="9f93f-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="9f93f-116">Si le contrôle qualité échoue, le contenant est rejeté et le travail de stockage existant pour lui est redirigé vers un autre emplacement pour une inspection plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="9f93f-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="9f93f-117">Un nouvel ordre de qualité est créé.</span><span class="sxs-lookup"><span data-stu-id="9f93f-117">A new quality order is created.</span></span> <span data-ttu-id="9f93f-118">Pour afficher l’ordre de qualité créé à partir de l’échec du contrôle qualité, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="9f93f-119">Ce processus peut également être configuré pour que tous les contenants scannés soient immédiatement détournés vers l’emplacement de contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="9f93f-120">Activez la fonctionnalité de contrôle qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="9f93f-121">Avant de pouvoir utiliser la fonctionnalité *Contrôle qualité*, vous devez l’activer sur votre système.</span><span class="sxs-lookup"><span data-stu-id="9f93f-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="9f93f-122">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9f93f-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="9f93f-123">Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="9f93f-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="9f93f-124">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="9f93f-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="9f93f-125">**Nom de la fonctionnalité :** *Contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="9f93f-126">Configurer la fonctionnalité pour l’exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="9f93f-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="9f93f-127">Cette section fournit des instructions et un exemple de la configuration de la fonctionnalité *Contrôle qualité* et prépare des exemples de données pour l’exemple de scénario fourni plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9f93f-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="9f93f-128">Rendre les exemple de données disponibles</span><span class="sxs-lookup"><span data-stu-id="9f93f-128">Make sample data available</span></span>

<span data-ttu-id="9f93f-129">Pour utiliser [l’exemple de scénario](#example-scenario) à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées.</span><span class="sxs-lookup"><span data-stu-id="9f93f-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="9f93f-130">En outre, vous devez sélectionner l’entité juridique **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="9f93f-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="9f93f-131">Modèle de contrôle qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-131">Quality check template</span></span>

<span data-ttu-id="9f93f-132">Le modèle de contrôle qualité définit les règles pour effectuer des contrôles ponctuels rapides de la qualité au moment de la réception.</span><span class="sxs-lookup"><span data-stu-id="9f93f-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="9f93f-133">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèle de contrôle qualité**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="9f93f-134">Cliquez sur **Nouveau** pour ajouter un modèle à la grille.</span><span class="sxs-lookup"><span data-stu-id="9f93f-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="9f93f-135">Définissez les valeurs suivantes pour définir le nouveau modèle :</span><span class="sxs-lookup"><span data-stu-id="9f93f-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="9f93f-136">**Nom du modèle de contrôle qualité :** *Contrôle à quai*</span><span class="sxs-lookup"><span data-stu-id="9f93f-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="9f93f-137">Entrez un nom qui identifie les stratégies appliquées pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="9f93f-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="9f93f-138">**Politique d’acceptation :** *Inviter l’utilisateur*</span><span class="sxs-lookup"><span data-stu-id="9f93f-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="9f93f-139">Spécifiez si les utilisateurs doivent être invités à accepter ou rejeter la qualité de stock pendant qu’ils traitent le travail, ou si la qualité doit être automatiquement rejetée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="9f93f-140">Les options disponibles sont *Rejet automatique* et *Inviter l’utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="9f93f-141">**Stratégie de traitement de la qualité :** *Créer un ordre de qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="9f93f-142">Sélectionnez la stratégie qui doit être utilisée lorsque la qualité du stock est rejetée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="9f93f-143">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="9f93f-143">The following options are available:</span></span>

        - <span data-ttu-id="9f93f-144">*Créer un travail uniquement* – Créez simplement du travail pour faciliter le mouvement des stocks.</span><span class="sxs-lookup"><span data-stu-id="9f93f-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="9f93f-145">*Créer un ordre de qualité* – Créez un ordre de qualité pour faciliter les tests de qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="9f93f-146">**Groupe de test :** *Pièce jointe*</span><span class="sxs-lookup"><span data-stu-id="9f93f-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="9f93f-147">Spécifiez le groupe de tests à utiliser dans l’ordre de qualité créé.</span><span class="sxs-lookup"><span data-stu-id="9f93f-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="9f93f-148">Les groupes de tests sont créés dans le module **Gestion des stocks**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="9f93f-149">Laissez l’option **Test destructif** désactivée pour le groupe de tests.</span><span class="sxs-lookup"><span data-stu-id="9f93f-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="9f93f-150">Cette option définit si l’échantillon doit être détruit dans le cadre des tests effectués au sein du groupe de tests.</span><span class="sxs-lookup"><span data-stu-id="9f93f-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="9f93f-151">Si un test destructif est utilisé, le système génère une transaction de stock à la création d’un ordre de qualité pour un article.</span><span class="sxs-lookup"><span data-stu-id="9f93f-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="9f93f-152">Le nouveau mouvement de stock anticipe la réduction de stock pour la quantité de test.</span><span class="sxs-lookup"><span data-stu-id="9f93f-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="9f93f-153">La réduction de stock a lieu lorsque l’ordre de qualité est terminé, via les étapes de validation.</span><span class="sxs-lookup"><span data-stu-id="9f93f-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="9f93f-154">Le mouvement de stock est identifié comme un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="9f93f-155">Classe de travail – Contrôle qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-155">Work class – Quality check</span></span>

<span data-ttu-id="9f93f-156">Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail que des magasiniers peuvent traiter sur un périphérique portable.</span><span class="sxs-lookup"><span data-stu-id="9f93f-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="9f93f-157">Accédez à **Gestion des entrepôts \> Configuration \> Travail \> Classes de travail**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="9f93f-158">Sélectionnez **Nouveau** pour créer une classe de travail.</span><span class="sxs-lookup"><span data-stu-id="9f93f-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="9f93f-159">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="9f93f-160">**ID classe de travail :** *Contrôle QC*</span><span class="sxs-lookup"><span data-stu-id="9f93f-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9f93f-161">Entrez un nom qui identifie la classe de travail.</span><span class="sxs-lookup"><span data-stu-id="9f93f-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="9f93f-162">**Description :** *Contrôle QC*</span><span class="sxs-lookup"><span data-stu-id="9f93f-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="9f93f-163">Entrez une brève description qui indique à quoi sert la classe de travail.</span><span class="sxs-lookup"><span data-stu-id="9f93f-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="9f93f-164">**Type d’ordre de travail :** *Qualité du contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="9f93f-165">Sélectionnez le type d’ordre de travail créé par la classe de travail.</span><span class="sxs-lookup"><span data-stu-id="9f93f-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="9f93f-166">Lorsque vous configurez le travail de contrôle qualité, sélectionnez toujours *Qualité du contrôle qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="9f93f-167">Sur l’organisateur **Types d’emplacement de rangement valides**, laissez le champ **Type d’emplacement** vide.</span><span class="sxs-lookup"><span data-stu-id="9f93f-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="9f93f-168">Si vous sélectionnez un type d’emplacement, vous limitez les emplacements où les articles peuvent être placés après leur prélèvement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="9f93f-169">Ce champ est utilisé lors de tentatives d’une directive d’emplacement pour résoudre l’emplacement, ou lorsqu’un magasinier spécifie manuellement l’emplacement pour l’élément du menu du périphérique portable.</span><span class="sxs-lookup"><span data-stu-id="9f93f-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="9f93f-170">Pour plus d’informations sur les classes de travail et comment les créer, voir [Créer une classe de travail](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="9f93f-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="9f93f-171">Modèle de travail</span><span class="sxs-lookup"><span data-stu-id="9f93f-171">Work template</span></span>

<span data-ttu-id="9f93f-172">Modèles de travail vous permet de définir les opérations de travail qui doivent être effectuées dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9f93f-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="9f93f-173">Généralement, les opérations de travail d’entrepôt se composent d’une paire d’actions : un magasinier prend un stock disponible dans un emplacement et le range dans un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="9f93f-174">Un modèle de travail pour le contrôle qualité définit les opérations de travail pour effectuer des contrôles qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="9f93f-175">Commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="9f93f-175">Purchase orders</span></span>

1. <span data-ttu-id="9f93f-176">Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="9f93f-177">Dans l’en-tête, définissez le champ **Type d’ordre de travail** sur *Commandes fournisseur*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="9f93f-178">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9f93f-179">Sélectionnez un modèle de travail qui doit inclure une étape de contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="9f93f-180">Dans la section **Aperçu**, dans le champ **Modèle de travail**, sélectionnez *51 Réception CF*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="9f93f-181">Dans la section **Détails du modèle de travail**, notez que la grille a deux lignes existantes : une pour *Prélèvement* et une pour *Rangement*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="9f93f-182">Dans la section **Détails du modèle de travail**, sélectionnez **Nouveau** pour ajouter une ligne de contrôle qualité à la grille.</span><span class="sxs-lookup"><span data-stu-id="9f93f-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="9f93f-183">Notez que le champ **Numéro de ligne** de la nouvelle ligne est défini sur *3*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="9f93f-184">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="9f93f-184">On the new line, set the following values.</span></span> <span data-ttu-id="9f93f-185">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="9f93f-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9f93f-186">**Type de travail :** *Contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="9f93f-187">**ID classe de travail :** *Achat*</span><span class="sxs-lookup"><span data-stu-id="9f93f-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="9f93f-188">**Nom du modèle de contrôle qualité :** *Contrôle à quai*</span><span class="sxs-lookup"><span data-stu-id="9f93f-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="9f93f-189">Sélectionnez l’ID unique de la classe de travail.</span><span class="sxs-lookup"><span data-stu-id="9f93f-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="9f93f-190">Vous utilisez cette valeur pour configurer les options de menu de l’appareil mobile et les types de travail que ces options de menu peuvent traiter.</span><span class="sxs-lookup"><span data-stu-id="9f93f-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="9f93f-191">Dans le volet Actions, sélectionnez **Enregistrer** pour enregistrer votre travail jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="9f93f-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="9f93f-192">Vous recevez un message d’information indiquant « Non valide - Le contrôle qualité doit intervenir directement après un prélèvement ».</span><span class="sxs-lookup"><span data-stu-id="9f93f-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="9f93f-193">Par conséquent, vous devez modifier la valeur du **Numéro de ligne** de la ligne que vous venez d’ajouter.</span><span class="sxs-lookup"><span data-stu-id="9f93f-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="9f93f-194">Suivez ces étapes pour modifier la valeur du **Numéro de ligne** pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="9f93f-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="9f93f-195">Dans la section **Détails du modèle de travail**, sélectionnez la ligne où le champ **Type de travail** est défini sur *Contrôle qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="9f93f-196">Sélectionnez le bouton **Déplacer vers le haut** ou **Déplacer vers le bas** pour déplacer la ligne *Contrôle qualité* pour qu’elle se situe après la ligne *Prélèvement*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="9f93f-197">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="9f93f-198">Qualité dans le contrôle qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-198">Quality in quality check</span></span>

<span data-ttu-id="9f93f-199">Ensuite, créez un modèle de travail pour le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="9f93f-200">Dans l’en-tête de la page **Modèles de travail**, modifiez la valeur du champ **Type d’ordre de travail** sur *Qualité du contrôle qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="9f93f-201">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille dans la section **Vue d’ensemble**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="9f93f-202">Dans la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9f93f-203">**Modèle de travail :** *51 Contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="9f93f-204">Entrez un nom pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="9f93f-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="9f93f-205">**Description du modèle de travail :** *51 Contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="9f93f-206">Sur le volet Action, sélectionnez **Enregistrer** pour rendre la section **Détails du modèle de travail** disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="9f93f-207">Alors que le nouveau modèle est toujours sélectionné dans la section **Aperçu**, sélectionnez **Nouveau** dans la section **Détails du modèle de travail** pour y ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="9f93f-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="9f93f-208">Dans la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9f93f-209">**Type de travail :** *Choisir*</span><span class="sxs-lookup"><span data-stu-id="9f93f-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="9f93f-210">**ID classe de travail :** *Contrôle QC*</span><span class="sxs-lookup"><span data-stu-id="9f93f-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9f93f-211">Sélectionnez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="9f93f-212">Dans la section **Détails du modèle de travail**, sélectionnez **Nouveau** à nouveau pour ajouter une autre ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="9f93f-213">Dans la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9f93f-214">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="9f93f-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="9f93f-215">**ID classe de travail :** *Contrôle QC*</span><span class="sxs-lookup"><span data-stu-id="9f93f-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9f93f-216">Sélectionnez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="9f93f-217">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9f93f-218">Pour plus d’informations sur les modèles de travail, voir [Contrôle du travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md)</span><span class="sxs-lookup"><span data-stu-id="9f93f-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="9f93f-219">Directive d’emplacement – Échecs de qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-219">Location directive – Quality failures</span></span>

<span data-ttu-id="9f93f-220">Les instructions d’emplacement sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock.</span><span class="sxs-lookup"><span data-stu-id="9f93f-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="9f93f-221">Par exemple, dans une transaction de commande client, une instruction d’emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés.</span><span class="sxs-lookup"><span data-stu-id="9f93f-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="9f93f-222">Vous devez configurer une règle de directive d’emplacement pour définir la manière dont les contrôles qualité échoués seront traités.</span><span class="sxs-lookup"><span data-stu-id="9f93f-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="9f93f-223">Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="9f93f-224">Dans le volet gauche, définissez le champ **Type d’ordre de travail** sur *commandes fournisseur* pour travailler avec des directives d’emplacement de ce type.</span><span class="sxs-lookup"><span data-stu-id="9f93f-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="9f93f-225">Dans le volet Actions, sélectionnez **Nouveau** pour créer une directive d’emplacement pour les contrôles qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="9f93f-226">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="9f93f-227">**Souche de N° :** Acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="9f93f-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="9f93f-228">**Nom :** *51 Vers qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="9f93f-229">Dans l’organisateur **Directives d’emplacement**, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="9f93f-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="9f93f-230">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="9f93f-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9f93f-231">**Type de travail :** *Put*</span><span class="sxs-lookup"><span data-stu-id="9f93f-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="9f93f-232">**Site :** *5*</span><span class="sxs-lookup"><span data-stu-id="9f93f-232">**Site:** *5*</span></span>
    - <span data-ttu-id="9f93f-233">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="9f93f-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="9f93f-234">Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer votre directive et rendre l’organisateur **Lignes** disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="9f93f-235">Dans l’organisateur **Lignes**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="9f93f-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="9f93f-236">Sur la nouvelle ligne, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="9f93f-236">On the new line, set the following values.</span></span> <span data-ttu-id="9f93f-237">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="9f93f-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9f93f-238">**Quantité de départ :** *1*</span><span class="sxs-lookup"><span data-stu-id="9f93f-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="9f93f-239">**Quantité d’arrivée :** *1000000*</span><span class="sxs-lookup"><span data-stu-id="9f93f-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="9f93f-240">Sur le volet Action, sélectionnez **Enregistrer** pour enregistrer la nouvelle ligne et rendre l’organisateur **Actions de directive d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="9f93f-241">Bien que la nouvelle ligne soit toujours sélectionnée sur l’organisateur **Lignes**, sélectionnez **Nouveau** sur l’organisateur **Actions de directive d’emplacement** pour ajouter une ligne à la grille ici, afin que vous puissiez configurer une action pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="9f93f-242">Dans la nouvelle ligne, définissez le champ **Nom** sur *Qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="9f93f-243">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="9f93f-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="9f93f-244">Sur le volet Action, sélectionnez **Enregistrer** pour rendre le bouton **Modifier la requête** de l’organisateur **Actions d’instruction d’emplacement** disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="9f93f-245">Bien que la ligne que vous venez d’ajouter est toujours sélectionnée sur l’organisateur **Actions de directive d’emplacement**, sélectionnez **Modifier la requête** pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier la requête pour l’action.</span><span class="sxs-lookup"><span data-stu-id="9f93f-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="9f93f-246">Sous l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne dans la requête.</span><span class="sxs-lookup"><span data-stu-id="9f93f-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="9f93f-247">Dans la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9f93f-248">**Table :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="9f93f-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9f93f-249">**Table dérivée :** *Emplacements*</span><span class="sxs-lookup"><span data-stu-id="9f93f-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9f93f-250">**Champ :** *Emplacement*</span><span class="sxs-lookup"><span data-stu-id="9f93f-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="9f93f-251">**Critères :** *QMS*</span><span class="sxs-lookup"><span data-stu-id="9f93f-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="9f93f-252">L’emplacement *QMS* est un emplacement d’entrepôt pour la qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="9f93f-253">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9f93f-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="9f93f-254">Vous devez maintenant modifier la séquence des instructions d’emplacement de commande fournisseur avec l’entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="9f93f-255">Enregistrez la nouvelle directive d’emplacement *51 Vers qualité*, actualisez la page et sélectionnez la directive d’emplacement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9f93f-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="9f93f-256">Ensuite, utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** sur le volet Actions pour mettre la directive d’emplacement pour l’entrepôt *51* dans l’ordre suivant.</span><span class="sxs-lookup"><span data-stu-id="9f93f-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="9f93f-257">(Avant de sélectionner **Déplacer vers le haut** ou **Déplacer vers le bas**, vous devez sélectionner une directive d’emplacement dans la liste.)</span><span class="sxs-lookup"><span data-stu-id="9f93f-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="9f93f-258">51 Vers qualité</span><span class="sxs-lookup"><span data-stu-id="9f93f-258">51 To Quality</span></span>
    2. <span data-ttu-id="9f93f-259">51 CF Direct</span><span class="sxs-lookup"><span data-stu-id="9f93f-259">51 PO Direct</span></span>
    3. <span data-ttu-id="9f93f-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="9f93f-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="9f93f-261">Options de menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="9f93f-261">Mobile device menu items</span></span>

<span data-ttu-id="9f93f-262">Configurez un élément de menu afin que les appareils mobiles puissent exécuter la fonction **Contrôle qualité**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="9f93f-263">Rangement d’achat</span><span class="sxs-lookup"><span data-stu-id="9f93f-263">Purchase putaway</span></span>

1. <span data-ttu-id="9f93f-264">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="9f93f-265">Dans la liste sélectionnez l’élément de menu **Rangement d’achat**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="9f93f-266">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9f93f-267">Dans la section **Classes de travail**, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="9f93f-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="9f93f-268">Dans la nouvelle ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9f93f-269">**ID classe de travail :** *Contrôle QC*</span><span class="sxs-lookup"><span data-stu-id="9f93f-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9f93f-270">Saisissez le nom de la [classe de travail](#work-class) que vous avez créée précédemment pour le travail de contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="9f93f-271">**Type d’ordre de travail :** *Qualité du contrôle qualité*</span><span class="sxs-lookup"><span data-stu-id="9f93f-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="9f93f-272">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="9f93f-273">Réception de ligne de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="9f93f-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="9f93f-274">Accédez à **Gestion des entrepôts \> Configuration \> Appareil mobile \> Options de menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="9f93f-275">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9f93f-276">Dans l’en-tête, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="9f93f-277">**Nom de l’option de menu :** *Réception de ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="9f93f-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="9f93f-278">**Titre :** *Réception de ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="9f93f-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="9f93f-279">**Mode :** *Travail*</span><span class="sxs-lookup"><span data-stu-id="9f93f-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="9f93f-280">**Utiliser un travail existant :** *Non*</span><span class="sxs-lookup"><span data-stu-id="9f93f-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="9f93f-281">Dans l’organisateur **Général**, définissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="9f93f-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="9f93f-282">Acceptez les valeurs par défaut pour les champs restants.</span><span class="sxs-lookup"><span data-stu-id="9f93f-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9f93f-283">**Processus de création du travail :** *Réception et rangement de la ligne de commande fournisseur*</span><span class="sxs-lookup"><span data-stu-id="9f93f-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="9f93f-284">**Générer un contenant :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="9f93f-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="9f93f-285">**Modèle de travail :** *51 CF Réception*</span><span class="sxs-lookup"><span data-stu-id="9f93f-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="9f93f-286">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="9f93f-287">Ajouter l’option de menu à un menu d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="9f93f-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="9f93f-288">Allez dans **Gestion des entrepôts \> Configuration \> Appareil mobile \> Menu d’appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="9f93f-289">Dans le volet de gauche, sélectionnez le menu **Entrant**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="9f93f-290">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9f93f-291">Dans la colonne **Menus et éléments de menus disponibles**, sélectionnez le nouvel élément de menu **Réception de ligne de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="9f93f-292">Sélectionnez le bouton en forme de flèche à droite pour déplacer **Réception de ligne de CF** vers la colonne **Structure du menu**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="9f93f-293">Dans la colonne **Structure du menu**, sélectionnez **Réception de la ligne de CF**, puis sélectionnez le bouton de flèche vers le haut ou vers le bas pour déplacer l’élément de menu vers la position souhaitée dans le menu de l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="9f93f-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="9f93f-294">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="9f93f-295">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="9f93f-295">Example scenario</span></span>

<span data-ttu-id="9f93f-296">Après avoir mis à disposition tous les exemples de données décrits précédemment et les avoir configurés, vous pouvez suivre ce scénario pour essayer la fonctionnalité *Contrôle qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="9f93f-297">Les valeurs affichées dans ce scénario supposent que vous travaillez avec les données de démonstration standard, que vous avez sélectionné l’entité juridique **USMF** et que vous avez préparé les exemples d’enregistrements décrits plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9f93f-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="9f93f-298">Ce scénario sert également d’exemple pour indiquer comment la fonctionnalité peut être utilisée dans un cadre de production.</span><span class="sxs-lookup"><span data-stu-id="9f93f-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="9f93f-299">Créer une commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="9f93f-299">Create a purchase order</span></span>

1. <span data-ttu-id="9f93f-300">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="9f93f-301">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9f93f-302">Dans la boîte de dialogue **Créer une commande fournisseur**, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9f93f-303">**Compte fournisseur :** *104*</span><span class="sxs-lookup"><span data-stu-id="9f93f-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="9f93f-304">**Entrepôt :** *51*</span><span class="sxs-lookup"><span data-stu-id="9f93f-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="9f93f-305">Sélectionnez **OK** pour fermer la boîte de dialogue et ouvrir la nouvelle commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f93f-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="9f93f-306">Sur l’organisateur **Lignes de commande fournisseur**, la grille contient une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="9f93f-307">Sur cette ligne, définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f93f-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="9f93f-308">**Numéro d’article :** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9f93f-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="9f93f-309">**Quantité :** *3*</span><span class="sxs-lookup"><span data-stu-id="9f93f-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="9f93f-310">**Unité :** *PL*</span><span class="sxs-lookup"><span data-stu-id="9f93f-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="9f93f-311">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="9f93f-312">Réception du contrôle qualité du processus</span><span class="sxs-lookup"><span data-stu-id="9f93f-312">Process quality check receiving</span></span>

<span data-ttu-id="9f93f-313">Une fois la commande fournisseur créée, elle peut être reçue en utilisant l’élément de menu **Réception de la ligne de CF** et la fonctionnalité du *Contrôle qualité*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="9f93f-314">Recevoir la palette 1</span><span class="sxs-lookup"><span data-stu-id="9f93f-314">Receive pallet 1</span></span>

1. <span data-ttu-id="9f93f-315">Connectez-vous à l’application d’entrepôt en tant qu’utilisateur de l’entrepôt *51*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="9f93f-316">(Entrez *51* comme ID utilisateur et *1* comme mot de passe.)</span><span class="sxs-lookup"><span data-stu-id="9f93f-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="9f93f-317">Allez à **Entrant \> Réception de la ligne de CF**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="9f93f-318">Dans le champ **PONUM**, entrez le numéro de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f93f-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="9f93f-319">Confirmez le numéro de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f93f-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="9f93f-320">Dans le champ **LINENUM**, entrez le numéro de la ligne de la commande fournisseur en cours de réception.</span><span class="sxs-lookup"><span data-stu-id="9f93f-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="9f93f-321">Comme la commande ne comporte qu’une seule ligne dans ce scénario, vous entrerez *1* dans le champ **LINENUM** pour chaque étape de réception.</span><span class="sxs-lookup"><span data-stu-id="9f93f-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="9f93f-322">Confirmez le numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-322">Confirm the line number.</span></span>
1. <span data-ttu-id="9f93f-323">Dans le champ **QTY**, entrez la quantité à recevoir.</span><span class="sxs-lookup"><span data-stu-id="9f93f-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="9f93f-324">Du fait que la commande fournisseur concerne trois palettes (*PL*) dans ce scénario, et il y a trois étapes de réception, vous allez saisir *1* dans le champ **QTY** pour chaque étape de réception.</span><span class="sxs-lookup"><span data-stu-id="9f93f-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="9f93f-325">Confirmez la quantité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-325">Confirm the quantity.</span></span>

    <span data-ttu-id="9f93f-326">La page **Contrôle qualité** qui apparaît n’a pas de champs de saisie.</span><span class="sxs-lookup"><span data-stu-id="9f93f-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="9f93f-327">Il n’a que le bouton de confirmation (coche) en bas et le bouton Menu (**≡**) au sommet.</span><span class="sxs-lookup"><span data-stu-id="9f93f-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="9f93f-328">(Le bouton Menu est parfois appelé le menu hamburger ou bouton hamburger.) Pour accélérer le processus de contrôle qualité, lorsque la palette passe le contrôle qualité, l’utilisateur confirme simplement la page **Contrôle qualité**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="9f93f-329">![Page Contrôle qualité](media/quality-check.png "Page Contrôle qualité")</span><span class="sxs-lookup"><span data-stu-id="9f93f-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="9f93f-330">Sélectionnez le bouton de confirmation pour réussir le contrôle qualité de la palette 1 de la ligne 1.</span><span class="sxs-lookup"><span data-stu-id="9f93f-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="9f93f-331">La page **Commandes fournisseur : Rangement** qui apparaît montre les détails du travail de rangement :</span><span class="sxs-lookup"><span data-stu-id="9f93f-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9f93f-332">**LOC :** Le système a déterminé l’emplacement</span><span class="sxs-lookup"><span data-stu-id="9f93f-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="9f93f-333">Cet emplacement est l’emplacement de stockage désigné pour la réception des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f93f-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="9f93f-334">**LP :** ID de contenant généré par le système</span><span class="sxs-lookup"><span data-stu-id="9f93f-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9f93f-335">**Article :** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9f93f-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9f93f-336">**Qté :** *1 PL : 100 unités*</span><span class="sxs-lookup"><span data-stu-id="9f93f-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9f93f-337">La description de l’article est également affichée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-337">The item description is also shown.</span></span>

1. <span data-ttu-id="9f93f-338">Confirmez le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="9f93f-339">Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="9f93f-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9f93f-340">Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.</span><span class="sxs-lookup"><span data-stu-id="9f93f-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="9f93f-341">Recevoir la palette 2</span><span class="sxs-lookup"><span data-stu-id="9f93f-341">Receive pallet 2</span></span>

<span data-ttu-id="9f93f-342">Pour ce scénario, la palette 2 sera rejetée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="9f93f-343">Dans le champ **LINENUM**, entrez *1* et confirmez le numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="9f93f-344">Le champ **QTY** est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-344">The **QTY** field is now available.</span></span> <span data-ttu-id="9f93f-345">Entrez *1* et confirmez la quantité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="9f93f-346">La page **Contrôle qualité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="9f93f-346">The **Quality check** page appears.</span></span> <span data-ttu-id="9f93f-347">Pour cette réception, la palette sera rejetée pour qualité, et elle sera mise dans l’emplacement de qualité *QMS*.</span><span class="sxs-lookup"><span data-stu-id="9f93f-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="9f93f-348">Sélectionnez le bouton Menu (**≡**) en haut de la page, puis, dans le menu, sélectionnez **Rejeter**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="9f93f-349">Sur la page **Tâche** qui apparaît, entrez **QMS** comme emplacement de *Rangement* où envoyer la palette pour une inspection plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="9f93f-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="9f93f-350">La page **Qualité du contrôle qualité : Rangement** qui apparaît montre les détails du travail de rangement :</span><span class="sxs-lookup"><span data-stu-id="9f93f-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9f93f-351">**LOC :** *QMS*</span><span class="sxs-lookup"><span data-stu-id="9f93f-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="9f93f-352">Cet emplacement est l’emplacement de stockage désigné pour la réception de la qualité rejetée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="9f93f-353">**LP :** ID de contenant généré par le système</span><span class="sxs-lookup"><span data-stu-id="9f93f-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9f93f-354">**Article :** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9f93f-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9f93f-355">**Qté :** *1 PL : 100 unités*</span><span class="sxs-lookup"><span data-stu-id="9f93f-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9f93f-356">La description de l’article est également affichée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-356">The item description is also shown.</span></span>

1. <span data-ttu-id="9f93f-357">Confirmez le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="9f93f-358">Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="9f93f-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9f93f-359">Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.</span><span class="sxs-lookup"><span data-stu-id="9f93f-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="9f93f-360">Vous avez maintenant terminé le contrôle qualité et créé un ordre de qualité pour la palette rejetée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="9f93f-361">Pour afficher l’ordre créé, accédez à **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.</span><span class="sxs-lookup"><span data-stu-id="9f93f-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="9f93f-362">Les tests d’ordre de qualité peuvent maintenant être traités.</span><span class="sxs-lookup"><span data-stu-id="9f93f-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="9f93f-363">Les tests de qualité ne sont pas traités dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9f93f-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="9f93f-364">Pour plus d’informations sur la gestion de la qualité, voir [Présentation de la gestion de la qualité](../inventory/enable-quality-management.md)</span><span class="sxs-lookup"><span data-stu-id="9f93f-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="9f93f-365">Recevoir la palette 3</span><span class="sxs-lookup"><span data-stu-id="9f93f-365">Receive pallet 3</span></span>

<span data-ttu-id="9f93f-366">Pour ce scénario, la palette 3 sera acceptée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="9f93f-367">Dans le champ **LINENUM**, entrez *1* et confirmez le numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="9f93f-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="9f93f-368">Le champ **QTY** est maintenant disponible.</span><span class="sxs-lookup"><span data-stu-id="9f93f-368">The **QTY** field is now available.</span></span> <span data-ttu-id="9f93f-369">Entrez *1* et confirmez la quantité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="9f93f-370">La page **Contrôle qualité** apparaît.</span><span class="sxs-lookup"><span data-stu-id="9f93f-370">The **Quality check** page appears.</span></span> <span data-ttu-id="9f93f-371">Pour cette réception, la palette sera acceptée pour qualité, et elle sera mise dans l’emplacement de rangement en vrac.</span><span class="sxs-lookup"><span data-stu-id="9f93f-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="9f93f-372">Sélectionnez le bouton de confirmation pour réussir le contrôle qualité.</span><span class="sxs-lookup"><span data-stu-id="9f93f-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="9f93f-373">La page **Commandes fournisseur : Rangement** qui apparaît montre les détails du travail de rangement :</span><span class="sxs-lookup"><span data-stu-id="9f93f-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9f93f-374">**LOC :** Le système a déterminé l’emplacement</span><span class="sxs-lookup"><span data-stu-id="9f93f-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="9f93f-375">Cet emplacement est l’emplacement de stockage désigné pour la réception des commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9f93f-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="9f93f-376">**LP :** ID de contenant généré par le système</span><span class="sxs-lookup"><span data-stu-id="9f93f-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9f93f-377">**Article :** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9f93f-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9f93f-378">**Qté :** *1 PL : 100 unités*</span><span class="sxs-lookup"><span data-stu-id="9f93f-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9f93f-379">La description de l’article est également affichée.</span><span class="sxs-lookup"><span data-stu-id="9f93f-379">The item description is also shown.</span></span>

1. <span data-ttu-id="9f93f-380">Confirmez le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="9f93f-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="9f93f-381">Sur la page **Tâche** de réception de la ligne de la commande fournisseur, vous recevez un message « Travail terminé ».</span><span class="sxs-lookup"><span data-stu-id="9f93f-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9f93f-382">Le champ **LINENUM** est disponible pour que vous puissiez commencer à recevoir la palette suivante.</span><span class="sxs-lookup"><span data-stu-id="9f93f-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="9f93f-383">Sélectionnez le bouton Menu (**≡**) en haut de la page, puis, dans le menu, sélectionnez **Annuler** pour revenir au menu.</span><span class="sxs-lookup"><span data-stu-id="9f93f-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="9f93f-384">Vous pouvez maintenant fermer l’application mobile.</span><span class="sxs-lookup"><span data-stu-id="9f93f-384">You can now close the mobile app.</span></span>
