---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 - Créer un format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents dans la sortie ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 618fabc96bdfeb0c2b577aa686702d9f1257ed70
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550715"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="d506c-103">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 - Créer un format)</span><span class="sxs-lookup"><span data-stu-id="d506c-103">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d506c-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="d506c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="d506c-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="d506c-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="d506c-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 : Étendre le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="d506c-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d506c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="d506c-108">Créer un format pour traiter les factures</span><span class="sxs-lookup"><span data-stu-id="d506c-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="d506c-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="d506c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d506c-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="d506c-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="d506c-111">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="d506c-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="d506c-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="d506c-113">Vous créerez un format pour générer des messageries électroniques contenant des informations sur les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="d506c-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="d506c-114">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="d506c-115">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de facture client(personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="d506c-116">Dans le champ Nom, tapez « Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="d506c-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="d506c-117">Exemple de message de facture électronique</span><span class="sxs-lookup"><span data-stu-id="d506c-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="d506c-118">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d506c-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="d506c-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="d506c-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="d506c-120">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="d506c-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="d506c-121">Créer un format pour compléter les pièces jointes en générant un message au format MIME</span><span class="sxs-lookup"><span data-stu-id="d506c-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="d506c-122">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="d506c-122">Click Designer.</span></span>
2. <span data-ttu-id="d506c-123">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="d506c-124">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="d506c-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="d506c-125">Dans le champ Nom, tapez « Facture ».</span><span class="sxs-lookup"><span data-stu-id="d506c-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="d506c-126">Facture</span><span class="sxs-lookup"><span data-stu-id="d506c-126">Invoice</span></span>  
5. <span data-ttu-id="d506c-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-127">Click OK.</span></span>
6. <span data-ttu-id="d506c-128">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="d506c-129">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="d506c-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="d506c-130">Dans le champ Nom, tapez « SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="d506c-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="d506c-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="d506c-131">SalesOrder</span></span>  
9. <span data-ttu-id="d506c-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-132">Click OK.</span></span>
10. <span data-ttu-id="d506c-133">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="d506c-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="d506c-134">Dans le champ Nom, tapez « InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="d506c-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="d506c-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="d506c-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="d506c-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-136">Click OK.</span></span>
13. <span data-ttu-id="d506c-137">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="d506c-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="d506c-138">Dans le champ Nom, tapez « InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="d506c-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="d506c-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="d506c-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="d506c-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-140">Click OK.</span></span>
16. <span data-ttu-id="d506c-141">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="d506c-142">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="d506c-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="d506c-143">Dans le champ Nom, tapez « EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="d506c-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="d506c-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="d506c-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="d506c-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-145">Click OK.</span></span>
20. <span data-ttu-id="d506c-146">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="d506c-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="d506c-147">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="d506c-147">Click Add Element.</span></span>
22. <span data-ttu-id="d506c-148">Dans le champ Nom, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="d506c-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="d506c-149">Document</span><span class="sxs-lookup"><span data-stu-id="d506c-149">Document</span></span>  
23. <span data-ttu-id="d506c-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-150">Click OK.</span></span>
24. <span data-ttu-id="d506c-151">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="d506c-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="d506c-152">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="d506c-153">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="d506c-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="d506c-154">Dans le champ Nom, tapez « FileName ».</span><span class="sxs-lookup"><span data-stu-id="d506c-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="d506c-155">FileName</span><span class="sxs-lookup"><span data-stu-id="d506c-155">FileName</span></span>  
28. <span data-ttu-id="d506c-156">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-156">Click OK.</span></span>
29. <span data-ttu-id="d506c-157">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="d506c-158">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="d506c-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="d506c-159">Dans le champ Nom, tapez « FileContent ».</span><span class="sxs-lookup"><span data-stu-id="d506c-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="d506c-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="d506c-160">FileContent</span></span>  
32. <span data-ttu-id="d506c-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-161">Click OK.</span></span>
33. <span data-ttu-id="d506c-162">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent ».</span><span class="sxs-lookup"><span data-stu-id="d506c-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="d506c-163">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d506c-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="d506c-164">Dans l'arborescence, sélectionnez « Texte\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="d506c-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="d506c-165">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d506c-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="d506c-166">Mettre en correspondance les éléments de format avec le modèle de données en tant que source de données</span><span class="sxs-lookup"><span data-stu-id="d506c-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="d506c-167">Dans l'arborescence, sélectionnez « Facture\SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="d506c-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="d506c-168">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="d506c-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="d506c-169">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="d506c-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="d506c-170">Dans l'arborescence, sélectionnez « Modèle\Numéro de commande client (SalesId) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="d506c-171">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-171">Click Bind.</span></span>
6. <span data-ttu-id="d506c-172">Dans l'arborescence, sélectionnez « Facture\InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="d506c-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="d506c-173">Dans l'arborescence, développez « Modèle\Facture de base (InvoiceBase) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="d506c-174">Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Numéro de facture (Id) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="d506c-175">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-175">Click Bind.</span></span>
10. <span data-ttu-id="d506c-176">Dans l'arborescence, sélectionnez « Facture\InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="d506c-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="d506c-177">Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Montant de la facture (Amount) ».</span><span class="sxs-lookup"><span data-stu-id="d506c-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="d506c-178">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-178">Click Bind.</span></span>
13. <span data-ttu-id="d506c-179">Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="d506c-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="d506c-180">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="d506c-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="d506c-181">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="d506c-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="d506c-182">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-182">Click Bind.</span></span>
17. <span data-ttu-id="d506c-183">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="d506c-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="d506c-184">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileName ».</span><span class="sxs-lookup"><span data-stu-id="d506c-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="d506c-185">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-185">Click Bind.</span></span>
20. <span data-ttu-id="d506c-186">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="d506c-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="d506c-187">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="d506c-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="d506c-188">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="d506c-188">Click Bind.</span></span>
23. <span data-ttu-id="d506c-189">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="d506c-189">Click Save.</span></span>
24. <span data-ttu-id="d506c-190">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="d506c-190">Close the page.</span></span>

