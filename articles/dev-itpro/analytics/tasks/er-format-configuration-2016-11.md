--- 
title: "ER Créer une configuration de format (novembre 2016)"
description: "es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f004451a260b5be6c15c3975cd9e63ba9c1a7a2e
ms.openlocfilehash: 6fa5023a29c95ab9f10d8aacd51edc1a06c3c152
ms.contentlocale: fr-fr
ms.lasthandoff: 02/06/2019

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="fadda-103">ER Créer une configuration de format (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="fadda-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fadda-104">es étapes suivantes expliquent comment un utilisateur dans l'administrateur système ou le rôle Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER).</span><span class="sxs-lookup"><span data-stu-id="fadda-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="fadda-105">Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="fadda-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="fadda-106">Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».</span><span class="sxs-lookup"><span data-stu-id="fadda-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="fadda-107">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="fadda-107">Create a new format configuration</span></span>
1. <span data-ttu-id="fadda-108">Accédez à **Administration d'organisation > Espaces de travail > États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="fadda-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="fadda-109">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="fadda-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="fadda-110">Dans l'arborescence, sélectionnez **Paiements (modèle simplifié)**.</span><span class="sxs-lookup"><span data-stu-id="fadda-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="fadda-111">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fadda-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="fadda-112">Si vous ne voyez pas **Créer la configuration**, vous devez activer le mode Configuration de la page **Paramètres de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="fadda-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="fadda-113">Dans le champ **Nouveau**, entrez **Format basé sur le PaymentModel du modèle du paiement**.</span><span class="sxs-lookup"><span data-stu-id="fadda-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="fadda-114">Dans le champ **Nom**, tapez **LE SYSTÈME BACS (R-U factice)**.</span><span class="sxs-lookup"><span data-stu-id="fadda-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="fadda-115">Dans le champ **Description**, entrez **Format de paiement fournisseur du SYSTÈME BACS (R-U factice)**.</span><span class="sxs-lookup"><span data-stu-id="fadda-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="fadda-116">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="fadda-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="fadda-117">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="fadda-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="fadda-118">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="fadda-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="fadda-119">Un format spécifique de document électronique peut être défini.</span><span class="sxs-lookup"><span data-stu-id="fadda-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="fadda-120">Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="fadda-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="fadda-121">Dans le champ **Définition du modèle de données**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fadda-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="fadda-122">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="fadda-122">Click **Create configuration**.</span></span> <span data-ttu-id="fadda-123">Une nouvelle configuration client a été créée.</span><span class="sxs-lookup"><span data-stu-id="fadda-123">A new configuration has been created.</span></span> <span data-ttu-id="fadda-124">La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="fadda-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="fadda-125">Si vous ne voyez pas **Créer la configuration**, vous devez activer le mode Configuration de la page **Paramètres de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="fadda-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="fadda-126">Créer le format d'un document électronique</span><span class="sxs-lookup"><span data-stu-id="fadda-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="fadda-127">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="fadda-127">Click **Designer**.</span></span>
2. <span data-ttu-id="fadda-128">Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fadda-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="fadda-129">Dans l'arborescence, sélectionnez **Common\File**.</span><span class="sxs-lookup"><span data-stu-id="fadda-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="fadda-130">Dans le champ **Nom**, tapez **Xml**.</span><span class="sxs-lookup"><span data-stu-id="fadda-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="fadda-131">Dans le champ **Encodage**, tapez **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="fadda-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="fadda-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-132">Click **OK**.</span></span>
7. <span data-ttu-id="fadda-133">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fadda-133">Click **Add**.</span></span>
8. <span data-ttu-id="fadda-134">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="fadda-135">Dans le champ **Nom**, tapez **Message**.</span><span class="sxs-lookup"><span data-stu-id="fadda-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="fadda-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-136">Click **OK**.</span></span>
11. <span data-ttu-id="fadda-137">Dans l'arborescence, sélectionnez **Xml\Message**.</span><span class="sxs-lookup"><span data-stu-id="fadda-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="fadda-138">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="fadda-139">Dans le champ **Nom**, tapez **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="fadda-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="fadda-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-140">Click **OK**.</span></span>
15. <span data-ttu-id="fadda-141">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="fadda-142">Dans le champ Nom, tapez **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="fadda-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="fadda-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-143">Click **OK**.</span></span>
18. <span data-ttu-id="fadda-144">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="fadda-145">Dans le champ **Nom**, tapez **Paiements**.</span><span class="sxs-lookup"><span data-stu-id="fadda-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="fadda-146">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-146">Click **OK**.</span></span>
21. <span data-ttu-id="fadda-147">Dans l'arborescence, sélectionnez **Xml\Message\Paiements**.</span><span class="sxs-lookup"><span data-stu-id="fadda-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="fadda-148">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="fadda-149">Dans le champ **Nom**, tapez **Article**.</span><span class="sxs-lookup"><span data-stu-id="fadda-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="fadda-150">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-150">Click **OK**.</span></span>
25. <span data-ttu-id="fadda-151">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="fadda-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="fadda-152">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fadda-152">Click **Add**.</span></span>
27. <span data-ttu-id="fadda-153">Dans l'arborescence, sélectionnez **XML\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="fadda-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="fadda-154">Dans le champ Nom, tapez **Id**.</span><span class="sxs-lookup"><span data-stu-id="fadda-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="fadda-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-155">Click **OK**.</span></span>
30. <span data-ttu-id="fadda-156">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fadda-156">Click **Add**.</span></span>
31. <span data-ttu-id="fadda-157">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="fadda-158">Dans le champ Nom, tapez **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fadda-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="fadda-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-159">Click **OK**.</span></span>
34. <span data-ttu-id="fadda-160">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fadda-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="fadda-161">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="fadda-162">Dans le champ Nom, tapez **Nom**.</span><span class="sxs-lookup"><span data-stu-id="fadda-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="fadda-163">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-163">Click **OK**.</span></span>
38. <span data-ttu-id="fadda-164">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="fadda-165">Dans le champ **Nom**, tapez **Banque**.</span><span class="sxs-lookup"><span data-stu-id="fadda-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="fadda-166">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-166">Click **OK**.</span></span>
41. <span data-ttu-id="fadda-167">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque**.</span><span class="sxs-lookup"><span data-stu-id="fadda-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="fadda-168">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="fadda-169">Dans le champ **Nom**, tapez **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="fadda-170">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-170">Click **OK**.</span></span>
45. <span data-ttu-id="fadda-171">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="fadda-172">Dans le champ **Nom**, tapez **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="fadda-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-173">Click **OK**.</span></span>
48. <span data-ttu-id="fadda-174">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fadda-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="fadda-175">Cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="fadda-175">Click **Copy**.</span></span>
50. <span data-ttu-id="fadda-176">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="fadda-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="fadda-177">Cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="fadda-177">Click **Paste**.</span></span>
52. <span data-ttu-id="fadda-178">Dans le champ **Nom**, tapez **Payeur**.</span><span class="sxs-lookup"><span data-stu-id="fadda-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="fadda-179">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="fadda-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="fadda-180">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="fadda-181">Dans le champ **Nom**, tapez **Devise**.</span><span class="sxs-lookup"><span data-stu-id="fadda-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="fadda-182">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-182">Click **OK**.</span></span>
57. <span data-ttu-id="fadda-183">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="fadda-184">Dans le champ **Nom**, tapez **Description**.</span><span class="sxs-lookup"><span data-stu-id="fadda-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="fadda-185">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-185">Click **OK**.</span></span>
60. <span data-ttu-id="fadda-186">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="fadda-187">Dans le champ Nom, tapez **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="fadda-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="fadda-188">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-188">Click **OK**.</span></span>
63. <span data-ttu-id="fadda-189">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="fadda-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="fadda-190">Dans le champ Nom, tapez **Montant**.</span><span class="sxs-lookup"><span data-stu-id="fadda-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="fadda-191">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="fadda-192">Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données</span><span class="sxs-lookup"><span data-stu-id="fadda-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="fadda-193">Dans l'arborescence, sélectionnez **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="fadda-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="fadda-194">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fadda-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="fadda-195">Dans l'arborescence, sélectionnez **Texte\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="fadda-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="fadda-196">Dans le champ **Format**, tapez **jj-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="fadda-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="fadda-197">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-197">Click **OK**.</span></span>
6. <span data-ttu-id="fadda-198">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="fadda-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="fadda-199">Cliquez sur **Ajouter DateTime**.</span><span class="sxs-lookup"><span data-stu-id="fadda-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="fadda-200">Dans le champ **Format**, tapez **jj-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="fadda-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="fadda-201">Dans le champ de type **DateTime**, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="fadda-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="fadda-202">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-202">Click **OK**.</span></span>
11. <span data-ttu-id="fadda-203">Dans l'arborescence, sélectionnez **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="fadda-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="fadda-204">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fadda-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="fadda-205">Dans l'arborescence, sélectionnez **Texte\Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="fadda-206">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-206">Click **OK**.</span></span>
15. <span data-ttu-id="fadda-207">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Nom**.</span><span class="sxs-lookup"><span data-stu-id="fadda-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="fadda-208">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-208">Click **Add String**.</span></span>
17. <span data-ttu-id="fadda-209">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-209">Click **OK**.</span></span>
18. <span data-ttu-id="fadda-210">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="fadda-211">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-211">Click **Add String**.</span></span>
20. <span data-ttu-id="fadda-212">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-212">Click **OK**.</span></span>
21. <span data-ttu-id="fadda-213">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="fadda-214">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-214">Click **Add String**.</span></span>
23. <span data-ttu-id="fadda-215">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-215">Click **OK**.</span></span>
24. <span data-ttu-id="fadda-216">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Nom**.</span><span class="sxs-lookup"><span data-stu-id="fadda-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="fadda-217">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-217">Click **Add String**.</span></span>
26. <span data-ttu-id="fadda-218">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-218">Click **OK**.</span></span>
27. <span data-ttu-id="fadda-219">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="fadda-220">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-220">Click **Add String**.</span></span>
29. <span data-ttu-id="fadda-221">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-221">Click **OK**.</span></span>
30. <span data-ttu-id="fadda-222">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="fadda-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="fadda-223">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-223">Click **Add String**.</span></span>
32. <span data-ttu-id="fadda-224">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-224">Click **OK**.</span></span>
33. <span data-ttu-id="fadda-225">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Devise**.</span><span class="sxs-lookup"><span data-stu-id="fadda-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="fadda-226">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-226">Click **Add String**.</span></span>
35. <span data-ttu-id="fadda-227">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-227">Click **OK**.</span></span>
36. <span data-ttu-id="fadda-228">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Description**.</span><span class="sxs-lookup"><span data-stu-id="fadda-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="fadda-229">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-229">Click **Add String**.</span></span>
38. <span data-ttu-id="fadda-230">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-230">Click **OK**.</span></span>
39. <span data-ttu-id="fadda-231">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Montant**.</span><span class="sxs-lookup"><span data-stu-id="fadda-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="fadda-232">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="fadda-232">Click **Add String**.</span></span>
41. <span data-ttu-id="fadda-233">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fadda-233">Click **OK**.</span></span>
42. <span data-ttu-id="fadda-234">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fadda-234">Click **Save**.</span></span>
43. <span data-ttu-id="fadda-235">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fadda-235">Close the page.</span></span>


