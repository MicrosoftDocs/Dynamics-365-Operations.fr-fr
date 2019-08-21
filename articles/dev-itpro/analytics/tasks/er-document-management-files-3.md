---
title: Créer des formats pour utiliser les fichiers de gestion des documents dans la sortie ER
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
ms.openlocfilehash: 05c0c4a38f34774e7018504c5e3fab834a2ec1b1
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850277"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3-create-format"></a><span data-ttu-id="a0139-103">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 : Créer un format)</span><span class="sxs-lookup"><span data-stu-id="a0139-103">ER Use Document Management files in format outputs (Part 3: Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0139-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="a0139-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="a0139-105">Ces étapes peuvent être effectuées dans n'importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="a0139-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="a0139-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 : Étendre le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="a0139-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="a0139-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="a0139-108">Créer un format pour traiter les factures</span><span class="sxs-lookup"><span data-stu-id="a0139-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="a0139-109">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="a0139-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="a0139-110">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="a0139-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="a0139-111">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="a0139-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="a0139-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="a0139-113">Vous créerez un format pour générer des messageries électroniques contenant des informations sur les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="a0139-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="a0139-114">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="a0139-115">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de facture client(personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="a0139-116">Dans le champ Nom, tapez « Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="a0139-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="a0139-117">Exemple de message de facture électronique</span><span class="sxs-lookup"><span data-stu-id="a0139-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="a0139-118">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="a0139-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="a0139-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="a0139-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="a0139-120">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="a0139-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="a0139-121">Créer un format pour compléter les pièces jointes en générant un message au format MIME</span><span class="sxs-lookup"><span data-stu-id="a0139-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="a0139-122">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="a0139-122">Click Designer.</span></span>
2. <span data-ttu-id="a0139-123">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="a0139-124">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="a0139-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="a0139-125">Dans le champ Nom, tapez « Facture ».</span><span class="sxs-lookup"><span data-stu-id="a0139-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="a0139-126">Facture</span><span class="sxs-lookup"><span data-stu-id="a0139-126">Invoice</span></span>  
5. <span data-ttu-id="a0139-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-127">Click OK.</span></span>
6. <span data-ttu-id="a0139-128">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="a0139-129">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="a0139-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="a0139-130">Dans le champ Nom, tapez « SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="a0139-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="a0139-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="a0139-131">SalesOrder</span></span>  
9. <span data-ttu-id="a0139-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-132">Click OK.</span></span>
10. <span data-ttu-id="a0139-133">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="a0139-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="a0139-134">Dans le champ Nom, tapez « InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="a0139-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="a0139-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="a0139-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="a0139-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-136">Click OK.</span></span>
13. <span data-ttu-id="a0139-137">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="a0139-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="a0139-138">Dans le champ Nom, tapez « InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="a0139-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="a0139-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="a0139-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="a0139-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-140">Click OK.</span></span>
16. <span data-ttu-id="a0139-141">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="a0139-142">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="a0139-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="a0139-143">Dans le champ Nom, tapez « EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="a0139-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="a0139-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="a0139-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="a0139-145">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-145">Click OK.</span></span>
20. <span data-ttu-id="a0139-146">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="a0139-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="a0139-147">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="a0139-147">Click Add Element.</span></span>
22. <span data-ttu-id="a0139-148">Dans le champ Nom, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="a0139-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="a0139-149">Document</span><span class="sxs-lookup"><span data-stu-id="a0139-149">Document</span></span>  
23. <span data-ttu-id="a0139-150">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-150">Click OK.</span></span>
24. <span data-ttu-id="a0139-151">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="a0139-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="a0139-152">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="a0139-153">Dans l'arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="a0139-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="a0139-154">Dans le champ Nom, tapez « FileName ».</span><span class="sxs-lookup"><span data-stu-id="a0139-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="a0139-155">FileName</span><span class="sxs-lookup"><span data-stu-id="a0139-155">FileName</span></span>  
28. <span data-ttu-id="a0139-156">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-156">Click OK.</span></span>
29. <span data-ttu-id="a0139-157">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="a0139-158">Dans l'arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="a0139-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="a0139-159">Dans le champ Nom, tapez « FileContent ».</span><span class="sxs-lookup"><span data-stu-id="a0139-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="a0139-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="a0139-160">FileContent</span></span>  
32. <span data-ttu-id="a0139-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-161">Click OK.</span></span>
33. <span data-ttu-id="a0139-162">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent ».</span><span class="sxs-lookup"><span data-stu-id="a0139-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="a0139-163">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="a0139-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="a0139-164">Dans l'arborescence, sélectionnez « Texte\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="a0139-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="a0139-165">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="a0139-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="a0139-166">Mettre en correspondance les éléments de format avec le modèle de données en tant que source de données</span><span class="sxs-lookup"><span data-stu-id="a0139-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="a0139-167">Dans l'arborescence, sélectionnez « Facture\SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="a0139-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="a0139-168">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="a0139-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="a0139-169">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="a0139-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="a0139-170">Dans l'arborescence, sélectionnez « Modèle\Numéro de commande client (SalesId) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="a0139-171">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-171">Click Bind.</span></span>
6. <span data-ttu-id="a0139-172">Dans l'arborescence, sélectionnez « Facture\InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="a0139-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="a0139-173">Dans l'arborescence, développez « Modèle\Facture de base (InvoiceBase) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="a0139-174">Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Numéro de facture (Id) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="a0139-175">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-175">Click Bind.</span></span>
10. <span data-ttu-id="a0139-176">Dans l'arborescence, sélectionnez « Facture\InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="a0139-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="a0139-177">Dans l'arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Montant de la facture (Amount) ».</span><span class="sxs-lookup"><span data-stu-id="a0139-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="a0139-178">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-178">Click Bind.</span></span>
13. <span data-ttu-id="a0139-179">Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="a0139-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="a0139-180">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="a0139-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="a0139-181">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="a0139-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="a0139-182">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-182">Click Bind.</span></span>
17. <span data-ttu-id="a0139-183">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="a0139-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="a0139-184">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileName ».</span><span class="sxs-lookup"><span data-stu-id="a0139-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="a0139-185">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-185">Click Bind.</span></span>
20. <span data-ttu-id="a0139-186">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="a0139-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="a0139-187">Dans l'arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="a0139-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="a0139-188">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="a0139-188">Click Bind.</span></span>
23. <span data-ttu-id="a0139-189">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a0139-189">Click Save.</span></span>
24. <span data-ttu-id="a0139-190">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a0139-190">Close the page.</span></span>

