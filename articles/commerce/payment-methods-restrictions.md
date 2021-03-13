---
title: Restreindre les modes de paiement pour les retours sans reçu
description: Cette rubrique décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.
author: rapraj
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1ff301aa5f88e34ed7ca24aa54df3fdc7daa1bf7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012389"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="64e34-103">Restreindre les modes de paiement pour les retours sans reçu</span><span class="sxs-lookup"><span data-stu-id="64e34-103">Restrict payment methods for returns without a receipt</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="64e34-104">Chaque type de paiement accepté par un détaillant doit être configurée lors du paramétrage du système.</span><span class="sxs-lookup"><span data-stu-id="64e34-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="64e34-105">Cette rubrique décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.</span><span class="sxs-lookup"><span data-stu-id="64e34-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="64e34-106">paramétrer les modes de paiement ;</span><span class="sxs-lookup"><span data-stu-id="64e34-106">Set up payment methods</span></span>

<span data-ttu-id="64e34-107">Pour paramétrer les modes de paiement, vous devez effectuer les tâches suivantes.</span><span class="sxs-lookup"><span data-stu-id="64e34-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="64e34-108">Créer les modes de paiement acceptés par l'ensemble de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="64e34-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="64e34-109">Création de types et de numéros de cartes pour l'organisation.</span><span class="sxs-lookup"><span data-stu-id="64e34-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="64e34-110">Si les cartes de crédit ou de débit sont acceptées, vous devez créer un mode de paiement par carte, puis créer les types et numéros de cartes pour toute l'organisation.</span><span class="sxs-lookup"><span data-stu-id="64e34-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="64e34-111">Paramétrer les modes de paiement du magasin.</span><span class="sxs-lookup"><span data-stu-id="64e34-111">Set up store payment methods.</span></span> <span data-ttu-id="64e34-112">Associez les modes de paiement à chaque magasin, puis entrez les paramètres propres au magasin pour chaque mode de paiement de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="64e34-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="64e34-113">Paramétrer les modes de paiement par carte pour les magasins.</span><span class="sxs-lookup"><span data-stu-id="64e34-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="64e34-114">Vous devez paramétrer la carte pour tous les modes de paiement par carte acceptés par le magasin.</span><span class="sxs-lookup"><span data-stu-id="64e34-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="64e34-115">![Paramétrage du magasin](media/NoReceiptReturns1.png "Paramétrage du magasin de vente au détail")</span><span class="sxs-lookup"><span data-stu-id="64e34-115">![Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="64e34-116">Restreindre les modes de paiement pour les retours sans reçu</span><span class="sxs-lookup"><span data-stu-id="64e34-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="64e34-117">Pour chaque mode de paiement du magasin, dans la page **Gestion du magasin**, sous **Retours sans reçu**, définissez **Limite pour les remboursements sans reçu** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="64e34-117">For each store payment method, on the **Store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="64e34-118">La valeur par défaut du bouton d'activation/de désactivation est **Non**, ce qui garantit que le mode de paiement est autorisé pour les remboursements.</span><span class="sxs-lookup"><span data-stu-id="64e34-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="64e34-119">Lorsque **Limitation des remboursements sans réception** est défini sur **Activé**, le mode de paiement sélectionné ne sera pas autorisé pour les remboursements.</span><span class="sxs-lookup"><span data-stu-id="64e34-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="64e34-120">![Mode de paiement du magasin](media/NoReceiptReturns3.png "Mode de paiement du magasin de vente au détail")</span><span class="sxs-lookup"><span data-stu-id="64e34-120">![Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="64e34-121">Quand un agent de caisse sélectionne un mode de paiement limité au remboursement sans reçu, un message s'affiche pour vérifier les modes de paiement acceptables.</span><span class="sxs-lookup"><span data-stu-id="64e34-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="64e34-122">![Modes de paiement acceptables](media/NoReceiptReturns4.png "Modes de paiement acceptables")</span><span class="sxs-lookup"><span data-stu-id="64e34-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="64e34-123">Si une transaction a à la fois un retour avec reçu et un retour sans reçu, les conditions de restriction ne seront pas appliquées, car la transaction est un workflow de retour avec reçu.</span><span class="sxs-lookup"><span data-stu-id="64e34-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

