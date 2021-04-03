---
title: Consolider les expéditions lorsque la stratégie de consolidation de l’expédition est remplacée à partir de la page Lancement dans l’entrepôt
description: Cette rubrique présente un scénario dans lequel une ou plusieurs lignes de vente doivent être validées manuellement dans l’entrepôt à partir de la page Lancement dans l’entrepôt et la stratégie de consolidation des expéditions définie par le système doit être remplacée avant la libération.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: be573f3a137fbd74ba2f5d8bb346e4bb9f9116c1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237105"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="89c51-103">Consolider les expéditions lorsque la stratégie de consolidation de l’expédition est remplacée à partir de la page Lancement dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="89c51-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89c51-104">Cette rubrique présente un scénario dans lequel une ou plusieurs lignes de vente doivent être validées manuellement dans l’entrepôt à partir de la page **Lancement dans l’entrepôt** et la stratégie de consolidation des expéditions définie par le système doit être remplacée avant la libération.</span><span class="sxs-lookup"><span data-stu-id="89c51-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="89c51-105">Un remplacement de la stratégie de consolidation des expéditions peut être nécessaire si, par exemple, une commande qui n’est généralement pas consolidée avec des expéditions en cours doit être consolidée avec des expéditions en cours.</span><span class="sxs-lookup"><span data-stu-id="89c51-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="89c51-106">Au cours du scénario, vous allez créer un ensemble de commandes client, puis remplacer la stratégie de consolidation des expéditions par défaut avant de lancer les commandes dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89c51-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="89c51-107">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="89c51-107">Make demo data available</span></span>

<span data-ttu-id="89c51-108">Le scénario de cette rubrique fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="89c51-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="89c51-109">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="89c51-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="89c51-110">Configurer des stratégies de consolidation d’expédition et des filtres de produits</span><span class="sxs-lookup"><span data-stu-id="89c51-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="89c51-111">Le scénario décrit ici suppose que vous avez déjà activé la fonctionnalité, effectué les exercices de la rubrique [Configurer les stratégies de consolidation de l’expédition](configure-shipment-consolidation-policies.md) et créé les stratégies et autres enregistrements qui y sont décrits.</span><span class="sxs-lookup"><span data-stu-id="89c51-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="89c51-112">Assurez-vous de faire ces exercices avant de continuer avec ce scénario.</span><span class="sxs-lookup"><span data-stu-id="89c51-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="89c51-113">Créez les commandes client pour ce scénario</span><span class="sxs-lookup"><span data-stu-id="89c51-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="89c51-114">Allez dans **Comptabilité client \> Commandes \> Toutes les commandes client** et créez trois commandes client identiques ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="89c51-114">Go to **Accounts receivable \> Orders \> All sales orders**, and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="89c51-115">**Compte client :** *US-002*</span><span class="sxs-lookup"><span data-stu-id="89c51-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="89c51-116">Ajoutez une ligne de commande possédant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="89c51-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="89c51-117">**Numéro d’article :** *A0001* (un article auquel aucun filtre **Code 4** n’est affecté)</span><span class="sxs-lookup"><span data-stu-id="89c51-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="89c51-118">**Quantité :** *1.00*</span><span class="sxs-lookup"><span data-stu-id="89c51-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="89c51-119">Sélectionnez **Stock \> Réservation**, puis, dans le volet Actions, sélectionnez **Réserver un lot** pour réserver la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="89c51-119">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="89c51-120">Validez les commandes client depuis la page Lancement dans l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="89c51-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="89c51-121">Suivez ces étapes pour remplacer la stratégie de consolidation des expéditions lors du lancement dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89c51-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="89c51-122">Allez dans **Gestion des entrepôts \> Lancement dans l’entrepôt \> Lancement dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89c51-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="89c51-123">Dans le volet supérieur, sélectionnez la première commande client que vous avez créée pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="89c51-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="89c51-124">Sélectionnez **Ajouter** pour ajouter la ligne dans le cadre du lancement dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89c51-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="89c51-125">Notez que la stratégie de consolidation d’expédition *Par défaut* est appliquée dans le volet inférieur.</span><span class="sxs-lookup"><span data-stu-id="89c51-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="89c51-126">Dans le volet inférieur, sélectionnez **Sélectionner une nouvelle stratégie de consolidation des expéditions**.</span><span class="sxs-lookup"><span data-stu-id="89c51-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="89c51-127">Sélectionnez une stratégie qui permet la consolidation avec d’autres expéditions en cours de la même stratégie.</span><span class="sxs-lookup"><span data-stu-id="89c51-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="89c51-128">Par exemple, sélectionnez la stratégie *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="89c51-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="89c51-129">Sélectionnez **Lancement dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89c51-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="89c51-130">Sélectionnez la deuxième et la troisième commande client que vous avez créée pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="89c51-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="89c51-131">Sélectionner **Ajouter** pour ajouter les lignes dans le cadre du lancement dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89c51-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="89c51-132">Notez que la stratégie *Par défaut* est appliquée dans le volet inférieur.</span><span class="sxs-lookup"><span data-stu-id="89c51-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="89c51-133">Sélectionnez la deuxième ligne, puis, dans le champ **Sélectionner une nouvelle stratégie de consolidation des expéditions**, sélectionnez la stratégie *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="89c51-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="89c51-134">Sélectionnez **Lancement dans l’entrepôt** pour les deux lignes.</span><span class="sxs-lookup"><span data-stu-id="89c51-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="89c51-135">Vérifier les expéditions</span><span class="sxs-lookup"><span data-stu-id="89c51-135">Verify the shipments</span></span>

<span data-ttu-id="89c51-136">Deux expéditions sont normalement créées :</span><span class="sxs-lookup"><span data-stu-id="89c51-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="89c51-137">La première expédition contient deux lignes et a été créée à l’aide de la stratégie de consolidation des expéditions *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="89c51-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="89c51-138">La deuxième expédition contient une ligne et a été créée à l’aide de la stratégie de consolidation des expéditions *Par défaut*.</span><span class="sxs-lookup"><span data-stu-id="89c51-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="89c51-139">Suivez ces étapes pour examiner les expéditions qui ont été créées.</span><span class="sxs-lookup"><span data-stu-id="89c51-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="89c51-140">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="89c51-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="89c51-141">Recherchez et sélectionnez l’expédition requise.</span><span class="sxs-lookup"><span data-stu-id="89c51-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="89c51-142">Dans le champ **Stratégie de consolidation d’expédition**, consultez la stratégie de consolidation utilisée lors de la création de l’expédition.</span><span class="sxs-lookup"><span data-stu-id="89c51-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89c51-143">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="89c51-143">Additional resources</span></span>

- [<span data-ttu-id="89c51-144">Stratégies de consolidation de l’expédition</span><span class="sxs-lookup"><span data-stu-id="89c51-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="89c51-145">Configurer les stratégies de consolidation de l’expédition</span><span class="sxs-lookup"><span data-stu-id="89c51-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]