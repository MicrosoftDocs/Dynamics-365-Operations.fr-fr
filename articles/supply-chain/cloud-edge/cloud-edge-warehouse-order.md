---
title: Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie
description: Cette rubrique fournit des informations sur la capacité de commandes d’entrepôt dans le cadre de la charge de travail de l’unité d’échelle d’entrepôt.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105706"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a><span data-ttu-id="7e47f-103">Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie</span><span class="sxs-lookup"><span data-stu-id="7e47f-103">Warehouse orders for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="7e47f-104">Toutes les fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque des charges de travail d’unité d’échelle sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="7e47f-104">Not all business functionality is fully supported in the public preview when scale unit workloads are used.</span></span> <span data-ttu-id="7e47f-105">Si vous utilisez des unités d’échelle, veillez à n’utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7e47f-105">If you're using scale units, be sure to use only those processes that this topic explicitly describes as supported.</span></span>

## <a name="what-are-warehouse-orders"></a><span data-ttu-id="7e47f-106">Que sont les commandes d’entrepôt ?</span><span class="sxs-lookup"><span data-stu-id="7e47f-106">What are warehouse orders?</span></span>

<span data-ttu-id="7e47f-107">Les *commandes d’entrepôt* désignent un type de commande créée pour prendre en charge les déploiements en entrepôt de l’unité d’échelle et du hub.</span><span class="sxs-lookup"><span data-stu-id="7e47f-107">*Warehouse orders* are a type of order that was created to support hub and scale unit warehouse deployments.</span></span> <span data-ttu-id="7e47f-108">Ils vous permettent de recevoir un inventaire lorsque vous exécutez une charge de travail d’entrepôt sur une unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="7e47f-108">They let you receive inventory when you're running a warehouse workload on a scale unit.</span></span> <span data-ttu-id="7e47f-109">Actuellement, ils sont utilisés uniquement avec les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7e47f-109">They are currently used only with purchase orders.</span></span>

<span data-ttu-id="7e47f-110">Les commandes d’entrepôt sont utilisées dans le cadre du traitement de la gestion en entrepôt, comme lorsque l’application d’entreposage est utilisée pour enregistrer l’inventaire physique disponible pendant le traitement d’une commande fournisseur entrante.</span><span class="sxs-lookup"><span data-stu-id="7e47f-110">Warehouse orders are used as part of warehouse management processing, such as when the warehouse app is used to register physical on-hand inventory during processing of an inbound purchase order.</span></span> <span data-ttu-id="7e47f-111">Les commandes d’entrepôt sont créées dans le cadre du processus *Libération dans l’entrepôt* disponible pour les commandes fournisseur qui précisent un entrepôt d’unité d’échelle et des éléments qui sont activés pour utiliser les processus de gestion de l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="7e47f-111">Warehouse orders are created as part of the *Release to warehouse* process that is available for purchase orders that specify a scale unit warehouse and items that are enabled to use warehouse management processes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e47f-112">Les commandes d’entrepôt sont disponibles uniquement dans les déploiements qui utilisent les [charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="7e47f-112">Warehouse orders are available only in deployments that use [warehouse management workloads for cloud and edge scale units](cloud-edge-workload-warehousing.md).</span></span>

## <a name="create-a-warehouse-order"></a><span data-ttu-id="7e47f-113">Créer une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="7e47f-113">Create a warehouse order</span></span>

<span data-ttu-id="7e47f-114">Pour créer une commande d’entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7e47f-114">To create a warehouse order, follow these steps.</span></span>

1. <span data-ttu-id="7e47f-115">Connectez-vous à l’instance de Microsoft Dynamics 365 Supply Chain Management en cours d’exécution sur le hub.</span><span class="sxs-lookup"><span data-stu-id="7e47f-115">Sign in to the instance of Microsoft Dynamics 365 Supply Chain Management that is running on the hub.</span></span> <span data-ttu-id="7e47f-116">(Vous devez lancer le processus *Libération dans l’entrepôt* pendant que vous êtes connecté au hub.)</span><span class="sxs-lookup"><span data-stu-id="7e47f-116">(You must initiate the *Release to warehouse* process while you're signed in on the hub.)</span></span>
1. <span data-ttu-id="7e47f-117">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-117">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="7e47f-118">Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-118">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="7e47f-119">Pour afficher les lignes de la commande d’entrepôt associé, ouvrez la commande fournisseur pertinente, sélectionnez une ligne dans la section **Lignes de la commande fournisseur**, et sur la barre d’outils, sélectionnez **Entrepôt \> Lignes de la commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-119">To view the related warehouse order lines, open the relevant purchase order, select a line in the **Purchase order lines** section, and then, on the toolbar, select **Warehouse \> Warehouse order lines**.</span></span> <span data-ttu-id="7e47f-120">Pour afficher toutes les lignes, accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-120">To view all the lines, go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>

## <a name="cancel-a-warehouse-order"></a><span data-ttu-id="7e47f-121">Annuler une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="7e47f-121">Cancel a warehouse order</span></span>

<span data-ttu-id="7e47f-122">Dans le cadre du processus de *Libération dans l’entrepôt*, les transactions d’inventaire des commandes fournisseur sont liées aux commandes d’entrepôt et verrouillées pour ne pas être mises à jour par le hub.</span><span class="sxs-lookup"><span data-stu-id="7e47f-122">As part of the *Release to warehouse* process, purchase order inventory transactions are linked to warehouse orders and locked from being updated by the hub.</span></span> <span data-ttu-id="7e47f-123">Si vous avez libéré vers l’entrepôt par erreur, ou si vous avez pour toute autre raison annulé la création des lignes de commande d’entrepôt, vous pouvez demander l’annulation des lignes de commande d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="7e47f-123">If you released to the warehouse by mistake, or if you have some other reason to reverse the creation of warehouse order lines, you can request to cancel warehouse order lines.</span></span>

<span data-ttu-id="7e47f-124">Pour ce faire, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7e47f-124">To cancel warehouse order lines, follow these steps.</span></span>

1. <span data-ttu-id="7e47f-125">Connectez-vous à l’instance de Supply Chain Management en cours d’exécution sur le hub.</span><span class="sxs-lookup"><span data-stu-id="7e47f-125">Sign in to the Supply Chain Management instance that is running on the hub.</span></span>
1. <span data-ttu-id="7e47f-126">Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-126">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**.</span></span>
1. <span data-ttu-id="7e47f-127">Sélectionnez la ligne appropriée.</span><span class="sxs-lookup"><span data-stu-id="7e47f-127">Select the relevant line.</span></span>
1. <span data-ttu-id="7e47f-128">Dans le volet Actions, sélectionnez **Annuler les lignes de commande d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-128">On the Action Pane, select **Cancel warehouse order lines**.</span></span>

> [!NOTE]
> <span data-ttu-id="7e47f-129">La demande d’annulation de lignes sera refusée pour toutes les lignes qui sont déjà en attente d’annulation ou qui sont en cours de traitement dans un entrepôt qui exécute sa charge de travail sur une unité d’échelle.</span><span class="sxs-lookup"><span data-stu-id="7e47f-129">The request to cancel lines will be denied for any lines that are already pending cancellation or that are actively being processed at a warehouse that is running its workload on a scale unit.</span></span>

## <a name="monitor-a-warehouse-order"></a><span data-ttu-id="7e47f-130">Surveiller une commande d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="7e47f-130">Monitor a warehouse order</span></span>

<span data-ttu-id="7e47f-131">Dans la vue **Lignes de commande d’entrepôt**, vous pouvez surveiller la progression de la réception entrante en examinant les valeurs dans la colonne **Quantité en attente de réception**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-131">In the **Warehouse order lines** view, you can monitor the progress of inbound receiving by reviewing the values in the **Quantity left to receive** column.</span></span> <span data-ttu-id="7e47f-132">Pour afficher les détails liés au travail effectué à l’aide de l’application d’entreposage, suivez l’une de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="7e47f-132">To view details that are related to work that is done by using the warehouse app, follow one of these steps.</span></span>

- <span data-ttu-id="7e47f-133">Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt** et utilisez le filtre pour trouver les lignes que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="7e47f-133">Go to **Warehouse management \> Inquiries and reports \> Warehouse order lines**, and use the filter to find the lines that you're looking for.</span></span>
- <span data-ttu-id="7e47f-134">Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur** et ouvrez la commande fournisseur pertinente.</span><span class="sxs-lookup"><span data-stu-id="7e47f-134">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**, and open the relevant purchase order.</span></span> <span data-ttu-id="7e47f-135">Dans la section **Lignes de commande fournisseur**, sélectionnez une ou plusieurs lignes, puis, dans la barre d’outils, sélectionnez **Entrepôt \> Entrées de réception d’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="7e47f-135">In the **Purchase order lines** section, select one or more lines, and then, on the toolbar, select **Warehouse \> Warehouse receipt entries**.</span></span>
