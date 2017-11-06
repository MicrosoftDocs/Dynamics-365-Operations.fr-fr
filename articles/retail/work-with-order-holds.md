---
title: Blocage de commandes
description: "Cette rubrique décrit les blocages sur les commandes à l'aide de Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8b4c8ecbef1dc667d3b60411a53f0c63686529c2
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="order-holds"></a><span data-ttu-id="e9686-103">Blocage de commandes</span><span class="sxs-lookup"><span data-stu-id="e9686-103">Order holds</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="e9686-104">Cette rubrique décrit les blocages sur les commandes à l'aide de Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e9686-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="e9686-105">Une commande peut être mise en attente pour diverses raisons.</span><span class="sxs-lookup"><span data-stu-id="e9686-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="e9686-106">Par exemple, vous pouvez mettre une commande en attente jusqu'à ce que l'adresse du client ou le mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client.</span><span class="sxs-lookup"><span data-stu-id="e9686-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="e9686-107">Lors du processus de vente, des commandes client doivent parfois être mises en attente.</span><span class="sxs-lookup"><span data-stu-id="e9686-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="e9686-108">Par exemple, une commande client peut être mise en attente en raison de problèmes avec un paiement client, en raison d'une suspicion de fraude ou parce qu'un responsable doit réviser la commande.</span><span class="sxs-lookup"><span data-stu-id="e9686-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="e9686-109">Lorsqu'une commande client est mise en attente, un code de blocage de commande est affecté à la commande client pour indiquer le motif du blocage.</span><span class="sxs-lookup"><span data-stu-id="e9686-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="e9686-110">Les codes de blocage de commande client sont configurés dans **Ventes et marketing** &gt; **Paramétrage** &gt; **Commandes client** &gt; **Codes de blocage de commande**.</span><span class="sxs-lookup"><span data-stu-id="e9686-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="e9686-111">Une commande client peut être mise en attente manuellement au moment de la création de la commande ou ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="e9686-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="e9686-112">En outre, une commande peut être mise en attente automatiquement, en fonction des règles de fraude.</span><span class="sxs-lookup"><span data-stu-id="e9686-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="e9686-113">Pendant qu'une commande client est en attente, vous devrez peut-être la mettre à jour avec plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="e9686-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="e9686-114">Sinon, vous souhaitez peut-être contrôler la commande client pendant que vous continuez à travailler dessus.</span><span class="sxs-lookup"><span data-stu-id="e9686-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="e9686-115">Vous pouvez extraire une commande client, la réenregistrer, et même, remplacer l'extraction d'un autre utilisateur à l'aide de l'atelier de fin de blocage des commandes (**Vente au détail** &gt; **Clients** &gt; **Blocages de commande**).</span><span class="sxs-lookup"><span data-stu-id="e9686-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="e9686-116">Lorsqu'une commande est prête à être terminée, vous devez supprimer le blocage avant de terminer le processus de commande.</span><span class="sxs-lookup"><span data-stu-id="e9686-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




