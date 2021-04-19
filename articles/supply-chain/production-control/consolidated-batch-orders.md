---
title: Lots de production consolidés
description: Cet article décrit le concept des lots de production consolidés.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7656889b69cfd1dcffb45b52eb649bce59629
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809228"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="a1281-103">Lots de production consolidés</span><span class="sxs-lookup"><span data-stu-id="a1281-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1281-104">Cet article décrit le concept des lots de production consolidés.</span><span class="sxs-lookup"><span data-stu-id="a1281-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="a1281-105">Un consommable produit est considéré comme un article parent, tandis qu’un article emballé est considéré comme un article enfant.</span><span class="sxs-lookup"><span data-stu-id="a1281-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="a1281-106">La relation entre le consommable et l’article emballé est exprimé par une conversion de consommables.</span><span class="sxs-lookup"><span data-stu-id="a1281-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="a1281-107">Cette conversion de consommables est définie sur le consommable lui-même.</span><span class="sxs-lookup"><span data-stu-id="a1281-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="a1281-108">Les articles emballés peuvent être emballés dans des conteneurs d’une seule et même taille ou de tailles différentes, eux-mêmes considérés comme une unité.</span><span class="sxs-lookup"><span data-stu-id="a1281-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="a1281-109">En consolidant les commandes pour un consommable, vous pouvez voir tous les lots de commandes associés sur un seul et même écran, ce qui vous permet de déterminer le travail restant à effectuer.</span><span class="sxs-lookup"><span data-stu-id="a1281-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="a1281-110">Un lot de production consolidé peut contenir toute combinaison des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1281-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="a1281-111">Une commande en vrac simple et plusieurs commandes emballées</span><span class="sxs-lookup"><span data-stu-id="a1281-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="a1281-112">Plusieurs commandes en vrac et plusieurs commandes emballées</span><span class="sxs-lookup"><span data-stu-id="a1281-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="a1281-113">Plusieurs commandes en vrac et une seule commande emballée</span><span class="sxs-lookup"><span data-stu-id="a1281-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="a1281-114">Les commandes emballées seules</span><span class="sxs-lookup"><span data-stu-id="a1281-114">Only packed orders</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]