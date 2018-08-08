--- 
title: "Planifier les chargements et les expéditions à l'aide de l'atelier Planification des chargements"
description: "Cette procédure indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client."
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="65c79-103">Planifier les chargements et les expéditions à l'aide de l'atelier Planification des chargements</span><span class="sxs-lookup"><span data-stu-id="65c79-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65c79-104">Cette procédure indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client.</span><span class="sxs-lookup"><span data-stu-id="65c79-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="65c79-105">Il est indispensable de créer la commande client en premier.</span><span class="sxs-lookup"><span data-stu-id="65c79-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="65c79-106">Cette procédure fait partie du travail quotidien pour le coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="65c79-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="65c79-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="65c79-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="65c79-108">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="65c79-108">Create a sales order</span></span>
1. <span data-ttu-id="65c79-109">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="65c79-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="65c79-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="65c79-110">Click New.</span></span>
3. <span data-ttu-id="65c79-111">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="65c79-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="65c79-112">Sélectionnez US-004.</span><span class="sxs-lookup"><span data-stu-id="65c79-112">Select account US-004.</span></span>
5. <span data-ttu-id="65c79-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="65c79-113">Click OK.</span></span>
6. <span data-ttu-id="65c79-114">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="65c79-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="65c79-115">Sélectionner l'article A0001.</span><span class="sxs-lookup"><span data-stu-id="65c79-115">Select item A0001.</span></span>
    * <span data-ttu-id="65c79-116">A0001 est activé pour la gestion du transport.</span><span class="sxs-lookup"><span data-stu-id="65c79-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="65c79-117">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="65c79-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="65c79-118">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="65c79-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="65c79-119">Dans le champ Entrepôt, tapez « 24 ».</span><span class="sxs-lookup"><span data-stu-id="65c79-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="65c79-120">Dans cet exemple sélectionnez l'entrepôt 24.</span><span class="sxs-lookup"><span data-stu-id="65c79-120">In this example select warehouse 24.</span></span> <span data-ttu-id="65c79-121">Cet entrepôt est activé pour la gestion du transport et la gestion avancée des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="65c79-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="65c79-122">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="65c79-122">Click Save.</span></span>
12. <span data-ttu-id="65c79-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="65c79-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="65c79-124">Créer une charge</span><span class="sxs-lookup"><span data-stu-id="65c79-124">Create a new load</span></span>
1. <span data-ttu-id="65c79-125">Accédez à Gestion du transport > Planning > Console de planification des charges.</span><span class="sxs-lookup"><span data-stu-id="65c79-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="65c79-126">Cliquez sur l'onglet Lignes de vente.</span><span class="sxs-lookup"><span data-stu-id="65c79-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="65c79-127">Désormais vous établirez la charge pour la commande client que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="65c79-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="65c79-128">Les charges peuvent être établies selon l'offre et de la demande des commandes fournisseurs, des ordres de transfert et des commandes client.</span><span class="sxs-lookup"><span data-stu-id="65c79-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="65c79-129">Dans le volet Actions, cliquez sur Approvisionnement et demande.</span><span class="sxs-lookup"><span data-stu-id="65c79-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="65c79-130">Cliquez sur À une nouvelle charge.</span><span class="sxs-lookup"><span data-stu-id="65c79-130">Click To new load.</span></span>
5. <span data-ttu-id="65c79-131">Dans le champ ID du modèle de charge, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="65c79-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="65c79-132">Le modèle de charge définit les mesures maximales pour le poids et le volume de la charge entière.</span><span class="sxs-lookup"><span data-stu-id="65c79-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="65c79-133">Par exemple, le modèle de charge peut représenter la taille d'un conteneur ou d'un camion.</span><span class="sxs-lookup"><span data-stu-id="65c79-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="65c79-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="65c79-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="65c79-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="65c79-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="65c79-136">Classer et acheminer la charge</span><span class="sxs-lookup"><span data-stu-id="65c79-136">Rate and route the load</span></span>
1. <span data-ttu-id="65c79-137">Cliquez sur Classement et acheminement.</span><span class="sxs-lookup"><span data-stu-id="65c79-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="65c79-138">Cliquez sur Atelier des routes et frais.</span><span class="sxs-lookup"><span data-stu-id="65c79-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="65c79-139">Cliquez sur Magasin de taux.</span><span class="sxs-lookup"><span data-stu-id="65c79-139">Click Rate shop.</span></span>
4. <span data-ttu-id="65c79-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="65c79-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="65c79-141">Cliquez sur Affecter.</span><span class="sxs-lookup"><span data-stu-id="65c79-141">Click Assign.</span></span>
6. <span data-ttu-id="65c79-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="65c79-142">Close the page.</span></span>
7. <span data-ttu-id="65c79-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="65c79-143">Close the page.</span></span>


