---
title: Retourner des articles pour plusieurs commandes et factures client
description: Cette rubrique décrit la fonctionnalité d’activation des retours pour plusieurs commandes et factures client dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4d1be6606793d498d01be91de6205e3a45c6dfdf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251257"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="a858c-103">Retourner des articles pour plusieurs commandes et factures client</span><span class="sxs-lookup"><span data-stu-id="a858c-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="a858c-104">Cet article décrit deux fonctionnalités qui optimisent les retours de commandes client sur plusieurs factures.</span><span class="sxs-lookup"><span data-stu-id="a858c-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="a858c-105">Activer les remboursements sur plusieurs captures</span><span class="sxs-lookup"><span data-stu-id="a858c-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="a858c-106">Cette fonctionnalité permet plusieurs remboursements liés à la même commande client.</span><span class="sxs-lookup"><span data-stu-id="a858c-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="a858c-107">Accédez à l’espace de travail **Gestion des fonctionnalités** et recherchez **Activer les remboursements sur plusieurs captures**.</span><span class="sxs-lookup"><span data-stu-id="a858c-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="a858c-108">Sélectionnez **Activer les remboursements sur plusieurs commandes**, puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="a858c-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="a858c-109">Activer le calcul de taxe correct pour les retours avec une quantité partielle</span><span class="sxs-lookup"><span data-stu-id="a858c-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="a858c-110">Cette fonctionnalité garantit que lorsqu’une commande est retournée à l’aide de plusieurs factures, les taxes seront finalement égales au montant des taxes initialement facturées.</span><span class="sxs-lookup"><span data-stu-id="a858c-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="a858c-111">Accédez à l’espace de travail **Gestion des fonctionnalités** et recherchez **Activer le calcul de taxe correct pour les retours avec une quantité partielle**.</span><span class="sxs-lookup"><span data-stu-id="a858c-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="a858c-112">Sélectionnez **Activer le calcul de taxe correct pour les retours avec une quantité partielle**, puis cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="a858c-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="a858c-113">Traiter les retours</span><span class="sxs-lookup"><span data-stu-id="a858c-113">Process returns</span></span>

<span data-ttu-id="a858c-114">Une fois ces fonctionnalités activées et les modifications synchronisées avec les magasins, le caissier du magasin peut sélectionner plusieurs commandes d’un client pour les retourner.</span><span class="sxs-lookup"><span data-stu-id="a858c-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="a858c-115">Lorsque les commandes sont sélectionnées, la liste de tous les produits retournables pour toutes les factures des commandes s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a858c-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="a858c-116">Le caissier peut ensuite sélectionner les produits à retourner.</span><span class="sxs-lookup"><span data-stu-id="a858c-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="a858c-117">Un ordre de retour unique sera créé pour tous les produits sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a858c-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="a858c-118">Si l’ordre est retourné intégralement, le montant des taxes restitué au client sera égal au montant des taxes initialement facturées.</span><span class="sxs-lookup"><span data-stu-id="a858c-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]