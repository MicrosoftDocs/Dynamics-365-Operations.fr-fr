---
title: ER Utiliser les dimensions financières comme source de données (Partie 1 – Créer un modèle de données)
description: Cette rubrique décrit comment configurer un modèle de gestion des états électroniques pour utiliser les dimensions financières comme source de données pour les rapports de gestion des états électroniques. (Partie 1)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92b44532dfae70f03d6686ca1d2f8b6f74345ee6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752458"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="b1b1d-104">ER Utiliser les dimensions financières comme source de données (Partie 1 – Créer un modèle de données)</span><span class="sxs-lookup"><span data-stu-id="b1b1d-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b1b1d-105">Les étapes suivantes expliquent comment un administrateur système ou un développeur d’états électroniques peut configurer un modèle de génération d’états électroniques (ER) pour utiliser les dimensions financières comme source de données pour les états ER.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="b1b1d-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="b1b1d-107">Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="b1b1d-108">Créer un modèle de données</span><span class="sxs-lookup"><span data-stu-id="b1b1d-108">Create a new data model</span></span>
1. <span data-ttu-id="b1b1d-109">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="b1b1d-110">Assurez-vous que le fournisseur « Litware, Inc. »</span><span class="sxs-lookup"><span data-stu-id="b1b1d-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="b1b1d-111">est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="b1b1d-112">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b1b1d-113">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="b1b1d-114">Dans le champ Nom, tapez « Exemple de modèle de dimensions financières ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="b1b1d-115">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-115">Click Create configuration.</span></span>
6. <span data-ttu-id="b1b1d-116">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-116">Click Designer.</span></span>
7. <span data-ttu-id="b1b1d-117">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="b1b1d-118">Dans le champ Nom, tapez « Entrée ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="b1b1d-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-119">Click Add.</span></span>
10. <span data-ttu-id="b1b1d-120">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="b1b1d-121">Dans le champ Nom, tapez « Société ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="b1b1d-122">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-122">Click Add.</span></span>
    * <span data-ttu-id="b1b1d-123">Nous ajouterons une nouvelle liste d’enregistrements à notre modèle.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-123">We will add to our model a new record list.</span></span> <span data-ttu-id="b1b1d-124">Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les paramètres des dimensions financières sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="b1b1d-125">Chaque dimension financière sera présentée dans cette liste en tant qu’enregistrement avec les champs appropriés représentant les paramètres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="b1b1d-126">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="b1b1d-127">Dans le champ Nom, tapez « Paramètre de dimensions ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="b1b1d-128">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="b1b1d-129">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-129">Click Add.</span></span>
17. <span data-ttu-id="b1b1d-130">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="b1b1d-131">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="b1b1d-132">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="b1b1d-133">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-133">Click Add.</span></span>
21. <span data-ttu-id="b1b1d-134">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="b1b1d-135">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="b1b1d-136">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-136">Click Add.</span></span>
24. <span data-ttu-id="b1b1d-137">Dans l’arborescence, sélectionnez « Entrée ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="b1b1d-138">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="b1b1d-139">Dans le champ Nom, tapez « Journal ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="b1b1d-140">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="b1b1d-141">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-141">Click Add.</span></span>
29. <span data-ttu-id="b1b1d-142">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="b1b1d-143">Dans le champ Nom, tapez « Traitement par lots ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="b1b1d-144">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="b1b1d-145">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-145">Click Add.</span></span>
33. <span data-ttu-id="b1b1d-146">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="b1b1d-147">Dans le champ Nom, tapez « Transaction ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="b1b1d-148">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="b1b1d-149">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-149">Click Add.</span></span>
37. <span data-ttu-id="b1b1d-150">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="b1b1d-151">Dans le champ Nom, tapez « Date ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="b1b1d-152">Sélectionnez « Date » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="b1b1d-153">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-153">Click Add.</span></span>
41. <span data-ttu-id="b1b1d-154">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="b1b1d-155">Dans le champ Nom, tapez « Débit ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="b1b1d-156">Sélectionnez « Réel » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="b1b1d-157">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-157">Click Add.</span></span>
45. <span data-ttu-id="b1b1d-158">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="b1b1d-159">Dans le champ Nom, tapez « Crédit ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="b1b1d-160">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-160">Click Add.</span></span>
48. <span data-ttu-id="b1b1d-161">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="b1b1d-162">Tapez « Devise » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="b1b1d-163">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="b1b1d-164">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-164">Click Add.</span></span>
52. <span data-ttu-id="b1b1d-165">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="b1b1d-166">Dans le champ Nom, tapez « N° document ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="b1b1d-167">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-167">Click Add.</span></span>
55. <span data-ttu-id="b1b1d-168">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="b1b1d-169">Dans le champ Nom, tapez « Données de dimensions ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="b1b1d-170">Sélectionnez « Liste d’enregistrements » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="b1b1d-171">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-171">Click Add.</span></span>
    * <span data-ttu-id="b1b1d-172">Nous avons ajouté une nouvelle liste d’enregistrements à notre modèle.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-172">We added to our model a new record list.</span></span> <span data-ttu-id="b1b1d-173">Cette liste exposera (pour les états ER utilisant ce modèle comme source de données) les valeurs des dimensions financières sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="b1b1d-174">Chaque dimension financière sera présentée dans cette liste en tant qu’enregistrement avec les champs appropriés représentant les valeurs de la dimension.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="b1b1d-175">Le nom de la dimension sera également présenté dans cet enregistrement en tant que champ à utiliser, si nécessaire, à des fins de sélection.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="b1b1d-176">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="b1b1d-177">Dans le champ Nom, tapez « Code ».</span><span class="sxs-lookup"><span data-stu-id="b1b1d-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="b1b1d-178">Sélectionnez « Chaîne » dans le champ Type d’article.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="b1b1d-179">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-179">Click Add.</span></span>
63. <span data-ttu-id="b1b1d-180">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="b1b1d-181">Tapez « Description » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="b1b1d-182">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-182">Click Add.</span></span>
66. <span data-ttu-id="b1b1d-183">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="b1b1d-184">Tapez « Nom » dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="b1b1d-185">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-185">Click Add.</span></span>
69. <span data-ttu-id="b1b1d-186">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-186">Click Save.</span></span>
70. <span data-ttu-id="b1b1d-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b1b1d-187">Close the page.</span></span>

![Page du concepteur des modèles de gestion des états électroniques](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]