---
title: Le produit est en attente pour les transactions
description: Après avoir confirmé les ordres de planification, vous recevez un message d’erreur indiquant qu’un article est en attente pour les transactions.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301277"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="b37d7-103">Le produit est en attente pour les transactions</span><span class="sxs-lookup"><span data-stu-id="b37d7-103">Product is on hold for transactions</span></span>

<span data-ttu-id="b37d7-104">Code d’erreur : SYS13295</span><span class="sxs-lookup"><span data-stu-id="b37d7-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="b37d7-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="b37d7-105">Symptoms</span></span>

<span data-ttu-id="b37d7-106">Après avoir confirmé des commandes planifiées, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="b37d7-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="b37d7-107">L’article %1 est bloqué pour les transactions dans %2.</span><span class="sxs-lookup"><span data-stu-id="b37d7-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="b37d7-108">Cause</span><span class="sxs-lookup"><span data-stu-id="b37d7-108">Cause</span></span>

<span data-ttu-id="b37d7-109">Lors de la description des articles bloqués, le système utilise les termes *bloqué*, *arrêté* et *en attente* de manière interchangeable.</span><span class="sxs-lookup"><span data-stu-id="b37d7-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="b37d7-110">Cette erreur signifie que l’article est défini comme **Arrêté** dans ses paramètres de commande par défaut.</span><span class="sxs-lookup"><span data-stu-id="b37d7-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="b37d7-111">Si un article est bloqué et que vous l’ajoutez à une ligne de commande fournisseur ou de commande client, vous recevez un message d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="b37d7-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="b37d7-112">Lorsque l’article est bloqué, les mouvements de stock associés à la ligne de commande fournisseur ou client ne peuvent pas être modifiés (par exemple lors de la validation d’un bon de livraison ou d’une facture).</span><span class="sxs-lookup"><span data-stu-id="b37d7-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="b37d7-113">Vous pouvez bloquer un article acheté et, simultanément, vendre l’article.</span><span class="sxs-lookup"><span data-stu-id="b37d7-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="b37d7-114">Dans ce cas, la case **Arrêté** est sélectionnée sur une commande fournisseur, mais l’article n’est pas bloqué dans le stock ni sur une commande client.</span><span class="sxs-lookup"><span data-stu-id="b37d7-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="b37d7-115">Voici quelques-unes des conditions qui peuvent empêcher la vente d’un numéro d’article :</span><span class="sxs-lookup"><span data-stu-id="b37d7-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="b37d7-116">L’article est encore en cours de développement ou de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b37d7-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="b37d7-117">Par conséquent, vous ne voulez pas qu’il soit vendu ou réservé.</span><span class="sxs-lookup"><span data-stu-id="b37d7-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="b37d7-118">Vous avez reçu de nombreux articles défectueux et les défauts doivent être corrigés avant que l’article puisse être vendu.</span><span class="sxs-lookup"><span data-stu-id="b37d7-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="b37d7-119">Dans les cas de ce type; vous pouvez donc bloquer l’article jusqu’à la résolution du problème.</span><span class="sxs-lookup"><span data-stu-id="b37d7-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="b37d7-120">Si un article est bloqué et que vous créez une ligne d’ordre de retour, vous recevez un message.</span><span class="sxs-lookup"><span data-stu-id="b37d7-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="b37d7-121">Vous ne pouvez pas bloquer une série ni un lot d’articles.</span><span class="sxs-lookup"><span data-stu-id="b37d7-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="b37d7-122">Si des parties d’un article doivent être bloquées, vous pouvez le faire en déplaçant le stock ou en bloquant la totalité du stock de l’article pour cette période.</span><span class="sxs-lookup"><span data-stu-id="b37d7-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="b37d7-123">Résolution</span><span class="sxs-lookup"><span data-stu-id="b37d7-123">Resolution</span></span>

- <span data-ttu-id="b37d7-124">Ouvrez la page **Paramètres de commande par défaut** de l’article et décochez la case **Arrêté**.</span><span class="sxs-lookup"><span data-stu-id="b37d7-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
