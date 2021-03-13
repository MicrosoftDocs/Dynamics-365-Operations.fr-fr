---
title: ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 - Modifier et exécuter le format)
description: Cette rubrique décrit comment configurer un format de gestion des états électroniques pour utiliser les fichiers de gestion des documents dans la sortie de gestion des états électroniques (pièces jointes). (Partie 5)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f96189163d5ecac47ade9f713b3fd689e41352d0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092486"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="68ce1-104">ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 5 - Modifier et exécuter le format)</span><span class="sxs-lookup"><span data-stu-id="68ce1-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="68ce1-105">Les étapes suivantes expliquent comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut configurer un format de génération d’états électroniques pour utiliser les fichiers de gestion des documents (pièces jointes) dans la sortie ER.</span><span class="sxs-lookup"><span data-stu-id="68ce1-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="68ce1-106">Ces étapes peuvent être effectuées dans la société DEMF.</span><span class="sxs-lookup"><span data-stu-id="68ce1-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="68ce1-107">Pour effectuer ces étapes, vous devez d’abord effectuer les étapes de la procédure « ER Utiliser les fichiers de gestion des documents dans les sorties de format (Partie 4 : Exécuter le format) ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="68ce1-108">Cette procédure s’applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="68ce1-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="68ce1-109">Modifier le format pour compléter les pièces jointes en générant des messages au format binaire</span><span class="sxs-lookup"><span data-stu-id="68ce1-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="68ce1-110">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="68ce1-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="68ce1-111">Dans l’arborescence, développez « Modèle de facture client ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="68ce1-112">Dans l’arborescence, développez « Modèle de facture client\Modèle de facture client (personnalisé) ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="68ce1-113">Dans l’arborescence, sélectionnez « Modèle de facture client\Modèle de facture client (personnalisé)\Exemple de message de facture électronique ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="68ce1-114">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="68ce1-114">Click Designer.</span></span>
    * <span data-ttu-id="68ce1-115">Vous complétez le message de la facture dans la sortie de génération en tant que fichier XML à l’aide du codage UNICODE.</span><span class="sxs-lookup"><span data-stu-id="68ce1-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="68ce1-116">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="68ce1-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="68ce1-117">Dans l’arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="68ce1-118">Dans le champ Nom, tapez « Message Xml ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="68ce1-119">Message Xml</span><span class="sxs-lookup"><span data-stu-id="68ce1-119">Xml message</span></span>  
9. <span data-ttu-id="68ce1-120">Dans le champ Encodage, tapez « UTF-8 ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="68ce1-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="68ce1-121">UTF-8</span></span>  
10. <span data-ttu-id="68ce1-122">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-122">Click OK.</span></span>
    * <span data-ttu-id="68ce1-123">Configurez la sortie de génération en tant que fichier compressé.</span><span class="sxs-lookup"><span data-stu-id="68ce1-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="68ce1-124">Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="68ce1-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="68ce1-125">Dans l’arborescence, sélectionnez « Commun\Dossier ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="68ce1-126">Dans le champ Nom, tapez « Compresser la sortie ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="68ce1-127">Compresser la sortie</span><span class="sxs-lookup"><span data-stu-id="68ce1-127">Zip output</span></span>  
14. <span data-ttu-id="68ce1-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-128">Click OK.</span></span>
15. <span data-ttu-id="68ce1-129">Dans l’arborescence, sélectionnez « Compresser la sortie ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="68ce1-130">Ajoutez les pièces jointes au fichier compressé en tant que fichiers avec les noms et les extensions d’origine.</span><span class="sxs-lookup"><span data-stu-id="68ce1-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="68ce1-131">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="68ce1-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="68ce1-132">Dans l’arborescence, sélectionnez « Common\File ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="68ce1-133">Dans le champ Nom, tapez « Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="68ce1-134">Fichier joint</span><span class="sxs-lookup"><span data-stu-id="68ce1-134">Attached file</span></span>  
19. <span data-ttu-id="68ce1-135">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-135">Click OK.</span></span>
20. <span data-ttu-id="68ce1-136">Dans l’arborescence, sélectionnez « Compresser la sortie\Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="68ce1-137">Cliquez sur Ajouter pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="68ce1-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="68ce1-138">Dans l’arborescence, sélectionnez « Texte\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="68ce1-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="68ce1-140">Mettre en correspondance les nouveaux éléments de format avec le modèle de données</span><span class="sxs-lookup"><span data-stu-id="68ce1-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="68ce1-141">Cliquez sur l’onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="68ce1-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="68ce1-142">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="68ce1-143">Dans l’arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="68ce1-144">Dans l’arborescence, sélectionnez « Compresser la sortie\Fichier joint\Base64 ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="68ce1-145">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Contenu du fichier ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="68ce1-146">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="68ce1-146">Click Bind.</span></span>
7. <span data-ttu-id="68ce1-147">Dans l’arborescence, sélectionnez « Compresser la sortie\Fichier joint ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="68ce1-148">Cliquez sur Modifier le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="68ce1-148">Click Edit filename.</span></span>
9. <span data-ttu-id="68ce1-149">Dans l’arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="68ce1-150">Dans l’arborescence, développez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="68ce1-151">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture\Nom de fichier ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="68ce1-152">Cliquez sur Ajouter une source de données.</span><span class="sxs-lookup"><span data-stu-id="68ce1-152">Click Add data source.</span></span>
13. <span data-ttu-id="68ce1-153">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68ce1-153">Click Save.</span></span>
14. <span data-ttu-id="68ce1-154">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68ce1-154">Close the page.</span></span>
15. <span data-ttu-id="68ce1-155">Dans l’arborescence, sélectionnez « Modèle\Pièces jointes à la facture ».</span><span class="sxs-lookup"><span data-stu-id="68ce1-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="68ce1-156">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="68ce1-156">Click Bind.</span></span>
17. <span data-ttu-id="68ce1-157">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="68ce1-157">Click Save.</span></span>
18. <span data-ttu-id="68ce1-158">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="68ce1-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="68ce1-159">Exécuter l’état désigné pour la facture sélectionnée</span><span class="sxs-lookup"><span data-stu-id="68ce1-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="68ce1-160">Cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="68ce1-160">Click Run.</span></span>
2. <span data-ttu-id="68ce1-161">Développez la section Enregistrements à inclure ().</span><span class="sxs-lookup"><span data-stu-id="68ce1-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="68ce1-162">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="68ce1-162">Click Filter.</span></span>
4. <span data-ttu-id="68ce1-163">Sélectionnez la ligne de la table Journal des factures client et du champ Commande client.</span><span class="sxs-lookup"><span data-stu-id="68ce1-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="68ce1-164">Dans le champ Critères, dans le champ « Commande client », tapez le numéro de commande 000148.</span><span class="sxs-lookup"><span data-stu-id="68ce1-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="68ce1-165">000148</span><span class="sxs-lookup"><span data-stu-id="68ce1-165">000148</span></span>  
6. <span data-ttu-id="68ce1-166">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-166">Click OK.</span></span>
7. <span data-ttu-id="68ce1-167">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="68ce1-167">Click OK.</span></span>
    * <span data-ttu-id="68ce1-168">Examinez la sortie générée.</span><span class="sxs-lookup"><span data-stu-id="68ce1-168">Review the generated output.</span></span> <span data-ttu-id="68ce1-169">Notez qu’en plus du message de la facture au format XML, un fichier unique a été créé pour chaque pièce jointe.</span><span class="sxs-lookup"><span data-stu-id="68ce1-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="68ce1-170">Les fichiers joints sont renseignés avec la sortie compressée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="68ce1-170">The attachment files are populated with the zipped output in binary format.</span></span>  

