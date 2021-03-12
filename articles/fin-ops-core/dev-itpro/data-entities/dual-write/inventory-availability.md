---
title: Disponibilité du stock en double écriture
description: Cette rubrique fournit des informations sur la consultation de la disponibilité du stock en double écriture.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: a7bfe998d2d787203a507a831c171fc43b03fedc
ms.sourcegitcommit: cc9921295f26804259cc9ec5137788ec9f2a4c6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2021
ms.locfileid: "4839547"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="5e44a-103">Disponibilité du stock en double écriture</span><span class="sxs-lookup"><span data-stu-id="5e44a-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e44a-104">Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d’ajouter un produit dans les formulaires **Devis**, **Commandes** ou **Factures** dans Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="5e44a-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="5e44a-105">Par exemple, la consultation du stock et la détermination d’une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="5e44a-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="5e44a-106">Si vous ne disposez pas d’un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues.</span><span class="sxs-lookup"><span data-stu-id="5e44a-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="5e44a-107">Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="5e44a-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="5e44a-108">Stock disponible</span><span class="sxs-lookup"><span data-stu-id="5e44a-108">On-hand inventory</span></span>

<span data-ttu-id="5e44a-109">Dans Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté à l’en-tête des pages **Devis**, **Commandes** et **Factures**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="5e44a-110">Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible.</span><span class="sxs-lookup"><span data-stu-id="5e44a-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="5e44a-111">Cette boîte de dialogue affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="5e44a-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="5e44a-112">La boîte de dialogue renvoie les informations de stock de Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e44a-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5e44a-113">Ces informations incluent les quantités suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e44a-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="5e44a-114">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="5e44a-114">On-hand quantity</span></span>
- <span data-ttu-id="5e44a-115">Quantité disponible réservée</span><span class="sxs-lookup"><span data-stu-id="5e44a-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="5e44a-116">Quantité disponible à disposition</span><span class="sxs-lookup"><span data-stu-id="5e44a-116">Available on-hand quantity</span></span>
- <span data-ttu-id="5e44a-117">Quantité commandée</span><span class="sxs-lookup"><span data-stu-id="5e44a-117">Ordered quantity</span></span>
- <span data-ttu-id="5e44a-118">Quantité en commande</span><span class="sxs-lookup"><span data-stu-id="5e44a-118">On-order quantity</span></span>
- <span data-ttu-id="5e44a-119">Quantité commandée réservée</span><span class="sxs-lookup"><span data-stu-id="5e44a-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="5e44a-120">Quantité totale disponible</span><span class="sxs-lookup"><span data-stu-id="5e44a-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="5e44a-121">Informations sur DAV</span><span class="sxs-lookup"><span data-stu-id="5e44a-121">ATP information</span></span>

<span data-ttu-id="5e44a-122">Dans Sales, un nouveau bouton **Informations ATP** a été ajouté aux lignes dans les pages **Devis**, **Commandes** et **Factures**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="5e44a-123">Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l’entrepôt et la quantité en commande.</span><span class="sxs-lookup"><span data-stu-id="5e44a-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="5e44a-124">Cette boîte de dialogue a les mêmes paramètres que ceux décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="5e44a-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="5e44a-125">La boîte de dialogue renvoie les informations ATP de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e44a-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="5e44a-126">Ces informations incluent les quantités suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e44a-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="5e44a-127">Quantité DAV</span><span class="sxs-lookup"><span data-stu-id="5e44a-127">ATP quantity</span></span>
- <span data-ttu-id="5e44a-128">Quantité de réception</span><span class="sxs-lookup"><span data-stu-id="5e44a-128">Receipt quantity</span></span>
- <span data-ttu-id="5e44a-129">Quantité de sortie</span><span class="sxs-lookup"><span data-stu-id="5e44a-129">Issue quantity</span></span>
- <span data-ttu-id="5e44a-130">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="5e44a-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5e44a-131">Comment ça fonctionne</span><span class="sxs-lookup"><span data-stu-id="5e44a-131">How it works</span></span>

<span data-ttu-id="5e44a-132">Lorsque vous sélectionnez le bouton **Stock disponible** sur la page **Devis**, **Commandes** ou **Factures**, un appel de double écriture en direct est effectué vers l'API **Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="5e44a-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="5e44a-133">L'API calcule le stock disponible pour le produit donné.</span><span class="sxs-lookup"><span data-stu-id="5e44a-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="5e44a-134">Le résultat est stocké dans les tables **InventCDSInventoryOnHandRequestEntity** et **InventCDSInventoryOnHandEntryEntity** , puis est écrit dans Dataverse par la double écriture.</span><span class="sxs-lookup"><span data-stu-id="5e44a-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="5e44a-135">Pour utiliser cette fonctionnalité, vous devez exécuter les mappages de double écriture suivants.</span><span class="sxs-lookup"><span data-stu-id="5e44a-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="5e44a-136">Ignorez la synchronisation initiale lorsque vous exécutez les mappages.</span><span class="sxs-lookup"><span data-stu-id="5e44a-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="5e44a-137">Entrées de stock CDS disponibles (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="5e44a-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="5e44a-138">Demandes de stock CDS disponibles (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="5e44a-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="5e44a-139">Modèles</span><span class="sxs-lookup"><span data-stu-id="5e44a-139">Templates</span></span>
<span data-ttu-id="5e44a-140">Les modèles suivants sont disponibles pour exposer les données de stock disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e44a-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="5e44a-141">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5e44a-141">Finance and Operations apps</span></span> | <span data-ttu-id="5e44a-142">Application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="5e44a-142">Customer engagement app</span></span> | <span data-ttu-id="5e44a-143">Description </span><span class="sxs-lookup"><span data-stu-id="5e44a-143">Description</span></span> 
---|---|---
[<span data-ttu-id="5e44a-144">Entrées disponibles dans le stock CDS</span><span class="sxs-lookup"><span data-stu-id="5e44a-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="5e44a-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="5e44a-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="5e44a-146">Demandes disponibles dans le stock CDS</span><span class="sxs-lookup"><span data-stu-id="5e44a-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="5e44a-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="5e44a-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="5e44a-148">Entrées de stock CDS disponibles (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="5e44a-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="5e44a-149">Ce modèle synchronise les données entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5e44a-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="5e44a-150">Champ Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5e44a-150">Finance and Operations field</span></span> | <span data-ttu-id="5e44a-151">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="5e44a-151">Map type</span></span> | <span data-ttu-id="5e44a-152">Champ Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="5e44a-152">Customer engagement field</span></span> | <span data-ttu-id="5e44a-153">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="5e44a-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="5e44a-154">Demandes de stock CDS disponibles(msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="5e44a-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="5e44a-155">Ce modèle synchronise les données entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5e44a-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="5e44a-156">Champ Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5e44a-156">Finance and Operations field</span></span> | <span data-ttu-id="5e44a-157">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="5e44a-157">Map type</span></span> | <span data-ttu-id="5e44a-158">Champ Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="5e44a-158">Customer engagement field</span></span> | <span data-ttu-id="5e44a-159">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="5e44a-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |




