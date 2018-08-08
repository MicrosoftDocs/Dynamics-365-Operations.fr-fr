---
title: Demandes d'articles dans une commande de service
description: "Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 3dc7c721af4b25e1586e546392518648110a3fb6
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="service-order-item-requirements"></a><span data-ttu-id="901dd-103">Demandes d'articles dans une commande de service</span><span class="sxs-lookup"><span data-stu-id="901dd-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="901dd-104">Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients.</span><span class="sxs-lookup"><span data-stu-id="901dd-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="901dd-105">Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="901dd-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="901dd-106">Une demande d'article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l'article.</span><span class="sxs-lookup"><span data-stu-id="901dd-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="901dd-107">En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="901dd-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="901dd-108">Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet.</span><span class="sxs-lookup"><span data-stu-id="901dd-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="901dd-109">Pour créer une demande d'article sur une commande de service, cette dernière doit être associée à un projet.</span><span class="sxs-lookup"><span data-stu-id="901dd-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="901dd-110">Dès qu'une demande d'article est créée pour une commande de service, elle peut être affichée à partir de **Projet** dans la commande de service individuelle ou via l'écran **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="901dd-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="901dd-111">Affichage d'une demande d'article à partir d'une commande de service</span><span class="sxs-lookup"><span data-stu-id="901dd-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="901dd-112">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="901dd-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="901dd-113">Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="901dd-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="901dd-114">Cliquez sur l'onglet **Projet**, puis consultez le champ **Commande de service** pour voir les commandes de service pour la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="901dd-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="901dd-115">Suppression des commandes de service avec les demandes d'articles</span><span class="sxs-lookup"><span data-stu-id="901dd-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="901dd-116">Si une demande d'articles est créée sur une commande de service, vous ne pouvez pas supprimer la commande de service.</span><span class="sxs-lookup"><span data-stu-id="901dd-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="901dd-117">Pour pouvoir supprimer la commande de service, vous devez supprimer la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="901dd-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="901dd-118">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="901dd-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="901dd-119">Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="901dd-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="901dd-120">Cet écran affiche la liste des demandes d'articles qui sont créées sur la commande de service.</span><span class="sxs-lookup"><span data-stu-id="901dd-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="901dd-121">Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="901dd-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="901dd-122">- ou -</span><span class="sxs-lookup"><span data-stu-id="901dd-122">–or–</span></span>

1.  <span data-ttu-id="901dd-123">Cliquez sur **Gestion et comptabilité des projets** \> **Commun** \> **Projets** \> **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="901dd-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="901dd-124">Ouvrez le projet contenant la commande de service dans laquelle une demande d'articles est créée.</span><span class="sxs-lookup"><span data-stu-id="901dd-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="901dd-125">Dans l'écran **Projet**, dans le volet droit, cliquez sur **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="901dd-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="901dd-126">L'écran **Demandes d'articles** s'ouvre et affiche la liste des demandes d'article qui sont associées au projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="901dd-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="901dd-127">Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="901dd-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="901dd-128">Voir également :</span><span class="sxs-lookup"><span data-stu-id="901dd-128">See also</span></span>

<span data-ttu-id="901dd-129">[Demandes d'articles (écran)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="901dd-129">[Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))</span></span>


