---
title: Résoudre les problèmes des opérations d’entrepôt sortantes
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts sortantes dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1344a1c16bf72b31f7aaf18aaeb6e08c7bc9d87e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223264"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="d3ec1-103">Résoudre les problèmes des opérations d’entrepôt sortantes</span><span class="sxs-lookup"><span data-stu-id="d3ec1-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3ec1-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors d’opérations d’entrepôts sortantes dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="d3ec1-105">Je reçois le message d’erreur suivant : "La commande client n’a pas pu être lancée".</span><span class="sxs-lookup"><span data-stu-id="d3ec1-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d3ec1-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-106">Issue description</span></span>

<span data-ttu-id="d3ec1-107">Ce problème peut se produire pour plusieurs raisons.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="d3ec1-108">Par exemple, la commande est en attente de gestion du crédit et aucune livraison ne peut être créée tant qu’une adresse postale valide n’est pas saisie pour toutes les lignes de vente associées à une commande client.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="d3ec1-109">Il existe également un blocage de commande qui doit être traité avant que la commande puisse être validée vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="d3ec1-110">Ce blocage peut être lié à la commande ou au compte client.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d3ec1-111">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-111">Issue resolution</span></span>

<span data-ttu-id="d3ec1-112">Ajoutez ou mettez à jour l’adresse sur la commande client et les lignes de commande, puis validez la commande vers l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="d3ec1-113">Les commandes ne peuvent être validées dans l’entrepôt que si elles ont une adresse de livraison valide (selon le format d’adresse configuré dans le module **Administration de l’organisation**).</span><span class="sxs-lookup"><span data-stu-id="d3ec1-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="d3ec1-114">Examinez le blocage de la commande et résolvez les problèmes.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="d3ec1-115">Supprimez ensuite le blocage de la commande ou du client et transférez la commande à l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="d3ec1-116">Je reçois le message suivant : "L’expédition pour chargement 1% a été confirmée. »</span><span class="sxs-lookup"><span data-stu-id="d3ec1-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="d3ec1-117">Cependant, aucune ligne n’est publiée.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d3ec1-118">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-118">Issue description</span></span>

<span data-ttu-id="d3ec1-119">Un envoi sur un chargement a été confirmé, mais aucun autre enregistrement n’a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d3ec1-120">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-120">Issue resolution</span></span>

<span data-ttu-id="d3ec1-121">La confirmation d’expédition n’affecte pas la publication.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="d3ec1-122">Elle met simplement à jour le statut de l’expédition et du chargement.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="d3ec1-123">La publication doit avoir lieu dans un processus distinct.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="d3ec1-124">Je reçois le message d’erreur suivant : "La livraison directe ne peut pas être traitée pour l’entrepôt 1% car la gestion d’entrepôt est activée.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="d3ec1-125">Spécifiez un autre entrepôt qui n’est pas activé pour la gestion de l’entrepôt. »</span><span class="sxs-lookup"><span data-stu-id="d3ec1-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d3ec1-126">Description du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-126">Issue description</span></span>

<span data-ttu-id="d3ec1-127">Un article est ajouté à une ligne de vente pour une livraison directe à partir d’un entrepôt activé pour la gestion des entrepôts (WMS).</span><span class="sxs-lookup"><span data-stu-id="d3ec1-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="d3ec1-128">Vous recevez ce message d’erreur lorsque la ligne de vente est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="d3ec1-129">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="d3ec1-129">Issue resolution</span></span>

<span data-ttu-id="d3ec1-130">Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="d3ec1-131">Actuellement, WMS ne prend pas en charge la livraison directe.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="d3ec1-132">Par conséquent, pour utiliser la livraison directe, vous devez sélectionner un article et un entrepôt non WMS.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]