---
title: Modifier des formats en réappliquant des modèles Excel
description: Pour réaliser les étapes de cette procédure, vous devez d'abord effectuer la procédure, ER - Concevoir une configuration pour générer des états au format OPENXML ».
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d5752caba9327475bb28c7bc6b0ee7e072f44f3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551159"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="14b9d-103">Modifier des formats en réappliquant des modèles Excel</span><span class="sxs-lookup"><span data-stu-id="14b9d-103">Modify formats by reapplying Excel templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14b9d-104">Pour réaliser les étapes de cette procédure, vous devez d'abord effectuer la procédure, ER - Concevoir une configuration pour générer des états au format OPENXML ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="14b9d-105">Cette procédure explique comment modifier une configuration du format ER en réappliquant un modèle Microsoft Excel modifié.</span><span class="sxs-lookup"><span data-stu-id="14b9d-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="14b9d-106">Dans cette procédure, vous importerez un modèle Excel modifié dans les configurations du format ER qui ont été créées pour la société fictive, Litware, Inc., puis générerez des documents électroniques.</span><span class="sxs-lookup"><span data-stu-id="14b9d-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="14b9d-107">Cette procédure est destinée aux utilisateurs disposant du rôle Administrateur système ou Développeur d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="14b9d-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="14b9d-108">Ces étapes peuvent être effectuées à l'aide de l'ensemble de données GBSI.</span><span class="sxs-lookup"><span data-stu-id="14b9d-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="14b9d-109">Avant de commencer, téléchargez et enregistrez le fichier, SampleVendPaymWsReport2.xlsx, répertorié dans la rubrique d'aide, Modifier un format de gestion d'états électroniques en réappliquant un modèle Excel (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="14b9d-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="14b9d-110">Accédez à Administration d'organisation > Espaces de travail > États électroniques.</span><span class="sxs-lookup"><span data-stu-id="14b9d-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="14b9d-111">Vérifiez que le fournisseur de configuration pour la société fictive, Litware, Inc., est disponible et marqué comme actif.</span><span class="sxs-lookup"><span data-stu-id="14b9d-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="14b9d-112">Si ce fournisseur de configuration ne s'affiche pas, effectuez les étapes de la procédure, Créer un fournisseur de configuration et le marquer comme actif.</span><span class="sxs-lookup"><span data-stu-id="14b9d-112">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="14b9d-113">Sélectionner le format ER</span><span class="sxs-lookup"><span data-stu-id="14b9d-113">Select the ER format</span></span>
1. <span data-ttu-id="14b9d-114">Cliquez sur Configurations des états.</span><span class="sxs-lookup"><span data-stu-id="14b9d-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="14b9d-115">Dans l'arborescence, développez « Payment model ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="14b9d-116">Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="14b9d-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="14b9d-117">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="14b9d-117">Click Attachments.</span></span>
    * <span data-ttu-id="14b9d-118">Notez que le fichier Excel SampleVendPaymWsReport.xlsx est actuellement utilisé comme modèle pour le traitement du journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="14b9d-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="14b9d-119">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="14b9d-119">Click Open.</span></span>
    * <span data-ttu-id="14b9d-120">Cliquez sur Ouvrir pour examiner la mise en page du modèle Excel.</span><span class="sxs-lookup"><span data-stu-id="14b9d-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="14b9d-121">Examinez le modèle.</span><span class="sxs-lookup"><span data-stu-id="14b9d-121">Review the template.</span></span> <span data-ttu-id="14b9d-122">Notez qu'il contient actuellement les détails suivants pour chaque ligne de paiement : le numéro de compte du fournisseur, le nom du fournisseur, la banque, le numéro d'acheminement, le numéro de compte, le débit, le crédit et la devise.</span><span class="sxs-lookup"><span data-stu-id="14b9d-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="14b9d-123">Pour cet exemple, nous souhaitons étendre cette liste en ajoutant des détails sur la date de paiement.</span><span class="sxs-lookup"><span data-stu-id="14b9d-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="14b9d-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="14b9d-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="14b9d-125">Réappliquer un nouveau modèle Excel au format ER</span><span class="sxs-lookup"><span data-stu-id="14b9d-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="14b9d-126">Cliquez sur Concepteur.</span><span class="sxs-lookup"><span data-stu-id="14b9d-126">Click Designer.</span></span>
    * <span data-ttu-id="14b9d-127">Ouvrez la version brouillon du format ER sélectionné pour modification.</span><span class="sxs-lookup"><span data-stu-id="14b9d-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="14b9d-128">Cliquez sur Importer dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="14b9d-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="14b9d-129">Cliquez sur Mettre à jour à partir d'Excel.</span><span class="sxs-lookup"><span data-stu-id="14b9d-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="14b9d-130">Cliquez sur « Mettre à jour le modèle », puis sélectionnez le fichier, SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="14b9d-130">Click ‘Update template’, and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="14b9d-131">Cliquez sur Mettre à jour le modèle et naviguez pour accéder au fichier SampleVendPaymWsReport2.xlsx précédemment téléchargé.</span><span class="sxs-lookup"><span data-stu-id="14b9d-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="14b9d-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="14b9d-132">Click OK.</span></span>
    * <span data-ttu-id="14b9d-133">Le modèle SampleVendPaymWsReport2.xlsx est appliqué.</span><span class="sxs-lookup"><span data-stu-id="14b9d-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="14b9d-134">La structure du format ER est synchronisée avec le contenu du modèle, dont les éléments sont ajoutés au format ER.</span><span class="sxs-lookup"><span data-stu-id="14b9d-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="14b9d-135">Tous les éléments existants dans le format ER qui ne sont pas inclus dans le modèle sont supprimés de la définition du format.</span><span class="sxs-lookup"><span data-stu-id="14b9d-135">Any existing elements in the ER format that aren’t included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="14b9d-136">Dans l'arborescence, sélectionnez « Excel ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="14b9d-137">Notez que le champ Modèle contient désormais une référence au nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="14b9d-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="14b9d-138">Cliquez sur Documents joints.</span><span class="sxs-lookup"><span data-stu-id="14b9d-138">Click Attachments.</span></span>
7. <span data-ttu-id="14b9d-139">Cliquez sur Ouvrir.</span><span class="sxs-lookup"><span data-stu-id="14b9d-139">Click Open.</span></span>
    * <span data-ttu-id="14b9d-140">Cliquez sur Ouvrir pour examiner la mise en page du modèle Excel modifié.</span><span class="sxs-lookup"><span data-stu-id="14b9d-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="14b9d-141">Examinez le modèle.</span><span class="sxs-lookup"><span data-stu-id="14b9d-141">Review the template.</span></span> <span data-ttu-id="14b9d-142">Notez qu'il contient maintenant une ligne pour la date de paiement.</span><span class="sxs-lookup"><span data-stu-id="14b9d-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="14b9d-143">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="14b9d-143">Close the page.</span></span>
9. <span data-ttu-id="14b9d-144">Dans l'arborescence, développez « Excel ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="14b9d-145">Dans l'arborescence, développez « Excel\PaymLines ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="14b9d-146">Dans l'arborescence, sélectionnez « Excel\PaymLines\PaymDate ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="14b9d-147">Notez que le format ER contient maintenant un élément de plus.</span><span class="sxs-lookup"><span data-stu-id="14b9d-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="14b9d-148">Une cellule, PaymDate, a été ajoutée au modèle Excel.</span><span class="sxs-lookup"><span data-stu-id="14b9d-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="14b9d-149">Cliquez sur l'onglet Mise en relation.</span><span class="sxs-lookup"><span data-stu-id="14b9d-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="14b9d-150">Dans l'arborescence , développez « model ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="14b9d-151">Dans l'arborescence, développez model\Payments.</span><span class="sxs-lookup"><span data-stu-id="14b9d-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="14b9d-152">Dans l'arborescence, sélectionnez « modèle\Paiments\Date de transaction(TransactionDate) ».</span><span class="sxs-lookup"><span data-stu-id="14b9d-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="14b9d-153">Cliquez sur Lier.</span><span class="sxs-lookup"><span data-stu-id="14b9d-153">Click Bind.</span></span>
    * <span data-ttu-id="14b9d-154">Spécifiez les données ajoutées à la nouvelle cellule au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="14b9d-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="14b9d-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="14b9d-155">Click Save.</span></span>
18. <span data-ttu-id="14b9d-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="14b9d-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="14b9d-157">Activer la version brouillon modifiée du format ER à utiliser dans le traitement du journal des paiements</span><span class="sxs-lookup"><span data-stu-id="14b9d-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="14b9d-158">Dans le volet Actions, cliquez sur Configurations.</span><span class="sxs-lookup"><span data-stu-id="14b9d-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="14b9d-159">Cliquez sur Paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="14b9d-159">Click User parameters.</span></span>
3. <span data-ttu-id="14b9d-160">Sélectionnez Oui dans le champ Paramètres d'exécution.</span><span class="sxs-lookup"><span data-stu-id="14b9d-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="14b9d-161">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="14b9d-161">Click OK.</span></span>
5. <span data-ttu-id="14b9d-162">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="14b9d-162">Click Edit.</span></span>
6. <span data-ttu-id="14b9d-163">Sélectionnez Oui dans le champ Exécuter le brouillon.</span><span class="sxs-lookup"><span data-stu-id="14b9d-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="14b9d-164">Utiliser la version brouillon modifiée du format ER pour le traitement du journal des paiements</span><span class="sxs-lookup"><span data-stu-id="14b9d-164">Use the modified draft version of the ER format for payment journal processing</span></span>
    * <span data-ttu-id="14b9d-165">Examinez la feuille de calcul créée, notamment les nouveaux détails des lignes de paiement – date de paiement.</span><span class="sxs-lookup"><span data-stu-id="14b9d-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  

