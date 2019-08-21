---
title: Planifier des chargements et des expéditions à l'aide de l'atelier Planification des chargements
description: Cette rubrique indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5e20eef8aa748bb64c6c14dd7e1d92ccf6592e0
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2019
ms.locfileid: "1739063"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="44ec0-103">Planifier des chargements et des expéditions à l'aide de l'atelier Planification des chargements</span><span class="sxs-lookup"><span data-stu-id="44ec0-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44ec0-104">Cette rubrique indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client.</span><span class="sxs-lookup"><span data-stu-id="44ec0-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="44ec0-105">Il est indispensable de créer la commande client en premier.</span><span class="sxs-lookup"><span data-stu-id="44ec0-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="44ec0-106">Cette procédure fait partie du travail quotidien pour le coordinateur de transport.</span><span class="sxs-lookup"><span data-stu-id="44ec0-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="44ec0-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="44ec0-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="44ec0-108">Créer une commande client</span><span class="sxs-lookup"><span data-stu-id="44ec0-108">Create a sales order</span></span>
1. <span data-ttu-id="44ec0-109">Allez dans **Volet de navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="44ec0-110">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-110">Select **New**.</span></span>
3. <span data-ttu-id="44ec0-111">Dans le champ **Compte client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="44ec0-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="44ec0-112">Sélectionnez le compte **US-004**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="44ec0-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-113">Select **OK**.</span></span>
6. <span data-ttu-id="44ec0-114">Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="44ec0-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="44ec0-115">Sélectionnez l'article **A0001**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-115">Select item **A0001**.</span></span> <span data-ttu-id="44ec0-116">**A0001** est activé pour la gestion du transport.</span><span class="sxs-lookup"><span data-stu-id="44ec0-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="44ec0-117">Dans le champ **Site**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche, puis sélectionnez un article.</span><span class="sxs-lookup"><span data-stu-id="44ec0-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="44ec0-118">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="44ec0-119">Dans le champ **Entrepôt**, entrez « 24 » pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="44ec0-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="44ec0-120">Cet entrepôt est activé pour la gestion du transport et la gestion avancée des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="44ec0-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="44ec0-121">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-121">Select **Save**.</span></span>
12. <span data-ttu-id="44ec0-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44ec0-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="44ec0-123">Créer une charge</span><span class="sxs-lookup"><span data-stu-id="44ec0-123">Create a new load</span></span>
1. <span data-ttu-id="44ec0-124">Allez dans **Volet de navigation > Modules > Gestion du transport > Planification > Console de planification des charges**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="44ec0-125">Sélectionnez l'onglet **Lignes de vente**. Désormais, vous établirez la charge pour la commande client que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="44ec0-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="44ec0-126">Les charges peuvent être établies selon l'offre et de la demande des commandes fournisseurs, des ordres de transfert et des commandes client.</span><span class="sxs-lookup"><span data-stu-id="44ec0-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="44ec0-127">Dans le volet Actions, sélectionnez **Approvisionnement et demande**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="44ec0-128">Sélectionnez **Dans une nouvelle charge**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-128">Select **To new load**.</span></span>
5. <span data-ttu-id="44ec0-129">Dans le champ **ID du modèle de charge**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="44ec0-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="44ec0-130">Le modèle de charge définit les mesures maximales pour le poids et le volume de la charge entière.</span><span class="sxs-lookup"><span data-stu-id="44ec0-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="44ec0-131">Par exemple, le modèle de charge peut représenter la taille d'un conteneur ou d'un camion.</span><span class="sxs-lookup"><span data-stu-id="44ec0-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="44ec0-132">Permet de sélectionner un article.</span><span class="sxs-lookup"><span data-stu-id="44ec0-132">Select an item.</span></span>
6. <span data-ttu-id="44ec0-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="44ec0-134">Classer et acheminer la charge</span><span class="sxs-lookup"><span data-stu-id="44ec0-134">Rate and route the load</span></span>
1. <span data-ttu-id="44ec0-135">Sélectionnez **Classement et acheminement**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="44ec0-136">Sélectionnez **Atelier des routes et frais**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="44ec0-137">Sélectionnez **Magasin de taux**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="44ec0-138">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="44ec0-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="44ec0-139">Sélectionnez **Assigner**.</span><span class="sxs-lookup"><span data-stu-id="44ec0-139">Select **Assign**.</span></span>
6. <span data-ttu-id="44ec0-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="44ec0-140">Close the page.</span></span>

