--- 
title: "Créer une hiérarchie d'états d'organisation"
description: "Utilisez cette procédure pour créer une hiérarchie d'état pour la génération d'états d'organisation."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f593c59660abcf5b0d5771ddd9daced6ec5fbfb4
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="66ce7-103">Créer une hiérarchie d'états d'organisation</span><span class="sxs-lookup"><span data-stu-id="66ce7-103">Create an organization report hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="66ce7-104">Utilisez cette procédure pour créer une hiérarchie d'état pour la génération d'états d'organisation.</span><span class="sxs-lookup"><span data-stu-id="66ce7-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="66ce7-105">Cet enregistrement a pour but de vous guider dans la hiérarchie de dimension afin que vous puissiez continuer jusqu'à ce que la structure de génération d'états d'organisation soit créée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="66ce7-106">Cet enregistrement utilise la société fictive USP2.</span><span class="sxs-lookup"><span data-stu-id="66ce7-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="66ce7-107">Accédez à Contrôle de gestion > Dimensions > Hiérarchies des dimensions.</span><span class="sxs-lookup"><span data-stu-id="66ce7-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="66ce7-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-108">Click New.</span></span>
3. <span data-ttu-id="66ce7-109">Dans le champ HierarchyTypeComboBox, sélectionnez « Hiérarchie de classification de dimension ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="66ce7-110">Sélectionnez Hiérarchie de classification de dimension.</span><span class="sxs-lookup"><span data-stu-id="66ce7-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="66ce7-111">Le type Hiérarchie de classification de dimension est utilisé pour définir les règles et les déclarations.</span><span class="sxs-lookup"><span data-stu-id="66ce7-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="66ce7-112">Il prend en charge toutes les dimensions, comme les objets de coût, les éléments de coût et les dimensions statistiques.</span><span class="sxs-lookup"><span data-stu-id="66ce7-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="66ce7-113">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-113">Click Create.</span></span>
5. <span data-ttu-id="66ce7-114">Dans le champ Nom de la hiérarchie des dimensions, tapez « Organisation USP2 ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="66ce7-115">Dans le champ Dimension, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-116">Sélectionnez Centres de coût.</span><span class="sxs-lookup"><span data-stu-id="66ce7-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="66ce7-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-117">Click Save.</span></span>
8. <span data-ttu-id="66ce7-118">Cliquez sur Afficher la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="66ce7-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="66ce7-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-119">Click New.</span></span>
10. <span data-ttu-id="66ce7-120">Dans le champ Nom du nœud, tapez « PDG ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="66ce7-121">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-121">Click Save.</span></span>
12. <span data-ttu-id="66ce7-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-122">Click New.</span></span>
13. <span data-ttu-id="66ce7-123">Dans le champ Nom du nœud, entrez « Centres de coût du PDG ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="66ce7-124">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-124">Click Save.</span></span>
15. <span data-ttu-id="66ce7-125">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-125">Click New.</span></span>
16. <span data-ttu-id="66ce7-126">Dans le champ Nom du nœud, entrez « Région est ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="66ce7-127">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-127">Click Save.</span></span>
18. <span data-ttu-id="66ce7-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-128">Click New.</span></span>
19. <span data-ttu-id="66ce7-129">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="66ce7-130">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-131">Sélectionnez le membre de dimension qui correspond au nœud.</span><span class="sxs-lookup"><span data-stu-id="66ce7-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="66ce7-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-132">Click Save.</span></span>
22. <span data-ttu-id="66ce7-133">Dans l'arborescence, sélectionnez « Organisation USP2\PDG\Centres de coût du PDG.</span><span class="sxs-lookup"><span data-stu-id="66ce7-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="66ce7-134">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-134">Click New.</span></span>
24. <span data-ttu-id="66ce7-135">Dans le champ Nom du nœud, entrez « Région ouest ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="66ce7-136">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-136">Click Save.</span></span>
26. <span data-ttu-id="66ce7-137">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-137">Click New.</span></span>
27. <span data-ttu-id="66ce7-138">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="66ce7-139">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-140">Sélectionnez le membre de dimension qui correspond au nœud.</span><span class="sxs-lookup"><span data-stu-id="66ce7-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="66ce7-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-141">Click Save.</span></span>
30. <span data-ttu-id="66ce7-142">Dans l'arborescence, sélectionnez « Organisation USP2\PDG ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="66ce7-143">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-143">Click New.</span></span>
32. <span data-ttu-id="66ce7-144">Dans le champ Nom du nœud, tapez « Centres de coût du directeur financier ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="66ce7-145">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-145">Click Save.</span></span>
34. <span data-ttu-id="66ce7-146">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-146">Click New.</span></span>
35. <span data-ttu-id="66ce7-147">Dans le champ Nom du nœud, tapez « Campa marketing ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="66ce7-148">Dans le champ Nom du nœud, tapez « Campagne marketing ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="66ce7-149">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-149">Click Save.</span></span>
38. <span data-ttu-id="66ce7-150">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-150">Click New.</span></span>
39. <span data-ttu-id="66ce7-151">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="66ce7-152">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-153">Sélectionnez le membre de dimension qui correspond au nœud.</span><span class="sxs-lookup"><span data-stu-id="66ce7-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="66ce7-154">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-154">Click Save.</span></span>
42. <span data-ttu-id="66ce7-155">Dans l'arborescence, sélectionnez « Organisation USP2\PDG\Centres de coût du directeur financier.</span><span class="sxs-lookup"><span data-stu-id="66ce7-155">In the tree, select 'Oganization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="66ce7-156">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-156">Click New.</span></span>
44. <span data-ttu-id="66ce7-157">Dans le champ Nom du nœud, tapez « Salons commerciaux ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="66ce7-158">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-158">Click Save.</span></span>
46. <span data-ttu-id="66ce7-159">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-159">Click New.</span></span>
47. <span data-ttu-id="66ce7-160">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="66ce7-161">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-162">Sélectionnez le membre de dimension qui correspond au nœud.</span><span class="sxs-lookup"><span data-stu-id="66ce7-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="66ce7-163">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-163">Click Save.</span></span>
50. <span data-ttu-id="66ce7-164">Dans l'arborescence, sélectionnez « Organisation USP2\PDG ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="66ce7-165">Dans le champ Nom du nœud, tapez « Centres de coût du directeur informatique ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="66ce7-166">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-166">Click Save.</span></span>
53. <span data-ttu-id="66ce7-167">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-167">Click New.</span></span>
54. <span data-ttu-id="66ce7-168">Dans le champ Nom du nœud, tapez « Centres d'appel ».</span><span class="sxs-lookup"><span data-stu-id="66ce7-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="66ce7-169">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-169">Click Save.</span></span>
56. <span data-ttu-id="66ce7-170">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="66ce7-170">Click New.</span></span>
57. <span data-ttu-id="66ce7-171">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="66ce7-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="66ce7-172">Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="66ce7-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="66ce7-173">Sélectionnez le membre de dimension qui correspond au nœud.</span><span class="sxs-lookup"><span data-stu-id="66ce7-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="66ce7-174">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="66ce7-174">Click Save.</span></span>


