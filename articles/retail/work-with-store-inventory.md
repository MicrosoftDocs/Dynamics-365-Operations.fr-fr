---
title: "Gérer le stock de magasin"
description: "Cet article décrit les types de documents qui peuvent être utilisés pour gérer le stock."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6245d37ace9f46ecce83a0cf80a014d5de898bbc
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="manage-store-inventory"></a><span data-ttu-id="3dbb9-103">Gérer le stock de magasin</span><span class="sxs-lookup"><span data-stu-id="3dbb9-103">Manage store inventory</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="3dbb9-104">Cet article décrit les types de documents qui peuvent être utilisés pour gérer le stock.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-104">This article describes the types of documents that you can use to manage inventory.</span></span>

<span data-ttu-id="3dbb9-105">Les types de documents suivants peuvent être utilisés pour gérer le stock de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-105">You can use the following types of documents to manage your organization's inventory.</span></span>

## <a name="purchase-orders"></a><span data-ttu-id="3dbb9-106">Commandes fournisseur</span><span class="sxs-lookup"><span data-stu-id="3dbb9-106">Purchase orders</span></span>
<span data-ttu-id="3dbb9-107">Les commandes fournisseur sont créées au siège social.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-107">Purchase orders are created at the head office.</span></span> <span data-ttu-id="3dbb9-108">Si un entrepôt de détail est indiqué dans l'en-tête de la commande fournisseur, la commande peut être reçue au magasin à l'aide de Modern POS (MPOS) ou de Cloud POS dans Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-108">If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="3dbb9-109">Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-109">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="3dbb9-110">Les quantités peuvent aussi être validées et envoyées au siège social.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-110">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="3dbb9-111">Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-111">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the purchase order.</span></span>

## <a name="transfer-orders"></a><span data-ttu-id="3dbb9-112">Ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="3dbb9-112">Transfer orders</span></span>
<span data-ttu-id="3dbb9-113">Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement à partir duquel les articles peuvent être expédiés.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-113">A transfer order can specify that a particular store is a location that items can be shipped from.</span></span> <span data-ttu-id="3dbb9-114">Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de prélèvement dans MPOS ou Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-114">In this case, the transfer order appears at the store as a picking request in MPOS or Cloud POS.</span></span> <span data-ttu-id="3dbb9-115">Après avoir été prélevées, les quantités demandées sont validées et envoyées au siège social.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-115">After the quantities that are requested are picked, they are committed and sent to the head office.</span></span> <span data-ttu-id="3dbb9-116">Au siège social, les quantités qui ont été prélevées au magasin sont affichées dans Microsoft Dynamics 365 for Retail, dans le champ **Expédier maintenant** de l'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-116">At the head office, the quantities that were picked at the store are displayed in Dynamics 365 for Retail, in the **Ship now** field on the transfer order.</span></span> <span data-ttu-id="3dbb9-117">Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement vers lequel les articles peuvent être expédiés.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-117">A transfer order may specify that a particular store is a location that items can be shipped to.</span></span> <span data-ttu-id="3dbb9-118">Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de réception dans MPOS ou Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-118">In this case, the transfer order appears at the store as a receiving request in MPOS or Cloud POS.</span></span> <span data-ttu-id="3dbb9-119">Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-119">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="3dbb9-120">Les quantités peuvent aussi être validées et envoyées au siège social.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-120">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="3dbb9-121">Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de l'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-121">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the transfer order.</span></span>

## <a name="stock-counts"></a><span data-ttu-id="3dbb9-122">Inventaires</span><span class="sxs-lookup"><span data-stu-id="3dbb9-122">Stock counts</span></span>
<span data-ttu-id="3dbb9-123">Les inventaires peuvent être planifiés ou non planifiés.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-123">Stock counts can be either scheduled or unscheduled.</span></span> <span data-ttu-id="3dbb9-124">Les inventaires planifiés sont engagés par le siège social, qui spécifie les articles à inventorier.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-124">Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</span></span> <span data-ttu-id="3dbb9-125">Le siège social crée un document d'inventaire qui peut être reçu au magasin, où les quantités du stock réel et disponible sont entrées dans MPOS ou Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-125">The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</span></span> <span data-ttu-id="3dbb9-126">Les inventaires non planifiés sont effectués dans un magasin et les quantités de stock disponible réelles sont mises à jour dans MPOS ou Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-126">Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</span></span> <span data-ttu-id="3dbb9-127">Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-127">Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</span></span> <span data-ttu-id="3dbb9-128">Lorsqu'un inventaire de l'un ou l'autre type est terminé, il est validé et envoyé au siège social.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-128">When a stock count of either type is completed, it is committed and sent to the head office.</span></span> <span data-ttu-id="3dbb9-129">Au siège social, le nombre est contrôlé et validé.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-129">At the head office, the count is validated and posted.</span></span>

## <a name="inventory-lookup"></a><span data-ttu-id="3dbb9-130">Recherche de stock</span><span class="sxs-lookup"><span data-stu-id="3dbb9-130">Inventory lookup</span></span>
<span data-ttu-id="3dbb9-131">La quantité actuelle disponible de produits pour plusieurs magasins et entrepôts peut être affichée dans la page Recherche de stock.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-131">The current product quantity on hand for multiple stores and warehouses can be viewed on the Inventory lookup page.</span></span> <span data-ttu-id="3dbb9-132">En plus de la quantité actuelle disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-132">In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</span></span> <span data-ttu-id="3dbb9-133">Pour ce faire, sélectionnez le magasin dont vous souhaitez afficher les quantités disponibles à la vente, puis cliquez sur **Afficher la disponibilité du magasin**.</span><span class="sxs-lookup"><span data-stu-id="3dbb9-133">To do so, select the store that you want to view the ATP for and then click **Show store availability**.</span></span>





