--- 
title: " Définir les programmes périodiques"
description: "Cette rubrique vous guide dans le paramétrage d'un programme périodique (également appelé commandes récurrentes)."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4f99b3b71e46aae1e510cc24efe2f99f1a258fa1
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="define-continuity-schedules"></a><span data-ttu-id="3dd11-103"> Définir les programmes périodiques</span><span class="sxs-lookup"><span data-stu-id="3dd11-103">Define continuity schedules</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3dd11-104">Cette rubrique vous guide dans le paramétrage d'un programme périodique (également appelé commandes récurrentes).</span><span class="sxs-lookup"><span data-stu-id="3dd11-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="3dd11-105">Elle utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="3dd11-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="3dd11-106">Créer un programme périodique</span><span class="sxs-lookup"><span data-stu-id="3dd11-106">Create continuity program</span></span>
1. <span data-ttu-id="3dd11-107">Accédez à Commerce et vente au détail > Périodicité > Programmes périodiques.</span><span class="sxs-lookup"><span data-stu-id="3dd11-107">Go to Retail and commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="3dd11-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3dd11-108">Click New.</span></span>
3. <span data-ttu-id="3dd11-109">Dans le champ ID programme, entrez l'ID du programme périodique.</span><span class="sxs-lookup"><span data-stu-id="3dd11-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="3dd11-110">Dans le champ Début de commande, sélectionnez « Premier événement ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="3dd11-111">Si un client passe une nouvelle commande pour le programme périodique, il existe deux options pour lesquelles le produit est expédié : 1.</span><span class="sxs-lookup"><span data-stu-id="3dd11-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="3dd11-112">Premier événement : le premier produit du programme périodique est expédié.</span><span class="sxs-lookup"><span data-stu-id="3dd11-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="3dd11-113">2.</span><span class="sxs-lookup"><span data-stu-id="3dd11-113">2.</span></span> <span data-ttu-id="3dd11-114">Événement actuel : le produit actuel est expédié.</span><span class="sxs-lookup"><span data-stu-id="3dd11-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="3dd11-115">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="3dd11-115">For example.</span></span> <span data-ttu-id="3dd11-116">trois mois dans le programme, le client reçoit le troisième produit du programme.</span><span class="sxs-lookup"><span data-stu-id="3dd11-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="3dd11-117">Sélectionnez » Oui » pour demander la date de début de la commande.</span><span class="sxs-lookup"><span data-stu-id="3dd11-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="3dd11-118">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3dd11-118">Click Add line.</span></span>
7. <span data-ttu-id="3dd11-119">Dans le champ Numéro d'article, tapez le numéro d'article du premier produit (0013).</span><span class="sxs-lookup"><span data-stu-id="3dd11-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="3dd11-120">Tapez « CP ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-120">Type 'CP'.</span></span>
9. <span data-ttu-id="3dd11-121">Entrez la date à laquelle le premier produit sera disponible à la commande.</span><span class="sxs-lookup"><span data-stu-id="3dd11-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="3dd11-122">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3dd11-122">Click Add line.</span></span>
11. <span data-ttu-id="3dd11-123">Dans le champ Numéro d'article, tapez « 0014 ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="3dd11-124">Dans le champ Code intervalle de dates, effacez la valeur pour que le champ soit vide.</span><span class="sxs-lookup"><span data-stu-id="3dd11-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="3dd11-125">Pour cette procédure, désactivez l'intervalle de dates.</span><span class="sxs-lookup"><span data-stu-id="3dd11-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="3dd11-126">Vous définirez la date comme valeur incrémentielle à partir de la date de début du premier article.</span><span class="sxs-lookup"><span data-stu-id="3dd11-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="3dd11-127">Vous entrerez ici l'intervalle d'expédition des produits.</span><span class="sxs-lookup"><span data-stu-id="3dd11-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="3dd11-128">Tapez « 30 ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-128">Type '30'.</span></span>
    * <span data-ttu-id="3dd11-129">Pour un programme mensuel, vous entrerez 30 jours pour l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="3dd11-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="3dd11-130">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="3dd11-130">Click Add line.</span></span>
15. <span data-ttu-id="3dd11-131">Dans le champ Numéro d'article, tapez « 0015 ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="3dd11-132">Tapez « Terminer ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-132">Type 'End'.</span></span>
17. <span data-ttu-id="3dd11-133">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3dd11-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="3dd11-134">Affecter à un article périodique</span><span class="sxs-lookup"><span data-stu-id="3dd11-134">Assign to continuity item</span></span>
1. <span data-ttu-id="3dd11-135">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="3dd11-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="3dd11-136">Sélectionnez l'article « 0016 ».</span><span class="sxs-lookup"><span data-stu-id="3dd11-136">Select item '0016'.</span></span>
    * <span data-ttu-id="3dd11-137">Pour cette procédure, vous sélectionnerez le numéro d'article 0016.</span><span class="sxs-lookup"><span data-stu-id="3dd11-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="3dd11-138">Normalement, vous créerez un produit lancé dont une logique métier périodique supplémentaire est appliquée lorsqu'il est placé sur une commande client dans le centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="3dd11-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="3dd11-139">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3dd11-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3dd11-140">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3dd11-140">Click Edit.</span></span>
5. <span data-ttu-id="3dd11-141">Développez ou réduisez la section Vendre.</span><span class="sxs-lookup"><span data-stu-id="3dd11-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="3dd11-142">Vous entrerez ici le programme périodique que cet article représente.</span><span class="sxs-lookup"><span data-stu-id="3dd11-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="3dd11-143">Tapez l'ID programme que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="3dd11-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="3dd11-144">Lorsque cet article est vendu dans un centre d'appels, une logique métier supplémentaire est appliquée à partir du programme périodique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3dd11-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="3dd11-145">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3dd11-145">Click Save.</span></span>


