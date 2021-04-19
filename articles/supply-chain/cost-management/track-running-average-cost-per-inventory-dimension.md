---
title: Suivi du coût moyen en vigueur par dimension de stock
description: Un groupe de dimensions de stock est associé à chaque article en stock. Par conséquent, le prix de revient moyen en vigueur d’un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8da13a01b28ca09ce9c29ecd3a9342dfb9eaa4bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834311"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="c4c56-104">Suivi du coût moyen en vigueur par dimension de stock</span><span class="sxs-lookup"><span data-stu-id="c4c56-104">Track running average cost per inventory dimension</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4c56-105">Un groupe de dimensions de stock est associé à chaque article en stock.</span><span class="sxs-lookup"><span data-stu-id="c4c56-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="c4c56-106">Par conséquent, le prix de revient moyen en vigueur d’un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier.</span><span class="sxs-lookup"><span data-stu-id="c4c56-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="c4c56-107">Il existe trois types de dimensions de stock : produit, stockage et suivi.</span><span class="sxs-lookup"><span data-stu-id="c4c56-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="c4c56-108">Les dimensions de produit comprennent une configuration, une taille et une couleur.</span><span class="sxs-lookup"><span data-stu-id="c4c56-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="c4c56-109">Leur suivi financier est toujours assuré.</span><span class="sxs-lookup"><span data-stu-id="c4c56-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="c4c56-110">Les dimensions de stockage et de suivi comprennent un site, un entrepôt, un emplacement, un statut de stock, un contenant, un numéro de lot et un numéro de série.</span><span class="sxs-lookup"><span data-stu-id="c4c56-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="c4c56-111">Vous pouvez choisir quelles dimensions de stockage et de suivi sont suivies au niveau financier.</span><span class="sxs-lookup"><span data-stu-id="c4c56-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="c4c56-112">**Exemple 1**</span><span class="sxs-lookup"><span data-stu-id="c4c56-112">**Example 1**</span></span> 

<span data-ttu-id="c4c56-113">Si le groupe de dimensions de stockage associé à l’article est suivi financièrement par entrepôt, le prix moyen actuel est calculé pour chaque entrepôt.</span><span class="sxs-lookup"><span data-stu-id="c4c56-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="c4c56-114">Les commandes fournisseur suivantes ont été facturées :</span><span class="sxs-lookup"><span data-stu-id="c4c56-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="c4c56-115">Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l’entrepôt EG.</span><span class="sxs-lookup"><span data-stu-id="c4c56-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="c4c56-116">Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l’entrepôt EG.</span><span class="sxs-lookup"><span data-stu-id="c4c56-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="c4c56-117">Une commande fournisseur comportant cinq articles à un prix de revient de 15,00 EUR a été facturée pour l’entrepôt EG.</span><span class="sxs-lookup"><span data-stu-id="c4c56-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="c4c56-118">Le prix de revient moyen en vigueur pour l’entrepôt EG est de 11,20 EUR, et le prix de revient moyen en vigueur pour l’entrepôt EP est de 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="c4c56-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="c4c56-119">Une facture de commande client est validée pour l’entrepôt EG.</span><span class="sxs-lookup"><span data-stu-id="c4c56-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="c4c56-120">La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 11,20 EUR.</span><span class="sxs-lookup"><span data-stu-id="c4c56-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="c4c56-121">Une autre commande client est validée pour l’entrepôt EP.</span><span class="sxs-lookup"><span data-stu-id="c4c56-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="c4c56-122">La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="c4c56-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="c4c56-123">**Exemple 2** Si le groupe de dimensions de stockage associé à l’article est suivi financièrement par entrepôt, et le groupe de dimensions de suivi est suivi financièrement par numéro de lot, le prix de revient moyen en vigueur est calculé pour chaque lot.</span><span class="sxs-lookup"><span data-stu-id="c4c56-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="c4c56-124">**Remarque :** nous vous recommandons de toujours afficher le prix de revient pour toutes les dimensions financières suivies actuellement.</span><span class="sxs-lookup"><span data-stu-id="c4c56-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="c4c56-125">Les commandes fournisseur suivantes ont été facturées :</span><span class="sxs-lookup"><span data-stu-id="c4c56-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="c4c56-126">Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l’entrepôt EG et le lot AAA.</span><span class="sxs-lookup"><span data-stu-id="c4c56-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="c4c56-127">Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l’entrepôt EG et le lot AAA.</span><span class="sxs-lookup"><span data-stu-id="c4c56-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="c4c56-128">Une commande fournisseur comportant deux articles à un prix de revient de 15,00 EUR a été facturée pour l’entrepôt EG et le lot BBB.</span><span class="sxs-lookup"><span data-stu-id="c4c56-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="c4c56-129">Le prix de revient moyen en vigueur pour l’entrepôt EG et le lot AAA est de 11,20 EUR, et le prix de revient moyen en vigueur pour l’entrepôt EP et le lot BBB est de 15,00 EUR.</span><span class="sxs-lookup"><span data-stu-id="c4c56-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]