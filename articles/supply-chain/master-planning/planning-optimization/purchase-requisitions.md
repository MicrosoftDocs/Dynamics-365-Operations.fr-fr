---
title: Demandes d’achat
description: Cette rubrique décrit comment les demandes d’achat sont prises en charge dans Optimisation de la planification.
author: ChristianRytt
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 564f87fe78e79107feb103f953ed4769e4734aa1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808038"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="65b6d-103">Demandes d’achat</span><span class="sxs-lookup"><span data-stu-id="65b6d-103">Purchase requisitions</span></span>

<span data-ttu-id="65b6d-104">La planification générale peut réapprovisionner les demandes d’achat approuvées.</span><span class="sxs-lookup"><span data-stu-id="65b6d-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="65b6d-105">Par conséquent, pour couvrir les demandes d’achat, les utilisateurs n’ont pas besoin d’utiliser un workflow pour créer des commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="65b6d-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="65b6d-106">À la place, les demandes d’achat peuvent être couvertes par la planification générale.</span><span class="sxs-lookup"><span data-stu-id="65b6d-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="65b6d-107">En raison de cette fonctionnalité, une demande d’achat peut produire une commande fournisseur, un ordre de transfert ou un ordre de fabrication, selon la valeur de **Type d’ordre prévisionnel** définie pour le produit associé.</span><span class="sxs-lookup"><span data-stu-id="65b6d-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="65b6d-108">Activer les plans généraux pour inclure des demandes</span><span class="sxs-lookup"><span data-stu-id="65b6d-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="65b6d-109">Pour inclure des demandes lors du calcul de la couverture pour un plan général, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="65b6d-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="65b6d-110">Accédez à **Planification générale** \> **Paramétrage** \> **Plans** \> **Plans généraux**.</span><span class="sxs-lookup"><span data-stu-id="65b6d-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="65b6d-111">Créez ou sélectionnez un plan général.</span><span class="sxs-lookup"><span data-stu-id="65b6d-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="65b6d-112">Dans le raccourci **Général**, définissez l’option **Inclure les demandes** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="65b6d-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="65b6d-113">Répétez les étapes 2 et 3 pour chaque plan général supplémentaire dans lequel vous souhaitez inclure des demandes.</span><span class="sxs-lookup"><span data-stu-id="65b6d-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="65b6d-114">Plage de gestion des demandes approuvées</span><span class="sxs-lookup"><span data-stu-id="65b6d-114">Approved requisitions time fence</span></span>

<span data-ttu-id="65b6d-115">La *plage de gestion des demandes approuvées* établit jusqu’où dans le temps (en jours) un plan général inclura la demande des demandes de réapprovisionnement approuvées.</span><span class="sxs-lookup"><span data-stu-id="65b6d-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="65b6d-116">Vous pouvez définir une plage de gestion des demandes approuvées à la fois au niveau du groupe de couverture et au niveau du plan général.</span><span class="sxs-lookup"><span data-stu-id="65b6d-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="65b6d-117">Définir la plage de gestion des demandes approuvées pour un groupe de couverture</span><span class="sxs-lookup"><span data-stu-id="65b6d-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="65b6d-118">Accédez à **Planification** \> **Paramétrage** \> **Couverture** \> **Groupes de couverture**.</span><span class="sxs-lookup"><span data-stu-id="65b6d-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**.</span></span>
1. <span data-ttu-id="65b6d-119">Créez ou sélectionnez un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="65b6d-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="65b6d-120">Dans le raccourci **Autre**, définissez le champ **Plage de gestion des demandes approuvées (jours)** sur le nombre de jours à inclure dans la plage de gestion.</span><span class="sxs-lookup"><span data-stu-id="65b6d-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="65b6d-121">Répétez les étapes 2 et 3 pour chaque groupe de couverture supplémentaire dans lequel vous souhaitez définir une plage de gestion des demandes approuvées.</span><span class="sxs-lookup"><span data-stu-id="65b6d-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="65b6d-122">Définir la plage de gestion des demandes approuvées pour des plans généraux individuels</span><span class="sxs-lookup"><span data-stu-id="65b6d-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="65b6d-123">Lorsque vous définissez une plage de gestion des demandes approuvées pour un plan général individuel, le paramètre remplace le paramètre de plage de gestion pour tout groupe de couverture applicable.</span><span class="sxs-lookup"><span data-stu-id="65b6d-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="65b6d-124">Accédez à **Planification générale** \> **Paramétrage** \> **Plans** \> **Plans généraux**.</span><span class="sxs-lookup"><span data-stu-id="65b6d-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="65b6d-125">Créez ou sélectionnez un plan général.</span><span class="sxs-lookup"><span data-stu-id="65b6d-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="65b6d-126">Dans le raccourci **Plages de gestion en jours**, définissez le champ **Plage de gestion des demandes approuvées (jours)** sur le nombre de jours à inclure dans la plage de gestion.</span><span class="sxs-lookup"><span data-stu-id="65b6d-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="65b6d-127">Répétez les étapes 2 et 3 pour chaque plan général supplémentaire dans lequel vous souhaitez définir une plage de gestion des demandes approuvées.</span><span class="sxs-lookup"><span data-stu-id="65b6d-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65b6d-128">**Prochainement :** les plages de gestion des demandes approuvées ne sont pas encore prises en charge pour l’optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="65b6d-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="65b6d-129">Jusqu’à ce qu’elles soient prises en charge, toutes les valeurs que vous entrez dans le champ **Plage de gestion des demandes approuvées (jours)** seront ignorées.</span><span class="sxs-lookup"><span data-stu-id="65b6d-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="65b6d-130">Approvisionnement indépendant, indépendamment du code de couverture</span><span class="sxs-lookup"><span data-stu-id="65b6d-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="65b6d-131">Les demandes d’achat sont toujours couvertes par les ordres prévisionnels indépendants, quel que soit le code de couverture.</span><span class="sxs-lookup"><span data-stu-id="65b6d-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="65b6d-132">Ce comportement garantit une traçabilité et des workflows précis entre les demandes d’achat et les ordres de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="65b6d-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="65b6d-133">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="65b6d-133">Example 1</span></span>

<span data-ttu-id="65b6d-134">Un produit est configuré pour avoir une valeur de **Code de couverture** de *Min/max*. Il a les statuts de stock et de demande suivants :</span><span class="sxs-lookup"><span data-stu-id="65b6d-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="65b6d-135">Quantité de stock disponible= 10.</span><span class="sxs-lookup"><span data-stu-id="65b6d-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="65b6d-136">Quantité de stock minimale = 15.</span><span class="sxs-lookup"><span data-stu-id="65b6d-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="65b6d-137">Quantité de stock maximale = 20.</span><span class="sxs-lookup"><span data-stu-id="65b6d-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="65b6d-138">Il existe une demande d’achat pour une pièce.</span><span class="sxs-lookup"><span data-stu-id="65b6d-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="65b6d-139">La date demandée est Aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="65b6d-139">It has a requested date of today.</span></span>

<span data-ttu-id="65b6d-140">Lors de l’exécution de la planification générale, deux ordres prévisionnels sont créés : un pour 10 pièces pour réapprovisionner le stock à la quantité maximale et un pour une pièce pour réapprovisionner la demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="65b6d-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="65b6d-141">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="65b6d-141">Example 2</span></span>

<span data-ttu-id="65b6d-142">Un produit est configuré pour avoir une valeur de **Code de couverture** de *Min/max*. Il a les statuts de stock et de demande suivants :</span><span class="sxs-lookup"><span data-stu-id="65b6d-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="65b6d-143">Quantité de stock disponible= 17.</span><span class="sxs-lookup"><span data-stu-id="65b6d-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="65b6d-144">Quantité de stock minimale = 15.</span><span class="sxs-lookup"><span data-stu-id="65b6d-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="65b6d-145">Quantité de stock maximale = 20.</span><span class="sxs-lookup"><span data-stu-id="65b6d-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="65b6d-146">Il existe une demande d’achat pour une pièce.</span><span class="sxs-lookup"><span data-stu-id="65b6d-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="65b6d-147">La date demandée est Aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="65b6d-147">It has a requested date of today.</span></span>

<span data-ttu-id="65b6d-148">Lors de l’exécution de la planification générale, un ordre prévisionnel pour une pièce est créé pour réapprovisionner la demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="65b6d-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="65b6d-149">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="65b6d-149">Example 3</span></span>

<span data-ttu-id="65b6d-150">Un produit est configuré pour avoir une valeur de **Code de couverture** de *Période* et une période de sept jours.</span><span class="sxs-lookup"><span data-stu-id="65b6d-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="65b6d-151">Il a les statuts de stock, de commande client et de demande suivants :</span><span class="sxs-lookup"><span data-stu-id="65b6d-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="65b6d-152">Quantité de stock disponible= 0.</span><span class="sxs-lookup"><span data-stu-id="65b6d-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="65b6d-153">Il existe une commande client de cinq pièces.</span><span class="sxs-lookup"><span data-stu-id="65b6d-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="65b6d-154">La date d’expédition prévue est Aujourd’hui plus un jour.</span><span class="sxs-lookup"><span data-stu-id="65b6d-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="65b6d-155">Il existe une demande d’achat pour trois pièces.</span><span class="sxs-lookup"><span data-stu-id="65b6d-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="65b6d-156">La date demandée est Aujourd’hui plus trois jours.</span><span class="sxs-lookup"><span data-stu-id="65b6d-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="65b6d-157">Lors de l’exécution de la planification générale, deux ordres prévisionnels sont créés : un pour trois pièces pour réapprovisionner la demande d’achat et un pour cinq pièces pour réapprovisionner la demande de commande client.</span><span class="sxs-lookup"><span data-stu-id="65b6d-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="65b6d-158">Une fois qu’un ordre prévisionnel lié à une demande d’achat est confirmé, le moteur de planification conserve le lien avec la demande d’achat.</span><span class="sxs-lookup"><span data-stu-id="65b6d-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="65b6d-159">S’il s’avère par la suite que l’ordre confirmé n’indique pas une quantité nécessaire pour traiter la demande d’achat, le système crée un nouvel ordre prévisionnel pour la différence.</span><span class="sxs-lookup"><span data-stu-id="65b6d-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="65b6d-160">Pour plus d’informations sur les demandes d’achat, voir [Présentation générale de la demande d’achat](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="65b6d-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]