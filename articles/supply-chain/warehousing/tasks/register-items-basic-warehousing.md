--- 
title: "Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles"
description: "Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ab824bd99347cbd090e99435217f9ce8ae992b3d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="00bf2-103">Enregistrer des articles pour un article activé pour l'entreposage de base à l'aide d'un journal des arrivées d'articles</span><span class="sxs-lookup"><span data-stu-id="00bf2-103">Register items for a basic warehousing enabled item using an item arrival journal</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="00bf2-104">Cette procédure décrit la manière dont vous enregistrez des articles à l'aide des journaux d'arrivée des articles lorsque vous utilisez l'« entreposage de base » dans le module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="00bf2-104">This procedure shows you how to register items using the item arrival journal when you are using “basic warehousing” in the Inventory management module.</span></span> <span data-ttu-id="00bf2-105">Cette opération est généralement effectuée par la personne qui s'occupe de la réception.</span><span class="sxs-lookup"><span data-stu-id="00bf2-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="00bf2-106">Vous pouvez exécuter cette procédure dans la société USMF fictive avec les valeurs d'exemple affichées.</span><span class="sxs-lookup"><span data-stu-id="00bf2-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="00bf2-107">Si vous n'utilisez pas USMF, vous devez avoir une commande fournisseur confirmée avec une ligne de commande fournisseur en cours avant de lancer ce guide.</span><span class="sxs-lookup"><span data-stu-id="00bf2-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="00bf2-108">L'article de la ligne doit être stocké et il ne doit ni utiliser les variantes de produit ni avoir des dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="00bf2-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="00bf2-109">Et l'article doit être associé à un groupe de dimension de stockage, dans lequel le site et l'entrepôt sont actifs.</span><span class="sxs-lookup"><span data-stu-id="00bf2-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="00bf2-110">Créer l'en-tête du journal des arrivées d'articles</span><span class="sxs-lookup"><span data-stu-id="00bf2-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="00bf2-111">Accédez à Gestion des stocks > Entrées de journal > Arrivée d'articles > Arrivée d'articles.</span><span class="sxs-lookup"><span data-stu-id="00bf2-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="00bf2-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="00bf2-112">Click New.</span></span>
3. <span data-ttu-id="00bf2-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="00bf2-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="00bf2-114">Si vous utilisez USMF, vous pouvez taper WHS.</span><span class="sxs-lookup"><span data-stu-id="00bf2-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="00bf2-115">Si vous utilisez d'autres données, le journal dont vous choisissez le nom doit avoir les propriétés suivantes : vérifiez l'emplacement de prélèvement doit être définie sur Non et Gestion des contrôles doit être définie sur Non.</span><span class="sxs-lookup"><span data-stu-id="00bf2-115">If you’re using other data, the journal whose name you choose has to have the following properties: check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="00bf2-116">Tapez une valeur dans le champ Bon de livraison.</span><span class="sxs-lookup"><span data-stu-id="00bf2-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="00bf2-117">Il s'agit de l'ID bon de livraison du bon de livraison émis par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00bf2-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="00bf2-118">Ajoutez un numéro unique.</span><span class="sxs-lookup"><span data-stu-id="00bf2-118">Add a unique number.</span></span>  
5. <span data-ttu-id="00bf2-119">Sélectionnez la commande fournisseur dans le champ Nombre.</span><span class="sxs-lookup"><span data-stu-id="00bf2-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="00bf2-120">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00bf2-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="00bf2-121">Ajouter des lignes aux journaux d'arrivée des articles</span><span class="sxs-lookup"><span data-stu-id="00bf2-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="00bf2-122">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="00bf2-122">Click Functions.</span></span>
2. <span data-ttu-id="00bf2-123">Cliquez sur Créer des lignes.</span><span class="sxs-lookup"><span data-stu-id="00bf2-123">Click Create lines.</span></span>
    * <span data-ttu-id="00bf2-124">Les lignes peuvent être entrées manuellement dans ce journal ou être créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="00bf2-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="00bf2-125">Cette opération vous indique comment créer cela automatiquement.</span><span class="sxs-lookup"><span data-stu-id="00bf2-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="00bf2-126">Cochez ou décochez la case Initialiser la quantité.</span><span class="sxs-lookup"><span data-stu-id="00bf2-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="00bf2-127">Cette opération initialisera la quantité sur les lignes de journal avec la quantité non enregistrée à partir de la ligne de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="00bf2-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="00bf2-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00bf2-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="00bf2-129">Valider le journal</span><span class="sxs-lookup"><span data-stu-id="00bf2-129">Post the journal</span></span>
1. <span data-ttu-id="00bf2-130">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="00bf2-130">Click Post.</span></span>
2. <span data-ttu-id="00bf2-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00bf2-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="00bf2-132">Générer l'accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="00bf2-132">Generate the product receipt</span></span>
1. <span data-ttu-id="00bf2-133">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="00bf2-133">Click Functions.</span></span>
2. <span data-ttu-id="00bf2-134">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="00bf2-134">Click Product receipt.</span></span>
3. <span data-ttu-id="00bf2-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="00bf2-135">Click OK.</span></span>


