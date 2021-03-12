---
title: Consolider les expéditions à l'aide du champ Lancement dans l'entrepôt depuis l'atelier de planification des chargements
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l'entrepôt dans le même chargement et sont ensuite automatiquement consolidées en expéditions.
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
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: c0af6764742532cbe181c8a20e7bf783b0e6d7cf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983089"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="bd0ac-103">Consolider les expéditions à l'aide du champ Lancement dans l'entrepôt depuis l'atelier de planification des chargements</span><span class="sxs-lookup"><span data-stu-id="bd0ac-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd0ac-104">Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l'entrepôt dans le même chargement et sont ensuite automatiquement consolidées en expéditions.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="bd0ac-105">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="bd0ac-105">Make demo data available</span></span>

<span data-ttu-id="bd0ac-106">Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="bd0ac-107">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l'entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="bd0ac-108">Configurer des stratégies de consolidation d'expédition et des filtres de produits</span><span class="sxs-lookup"><span data-stu-id="bd0ac-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="bd0ac-109">Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="bd0ac-110">Assurez-vous de faire ces exercices avant de continuer avec ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="bd0ac-111">Créez les commandes client pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="bd0ac-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="bd0ac-112">Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="bd0ac-113">Vous devez travailler avec un entrepôt activé pour les processus d'entrepôt avancés (WMS).</span><span class="sxs-lookup"><span data-stu-id="bd0ac-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="bd0ac-114">À moins qu'un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="bd0ac-115">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="bd0ac-116">Créer le jeu de commandes 1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="bd0ac-117">Commande client 1-1</span><span class="sxs-lookup"><span data-stu-id="bd0ac-117">Sales order 1-1</span></span>

1. <span data-ttu-id="bd0ac-118">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-119">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bd0ac-120">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="bd0ac-121">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-122">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-123">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-124">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="bd0ac-125">Commande client 1-2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-125">Sales order 1-2</span></span>

1. <span data-ttu-id="bd0ac-126">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-127">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bd0ac-128">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="bd0ac-129">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-130">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-131">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-132">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="bd0ac-133">Commande client 1-3</span><span class="sxs-lookup"><span data-stu-id="bd0ac-133">Sales order 1-3</span></span>

1. <span data-ttu-id="bd0ac-134">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-135">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bd0ac-136">**Mode de livraison :** *10*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="bd0ac-137">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-138">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-139">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-140">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="bd0ac-141">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-142">**Numéro d'article :** *A0002* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-143">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="bd0ac-144">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="bd0ac-145">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="bd0ac-146">Créer le jeu de commandes 2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="bd0ac-147">Commandes client 2-1 et 2-2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="bd0ac-148">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-149">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="bd0ac-150">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-151">**Numéro d'article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="bd0ac-152">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-153">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="bd0ac-154">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-155">**Numéro d'article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="bd0ac-156">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="bd0ac-157">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="bd0ac-158">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la deuxième ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="bd0ac-159">Créer le jeu de commandes 3</span><span class="sxs-lookup"><span data-stu-id="bd0ac-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="bd0ac-160">Commandes client 3-1 et 3-2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="bd0ac-161">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-162">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bd0ac-163">**Demande client :** *1*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="bd0ac-164">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-165">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-166">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-167">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="bd0ac-168">Commandes client 3-3 et 3-4</span><span class="sxs-lookup"><span data-stu-id="bd0ac-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="bd0ac-169">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-170">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bd0ac-171">**Demande client :** *2*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="bd0ac-172">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-173">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-174">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-175">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="bd0ac-176">Créer le jeu de commandes 4</span><span class="sxs-lookup"><span data-stu-id="bd0ac-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="bd0ac-177">Commandes client 4-1 et 4-2</span><span class="sxs-lookup"><span data-stu-id="bd0ac-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="bd0ac-178">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-179">**Compte client :** *US-003*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="bd0ac-180">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-181">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-182">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-183">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="bd0ac-184">Commandes client 4-3 et 4-4</span><span class="sxs-lookup"><span data-stu-id="bd0ac-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="bd0ac-185">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-186">**Compte client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="bd0ac-187">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-188">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-189">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-190">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="bd0ac-191">Commandes client 4-5 et 4-6</span><span class="sxs-lookup"><span data-stu-id="bd0ac-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="bd0ac-192">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-193">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="bd0ac-194">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-194">**Site:** *6*</span></span>
    - <span data-ttu-id="bd0ac-195">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="bd0ac-196">**Regroupement :** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="bd0ac-197">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-198">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-199">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-200">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="bd0ac-201">Commandes client 4-7 et 4-8</span><span class="sxs-lookup"><span data-stu-id="bd0ac-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="bd0ac-202">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="bd0ac-203">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="bd0ac-204">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-204">**Site:** *6*</span></span>
    - <span data-ttu-id="bd0ac-205">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="bd0ac-206">**Regroupement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="bd0ac-207">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="bd0ac-208">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="bd0ac-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="bd0ac-209">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="bd0ac-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="bd0ac-210">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="bd0ac-211">Utilisez l'atelier de planification des chargements pour créer des chargements et les lancer dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="bd0ac-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="bd0ac-212">Suivez ces étapes pour créer un chargement pour chaque jeu de commandes que vous avez créé pour ce scénario, puis lancez-le dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="bd0ac-213">Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="bd0ac-214">Sur l'onglet **Lignes de vente**, recherchez et sélectionnez toutes les lignes de commande client dans l'un des jeux de commandes que vous avez créés pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="bd0ac-215">Sur le volet Actions, sur l'onglet **Approvisionnement et demande**, sélectionnez **Ajouter \> Dans un nouveau chargement** pour ajouter les lignes de commande sélectionnées à un nouveau chargement.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="bd0ac-216">Dans la boîte de dialogue **Affectation des modèles de chargement**, dans le champ **ID du modèle de chargement**, sélectionnez un modèle de chargement, tel que *Modèle de chargement standard*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="bd0ac-217">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="bd0ac-218">Dans la section **Chargements**, recherchez et sélectionnez le chargement que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="bd0ac-219">Sélectionnez **Lancer \> Lancement dans l'entrepôt** pour lancer le chargement sélectionné dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="bd0ac-220">Répétez cette procédure pour les trois autres jeux de commandes que vous avez créés pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="bd0ac-221">Vérifier les expéditions</span><span class="sxs-lookup"><span data-stu-id="bd0ac-221">Verify the shipments</span></span>

<span data-ttu-id="bd0ac-222">La procédure suivante vous permet de vérifier les expéditions qui ont été créées ou mises à jour suite à la consolidation des expéditions.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="bd0ac-223">Utilisez-la pour passer en revue chaque jeu de commandes que vous avez créé pour ce scénario, puis passez en revue les sous-sections qui suivent pour vous assurer que vous avez obtenu les résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="bd0ac-224">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="bd0ac-225">Recherchez et sélectionnez l'expédition requise.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="bd0ac-226">Si une stratégie de consolidation a été utilisée lors de la création ou de la mise à jour de l'expédition, elle doit apparaître dans le champ **Stratégie de consolidation d'expédition**.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="bd0ac-227">Lancer le jeu de commandes 1 dans un chargement</span><span class="sxs-lookup"><span data-stu-id="bd0ac-227">Release order set 1 in one load</span></span>

<span data-ttu-id="bd0ac-228">Deux expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="bd0ac-229">La première expédition contient trois lignes et a été créée à l'aide de la stratégie de consolidation des expéditions *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="bd0ac-230">Le deuxième envoi, qui n'utilise pas le moyen de transport *Avion*, a été créé en utilisant la stratégie de consolidation des expéditions *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="bd0ac-231">Lancer le jeu de commandes 2 dans un chargement</span><span class="sxs-lookup"><span data-stu-id="bd0ac-231">Release order set 2 in one load</span></span>

<span data-ttu-id="bd0ac-232">Trois expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="bd0ac-233">La première expédition contient les articles *Inflammables*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="bd0ac-234">Chacune des deux autres expéditions contient une ligne avec l'article *Explosif*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="bd0ac-235">Lancer le jeu de commandes 3 dans un chargement</span><span class="sxs-lookup"><span data-stu-id="bd0ac-235">Release order set 3 in one load</span></span>

<span data-ttu-id="bd0ac-236">Deux expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="bd0ac-237">La première expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *1*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="bd0ac-238">La deuxième expédition contient des lignes de commande provenant de la commande client où le champ **Demande client** est défini sur *2*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="bd0ac-239">Lancer le jeu de commandes 4 dans un chargement</span><span class="sxs-lookup"><span data-stu-id="bd0ac-239">Release order set 4 in one load</span></span>

<span data-ttu-id="bd0ac-240">Quatre expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="bd0ac-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="bd0ac-241">Les lignes des deux commandes pour le compte *US-003* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="bd0ac-242">Les lignes des deux commandes pour le compte *US-004* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="bd0ac-243">Les lignes des commandes client 4-5 et 4-6 pour le compte *US-007* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="bd0ac-244">Les lignes des commandes client 4-7 et 4-8 pour le compte *US-007* ont été regroupées en une seule expédition à l'aide de la stratégie de consolidation des expéditions *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="bd0ac-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd0ac-245">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bd0ac-245">Additional resources</span></span>

- [<span data-ttu-id="bd0ac-246">Stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="bd0ac-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="bd0ac-247">Configurer les stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="bd0ac-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
