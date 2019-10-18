---
title: ER Créer une configuration de format (novembre 2016)
description: Cette rubrique explique comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1fd41b1724eb2e0405c0e7a7e0ff0aea4a945e0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184943"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="f3b66-103">ER Créer une configuration de format (novembre 2016)</span><span class="sxs-lookup"><span data-stu-id="f3b66-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3b66-104">Cette rubrique explique comment un utilisateur ayant le rôle d'administrateur système ou de développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER).</span><span class="sxs-lookup"><span data-stu-id="f3b66-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f3b66-105">Cette configuration de formats définira le format des documents électroniques utilisés pour traiter les paiements.</span><span class="sxs-lookup"><span data-stu-id="f3b66-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f3b66-106">Dans cet exemple, vous allez créer une configuration de format pour la société témoin, Litware, Inc. Pour effectuer ces étapes, vous devez d'abord accomplir celles de la procédure « Mettre en relation le modèle aux sources de données sélectionnées ».</span><span class="sxs-lookup"><span data-stu-id="f3b66-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f3b66-107">Créer une configuration de format</span><span class="sxs-lookup"><span data-stu-id="f3b66-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f3b66-108">Accédez à **Administration d'organisation > Espaces de travail > États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="f3b66-109">Cliquez sur **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="f3b66-110">Dans l'arborescence, sélectionnez **Paiements (modèle simplifié)**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="f3b66-111">Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f3b66-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="f3b66-112">Si vous ne voyez pas **Créer la configuration**, vous devez activer le mode Configuration de la page **Paramètres de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="f3b66-113">Dans le champ **Nouveau**, entrez **Format basé sur le PaymentModel du modèle du paiement**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="f3b66-114">Dans le champ **Nom**, tapez **LE SYSTÈME BACS (R-U factice)**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="f3b66-115">Dans le champ **Description**, entrez **Format de paiement fournisseur du SYSTÈME BACS (R-U factice)**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="f3b66-116">Le fournisseur de configuration actif est automatiquement entré ici.</span><span class="sxs-lookup"><span data-stu-id="f3b66-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f3b66-117">Ce fournisseur pourra mettre à jour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="f3b66-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f3b66-118">D'autres fournisseurs peuvent utiliser cette configuration, mais ne peuvent pas la mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f3b66-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f3b66-119">Un format spécifique de document électronique peut être défini.</span><span class="sxs-lookup"><span data-stu-id="f3b66-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f3b66-120">Laissez ce champ vide si vous souhaitez sélectionner un format au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f3b66-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f3b66-121">Dans le champ **Définition du modèle de données**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f3b66-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="f3b66-122">Cliquez sur **Créer une configuration**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-122">Click **Create configuration**.</span></span> <span data-ttu-id="f3b66-123">Une nouvelle configuration client a été créée.</span><span class="sxs-lookup"><span data-stu-id="f3b66-123">A new configuration has been created.</span></span> <span data-ttu-id="f3b66-124">La version temporaire peut servir à enregistrer le format de conception pour gérer des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="f3b66-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="f3b66-125">Créer le format d'un document électronique</span><span class="sxs-lookup"><span data-stu-id="f3b66-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="f3b66-126">Cliquez sur **Concepteur**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-126">Click **Designer**.</span></span>
2. <span data-ttu-id="f3b66-127">Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f3b66-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="f3b66-128">Dans l'arborescence, sélectionnez **Common\File**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="f3b66-129">Dans le champ **Nom**, tapez **Xml**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="f3b66-130">Dans le champ **Encodage**, tapez **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="f3b66-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-131">Click **OK**.</span></span>
7. <span data-ttu-id="f3b66-132">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-132">Click **Add**.</span></span>
8. <span data-ttu-id="f3b66-133">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="f3b66-134">Dans le champ **Nom**, tapez **Message**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="f3b66-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-135">Click **OK**.</span></span>
11. <span data-ttu-id="f3b66-136">Dans l'arborescence, sélectionnez **Xml\Message**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="f3b66-137">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="f3b66-138">Dans le champ **Nom**, tapez **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="f3b66-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-139">Click **OK**.</span></span>
15. <span data-ttu-id="f3b66-140">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="f3b66-141">Dans le champ Nom, tapez **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="f3b66-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-142">Click **OK**.</span></span>
18. <span data-ttu-id="f3b66-143">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="f3b66-144">Dans le champ **Nom**, tapez **Paiements**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="f3b66-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-145">Click **OK**.</span></span>
21. <span data-ttu-id="f3b66-146">Dans l'arborescence, sélectionnez **Xml\Message\Paiements**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="f3b66-147">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="f3b66-148">Dans le champ **Nom**, tapez **Article**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="f3b66-149">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-149">Click **OK**.</span></span>
25. <span data-ttu-id="f3b66-150">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="f3b66-151">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-151">Click **Add**.</span></span>
27. <span data-ttu-id="f3b66-152">Dans l'arborescence, sélectionnez **XML\Attribut**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="f3b66-153">Dans le champ Nom, tapez **Id**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="f3b66-154">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-154">Click **OK**.</span></span>
30. <span data-ttu-id="f3b66-155">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-155">Click **Add**.</span></span>
31. <span data-ttu-id="f3b66-156">Dans l'arborescence, sélectionnez **XML\Élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="f3b66-157">Dans le champ Nom, tapez **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="f3b66-158">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-158">Click **OK**.</span></span>
34. <span data-ttu-id="f3b66-159">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="f3b66-160">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="f3b66-161">Dans le champ Nom, tapez **Nom**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="f3b66-162">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-162">Click **OK**.</span></span>
38. <span data-ttu-id="f3b66-163">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="f3b66-164">Dans le champ **Nom**, tapez **Banque**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="f3b66-165">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-165">Click **OK**.</span></span>
41. <span data-ttu-id="f3b66-166">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="f3b66-167">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="f3b66-168">Dans le champ **Nom**, tapez **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="f3b66-169">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-169">Click **OK**.</span></span>
45. <span data-ttu-id="f3b66-170">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="f3b66-171">Dans le champ **Nom**, tapez **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="f3b66-172">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-172">Click **OK**.</span></span>
48. <span data-ttu-id="f3b66-173">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="f3b66-174">Cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-174">Click **Copy**.</span></span>
50. <span data-ttu-id="f3b66-175">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="f3b66-176">Cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-176">Click **Paste**.</span></span>
52. <span data-ttu-id="f3b66-177">Dans le champ **Nom**, tapez **Payeur**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="f3b66-178">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="f3b66-179">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="f3b66-180">Dans le champ **Nom**, tapez **Devise**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="f3b66-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-181">Click **OK**.</span></span>
57. <span data-ttu-id="f3b66-182">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="f3b66-183">Dans le champ **Nom**, tapez **Description**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="f3b66-184">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-184">Click **OK**.</span></span>
60. <span data-ttu-id="f3b66-185">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="f3b66-186">Dans le champ Nom, tapez **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="f3b66-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-187">Click **OK**.</span></span>
63. <span data-ttu-id="f3b66-188">Cliquez sur **Ajouter un élément**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="f3b66-189">Dans le champ Nom, tapez **Montant**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="f3b66-190">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f3b66-191">Préparer des composants de format pour la mise en correspondance aux éléments de modèle de données</span><span class="sxs-lookup"><span data-stu-id="f3b66-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f3b66-192">Dans l'arborescence, sélectionnez **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="f3b66-193">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f3b66-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="f3b66-194">Dans l'arborescence, sélectionnez **Texte\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="f3b66-195">Dans le champ **Format**, tapez **jj-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="f3b66-196">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-196">Click **OK**.</span></span>
6. <span data-ttu-id="f3b66-197">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="f3b66-198">Cliquez sur **Ajouter DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="f3b66-199">Dans le champ **Format**, tapez **jj-MM-aaaa**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="f3b66-200">Dans le champ de type **DateTime**, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="f3b66-201">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-201">Click **OK**.</span></span>
11. <span data-ttu-id="f3b66-202">Dans l'arborescence, sélectionnez **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="f3b66-203">Cliquez sur **Ajouter** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f3b66-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="f3b66-204">Dans l'arborescence, sélectionnez **Texte\Chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="f3b66-205">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-205">Click **OK**.</span></span>
15. <span data-ttu-id="f3b66-206">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Nom**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="f3b66-207">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-207">Click **Add String**.</span></span>
17. <span data-ttu-id="f3b66-208">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-208">Click **OK**.</span></span>
18. <span data-ttu-id="f3b66-209">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="f3b66-210">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-210">Click **Add String**.</span></span>
20. <span data-ttu-id="f3b66-211">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-211">Click **OK**.</span></span>
21. <span data-ttu-id="f3b66-212">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Fournisseur\Banque\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="f3b66-213">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-213">Click **Add String**.</span></span>
23. <span data-ttu-id="f3b66-214">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-214">Click **OK**.</span></span>
24. <span data-ttu-id="f3b66-215">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Nom**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="f3b66-216">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-216">Click **Add String**.</span></span>
26. <span data-ttu-id="f3b66-217">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-217">Click **OK**.</span></span>
27. <span data-ttu-id="f3b66-218">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="f3b66-219">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-219">Click **Add String**.</span></span>
29. <span data-ttu-id="f3b66-220">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-220">Click **OK**.</span></span>
30. <span data-ttu-id="f3b66-221">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Payeur\Banque\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="f3b66-222">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-222">Click **Add String**.</span></span>
32. <span data-ttu-id="f3b66-223">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-223">Click **OK**.</span></span>
33. <span data-ttu-id="f3b66-224">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Devise**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="f3b66-225">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-225">Click **Add String**.</span></span>
35. <span data-ttu-id="f3b66-226">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-226">Click **OK**.</span></span>
36. <span data-ttu-id="f3b66-227">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Description**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="f3b66-228">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-228">Click **Add String**.</span></span>
38. <span data-ttu-id="f3b66-229">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-229">Click **OK**.</span></span>
39. <span data-ttu-id="f3b66-230">Dans l'arborescence, sélectionnez **Xml\Message\Paiements\Article\Montant**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="f3b66-231">Cliquez sur **Ajouter une chaîne**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-231">Click **Add String**.</span></span>
41. <span data-ttu-id="f3b66-232">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-232">Click **OK**.</span></span>
42. <span data-ttu-id="f3b66-233">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f3b66-233">Click **Save**.</span></span>
43. <span data-ttu-id="f3b66-234">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f3b66-234">Close the page.</span></span>

