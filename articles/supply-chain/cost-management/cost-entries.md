---
title: Écritures de coût
description: Cet article fournit des informations sur les entrées de coût et à quel moment elles sont créées. Une entrée de coût est un enregistrement qui enregistre la quantité et le coût d’un événement donné.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48c37e4355bc3448930a7cfa73ce08ac8e439b97
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839413"
---
# <a name="cost-entries"></a><span data-ttu-id="db01e-104">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="db01e-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db01e-105">Cet article fournit des informations sur les entrées de coût et à quel moment elles sont créées.</span><span class="sxs-lookup"><span data-stu-id="db01e-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="db01e-106">Une entrée de coût est un enregistrement qui enregistre la quantité et le coût d’un événement donné.</span><span class="sxs-lookup"><span data-stu-id="db01e-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="db01e-107">Les entrées de coût sont des agrégations des mouvements de stock qui sont enregistrés sur les dimensions de stock financier actives.</span><span class="sxs-lookup"><span data-stu-id="db01e-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="db01e-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="db01e-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="db01e-109">Exemple 1 : aucune écriture de coût n’est créée</span><span class="sxs-lookup"><span data-stu-id="db01e-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="db01e-110">Un événement de journal de transfert est enregistré.</span><span class="sxs-lookup"><span data-stu-id="db01e-110">A transfer journal event is registered.</span></span> <span data-ttu-id="db01e-111">L’événement transfère une pièce de l’article A de l’emplacement A à l’emplacement B. La dimension de stock d’emplacement n’est pas prise en considération dans l’objet de coût.</span><span class="sxs-lookup"><span data-stu-id="db01e-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="db01e-112">Par conséquent, l’événement crée deux mouvements de stock et aucune écriture de coût.</span><span class="sxs-lookup"><span data-stu-id="db01e-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="db01e-113">Exemple 2 : des écritures de coût sont créées</span><span class="sxs-lookup"><span data-stu-id="db01e-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="db01e-114">Un événement de journal de transfert est enregistré.</span><span class="sxs-lookup"><span data-stu-id="db01e-114">A transfer journal event is registered.</span></span> <span data-ttu-id="db01e-115">L’événement transfère une pièce de l’article A du site 1 au site 2.</span><span class="sxs-lookup"><span data-stu-id="db01e-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="db01e-116">La dimension de stock de site est prise en considération dans l’objet de coût.</span><span class="sxs-lookup"><span data-stu-id="db01e-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="db01e-117">Par conséquent, l’événement crée deux mouvements de stock et deux écritures de coût.</span><span class="sxs-lookup"><span data-stu-id="db01e-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="db01e-118">Exemple 3 : une écriture de coût est créée</span><span class="sxs-lookup"><span data-stu-id="db01e-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="db01e-119">Un événement d’accusé de réception de marchandises est enregistré pour une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="db01e-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="db01e-120">L’événement enregistre 100 pièces de l’article A à un coût unitaire de 10.00 dollars américain (USD).</span><span class="sxs-lookup"><span data-stu-id="db01e-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="db01e-121">Étant donné que l’article A utilise un numéro de série aux fins du suivi de la Gestion des stocks, un numéro de série unique est créé pour chaque article reçu.</span><span class="sxs-lookup"><span data-stu-id="db01e-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="db01e-122">Par conséquent, l’événement crée 100 mouvements de stock et une écriture de coût.</span><span class="sxs-lookup"><span data-stu-id="db01e-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="db01e-123">Page des écritures de coût</span><span class="sxs-lookup"><span data-stu-id="db01e-123">Cost entries page</span></span>
<span data-ttu-id="db01e-124">La nouvelle page **Écritures de coût** permet d’afficher et contrôler les enregistrements des quantités et des coûts.</span><span class="sxs-lookup"><span data-stu-id="db01e-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="db01e-125">Cette page complète les pâges **Mouvement de stock** et **Lettrage de stock**.</span><span class="sxs-lookup"><span data-stu-id="db01e-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="db01e-126">Les enregistrements sont enregistrés dans l’ordre chronologique pour un événement.</span><span class="sxs-lookup"><span data-stu-id="db01e-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="db01e-127">Par conséquent, vous pouvez rapidement trouver et contrôler les coûts cumulés d’un événement spécifique ou de tous les événements liés à un document.</span><span class="sxs-lookup"><span data-stu-id="db01e-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="db01e-128">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="db01e-128">Here is an example:</span></span>

-   <span data-ttu-id="db01e-129">Un événement d’accusé de réception de marchandises est enregistré pour l’article A. Cent pièces sont reçues à un coût unitaire de 10,00 USD chacune.</span><span class="sxs-lookup"><span data-stu-id="db01e-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="db01e-130">Quelques jours après que l’événement de facture a été enregistré, le coût grimpe à 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="db01e-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="db01e-131">Par conséquent, le montant total est de 1 100 €.</span><span class="sxs-lookup"><span data-stu-id="db01e-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="db01e-132">Un deuxième N° document est créé pour expliquer la différence de 100 USD.</span><span class="sxs-lookup"><span data-stu-id="db01e-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="db01e-133">Quelques jours plus tard, les frais divers de 15,00 USD pour couvrir le coût du transport sont enregistrés sur la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="db01e-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="db01e-134">Pièce justificative</span><span class="sxs-lookup"><span data-stu-id="db01e-134">Voucher</span></span> | <span data-ttu-id="db01e-135">date ;</span><span class="sxs-lookup"><span data-stu-id="db01e-135">Date</span></span>       | <span data-ttu-id="db01e-136">Référence</span><span class="sxs-lookup"><span data-stu-id="db01e-136">Reference</span></span>      | <span data-ttu-id="db01e-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="db01e-137">Number</span></span> | <span data-ttu-id="db01e-138">N° de traitement</span><span class="sxs-lookup"><span data-stu-id="db01e-138">Lot ID</span></span>  | <span data-ttu-id="db01e-139">Quantité</span><span class="sxs-lookup"><span data-stu-id="db01e-139">Quantity</span></span> | <span data-ttu-id="db01e-140">Montant</span><span class="sxs-lookup"><span data-stu-id="db01e-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="db01e-141">00001</span><span class="sxs-lookup"><span data-stu-id="db01e-141">00001</span></span>   | <span data-ttu-id="db01e-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="db01e-142">01-01-2015</span></span> | <span data-ttu-id="db01e-143">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="db01e-143">Purchase order</span></span> | <span data-ttu-id="db01e-144">100001</span><span class="sxs-lookup"><span data-stu-id="db01e-144">100001</span></span> | <span data-ttu-id="db01e-145">0000101</span><span class="sxs-lookup"><span data-stu-id="db01e-145">0000101</span></span> | <span data-ttu-id="db01e-146">100,00</span><span class="sxs-lookup"><span data-stu-id="db01e-146">100.00</span></span>   | <span data-ttu-id="db01e-147">1 000,00</span><span class="sxs-lookup"><span data-stu-id="db01e-147">1000.00</span></span> |
| <span data-ttu-id="db01e-148">00002</span><span class="sxs-lookup"><span data-stu-id="db01e-148">00002</span></span>   | <span data-ttu-id="db01e-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="db01e-149">20-01-2015</span></span> | <span data-ttu-id="db01e-150">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="db01e-150">Purchase order</span></span> | <span data-ttu-id="db01e-151">100001</span><span class="sxs-lookup"><span data-stu-id="db01e-151">100001</span></span> | <span data-ttu-id="db01e-152">0000101</span><span class="sxs-lookup"><span data-stu-id="db01e-152">0000101</span></span> |          | <span data-ttu-id="db01e-153">100,00</span><span class="sxs-lookup"><span data-stu-id="db01e-153">100.00</span></span>  |
| <span data-ttu-id="db01e-154">00003</span><span class="sxs-lookup"><span data-stu-id="db01e-154">00003</span></span>   | <span data-ttu-id="db01e-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="db01e-155">31-01-2015</span></span> | <span data-ttu-id="db01e-156">Ajustement</span><span class="sxs-lookup"><span data-stu-id="db01e-156">Adjustment</span></span>     | <span data-ttu-id="db01e-157">100001</span><span class="sxs-lookup"><span data-stu-id="db01e-157">100001</span></span> | <span data-ttu-id="db01e-158">0000101</span><span class="sxs-lookup"><span data-stu-id="db01e-158">0000101</span></span> |          | <span data-ttu-id="db01e-159">15,00</span><span class="sxs-lookup"><span data-stu-id="db01e-159">15.00</span></span>   |

<span data-ttu-id="db01e-160">La page **Écritures de coût** active le filtrage par ID et date de document.</span><span class="sxs-lookup"><span data-stu-id="db01e-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="db01e-161">Ls écritures de coût sont disponibles uniquement pour les [objets de coût](cost-object.md) ou les produits lancés.</span><span class="sxs-lookup"><span data-stu-id="db01e-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="db01e-162">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="db01e-162">Additional resources</span></span>
--------

[<span data-ttu-id="db01e-163">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="db01e-163">Cost objects</span></span>](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]