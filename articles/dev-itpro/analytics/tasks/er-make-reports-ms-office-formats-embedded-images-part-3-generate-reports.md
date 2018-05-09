--- 
title: "Générer des états dans des formats Microsoft Office avec des images intégrées"
description: "Les étapes suivantes expliquent comment un utilisateur jouant le rôle de « Administrateur système » ou de « Développeur d'états électroniques » peut créer des configurations d'états électroniques (ER) pour générer des documents électroniques au format MS Office (Excel et Word) contenant des images intégrées."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e48b69bcb9f6cd16cc24dc52396dcffbe4074030
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="generate-reports-in-microsoft-office-formats-with-embedded-images"></a><span data-ttu-id="ecd96-103">Générer des états dans des formats Microsoft Office avec des images intégrées</span><span class="sxs-lookup"><span data-stu-id="ecd96-103">Generate reports in Microsoft Office formats with embedded images</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ecd96-104">Les étapes suivantes expliquent comment un utilisateur jouant le rôle de « Administrateur système » ou de « Développeur d'états électroniques » peut créer des configurations d'états électroniques (ER) pour générer des documents électroniques au format MS Office (Excel et Word) contenant des images intégrées.</span><span class="sxs-lookup"><span data-stu-id="ecd96-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="ecd96-105">Dans cet exemple, vous utiliserez les configurations ER créées pour la société fictive, « Litware, Inc. ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="ecd96-106">Pour réaliser ces étapes, vous devez d'abord effectuer les étapes du guide de tâche « ER Créer des états aux formats MS Office avec des images intégrées (Partie 2 : Examiner les configurations) ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="ecd96-107">Ces étapes peuvent être effectuées dans la société « USMF ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="ecd96-108">Exécuter le format avec la mise en correspondance initiale du modèle</span><span class="sxs-lookup"><span data-stu-id="ecd96-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="ecd96-109">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="ecd96-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="ecd96-110">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="ecd96-111">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="ecd96-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="ecd96-112">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-112">Click Check.</span></span>
5. <span data-ttu-id="ecd96-113">Cliquer sur Test d'impression.</span><span class="sxs-lookup"><span data-stu-id="ecd96-113">Click Print test.</span></span>
    * <span data-ttu-id="ecd96-114">Exécutez le format à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="ecd96-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="ecd96-115">Sélectionnez Oui dans le champ Format de chèque négociable.</span><span class="sxs-lookup"><span data-stu-id="ecd96-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="ecd96-116">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ecd96-116">Click OK.</span></span>
    * <span data-ttu-id="ecd96-117">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-117">Review the created output.</span></span> <span data-ttu-id="ecd96-118">Notez que le logo de la société est présenté dans l'état ainsi que la signature de la personne autorisée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="ecd96-119">L'image de la signature est extraite du champ du type de données « Conteneur » de l'enregistrement de mise en page de chèque associé au compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ecd96-119">The signature image is taken from the field of the ‘Container’ data type of the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="ecd96-120">Développez la section Copies.</span><span class="sxs-lookup"><span data-stu-id="ecd96-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="ecd96-121">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-121">Click Edit.</span></span>
10. <span data-ttu-id="ecd96-122">Dans le champ Filigrane, entrez « Imprimer le filigrane comme annulé ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="ecd96-123">Modifiez le paramètre de mise en page du filigrane pour afficher le texte du filigrane lors de la génération du document dans un élément au format Excel.</span><span class="sxs-lookup"><span data-stu-id="ecd96-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="ecd96-124">Cliquer sur Test d'impression.</span><span class="sxs-lookup"><span data-stu-id="ecd96-124">Click Print test.</span></span>
12. <span data-ttu-id="ecd96-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ecd96-125">Click OK.</span></span>
    * <span data-ttu-id="ecd96-126">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-126">Review the created output.</span></span> <span data-ttu-id="ecd96-127">Notez que le filigrane s'affiche dans l'état créé conformément à l'option de sélection.</span><span class="sxs-lookup"><span data-stu-id="ecd96-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="ecd96-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-128">Close the page.</span></span>
14. <span data-ttu-id="ecd96-129">Dans le volet Actions, cliquez sur Gérer les paiements.</span><span class="sxs-lookup"><span data-stu-id="ecd96-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="ecd96-130">Cliquez sur Chèques.</span><span class="sxs-lookup"><span data-stu-id="ecd96-130">Click Checks.</span></span>
16. <span data-ttu-id="ecd96-131">Cliquez sur Afficher les filtres.</span><span class="sxs-lookup"><span data-stu-id="ecd96-131">Click Show filters.</span></span>
17. <span data-ttu-id="ecd96-132">Appliquez les filtres suivants : entrez la valeur de filtre « 381 », « 385 », « 389 » dans le champ « Numéro de chèque » en utilisant l'opérateur de filtre « est l'un de ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="ecd96-133">Dans la liste, marquez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="ecd96-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="ecd96-134">Cliquez sur Imprimer une copie du chèque.</span><span class="sxs-lookup"><span data-stu-id="ecd96-134">Click Print check copy.</span></span>
    * <span data-ttu-id="ecd96-135">Exécutez le format pour réimprimer les chèques sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="ecd96-135">Run the format to re-print the selected cheques.</span></span>  
    * <span data-ttu-id="ecd96-136">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-136">Review the created output.</span></span> <span data-ttu-id="ecd96-137">Notez que les chèques sélectionnés ont été réimprimés.</span><span class="sxs-lookup"><span data-stu-id="ecd96-137">Note that the selected cheques have been re-printed.</span></span> <span data-ttu-id="ecd96-138">Le logo et les libellés de la société ne sont pas imprimés, car ils sont présentés sur le formulaire pré-imprimé.</span><span class="sxs-lookup"><span data-stu-id="ecd96-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="ecd96-139">Modifier la mise en correspondance du modèle de données importé</span><span class="sxs-lookup"><span data-stu-id="ecd96-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="ecd96-140">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-140">Close the page.</span></span>
2. <span data-ttu-id="ecd96-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-141">Close the page.</span></span>
3. <span data-ttu-id="ecd96-142">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="ecd96-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="ecd96-143">Dans l'arborescence, sélectionnez « Modèle pour les chèques »</span><span class="sxs-lookup"><span data-stu-id="ecd96-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="ecd96-144">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ecd96-144">Click Designer.</span></span>
6. <span data-ttu-id="ecd96-145">Cliquez sur Mettre en correspondance le modèle à la source de données.</span><span class="sxs-lookup"><span data-stu-id="ecd96-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="ecd96-146">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ecd96-146">Click Designer.</span></span>
    * <span data-ttu-id="ecd96-147">Nous modifierons la liaison de l'élément de signature du modèle de données pour obtenir l'image de la signature à partir du fichier qui a été lié à l'enregistrement de mise en page de chèque associé au compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ecd96-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="ecd96-148">Désactivez Afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="ecd96-148">Turn Show details off.</span></span>
9. <span data-ttu-id="ecd96-149">Dans l'arborescence, développez « layout ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="ecd96-150">Dans l'arborescence, développez « layout\signature »</span><span class="sxs-lookup"><span data-stu-id="ecd96-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="ecd96-151">Dans l'arborescence, sélectionnez « layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="ecd96-152">Dans l'arborescence, développez « chequesaccount ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="ecd96-153">Dans l'arborescence, développez « chequesaccount\<Relations ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="ecd96-154">Dans l'arborescence, développez « chequesaccount\<Relations\BankChequeLayout ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="ecd96-155">Dans l'arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="ecd96-156">Dans l'arborescence, développez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="ecd96-157">Dans l'arborescence, sélectionnez « chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer() ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="ecd96-158">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-158">Click Bind.</span></span>
19. <span data-ttu-id="ecd96-159">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ecd96-159">Click Save.</span></span>
20. <span data-ttu-id="ecd96-160">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-160">Close the page.</span></span>
21. <span data-ttu-id="ecd96-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-161">Close the page.</span></span>
22. <span data-ttu-id="ecd96-162">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-162">Close the page.</span></span>
23. <span data-ttu-id="ecd96-163">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="ecd96-164">Exécuter le format avec la mise en correspondance ajustée du modèle</span><span class="sxs-lookup"><span data-stu-id="ecd96-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="ecd96-165">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="ecd96-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="ecd96-166">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="ecd96-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ecd96-167">Par exemple, filtrez le champ Compte bancaire avec la valeur « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="ecd96-168">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="ecd96-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="ecd96-169">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-169">Click Check.</span></span>
5. <span data-ttu-id="ecd96-170">Cliquer sur Test d'impression.</span><span class="sxs-lookup"><span data-stu-id="ecd96-170">Click Print test.</span></span>
6. <span data-ttu-id="ecd96-171">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ecd96-171">Click OK.</span></span>
    * <span data-ttu-id="ecd96-172">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-172">Review the created output.</span></span> <span data-ttu-id="ecd96-173">Notez que l'image de la pièce jointe Gestion des documents est présentée comme la signature d'une personne autorisée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="ecd96-174">Utiliser le document MS Word comme modèle dans le format importé</span><span class="sxs-lookup"><span data-stu-id="ecd96-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="ecd96-175">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-175">Close the page.</span></span>
2. <span data-ttu-id="ecd96-176">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-176">Close the page.</span></span>
3. <span data-ttu-id="ecd96-177">Accédez à Administration d'organisation > États électroniques > Configurations.</span><span class="sxs-lookup"><span data-stu-id="ecd96-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="ecd96-178">Dans l'arborescence, développez « Modèle pour les chèques »</span><span class="sxs-lookup"><span data-stu-id="ecd96-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="ecd96-179">Dans l'arborescence, sélectionnez « Modèle pour les chèques\Format d'impression des chèques ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="ecd96-180">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="ecd96-180">Click Designer.</span></span>
7. <span data-ttu-id="ecd96-181">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="ecd96-181">Click Attachments.</span></span>
8. <span data-ttu-id="ecd96-182">Cliquez sur Supprimer.</span><span class="sxs-lookup"><span data-stu-id="ecd96-182">Click Delete.</span></span>
9. <span data-ttu-id="ecd96-183">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="ecd96-183">Click Yes.</span></span>
10. <span data-ttu-id="ecd96-184">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="ecd96-184">Click New.</span></span>
11. <span data-ttu-id="ecd96-185">Cliquez sur Fichier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-185">Click File.</span></span>
    * <span data-ttu-id="ecd96-186">Cliquez sur Parcourir et sélectionnez le fichier « Modèle de chèque Word.docx » téléchargé à l'avance.</span><span class="sxs-lookup"><span data-stu-id="ecd96-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="ecd96-187">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-187">Close the page.</span></span>
13. <span data-ttu-id="ecd96-188">Dans le champ Modèle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="ecd96-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="ecd96-189">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ecd96-189">Click Save.</span></span>
15. <span data-ttu-id="ecd96-190">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-190">Close the page.</span></span>
16. <span data-ttu-id="ecd96-191">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-191">Click Edit.</span></span>
17. <span data-ttu-id="ecd96-192">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="ecd96-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="ecd96-193">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ecd96-193">Close the page.</span></span>
19. <span data-ttu-id="ecd96-194">Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="ecd96-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="ecd96-195">Utilisez le filtre rapide pour filtrer sur le champ Compte bancaire avec une valeur de « USMF OPER ».</span><span class="sxs-lookup"><span data-stu-id="ecd96-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="ecd96-196">Cliquez sur Vérifier.</span><span class="sxs-lookup"><span data-stu-id="ecd96-196">Click Check.</span></span>
22. <span data-ttu-id="ecd96-197">Cliquer sur Test d'impression.</span><span class="sxs-lookup"><span data-stu-id="ecd96-197">Click Print test.</span></span>
23. <span data-ttu-id="ecd96-198">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ecd96-198">Click OK.</span></span>
    * <span data-ttu-id="ecd96-199">Examinez la sortie créée.</span><span class="sxs-lookup"><span data-stu-id="ecd96-199">Review the created output.</span></span> <span data-ttu-id="ecd96-200">Notez que la sortie a été générée en tant que document MS Word avec des images intégrées présentant le logo de la société, la signature d'une personne autorisée et le texte sélectionné du filigrane.</span><span class="sxs-lookup"><span data-stu-id="ecd96-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  


