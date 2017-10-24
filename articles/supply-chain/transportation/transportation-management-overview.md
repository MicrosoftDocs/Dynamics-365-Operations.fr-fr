---
title: Vue d'ensemble de la gestion du transport
description: "Cette rubrique fournit une vue d'ensemble de la fonctionnalité de gestion du transport dans Microsoft Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1c71c8f6c4f94342ac18cbfb7dfbc02ddb3f9f35
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="transportation-management-overview"></a><span data-ttu-id="f9584-103">Vue d'ensemble de la gestion du transport</span><span class="sxs-lookup"><span data-stu-id="f9584-103">Transportation management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f9584-104">Cette rubrique fournit une vue d'ensemble de la fonctionnalité de gestion du transport dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9584-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="f9584-105">La Gestion du transport vous permet d'utiliser les transports de votre société et d'identifier les solutions utilisant des fournisseurs et des prestataires d'acheminement spécifiques pour les commandes entrantes et sortantes.</span><span class="sxs-lookup"><span data-stu-id="f9584-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="f9584-106">Par exemple, vous pouvez identifier le parcours le plus rapide ou le moins cher pour une expédition.</span><span class="sxs-lookup"><span data-stu-id="f9584-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="f9584-107">Le tableau suivant décrit les principaux scénarios utilisés pour la gestion du transport dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9584-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9584-108">Scénario</span><span class="sxs-lookup"><span data-stu-id="f9584-108">Scenario</span></span></th>
<th><span data-ttu-id="f9584-109">Avantages de la Gestion du transport</span><span class="sxs-lookup"><span data-stu-id="f9584-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f9584-110">Utilisez des fournisseurs logistique externes pour les activités de transport.</span><span class="sxs-lookup"><span data-stu-id="f9584-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="f9584-111">Utilisez la Gestion du transport pour le transport entrant et/ou sortant.</span><span class="sxs-lookup"><span data-stu-id="f9584-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f9584-112">La propre flotte de la société est disponible pour la livraison/le chargement et les frais de livraison sont transférés aux clients.</span><span class="sxs-lookup"><span data-stu-id="f9584-112">The company's own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="f9584-113">Pour les processus sortants, vous pouvez utiliser la Gestion du transport pour déterminer les frais de transport et les transférer aux clients.</span><span class="sxs-lookup"><span data-stu-id="f9584-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="f9584-114">Toutefois, le processus de rapprochement de la facture du transporteur n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f9584-114">However, the carrier invoice reconciliation process isn't required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f9584-115">La propre flotte de la société est disponible pour la livraison/le chargement, mais des frais de livraison ne sont pas transférés aux clients, car les prix des produits comprennent le transport.</span><span class="sxs-lookup"><span data-stu-id="f9584-115">The company's own fleet is available for delivery/pickup, but delivery charges aren't passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="f9584-116">Une grande partie de la fonctionnalité Gestion du transport n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f9584-116">A lot of the Transportation management functionality isn't required.</span></span> <span data-ttu-id="f9584-117">Toutefois, vous pouvez utiliser la Gestion du transport pour déterminer les taux de transport et pour ajuster le prix de vente en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f9584-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f9584-118">Le service logistique est fourni par une autre entité juridique dans la même société.</span><span class="sxs-lookup"><span data-stu-id="f9584-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="f9584-119">Utilisez la Gestion du transport en traitant l'autre entité juridique comme n'importe quel transporteur.</span><span class="sxs-lookup"><span data-stu-id="f9584-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="f9584-120">Vous ne pouvez pas automatiser les transactions économiques entre les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="f9584-120">You can't automate the economic transactions between legal entities.</span></span> <span data-ttu-id="f9584-121">Par conséquent, vous devez gérer ces transactions manuellement (par exemple, en créant une commande fournisseur).</span><span class="sxs-lookup"><span data-stu-id="f9584-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="f9584-122">Dans l'entité juridique qui fournit les services logistiques, la Gestion du transport peut être utilisée pour déterminer les taux de transport.</span><span class="sxs-lookup"><span data-stu-id="f9584-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="f9584-123">Planification du transport dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f9584-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="f9584-124">Dans Gestion du transport, la planification des transports peut être basée sur les commandes ou sur les expéditions créées selon ces commandes.</span><span class="sxs-lookup"><span data-stu-id="f9584-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="f9584-125">Les expéditions existent toujours à un moment donné mais elles ne sont pas requises pour la planification des transports.</span><span class="sxs-lookup"><span data-stu-id="f9584-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="f9584-126">Les ordres de transfert font partie du scénario sortant et peuvent être planifiés avec des commandes client.</span><span class="sxs-lookup"><span data-stu-id="f9584-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Load drawing](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="f9584-128">Transport entrant</span><span class="sxs-lookup"><span data-stu-id="f9584-128">Inbound transportation</span></span>
<span data-ttu-id="f9584-129">Lorsque vous commandez des articles à un fournisseur et que ces articles doivent être livrés à votre entrepôt, vous pouvez souhaiter organiser le transport des articles vous-même.</span><span class="sxs-lookup"><span data-stu-id="f9584-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="f9584-130">Utilisez Finance and Operations pour planifier le transport et la réception de la charge entrante.</span><span class="sxs-lookup"><span data-stu-id="f9584-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="f9584-131">La figure suivante indique le flux du processus entreprise de planification du transport pour un chargement entrant.</span><span class="sxs-lookup"><span data-stu-id="f9584-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Flux de processus entreprise pour le transport de chargement entrant](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="f9584-133">Transport sortant</span><span class="sxs-lookup"><span data-stu-id="f9584-133">Outbound transportation</span></span>
<span data-ttu-id="f9584-134">Vous pouvez planifier et traiter une charge sortante pour expédier des articles spécifiques de l'entrepôt d'une société à un client.</span><span class="sxs-lookup"><span data-stu-id="f9584-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="f9584-135">Utilisez Finance and Operations pour planifier le transport et l'expédition d'une charge sortante.</span><span class="sxs-lookup"><span data-stu-id="f9584-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="f9584-136">La figure suivante indique le flux du processus entreprise de planification et le traitement des charges sortantes pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="f9584-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planification et traitement des charges sortantes](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="f9584-138">Création de chargement</span><span class="sxs-lookup"><span data-stu-id="f9584-138">Load building</span></span>
<span data-ttu-id="f9584-139">Finance and Operations fournit une stratégie de création de chargement qui est nommée Stratégie de création de chargement basée sur le volume.</span><span class="sxs-lookup"><span data-stu-id="f9584-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="f9584-140">Cette stratégie vous permet d'utiliser les valeurs maximales spécifiées pour la hauteur et le poids dans le modèle de chargement, sinon vous pouvez remplacer les paramètres en entrant de nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="f9584-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="f9584-141">Pour utiliser cette stratégie, sélectionnez-la dans le champ **Stratégie de création de chargement** dans l'organisateur **Paramétrage** sur la page **Atelier de création de chargement**.</span><span class="sxs-lookup"><span data-stu-id="f9584-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="f9584-142">En outre, vous pouvez ajouter vos propres stratégies de création de chargement en créant une nouvelle classe dans l'arbre d'objets d'application (AOA).</span><span class="sxs-lookup"><span data-stu-id="f9584-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>




