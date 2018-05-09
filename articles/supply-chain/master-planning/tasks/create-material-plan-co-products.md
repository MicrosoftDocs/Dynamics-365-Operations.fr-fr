--- 
title: "Créer un plan matières pour des coproduits"
description: "Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f3a411e8fc773957b5ce3f24749242d9d0c6ffd0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="04d84-103">Créer un plan matières pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="04d84-103">Create a material plan for co-products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04d84-104">Le responsable de production organise les besoins en matières pour les articles qui sont des coproduits de formules.</span><span class="sxs-lookup"><span data-stu-id="04d84-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="04d84-105">La société fictive de démonstration utilisée pour créer cette procédure est USP2.</span><span class="sxs-lookup"><span data-stu-id="04d84-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="04d84-106">Créer une demande pour un coproduit</span><span class="sxs-lookup"><span data-stu-id="04d84-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="04d84-107">Allez dans le Tableau de bord par défaut.</span><span class="sxs-lookup"><span data-stu-id="04d84-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="04d84-108">Cliquez sur Traitement et recherche de commande client.</span><span class="sxs-lookup"><span data-stu-id="04d84-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="04d84-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="04d84-109">Click New.</span></span>
4. <span data-ttu-id="04d84-110">Cliquez sur Commande client.</span><span class="sxs-lookup"><span data-stu-id="04d84-110">Click Sales order.</span></span>
5. <span data-ttu-id="04d84-111">Tapez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="04d84-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="04d84-112">Exemple : US-001</span><span class="sxs-lookup"><span data-stu-id="04d84-112">Example: US-001</span></span>  
6. <span data-ttu-id="04d84-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="04d84-113">Click OK.</span></span>
7. <span data-ttu-id="04d84-114">Tapez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="04d84-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="04d84-115">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="04d84-115">Example: P6003</span></span>  
8. <span data-ttu-id="04d84-116">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="04d84-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="04d84-117">Exemple : 50000</span><span class="sxs-lookup"><span data-stu-id="04d84-117">Example: 50000</span></span>  
9. <span data-ttu-id="04d84-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="04d84-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="04d84-119">Créer un plan matières pour des coproduits</span><span class="sxs-lookup"><span data-stu-id="04d84-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="04d84-120">Cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="04d84-120">Click Master planning.</span></span>
2. <span data-ttu-id="04d84-121">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="04d84-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="04d84-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04d84-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="04d84-123">Exemple : Programme</span><span class="sxs-lookup"><span data-stu-id="04d84-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="04d84-124">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="04d84-124">Click Run.</span></span>
5. <span data-ttu-id="04d84-125">Développez ou réduisez la section Enregistrements à inclure.</span><span class="sxs-lookup"><span data-stu-id="04d84-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="04d84-126">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="04d84-126">Click Filter.</span></span>
7. <span data-ttu-id="04d84-127">Dans la liste, sélectionnez la ligne pour Champ = Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="04d84-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="04d84-128">Tapez une valeur dans le champ Critères.</span><span class="sxs-lookup"><span data-stu-id="04d84-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="04d84-129">Exemple : P6003</span><span class="sxs-lookup"><span data-stu-id="04d84-129">Example: P6003</span></span>  
9. <span data-ttu-id="04d84-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="04d84-130">Click OK.</span></span>
10. <span data-ttu-id="04d84-131">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="04d84-131">Click OK.</span></span>
11. <span data-ttu-id="04d84-132">Cliquez sur Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="04d84-132">Click Planned orders.</span></span>
12. <span data-ttu-id="04d84-133">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="04d84-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="04d84-134">Par exemple, filtrez su le champ Numéro d'article avec une valeur de « P6000 ».</span><span class="sxs-lookup"><span data-stu-id="04d84-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="04d84-135">Filtrez par élément de formule ayant comme coproduit de l'article pour lequel vous avez créé une commande client.</span><span class="sxs-lookup"><span data-stu-id="04d84-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="04d84-136">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04d84-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="04d84-137">Sélectionnez n'importe quelle ligne renvoyée par le filtre.</span><span class="sxs-lookup"><span data-stu-id="04d84-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="04d84-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04d84-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="04d84-139">Développez ou réduisez la section Origine des besoins.</span><span class="sxs-lookup"><span data-stu-id="04d84-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="04d84-140">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04d84-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="04d84-141">L'ordre prévisionnel est chevillé à la commande client du coproduit.</span><span class="sxs-lookup"><span data-stu-id="04d84-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="04d84-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="04d84-142">Close the page.</span></span>


