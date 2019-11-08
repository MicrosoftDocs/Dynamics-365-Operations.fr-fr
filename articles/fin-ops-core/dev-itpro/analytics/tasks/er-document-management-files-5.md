---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 - Modifier et exécuter le format)
description: Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de075899547d194fb9eb0e68947efd005c101851
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550692"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="26d3f-103">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 - Modifier et exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="26d3f-103">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26d3f-104">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d'administrateur système ou de développeur d'états électroniques peut configurer un format de génération d'états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="26d3f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="26d3f-105">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="26d3f-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="26d3f-106">Pour effectuer ces étapes, vous devez d'abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 : Exécuter le format) ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4: Run format)” procedure.</span></span>

<span data-ttu-id="26d3f-107">Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="26d3f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="26d3f-108">Modifier le format pour compléter les pièces jointes en générant des messages au format binaire</span><span class="sxs-lookup"><span data-stu-id="26d3f-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="26d3f-109">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="26d3f-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="26d3f-110">Dans l'arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="26d3f-111">Dans l'arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="26d3f-112">Dans l'arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="26d3f-113">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="26d3f-113">Click Designer.</span></span>
    * <span data-ttu-id="26d3f-114">Vous complétez le message de la facture dans la sortie de génération en tant que fichier XML à l'aide du codage UNICODE.</span><span class="sxs-lookup"><span data-stu-id="26d3f-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="26d3f-115">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26d3f-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="26d3f-116">Dans l'arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="26d3f-117">Dans le champ Nom, tapez « Message Xml ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="26d3f-118">Message Xml</span><span class="sxs-lookup"><span data-stu-id="26d3f-118">Xml message</span></span>  
9. <span data-ttu-id="26d3f-119">Dans le champ Encodage, tapez « UTF-8 ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="26d3f-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="26d3f-120">UTF-8</span></span>  
10. <span data-ttu-id="26d3f-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-121">Click OK.</span></span>
    * <span data-ttu-id="26d3f-122">Configurez la sortie de génération en tant que fichier compressé.</span><span class="sxs-lookup"><span data-stu-id="26d3f-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="26d3f-123">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26d3f-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="26d3f-124">Dans l'arborescence, sélectionnez « Commun\Dossier ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="26d3f-125">Dans le champ Nom, tapez « Compresser la sortie ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="26d3f-126">Compresser la sortie</span><span class="sxs-lookup"><span data-stu-id="26d3f-126">Zip output</span></span>  
14. <span data-ttu-id="26d3f-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-127">Click OK.</span></span>
15. <span data-ttu-id="26d3f-128">Dans l'arborescence, sélectionnez « Compresser la sortie ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="26d3f-129">Ajoutez les pièces jointes au fichier compressé en tant que fichiers avec les noms et les extensions d'origine.</span><span class="sxs-lookup"><span data-stu-id="26d3f-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="26d3f-130">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26d3f-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="26d3f-131">Dans l'arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="26d3f-132">Dans le champ Nom, tapez « Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="26d3f-133">Fichier joint</span><span class="sxs-lookup"><span data-stu-id="26d3f-133">Attached file</span></span>  
19. <span data-ttu-id="26d3f-134">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-134">Click OK.</span></span>
20. <span data-ttu-id="26d3f-135">Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="26d3f-136">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="26d3f-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="26d3f-137">Dans l'arborescence, sélectionnez « Texte\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="26d3f-138">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="26d3f-139">Mettre en correspondance les nouveaux éléments de format avec le modèle de données</span><span class="sxs-lookup"><span data-stu-id="26d3f-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="26d3f-140">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="26d3f-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="26d3f-141">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="26d3f-142">Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="26d3f-143">Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="26d3f-144">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="26d3f-145">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="26d3f-145">Click Bind.</span></span>
7. <span data-ttu-id="26d3f-146">Dans l'arborescence, sélectionnez « Compresser la sortie\Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="26d3f-147">Cliquez sur Modifier le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="26d3f-147">Click Edit filename.</span></span>
9. <span data-ttu-id="26d3f-148">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="26d3f-149">Dans l'arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="26d3f-150">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="26d3f-151">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="26d3f-151">Click Add data source.</span></span>
13. <span data-ttu-id="26d3f-152">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="26d3f-152">Click Save.</span></span>
14. <span data-ttu-id="26d3f-153">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="26d3f-153">Close the page.</span></span>
15. <span data-ttu-id="26d3f-154">Dans l'arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="26d3f-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="26d3f-155">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="26d3f-155">Click Bind.</span></span>
17. <span data-ttu-id="26d3f-156">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="26d3f-156">Click Save.</span></span>
18. <span data-ttu-id="26d3f-157">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="26d3f-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="26d3f-158">Exécuter l'état désigné pour la facture sélectionnée</span><span class="sxs-lookup"><span data-stu-id="26d3f-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="26d3f-159">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="26d3f-159">Click Run.</span></span>
2. <span data-ttu-id="26d3f-160">Développez la section Enregistrements à inclure ().</span><span class="sxs-lookup"><span data-stu-id="26d3f-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="26d3f-161">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="26d3f-161">Click Filter.</span></span>
4. <span data-ttu-id="26d3f-162">Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="26d3f-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="26d3f-163">Dans le champ Critères, dans le champ « Commande client », tapez le numéro de commande 000148.</span><span class="sxs-lookup"><span data-stu-id="26d3f-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="26d3f-164">000148</span><span class="sxs-lookup"><span data-stu-id="26d3f-164">000148</span></span>  
6. <span data-ttu-id="26d3f-165">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-165">Click OK.</span></span>
7. <span data-ttu-id="26d3f-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="26d3f-166">Click OK.</span></span>
    * <span data-ttu-id="26d3f-167">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="26d3f-167">Review the generated output.</span></span> <span data-ttu-id="26d3f-168">Notez qu'en plus du message de la facture au format XML, un fichier unique a été créé pour chaque pièce jointe.</span><span class="sxs-lookup"><span data-stu-id="26d3f-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="26d3f-169">Les fichiers joints sont renseignés avec la sortie compressée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="26d3f-169">The attachment files are populated with the zipped output in binary format.</span></span>  

