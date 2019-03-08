---
title: Gérer les commandes en attente
description: Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad19ff166c15748b7bbb4b82ef71dbf3e1e8ebd2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "323960"
---
# <a name="manage-order-holds"></a><span data-ttu-id="cc143-103">Gérer les commandes en attente</span><span class="sxs-lookup"><span data-stu-id="cc143-103">Manage order holds</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc143-104">Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande.</span><span class="sxs-lookup"><span data-stu-id="cc143-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="cc143-105">Une commande peut être mise en attente pour des raisons diverses.</span><span class="sxs-lookup"><span data-stu-id="cc143-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="cc143-106">Par exemple, vous pouvez mettre une commande en attente jusqu'à ce qu'une adresse du client ou un mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client.</span><span class="sxs-lookup"><span data-stu-id="cc143-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="cc143-107">Tant que la commande est en attente, elle ne peut pas être traitée par l'entrepôt pour l'expédition.</span><span class="sxs-lookup"><span data-stu-id="cc143-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="cc143-108">Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.</span><span class="sxs-lookup"><span data-stu-id="cc143-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="cc143-109">Paramétrer des blocages de commande</span><span class="sxs-lookup"><span data-stu-id="cc143-109">Set up order holds</span></span>
1. <span data-ttu-id="cc143-110">Accédez à Ventes et marketing > Paramétrage > Commandes client > Codes de blocage de commande.</span><span class="sxs-lookup"><span data-stu-id="cc143-110">Go to Sales and marketing > Setup > Sales orders > Order hold codes.</span></span>
2. <span data-ttu-id="cc143-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cc143-111">Click New.</span></span>
3. <span data-ttu-id="cc143-112">Dans le champ Code de blocage, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cc143-112">In the Hold code field, type a value.</span></span>
    * <span data-ttu-id="cc143-113">Par exemple, tapez Rappeler.</span><span class="sxs-lookup"><span data-stu-id="cc143-113">For example, type Call back.</span></span>  
4. <span data-ttu-id="cc143-114">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="cc143-114">In the Description field, type a value.</span></span>
    * <span data-ttu-id="cc143-115">Par exemple, Commande bloquée dans l'attente du rappel du client.</span><span class="sxs-lookup"><span data-stu-id="cc143-115">For example, Order held waiting for customer callback.</span></span>  
    * <span data-ttu-id="cc143-116">Le cas échéant, activez la case à cocher Supprimer des réservations pour supprimer toute réservation physique de la commande lorsque ce code de blocage est ajouté.</span><span class="sxs-lookup"><span data-stu-id="cc143-116">Optionally, select the Remove reservations check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="cc143-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cc143-117">Click Save.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="cc143-118">Mettre une commande en attente</span><span class="sxs-lookup"><span data-stu-id="cc143-118">Place order on hold</span></span>
1. <span data-ttu-id="cc143-119">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="cc143-119">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="cc143-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cc143-120">Click New.</span></span>
3. <span data-ttu-id="cc143-121">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="cc143-121">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="cc143-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="cc143-122">Click OK.</span></span>
5. <span data-ttu-id="cc143-123">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="cc143-123">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="cc143-124">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="cc143-124">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="cc143-125">Cliquez sur Commandes client dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cc143-125">On the Action Pane, click Sales order.</span></span>
8. <span data-ttu-id="cc143-126">Cliquez sur Blocage de commandes.</span><span class="sxs-lookup"><span data-stu-id="cc143-126">Click Order holds.</span></span>
9. <span data-ttu-id="cc143-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="cc143-127">Click New.</span></span>
10. <span data-ttu-id="cc143-128">Dans le champ Code de blocage, sélectionnez le code créé à la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="cc143-128">In the Hold code field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="cc143-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="cc143-129">Click Save.</span></span>
12. <span data-ttu-id="cc143-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="cc143-130">Close the page.</span></span>
13. <span data-ttu-id="cc143-131">Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="cc143-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
14. <span data-ttu-id="cc143-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc143-132">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cc143-133">Les champs « Ne pas traiter » et « Bloquer » des commandes actuellement en attente sont activés.</span><span class="sxs-lookup"><span data-stu-id="cc143-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>    
15. <span data-ttu-id="cc143-134">Cliquez sur Prélever et emballer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="cc143-134">On the Action Pane, click Pick and pack.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="cc143-135">Gérer les commandes en attente</span><span class="sxs-lookup"><span data-stu-id="cc143-135">Manage order holds</span></span>
1. <span data-ttu-id="cc143-136">Accédez à Ventes et marketing > Commandes client > Commandes en cours > Blocage de commandes.</span><span class="sxs-lookup"><span data-stu-id="cc143-136">Go to Sales and marketing > Sales orders > Open orders > Order holds.</span></span>
    * <span data-ttu-id="cc143-137">La page de blocage des commandes se présente comme une console où vous pouvez obtenir une vue d'ensemble de tous les blocages actuels et traités, et les gèrer avec les commandes client associées.</span><span class="sxs-lookup"><span data-stu-id="cc143-137">Order holds page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>      
2. <span data-ttu-id="cc143-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc143-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="cc143-139">Dans le volet Action, cliquez sur Extraire le blocage.</span><span class="sxs-lookup"><span data-stu-id="cc143-139">On the Action Pane, click Hold checkout.</span></span>
4. <span data-ttu-id="cc143-140">Cliquez sur Extraction.</span><span class="sxs-lookup"><span data-stu-id="cc143-140">Click Check out.</span></span>
5. <span data-ttu-id="cc143-141">Dans la liste, désactiver la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cc143-141">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="cc143-142">Le champ Extrait par contient désormais votre ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cc143-142">The Checkout out to field now shows your user ID.</span></span>   
6. <span data-ttu-id="cc143-143">Cliquez sur Supprimer l'extraction.</span><span class="sxs-lookup"><span data-stu-id="cc143-143">Click Clear checkout.</span></span>
7. <span data-ttu-id="cc143-144">Dans le volet Action, cliquez sur Supprimer le blocage.</span><span class="sxs-lookup"><span data-stu-id="cc143-144">On the Action Pane, click Clear hold.</span></span>
    * <span data-ttu-id="cc143-145">Lorsque vous êtes prêt à lever le blocage et à autoriser la commande à passer à l'étape de traitement suivante, vous devez supprimer le blocage.</span><span class="sxs-lookup"><span data-stu-id="cc143-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="cc143-146">Si la commande n'a pas besoin d'être modifiée, vous pouvez exécuter l'action Supprimer les blocages.</span><span class="sxs-lookup"><span data-stu-id="cc143-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="cc143-147">Toutefois, vous pouvez utiliser l'action Supprimer et modifier, si au moment de lever le blocage, la commande doit être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="cc143-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    * <span data-ttu-id="cc143-148">L'action Supprimer et soumettre n'est applicable que si vous utilisez la fonctionnalité Centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="cc143-148">The Clear and submit action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="cc143-149">Cliquez sur Supprimer le blocage.</span><span class="sxs-lookup"><span data-stu-id="cc143-149">Click Clear holds.</span></span>
    * <span data-ttu-id="cc143-150">Le blocage a désormais été effacé de la commande et supprimé de la liste Blocages actifs.</span><span class="sxs-lookup"><span data-stu-id="cc143-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="cc143-151">Pour afficher tous les blocages ou leur sous-ensemble défini selon un statut spécifique, modifiez la valeur du champ Afficher.</span><span class="sxs-lookup"><span data-stu-id="cc143-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     

