---
title: Créer des gammes (février 2016)
description: Cette tâche consiste à créer des gammes de production pur un produit fini et semi-fini.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567849"
---
# <a name="create-routes-february-2016"></a><span data-ttu-id="3b6ae-103">Créer des gammes (février 2016)</span><span class="sxs-lookup"><span data-stu-id="3b6ae-103">Create routes (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b6ae-104">Cette tâche consiste à créer des gammes de production pur un produit fini et semi-fini.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="3b6ae-105">Il s'agit de la cinquième tâche dans la série de calculs des nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="3b6ae-106">Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="3b6ae-107">Créer une gamme pour un produit semi-fini</span><span class="sxs-lookup"><span data-stu-id="3b6ae-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="3b6ae-108">Allez à Gestion des informations sur les produits > Produits > Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="3b6ae-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3b6ae-110">Sélectionnez le numéro d'article BOM_2.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="3b6ae-111">Cliquez sur Ingénieur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="3b6ae-112">Cliquez sur Gamme</span><span class="sxs-lookup"><span data-stu-id="3b6ae-112">Click Route.</span></span>
5. <span data-ttu-id="3b6ae-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-113">Click New.</span></span>
6. <span data-ttu-id="3b6ae-114">Cliquez sur Gamme et version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-114">Click Route and route version.</span></span>
7. <span data-ttu-id="3b6ae-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3b6ae-116">Entrez ROUTE_2, par exemple.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="3b6ae-117">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-118">Pour cet exemple, entrez ou sélectionnez le site 1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="3b6ae-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-119">Click OK.</span></span>
10. <span data-ttu-id="3b6ae-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-120">Click New.</span></span>
11. <span data-ttu-id="3b6ae-121">Dans le champ Opération, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-122">Pour cet exemple, sélectionnez Assemblage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="3b6ae-123">Entrez un nombre dans le champ Temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="3b6ae-124">Entrez 1, par exemple.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-124">For example, type 1.</span></span> <span data-ttu-id="3b6ae-125">Les temps d'exécution font généralement partie du prix calculé pour un article.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="3b6ae-126">Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-127">Pour cet exemple, sélectionnez Std.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="3b6ae-128">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="3b6ae-129">Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-130">Pour cet exemple, sélectionnez Assemblage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="3b6ae-131">Cliquer sur l'onglet Temps.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-131">Click the Times tab.</span></span>
17. <span data-ttu-id="3b6ae-132">Dans le champ Temps de réglage, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="3b6ae-133">Pour cet exemple, tapez 1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-133">For this example, type 1.</span></span> <span data-ttu-id="3b6ae-134">Les temps de réglage font généralement partie du prix calculé pour un article.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="3b6ae-135">Dans le volet Action, cliquez Version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="3b6ae-136">Cliquez sur Approuver.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-136">Click Approve.</span></span>
20. <span data-ttu-id="3b6ae-137">Sélectionnez Oui dans le champ Voulez-vous également approuver la gamme ? .</span><span class="sxs-lookup"><span data-stu-id="3b6ae-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="3b6ae-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-138">Click OK.</span></span>
22. <span data-ttu-id="3b6ae-139">Dans le volet Action, cliquez Version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="3b6ae-140">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-140">Click Activate.</span></span>
24. <span data-ttu-id="3b6ae-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-141">Close the page.</span></span>
25. <span data-ttu-id="3b6ae-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="3b6ae-143">Créer une gamme pour un produit fini</span><span class="sxs-lookup"><span data-stu-id="3b6ae-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="3b6ae-144">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3b6ae-145">Sélectionnez le numéro d'article BOM_1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="3b6ae-146">Cliquez sur Ingénieur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="3b6ae-147">Cliquez sur Gamme</span><span class="sxs-lookup"><span data-stu-id="3b6ae-147">Click Route.</span></span>
4. <span data-ttu-id="3b6ae-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-148">Click New.</span></span>
5. <span data-ttu-id="3b6ae-149">Cliquez sur Gamme et version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-149">Click Route and route version.</span></span>
6. <span data-ttu-id="3b6ae-150">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3b6ae-151">Pour cet exemple; entrez ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="3b6ae-152">Saisissez ou sélectionnez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-153">Pour cet exemple, entrez ou sélectionnez le site 1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="3b6ae-154">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-154">Click OK.</span></span>
9. <span data-ttu-id="3b6ae-155">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-155">Click New.</span></span>
10. <span data-ttu-id="3b6ae-156">Dans le champ Opération, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-157">Pour cet exemple, sélectionnez Conditionnement.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="3b6ae-158">Entrez un nombre dans le champ Temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="3b6ae-159">Pour cet exemple, tapez 1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="3b6ae-160">Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-161">Pour cet exemple, sélectionnez Std.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="3b6ae-162">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="3b6ae-163">Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="3b6ae-164">Pour cet exemple, sélectionnez Conditionnement.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="3b6ae-165">Cliquer sur l'onglet Temps.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-165">Click the Times tab.</span></span>
16. <span data-ttu-id="3b6ae-166">Dans le champ Temps de réglage, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="3b6ae-167">Pour cet exemple, tapez 1.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="3b6ae-168">Dans le volet Action, cliquez Version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="3b6ae-169">Cliquez sur Approuver.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-169">Click Approve.</span></span>
19. <span data-ttu-id="3b6ae-170">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-170">Click OK.</span></span>
20. <span data-ttu-id="3b6ae-171">Dans le volet Action, cliquez Version de gamme.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="3b6ae-172">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-172">Click Activate.</span></span>
22. <span data-ttu-id="3b6ae-173">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-173">Close the page.</span></span>
23. <span data-ttu-id="3b6ae-174">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="3b6ae-175">Activer la consommation automatique du temps de réglage</span><span class="sxs-lookup"><span data-stu-id="3b6ae-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="3b6ae-176">Accédez à Contrôle de la production > Paramétrage > Gammes > Groupes de gammes.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="3b6ae-177">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3b6ae-178">Sélectionnez Std dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="3b6ae-179">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-179">Click Edit.</span></span>
4. <span data-ttu-id="3b6ae-180">Sélectionnez Oui le champ Temps de réglage.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="3b6ae-181">Les temps de réglage font généralement partie du prix calculé pour un article.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="3b6ae-182">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-182">Click Save.</span></span>
6. <span data-ttu-id="3b6ae-183">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-183">Close the page.</span></span>

