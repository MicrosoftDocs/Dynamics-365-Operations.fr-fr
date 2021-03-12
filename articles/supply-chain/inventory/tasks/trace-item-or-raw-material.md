---
title: Suivre un article ou une matière première
description: Cette procédure illustre comment utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été ou sont utilisés.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 044b098b24d8cdf8008824b7ed1359f2b0566a8f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961486"
---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="84fcd-103">Suivre un article ou une matière première</span><span class="sxs-lookup"><span data-stu-id="84fcd-103">Trace an item or raw material</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="84fcd-104">Cette procédure illustre comment utiliser le suivi d'article pour identifier où les articles ou les matières premières ont été ou sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="84fcd-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="84fcd-105">Avec cette procédure, vous pouvez identifier un article, le suivre jusqu'à la source, puis le suivre à nouveau en avant via la production et la vente du produit fini.</span><span class="sxs-lookup"><span data-stu-id="84fcd-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="84fcd-106">Le processus peut être utilisé pour étudier les clients concernés, les commandes client affectées, et plus.</span><span class="sxs-lookup"><span data-stu-id="84fcd-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="84fcd-107">La société fictive USP2 sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="84fcd-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="84fcd-108">Suivre un article vers l'arrière à l'aide d'un numéro de lot connu</span><span class="sxs-lookup"><span data-stu-id="84fcd-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="84fcd-109">Dans le **Volet de navigation**, accédez à **Modules > Gestion des stocks > Recherches et états > Dimensions de suivi > Suivi d'article**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-109">In the **Navigation pane**, go to **Modules > Inventory management > Inquiries and reports > Tracking dimensions > Item tracing**.</span></span>
2. <span data-ttu-id="84fcd-110">Dans le champ **Numéro d'article**, sélectionnez « P9100 ».</span><span class="sxs-lookup"><span data-stu-id="84fcd-110">In the **Item number** field, select 'P9100'.</span></span>
3. <span data-ttu-id="84fcd-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84fcd-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="84fcd-112">Dans le champ **En avant ou En arrière**, sélectionnez « En arrière ».</span><span class="sxs-lookup"><span data-stu-id="84fcd-112">In the **Forward or backward** field, select 'Backward'.</span></span>
5. <span data-ttu-id="84fcd-113">Dans le champ **Numéro de lot**, sélectionnez « as-12-344-01 ».</span><span class="sxs-lookup"><span data-stu-id="84fcd-113">In the **Batch number** field, select 'as-12-344-01'.</span></span>
6. <span data-ttu-id="84fcd-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="84fcd-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="84fcd-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-115">Click **OK**.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="84fcd-116">Identifier un article, le suivre vers lavant, puis effectuer une analyse</span><span class="sxs-lookup"><span data-stu-id="84fcd-116">Identify an item, trace it forward, and make an analysis</span></span>

<span data-ttu-id="84fcd-117">Le nœud supérieur de l'arborescence représente la quantité disponible de l'article et du lot sélectionné.</span><span class="sxs-lookup"><span data-stu-id="84fcd-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="84fcd-118">Vous devez développer les nœuds de l'arborescence pour rechercher l'article sur lequel doit être exécuté le suivi en avant.</span><span class="sxs-lookup"><span data-stu-id="84fcd-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="84fcd-119">Dans l'arborescence, développez les nœuds décrits ci-dessous, puis sélectionnez le dernier nœud.</span><span class="sxs-lookup"><span data-stu-id="84fcd-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    
    <span data-ttu-id="84fcd-120">Développez : « P9100/1/10/as-12-344-01 ● 2 barils ● 7,00 gallons\P9100 ● Prélevé ● Commande client 000072 ● 22/12/2015 ● -1 baril ● -4,00 gallons ● Site=1, Entrepôt=10, Numéro de lot=as-12-344-01\P9100 ● Production B-000050 ● 9/12/2015 ● 7 barils ● 27,00 gallons ● Site=1, Entrepôt=10, Numéro de lot=as-12-344-01 ● Co-produits : P9101 » puis sélectionnez le nœud.</span><span class="sxs-lookup"><span data-stu-id="84fcd-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="84fcd-121">Dans l'arborescence, développez le nœud décrit ci-dessous, puis sélectionnez ce nœud.</span><span class="sxs-lookup"><span data-stu-id="84fcd-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    
    <span data-ttu-id="84fcd-122">À partir du nœud que vous venez de sélectionner, développez « M9103 ● Ligne de production B-000050 ● 12/9/2015 ● -80 kg ● Taille=70, Couleur=OK,Site=1, Entrepôt=10, Numéro de lot=App01 », puis sélectionnez ce nœud.</span><span class="sxs-lookup"><span data-stu-id="84fcd-122">Starting from the node that you've just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="84fcd-123">Cliquez sur **Suivi à partir du nœud**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-123">Click **Trace from node**.</span></span>
4. <span data-ttu-id="84fcd-124">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-124">Click **Forward**.</span></span>
5. <span data-ttu-id="84fcd-125">Dans le **volet Actions**, cliquez sur **Suivi**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-125">On the **Action Pane**, click **Tracing**.</span></span>
    
    <span data-ttu-id="84fcd-126">Il existe plusieurs options de suivi qui fournissent des informations sur les clients concernés par l'article que vous suivez, et sur les commandes client liées à l'article qui ont été ou non expédiées.</span><span class="sxs-lookup"><span data-stu-id="84fcd-126">There are several tracing options which provide information about the customers impacted by the item that you're tracing, and the sales orders related to the item which have and haven't been shipped.</span></span>   
6. <span data-ttu-id="84fcd-127">Cliquez sur **Clients**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-127">Click **Customers**.</span></span>
7. <span data-ttu-id="84fcd-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="84fcd-128">Close the page.</span></span>
8. <span data-ttu-id="84fcd-129">Dans le **volet Actions**, cliquez sur **Suivi**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-129">On the **Action Pane**, click **Tracing**.</span></span>
9. <span data-ttu-id="84fcd-130">Cliquez sur **Commandes client non expédiées**.</span><span class="sxs-lookup"><span data-stu-id="84fcd-130">Click **Shipped sales orders**.</span></span>
10. <span data-ttu-id="84fcd-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="84fcd-131">Close the page.</span></span>

