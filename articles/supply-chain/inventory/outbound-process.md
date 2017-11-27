---
title: Processus sortant
description: Cette rubrique fournit une vue d'ensemble du processus sortant dans la Gestion des stocks.
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1b8b17b719713097d77a117cca53eff6886ff1c7
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="outbound-process"></a><span data-ttu-id="8393d-103">Processus sortant</span><span class="sxs-lookup"><span data-stu-id="8393d-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8393d-104">Cette rubrique fournit une vue d'ensemble du processus sortant dans la Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="8393d-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="8393d-105">Ordres de sortie</span><span class="sxs-lookup"><span data-stu-id="8393d-105">Output orders</span></span>

<span data-ttu-id="8393d-106">Les ordres de sortie permettent de lier les lignes de commande client et les lignes d'ordre de transfert avec les processus sortants de prélèvement qui utilisent des prélèvements.</span><span class="sxs-lookup"><span data-stu-id="8393d-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="8393d-107">Lorsque des prélèvements sont générés à partir de commandes client ou d'ordres de transfert, des ordres de sortie et des expéditions sont automatiquement créés.</span><span class="sxs-lookup"><span data-stu-id="8393d-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="8393d-108">Un prélèvement a une relation de 1 à 1 avec une expédition.</span><span class="sxs-lookup"><span data-stu-id="8393d-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="8393d-109">L'expédition de l'ordre de transfert ou le bon de livraison de la commande client peut être traité(e) à l'expédition.</span><span class="sxs-lookup"><span data-stu-id="8393d-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="8393d-110">Le diagramme suivant présente une vue d'ensemble du processus relatif aux ordres de sortie.</span><span class="sxs-lookup"><span data-stu-id="8393d-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="8393d-111">[![Vue d'ensemble du processus relatif aux ordres de sortie](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="8393d-112">Vous pouvez paramétrer des règles sortantes pour définir la manière dont le programme doit gérer le processus sortant.</span><span class="sxs-lookup"><span data-stu-id="8393d-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="8393d-113">Vous pouvez utiliser ces règles pour contrôler le processus d'expédition.</span><span class="sxs-lookup"><span data-stu-id="8393d-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="8393d-114">En particulier, vous pouvez utiliser les règles pour contrôler à quel stade du processus une expédition peut être effectuée.</span><span class="sxs-lookup"><span data-stu-id="8393d-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="8393d-115">Les paramètres suivants définissent la manière dont les processus sortants sont gérés.</span><span class="sxs-lookup"><span data-stu-id="8393d-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="8393d-116">Statut du parcours de prélèvement pour les commandes client et les ordres de transfert</span><span class="sxs-lookup"><span data-stu-id="8393d-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="8393d-117">Accédez à **Comptabilité client** \> **Paramétrage** \> **Paramètres de comptabilité client**, puis, dans l'onglet **Mises à jour**, sélectionnez une valeur dans le champ **Statut du parcours de prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="8393d-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="8393d-118">[![Champ Statut du parcours de prélèvement pour les commandes client](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="8393d-119">Si le champ **Statut du parcours de prélèvement** est défini sur **Terminé**, le processus de prélèvement s'effectue automatiquement dans le cadre du processus de génération des prélèvements.</span><span class="sxs-lookup"><span data-stu-id="8393d-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="8393d-120">Si le champ est défini sur **Activé**, les lignes de prélèvement doivent être manuellement mises à jour.</span><span class="sxs-lookup"><span data-stu-id="8393d-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="8393d-121">Le même paramétrage s'applique aux ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="8393d-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="8393d-122">Accédez à **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts**, puis, dans l'onglet **Transport**, sélectionnez une valeur dans le champ **Statut du parcours de prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="8393d-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="8393d-123">[![Champ Statut du parcours de prélèvement pour les ordres de transfert](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="8393d-124">Fin de la commande de stock sortante</span><span class="sxs-lookup"><span data-stu-id="8393d-124">End output inventory orders</span></span>

<span data-ttu-id="8393d-125">Accédez à **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts**, puis, dans l'onglet **Général**, définissez l'option **Fin de la commande de stock sortante**.</span><span class="sxs-lookup"><span data-stu-id="8393d-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="8393d-126">[![Option Fin de la commande de stock sortante](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="8393d-127">Lorsque le magasinier réduit les quantités de prélèvements, les quantités de la commande de stock correspondantes sont supprimées de l'expédition.</span><span class="sxs-lookup"><span data-stu-id="8393d-127">When the warehouse worker reduces the picking list quantities, then the corresponding inventory order quantities will be removed from the shipment.</span></span> <span data-ttu-id="8393d-128">Lorsque le prélèvement est mis à jour à un moment donné, les quantités restantes sont déclarées et reviennent au niveau de la commande si l'option **Fin de la commande de stock sortante** est définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="8393d-128">When the picking list is updated at a point in time, the remaining quantities get reported back to the order if the **End output inventory order** option is set to **Yes**.</span></span> <span data-ttu-id="8393d-129">Si l'option **Fin de la commande de stock sortante** est définie sur **Non**, les quantités restantes sont conservées comme quantité d'ordre de sortie ouvert et doivent être ajoutées à un nouveau prélèvement dans le cadre de la fonctionnalité **Ouvrir les ordres de sortie**.</span><span class="sxs-lookup"><span data-stu-id="8393d-129">If the **End output inventory order** option is set to **No**, the remaining quantities are kept as an open output order quantity and must be added to a new picking list as part of the **Open output orders** functionality.</span></span> 

<span data-ttu-id="8393d-130">[![Commande Ouvrir les ordres de sortie du menu Fonctions](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-130">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="8393d-131">[![Menu Fonctions de la page Ouvrir les ordres de sortie](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-131">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="8393d-132">Réduire la quantité</span><span class="sxs-lookup"><span data-stu-id="8393d-132">Reduce quantity</span></span>

<span data-ttu-id="8393d-133">Le troisième paramètre que vous pouvez utiliser dans le cadre du processus de génération des prélèvements est le paramètre **Réduire la quantité**.</span><span class="sxs-lookup"><span data-stu-id="8393d-133">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="8393d-134">La définition de ce paramètre fonctionne avec le paramètre **Réservation** qui déclenche un processus de réservation dans le cadre de la libération dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="8393d-134">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="8393d-135">[![Paramètre Réduire la quantité](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-135">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="8393d-136">Exemple d'un processus sortant pour une commande client</span><span class="sxs-lookup"><span data-stu-id="8393d-136">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="8393d-137">Pour cet exemple, il existe une commande client pour deux articles.</span><span class="sxs-lookup"><span data-stu-id="8393d-137">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="8393d-138">Lors de la génération des prélèvements, sélectionnez le paramètre **Réduire la quantité**.</span><span class="sxs-lookup"><span data-stu-id="8393d-138">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="8393d-139">Par conséquent, vous lancez et créez des lignes de prélèvement uniquement pour le stock disponible.</span><span class="sxs-lookup"><span data-stu-id="8393d-139">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="8393d-140">Le prélèvement doit être déclaré via un processus d'enregistrement des prélèvements (**Statut du parcours de prélèvement** = **Activé**).</span><span class="sxs-lookup"><span data-stu-id="8393d-140">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="8393d-141">Le stock qui n'a pas encore été réservé est réservé lors de la génération du prélèvement.</span><span class="sxs-lookup"><span data-stu-id="8393d-141">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="8393d-142">Le stock disponible peut être supprimé de la commande client ou libéré vers l'entrepôt pour traitement sortant ultérieurement, lorsque le stock est disponible pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="8393d-142">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="8393d-143">[![Mettre à jour les prélèvements](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-143">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="8393d-144">Dès que toutes les lignes de prélèvement sont prélevées sur la page **Confirmation prélèvement**, l'expédition associée est terminée.</span><span class="sxs-lookup"><span data-stu-id="8393d-144">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="8393d-145">Le processus pour les bons de livraison de commande client peut ensuite être initialisé selon le stock prélevé.</span><span class="sxs-lookup"><span data-stu-id="8393d-145">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="8393d-146">[![Mettre à jour les expéditions sortantes](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="8393d-146">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>

