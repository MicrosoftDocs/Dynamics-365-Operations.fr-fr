---
title: ER Utiliser les dimensions financières comme source de données (Partie 1 - Créer un modèle de données)
description: Les étapes suivantes expliquent comment un administrateur système ou un développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84f546b73eefe3ead78c6ab3fdbbc05d0db5fef5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544700"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="34cbc-103">ER Utiliser les dimensions financières comme source de données (Partie 1 : Créer un modèle de données)</span><span class="sxs-lookup"><span data-stu-id="34cbc-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34cbc-104">Les étapes suivantes expliquent comment un administrateur système ou un développeur d'états électroniques peut configurer un modèle de génération d'états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="34cbc-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="34cbc-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="34cbc-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="34cbc-106">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="34cbc-107">Créer un modèle de données</span><span class="sxs-lookup"><span data-stu-id="34cbc-107">Create a new data model</span></span>
1. <span data-ttu-id="34cbc-108">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="34cbc-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="34cbc-109">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="34cbc-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="34cbc-110">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="34cbc-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="34cbc-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="34cbc-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="34cbc-112">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="34cbc-113">Dans le champ Nom, tapez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="34cbc-114">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="34cbc-114">Click Create configuration.</span></span>
6. <span data-ttu-id="34cbc-115">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="34cbc-115">Click Designer.</span></span>
7. <span data-ttu-id="34cbc-116">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="34cbc-117">Dans le champ Nom, tapez « Entrée ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="34cbc-118">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-118">Click Add.</span></span>
10. <span data-ttu-id="34cbc-119">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="34cbc-120">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="34cbc-121">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-121">Click Add.</span></span>
    * <span data-ttu-id="34cbc-122">Nous ajouterons une nouvelle liste d'enregistrements à notre modèle.</span><span class="sxs-lookup"><span data-stu-id="34cbc-122">We will add to our model a new record list.</span></span> <span data-ttu-id="34cbc-123">Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les paramètres des dimensions financières sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="34cbc-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="34cbc-124">Chaque dimension financière sera présentée dans cette liste en tant qu'enregistrement avec les champs appropriés représentant les paramètres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="34cbc-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="34cbc-125">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="34cbc-126">Dans le champ Nom, tapez « Paramètre de dimensions ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="34cbc-127">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="34cbc-128">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-128">Click Add.</span></span>
17. <span data-ttu-id="34cbc-129">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="34cbc-130">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="34cbc-131">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="34cbc-132">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-132">Click Add.</span></span>
21. <span data-ttu-id="34cbc-133">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="34cbc-134">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34cbc-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="34cbc-135">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-135">Click Add.</span></span>
24. <span data-ttu-id="34cbc-136">Dans l'arborescence, sélectionnez « Entrée ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="34cbc-137">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="34cbc-138">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="34cbc-139">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="34cbc-140">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-140">Click Add.</span></span>
29. <span data-ttu-id="34cbc-141">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="34cbc-142">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="34cbc-143">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="34cbc-144">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-144">Click Add.</span></span>
33. <span data-ttu-id="34cbc-145">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="34cbc-146">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="34cbc-147">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="34cbc-148">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-148">Click Add.</span></span>
37. <span data-ttu-id="34cbc-149">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="34cbc-150">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="34cbc-151">Sélectionnez « Date » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="34cbc-152">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-152">Click Add.</span></span>
41. <span data-ttu-id="34cbc-153">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="34cbc-154">Dans le champ Nom, tapez « Débit ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="34cbc-155">Sélectionnez « Réel » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="34cbc-156">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-156">Click Add.</span></span>
45. <span data-ttu-id="34cbc-157">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="34cbc-158">Dans le champ Nom, tapez « Crédit ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="34cbc-159">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-159">Click Add.</span></span>
48. <span data-ttu-id="34cbc-160">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="34cbc-161">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34cbc-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="34cbc-162">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="34cbc-163">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-163">Click Add.</span></span>
52. <span data-ttu-id="34cbc-164">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="34cbc-165">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="34cbc-166">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-166">Click Add.</span></span>
55. <span data-ttu-id="34cbc-167">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="34cbc-168">Dans le champ Nom, tapez « Données de dimensions ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="34cbc-169">Sélectionnez « Liste d'enregistrements » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="34cbc-170">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-170">Click Add.</span></span>
    * <span data-ttu-id="34cbc-171">Nous avons ajouté une nouvelle liste d'enregistrements à notre modèle.</span><span class="sxs-lookup"><span data-stu-id="34cbc-171">We added to our model a new record list.</span></span> <span data-ttu-id="34cbc-172">Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les valeurs des dimensions financières sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="34cbc-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="34cbc-173">Chaque dimension financière sera présentée dans cette liste en tant qu'enregistrement avec les champs appropriés représentant les valeurs de la dimension.</span><span class="sxs-lookup"><span data-stu-id="34cbc-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="34cbc-174">Le nom de la dimension sera également présenté dans cet enregistrement en tant que champ à utiliser, si nécessaire, à des fins de sélection.</span><span class="sxs-lookup"><span data-stu-id="34cbc-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="34cbc-175">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="34cbc-176">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="34cbc-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="34cbc-177">Sélectionnez « Chaîne » dans le champ Type d'article.</span><span class="sxs-lookup"><span data-stu-id="34cbc-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="34cbc-178">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-178">Click Add.</span></span>
63. <span data-ttu-id="34cbc-179">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="34cbc-180">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34cbc-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="34cbc-181">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-181">Click Add.</span></span>
66. <span data-ttu-id="34cbc-182">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="34cbc-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="34cbc-183">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="34cbc-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="34cbc-184">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="34cbc-184">Click Add.</span></span>
69. <span data-ttu-id="34cbc-185">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="34cbc-185">Click Save.</span></span>
70. <span data-ttu-id="34cbc-186">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="34cbc-186">Close the page.</span></span>

