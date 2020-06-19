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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426980"
---
# <a name="inventory-availability"></a><span data-ttu-id="5a90a-103">Disponibilité du stock</span><span class="sxs-lookup"><span data-stu-id="5a90a-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5a90a-104">Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d'ajouter un produit dans les formulaires **Devis**, **Commandes** ou **Factures** dans les applications pilotées par modèles dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5a90a-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="5a90a-105">Par exemple, la consultation du stock et la détermination d'une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="5a90a-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="5a90a-106">Si vous ne disposez pas d'un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues.</span><span class="sxs-lookup"><span data-stu-id="5a90a-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="5a90a-107">Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="5a90a-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="5a90a-108">Stock disponible</span><span class="sxs-lookup"><span data-stu-id="5a90a-108">On-hand Inventory</span></span> 

<span data-ttu-id="5a90a-109">Dans l'en-tête des formulaires **Devis**, **Commandes** ou **Factures** de Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="5a90a-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="5a90a-110">Lorsque vous cliquez sur le bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible.</span><span class="sxs-lookup"><span data-stu-id="5a90a-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="5a90a-111">Il renvoie les informations de stock de Dynamics 365 Supply Chain Management et affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="5a90a-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="5a90a-112">Ces informations comprennent ces quantités :</span><span class="sxs-lookup"><span data-stu-id="5a90a-112">The information includes these quantities:</span></span>

- <span data-ttu-id="5a90a-113">**Quantité disponible**</span><span class="sxs-lookup"><span data-stu-id="5a90a-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="5a90a-114">**Quantité disponible réservée**</span><span class="sxs-lookup"><span data-stu-id="5a90a-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="5a90a-115">**Quantité disponible à disposition**</span><span class="sxs-lookup"><span data-stu-id="5a90a-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="5a90a-116">**Quantité commandée**</span><span class="sxs-lookup"><span data-stu-id="5a90a-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="5a90a-117">**Quantité en commande**</span><span class="sxs-lookup"><span data-stu-id="5a90a-117">**On-order Quantity**</span></span>
- <span data-ttu-id="5a90a-118">**Quantité commandée réservée**</span><span class="sxs-lookup"><span data-stu-id="5a90a-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="5a90a-119">**Quantité totale disponible**</span><span class="sxs-lookup"><span data-stu-id="5a90a-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="5a90a-120">Informations sur DAV</span><span class="sxs-lookup"><span data-stu-id="5a90a-120">ATP information</span></span>

<span data-ttu-id="5a90a-121">Dans les articles de ligne des formulaires **Devis**, **Commandes** ou **Factures** de Dynamics 365 Sales, un nouveau bouton **Informations DAV** a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="5a90a-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="5a90a-122">Lorsque vous cliquez sur le bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l'entrepôt et la quantité en commande.</span><span class="sxs-lookup"><span data-stu-id="5a90a-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="5a90a-123">Il renvoie les **Informations DAV** de Supply Chain Management et affiche les paramètres décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="5a90a-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="5a90a-124">Les informations comprennent **Quantité DAV**, **Quantité de réception**, **Quantité de sortie** et **Quantité disponible**.</span><span class="sxs-lookup"><span data-stu-id="5a90a-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
