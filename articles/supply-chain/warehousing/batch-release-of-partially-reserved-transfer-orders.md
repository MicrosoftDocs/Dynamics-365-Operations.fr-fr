---
title: "Lancement par lots des ordres de transfert partiellement réservés"
description: "Cette rubrique explique comment configurer et appliquer le lancement par lots des ordres de transfert partiellement réservés à partir d'un appareil mobile."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 3aa9b24c40efb053507b10a7a219857480e0b75e
ms.contentlocale: fr-fr
ms.lasthandoff: 12/14/2017

---

# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="2d620-103">Lancement par lots des ordres de transfert partiellement réservés</span><span class="sxs-lookup"><span data-stu-id="2d620-103">Batch release of partially reserved transfer orders</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2d620-104">La fonctionnalité de lancement par lots des ordres de transfert partiellement réservés permet de lancer partiellement des ordres de transfert à l'attention à un entrepôt à l'aide d'un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2d620-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="2d620-105">Comme vous avez la possibilité de lancer une quantité partielle, vous ne devez pas attendre que la quantité de la commande entière soit disponible dans l'entrepôt avant de lancer un ordre.</span><span class="sxs-lookup"><span data-stu-id="2d620-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="2d620-106">Le lancement des commandes à un entrepôt est un processus de gestion des entrepôts avancé.</span><span class="sxs-lookup"><span data-stu-id="2d620-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="2d620-107">Ce processus implique des activités, comme le prélèvement, l'emballage et l'expédition, auxquelles un employé d'entrepôt peut procéder à l'aide d'un périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="2d620-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="2d620-108">Dans ce cas</span><span class="sxs-lookup"><span data-stu-id="2d620-108">Where it applies</span></span>

<span data-ttu-id="2d620-109">Pour cette fonctionnalité, les ordres de transfert sont lancés à un entrepôt à l'aide d'un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="2d620-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="2d620-110">Cette fonctionnalité est utile si vous n'avez pas suffisamment de stock dans l'entrepôt, mais que vous souhaitez toujours transférer des articles d'un entrepôt à un autre.</span><span class="sxs-lookup"><span data-stu-id="2d620-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="2d620-111">Comment elle est paramétrée</span><span class="sxs-lookup"><span data-stu-id="2d620-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="2d620-112">Spécifier les critères d'exécution pour les ordres de transfert et les commandes client</span><span class="sxs-lookup"><span data-stu-id="2d620-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="2d620-113">Avant qu'un ordre puisse être partiellement lancé à un entrepôt dans un lot, les critères d'exécution doivent être remplis.</span><span class="sxs-lookup"><span data-stu-id="2d620-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="2d620-114">Ces critères d'exécution sont déterminés par la stratégie d'exécution.</span><span class="sxs-lookup"><span data-stu-id="2d620-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="2d620-115">Les stratégies d'exécution pour les ordres de transfert et les commandes client sont spécifiées pour la société.</span><span class="sxs-lookup"><span data-stu-id="2d620-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="2d620-116">En fonction du paramétrage de la stratégie d'exécution, le lancement des commandes dans un lot est accepté ou rejeté.</span><span class="sxs-lookup"><span data-stu-id="2d620-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="2d620-117">Les commandes sont ensuite traitées en conséquence.</span><span class="sxs-lookup"><span data-stu-id="2d620-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="2d620-118">Pour créer des stratégies d'exécution pour les ordres de transfert et les commandes client, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Libérer dans l'entrepôt** \> **Stratégie d'exécution**, puis créez une stratégie d'exécution de commande en entrant un nom et une description.</span><span class="sxs-lookup"><span data-stu-id="2d620-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="2d620-119">Pour spécifier un taux d'exécution, un type de valeur et le message qui s'affichent si la stratégie d'exécution n'est pas respectée, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Libérer dans l'entrepôt** \> **Stratégie d'exécution**, puis définissez les champs **Taux d'exécution**, **Type de valeur** et **Message de violation d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="2d620-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then set the **Fulfillment rate**, **Value type**, and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="2d620-120">Définir les stratégies d'exécution pour les ordres de transfert et les commandes client</span><span class="sxs-lookup"><span data-stu-id="2d620-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="2d620-121">Pour définir les stratégies d'exécution pour les ordres de transfert, cliquez sur **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts** \> **Ordres de transfert** \> **Gestion des entrepôts**, puis sélectionnez une stratégie d'exécution d'ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="2d620-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management**, and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="2d620-122">Pour définir les stratégies d'exécution de commande pour les commandes client, cliquez sur **Ventes** \> **Paramétrage** \> **Paramètres des ventes** \> **Gestion des entrepôts**, puis sélectionnez une stratégie d'exécution de commande client.</span><span class="sxs-lookup"><span data-stu-id="2d620-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management**, and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="2d620-123">Autoriser le lancement dans un lot et spécifier la quantité qui doit être lancée dans un lot</span><span class="sxs-lookup"><span data-stu-id="2d620-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="2d620-124">Un traitement par lots est utilisé pour lancer des ordres à un entrepôt dans un lot.</span><span class="sxs-lookup"><span data-stu-id="2d620-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="2d620-125">Les paramètres qui distinguent les ordres qui doivent être exécutés dans un traitement par lots sont définis dans le traitement par lots lui-même.</span><span class="sxs-lookup"><span data-stu-id="2d620-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="2d620-126">Le paramètre **Quantité** spécifie si toute la quantité ou la quantité physiquement réservée doit être lancée dans le lot.</span><span class="sxs-lookup"><span data-stu-id="2d620-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="2d620-127">Le paramètre **Autoriser la libération des commandes partiellement libérées** détermine si les ordres du lot doivent être acceptés ou rejetés s'ils ont été partiellement lancés précédemment.</span><span class="sxs-lookup"><span data-stu-id="2d620-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="2d620-128">Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les ordres de transfert, cliquez sur **Gestion des entrepôts** \> **Libérer dans l'entrepôt** \> **Lancement automatique des ordres de transfert**.</span><span class="sxs-lookup"><span data-stu-id="2d620-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="2d620-129">Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les commandes client, cliquez sur **Gestion des entrepôts** \> **Libérer dans l'entrepôt** \> **Lancement automatique de commandes client**.</span><span class="sxs-lookup"><span data-stu-id="2d620-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>

