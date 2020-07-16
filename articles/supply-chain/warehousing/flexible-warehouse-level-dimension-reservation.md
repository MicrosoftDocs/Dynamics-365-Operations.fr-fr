---
title: Politique de réservation de dimension flexible au niveau de l'entrepôt
description: Cette rubrique décrit la politique de réservation de stock qui permet aux entreprises qui vendent des produits suivis par lots et exécutent leur logistique en tant qu'opérations activées par WMS de réserver des lots spécifiques pour les commandes client, même si la hiérarchie de réservation associée aux produits interdit la réservation de lots spécifiques.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: ec80346126713cc604b00e6ca7f6e8f4c242dc6f
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530303"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="e89e0-103">Politique de réservation de dimension flexible au niveau de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e89e0-104">Lorsqu'une hiérarchie de réservation de stock de type « Batch-below\[location\] » est associée aux produits, les entreprises qui vendent des produits suivis par lots et gèrent leur logistique en tant qu'opérations activées pour Microsoft Dynamics 365 Warehouse Management System (WMS) ne peuvent pas réserver des lots spécifiques de ces produits pour les commandes client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="e89e0-105">Cette rubrique décrit la politique de réservation de stock qui permet à ces entreprises de réserver des lots spécifiques, même lorsque les produits sont associés avec une hiérarchie de réservation « Batch-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="e89e0-106">Hiérarchie de réservation du stock</span><span class="sxs-lookup"><span data-stu-id="e89e0-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="e89e0-107">Cette section résume la hiérarchie de réservation de stock existante.</span><span class="sxs-lookup"><span data-stu-id="e89e0-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="e89e0-108">Elle se concentre sur la façon dont les articles suivis par lots et suivis en série sont traités.</span><span class="sxs-lookup"><span data-stu-id="e89e0-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="e89e0-109">La hiérarchie de réservation de stock impose que, en ce qui concerne les dimensions de stockage, l'ordre à la demande porte les dimensions obligatoires du site, de l'entrepôt et du statut du stock, tandis que la logique d'entrepôt est responsable d'affecter un emplacement aux quantités demandées et de réserver l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="e89e0-110">En d'autres termes, lors des interactions entre la commande à la demande et les opérations de l'entrepôt, la commande à la demande devrait indiquer d'où la commande doit être expédiée (c'est-à-dire quel site et quel entrepôt).</span><span class="sxs-lookup"><span data-stu-id="e89e0-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="e89e0-111">L'entrepôt s'appuie ensuite sur sa logique pour trouver la quantité requise dans les locaux de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="e89e0-112">Cependant, pour refléter le modèle opérationnel de l'entreprise, les dimensions de suivi (numéros de lot et de série) sont soumises à plus de flexibilité.</span><span class="sxs-lookup"><span data-stu-id="e89e0-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="e89e0-113">Une hiérarchie de réservation de stock peut prendre en charge des scénarios dans lesquels les conditions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="e89e0-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="e89e0-114">L'entreprise s'appuie sur ses opérations d'entrepôt pour gérer le prélèvement des quantités qui ont des numéros de lot ou de série, après que les quantités ont été trouvées dans l'espace de stockage de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="e89e0-115">Ce modèle est souvent appelé *Batch-below\[location\]*.</span><span class="sxs-lookup"><span data-stu-id="e89e0-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="e89e0-116">Il est généralement utilisé lorsque l'identification du lot ou du numéro de série d'un produit n'est pas importante pour les clients qui adressent la demande à l'entreprise vendeuse.</span><span class="sxs-lookup"><span data-stu-id="e89e0-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="e89e0-117">Si les numéros de lot ou de série font partie de la spécification de commande d'un client et qu'ils sont enregistrés sur la commande à la demande, les opérations d'entrepôt qui trouvent les quantités dans l'entrepôt sont limitées par les numéros spécifiques demandés et ne sont pas autorisées à les modifier.</span><span class="sxs-lookup"><span data-stu-id="e89e0-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="e89e0-118">Ce modèle est souvent appelé *Batch-above\[location\]*.</span><span class="sxs-lookup"><span data-stu-id="e89e0-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="e89e0-119">Dans ces scénarios, la difficulté est qu'une seule hiérarchie de réservation de stock peut être affectée à chaque produit lancé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="e89e0-120">Par conséquent, pour que le WMS gère les articles suivis, une fois que l'affectation de la hiérarchie a déterminé le moment où le numéro de lot ou de série doit être réservé (soit lors de la prise de la commande à la demande, soit pendant le travail de prélèvement en entrepôt), ce délai ne peut pas être modifié sur une base ad hoc.</span><span class="sxs-lookup"><span data-stu-id="e89e0-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="e89e0-121">Réservation flexible pour les articles suivis par lots</span><span class="sxs-lookup"><span data-stu-id="e89e0-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="e89e0-122">Scénario d'entreprise</span><span class="sxs-lookup"><span data-stu-id="e89e0-122">Business scenario</span></span>

<span data-ttu-id="e89e0-123">Dans ce scénario, une entreprise utilise une stratégie de stock où les produits finis sont suivis par numéros de lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="e89e0-124">Cette entreprise utilise également la charge de travail WMS.</span><span class="sxs-lookup"><span data-stu-id="e89e0-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="e89e0-125">Étant donné que cette charge de travail possède une logique bien établie pour la planification et l'exécution des opérations de prélèvement et d'expédition en entrepôt des articles activés par lots, la plupart des articles finis sont associés à une hiérarchie de réservation de stock « Batch-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="e89e0-126">L'avantage de ce type de configuration opérationnelle est que les décisions (qui sont en fait des décisions de réservation) concernant les lots à prélever et où les placer dans l'entrepôt sont reportées jusqu'au début des opérations de prélèvement de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="e89e0-127">Elles ne sont pas prises lors de la commande du client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="e89e0-128">Si la hiérarchie de réservation « Batch-below\[location\] » sert bien les objectifs commerciaux de la société, de nombreux clients établis ont souvent besoin du même lot qu'ils ont précédemment acheté lorsqu'ils commandent des produits.</span><span class="sxs-lookup"><span data-stu-id="e89e0-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="e89e0-129">Par conséquent, l'entreprise doit viser la flexibilité dans la façon dont les règles de réservation par lots sont traitées, de sorte que, selon la demande des clients pour le même article, les comportements suivants puissent se produire :</span><span class="sxs-lookup"><span data-stu-id="e89e0-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="e89e0-130">Un numéro de lot peut être enregistré et réservé lorsque la commande est prise par le processeur de vente, et ne peut pas être modifié pendant les opérations de l'entrepôt et / ou pris par d'autres demandes.</span><span class="sxs-lookup"><span data-stu-id="e89e0-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="e89e0-131">Ce comportement garantit que le numéro de lot qui a été commandé est expédié au client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="e89e0-132">Si le numéro de lot n'est pas important pour le client, les opérations de l'entrepôt peuvent déterminer un numéro de lot pendant le travail de prélèvement, après l'enregistrement et la réservation de la commande client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="e89e0-133">Permettre la réservation d'un lot spécifique à la commande client</span><span class="sxs-lookup"><span data-stu-id="e89e0-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="e89e0-134">Pour permettre la flexibilité souhaitée dans le comportement de réservation de lots pour les articles associés à une hiérarchie de réservation de stock « Batch-below\[location\] », les gestionnaires de stock doivent sélectionner la case à cocher **Autoriser la réservation à la commande** pour le niveau **Numéro du lot** sur la page **Hiérarchies de réservation du stock**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Rendre flexible la hiérarchie de réservation du stock](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="e89e0-136">Quand le niveau **Numéro du lot** dans la hiérarchie est sélectionné, toutes les dimensions au-dessus de ce niveau et jusqu'à l'**Emplacement** seront automatiquement sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="e89e0-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="e89e0-137">(Par défaut, toutes les dimensions au-dessus de l'**Emplacement** sont présélectionnés.) Ce comportement reflète la logique selon laquelle toutes les dimensions dans la plage entre le numéro de lot et l'emplacement sont également automatiquement réservées après avoir réservé un numéro de lot spécifique sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e89e0-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="e89e0-138">La case à cocher **Autoriser la réservation à la commande** s'applique uniquement aux niveaux de hiérarchie de réservation inférieurs à la dimension d'emplacement de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="e89e0-139">**Numéro du lot** est le seul niveau de la hiérarchie ouvert à la politique de réservation flexible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="e89e0-140">En d'autres termes, vous ne pouvez pas sélectionner la case à cocher **Autoriser la réservation à la commande** pour le niveau **Emplacement**, **Contenant**, ou **Numéro de série**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="e89e0-141">Si votre hiérarchie de réservation comprend la dimension du numéro de série (qui doit toujours être inférieure au niveau **Numéro du lot** et si vous avez activé la réservation spécifique au lot pour le numéro de lot, le système continuera à gérer les opérations de réservation et de prélèvement de numéro de série, en fonction des règles qui s'appliquent à la politique de réservation « Serial-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="e89e0-142">À tout moment, vous pouvez autoriser une réservation spécifique au lot pour une hiérarchie de réservation « Batch-below\[location\] » existante dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="e89e0-143">Cette modification n'affectera pas les réservations et les travaux d'entrepôt ouverts créés avant la modification.</span><span class="sxs-lookup"><span data-stu-id="e89e0-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="e89e0-144">Cependant, la case à cocher **Autoriser la réservation à la commande** ne peut pas être désactivée si des transactions de stock problématiques de type **Commandé réservé**, **Physique réservé**, ou **Commandé** existent pour un ou plusieurs éléments associés à cette hiérarchie de réservation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="e89e0-145">Si la hiérarchie de réservation existante d'un article n'autorise pas la spécification du lot sur la commande, vous pouvez le réaffecter à une hiérarchie de réservation qui autorise la spécification du lot, à condition que la structure de niveau de hiérarchie soit la même dans les deux hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="e89e0-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="e89e0-146">Utilisez la foction **Modifier la hiérarchie de réservation pour les articles** pour effectuer la réaffectation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="e89e0-147">Cette modification peut être pertinente lorsque vous souhaitez empêcher la réservation de lots flexible pour un sous-ensemble d'articles suivis par lots, mais l'autorisez pour le reste du portefeuille de produits.</span><span class="sxs-lookup"><span data-stu-id="e89e0-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="e89e0-148">Que vous ayez sélectionné ou non la case à cocher **Autoriser la réservation à la commande**, si vous ne souhaitez pas réserver un numéro de lot spécifique pour l'article sur une ligne de commande, la logique des opérations d'entrepôt par défaut qui est valide pour une hiérarchie de réservation « Batch-below\[location\] » s'applique toujours.</span><span class="sxs-lookup"><span data-stu-id="e89e0-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="e89e0-149">Réserver un numéro de lot spécifique pour une commande client</span><span class="sxs-lookup"><span data-stu-id="e89e0-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="e89e0-150">Après qu'une hiérarchie de réservation du stock « Batch-below\[location\] » pour un article suivi par lot est configurée pour permettre la réservation de numéros de lot spécifiques sur les commandes client, les processeurs de commande client peuvent prendre des commandes client pour le même article de l'une des manières suivantes, selon la demande du client :</span><span class="sxs-lookup"><span data-stu-id="e89e0-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="e89e0-151">**Entrez les détails de la commande sans spécifier de numéro de lot** - Cette approche doit être utilisée lorsque la spécification du lot du produit n'est pas importante pour le client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="e89e0-152">Tous les processus existants associés à la gestion d'une commande de ce type dans le système restent inchangés.</span><span class="sxs-lookup"><span data-stu-id="e89e0-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="e89e0-153">Aucune mesure supplémentaire n'est requise de la part des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e89e0-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="e89e0-154">**Entrer les détails de la commande et réserver un numéro de lot spécifique** - Cette approche doit être utilisée lorsque le client demande un lot spécifique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="e89e0-155">En règle générale, les clients demandent un lot spécifique lorsqu'ils réorganisent un produit qu'ils ont précédemment acheté.</span><span class="sxs-lookup"><span data-stu-id="e89e0-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="e89e0-156">Ce type de réservation spécifique au lot est appelé *réservation confirmée par la commande*.</span><span class="sxs-lookup"><span data-stu-id="e89e0-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="e89e0-157">L'ensemble de règles suivant est valide lorsque des quantités sont traitées et qu'un numéro de lot est validé pour une commande spécifique :</span><span class="sxs-lookup"><span data-stu-id="e89e0-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="e89e0-158">Pour autoriser la réservation d'un numéro de lot spécifique pour un article selon la politique de réservation « Batch-below\[location\] », le système doit réserver toutes les dimensions jusqu'à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="e89e0-159">Cette plage inclut généralement la dimension du contenant.</span><span class="sxs-lookup"><span data-stu-id="e89e0-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="e89e0-160">Les directives d'emplacement ne sont pas utilisées lorsque le travail de prélèvement est créé pour une ligne de vente qui utilise la réservation par lots validée par la commande.</span><span class="sxs-lookup"><span data-stu-id="e89e0-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="e89e0-161">Pendant le traitement en magasin des travaux pour les lots validés par la commande, ni l'utilisateur ni le système ne sont autorisés à modifier le numéro de lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="e89e0-162">(Ce traitement inclut la gestion des exceptions.)</span><span class="sxs-lookup"><span data-stu-id="e89e0-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="e89e0-163">L'exemple suivant montre le flux de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="e89e0-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e89e0-164">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="e89e0-164">Example scenario</span></span>

<span data-ttu-id="e89e0-165">Pour cet exemple, il convient d'avoir des données de démonstration installées, et vous utiliserez l'exemple d'entreprise **USMF**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="e89e0-166">Configurer une hiérarchie de réservation de stock pour autoriser la réservation spécifique au lot</span><span class="sxs-lookup"><span data-stu-id="e89e0-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="e89e0-167">Allez à **Gestion des entrepôts** \> **Configuration** \> **Stock \> Hiérarchie de réservation**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="e89e0-168">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-168">Select **New**.</span></span>
3. <span data-ttu-id="e89e0-169">Entrez un nom unique dans le champ **Nom** (par exemple **Lot-Flex**).</span><span class="sxs-lookup"><span data-stu-id="e89e0-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="e89e0-170">Dans le champ **Description**, entrez une description (par exemple **Lot, moins prioritaire, flexible**).</span><span class="sxs-lookup"><span data-stu-id="e89e0-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="e89e0-171">Dans le chanp **Sélectionné(s)**, sélectionnez **Numéro de série** et **Propriétaire**, puis sélectionnez le bouton fléché gauche pour les déplacer vers le champ **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="e89e0-172">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-172">Select **OK**.</span></span>
7. <span data-ttu-id="e89e0-173">Dans la rangée pour le niveau de dimension **Numéro du lot**, sélectionnez la case à cocher **Autoriser la réservation à la commande**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="e89e0-174">Les niveaux **Contenant** et **Emplacement** sont automatiquement sélectionnés et vous ne pouvez pas les désactiver.</span><span class="sxs-lookup"><span data-stu-id="e89e0-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="e89e0-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="e89e0-176">Créer un produit lancé</span><span class="sxs-lookup"><span data-stu-id="e89e0-176">Create a new released product</span></span>

1. <span data-ttu-id="e89e0-177">Définissez les trois paramètres de données de base du produit en utilisant ces valeurs :</span><span class="sxs-lookup"><span data-stu-id="e89e0-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="e89e0-178">Dans le champ **Groupe de dimension de stockage**, sélectionnez **Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="e89e0-179">Dans le champ **Groupe de dimension de suivi**, sélectionnez **Lot-Phy**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="e89e0-180">Sélectionnez **Lot-Flex** dans le champ **Hiérarchie de réservation**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="e89e0-181">Créez deux numéros de lot, tels que **B11** et **B22**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="e89e0-182">Ajoutez les quantités d'articles au stock disponible en utilisant les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="e89e0-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="e89e0-183">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-183">Warehouse</span></span> | <span data-ttu-id="e89e0-184">Numéro du lot</span><span class="sxs-lookup"><span data-stu-id="e89e0-184">Batch number</span></span> | <span data-ttu-id="e89e0-185">Emplacement</span><span class="sxs-lookup"><span data-stu-id="e89e0-185">Location</span></span> | <span data-ttu-id="e89e0-186">Contenant</span><span class="sxs-lookup"><span data-stu-id="e89e0-186">License plate</span></span> | <span data-ttu-id="e89e0-187">Quantité</span><span class="sxs-lookup"><span data-stu-id="e89e0-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="e89e0-188">24</span><span class="sxs-lookup"><span data-stu-id="e89e0-188">24</span></span>        | <span data-ttu-id="e89e0-189">B11</span><span class="sxs-lookup"><span data-stu-id="e89e0-189">B11</span></span>          | <span data-ttu-id="e89e0-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="e89e0-190">BULK-001</span></span> | <span data-ttu-id="e89e0-191">Aucune</span><span class="sxs-lookup"><span data-stu-id="e89e0-191">None</span></span>          | <span data-ttu-id="e89e0-192">10</span><span class="sxs-lookup"><span data-stu-id="e89e0-192">10</span></span>       |
    | <span data-ttu-id="e89e0-193">24</span><span class="sxs-lookup"><span data-stu-id="e89e0-193">24</span></span>        | <span data-ttu-id="e89e0-194">B11</span><span class="sxs-lookup"><span data-stu-id="e89e0-194">B11</span></span>          | <span data-ttu-id="e89e0-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="e89e0-195">FL-001</span></span>   | <span data-ttu-id="e89e0-196">LP11</span><span class="sxs-lookup"><span data-stu-id="e89e0-196">LP11</span></span>          | <span data-ttu-id="e89e0-197">10</span><span class="sxs-lookup"><span data-stu-id="e89e0-197">10</span></span>       |
    | <span data-ttu-id="e89e0-198">24</span><span class="sxs-lookup"><span data-stu-id="e89e0-198">24</span></span>        | <span data-ttu-id="e89e0-199">B22</span><span class="sxs-lookup"><span data-stu-id="e89e0-199">B22</span></span>          | <span data-ttu-id="e89e0-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="e89e0-200">FL-002</span></span>   | <span data-ttu-id="e89e0-201">LP22</span><span class="sxs-lookup"><span data-stu-id="e89e0-201">LP22</span></span>          | <span data-ttu-id="e89e0-202">10</span><span class="sxs-lookup"><span data-stu-id="e89e0-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="e89e0-203">Entrer les détails des commandes client</span><span class="sxs-lookup"><span data-stu-id="e89e0-203">Enter sales order details</span></span>

1. <span data-ttu-id="e89e0-204">Accédez à **Ventes et marketing** \> **Commandes client** \> **Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="e89e0-205">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-205">Select **New**.</span></span>
3. <span data-ttu-id="e89e0-206">Dans l'en-tête de la commande client, dans le champ **Compte client**, entrez **US-003**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="e89e0-207">Ajoutez une ligne pour le nouvel article, puis entrez **10** comme quantité.</span><span class="sxs-lookup"><span data-stu-id="e89e0-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="e89e0-208">Veillez à ce que le champ **Entrepôt** soit défini sur **24**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="e89e0-209">Dans l'organisateur **Lignes de commande client**, sélectionnez **Stock**, puis, dans le groupe **Mettre à jour**, sélectionnez **Réservation de lot**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="e89e0-210">La page **Réservation de lot** affiche la liste des lots disponibles à la réservation pour la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e89e0-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="e89e0-211">Pour cet exemple, elle montre une quantité de **20** pour le numéro de lot **B11** et une quantité de **10** pour le numéro de lot **B22**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="e89e0-212">Notez que la page **Réservation de lot** n'est pas accessible à partir d'une ligne si l'élément de cette ligne est associé à la hiérarchie de réservation « Batch-below\[location\] », sauf s'il est configuré pour autoriser une réservation spécifique au lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e89e0-213">Pour réserver un lot spécifique pour une commande client, vous devez utiliser la page **Réservation de lot**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="e89e0-214">Si vous saisissez le numéro de lot directement sur la ligne de commande client, le système se comportera comme si vous aviez entré une valeur de lot spécifique pour un article soumis à la politique de réservation « Batch-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="e89e0-215">Lorsque vous enregistrez la ligne, vous recevrez un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="e89e0-216">Si vous confirmez que le numéro de lot doit être spécifié directement sur la ligne de commande, la ligne ne sera pas gérée par la logique de gestion d'entrepôt standard.</span><span class="sxs-lookup"><span data-stu-id="e89e0-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="e89e0-217">Si vous réservez la quantité à partir de la page **Réservation**, aucun lot spécifique ne sera réservé et l'exécution des opérations d'entrepôt pour la ligne suivra les règles applicables dans le cadre de la politique de réservation « Batch-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="e89e0-218">En général, cette page fonctionne et interagit de la même manière qu'elle fonctionne et interagit pour les articles qui ont une hiérarchie de réservation associée de type « Batch-below\[location\] ».</span><span class="sxs-lookup"><span data-stu-id="e89e0-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="e89e0-219">Cependant, les exceptions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="e89e0-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="e89e0-220">L'organisateur **Numéros de lot validés sur la ligne source** affiche les numéros de lot réservés pour la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e89e0-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="e89e0-221">Les valeurs des lots dans la grille seront affichées tout au long du cycle d'exécution de la ligne de commande, y compris les étapes de traitement de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-221">The batch values in the grid will be shown throughout the fulfillment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="e89e0-222">En revanche, sur l'organisateur **Vue d'ensemble**, la réservation de ligne de commande normale (c'est-à-dire la réservation effectuée pour les dimensions au-dessus du niveau **Emplacement**) est affichée dans la grille jusqu'au moment où le travail d'entrepôt est créé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="e89e0-223">L'entité de travail prend alors en charge la réservation de ligne, et la réservation de ligne n'apparaît plus sur la page.</span><span class="sxs-lookup"><span data-stu-id="e89e0-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="e89e0-224">L'organisateur **Numéros de lot validés sur la ligne source** permet de garantir que le processeur de commande client peut afficher les numéros de lot qui ont été validés pour la commande du client à tout moment au cours de son cycle de vie, jusqu'à la facturation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="e89e0-225">En plus de réserver un lot spécifique, un utilisateur peut sélectionner manuellement l'emplacement spécifique et le contenant du lot au lieu de laisser le système les sélectionner automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="e89e0-226">Cette capacité est liée à la conception du mécanisme de réservation de lots validé par la commande.</span><span class="sxs-lookup"><span data-stu-id="e89e0-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="e89e0-227">Comme mentionné plus haut, lorsqu'un numéro de lot est réservé pour un article selon la politique de réservation « Batch-below\[location\] », le système doit réserver toutes les dimensions jusqu'à l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="e89e0-228">Par conséquent, le travail d'entrepôt comportera les mêmes dimensions de stockage qui ont été réservées par les utilisateurs qui ont travaillé sur les commandes, et parfois cela ne correspond pas à l'emplacement de stockage de l'article le plus pratique, voire ce choix est impossible pour les opérations de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="e89e0-229">Si les processeurs de la commande sont conscients des contraintes de l'entrepôt, ils peuvent sélectionner manuellement les emplacements spécifiques et les contenants lorsqu'ils réservent un lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="e89e0-230">Dans ce cas, l'utilisateur doit utiliser la fonction **Afficher les dimensions** sur l'en-tête de la page et doit ajouter l'emplacement et le contenant dans la grille de l'organisateur **Vue d'ensemble**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="e89e0-231">Sur la page **Réservation de lot**, sélectionnez la ligne pour le lot **B11**, puis sélectionnez **Réserver une ligne**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="e89e0-232">Il n'y a pas de logique désignée pour attribuer des emplacements et des contenants lors de la réservation automatique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="e89e0-233">Vous pouvez saisir manuellement la quantité dans le champ **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="e89e0-234">Notez que, sur l'organisateur **Numéros de lot validés sur la ligne source**, le lot **B11** est affiché comme **Validé**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Validation d'un numéro de lot spécifique sur une ligne de commande client sur la page de réservation de lot](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="e89e0-236">La réservation de la quantité sur une ligne de commande client peut être effectuée sur plusieurs lots.</span><span class="sxs-lookup"><span data-stu-id="e89e0-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="e89e0-237">De même, la réservation du même lot peut être effectuée sur plusieurs emplacements et contenants (si les contenants sont activés pour les emplacements).</span><span class="sxs-lookup"><span data-stu-id="e89e0-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="e89e0-238">La réservation d'un lot spécifique pour la quantité sur une ligne de commande client peut également être partielle.</span><span class="sxs-lookup"><span data-stu-id="e89e0-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="e89e0-239">Par exemple, la quantité totale de 100 unités peut être réservée pour qu'un lot spécifique soit validé à 20 unités, tandis que 80 unités sont réservées au niveau du site et de l'entrepôt pour tout lot disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="e89e0-240">Dans ce cas, le WMS gérera les opérations de prélèvement en utilisant deux lignes de travail distinctes.</span><span class="sxs-lookup"><span data-stu-id="e89e0-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="e89e0-241">Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="e89e0-242">Sélectionnez votre article, puis sélectionnez **Gérer le stock**\>**Vue** \>**Transactions**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Réservation validée en tant que type de transaction de stock](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="e89e0-244">Vérifiez les transactions de stock de l'article qui sont liées à la réservation de la ligne de commande client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="e89e0-245">Une transaction où la **Référence** est définie sur **Commande client** et le **Problème** est défini sur **Physique réservé** représente la réservation de la ligne de commande pour les dimensions de stock au-dessus du niveau **Emplacement**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="e89e0-246">Selon la hiérarchie de réservation de stock de l'article, ces dimensions sont le site, l'entrepôt et l'état du stock.</span><span class="sxs-lookup"><span data-stu-id="e89e0-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="e89e0-247">Une transaction où le champ **Référence** est défini sur **Réservation confirmée par la commande** et le champ **Problème** est défini sur **Physique réservé** représente la réservation de la ligne de commande pour le lot spécifique et toutes les dimensions de stock au-dessus.</span><span class="sxs-lookup"><span data-stu-id="e89e0-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="e89e0-248">Selon la hiérarchie de réservation de stock de l'article, ces dimensions sont le numéro du lot et l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="e89e0-249">Dans cet exemple, l'emplacement est **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="e89e0-250">Dans l'en-tête de la commande client, sélectionnez **Entrepôt** \>**Actions** \>**Libérer dans l'entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="e89e0-251">La ligne de commande est maintenant traité par vagues et une charge et un travail sont créés.</span><span class="sxs-lookup"><span data-stu-id="e89e0-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="e89e0-252">Examiner et traiter le travail en entrepôt dont les numéros de lot sont validés par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="e89e0-253">Sur l'organisateur **Lignes de commande client**, sélectionnez **Entrepôt** \>**Détails du travail**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="e89e0-254">Le travail qui gère l'opération de prélèvement pour les quantités de lots validées sur la ligne de commande client présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e89e0-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="e89e0-255">Pour créer un travail, le système utilise des modèles de travail mais pas des directives d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="e89e0-256">Tous les paramètres standard définis pour les modèles de travail, tels que le nombre maximal de lignes de sélection ou une unité de mesure spécifique, seront appliqués pour déterminer le moment où un nouveau travail doit être créé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="e89e0-257">Cependant, les règles associées aux directives d'emplacement pour identifier les emplacements de prélèvement ne sont pas prises en compte, car la réservation validée par la commande spécifie déjà toutes les dimensions du stock.</span><span class="sxs-lookup"><span data-stu-id="e89e0-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="e89e0-258">Ces dimensions de stock incluent les dimensions au niveau du stockage en entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="e89e0-259">Par conséquent, le travail hérite de ces dimensions sans avoir à consulter les directives d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="e89e0-260">Le numéro de lot n'apparaît pas sur la ligne de prélèvement (comme c'est le cas pour la ligne de travail créée pour un article auquel est associé une hiérarchie de réservation « Batch-above\[location\] ».) Au lieu de cela, le numéro de lot « origine » et toutes les autres dimensions de stockage sont affichés sur la transaction de stock de la ligne de travail qui est référencée à partir des transactions de stock associées.</span><span class="sxs-lookup"><span data-stu-id="e89e0-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Transaction de stock d'entrepôt pour les travaux provenant de la réservation validée par la commande](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="e89e0-262">Une fois le travail créé, la transaction de stock de l'article où le champ **Référence** est défini sur **Réservation confirmée par la commande** est retirée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="e89e0-263">La transaction de stock où le champ **Référence** est défini sur **Travail** détient désormais la réservation physique sur toutes les dimensions de stock de la quantité.</span><span class="sxs-lookup"><span data-stu-id="e89e0-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="e89e0-264">Les opérations d'entrepôt peuvent procéder à l'exécution des travaux de la manière habituelle.</span><span class="sxs-lookup"><span data-stu-id="e89e0-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="e89e0-265">Cependant, les instructions sur l'appareil mobile demanderont au collaborateur de choisir un numéro de lot spécifique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="e89e0-266">Dans les environnements d'entrepôt où les emplacements sont contrôlés par contenant, lorsqu'un collaborateur atteint un emplacement qui stocke le même lot sur plusieurs contenants, il peut choisir n'importe quel contenant qui n'est pas déjà réservé (par exemple, par une autre réservation confirmée par la commande ou un travail provenant d'une réservation de ce type.)</span><span class="sxs-lookup"><span data-stu-id="e89e0-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="e89e0-267">S'il s'avère impossible de prélever à partir de l'emplacement spécifié sur la ligne de travail, les opérateurs de l'entrepôt peuvent utiliser l'une des actions suivantes pour rediriger le prélèvement du lot spécifique à partir d'un emplacement plus pratique :</span><span class="sxs-lookup"><span data-stu-id="e89e0-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="e89e0-268">L'action **Emplacement de remplacement** standard sur un appareil mobile (à condition que le paramètre **Autoriser le remplacement de l'emplacement de prélèvement** soit activé pour le collaborateur de l'entrepôt)</span><span class="sxs-lookup"><span data-stu-id="e89e0-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="e89e0-269">L'action **Changer d'emplacement** sur la page **Détails de la liste de travail**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="e89e0-270">Sur l'appareil mobile, terminez le prélèvement et le rangement du travail.</span><span class="sxs-lookup"><span data-stu-id="e89e0-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="e89e0-271">La quantité de **10** pour le numéro de lot **B11** est maintenant sélectionnée pour la ligne de commande client et placée dans l'empalcement **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="e89e0-272">À ce stade, le lot est prêt à être chargé dans le camion et expédié à l'adresse du client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="e89e0-273">Gestion des exceptions pour un travail d'entrepôt dont les numéros de lot sont validés par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-273">Exception handling of warehouse work that has order-committed batch numbers</span></span>

<span data-ttu-id="e89e0-274">Le travail d'entrepôt pour le prélèvement de numéros de lot validés par la commande est soumis à la même gestion et aux mêmes exceptions qu'un travail normal.</span><span class="sxs-lookup"><span data-stu-id="e89e0-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="e89e0-275">En général, la ligne ou le travail ouvert peut être annulé, il peut être interrompu car un emplacement utilisateur est plein, il peut être sélectionné et il peut être mis à jour en raison d'un mouvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="e89e0-276">De même, la quantité de travail sélectionnée déjà terminée peut être réduite ou le travail peut être inversé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="e89e0-277">La règle clé suivante est appliquée à toutes ces actions de gestion des exceptions : le numéro de lot réservé pour le client ne peut jamais être remplacé par un numéro de lot différent, mais ses dimensions de stockage (emplacement et contenant) peuvent être modifiées via une mise à jour manuelle par l'utilisateur ou une mise à jour automatique par le système.</span><span class="sxs-lookup"><span data-stu-id="e89e0-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="e89e0-278">La mise à jour automatique est basée sur la même affectation aléatoire des dimensions de stockage qui s'appliquait lorsqu'un lot spécifique était automatiquement réservé mais qu'aucune dimension de stockage n'était spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="e89e0-279">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="e89e0-279">Example scenario</span></span>

<span data-ttu-id="e89e0-280">Un exemple de ce scénario est une situation où un travail précédemment terminé est modifié à l'aide de la fonction **Réduire la quantité prélevée**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="e89e0-281">Cet exemple est la suite de l'exemple précédent dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="e89e0-282">Allez à **Gestion des entrepôts** \> **Charges** \> **Chargements actifs**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="e89e0-283">Sélectionnez le chargement créé lors de l'expédition de votre commande client.</span><span class="sxs-lookup"><span data-stu-id="e89e0-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="e89e0-284">Dans l'organisateur **Charger des lignes de commande**, sélectionnez **Réduire la quantité prélevée**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="e89e0-285">Sur la page **RRéduire la quantité prélevée**, dans le champ **Déplacer vers l'emplacement**, sélectionnez **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="e89e0-286">Dans le champ **Déplacer vers le contenant**, sélectionnez **LP33**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="e89e0-287">Dans la grille, dans le champ **Quantité en stock à ne pas prélever**, entrez **10**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="e89e0-288">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-288">Select **OK**.</span></span>

<span data-ttu-id="e89e0-289">Voici les résultats de l'action de non prélèvement :</span><span class="sxs-lookup"><span data-stu-id="e89e0-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="e89e0-290">Le statut du travail précédemment clôturé est défini sur **Annulé**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="e89e0-291">Un nouveau travail de type **Mouvement de stock** est créé pour la quantité non prélevée de **10** pour le numéro de lot **B11**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="e89e0-292">Ce travail représente le mouvement de l'emplacement **Baydoor** vers le contenant **LP33** à l'emplacement **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="e89e0-293">Le statut est défini sur **Clôturé**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="e89e0-294">Le système réserve à nouveau le numéro de lot qui avait été initialement commandé et attribue l'emplacement et les ID de contenant.</span><span class="sxs-lookup"><span data-stu-id="e89e0-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="e89e0-295">(Ce processus équivaut à exécuter la fonction **Réserver une ligne** pour la ligne de commande pour un numéro de lot donné).</span><span class="sxs-lookup"><span data-stu-id="e89e0-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="e89e0-296">En conséquence, le lot **B11** apparaît comme validé sur l'organisateur **Numéros de lot validés sur la ligne source** de la page **Réservation de lot** et le champ **Réservation** contient une quantité de **10** pour le numéro de lot **B11**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="e89e0-297">De plus, l'**Emplacement** est défini sur **FL-001**, et le champ **Contenant** est défini sur **LP11**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="e89e0-298">(Vous pouvez ajouter ces champs à la grille s'ils ne sont pas visibles.)</span><span class="sxs-lookup"><span data-stu-id="e89e0-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="e89e0-299">Les tableaux suivants fournissent une vue d'ensemble qui montre comment le système gère la réservation par lots validée par la commande pour des actions d'entrepôt spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e89e0-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="e89e0-300">Pour interpréter le contenu des tableaux, supposez que chaque action d'entrepôt est exécutée dans le contexte d'un travail d'entrepôt existant provenant d'une réservation par lots validée par une commande, ou que l'exécution de chaque action d'entrepôt affecte un travail de ce type.</span><span class="sxs-lookup"><span data-stu-id="e89e0-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="e89e0-301">Dans ces tableaux, la colonne « La quantité de lot est disponible » indique si une quantité de lot est disponible en plus de la quantité qui est déjà réservée pour les réservations validées par la commande en cours ou déjà réservée par le travail d'entrepôt qui provient de réservations de ce type.</span><span class="sxs-lookup"><span data-stu-id="e89e0-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="e89e0-302">Remplacement de l'emplacement de prélèvement sur le travail ouvert</span><span class="sxs-lookup"><span data-stu-id="e89e0-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-303">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-304">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-305">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-305">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-306">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-306">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-307">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-308">L'option <strong>Autoriser le remplacement de l'emplacement de prélèvement</strong> est activée pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e89e0-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="e89e0-309">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-310">Sélectionnez l'élément de menu <strong>Emplacement de remplacement</strong> sur l'application d'entrepôt lorsque vous commencez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-310">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="e89e0-311">Sélectionnez <strong>Suggérer</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="e89e0-312">Confirmez le nouvel emplacement suggéré en fonction de la disponibilité de la quantité de lots.</span><span class="sxs-lookup"><span data-stu-id="e89e0-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-313">Sur le travail en cours, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="e89e0-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="e89e0-314">L'emplacement sur la ligne de sélection est mis à jour vers le nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="e89e0-315">(Si l'emplacement est contrôlé par le contenant, un contenant aléatoire est affecté à la transaction de stock, et le collaborateur peut choisir parmi n'importe quel contenant qui a une quantité disponible.)</span><span class="sxs-lookup"><span data-stu-id="e89e0-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="e89e0-316">Si la quantité se trouve sur plusieurs contenants dans le nouvel emplacement, la ligne de prélèvement d'origine est divisée en plusieurs lignes pour correspondre à chaque contenant.</span><span class="sxs-lookup"><span data-stu-id="e89e0-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-317">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-318">N°</span><span class="sxs-lookup"><span data-stu-id="e89e0-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-319">Sélectionnez l'élément de menu <strong>Emplacement de remplacement</strong> sur l'application d'entrepôt lorsque vous commencez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-319">Select the <strong>Override location</strong> menu item on the warehouse app when you start picking work.</span></span></li>
<li><span data-ttu-id="e89e0-320">Entrez manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-321">L'action <strong>Emplacement de remplacement</strong> n'est pas possible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="e89e0-322">Elle échoue et une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="e89e0-323">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="e89e0-324">Bouton Complet - Fractionner une ligne de travail en raison d'un dépassement sur l'emplacement de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-325">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-326">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-327">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-327">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-328">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-328">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-329">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e89e0-330">L'option <strong>Autoriser le fractionnement du travail </strong> est activée sur l'élément de menu de l'appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e89e0-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="e89e0-331">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-332">Sélectionnez l'élément de menu <strong>Complet</strong> sur l'application d'entrepôt lorsque vous traitez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-332">Select the <strong>Full</strong> menu item on the warehouse app when you process picking work.</span></span></li>
<li><span data-ttu-id="e89e0-333">Dans le champ <strong>Qté prélevée</strong>, entrez la quantité partielle de prélèvement requise pour indiquer la pleine capacité.</span><span class="sxs-lookup"><span data-stu-id="e89e0-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-334">Sur le travail en cours, la quantité est mise à jour avec la quantité restante qui doit être prélevée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="e89e0-335">Un nouveau travail pour la quantité prélevée est créé et fermé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="e89e0-336">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="e89e0-337">Réduisez la quantité prélevée du travail terminé (à partir d'un chargement)</span><span class="sxs-lookup"><span data-stu-id="e89e0-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-338">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-339">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-340">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-340">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-341">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-341">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-342">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-343">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-343">Not applicable</span></span></td>
<td><span data-ttu-id="e89e0-344">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-345">Ouvrez la page <strong>Réduire la quantité prélevée</strong> à partir de la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="e89e0-346">Entrer la quantité complète à ne pas prélever.</span><span class="sxs-lookup"><span data-stu-id="e89e0-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="e89e0-347">Sélectionnez un emplacement « déplacer vers » / contenant.</span><span class="sxs-lookup"><span data-stu-id="e89e0-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="e89e0-348">Le travail associé à la ligne de chargement est annulé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="e89e0-349">Un nouveau travail pour le mouvement de stock est créé et fermé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-350">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-351">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-352">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-352">No</span></span></td>
<td><span data-ttu-id="e89e0-353">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-353">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-354">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-354">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-355">La quantité est réservée pour le même lot et pour le même emplacement et le même contenant (si l'emplacement est contrôlé par le contenant) qui ont été saisis lors du prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="e89e0-356">Déplacer un article dans un entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="e89e0-357">Cette action d'entrepôt ne s'applique qu'au mouvement de type **Processus de création du travail**, pas au mouvement par modèle.</span><span class="sxs-lookup"><span data-stu-id="e89e0-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-358">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-359">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-360">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-360">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-361">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-361">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-362">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-363">L'option <strong>Autoriser les mouvements de stock avec le travail associé</strong> est activée sur le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e89e0-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="e89e0-364">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-365">Démarrez un mouvement sur l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-365">Start a movement on the warehouse app.</span></span></li>
<li><span data-ttu-id="e89e0-366">Entrez les emplacements d'origine et de destination.</span><span class="sxs-lookup"><span data-stu-id="e89e0-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="e89e0-367">Sur tous les travaux existants affectés par le déplacement, l'emplacement de prélèvement est mis à jour vers le nouvel emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="e89e0-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="e89e0-368">Un nouveau travail pour le mouvement de stock est créé et fermé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-369">Toutes les réservations existantes qui sont affectées par le mouvement de quantité à partir de l'emplacement donné sont re-réservées pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-370">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-371">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-371">No</span></span></td>
<td><span data-ttu-id="e89e0-372">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-372">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-373">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-373">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-374">Toutes les réservations existantes qui sont affectées par le mouvement de quantité à partir de l'emplacement donné sont réservées de nouveau pour le même lot, ainsi que pour le nouvel emplacement de destination et le nouveau contenant (si l'emplacement est contrôlé par le contenant).</span><span class="sxs-lookup"><span data-stu-id="e89e0-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="e89e0-375">Contrepasser la quantité prélevée du travail terminé (à partir d'un chargement ou de la vague)</span><span class="sxs-lookup"><span data-stu-id="e89e0-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-376">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-377">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-378">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-378">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-379">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-379">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-380">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="e89e0-381">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-381">Not applicable</span></span></td>
<td><span data-ttu-id="e89e0-382">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-383">Ouvrez la page <strong>Contrepasser le travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="e89e0-384">Sur la page de demande, sélectionnez l'option <strong>Laisser les articles à l'emplacement actuel</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-385">Les travaux associés à la ligne de chargement sont annulés.</span><span class="sxs-lookup"><span data-stu-id="e89e0-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="e89e0-386">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-387">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-388">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-388">No</span></span></td>
<td><span data-ttu-id="e89e0-389">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-389">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-390">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-390">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-391">La quantité est réservée de nouveau pour le même lot, ainsi que pour l'emplacement et le contenant où la quantité a été laissée lors de la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-392">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-393">Ouvrez la page <strong>Contrepasser le travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="e89e0-394">Sur la page de demande, sélectionnez l'option <strong>Affecter des articles à cet emplacement</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-395">Le travail actuel est annulé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="e89e0-396">Un nouveau travail pour le mouvement de stock est créé et fermé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-397">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-398">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-399">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-399">No</span></span></td>
<td><span data-ttu-id="e89e0-400">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-400">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-401">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-401">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-402">La quantité est réservée de nouveau pour le même lot, ainsi que pour l'emplacement et le contenant auquel la quantité a été affectée lors de la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-403">Oui/Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-404">Ouvrez la page <strong>Contrepasser le travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="e89e0-405">Sur la page de demande, sélectionnez l'option <strong>Déplacer des articles vers cet emplacement</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-406">La contrepassation n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e89e0-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="e89e0-407">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-408">Oui/Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-409">Ouvrez la page <strong>Contrepasser le travail</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="e89e0-410">Sur la page de demande, sélectionnez l'option <strong>Déplacer des articles selon les instructions d'emplacement</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-411">La contrepassation n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e89e0-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="e89e0-412">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="e89e0-413">Sélection rapide d'une quantité - Enregistrer la quantité comme physiquement introuvable à l'emplacement / dans le contenant pendant que vous effectuez un travail de prélèvement</span><span class="sxs-lookup"><span data-stu-id="e89e0-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-414">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-415">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-416">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-416">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-417">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-417">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-418">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-419">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Aucun</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="e89e0-420">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-421">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-421">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-422">Dans le champ <strong>Prélever une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-423">Dans le champ <strong>Nom</strong>, entrez <strong>Aucune imposition</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-424">Le travail en cours est fermé et la quantité prélevée est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="e89e0-425">Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-426">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-427">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-428">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-428">No</span></span></td>
<td><span data-ttu-id="e89e0-429">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e89e0-430">L'action de sélection rapide échoue et une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="e89e0-431">Le travail en cours reste ouvert.</span><span class="sxs-lookup"><span data-stu-id="e89e0-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-432">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-433">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Aucun</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="e89e0-434">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-435">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-435">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-436">Dans le champ <strong>Prélever une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-437">Dans le champ <strong>Nom</strong>, entrez <strong>Aucune imposition</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-438">Le travail en cours est fermé et la quantité prélevée est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="e89e0-439">Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-440">Toutes les réservations existantes qui sont affectées par l'ajustement de quantité dans l'emplacement faisant l'objet d'un prélèvement partiel sont re-réservées pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-441">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-442">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-442">No</span></span></td>
<td><span data-ttu-id="e89e0-443">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-443">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-444">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-444">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-445">Toutes les réservations existantes qui sont affectées par l'ajustement de quantité dans l'emplacement faisant l'objet d'un prélèvement partiel supprimées.</span><span class="sxs-lookup"><span data-stu-id="e89e0-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-446">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non/Oui</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="e89e0-447">De plus, l'option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e89e0-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="e89e0-448">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-449">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-449">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-450">Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-451">Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="e89e0-452">Sélectionnez l'emplacement / le contenant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e89e0-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-453">Sur le travail en cours, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="e89e0-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="e89e0-454">La ligne de prélèvement est fermée et la quantité prélevée est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="e89e0-455">La ligne de placement est annulée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="e89e0-456">Une nouvelle ligne de prélèvement a été créée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-456">A new pick line is created.</span></span> <span data-ttu-id="e89e0-457">Elle utilise l'emplacement / contenant que l'utilisateur a sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e89e0-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="e89e0-458">Une nouvelle ligne de placement a été créée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e89e0-459">Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-460">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-461">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Non</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="e89e0-462">De plus, l'option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e89e0-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="e89e0-463">N°</span><span class="sxs-lookup"><span data-stu-id="e89e0-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-464">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-464">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-465">Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-466">Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-467">L'action de sélection rapide échoue et une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="e89e0-468">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-469">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Manuel</strong>, <strong>Ajuster le stock </strong> = <strong>Oui</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="e89e0-470">De plus, l'option <strong>Autoriser la réaffectation manuelle des articles </strong>est activée pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e89e0-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="e89e0-471">N°</span><span class="sxs-lookup"><span data-stu-id="e89e0-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-472">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-472">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-473">Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-474">Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation manuelle</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="e89e0-475">Sélectionnez l'emplacement / le contenant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e89e0-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="e89e0-476">Sur le travail en cours, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="e89e0-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="e89e0-477">La ligne de prélèvement est fermée et la quantité prélevée est 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="e89e0-478">La ligne de placement est annulée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e89e0-479">Une transaction de stock de type <strong>Comptage </strong>et le type de problème <strong>Vendu </strong>sont créés pour représenter l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="e89e0-480">Toutes les réservations existantes qui sont affectées par l'ajustement de quantité dans l'emplacement/contenant faisant l'objet d'un prélèvement partiel supprimées.</span><span class="sxs-lookup"><span data-stu-id="e89e0-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-481">Une exception du travail de type <strong>Prélèvement partiel</strong> est configurée, où <strong>Réaffectation des articles </strong> = <strong>Automatique</strong>, <strong>Ajuster le stock </strong> = <strong>Oui/Non</strong>, et <strong>Supprimer des réservations </strong> = <strong>Oui/Non</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="e89e0-482">Non applicable</span><span class="sxs-lookup"><span data-stu-id="e89e0-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-483">Sélectionnez l'élément de menu <strong>Prélèvement partiel</strong> sur l'application d'entrepôt lorsque vous exécutez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="e89e0-483">Select the <strong>Shortpick</strong> menu item on the warehouse app when you run picking work.</span></span></li>
<li><span data-ttu-id="e89e0-484">Dans le champ <strong>Prélever partiellemment une quantité</strong>, entrez <strong>0</strong> (zéro).</span><span class="sxs-lookup"><span data-stu-id="e89e0-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="e89e0-485">Dans le champ <strong>Motif</strong>, sélectionnez <strong>Prélèvement partiel avec réallocation automatique</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-486">Le prélèvement partiel qui implique une réallocation automatique n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e89e0-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="e89e0-487">Le prélèvement partiel qui implique une réallocation automatique n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e89e0-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="e89e0-488">Modifier le statut du stock</span><span class="sxs-lookup"><span data-stu-id="e89e0-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="e89e0-489">Cette action d'entrepôt peut être effectuée à partir de plusieurs points d'entrée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="e89e0-490">L'exemple présenté ici utilise l'action **Modification du statut du stock** sur la page **Disponible par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="e89e0-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e89e0-491">Paramètre de configuration clé</span><span class="sxs-lookup"><span data-stu-id="e89e0-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="e89e0-492">La quantité de lot est disponible</span><span class="sxs-lookup"><span data-stu-id="e89e0-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="e89e0-493">Étapes clés pour l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e89e0-493">Key user steps</span></span></th>
<th><span data-ttu-id="e89e0-494">Travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e89e0-494">Warehouse work</span></span></th>
<th><span data-ttu-id="e89e0-495">Réservation de lots validée par la commande</span><span class="sxs-lookup"><span data-stu-id="e89e0-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-496">Sur l'onglet <strong>Entrepôt</strong>, dans l'enregistrement <strong>Entrepôt</strong>, le champ <strong>Supprimer les réservations et marquages </strong>est défini sur <strong>Réservations </strong>ou <strong>Marquages et réservations</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="e89e0-497">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-498">Sélectionnez un emplacement spécifique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="e89e0-499">Sélectionnez une ligne qui a un élément, un emplacement et un contenant spécifiques (si l'emplacement est contrôlé par le contenant).</span><span class="sxs-lookup"><span data-stu-id="e89e0-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="e89e0-500">Sélectionnez <strong>Modification du statut du stock</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="e89e0-501">Définissez le champ <strong>Statut du stock </strong>sur <strong>Blocage</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-502">Les modifications de l'état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</span><span class="sxs-lookup"><span data-stu-id="e89e0-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e89e0-503">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-504">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="e89e0-505">Deux transactions de stock de type <strong>Modification du statut du stock </strong>sont créés pour représenter la modification de la dimension d'état de stock.</span><span class="sxs-lookup"><span data-stu-id="e89e0-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="e89e0-506">Une transaction de stock de type <strong>Blocage su stock </strong>et le type de problème<strong>Physique réservé </strong>est créé pour représenter la réservation de la quantité bloquée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-507">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-507">No</span></span></td>
<td><span data-ttu-id="e89e0-508">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-508">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-509">Les modifications de l'état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</span><span class="sxs-lookup"><span data-stu-id="e89e0-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="e89e0-510">La réservation est supprimée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="e89e0-511">Deux transactions de stock de type <strong>Modification du statut du stock </strong>sont créés pour représenter la modification de la dimension d'état de stock.</span><span class="sxs-lookup"><span data-stu-id="e89e0-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="e89e0-512">Une transaction de stock de type <strong>Blocage su stock </strong>et le type de problème<strong>Physique réservé </strong>est créé pour représenter la réservation de la quantité bloquée.</span><span class="sxs-lookup"><span data-stu-id="e89e0-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="e89e0-513">Sur l'onglet <strong>Entrepôt</strong>, dans l'enregistrement <strong>Entrepôt</strong>, le champ <strong>Supprimer les réservations et marquages</strong> est défini sur <strong>Aucun</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="e89e0-514">Oui</span><span class="sxs-lookup"><span data-stu-id="e89e0-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="e89e0-515">Sélectionnez un emplacement spécifique.</span><span class="sxs-lookup"><span data-stu-id="e89e0-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="e89e0-516">Sélectionnez une ligne qui a un élément, un emplacement et un contenant spécifiques (si l'emplacement est contrôlé par le contenant).</span><span class="sxs-lookup"><span data-stu-id="e89e0-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="e89e0-517">Sélectionnez <strong>Modification du statut du stock</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="e89e0-518">Définissez le champ <strong>Statut du stock </strong>sur <strong>Blocage</strong>.</span><span class="sxs-lookup"><span data-stu-id="e89e0-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="e89e0-519">Les modifications de l'état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</span><span class="sxs-lookup"><span data-stu-id="e89e0-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="e89e0-520">La quantité est réservée de nouveau pour le même lot.</span><span class="sxs-lookup"><span data-stu-id="e89e0-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="e89e0-521">Le système attribue au hasard un emplacement et un contenant (si l'emplacement est contrôlé par le contenant) où la quantité est disponible.</span><span class="sxs-lookup"><span data-stu-id="e89e0-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e89e0-522">Non</span><span class="sxs-lookup"><span data-stu-id="e89e0-522">No</span></span></td>
<td><span data-ttu-id="e89e0-523">Voir la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="e89e0-523">See the previous row.</span></span></td>
<td><span data-ttu-id="e89e0-524">Les modifications de l'état des stocks ne sont pas autorisées pour les quantités réservées pour le travail.</span><span class="sxs-lookup"><span data-stu-id="e89e0-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="e89e0-525">Les modifications de l'état du stock ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="e89e0-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="e89e0-526">Limites</span><span class="sxs-lookup"><span data-stu-id="e89e0-526">Limitations</span></span>

- <span data-ttu-id="e89e0-527">La fonctionnalité de réservation de dimension flexible au niveau de l'entrepôt ne prend pas en charge les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="e89e0-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="e89e0-528">Gestion du poids variable</span><span class="sxs-lookup"><span data-stu-id="e89e0-528">Catch weight management</span></span>
    - <span data-ttu-id="e89e0-529">Stock physique négatif</span><span class="sxs-lookup"><span data-stu-id="e89e0-529">Physical negative inventory</span></span>
    - <span data-ttu-id="e89e0-530">Réservation contre fourniture commandée</span><span class="sxs-lookup"><span data-stu-id="e89e0-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="e89e0-531">Ordres de transfert et prélèvement des matières premières</span><span class="sxs-lookup"><span data-stu-id="e89e0-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="e89e0-532">La règle de consolidation des conteneurs pour l'emballage par unité de directive présente des limites.</span><span class="sxs-lookup"><span data-stu-id="e89e0-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="e89e0-533">Pour les réservations validées par la commande, nous vous recommandons de ne pas utiliser de modèles de construction de conteneur où le cham **Pack par unité de directive** est activé.</span><span class="sxs-lookup"><span data-stu-id="e89e0-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="e89e0-534">Dans la conception actuelle, les directives d'emplacement ne sont pas utilisées lors de la création d'un travail d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e89e0-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="e89e0-535">Par conséquent, seule l'unité la plus basse du groupe de séquences d'unités (l'unité d'inventaire) est appliquée pendant l'étape de vague de conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="e89e0-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
