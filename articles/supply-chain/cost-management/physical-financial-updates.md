---
title: Mises à jour physiques et financières
description: Cette rubrique fournit une vue d'ensemble des types de transactions qui augmentent les quantités en stock ou de celles qui les diminuent.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ea79bd9c6561c4e4f6fad2c177f44fe62bdea5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428074"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="57257-103">Mises à jour physiques et financières</span><span class="sxs-lookup"><span data-stu-id="57257-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57257-104">Cette rubrique fournit une vue d'ensemble des types de transactions qui augmentent les quantités en stock ou de celles qui les diminuent.</span><span class="sxs-lookup"><span data-stu-id="57257-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="57257-105">Les transactions de stock peuvent être mises à jour physiquement et financièrement dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="57257-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="57257-106">Certains types de transactions physiques et financières augmentent les quantités en stock, tandis que d'autres les diminuent.</span><span class="sxs-lookup"><span data-stu-id="57257-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="57257-107">Augmentations physiques</span><span class="sxs-lookup"><span data-stu-id="57257-107">Physical increases</span></span>
<span data-ttu-id="57257-108">Lorsqu'une transaction physique est validée, le statut de l'enregistrement de la transaction est **Reçu**.</span><span class="sxs-lookup"><span data-stu-id="57257-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="57257-109">Les transactions suivantes sont considérées comme des augmentations physiques :</span><span class="sxs-lookup"><span data-stu-id="57257-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="57257-110">Réceptions de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="57257-110">Purchase order receipt</span></span>
-   <span data-ttu-id="57257-111">Retour de bon de livraison de commande client</span><span class="sxs-lookup"><span data-stu-id="57257-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="57257-112">Déclaration de fin d'ordres de fabrication</span><span class="sxs-lookup"><span data-stu-id="57257-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="57257-113">Sous-produit sur des prélèvements d'ordres de fabrication</span><span class="sxs-lookup"><span data-stu-id="57257-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="57257-114">Augmentations financières</span><span class="sxs-lookup"><span data-stu-id="57257-114">Financial increases</span></span>
<span data-ttu-id="57257-115">Lorsqu'une transaction de réception financière est validée, le statut de l'enregistrement de la transaction qui augmente la quantité est **Acheté**.</span><span class="sxs-lookup"><span data-stu-id="57257-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="57257-116">Les transactions suivantes sont considérées comme des augmentations financières :</span><span class="sxs-lookup"><span data-stu-id="57257-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="57257-117">Facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="57257-117">Vendor invoice</span></span>
-   <span data-ttu-id="57257-118">Facture de commande client pour un retour</span><span class="sxs-lookup"><span data-stu-id="57257-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="57257-119">Évaluation des coûts de l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="57257-119">Production order costing</span></span>
-   <span data-ttu-id="57257-120">Journaux de stock de quantité positive, tels que mouvement, résultat, inventaire, nomenclatures et transferts</span><span class="sxs-lookup"><span data-stu-id="57257-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="57257-121">Transactions qui augmentent la quantité</span><span class="sxs-lookup"><span data-stu-id="57257-121">Transactions that increase quantity</span></span>
<span data-ttu-id="57257-122">Les transactions qui augmentent la quantité sont validées au prix de revient moyen en vigueur.</span><span class="sxs-lookup"><span data-stu-id="57257-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="57257-123">Le prix de revient moyen calculé en vigueur est basé sur le coût de chacune de ces transactions pour chaque dimension de stock suivie financièrement.</span><span class="sxs-lookup"><span data-stu-id="57257-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="57257-124">Pour plus d'informations sur l'exécution d'un prix de revient moyen, voir [Prix de revient moyen en cours](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="57257-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="57257-125">Transactions qui diminuent la quantité</span><span class="sxs-lookup"><span data-stu-id="57257-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="57257-126">Le prix de revient moyen calculé est utilisé lorsqu'une transaction qui diminue la quantité est validée, quel que soit le modèle de stock associé au stock.</span><span class="sxs-lookup"><span data-stu-id="57257-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="57257-127">Cela nécessite que la transaction qui diminue la quantité n'ait pas été marquée par rapport à une autre transaction avant la validation.</span><span class="sxs-lookup"><span data-stu-id="57257-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="57257-128">Si le stock physique disponible devient négatif, le coût du stock défini pour l'article sur la page **Article** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="57257-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="57257-129">Si la fonctionnalité multisite est activée, ce coût sera alors le coût de stock défini pour un site sur la page **Paramètres de commande par défaut**.</span><span class="sxs-lookup"><span data-stu-id="57257-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="57257-130">Comparatif Sorties physiques/Sorties financières</span><span class="sxs-lookup"><span data-stu-id="57257-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="57257-131">Lorsqu'une transaction de sortie physique est validée, le statut de l'enregistrement de la transaction est **Déduit**.</span><span class="sxs-lookup"><span data-stu-id="57257-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="57257-132">Les transactions suivantes sont considérées comme des sorties physiques :</span><span class="sxs-lookup"><span data-stu-id="57257-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="57257-133">Journaux des prélèvements d'ordres de fabrication</span><span class="sxs-lookup"><span data-stu-id="57257-133">Production order picking list journal</span></span>
-   <span data-ttu-id="57257-134">Bon de livraison de commande client</span><span class="sxs-lookup"><span data-stu-id="57257-134">Sales order packing slip</span></span>
-   <span data-ttu-id="57257-135">Retour de bon de livraison de commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="57257-135">Purchase order packing slip return</span></span>

<span data-ttu-id="57257-136">Lorsqu'une transaction financière est validée, le statut de l'enregistrement de la transaction est **Vendu**.</span><span class="sxs-lookup"><span data-stu-id="57257-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="57257-137">Les transactions suivantes sont considérées comme des sorties financières :</span><span class="sxs-lookup"><span data-stu-id="57257-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="57257-138">Fin d'un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="57257-138">Ending a production order</span></span>
-   <span data-ttu-id="57257-139">Facture de commande client</span><span class="sxs-lookup"><span data-stu-id="57257-139">Sales order invoice</span></span>
-   <span data-ttu-id="57257-140">Retour de facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="57257-140">Vendor invoice return</span></span>
-   <span data-ttu-id="57257-141">Journaux de stock de quantité négative, tels que mouvement, résultat, inventaire, nomenclatures et transferts</span><span class="sxs-lookup"><span data-stu-id="57257-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="57257-142">Les transactions qui diminuent la quantité sont validées au prix de revient moyen en vigueur.</span><span class="sxs-lookup"><span data-stu-id="57257-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="57257-143">Aussi, la procédure de clôture du stock est requise pour régler les transactions de sorties en transactions de réception sur la base du modèle de stock affecté à chaque article.</span><span class="sxs-lookup"><span data-stu-id="57257-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>
