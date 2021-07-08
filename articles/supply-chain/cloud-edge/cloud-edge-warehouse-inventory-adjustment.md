---
title: Ajustement du stock de l’entrepôt
description: Cette rubrique fournit des informations sur le journal d’ajustement des stocks de l’entrepôt et le traitement lorsque vous utilisez des unités d’échelle.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1bf147ce430d84980516d8d4824081ee2a9321a2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271230"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="89255-103">Ajustement du stock de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="89255-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89255-104">La fonction d’ajustement du stock en entrepôt est utilisée lors de l’exécution des unités d’échelle cloud et de périphérie pour les [charges de travail de fabrication](cloud-edge-workload-manufacturing.md) et les [charges de travail de gestion d’entrepôt](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="89255-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="89255-105">Lorsqu’un collaborateur effectue un ajustement de stock à l’aide de l’application d’entrepôt pour une charge de travail de gestion d’entrepôt utilisant un unité d’échelle, le stock physique disponible doit être mis à jour par la tâche de traitement par lots **Journal d’ajustement des stocks d’entrepôt**, que vous exécutez et planifiez en accédant à **Gestion des entrepôts >Tâches périodiques > Journal d’ajustement des stocks d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89255-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="89255-106">Les processus de travail suivants de l’application d’entrepôt utilisent actuellement les charges de travail d’unité d’échelle **Journal d’ajustement des stocks d’entrepôt** :</span><span class="sxs-lookup"><span data-stu-id="89255-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="89255-107">Ajustement (entrée/sortie)</span><span class="sxs-lookup"><span data-stu-id="89255-107">Adjustment in/out</span></span>
- <span data-ttu-id="89255-108">Inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="89255-108">Cycle counting</span></span>
- <span data-ttu-id="89255-109">Chargement de contenant</span><span class="sxs-lookup"><span data-stu-id="89255-109">License plate loading</span></span>

<span data-ttu-id="89255-110">Plusieurs transactions de stock sont créées dans le cadre de chaque processus d’ajustement, car les déploiements du hub et des unités d’échelle partagent les enregistrements de stock.</span><span class="sxs-lookup"><span data-stu-id="89255-110">Several inventory transactions are created as part of each inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="89255-111">Exemple d’ajustement de stock</span><span class="sxs-lookup"><span data-stu-id="89255-111">Inventory adjustment example</span></span>

<span data-ttu-id="89255-112">Dans cet exemple, un magasinier a utilisé l’application d’entrepôt pour enregistrer un ajout de stock disponible.</span><span class="sxs-lookup"><span data-stu-id="89255-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="89255-113">Tout d’abord, la charge de travail de l’unité d’échelle crée une transaction d’ajustement de stock d’entrepôt pour ajustement physique positif, qui est ensuite synchronisée avec le hub et entraîne une augmentation du stock disponible sur le hub.</span><span class="sxs-lookup"><span data-stu-id="89255-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="89255-114">Type</span><span class="sxs-lookup"><span data-stu-id="89255-114">Type</span></span>                                    | <span data-ttu-id="89255-115">Unité d’échelle</span><span class="sxs-lookup"><span data-stu-id="89255-115">Scale unit</span></span> | <span data-ttu-id="89255-116">Direction</span><span class="sxs-lookup"><span data-stu-id="89255-116">Direction</span></span> | <span data-ttu-id="89255-117">Hub</span><span class="sxs-lookup"><span data-stu-id="89255-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="89255-118">Ajustement du stock de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="89255-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="89255-119">+1</span><span class="sxs-lookup"><span data-stu-id="89255-119">+1</span></span>         | ->        | <span data-ttu-id="89255-120">+1</span><span class="sxs-lookup"><span data-stu-id="89255-120">+1</span></span>  |

<span data-ttu-id="89255-121">Le hub traite ensuite une écriture de journal de comptage, qui est reçue via les [messages du processeur de messages](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="89255-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="89255-122">Cela met à jour le stock supplémentaire disponible.</span><span class="sxs-lookup"><span data-stu-id="89255-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="89255-123">Pour éviter un double stock disponible, le hub crée une transaction de compensation dans le cadre de ce processus et supprime le stock disponible précédemment enregistré, lié à l’ajustement de stock d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89255-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="89255-124">Type</span><span class="sxs-lookup"><span data-stu-id="89255-124">Type</span></span>                                    | <span data-ttu-id="89255-125">Unité d’échelle</span><span class="sxs-lookup"><span data-stu-id="89255-125">Scale unit</span></span> | <span data-ttu-id="89255-126">Direction</span><span class="sxs-lookup"><span data-stu-id="89255-126">Direction</span></span> | <span data-ttu-id="89255-127">Hub</span><span class="sxs-lookup"><span data-stu-id="89255-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="89255-128">Comptage</span><span class="sxs-lookup"><span data-stu-id="89255-128">Counting</span></span>                                | <span data-ttu-id="89255-129">+1</span><span class="sxs-lookup"><span data-stu-id="89255-129">+1</span></span>         | <-        | <span data-ttu-id="89255-130">+1</span><span class="sxs-lookup"><span data-stu-id="89255-130">+1</span></span>  |
| <span data-ttu-id="89255-131">Ajustement de l’inventaire d’entrepôt (contrepartie)</span><span class="sxs-lookup"><span data-stu-id="89255-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="89255-132">-1</span><span class="sxs-lookup"><span data-stu-id="89255-132">-1</span></span>         | <-        | <span data-ttu-id="89255-133">-1</span><span class="sxs-lookup"><span data-stu-id="89255-133">-1</span></span>  |

<span data-ttu-id="89255-134">Une fois qu’une unité d’échelle a créé un **Journal d’ajustement des stocks d’entrepôt** sur le hub, vous pouvez consulter à la fois le **Journal de comptage** et le **Journal de compensation**, qui sont créés par le hub dans le cadre du processus d’ajustement.</span><span class="sxs-lookup"><span data-stu-id="89255-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="89255-135">Vous pouvez consulter chacune de ces écritures de journal et transactions dans Supply Chain Management en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="89255-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="89255-136">Connectez-vous à l’unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="89255-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="89255-137">Accédez à **Gestion des entrepôts \> Tâches périodiques \> Journal d’ajustement des stocks d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89255-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="89255-138">Sur la page **Journal d’ajustement des stocks d’entrepôt**, recherchez et ouvrez le journal qui a enregistré la variation de stock disponible.</span><span class="sxs-lookup"><span data-stu-id="89255-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="89255-139">La section **Lignes de journal** montre chaque ajustement enregistré par ce journal.</span><span class="sxs-lookup"><span data-stu-id="89255-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="89255-140">Connectez-vous au hub.</span><span class="sxs-lookup"><span data-stu-id="89255-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="89255-141">Accédez à **Gestion des entrepôts \> Tâches périodiques \> Journal d’ajustement des stocks d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89255-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="89255-142">Sur la page **Journal d’ajustement des stocks d’entrepôt**, vous devriez voir le même journal répertorié si le hub et l’unité d’échelle ont été synchronisés.</span><span class="sxs-lookup"><span data-stu-id="89255-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="89255-143">Ouvrez le journal.</span><span class="sxs-lookup"><span data-stu-id="89255-143">Open the journal.</span></span> <span data-ttu-id="89255-144">Si les [messages du processeur de messages](cloud-edge-message-processor-messages.md) ont été traités, vous verrez des liens vers le **Journal de comptage** et le **Journal de compensation** dans l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="89255-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="89255-145">Le **Journal de comptage** doit afficher les mêmes valeurs de dimension que les lignes du journal.</span><span class="sxs-lookup"><span data-stu-id="89255-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="89255-146">Le **Journal de compensation** doit afficher la compensation, ce qui supprime le double ajustement de stock.</span><span class="sxs-lookup"><span data-stu-id="89255-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="89255-147">Une fois la synchronisation et le traitement terminés, le **Journal de comptage** et le **Journal de compensation** sont synchronisés avec l’unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="89255-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="89255-148">Cela peut également être vérifié à partir de la page **Journal d’ajustement des stocks d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89255-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
