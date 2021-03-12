---
title: Consolider les expéditions manuellement à l'aide de la page Consolider les expéditions
description: Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées ultérieurement à l'aide de la page Consolider les expéditions.
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
ms.openlocfilehash: 0e580253de0d787b721c2f729ecc96db56b91af0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983013"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="62478-103">Consolider les expéditions manuellement à l'aide de la page Consolider les expéditions</span><span class="sxs-lookup"><span data-stu-id="62478-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62478-104">Cette rubrique présente un scénario dans lequel plusieurs commandes sont validées dans l'entrepôt puis consolidées ultérieurement à l'aide de la page **Consolider les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="62478-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="62478-105">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="62478-105">Make demo data available</span></span>

<span data-ttu-id="62478-106">Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="62478-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="62478-107">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l'entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="62478-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="62478-108">Configurer des stratégies de consolidation d'expédition et des filtres de produits</span><span class="sxs-lookup"><span data-stu-id="62478-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="62478-109">Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits.</span><span class="sxs-lookup"><span data-stu-id="62478-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="62478-110">Assurez-vous de faire ces exercices avant de continuer avec ce scénario.</span><span class="sxs-lookup"><span data-stu-id="62478-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="62478-111">Créez les commandes client pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="62478-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="62478-112">Commencez par créer une collection de commandes client avec lesquelles vous pouvez travailler.</span><span class="sxs-lookup"><span data-stu-id="62478-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="62478-113">Vous devez travailler avec un entrepôt activé pour les processus d'entrepôt avancés (WMS).</span><span class="sxs-lookup"><span data-stu-id="62478-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="62478-114">À moins qu'un autre entrepôt ne soit explicitement mentionné, ce même entrepôt doit être utilisé pour chacun des ensembles de commandes suivants.</span><span class="sxs-lookup"><span data-stu-id="62478-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="62478-115">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez une collection de commandes client dont les paramètres sont décrits dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="62478-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="62478-116">Créer les commandes client 1 et 2</span><span class="sxs-lookup"><span data-stu-id="62478-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="62478-117">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="62478-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62478-118">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="62478-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="62478-119">**Regroupement :** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="62478-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="62478-120">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="62478-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62478-121">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="62478-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62478-122">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62478-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62478-123">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="62478-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="62478-124">Créer les commandes client 3 et 4</span><span class="sxs-lookup"><span data-stu-id="62478-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="62478-125">Créez deux commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="62478-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="62478-126">**Compte client :** *US-007*</span><span class="sxs-lookup"><span data-stu-id="62478-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="62478-127">**Regroupement :** Laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="62478-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="62478-128">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="62478-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="62478-129">**Numéro d'article :** *A0001* (un article auquel aucun filtre **Code 4** n'est affecté)</span><span class="sxs-lookup"><span data-stu-id="62478-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="62478-130">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="62478-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="62478-131">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="62478-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="62478-132">Lancer les commandes dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="62478-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="62478-133">Suivez ces étapes pour valider chaque commande client que vous avez créée pour ce scénario dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="62478-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="62478-134">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="62478-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="62478-135">Recherchez et sélectionnez la commande client à lancer.</span><span class="sxs-lookup"><span data-stu-id="62478-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="62478-136">Dans le volet Actions, sous l'onglet **Entrepôt**, sélectionnez **Actions \> Lancer dans l'entrepôt** pour lancer la commande client sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="62478-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="62478-137">Répétez cette procédure pour chaque autre commande client que vous avez créée pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="62478-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="62478-138">Consolider les expéditions</span><span class="sxs-lookup"><span data-stu-id="62478-138">Consolidate shipments</span></span>

1. <span data-ttu-id="62478-139">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="62478-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="62478-140">Recherchez et sélectionnez un envoi créé lors de la validation de la commande client 1 dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="62478-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="62478-141">(Le champ **Stratégie de consolidation d'expédition** doit être défini sur *Regroupement de commandes*.)</span><span class="sxs-lookup"><span data-stu-id="62478-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="62478-142">Dans le volet Actions, sous l'onglet **Expéditions**, sélectionnez **Expéditions \> Consolider les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="62478-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="62478-143">Vérifiez les expéditions qui sont suggérées pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="62478-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="62478-144">Une seule expédition ayant la même stratégie doit être suggérée pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="62478-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="62478-145">Fermez la page **Consolidation des expéditions**.</span><span class="sxs-lookup"><span data-stu-id="62478-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="62478-146">Recherchez et sélectionnez un envoi créé lors de la validation de la commande client 3 dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="62478-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="62478-147">(Le champ **Stratégie de consolidation d'expédition** doit être défini sur *Par défaut*.)</span><span class="sxs-lookup"><span data-stu-id="62478-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="62478-148">Dans le volet Actions, sous l'onglet **Expéditions**, sélectionnez **Expéditions \> Consolider les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="62478-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="62478-149">Vérifiez qu'aucune expédition n'est suggérée pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="62478-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="62478-150">Sélectionnez **Afficher les filtres**.</span><span class="sxs-lookup"><span data-stu-id="62478-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="62478-151">Dans le volet **Filtres**, supprimez le filtre **Numéro de commande**, puis sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="62478-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="62478-152">Vérifiez les expéditions qui sont suggérées pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="62478-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="62478-153">Une seule expédition ayant la même stratégie doit être suggérée pour la consolidation.</span><span class="sxs-lookup"><span data-stu-id="62478-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62478-154">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="62478-154">Additional resources</span></span>

- [<span data-ttu-id="62478-155">Stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="62478-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="62478-156">Configurer les stratégies de consolidation de l'expédition</span><span class="sxs-lookup"><span data-stu-id="62478-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)