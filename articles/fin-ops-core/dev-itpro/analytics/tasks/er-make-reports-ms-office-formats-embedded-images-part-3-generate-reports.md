---
title: Générer des états dans des formats Office avec des images intégrées
description: Cette rubrique décrit comment créer des configurations pour la gestion des états électroniques pour générer des documents électroniques dans Excel et Word contenant des images intégrées.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e15162251e5d6fa91c5a938fd846ef5b5c8cd7f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093821"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="e1d7b-103">Générer des états dans des formats Office avec des images intégrées</span><span class="sxs-lookup"><span data-stu-id="e1d7b-103">Generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1d7b-104">Les étapes suivantes expliquent comment un utilisateur jouant le rôle de « Administrateur système » ou de « Développeur d’états électroniques » peut créer des configurations d’états électroniques (ER) pour générer des documents électroniques au format MS Office (Excel et Word) contenant des images intégrées.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-104">The following steps explain how a user playing either 'System administrator' or 'Electronic reporting developer' role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="e1d7b-105">Dans cet exemple, vous utiliserez les configurations ER créées pour la société fictive, « Litware, Inc. ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-105">In this example, you will use created ER configurations for sample company, 'Litware, Inc.'.</span></span>  <span data-ttu-id="e1d7b-106">Pour réaliser ces étapes, vous devez d’abord effectuer les étapes du guide de tâche « ER Créer des états aux formats MS Office avec des images intégrées (Partie 2 : Examiner les configurations) ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-106">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)" task guide.</span></span> <span data-ttu-id="e1d7b-107">Ces étapes peuvent être effectuées dans la société « USMF ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-107">These steps can be performed in 'USMF' company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="e1d7b-108">Exécuter le format avec la mise en correspondance initiale du modèle</span><span class="sxs-lookup"><span data-stu-id="e1d7b-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="e1d7b-109">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="e1d7b-110">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="e1d7b-111">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="e1d7b-112">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-112">Click Check.</span></span>
5. <span data-ttu-id="e1d7b-113">Cliquer sur Test d’impression.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-113">Click Print test.</span></span>
    * <span data-ttu-id="e1d7b-114">Exécutez le format à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="e1d7b-115">Sélectionnez Oui dans le champ Format de chèque négociable.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="e1d7b-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-116">Click OK.</span></span>
    * <span data-ttu-id="e1d7b-117">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-117">Review the created output.</span></span> <span data-ttu-id="e1d7b-118">Le logo de la société est présenté dans l’état ainsi que la signature de la personne autorisée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-118">The company logo is presented in the report as well as the authorized person's signature.</span></span> <span data-ttu-id="e1d7b-119">L’image de la signature est extraite du champ du type de données « Conteneur » de l’enregistrement de mise en page de chèque associé au compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-119">The signature image is taken from the field of the 'Container' data type of the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="e1d7b-120">Développez la section Copies.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="e1d7b-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-121">Click Edit.</span></span>
10. <span data-ttu-id="e1d7b-122">Dans le champ Filigrane, entrez « Imprimer le filigrane comme annulé ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="e1d7b-123">Modifiez le paramètre de mise en page du filigrane pour afficher le texte du filigrane lors de la génération du document dans un élément au format Excel.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="e1d7b-124">Cliquer sur Test d’impression.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-124">Click Print test.</span></span>
12. <span data-ttu-id="e1d7b-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-125">Click OK.</span></span>
    * <span data-ttu-id="e1d7b-126">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-126">Review the created output.</span></span> <span data-ttu-id="e1d7b-127">Le filigrane s’affiche dans l’état créé conformément à l’option de sélection.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-127">The watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="e1d7b-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-128">Close the page.</span></span>
14. <span data-ttu-id="e1d7b-129">Dans le volet Actions, cliquez sur Gérer les paiements.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="e1d7b-130">Cliquez sur Chèques.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-130">Click Checks.</span></span>
16. <span data-ttu-id="e1d7b-131">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-131">Click Show filters.</span></span>
17. <span data-ttu-id="e1d7b-132">Appliquez les filtres suivants : entrez la valeur de filtre « 381 », « 385 », « 389 » dans le champ « Numéro de chèque » en utilisant l’opérateur de filtre « est l’un de ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="e1d7b-133">Dans la liste, marquez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="e1d7b-134">Cliquez sur Imprimer une copie du chèque.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-134">Click Print check copy.</span></span>
    * <span data-ttu-id="e1d7b-135">Exécutez le format pour réimprimer les chèques sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-135">Run the format to reprint the selected cheques.</span></span>  
    * <span data-ttu-id="e1d7b-136">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-136">Review the created output.</span></span> <span data-ttu-id="e1d7b-137">Les chèques sélectionnés ont été réimprimés.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-137">The selected cheques have been reprinted.</span></span> <span data-ttu-id="e1d7b-138">Le logo et les libellés de la société ne sont pas imprimés, car ils sont présentés sur le formulaire pré-imprimé.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="e1d7b-139">Modifier la mise en correspondance du modèle de données importé</span><span class="sxs-lookup"><span data-stu-id="e1d7b-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="e1d7b-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-140">Close the page.</span></span>
2. <span data-ttu-id="e1d7b-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-141">Close the page.</span></span>
3. <span data-ttu-id="e1d7b-142">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="e1d7b-143">Dans l’arborescence, sélectionnez « Modèle pour les chèques »</span><span class="sxs-lookup"><span data-stu-id="e1d7b-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="e1d7b-144">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-144">Click Designer.</span></span>
6. <span data-ttu-id="e1d7b-145">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="e1d7b-146">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-146">Click Designer.</span></span>
    * <span data-ttu-id="e1d7b-147">Nous modifierons la liaison de l’élément de signature du modèle de données pour obtenir l’image de la signature à partir du fichier qui a été lié à l’enregistrement de mise en page de chèque associé au compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-147">We will change the binding of the data model's signature item to get the signature image from the file that has been attached to the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="e1d7b-148">Désactivez Afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-148">Turn off Show details.</span></span>
9. <span data-ttu-id="e1d7b-149">Dans l’arborescence, développez « layout ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="e1d7b-150">Dans l’arborescence, développez « layout\signature »</span><span class="sxs-lookup"><span data-stu-id="e1d7b-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="e1d7b-151">Dans l’arborescence, sélectionnez « layout\signature\image = chequesaccount.’<Relations’.BankChequeLayout.Signature1Bmp ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="e1d7b-152">Dans l’arborescence, développez « chequesaccount ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="e1d7b-153">Dans l’arborescence, développez « chequesaccount\<Relations ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="e1d7b-154">Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="e1d7b-155">Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="e1d7b-156">Dans l’arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="e1d7b-157">Dans l’arborescence, sélectionnez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer() ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="e1d7b-158">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-158">Click Bind.</span></span>
19. <span data-ttu-id="e1d7b-159">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-159">Click Save.</span></span>
20. <span data-ttu-id="e1d7b-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-160">Close the page.</span></span>
21. <span data-ttu-id="e1d7b-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-161">Close the page.</span></span>
22. <span data-ttu-id="e1d7b-162">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-162">Close the page.</span></span>
23. <span data-ttu-id="e1d7b-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="e1d7b-164">Exécuter le format avec la mise en correspondance ajustée du modèle</span><span class="sxs-lookup"><span data-stu-id="e1d7b-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="e1d7b-165">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="e1d7b-166">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e1d7b-167">Par exemple, filtrez le champ Compte bancaire avec la valeur « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="e1d7b-168">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="e1d7b-169">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-169">Click Check.</span></span>
5. <span data-ttu-id="e1d7b-170">Cliquer sur Test d’impression.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-170">Click Print test.</span></span>
6. <span data-ttu-id="e1d7b-171">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-171">Click OK.</span></span>
    * <span data-ttu-id="e1d7b-172">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-172">Review the created output.</span></span> <span data-ttu-id="e1d7b-173">L’image de la pièce jointe Gestion des documents est présentée comme la signature d’une personne autorisée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-173">The image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="e1d7b-174">Utiliser le document MS Word comme modèle dans le format importé</span><span class="sxs-lookup"><span data-stu-id="e1d7b-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="e1d7b-175">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-175">Close the page.</span></span>
2. <span data-ttu-id="e1d7b-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-176">Close the page.</span></span>
3. <span data-ttu-id="e1d7b-177">Accédez à Administration d’organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="e1d7b-178">Dans l’arborescence, développez « Modèle pour les chèques »</span><span class="sxs-lookup"><span data-stu-id="e1d7b-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="e1d7b-179">Dans l’arborescence, sélectionnez « Modèle pour les chèques\Format d’impression des chèques ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="e1d7b-180">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-180">Click Designer.</span></span>
7. <span data-ttu-id="e1d7b-181">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-181">Click Attachments.</span></span>
8. <span data-ttu-id="e1d7b-182">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-182">Click Delete.</span></span>
9. <span data-ttu-id="e1d7b-183">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-183">Click Yes.</span></span>
10. <span data-ttu-id="e1d7b-184">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-184">Click New.</span></span>
11. <span data-ttu-id="e1d7b-185">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-185">Click File.</span></span>
    * <span data-ttu-id="e1d7b-186">Cliquez sur Parcourir et sélectionnez le fichier « Modèle de chèque Word.docx » téléchargé à l’avance.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-186">Click Browse and select the downloaded in advance 'Cheque template Word.docx' file.</span></span>  
12. <span data-ttu-id="e1d7b-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-187">Close the page.</span></span>
13. <span data-ttu-id="e1d7b-188">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="e1d7b-189">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-189">Click Save.</span></span>
15. <span data-ttu-id="e1d7b-190">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-190">Close the page.</span></span>
16. <span data-ttu-id="e1d7b-191">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-191">Click Edit.</span></span>
17. <span data-ttu-id="e1d7b-192">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="e1d7b-193">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-193">Close the page.</span></span>
19. <span data-ttu-id="e1d7b-194">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="e1d7b-195">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="e1d7b-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="e1d7b-196">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-196">Click Check.</span></span>
22. <span data-ttu-id="e1d7b-197">Cliquer sur Test d’impression.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-197">Click Print test.</span></span>
23. <span data-ttu-id="e1d7b-198">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-198">Click OK.</span></span>
    * <span data-ttu-id="e1d7b-199">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-199">Review the created output.</span></span> <span data-ttu-id="e1d7b-200">La sortie a été générée en tant que document Word avec des images intégrées présentant le logo de la société, la signature d’une personne autorisée et le texte sélectionné du filigrane.</span><span class="sxs-lookup"><span data-stu-id="e1d7b-200">The output has been generated as a Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  

