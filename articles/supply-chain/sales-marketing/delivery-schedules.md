---
title: Plans de livraison
description: "Les plans de livraison vous permettent de suivre la quantité sur la ligne de commande lorsque vous effectuez plusieurs livraisons pour une seule commande client, un devis de vente ou une commande fournisseur."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ceb568cc223a631f704caf2417f1a3bd56b56288
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="delivery-schedules"></a><span data-ttu-id="d45b7-103">Plans de livraison</span><span class="sxs-lookup"><span data-stu-id="d45b7-103">Delivery schedules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d45b7-104">Les plans de livraison vous permettent de suivre la quantité sur la ligne de commande lorsque vous effectuez plusieurs livraisons pour une seule commande client, un devis de vente ou une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d45b7-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="d45b7-105">Utilisez un plan de livraison lorsque la quantité totale d'une ligne de commande ou de devis doit être livrée dans le cadre de plusieurs expéditions.</span><span class="sxs-lookup"><span data-stu-id="d45b7-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="d45b7-106">Les expéditions individuelles sont représentées par des lignes de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="d45b7-107">Deux lignes de livraison ou plus constituent un calendrier de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="d45b7-108">Les lignes de livraison peuvent avoir des dates de livraison, des quantités, des modes de livraison et des dimensions de stockage différents (telles qu'un site ou un entrepôt).</span><span class="sxs-lookup"><span data-stu-id="d45b7-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="d45b7-109">**Exemple d'un plan de livraison**</span><span class="sxs-lookup"><span data-stu-id="d45b7-109">**Example of a delivery schedule**</span></span>

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="d45b7-110">Commande totale (ligne de commande d'origine)</span><span class="sxs-lookup"><span data-stu-id="d45b7-110">Total order (original order line)</span></span> | <span data-ttu-id="d45b7-111">600 chaises</span><span class="sxs-lookup"><span data-stu-id="d45b7-111">600 chairs</span></span>                               |
| <span data-ttu-id="d45b7-112">Calendrier de livraison demandé</span><span class="sxs-lookup"><span data-stu-id="d45b7-112">Requested delivery schedule</span></span>       | <span data-ttu-id="d45b7-113">100 chaises par mois</span><span class="sxs-lookup"><span data-stu-id="d45b7-113">100 chairs per month</span></span>                     |
| <span data-ttu-id="d45b7-114">Délai de livraison demandé</span><span class="sxs-lookup"><span data-stu-id="d45b7-114">Requested time frame for delivery</span></span> | <span data-ttu-id="d45b7-115">6 mois, le premier jour de chaque mois</span><span class="sxs-lookup"><span data-stu-id="d45b7-115">6 months, on the first day of each month</span></span> |

<span data-ttu-id="d45b7-116">Dans ce scénario, le client demande une livraison de 600 chaises en lots de 100 chaises sur une période de six mois.</span><span class="sxs-lookup"><span data-stu-id="d45b7-116">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="d45b7-117">Pour assurer le suivi des exigences de livraison, vous créez un plan de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-117">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="d45b7-118">Dans la page Plan de livraison, vous créez six lignes de livraison distinctes.</span><span class="sxs-lookup"><span data-stu-id="d45b7-118">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="d45b7-119">Chaque ligne de livraison contient 100 chaises et indique la date de livraison de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="d45b7-119">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="d45b7-120">Dans ce cas, chaque ligne est décalée sur le premier du mois pendant six mois consécutifs.</span><span class="sxs-lookup"><span data-stu-id="d45b7-120">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="d45b7-121">Lorsque vous créez un plan de livraison, le type de la ligne de commande d'origine passe automatiquement à **Ligne de commande avec livraisons multiples**.</span><span class="sxs-lookup"><span data-stu-id="d45b7-121">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="d45b7-122">Une ligne de ce type est appelée une ligne commerciale et est marquée par une icône.</span><span class="sxs-lookup"><span data-stu-id="d45b7-122">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="d45b7-123">La ligne de livraison est marquée par une icône différente.</span><span class="sxs-lookup"><span data-stu-id="d45b7-123">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="d45b7-124">Si vous modifiez une quantité sur une ligne de livraison, la ligne commerciale est mise à jour en fonction de la quantité totale du plan de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-124">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="d45b7-125">Si un accord commercial a défini une remise totale pour la commande, le calendrier de livraison garantit que votre commande est éligible pour cette remise, même si la commande est fractionnée en plusieurs livraisons.</span><span class="sxs-lookup"><span data-stu-id="d45b7-125">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="d45b7-126">Les commandes contenant un plan de livraison sont traitées par rapport aux lignes de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-126">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="d45b7-127">Le traitement inclut la validation des bons de livraison, des accusés de réception de marchandises et des factures.</span><span class="sxs-lookup"><span data-stu-id="d45b7-127">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="d45b7-128">Les impressions des commandes et des devis contenant un plan de livraison affichent uniquement les lignes de livraison.</span><span class="sxs-lookup"><span data-stu-id="d45b7-128">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="d45b7-129">Elles n'affichent pas les lignes d'origine (lignes commerciales).</span><span class="sxs-lookup"><span data-stu-id="d45b7-129">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="d45b7-130">**Remarque :** en outre, seules les lignes de livraison sont affichées lorsque vous exécutez les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d45b7-130">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="d45b7-131">Valider</span><span class="sxs-lookup"><span data-stu-id="d45b7-131">Post</span></span>
-   <span data-ttu-id="d45b7-132">Copier des pages</span><span class="sxs-lookup"><span data-stu-id="d45b7-132">Copy pages</span></span>
-   <span data-ttu-id="d45b7-133">Parcourir les pages de listes et les états</span><span class="sxs-lookup"><span data-stu-id="d45b7-133">Browse list pages and reports</span></span>

<span data-ttu-id="d45b7-134">Lorsque vous confirmez des devis de vente, les commandes client générées affichent l'ensemble du plan de livraison, même les lignes de commande contenant plusieurs livraisons.</span><span class="sxs-lookup"><span data-stu-id="d45b7-134">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="d45b7-135">En outre, l'ensemble du plan de livraison s'affiche sur toutes les pages principales (commandes client, devis de vente et commandes fournisseur).</span><span class="sxs-lookup"><span data-stu-id="d45b7-135">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>




