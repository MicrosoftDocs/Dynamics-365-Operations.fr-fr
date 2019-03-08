---
title: Définir le processus de comptage de cycle partiel d'emplacement
description: Lorsque vous utilisez des plans d'inventaire tournant pour créer le travail d'inventaire, vous pouvez guider les opérations d'inventaire réelles en demandant que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de l'ensemble du stock disponible dans l'emplacement.
author: ShylaThompson
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3aafb42cea1664b0629f57fe4492736601902cc1
ms.sourcegitcommit: bacad87e2b9146e08e6fe16af01356954eb90574
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "373398"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="68f7a-103">Définir le processus de comptage de cycle partiel d'emplacement</span><span class="sxs-lookup"><span data-stu-id="68f7a-103">Define partial location cycle counting process</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68f7a-104">Lorsque vous utilisez des plans d'inventaire tournant pour créer le travail d'inventaire, vous pouvez guider les opérations d'inventaire réelles en demandant que seuls des produits et des variantes de produit spécifiques soient comptabilisés au lieu de l'ensemble du stock disponible dans l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="68f7a-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="68f7a-105">Lorsque vous appliquez un filtre sur des produits spécifiques, le gestionnaire d'entrepôt peut réduire les frais généraux de révision, éviter toute erreur de consolidation et gagner du temps.</span><span class="sxs-lookup"><span data-stu-id="68f7a-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="68f7a-106">Généralement, un gestionnaire d'entrepôt effectue les tâches de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="68f7a-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="68f7a-107">Vous pouvez exécuter cette procédure avec la société fictive de démonstration USMF ou avec vos propres données.</span><span class="sxs-lookup"><span data-stu-id="68f7a-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="68f7a-108">Créer un modèle de travail d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="68f7a-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="68f7a-109">Accédez à Gestion des entrepôts > Configuration > Travail > Modèles de travail.</span><span class="sxs-lookup"><span data-stu-id="68f7a-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="68f7a-110">Dans le champ Type d'ordre d'exécution, sélectionnez « Cycle tournant ».</span><span class="sxs-lookup"><span data-stu-id="68f7a-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="68f7a-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68f7a-111">Click New.</span></span>
4. <span data-ttu-id="68f7a-112">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="68f7a-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="68f7a-113">L'ordre de tri est du plus petit nombre au plus grand nombre.</span><span class="sxs-lookup"><span data-stu-id="68f7a-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="68f7a-114">La valeur doit être supérieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="68f7a-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="68f7a-115">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68f7a-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="68f7a-116">Dans le champ Modèle de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="68f7a-117">Dans le champ Description du modèle de travail, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="68f7a-118">Dans le champ ID pool de travail, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="68f7a-119">Dans le champ Priorité du travail, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="68f7a-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68f7a-120">Click Save.</span></span>
11. <span data-ttu-id="68f7a-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68f7a-121">Click New.</span></span>
12. <span data-ttu-id="68f7a-122">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68f7a-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="68f7a-123">Dans le champ Type de travail, sélectionnez « Comptage ».</span><span class="sxs-lookup"><span data-stu-id="68f7a-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="68f7a-124">Saisissez ou sélectionnez une valeur dans le champ ID classe de travail.</span><span class="sxs-lookup"><span data-stu-id="68f7a-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="68f7a-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68f7a-125">Click Save.</span></span>
16. <span data-ttu-id="68f7a-126">Cliquez sur Pauses de ligne de travail.</span><span class="sxs-lookup"><span data-stu-id="68f7a-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="68f7a-127">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68f7a-127">Click New.</span></span>
18. <span data-ttu-id="68f7a-128">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="68f7a-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="68f7a-129">L'ordre de tri est du plus petit nombre au plus grand nombre.</span><span class="sxs-lookup"><span data-stu-id="68f7a-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="68f7a-130">La valeur doit être supérieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="68f7a-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="68f7a-131">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68f7a-131">Click Save.</span></span>
20. <span data-ttu-id="68f7a-132">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68f7a-132">Close the page.</span></span>
21. <span data-ttu-id="68f7a-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68f7a-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="68f7a-134">Créer un plan d'inventaire tournant</span><span class="sxs-lookup"><span data-stu-id="68f7a-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="68f7a-135">Accédez à Gestion de l'entrepôt > Paramétrage > Inventaire tournant > Plans d'inventaire tournant.</span><span class="sxs-lookup"><span data-stu-id="68f7a-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="68f7a-136">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68f7a-136">Click New.</span></span>
3. <span data-ttu-id="68f7a-137">Dans le champ ID plan d'inventaire tournant, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="68f7a-138">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="68f7a-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="68f7a-139">Dans le champ Nombre maximal d'inventaires tournants, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="68f7a-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="68f7a-140">Saisissez ou sélectionnez une valeur dans le champ Modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="68f7a-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="68f7a-141">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="68f7a-141">Click New.</span></span>
8. <span data-ttu-id="68f7a-142">Entrez un nombre dans le champ Numéro de souche.</span><span class="sxs-lookup"><span data-stu-id="68f7a-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="68f7a-143">L'ordre de tri est du plus petit nombre au plus grand nombre.</span><span class="sxs-lookup"><span data-stu-id="68f7a-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="68f7a-144">La valeur doit être supérieure à 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="68f7a-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="68f7a-145">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="68f7a-146">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68f7a-146">Click Save.</span></span>
11. <span data-ttu-id="68f7a-147">Cliquez sur Définir une requête de produit.</span><span class="sxs-lookup"><span data-stu-id="68f7a-147">Click Define product query.</span></span>
12. <span data-ttu-id="68f7a-148">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="68f7a-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="68f7a-149">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="68f7a-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="68f7a-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68f7a-150">Click OK.</span></span>
15. <span data-ttu-id="68f7a-151">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68f7a-151">Close the page.</span></span>

