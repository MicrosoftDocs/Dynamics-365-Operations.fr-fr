---
title: Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie
description: Cette rubrique fournit des informations sur la capacité de commandes d’entrepôt dans le cadre de la charge de travail de l’unité d’échelle d’entrepôt.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ff1f13198a7acc35897252f3ca8f6c2b1f56852e
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938274"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="e3695-103">Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie</span><span class="sxs-lookup"><span data-stu-id="e3695-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="e3695-104">Toutes les fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque des charges de travail d’unité d’échelle sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="e3695-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="e3695-105">Si vous utilisez des unités d’échelle, veillez à n’utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e3695-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="e3695-106">Que sont les commandes d’entrepôt ?</span><span class="sxs-lookup"><span data-stu-id="e3695-106">What are warehouse orders?</span></span>

<span data-ttu-id="e3695-107">Les *commandes d’entrepôt* désignent un type de commande créée pour prendre en charge les déploiements en entrepôt de l’unité d’échelle et du hub.</span><span class="sxs-lookup"><span data-stu-id="e3695-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="e3695-108">Ils vous permettent de recevoir un inventaire lorsque vous exécutez une charge de travail d’entrepôt sur une unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="e3695-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="e3695-109">Actuellement, ils sont utilisés uniquement avec les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3695-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="e3695-110">Les commandes d’entrepôt sont utilisées dans le cadre du traitement de la gestion en entrepôt, comme lorsque application mobile Gestion des entrepôts est utilisée pour enregistrer l’inventaire physique disponible pendant le traitement d’une commande fournisseur entrante.</span><span class="sxs-lookup"><span data-stu-id="e3695-110">Warehouse orders are used as part of warehouse management processing, such as when the Warehouse Management mobile app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="e3695-111">Les commandes d’entrepôt sont créées dans le cadre du processus *Libération dans l’entrepôt* disponible pour les commandes fournisseur qui précisent un entrepôt d’unité d’échelle et des éléments qui sont activés pour utiliser les processus de gestion de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e3695-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3695-112">Les commandes d’entrepôt sont disponibles uniquement dans les déploiements qui utilisent les [charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="e3695-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="e3695-113">Créer une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="e3695-113">Create a warehouse order</span></span>

<span data-ttu-id="e3695-114">Pour créer une commande d’entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e3695-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="e3695-115">Connectez-vous à l’instance de Microsoft Dynamics 365 Supply Chain Management en cours d’exécution sur le hub.</span><span class="sxs-lookup"><span data-stu-id="e3695-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="e3695-116">(Vous devez lancer le processus *Libération dans l’entrepôt* pendant que vous êtes connecté au hub.)</span><span class="sxs-lookup"><span data-stu-id="e3695-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="e3695-117">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="e3695-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="e3695-118">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="e3695-119">Pour afficher les lignes de la commande d’entrepôt associé, ouvrez la commande fournisseur pertinente, sélectionnez une ligne dans la section **Lignes de la commande fournisseur**, et sur la barre d’outils, sélectionnez **Entrepôt \> Lignes de la commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="e3695-120">Pour afficher toutes les lignes, accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

<span data-ttu-id="e3695-121">Vous pouvez également déclencher le processus *Libération dans l’entrepôt* à partir d’un traitement par lots en accédant à **Gestion des entrepôts > Libération vers l’entrepôt > Libération automatique des commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="e3695-121">You can also trigger the *Release to warehouse* process from a batch job by going to **Warehouse management > Release to warehouse > Automatic release of purchase orders**.</span></span> <span data-ttu-id="e3695-122">Lors de la configuration du traitement par lots, vous pouvez sélectionner des lignes de commande fournisseur spécifiques en fonction d’une requête.</span><span class="sxs-lookup"><span data-stu-id="e3695-122">When setting up the batch job, you can select specific purchase order lines based on a query.</span></span> <span data-ttu-id="e3695-123">Un scénario typique serait de configurer un traitement par lots récurrent qui libère toutes les lignes de commande fournisseur confirmées qui devraient arriver le jour suivant.</span><span class="sxs-lookup"><span data-stu-id="e3695-123">A typical scenario would be to set up a recurrent batch job that releases all the confirmed purchase order lines expected to arrive the next day.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="e3695-124">Annuler une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="e3695-124">Cancel a warehouse order</span></span>

<span data-ttu-id="e3695-125">Dans le cadre du processus de *Libération dans l’entrepôt*, les transactions d’inventaire des commandes fournisseur sont liées aux commandes d’entrepôt et verrouillées pour ne pas être mises à jour par le hub.</span><span class="sxs-lookup"><span data-stu-id="e3695-125">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="e3695-126">Si vous avez libéré vers l’entrepôt par erreur, ou si vous avez pour toute autre raison annulé la création des lignes de commande d’entrepôt, vous pouvez demander l’annulation des lignes de commande d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e3695-126">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="e3695-127">Pour ce faire, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e3695-127">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="e3695-128">Connectez-vous à l’instance de Supply Chain Management en cours d’exécution sur le hub.</span><span class="sxs-lookup"><span data-stu-id="e3695-128">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="e3695-129">Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-129">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="e3695-130">Sélectionnez la ligne appropriée.</span><span class="sxs-lookup"><span data-stu-id="e3695-130">Select the relevant line.</span></span>
1. <span data-ttu-id="e3695-131">Dans le volet Actions, sélectionnez **Annuler les lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-131">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="e3695-132">La demande d’annulation de lignes sera refusée pour toutes les lignes qui sont déjà en attente d’annulation ou qui sont en cours de traitement dans un entrepôt qui exécute sa charge de travail sur une unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="e3695-132">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="e3695-133">Surveiller une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="e3695-133">Monitor a warehouse order</span></span>

<span data-ttu-id="e3695-134">Dans la vue **Lignes de commande d’entrepôt**, vous pouvez surveiller la progression de la réception entrante en examinant les valeurs dans la colonne **Quantité en attente de réception**.</span><span class="sxs-lookup"><span data-stu-id="e3695-134">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="e3695-135">Pour afficher les détails liés au travail effectué à l’aide de l’application mobile Gestion des entrepôts, suivez l’une de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="e3695-135">To view details that are related to work that is done by using the Warehouse Management mobile app, follow one of these steps.</span></span>

- <span data-ttu-id="e3695-136">Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt** et utilisez le filtre pour trouver les lignes que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="e3695-136">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="e3695-137">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur** et ouvrez la commande fournisseur pertinente.</span><span class="sxs-lookup"><span data-stu-id="e3695-137">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="e3695-138">Dans la section **Lignes de commande fournisseur**, sélectionnez une ou plusieurs lignes, puis, dans la barre d’outils, sélectionnez **Entrepôt \> Entrées de réception d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e3695-138">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
