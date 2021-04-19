---
title: Consolider les expéditions lorsqu’elles sont validées dans l’entrepôt à l’aide de l’option Lancement automatique des commandes client
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l’entrepôt dans la même procédure périodique de lancement dans l’entrepôt automatisée.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 82a95ecf196ef7c33831da7f4d03df629b17fa53
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807558"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="5719f-103">Consolider les expéditions lorsqu’elles sont validées dans l’entrepôt à l’aide de l’option Lancement automatique des commandes client</span><span class="sxs-lookup"><span data-stu-id="5719f-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5719f-104">Cette rubrique présente un scénario dans lequel plusieurs commandes sont lancées dans l’entrepôt dans la même procédure périodique de lancement dans l’entrepôt automatisée.</span><span class="sxs-lookup"><span data-stu-id="5719f-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="5719f-105">Les commandes seront automatiquement regroupées en expéditions, en fonction de règles définies comme stratégies de consolidation.</span><span class="sxs-lookup"><span data-stu-id="5719f-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="5719f-106">Au cours du scénario, vous allez créer des ensembles de commandes client et lancer chaque ensemble dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5719f-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="5719f-107">Vous passerez ensuite en revue les envois créés ou mis à jour pendant la consolidation des expéditions, en fonction des stratégies configurées.</span><span class="sxs-lookup"><span data-stu-id="5719f-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="5719f-108">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="5719f-108">Make demo data available</span></span>

<span data-ttu-id="5719f-109">Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5719f-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5719f-110">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="5719f-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="5719f-111">Configurer des stratégies de consolidation d’expédition et des filtres de produits</span><span class="sxs-lookup"><span data-stu-id="5719f-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="5719f-112">Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits.</span><span class="sxs-lookup"><span data-stu-id="5719f-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="5719f-113">Assurez-vous de faire ces exercices avant de continuer avec ce scénario.</span><span class="sxs-lookup"><span data-stu-id="5719f-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="5719f-114">Créez les commandes client pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="5719f-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="5719f-115">Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler.</span><span class="sxs-lookup"><span data-stu-id="5719f-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="5719f-116">Vous devez travailler avec un entrepôt activé pour les processus d’entrepôt avancés (WMS).</span><span class="sxs-lookup"><span data-stu-id="5719f-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="5719f-117">À moins qu’un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.</span><span class="sxs-lookup"><span data-stu-id="5719f-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="5719f-118">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="5719f-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="5719f-119">Créer le jeu de commandes 1</span><span class="sxs-lookup"><span data-stu-id="5719f-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="5719f-120">Commande client 1-1</span><span class="sxs-lookup"><span data-stu-id="5719f-120">Sales order 1-1</span></span>

1. <span data-ttu-id="5719f-121">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-122">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-123">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="5719f-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="5719f-124">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-125">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-126">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="5719f-127">Commande client 1-2</span><span class="sxs-lookup"><span data-stu-id="5719f-127">Sales order 1-2</span></span>

1. <span data-ttu-id="5719f-128">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-129">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-130">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="5719f-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="5719f-131">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-132">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-133">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="5719f-134">Commande client 1-3</span><span class="sxs-lookup"><span data-stu-id="5719f-134">Sales order 1-3</span></span>

1. <span data-ttu-id="5719f-135">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-136">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-137">**Mode de livraison :** *10*</span><span class="sxs-lookup"><span data-stu-id="5719f-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="5719f-138">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-139">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-140">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="5719f-141">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-142">**Numéro d’article :** *A0002* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-143">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="5719f-144">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="5719f-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="5719f-145">Créer le jeu de commandes 2</span><span class="sxs-lookup"><span data-stu-id="5719f-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="5719f-146">Commandes client 2-1 et 2-2</span><span class="sxs-lookup"><span data-stu-id="5719f-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="5719f-147">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-148">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="5719f-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="5719f-149">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-150">**Numéro d’article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)</span><span class="sxs-lookup"><span data-stu-id="5719f-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="5719f-151">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="5719f-152">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-153">**Numéro d’article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)</span><span class="sxs-lookup"><span data-stu-id="5719f-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="5719f-154">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="5719f-155">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="5719f-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="5719f-156">Créer le jeu de commandes 3</span><span class="sxs-lookup"><span data-stu-id="5719f-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="5719f-157">Commande client 3-1</span><span class="sxs-lookup"><span data-stu-id="5719f-157">Sales order 3-1</span></span>

1. <span data-ttu-id="5719f-158">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-159">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="5719f-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="5719f-160">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-161">**Numéro d’article :** *M9200* (un article où le filtre **Code 4** est défini sur *Inflammable*)</span><span class="sxs-lookup"><span data-stu-id="5719f-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="5719f-162">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="5719f-163">Ajoutez une deuxième ligne de commande avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-164">**Numéro d’article :** *M9201* (un article où le filtre **Code 4** est défini sur *Explosif*)</span><span class="sxs-lookup"><span data-stu-id="5719f-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="5719f-165">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="5719f-166">**Mode de livraison :** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="5719f-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="5719f-167">Cette commande est identique aux deux commandes que vous avez créées pour le jeu de commandes 2.</span><span class="sxs-lookup"><span data-stu-id="5719f-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="5719f-168">Cependant, elle est répertoriée comme son propre ensemble de commandes, car vous la publierez séparément plus tard dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="5719f-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="5719f-169">Créer le jeu de commandes 4</span><span class="sxs-lookup"><span data-stu-id="5719f-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="5719f-170">Commande client 4-1</span><span class="sxs-lookup"><span data-stu-id="5719f-170">Sales order 4-1</span></span>

1. <span data-ttu-id="5719f-171">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-172">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-173">**Bon de commande client :** *1*</span><span class="sxs-lookup"><span data-stu-id="5719f-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="5719f-174">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-175">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-176">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="5719f-177">Créer le jeu de commandes 5</span><span class="sxs-lookup"><span data-stu-id="5719f-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="5719f-178">Commandes client 5-1 et 5-2</span><span class="sxs-lookup"><span data-stu-id="5719f-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="5719f-179">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-180">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-181">**Demande client :** *2*</span><span class="sxs-lookup"><span data-stu-id="5719f-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="5719f-182">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-183">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-184">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="5719f-185">Commande client 5-3</span><span class="sxs-lookup"><span data-stu-id="5719f-185">Sales order 5-3</span></span>

1. <span data-ttu-id="5719f-186">Créez une commande client possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="5719f-187">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="5719f-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="5719f-188">**Bon de commande client :** *1*</span><span class="sxs-lookup"><span data-stu-id="5719f-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="5719f-189">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-190">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-191">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="5719f-192">Créer le jeu de commandes 6</span><span class="sxs-lookup"><span data-stu-id="5719f-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="5719f-193">Commandes client 6-1 et 6-2</span><span class="sxs-lookup"><span data-stu-id="5719f-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="5719f-194">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-195">**Compte client :** *US-003*</span><span class="sxs-lookup"><span data-stu-id="5719f-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="5719f-196">**Demande client :** *2*</span><span class="sxs-lookup"><span data-stu-id="5719f-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="5719f-197">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-198">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-199">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="5719f-200">Commandes client 6-3 et 6-4</span><span class="sxs-lookup"><span data-stu-id="5719f-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="5719f-201">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-202">**Compte client :** *US-004*</span><span class="sxs-lookup"><span data-stu-id="5719f-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="5719f-203">**Demande client :** *1*</span><span class="sxs-lookup"><span data-stu-id="5719f-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="5719f-204">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-205">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-206">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="5719f-207">Commandes client 6-5 et 6-6</span><span class="sxs-lookup"><span data-stu-id="5719f-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="5719f-208">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-209">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="5719f-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="5719f-210">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="5719f-210">**Site:** *6*</span></span>
    - <span data-ttu-id="5719f-211">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="5719f-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="5719f-212">**Regroupement :** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="5719f-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="5719f-213">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-214">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-215">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="5719f-216">Commandes client 6-7 et 6-8</span><span class="sxs-lookup"><span data-stu-id="5719f-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="5719f-217">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5719f-218">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="5719f-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="5719f-219">**Site :** *6*</span><span class="sxs-lookup"><span data-stu-id="5719f-219">**Site:** *6*</span></span>
    - <span data-ttu-id="5719f-220">**Entrepôt :** *61*</span><span class="sxs-lookup"><span data-stu-id="5719f-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="5719f-221">**Regroupement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="5719f-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="5719f-222">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="5719f-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5719f-223">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="5719f-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5719f-224">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5719f-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="5719f-225">Lancement automatique des commandes client dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="5719f-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="5719f-226">Pour chaque ensemble de commandes client que vous avez créé précédemment, vous devez exécuter une procédure de lancement automatique dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="5719f-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="5719f-227">Dans chaque cas, vous allez exécuter la [procédure basique de lancement en entrepôt](#release-procedure) qui est fournie ici.</span><span class="sxs-lookup"><span data-stu-id="5719f-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="5719f-228">Procédure basique de lancement en entrepôt</span><span class="sxs-lookup"><span data-stu-id="5719f-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="5719f-229">Pour chaque ensemble de commandes client que vous avez créé précédemment, vous exécuterez les trois procédures décrites dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="5719f-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="5719f-230">Mettre à jour le modèle de vague qui sera utilisé lors du lancement</span><span class="sxs-lookup"><span data-stu-id="5719f-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="5719f-231">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="5719f-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="5719f-232">Définissez le champ **Type de modèle de vague** sur *Expédition*.</span><span class="sxs-lookup"><span data-stu-id="5719f-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="5719f-233">Recherchez et sélectionnez le modèle de vague associé à l’entrepôt que vous avez utilisé dans les jeux de commandes que vous avez créés pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="5719f-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="5719f-234">Par exemple, si vous avez utilisé l’entrepôt *24*, sélectionnez le modèle de vague **Expédition par défaut 24**.</span><span class="sxs-lookup"><span data-stu-id="5719f-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="5719f-235">Si vous avez utilisé l’entrepôt *61*, sélectionnez le modèle de vague **Expédition 61**.</span><span class="sxs-lookup"><span data-stu-id="5719f-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="5719f-236">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5719f-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="5719f-237">Définissez l’option **Traiter la vague à la sortie dans l’entrepôt** sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="5719f-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="5719f-238">Lancer dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="5719f-238">Release to the warehouse</span></span>

1. <span data-ttu-id="5719f-239">Allez dans **Gestion des entrepôts \> Lancement dans l’entrepôt \> Lancement automatique des commandes client**.</span><span class="sxs-lookup"><span data-stu-id="5719f-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="5719f-240">Définissez le champ **Quantité à débloquer** sur *Tout*.</span><span class="sxs-lookup"><span data-stu-id="5719f-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="5719f-241">Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtre** pour ouvrir la boîte de dialogue de requête.</span><span class="sxs-lookup"><span data-stu-id="5719f-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="5719f-242">Dans l’onglet **Plage**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants sur la grille :</span><span class="sxs-lookup"><span data-stu-id="5719f-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="5719f-243">**Table :** *Commandes client*</span><span class="sxs-lookup"><span data-stu-id="5719f-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="5719f-244">**Table dérivée :** *Commande client*</span><span class="sxs-lookup"><span data-stu-id="5719f-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="5719f-245">**Champ :** *Commande client*</span><span class="sxs-lookup"><span data-stu-id="5719f-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="5719f-246">**Critères :** Saisissez une liste séparée par des virgules des numéros de commande client du jeu de commandes souhaité.</span><span class="sxs-lookup"><span data-stu-id="5719f-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="5719f-247">Cliquez sur **OK** pour enregistrer votre requête.</span><span class="sxs-lookup"><span data-stu-id="5719f-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="5719f-248">Cliquez sur **OK** pour démarrer la procédure *Lancement automatique dans l’entrepôt*.</span><span class="sxs-lookup"><span data-stu-id="5719f-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="5719f-249">Vérifier l’expédition créée ou mise à jour</span><span class="sxs-lookup"><span data-stu-id="5719f-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="5719f-250">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="5719f-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="5719f-251">Recherchez et sélectionnez l’expédition requise.</span><span class="sxs-lookup"><span data-stu-id="5719f-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="5719f-252">Si une stratégie de consolidation a été utilisée lors de la création ou de la mise à jour de l’expédition, elle doit apparaître dans le champ **Stratégie de consolidation d’expédition**.</span><span class="sxs-lookup"><span data-stu-id="5719f-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="5719f-253">Lancer les commandes client du jeu de commandes 1</span><span class="sxs-lookup"><span data-stu-id="5719f-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="5719f-254">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour libérer les commandes client du jeu de commandes 1.</span><span class="sxs-lookup"><span data-stu-id="5719f-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="5719f-255">Lorsque vous avez terminé, vous devriez voir que deux expéditions ont été créées :</span><span class="sxs-lookup"><span data-stu-id="5719f-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="5719f-256">La première expédition contient trois lignes et a été créée à l’aide de la stratégie de consolidation des expéditions *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="5719f-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="5719f-257">Le deuxième envoi, qui n’utilise pas le moyen de transport *Avion*, a été créé en utilisant la stratégie de consolidation des expéditions *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="5719f-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="5719f-258">Lancer les commandes client du jeu de commandes 2</span><span class="sxs-lookup"><span data-stu-id="5719f-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="5719f-259">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 2.</span><span class="sxs-lookup"><span data-stu-id="5719f-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="5719f-260">Lorsque vous avez terminé, vous devriez voir que trois expéditions ont été créées :</span><span class="sxs-lookup"><span data-stu-id="5719f-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="5719f-261">La première expédition contient les articles *Inflammables*.</span><span class="sxs-lookup"><span data-stu-id="5719f-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="5719f-262">Chacune des deux autres expéditions contient une ligne avec l’article *Explosif*.</span><span class="sxs-lookup"><span data-stu-id="5719f-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="5719f-263">Lancer les commandes client du jeu de commandes 3</span><span class="sxs-lookup"><span data-stu-id="5719f-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="5719f-264">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 3.</span><span class="sxs-lookup"><span data-stu-id="5719f-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="5719f-265">Une fois que vous avez terminé, vous devriez voir que les actions suivantes se sont produites :</span><span class="sxs-lookup"><span data-stu-id="5719f-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="5719f-266">Une expédition existante (celle créée lors du lancement du jeu de commandes 2 dans l’entrepôt) a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5719f-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="5719f-267">Une ligne avec l’article *Inflammable* a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5719f-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="5719f-268">Une nouvelle expédition a été créée et contient l’article *Explosif*.</span><span class="sxs-lookup"><span data-stu-id="5719f-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="5719f-269">Lancer les commandes client du jeu de commandes 4</span><span class="sxs-lookup"><span data-stu-id="5719f-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="5719f-270">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 4.</span><span class="sxs-lookup"><span data-stu-id="5719f-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="5719f-271">Lorsque vous avez terminé, vous devriez voir qu’une seule expédition existante (où le champ **Demande client** est défini sur *1*) a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5719f-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="5719f-272">Une nouvelle ligne y a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5719f-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="5719f-273">Lancer les commandes client du jeu de commandes 5</span><span class="sxs-lookup"><span data-stu-id="5719f-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="5719f-274">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 5.</span><span class="sxs-lookup"><span data-stu-id="5719f-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="5719f-275">Une fois que vous avez terminé, vous devriez voir que les actions suivantes se sont produites :</span><span class="sxs-lookup"><span data-stu-id="5719f-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="5719f-276">Une expédition existante (où le champ **Demande client** est défini sur *1*) a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5719f-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="5719f-277">Une ligne de la commande client 5-3 (où le champ **Demande client** est défini sur *1*) y a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5719f-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="5719f-278">Une nouvelle expédition a été créée, où les lignes des commandes client 5-1 et 5-2 sont regroupées en une seule expédition.</span><span class="sxs-lookup"><span data-stu-id="5719f-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="5719f-279">Lancer les commandes client du jeu de commandes 6</span><span class="sxs-lookup"><span data-stu-id="5719f-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="5719f-280">Suivez la [procédure basique de lancement en entrepôt](#release-procedure) pour lancer les commandes client du jeu de commandes 6.</span><span class="sxs-lookup"><span data-stu-id="5719f-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="5719f-281">Lorsque vous avez terminé, vous devriez voir que quatre expéditions ont été créées :</span><span class="sxs-lookup"><span data-stu-id="5719f-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="5719f-282">Les lignes des deux commandes pour le client *US-003* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="5719f-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="5719f-283">Les lignes des deux commandes pour le client *US-004* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="5719f-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="5719f-284">Les lignes des commandes client 6-5 et 6-6 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *Regroupement de commandes*.</span><span class="sxs-lookup"><span data-stu-id="5719f-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="5719f-285">Les lignes des commandes client 6-7 et 6-8 pour le client *US-007* ont été regroupées en une seule expédition à l’aide de la stratégie de consolidation des expéditions *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="5719f-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5719f-286">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="5719f-286">Additional resources</span></span>

- [<span data-ttu-id="5719f-287">Stratégies de consolidation de l’expédition</span><span class="sxs-lookup"><span data-stu-id="5719f-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="5719f-288">Configurer les stratégies de consolidation de l’expédition</span><span class="sxs-lookup"><span data-stu-id="5719f-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]