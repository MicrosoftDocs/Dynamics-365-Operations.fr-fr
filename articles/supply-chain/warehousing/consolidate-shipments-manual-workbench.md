---
title: Consolider les expéditions à l'aide de l'atelier de consolidation des expéditions
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées en expéditions ultérieurement à l'aide de l'atelier de consolidation des expéditions.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383769"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="f91cc-103">Consolider les expéditions à l'aide de l'atelier de consolidation des expéditions</span><span class="sxs-lookup"><span data-stu-id="f91cc-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f91cc-104">Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées en expéditions ultérieurement à l'aide de l'atelier de consolidation des expéditions.</span><span class="sxs-lookup"><span data-stu-id="f91cc-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="f91cc-105">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="f91cc-105">Make demo data available</span></span>

<span data-ttu-id="f91cc-106">Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f91cc-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f91cc-107">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l'entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="f91cc-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="f91cc-108">Configurer des stratégies de consolidation d'expédition et des filtres de produits</span><span class="sxs-lookup"><span data-stu-id="f91cc-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="f91cc-109">Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits.</span><span class="sxs-lookup"><span data-stu-id="f91cc-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="f91cc-110">Assurez-vous de faire ces exercices avant de continuer avec ce scénario.</span><span class="sxs-lookup"><span data-stu-id="f91cc-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="f91cc-111">Activer la fonctionnalité de consolidation manuelle des expéditions</span><span class="sxs-lookup"><span data-stu-id="f91cc-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="f91cc-112">Avant de pouvoir utiliser la fonctionnalité *Consolidation manuelle des expéditions*, vous devez l'activer dans votre système.</span><span class="sxs-lookup"><span data-stu-id="f91cc-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="f91cc-113">Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f91cc-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="f91cc-114">Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="f91cc-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f91cc-115">**Module :** *Gestion des entrepôts*</span><span class="sxs-lookup"><span data-stu-id="f91cc-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f91cc-116">**Nom de la fonctionnalité :** *Consolidation manuelle des expéditions*</span><span class="sxs-lookup"><span data-stu-id="f91cc-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="f91cc-117">Comme mentionné dans [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md), vous devez également activer la fonctionnalité *Consolider les expéditions* avant de pouvoir créer des stratégies.</span><span class="sxs-lookup"><span data-stu-id="f91cc-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="f91cc-118">Cependant, vous devriez déjà avoir terminé cette étape.</span><span class="sxs-lookup"><span data-stu-id="f91cc-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="f91cc-119">Créez les commandes client pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="f91cc-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="f91cc-120">Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler.</span><span class="sxs-lookup"><span data-stu-id="f91cc-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="f91cc-121">Vous devez travailler avec un entrepôt activé pour les processus d'entrepôt avancés (WMS).</span><span class="sxs-lookup"><span data-stu-id="f91cc-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="f91cc-122">À moins qu'un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.</span><span class="sxs-lookup"><span data-stu-id="f91cc-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="f91cc-123">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="f91cc-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="f91cc-124">Créer le jeu de commandes 1</span><span class="sxs-lookup"><span data-stu-id="f91cc-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="f91cc-125">Commandes client 1-1 et 1-2</span><span class="sxs-lookup"><span data-stu-id="f91cc-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="f91cc-126">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-127">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f91cc-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f91cc-128">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="f91cc-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="f91cc-129">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-130">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-131">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-132">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="f91cc-133">Commande client 1-3</span><span class="sxs-lookup"><span data-stu-id="f91cc-133">Sales order 1-3</span></span>

1. <span data-ttu-id="f91cc-134">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-135">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f91cc-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f91cc-136">**Mode de livraison :** *10*</span><span class="sxs-lookup"><span data-stu-id="f91cc-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="f91cc-137">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-138">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-139">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-140">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="f91cc-141">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-142">**Numéro d'article :** *A0002* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-143">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="f91cc-144">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="f91cc-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="f91cc-145">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="f91cc-146">Créer le jeu de commandes 2</span><span class="sxs-lookup"><span data-stu-id="f91cc-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="f91cc-147">Commandes client 2-1 et 2-2</span><span class="sxs-lookup"><span data-stu-id="f91cc-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="f91cc-148">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-149">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="f91cc-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="f91cc-150">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="f91cc-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="f91cc-151">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-152">**Numéro d'article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)</span><span class="sxs-lookup"><span data-stu-id="f91cc-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="f91cc-153">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-154">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="f91cc-155">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-156">**Numéro d'article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)</span><span class="sxs-lookup"><span data-stu-id="f91cc-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="f91cc-157">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="f91cc-158">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="f91cc-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="f91cc-159">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="f91cc-160">Créer le jeu de commandes 3</span><span class="sxs-lookup"><span data-stu-id="f91cc-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="f91cc-161">Commandes client 3-1 et 3-2</span><span class="sxs-lookup"><span data-stu-id="f91cc-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="f91cc-162">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-163">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f91cc-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f91cc-164">**Demande client :** *1*</span><span class="sxs-lookup"><span data-stu-id="f91cc-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="f91cc-165">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-166">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-167">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-168">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="f91cc-169">Commandes client 3-3 et 3-4</span><span class="sxs-lookup"><span data-stu-id="f91cc-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="f91cc-170">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-171">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="f91cc-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="f91cc-172">**Demande client :** *2*</span><span class="sxs-lookup"><span data-stu-id="f91cc-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="f91cc-173">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-174">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-175">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-176">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="f91cc-177">Créer le jeu de commandes 4</span><span class="sxs-lookup"><span data-stu-id="f91cc-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="f91cc-178">Commandes client 4-1 et 4-2</span><span class="sxs-lookup"><span data-stu-id="f91cc-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="f91cc-179">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-180">**Compte client :** *US-003*</span><span class="sxs-lookup"><span data-stu-id="f91cc-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="f91cc-181">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-182">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-183">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-184">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="f91cc-185">Commandes client 4-3 et 4-4</span><span class="sxs-lookup"><span data-stu-id="f91cc-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="f91cc-186">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-187">**Compte client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="f91cc-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="f91cc-188">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-189">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-190">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-191">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="f91cc-192">Commandes client 4-5 et 4-6</span><span class="sxs-lookup"><span data-stu-id="f91cc-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="f91cc-193">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-194">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="f91cc-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="f91cc-195">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="f91cc-195">**Site:** *6*</span></span>
    - <span data-ttu-id="f91cc-196">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="f91cc-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="f91cc-197">**Regroupement :** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="f91cc-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="f91cc-198">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-199">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-200">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-201">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="f91cc-202">Commandes client 4-7 et 4-8</span><span class="sxs-lookup"><span data-stu-id="f91cc-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="f91cc-203">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="f91cc-204">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="f91cc-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="f91cc-205">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="f91cc-205">**Site:** *6*</span></span>
    - <span data-ttu-id="f91cc-206">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="f91cc-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="f91cc-207">**Regroupement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="f91cc-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="f91cc-208">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f91cc-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="f91cc-209">**Numéro d'article :** *A0001* (un article auquel aucun filtre**Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="f91cc-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="f91cc-210">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="f91cc-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="f91cc-211">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f91cc-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="f91cc-212">Lancer les commandes dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f91cc-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="f91cc-213">Suivez ces étapes pour valider chaque commande client que vous avez créée pour ce scénario dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="f91cc-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="f91cc-214">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="f91cc-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="f91cc-215">Recherchez et sélectionnez la commande client à lancer.</span><span class="sxs-lookup"><span data-stu-id="f91cc-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="f91cc-216">Dans le volet Actions, sous l'onglet **Entrepôt**, sélectionnez **Actions \> Lancer dans l'entrepôt** pour lancer la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f91cc-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="f91cc-217">Répétez cette procédure pour chaque autre commande client que vous avez créée pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="f91cc-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="f91cc-218">Consolider les expéditions à l'aide de l'atelier de consolidation des expéditions</span><span class="sxs-lookup"><span data-stu-id="f91cc-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="f91cc-219">Allez dans **Gestion des entrepôts \> Lancement dans l'entrepôt \> Atelier de consolidation des expéditions**.</span><span class="sxs-lookup"><span data-stu-id="f91cc-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="f91cc-220">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="f91cc-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="f91cc-221">Dans la boîte de dialogue de l'éditeur de requête, sur l'onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :</span><span class="sxs-lookup"><span data-stu-id="f91cc-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="f91cc-222">**Table :** *Commandes client*</span><span class="sxs-lookup"><span data-stu-id="f91cc-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="f91cc-223">**Champ :** *Commande client*</span><span class="sxs-lookup"><span data-stu-id="f91cc-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="f91cc-224">**Critères :** Saisissez une liste séparée par des virgules des numéros de commande client pour chaque jeu de commandes que vous avez créé pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="f91cc-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="f91cc-225">Sélectionnez **OK** pour enregistrer votre requête et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f91cc-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="f91cc-226">Sélectionnez **Consolider les expéditions** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f91cc-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="f91cc-227">Sélectionnez toutes les expéditions, puis sélectionnez **Consolider** sur le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f91cc-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="f91cc-228">Vérifier les expéditions</span><span class="sxs-lookup"><span data-stu-id="f91cc-228">Verify the shipments</span></span>

<span data-ttu-id="f91cc-229">La procédure suivante vous permet de vérifier les expéditions qui ont été créées ou mises à jour suite à la consolidation des expéditions.</span><span class="sxs-lookup"><span data-stu-id="f91cc-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="f91cc-230">Utilisez-la pour passer en revue chaque jeu de commandes que vous avez créé pour ce scénario, puis passez en revue les sous-sections qui suivent pour vous assurer que vous avez obtenu les résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="f91cc-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="f91cc-231">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="f91cc-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="f91cc-232">Recherchez et sélectionnez l'expédition requise.</span><span class="sxs-lookup"><span data-stu-id="f91cc-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="f91cc-233">Si une stratégie de consolidation a été utilisée lors de la création ou de la mise à jour de l'expédition, elle doit apparaître dans le champ **Stratégie de consolidation d'expédition**.</span><span class="sxs-lookup"><span data-stu-id="f91cc-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="f91cc-234">Expéditions connexes pour le jeu de commandes 1</span><span class="sxs-lookup"><span data-stu-id="f91cc-234">Related shipments for order set 1</span></span>

<span data-ttu-id="f91cc-235">Deux expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="f91cc-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="f91cc-236">La première expédition contient trois lignes et a été créée à l'aide de la stratégie de consolidation des expéditions *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="f91cc-237">Le deuxième envoi, qui n'utilise pas le moyen de transport *Avion*, a été créé en utilisant la stratégie de consolidation des expéditions *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="f91cc-238">Expéditions connexes pour le jeu de commandes 2</span><span class="sxs-lookup"><span data-stu-id="f91cc-238">Related shipments for order set 2</span></span>

<span data-ttu-id="f91cc-239">Trois expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="f91cc-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="f91cc-240">La première expédition contient les articles *Inflammables*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="f91cc-241">Chacune des deux autres expéditions contient une ligne avec l'article *Explosif*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="f91cc-242">Expéditions connexes pour le jeu de commandes 3</span><span class="sxs-lookup"><span data-stu-id="f91cc-242">Related shipments for order set 3</span></span>

<span data-ttu-id="f91cc-243">Deux expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="f91cc-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="f91cc-244">La première expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *1*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="f91cc-245">La deuxième expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *2*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="f91cc-246">Expéditions connexes pour le jeu de commandes 4</span><span class="sxs-lookup"><span data-stu-id="f91cc-246">Related shipments for order set 4</span></span>

<span data-ttu-id="f91cc-247">Quatre expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="f91cc-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="f91cc-248">Les lignes des deux commandes pour le client *US-003* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="f91cc-249">Les lignes des deux commandes pour le client *US-004* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="f91cc-250">Les lignes des commandes client 4-5 et 4-6 pour le client *US-007* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="f91cc-251">Les lignes des commandes client 4-7 et 4-8 pour le client *US-007* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="f91cc-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f91cc-252">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f91cc-252">Additional resources</span></span>

- [<span data-ttu-id="f91cc-253">Stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="f91cc-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="f91cc-254">Configurer les stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="f91cc-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
