---
title: Demandes d'articles dans une commande de service
description: Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e31f58cf8782c715b97bdae0e89f684b15a76d2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215077"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="1c6be-103">Demandes d'articles dans une commande de service</span><span class="sxs-lookup"><span data-stu-id="1c6be-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1c6be-104">Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients.</span><span class="sxs-lookup"><span data-stu-id="1c6be-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="1c6be-105">Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.</span><span class="sxs-lookup"><span data-stu-id="1c6be-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="1c6be-106">Une demande d'article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l'article.</span><span class="sxs-lookup"><span data-stu-id="1c6be-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="1c6be-107">En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="1c6be-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="1c6be-108">Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet.</span><span class="sxs-lookup"><span data-stu-id="1c6be-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="1c6be-109">Pour créer une demande d'article sur une commande de service, cette dernière doit être associée à un projet.</span><span class="sxs-lookup"><span data-stu-id="1c6be-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="1c6be-110">Dès qu'une demande d'article est créée pour une commande de service, elle peut être affichée à partir de **Projet** dans la commande de service individuelle ou via l'écran **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="1c6be-111">Affichage d'une demande d'article à partir d'une commande de service</span><span class="sxs-lookup"><span data-stu-id="1c6be-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="1c6be-112">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="1c6be-113">Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="1c6be-114">Cliquez sur l'onglet **Projet**, puis consultez le champ **Commande de service** pour voir les commandes de service pour la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="1c6be-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="1c6be-115">Suppression des commandes de service avec les demandes d'articles</span><span class="sxs-lookup"><span data-stu-id="1c6be-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="1c6be-116">Si une demande d'articles est créée sur une commande de service, vous ne pouvez pas supprimer la commande de service.</span><span class="sxs-lookup"><span data-stu-id="1c6be-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="1c6be-117">Pour pouvoir supprimer la commande de service, vous devez supprimer la demande d'articles.</span><span class="sxs-lookup"><span data-stu-id="1c6be-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="1c6be-118">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="1c6be-119">Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="1c6be-120">Cet écran affiche la liste des demandes d'articles qui sont créées sur la commande de service.</span><span class="sxs-lookup"><span data-stu-id="1c6be-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="1c6be-121">Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="1c6be-122">- ou -</span><span class="sxs-lookup"><span data-stu-id="1c6be-122">–or–</span></span>

1.  <span data-ttu-id="1c6be-123">Cliquez sur **Gestion et comptabilité des projets** \> **Commun** \> **Projets** \> **Tous les projets**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="1c6be-124">Ouvrez le projet contenant la commande de service dans laquelle une demande d'articles est créée.</span><span class="sxs-lookup"><span data-stu-id="1c6be-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="1c6be-125">Dans l'écran **Projet**, dans le volet droit, cliquez sur **Demandes d'articles**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="1c6be-126">L'écran **Demandes d'articles** s'ouvre et affiche la liste des demandes d'article qui sont associées au projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1c6be-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="1c6be-127">Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1c6be-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c6be-128">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1c6be-128">See also</span></span>

<span data-ttu-id="1c6be-129">[Demandes d'articles (écran)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="1c6be-129">[Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span></span>

