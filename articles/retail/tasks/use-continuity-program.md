--- 
title: "Vente de programme périodique et de traitement des commandes client associées"
description: "Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 5fe1823c9b684bbc5ac5bd0871cc5c0a0e6ce678
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="selling-continuity-programs-and-processing-related-sales-orders"></a><span data-ttu-id="e1b16-103">Vente de programme périodique et de traitement des commandes client associées</span><span class="sxs-lookup"><span data-stu-id="e1b16-103">Selling continuity programs and processing related sales orders</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e1b16-104">Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées.</span><span class="sxs-lookup"><span data-stu-id="e1b16-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="e1b16-105">Pour exécuter cette procédure, l'utilisateur doit être configuré comme utilisateur du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="e1b16-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="e1b16-106">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e1b16-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="e1b16-107">Accédez à Commerce et vente au détail > Clients > Service client.</span><span class="sxs-lookup"><span data-stu-id="e1b16-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="e1b16-108">Dans le champ SearchText, tapez « Karen », puis appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="e1b16-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="e1b16-109">La boîte de dialogue de recherche avancée doit s'afficher.</span><span class="sxs-lookup"><span data-stu-id="e1b16-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="e1b16-110">Si elle ne s'affiche pas, cliquez sur Rechercher à droite de ce champ.</span><span class="sxs-lookup"><span data-stu-id="e1b16-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="e1b16-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e1b16-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e1b16-112">Il ne doit y avoir qu'une ligne portant la mention Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="e1b16-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="e1b16-113">Sélectionnez la ligne en cliquant sur la colonne à l'extrême gauche de la grille.</span><span class="sxs-lookup"><span data-stu-id="e1b16-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="e1b16-114">Cliquez sur Sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e1b16-114">Click Select.</span></span>
5. <span data-ttu-id="e1b16-115">Cliquez sur Nouvelle commande client.</span><span class="sxs-lookup"><span data-stu-id="e1b16-115">Click New sales order.</span></span>
    * <span data-ttu-id="e1b16-116">Il est conseillé de noter le numéro de la commande client.</span><span class="sxs-lookup"><span data-stu-id="e1b16-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="e1b16-117">Vous en aurez besoin ultérieurement dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e1b16-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="e1b16-118">Dans le champ Numéro d'article, tapez « 88000 », puis appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="e1b16-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="e1b16-119">Il s'agit d'un article périodique dans les données de démonstration USRT.</span><span class="sxs-lookup"><span data-stu-id="e1b16-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="e1b16-120">Cliquez sur Terminé.</span><span class="sxs-lookup"><span data-stu-id="e1b16-120">Click Complete.</span></span>
8. <span data-ttu-id="e1b16-121">Dans le champ Mode de paiement, entrez « Visa ».</span><span class="sxs-lookup"><span data-stu-id="e1b16-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="e1b16-122">Cliquez sur Ajouter une carte de crédit.</span><span class="sxs-lookup"><span data-stu-id="e1b16-122">Click Add credit card.</span></span>
    * <span data-ttu-id="e1b16-123">Entrez les informations de carte de crédit requises dans cette page.</span><span class="sxs-lookup"><span data-stu-id="e1b16-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="e1b16-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1b16-124">Click OK.</span></span>
11. <span data-ttu-id="e1b16-125">Développez la section Paiement.</span><span class="sxs-lookup"><span data-stu-id="e1b16-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="e1b16-126">Pour envoyer une commande du centre d'appels, les paiements doivent être entrés pour la commande.</span><span class="sxs-lookup"><span data-stu-id="e1b16-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="e1b16-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1b16-127">Click OK.</span></span>
13. <span data-ttu-id="e1b16-128">Cliquez sur Soumettre.</span><span class="sxs-lookup"><span data-stu-id="e1b16-128">Click Submit.</span></span>
    * <span data-ttu-id="e1b16-129">Vous avez terminé de créer une commande périodique.</span><span class="sxs-lookup"><span data-stu-id="e1b16-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="e1b16-130">Vous exécuterez ensuite deux processus de traitement par lots qui sont utilisés pour traiter les commandes périodiques.</span><span class="sxs-lookup"><span data-stu-id="e1b16-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="e1b16-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1b16-131">Close the page.</span></span>
15. <span data-ttu-id="e1b16-132">Accédez à Commerce et vente au détail > Périodicité > Traiter les paiements périodiques.</span><span class="sxs-lookup"><span data-stu-id="e1b16-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="e1b16-133">Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="e1b16-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="e1b16-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1b16-134">Click OK.</span></span>
18. <span data-ttu-id="e1b16-135">Accédez à Commerce et vente au détail > Périodicité > Créer des commandes enfant périodiques.</span><span class="sxs-lookup"><span data-stu-id="e1b16-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="e1b16-136">Ce processus créera des commandes client en fonction des paramètres de vos programmes périodiques.</span><span class="sxs-lookup"><span data-stu-id="e1b16-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="e1b16-137">Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.</span><span class="sxs-lookup"><span data-stu-id="e1b16-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="e1b16-138">L'article « 88000 »est un article périodique dans les données de démonstration USRT.</span><span class="sxs-lookup"><span data-stu-id="e1b16-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="e1b16-139">Dans le champ Commande client, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1b16-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="e1b16-140">Entrez le numéro de la commande client que vous avez noté précédemment dans la procédure.</span><span class="sxs-lookup"><span data-stu-id="e1b16-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="e1b16-141">La durée de traitement sera maintenue à une valeur minimale pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e1b16-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="e1b16-142">Le champ Commande client est facultatif ; vous pouvez traiter toutes les commandes pour n'importe quel programme.</span><span class="sxs-lookup"><span data-stu-id="e1b16-142">The Sales order field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="e1b16-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1b16-143">Click OK.</span></span>


