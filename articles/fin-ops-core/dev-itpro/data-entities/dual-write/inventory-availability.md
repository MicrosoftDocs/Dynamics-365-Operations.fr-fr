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
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997890"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="0d164-103">Disponibilité du stock en double écriture</span><span class="sxs-lookup"><span data-stu-id="0d164-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0d164-104">Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d'ajouter un produit dans les formulaires **Devis** , **Commandes** ou **Factures** dans Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0d164-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations** , **Orders** , or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="0d164-105">Par exemple, la consultation du stock et la détermination d'une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="0d164-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="0d164-106">Si vous ne disposez pas d'un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues.</span><span class="sxs-lookup"><span data-stu-id="0d164-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="0d164-107">Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="0d164-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="0d164-108">Stock disponible</span><span class="sxs-lookup"><span data-stu-id="0d164-108">On-hand inventory</span></span>

<span data-ttu-id="0d164-109">Dans Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté à l'en-tête des pages **Devis** , **Commandes** et **Factures**.</span><span class="sxs-lookup"><span data-stu-id="0d164-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="0d164-110">Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible.</span><span class="sxs-lookup"><span data-stu-id="0d164-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="0d164-111">Cette boîte de dialogue affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="0d164-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="0d164-112">La boîte de dialogue renvoie les informations de stock de Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d164-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0d164-113">Ces informations incluent les quantités suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d164-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="0d164-114">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="0d164-114">On-hand quantity</span></span>
- <span data-ttu-id="0d164-115">Quantité disponible réservée</span><span class="sxs-lookup"><span data-stu-id="0d164-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="0d164-116">Quantité disponible à disposition</span><span class="sxs-lookup"><span data-stu-id="0d164-116">Available on-hand quantity</span></span>
- <span data-ttu-id="0d164-117">Quantité commandée</span><span class="sxs-lookup"><span data-stu-id="0d164-117">Ordered quantity</span></span>
- <span data-ttu-id="0d164-118">Quantité en commande</span><span class="sxs-lookup"><span data-stu-id="0d164-118">On-order quantity</span></span>
- <span data-ttu-id="0d164-119">Quantité commandée réservée</span><span class="sxs-lookup"><span data-stu-id="0d164-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="0d164-120">Quantité totale disponible</span><span class="sxs-lookup"><span data-stu-id="0d164-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="0d164-121">Informations sur DAV</span><span class="sxs-lookup"><span data-stu-id="0d164-121">ATP information</span></span>

<span data-ttu-id="0d164-122">Dans Sales, un nouveau bouton **Informations ATP** a été ajouté aux lignes dans les pages **Devis** , **Commandes** et **Factures**.</span><span class="sxs-lookup"><span data-stu-id="0d164-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="0d164-123">Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l'entrepôt et la quantité en commande.</span><span class="sxs-lookup"><span data-stu-id="0d164-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="0d164-124">Cette boîte de dialogue a les mêmes paramètres que ceux décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="0d164-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="0d164-125">La boîte de dialogue renvoie les informations ATP de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d164-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="0d164-126">Ces informations incluent les quantités suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d164-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="0d164-127">Quantité DAV</span><span class="sxs-lookup"><span data-stu-id="0d164-127">ATP quantity</span></span>
- <span data-ttu-id="0d164-128">Quantité de réception</span><span class="sxs-lookup"><span data-stu-id="0d164-128">Receipt quantity</span></span>
- <span data-ttu-id="0d164-129">Quantité de sortie</span><span class="sxs-lookup"><span data-stu-id="0d164-129">Issue quantity</span></span>
- <span data-ttu-id="0d164-130">Quantité disponible</span><span class="sxs-lookup"><span data-stu-id="0d164-130">On-hand quantity</span></span>
