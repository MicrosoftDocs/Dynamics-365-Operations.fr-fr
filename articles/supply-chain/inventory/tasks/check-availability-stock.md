---
title: Vérifier la disponibilité du stock
description: Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique.
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6ced839f93103a62bcfa8ea14ca463f0f1e174e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145845"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="16da4-103">Vérifier la disponibilité du stock</span><span class="sxs-lookup"><span data-stu-id="16da4-103">Check the availability of stock</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="16da4-104">Cette procédure vous indique comment contrôler le stock physique disponible pour un article spécifique.</span><span class="sxs-lookup"><span data-stu-id="16da4-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="16da4-105">Elle vous indique également comment obtenir des informations d'approvisionnement associées à un article.</span><span class="sxs-lookup"><span data-stu-id="16da4-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="16da4-106">Le stock physique disponible représente le stock disponible (c'est-à-dire tout ce qui est acheté, reçu et enregistré).</span><span class="sxs-lookup"><span data-stu-id="16da4-106">Physical on-hand inventory is the on-hand inventory that's available – that is, it's purchased, received and registered.</span></span> <span data-ttu-id="16da4-107">Le stock disponible inclut le stock disponible, mais également le stock commandé et prévu, mais pas encore reçu ou enregistré.</span><span class="sxs-lookup"><span data-stu-id="16da4-107">On-hand inventory includes the available on-hand inventory, but also the inventory that's been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="16da4-108">Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="16da4-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="16da4-109">Si vous utilisez USMF, vous pouvez utiliser les valeurs des exemples affichées.</span><span class="sxs-lookup"><span data-stu-id="16da4-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="16da4-110">Ces tâches sont généralement effectuées par un magasinier.</span><span class="sxs-lookup"><span data-stu-id="16da4-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="16da4-111">Vérifier un article dans le stock disponible</span><span class="sxs-lookup"><span data-stu-id="16da4-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="16da4-112">Accédez à **Volet de navigation > Modules > Gestion des stocks > Recherches et états > Stock disponible**.</span><span class="sxs-lookup"><span data-stu-id="16da4-112">Go to **Navigation pane > Modules > Inventory management > Inquiries and reports > On-hand inventory**.</span></span>
2. <span data-ttu-id="16da4-113">Sélectionnez la ligne **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="16da4-113">Select the **Item number** row.</span></span> <span data-ttu-id="16da4-114">Pour rechercher le stock disponible par numéro d'article, sélectionnez la ligne où Tableau est défini sur **Stock disponible** et Champ est défini sur Numéro d'**article**.</span><span class="sxs-lookup"><span data-stu-id="16da4-114">To query the on-hand inventory by item number, select the row where the Table is set to **On-hand inventory** and Field is set to **Item** number.</span></span>
3. <span data-ttu-id="16da4-115">Dans le champ **Critères**, sélectionnez l'article à rechercher.</span><span class="sxs-lookup"><span data-stu-id="16da4-115">In the **Criteria** field, select the item you want to query.</span></span> <span data-ttu-id="16da4-116">Si vous utilisez la société fictive USMF, vous pouvez sélectionner M9201.</span><span class="sxs-lookup"><span data-stu-id="16da4-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="16da4-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16da4-117">Click **OK**.</span></span>
5. <span data-ttu-id="16da4-118">Dans le volet **Actions**, cliquez sur **Dimensions**.</span><span class="sxs-lookup"><span data-stu-id="16da4-118">On the **Action pane**, click **Dimensions**.</span></span> <span data-ttu-id="16da4-119">L'onglet **Dimensions** vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible.</span><span class="sxs-lookup"><span data-stu-id="16da4-119">The **Dimensions** tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="16da4-120">Si vous avez besoin de données liées à la réservation, vous devez afficher toutes les dimensions de stock pour les articles qui utilisent des processus avancés de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="16da4-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>
6. <span data-ttu-id="16da4-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16da4-121">Click **OK**.</span></span>
7. <span data-ttu-id="16da4-122">Dans le volet **Actions**, cliquez sur **Informations associées**.</span><span class="sxs-lookup"><span data-stu-id="16da4-122">On the **Action Pane**, click **Related information**.</span></span> <span data-ttu-id="16da4-123">Si vous ne voyez pas cette option, vous devez cliquer sur le bouton représentant des points de suspension (…) pour afficher les options du volet d'action supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="16da4-123">If you don't see this option, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>
8. <span data-ttu-id="16da4-124">Cliquez sur **Vue d'ensemble de l'approvisionnement**.</span><span class="sxs-lookup"><span data-stu-id="16da4-124">Click **Supply overview**.</span></span> <span data-ttu-id="16da4-125">L'onglet **Vue d'ensemble de l'approvisionnement** fournit des informations d'approvisionnement pour un article spécifique, telles que la quantité disponible, le délai, et les informations fournisseur.</span><span class="sxs-lookup"><span data-stu-id="16da4-125">The **Supply overview** tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="16da4-126">Développez la section **Disponible**.</span><span class="sxs-lookup"><span data-stu-id="16da4-126">Expand the **On-hand** section.</span></span>
10. <span data-ttu-id="16da4-127">Développez la section **Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="16da4-127">Expand the **Vendors** section.</span></span>
11. <span data-ttu-id="16da4-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-128">Close the page.</span></span>
12. <span data-ttu-id="16da4-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="16da4-130">Vérifier le stock physique disponible</span><span class="sxs-lookup"><span data-stu-id="16da4-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="16da4-131">Accédez à **Volet de navigation > Modules > Gestion de l'entrepôt > Recherches et états > Stock physique**.</span><span class="sxs-lookup"><span data-stu-id="16da4-131">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > Physical on-hand inventory**.</span></span>
2. <span data-ttu-id="16da4-132">Dans le champ **Numéro d'article**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="16da4-132">In the **Item number** field, type a value.</span></span> <span data-ttu-id="16da4-133">Vous pouvez utiliser les champs Site et Entrepôt pour filtrer la liste des articles.</span><span class="sxs-lookup"><span data-stu-id="16da4-133">You can use the Site and Warehouse fields to filter the list of items.</span></span> 
3. <span data-ttu-id="16da4-134">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-134">Refresh the page.</span></span>
4. <span data-ttu-id="16da4-135">Dans le volet **Actions**, cliquez sur **Affichage des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="16da4-135">On the **Action pane**, click **Display Dimensions**.</span></span> <span data-ttu-id="16da4-136">L'onglet Affichage des dimensions vous permet de sélectionner la quantité de détails à afficher à propos du stock disponible.</span><span class="sxs-lookup"><span data-stu-id="16da4-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>
5. <span data-ttu-id="16da4-137">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16da4-137">Click **OK**.</span></span>
6. <span data-ttu-id="16da4-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="16da4-139">Vérifier le stock disponible par emplacement</span><span class="sxs-lookup"><span data-stu-id="16da4-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="16da4-140">Accédez à **Volet de navigation > Modules > Gestion de l'entrepôt > Recherches et états > Disponible par emplacement**.</span><span class="sxs-lookup"><span data-stu-id="16da4-140">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > On hand by location**.</span></span>
2. <span data-ttu-id="16da4-141">Dans le champ **Entrepôts**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="16da4-141">In the **Warehouse** field, type a value.</span></span> <span data-ttu-id="16da4-142">Si vous utilisez la société fictive USMF, vous pouvez utiliser 51.</span><span class="sxs-lookup"><span data-stu-id="16da4-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="16da4-143">Actualisez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-143">Refresh the page.</span></span>
4. <span data-ttu-id="16da4-144">Cliquez sur **Affichage des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="16da4-144">Click **Display Dimensions**.</span></span>
5. <span data-ttu-id="16da4-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16da4-145">Click **OK**.</span></span>
6. <span data-ttu-id="16da4-146">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="16da4-146">Close the page.</span></span>

