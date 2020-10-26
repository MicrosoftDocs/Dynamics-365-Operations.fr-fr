---
title: Gérer les commandes en attente
description: Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caf6651813f0111b873db1769140d973f1a2e3b
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981967"
---
# <a name="manage-order-holds"></a><span data-ttu-id="c714e-103">Gérer les commandes en attente</span><span class="sxs-lookup"><span data-stu-id="c714e-103">Manage order holds</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c714e-104">Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande.</span><span class="sxs-lookup"><span data-stu-id="c714e-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="c714e-105">Une commande peut être mise en attente pour des raisons diverses.</span><span class="sxs-lookup"><span data-stu-id="c714e-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="c714e-106">Par exemple, vous pouvez mettre une commande en attente jusqu'à ce qu'une adresse du client ou un mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client.</span><span class="sxs-lookup"><span data-stu-id="c714e-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer's credit limit.</span></span> <span data-ttu-id="c714e-107">Tant que la commande est en attente, elle ne peut pas être traitée par l'entrepôt pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="c714e-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="c714e-108">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="c714e-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="c714e-109">Paramétrer des blocages de commande</span><span class="sxs-lookup"><span data-stu-id="c714e-109">Set up order holds</span></span>
1. <span data-ttu-id="c714e-110">Accédez à **volet Navigation > Modules > Ventes et marketing > Configuration > Commandes client > Codes de blocage de commande**.</span><span class="sxs-lookup"><span data-stu-id="c714e-110">Go to **Navigation pane > Modules > Sales and marketing > Setup > Sales orders > Order hold codes**.</span></span>
2. <span data-ttu-id="c714e-111">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c714e-111">Click **New**.</span></span>
3. <span data-ttu-id="c714e-112">Dans le champ **Code de blocage**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="c714e-112">In the **Hold code** field, type a value.</span></span> <span data-ttu-id="c714e-113">Par exemple, tapez Rappeler.</span><span class="sxs-lookup"><span data-stu-id="c714e-113">For example, type 'Call back'.</span></span>  
4. <span data-ttu-id="c714e-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="c714e-114">In the **Description** field, type a value.</span></span>
    - <span data-ttu-id="c714e-115">Par exemple, Commande bloquée dans l'attente du rappel du client.</span><span class="sxs-lookup"><span data-stu-id="c714e-115">For example, Order held waiting for customer callback.</span></span>  
    - <span data-ttu-id="c714e-116">Le cas échéant, activez la case à cocher **Supprimer des réservations** pour supprimer toute réservation physique de la commande lorsque ce code de blocage est ajouté.</span><span class="sxs-lookup"><span data-stu-id="c714e-116">Optionally, select the **Remove reservations** check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="c714e-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c714e-117">Click **Save**.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="c714e-118">Mettre une commande en attente</span><span class="sxs-lookup"><span data-stu-id="c714e-118">Place order on hold</span></span>
1. <span data-ttu-id="c714e-119">Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="c714e-119">Go to **Navigation pane > Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="c714e-120">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c714e-120">Click **New**.</span></span>
3. <span data-ttu-id="c714e-121">Entrez ou sélectionnez une valeur dans le champ **Compte client**.</span><span class="sxs-lookup"><span data-stu-id="c714e-121">In the **Customer account** field, enter or select a value.</span></span>
4. <span data-ttu-id="c714e-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c714e-122">Click **OK**.</span></span>
5. <span data-ttu-id="c714e-123">Entrez ou sélectionnez une valeur dans le champ **Numéro d'article**.</span><span class="sxs-lookup"><span data-stu-id="c714e-123">In the **Item number** field, enter or select a value.</span></span>
6. <span data-ttu-id="c714e-124">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="c714e-124">In the **Quantity** field, enter a number.</span></span>
7. <span data-ttu-id="c714e-125">Cliquez sur **Commande client** dans le **volet Actions**.</span><span class="sxs-lookup"><span data-stu-id="c714e-125">On the **Action Pane**, click **Sales order**.</span></span>
8. <span data-ttu-id="c714e-126">Cliquez sur **Blocage de commandes**.</span><span class="sxs-lookup"><span data-stu-id="c714e-126">Click **Order holds**.</span></span>
9. <span data-ttu-id="c714e-127">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c714e-127">Click **New**.</span></span>
10. <span data-ttu-id="c714e-128">Dans le champ **Code de blocage**, sélectionnez le code créé à la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="c714e-128">In the **Hold code** field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="c714e-129">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c714e-129">Click **Save**.</span></span>
12. <span data-ttu-id="c714e-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c714e-130">Close the page.</span></span>
13. <span data-ttu-id="c714e-131">Accédez à **Ventes et marketing > Commandes client > Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="c714e-131">Go to **Sales and marketing > Sales orders > All sales orders**.</span></span>
14. <span data-ttu-id="c714e-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c714e-132">In the list, mark the selected row.</span></span> <span data-ttu-id="c714e-133">Les champs « Ne pas traiter » et « Bloquer » des commandes actuellement en attente sont activés.</span><span class="sxs-lookup"><span data-stu-id="c714e-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>
15. <span data-ttu-id="c714e-134">Dans le volet Actions, cliquez sur **Prélever et emballer**.</span><span class="sxs-lookup"><span data-stu-id="c714e-134">On the Action Pane, click **Pick and pack**.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="c714e-135">Gérer les commandes en attente</span><span class="sxs-lookup"><span data-stu-id="c714e-135">Manage order holds</span></span>
1. <span data-ttu-id="c714e-136">Accédez à **Ventes et marketing > Commandes client > Commandes en cours > Blocage de commandes**.</span><span class="sxs-lookup"><span data-stu-id="c714e-136">Go to **Sales and marketing > Sales orders > Open orders > Order holds**.</span></span> <span data-ttu-id="c714e-137">La page **Blocage de commandes** se présente comme une console où vous pouvez obtenir une vue d'ensemble de tous les blocages actuels et traités, et les gérer avec les commandes client associées.</span><span class="sxs-lookup"><span data-stu-id="c714e-137">**Order holds** page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>     
2. <span data-ttu-id="c714e-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c714e-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="c714e-139">Dans le **volet Actions**, cliquez sur **Extraire le blocage**.</span><span class="sxs-lookup"><span data-stu-id="c714e-139">On the **Action Pane**, click **Hold checkout**.</span></span>
4. <span data-ttu-id="c714e-140">Cliquez sur **Extraction**.</span><span class="sxs-lookup"><span data-stu-id="c714e-140">Click **Check out**.</span></span>
5. <span data-ttu-id="c714e-141">Dans la liste, désactiver la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c714e-141">In the list, unmark the selected row.</span></span> <span data-ttu-id="c714e-142">Le champ **Extrait par** contient désormais votre ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c714e-142">The **Checkout out to** field now shows your user ID.</span></span>   
6. <span data-ttu-id="c714e-143">Cliquez sur **Supprimer l'extraction**.</span><span class="sxs-lookup"><span data-stu-id="c714e-143">Click **Clear checkout**.</span></span>
7. <span data-ttu-id="c714e-144">Dans le **volet Actions**, cliquez sur **Supprimer le blocage**.</span><span class="sxs-lookup"><span data-stu-id="c714e-144">On the **Action Pane**, click **Clear hold**.</span></span>
    - <span data-ttu-id="c714e-145">Lorsque vous êtes prêt à lever le blocage et à autoriser la commande à passer à l'étape de traitement suivante, vous devez supprimer le blocage.</span><span class="sxs-lookup"><span data-stu-id="c714e-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="c714e-146">Si la commande n'a pas besoin d'être modifiée, vous pouvez exécuter l'action Supprimer les blocages.</span><span class="sxs-lookup"><span data-stu-id="c714e-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="c714e-147">Toutefois, vous pouvez utiliser l'action Supprimer et modifier, si au moment de lever le blocage, la commande doit être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="c714e-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    - <span data-ttu-id="c714e-148">L'action **Supprimer et soumettre** n'est applicable que si vous utilisez la fonctionnalité Centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="c714e-148">The **Clear and submit** action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="c714e-149">Cliquez sur **Supprimer le blocage**.</span><span class="sxs-lookup"><span data-stu-id="c714e-149">Click **Clear holds**.</span></span> <span data-ttu-id="c714e-150">Le blocage a désormais été effacé de la commande et supprimé de la liste Blocages actifs.</span><span class="sxs-lookup"><span data-stu-id="c714e-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="c714e-151">Pour afficher tous les blocages ou leur sous-ensemble défini selon un statut spécifique, modifiez la valeur du champ Afficher.</span><span class="sxs-lookup"><span data-stu-id="c714e-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     

