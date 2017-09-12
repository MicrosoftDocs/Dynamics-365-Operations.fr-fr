--- 
title: "Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles"
description: "Cette procédure montre le mode de réception des articles sur une commande fournisseur à partir d'une demande d'articles."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7c9093439c4c0c4645d96ad97ba56f31026ec334
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="f50cf-103">Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles</span><span class="sxs-lookup"><span data-stu-id="f50cf-103">Receive items on purchase order from item requirement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f50cf-104">Cette procédure montre le mode de réception des articles sur une commande fournisseur à partir d'une demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="f50cf-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="f50cf-105">En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="f50cf-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="f50cf-106">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="f50cf-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="f50cf-107">Accédez à Gestion et comptabilité des projets > Projets > Tous les projets.</span><span class="sxs-lookup"><span data-stu-id="f50cf-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="f50cf-108">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f50cf-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="f50cf-109">Cliquez sur Planifier dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f50cf-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="f50cf-110">Cliquez sur Demandes d'articles.</span><span class="sxs-lookup"><span data-stu-id="f50cf-110">Click Item requirements.</span></span>
5. <span data-ttu-id="f50cf-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="f50cf-111">Click New.</span></span>
6. <span data-ttu-id="f50cf-112">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f50cf-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="f50cf-113">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="f50cf-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="f50cf-114">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="f50cf-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="f50cf-115">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f50cf-115">Click Save.</span></span>
10. <span data-ttu-id="f50cf-116">Dans le volet Actions, cliquez sur Gérer.</span><span class="sxs-lookup"><span data-stu-id="f50cf-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="f50cf-117">Cliquez sur Fonctions.</span><span class="sxs-lookup"><span data-stu-id="f50cf-117">Click Functions.</span></span>
12. <span data-ttu-id="f50cf-118">Cliquez sur Créer une commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f50cf-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="f50cf-119">Activez la case à cocher Inclure.</span><span class="sxs-lookup"><span data-stu-id="f50cf-119">Select the Include check box.</span></span>
14. <span data-ttu-id="f50cf-120">Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f50cf-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="f50cf-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f50cf-121">Click OK.</span></span>
16. <span data-ttu-id="f50cf-122">Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f50cf-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="f50cf-123">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f50cf-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="f50cf-124">Cliquez sur Achats dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f50cf-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="f50cf-125">Cliquez sur Confirmer.</span><span class="sxs-lookup"><span data-stu-id="f50cf-125">Click Confirm.</span></span>
20. <span data-ttu-id="f50cf-126">Dans le volet Actions, cliquez sur Recevoir.</span><span class="sxs-lookup"><span data-stu-id="f50cf-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="f50cf-127">Cliquez sur Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="f50cf-127">Click Product receipt.</span></span>
22. <span data-ttu-id="f50cf-128">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f50cf-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="f50cf-129">Tapez une valeur dans le champ Accusé de réception de marchandises.</span><span class="sxs-lookup"><span data-stu-id="f50cf-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="f50cf-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f50cf-130">Click OK.</span></span>


