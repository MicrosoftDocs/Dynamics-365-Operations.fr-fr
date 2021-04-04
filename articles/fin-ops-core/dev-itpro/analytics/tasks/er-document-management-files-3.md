---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 - Créer un format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques. (Partie 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1ebc15cd980734aebec63d6758404868c1e36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559747"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="aaf40-104">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 3 - Créer un format)</span><span class="sxs-lookup"><span data-stu-id="aaf40-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aaf40-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="aaf40-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="aaf40-106">Ces étapes peuvent être effectuées dans n’importe quelle société.</span><span class="sxs-lookup"><span data-stu-id="aaf40-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="aaf40-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 2 : Étendre le modèle de données) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="aaf40-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="aaf40-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="aaf40-109">Créer un format pour traiter les factures</span><span class="sxs-lookup"><span data-stu-id="aaf40-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="aaf40-110">Accédez à Administration d’organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="aaf40-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="aaf40-111">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="aaf40-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="aaf40-112">Dans l’arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="aaf40-113">Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="aaf40-114">Vous créerez un format pour générer des messageries électroniques contenant des informations sur les fichiers joints à une commande client associée à une facture à traitement électronique.</span><span class="sxs-lookup"><span data-stu-id="aaf40-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="aaf40-115">Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="aaf40-116">Dans le champ Nouveau, entrez « Format basé sur le modèle de données Modèle de facture client(personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="aaf40-117">Dans le champ Nom, tapez « Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="aaf40-118">Exemple de message de facture électronique</span><span class="sxs-lookup"><span data-stu-id="aaf40-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="aaf40-119">Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="aaf40-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="aaf40-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="aaf40-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="aaf40-121">Cliquez sur Créer une configuration.</span><span class="sxs-lookup"><span data-stu-id="aaf40-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="aaf40-122">Créer un format pour compléter les pièces jointes en générant un message au format MIME</span><span class="sxs-lookup"><span data-stu-id="aaf40-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="aaf40-123">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="aaf40-123">Click Designer.</span></span>
2. <span data-ttu-id="aaf40-124">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="aaf40-125">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="aaf40-126">Dans le champ Nom, tapez « Facture ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="aaf40-127">Facture</span><span class="sxs-lookup"><span data-stu-id="aaf40-127">Invoice</span></span>  
5. <span data-ttu-id="aaf40-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-128">Click OK.</span></span>
6. <span data-ttu-id="aaf40-129">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="aaf40-130">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="aaf40-131">Dans le champ Nom, tapez « SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="aaf40-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="aaf40-132">SalesOrder</span></span>  
9. <span data-ttu-id="aaf40-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-133">Click OK.</span></span>
10. <span data-ttu-id="aaf40-134">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="aaf40-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="aaf40-135">Dans le champ Nom, tapez « InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="aaf40-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="aaf40-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="aaf40-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-137">Click OK.</span></span>
13. <span data-ttu-id="aaf40-138">Cliquez sur Ajouter un attribut.</span><span class="sxs-lookup"><span data-stu-id="aaf40-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="aaf40-139">Dans le champ Nom, tapez « InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="aaf40-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="aaf40-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="aaf40-141">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-141">Click OK.</span></span>
16. <span data-ttu-id="aaf40-142">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="aaf40-143">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="aaf40-144">Dans le champ Nom, tapez « EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="aaf40-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="aaf40-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="aaf40-146">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-146">Click OK.</span></span>
20. <span data-ttu-id="aaf40-147">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="aaf40-148">Cliquez sur Ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="aaf40-148">Click Add Element.</span></span>
22. <span data-ttu-id="aaf40-149">Dans le champ Nom, tapez « Document ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="aaf40-150">Document</span><span class="sxs-lookup"><span data-stu-id="aaf40-150">Document</span></span>  
23. <span data-ttu-id="aaf40-151">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-151">Click OK.</span></span>
24. <span data-ttu-id="aaf40-152">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="aaf40-153">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="aaf40-154">Dans l’arborescence, sélectionnez « XML\Attribut ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="aaf40-155">Dans le champ Nom, tapez « FileName ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="aaf40-156">FileName</span><span class="sxs-lookup"><span data-stu-id="aaf40-156">FileName</span></span>  
28. <span data-ttu-id="aaf40-157">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-157">Click OK.</span></span>
29. <span data-ttu-id="aaf40-158">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="aaf40-159">Dans l’arborescence , sélectionnez « XML\Élément ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="aaf40-160">Dans le champ Nom, tapez « FileContent ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="aaf40-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="aaf40-161">FileContent</span></span>  
32. <span data-ttu-id="aaf40-162">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-162">Click OK.</span></span>
33. <span data-ttu-id="aaf40-163">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="aaf40-164">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="aaf40-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="aaf40-165">Dans l’arborescence, sélectionnez « Texte\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="aaf40-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aaf40-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="aaf40-167">Mettre en correspondance les éléments de format avec le modèle de données en tant que source de données</span><span class="sxs-lookup"><span data-stu-id="aaf40-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="aaf40-168">Dans l’arborescence, sélectionnez « Facture\SalesOrder ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="aaf40-169">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="aaf40-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="aaf40-170">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="aaf40-171">Dans l’arborescence, sélectionnez « Modèle\Numéro de commande client (SalesId) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="aaf40-172">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-172">Click Bind.</span></span>
6. <span data-ttu-id="aaf40-173">Dans l’arborescence, sélectionnez « Facture\InvoiceNumber ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="aaf40-174">Dans l’arborescence, développez « Modèle\Facture de base (InvoiceBase) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="aaf40-175">Dans l’arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Numéro de facture (Id) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="aaf40-176">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-176">Click Bind.</span></span>
10. <span data-ttu-id="aaf40-177">Dans l’arborescence, sélectionnez « Facture\InvoiceAmount ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="aaf40-178">Dans l’arborescence, sélectionnez « Modèle\Facture de base (InvoiceBase)\Montant de la facture (Amount) ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="aaf40-179">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-179">Click Bind.</span></span>
13. <span data-ttu-id="aaf40-180">Dans l’arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="aaf40-181">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="aaf40-182">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileContent\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="aaf40-183">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-183">Click Bind.</span></span>
17. <span data-ttu-id="aaf40-184">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="aaf40-185">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs\Document\FileName ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="aaf40-186">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-186">Click Bind.</span></span>
20. <span data-ttu-id="aaf40-187">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="aaf40-188">Dans l’arborescence, sélectionnez « Facture\EnclosedDocs\Document ».</span><span class="sxs-lookup"><span data-stu-id="aaf40-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="aaf40-189">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="aaf40-189">Click Bind.</span></span>
23. <span data-ttu-id="aaf40-190">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="aaf40-190">Click Save.</span></span>
24. <span data-ttu-id="aaf40-191">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="aaf40-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]