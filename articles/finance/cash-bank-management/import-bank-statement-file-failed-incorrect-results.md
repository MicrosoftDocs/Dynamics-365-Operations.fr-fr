---
title: Dépannage d’importation de fichier de relevé bancaire
description: Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 Finance. En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement. Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects. Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire. Cet article décrit comment résoudre ces différences ainsi que les problèmes.
author: panolte
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09b24b88ee5f8104aabd11397d5bd2745e846cb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443052"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="1ccff-107">Dépannage d’importation de fichier de relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="1ccff-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ccff-108">Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="1ccff-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="1ccff-109">En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement.</span><span class="sxs-lookup"><span data-stu-id="1ccff-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="1ccff-110">Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects.</span><span class="sxs-lookup"><span data-stu-id="1ccff-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="1ccff-111">Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="1ccff-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="1ccff-112">Cet article décrit comment résoudre ces différences ainsi que les problèmes.</span><span class="sxs-lookup"><span data-stu-id="1ccff-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="1ccff-113">Quelle est l’erreur ?</span><span class="sxs-lookup"><span data-stu-id="1ccff-113">What is the error?</span></span>
------------------

<span data-ttu-id="1ccff-114">Une fois que vous avez essayé d’importer un fichier de relevé bancaire, allez dans l’historique des tâches de gestion des données et ses détails d’exécution pour trouver l’erreur.</span><span class="sxs-lookup"><span data-stu-id="1ccff-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="1ccff-115">L’erreur peut aider en pointant vers le relevé, le solde ou la ligne de relevé.</span><span class="sxs-lookup"><span data-stu-id="1ccff-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="1ccff-116">Toutefois, il est peu probable qu’elle fournisse assez d’informations pour vous aider à identifier le champ ou l’élément qui provoque le problème.</span><span class="sxs-lookup"><span data-stu-id="1ccff-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="1ccff-117">Quelles sont les différences ?</span><span class="sxs-lookup"><span data-stu-id="1ccff-117">What are the differences?</span></span>
<span data-ttu-id="1ccff-118">Comparez la définition bancaire de la mise en page de fichier à la définition d’importation de Finance, et notez les différences dans les champs et les éléments.</span><span class="sxs-lookup"><span data-stu-id="1ccff-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="1ccff-119">Comparez le fichier de relevé bancaire à l’exemple de fichier Finance associé.</span><span class="sxs-lookup"><span data-stu-id="1ccff-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="1ccff-120">Dans les fichiers ISO20022, il est facile d’afficher toutes les différences.</span><span class="sxs-lookup"><span data-stu-id="1ccff-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="1ccff-121">Différences de fuseau horaire dans les relevés bancaires importés</span><span class="sxs-lookup"><span data-stu-id="1ccff-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="1ccff-122">Les valeurs d’heure et de date dans le fichier d’importation peuvent différer des valeurs d’heure et de date affichées dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ccff-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="1ccff-123">Pour éviter cet écart, saisissez la préférence de fuseau horaire sur la page **Configurer les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="1ccff-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="1ccff-124">Voir [Paramétrage du processus d’importation du rapprochement bancaire](set-up-advanced-bank-reconciliation-import-process.md) pour en savoir plus sur la saisie d’une préférence de fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="1ccff-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="1ccff-125">Transformations</span><span class="sxs-lookup"><span data-stu-id="1ccff-125">Transformations</span></span>
<span data-ttu-id="1ccff-126">Généralement, la modification doit être effectuée dans l’une des trois transformations.</span><span class="sxs-lookup"><span data-stu-id="1ccff-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="1ccff-127">Chaque transformation concerne une norme spécifique.</span><span class="sxs-lookup"><span data-stu-id="1ccff-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="1ccff-128">Nom de la ressource</span><span class="sxs-lookup"><span data-stu-id="1ccff-128">Resource name</span></span>                                         | <span data-ttu-id="1ccff-129">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="1ccff-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="1ccff-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="1ccff-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="1ccff-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="1ccff-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="1ccff-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="1ccff-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="1ccff-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="1ccff-136">Transformations de débogage</span><span class="sxs-lookup"><span data-stu-id="1ccff-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="1ccff-137">Modifiez les fichiers BAI2 et MT940</span><span class="sxs-lookup"><span data-stu-id="1ccff-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="1ccff-138">Les fichiers BAI2 et MT940 sont basés sur des fichiers texte et exigent un ajustement pour activer le débogage Extensible Stylesheet Language Transformations (XSLT).</span><span class="sxs-lookup"><span data-stu-id="1ccff-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="1ccff-139">Le programme effectue cet ajustement lors de l’importation d’un fichier.</span><span class="sxs-lookup"><span data-stu-id="1ccff-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="1ccff-140">Créez un fichier XML, puis copiez le texte suivant dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="1ccff-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="1ccff-141">Copiez le contenu du fichier de relevé bancaire, et collez-le dans le fichier XML afin qu’il remplace **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="1ccff-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="1ccff-142">Déboguer un XSLT</span><span class="sxs-lookup"><span data-stu-id="1ccff-142">Debug the XSLT</span></span>

<span data-ttu-id="1ccff-143">Pour plus d’informations, voir <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="1ccff-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="1ccff-144">Démarrez Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ccff-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="1ccff-145">Créez une application de console.</span><span class="sxs-lookup"><span data-stu-id="1ccff-145">Create a console application.</span></span>
3.  <span data-ttu-id="1ccff-146">Ouvrez le XSLT approprié.</span><span class="sxs-lookup"><span data-stu-id="1ccff-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="1ccff-147">Cliquez sur le XLST et sa page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="1ccff-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="1ccff-148">Définissez l’entrée de l’emplacement du fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="1ccff-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="1ccff-149">Définissez un emplacement et un nom de fichier pour le résultat.</span><span class="sxs-lookup"><span data-stu-id="1ccff-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="1ccff-150">Définissez les points d’arrêt requis.</span><span class="sxs-lookup"><span data-stu-id="1ccff-150">Set the required break points.</span></span>
8.  <span data-ttu-id="1ccff-151">Dans le menu, cliquez sur **XML** &gt; **Démarrer le débogage XSLT**.</span><span class="sxs-lookup"><span data-stu-id="1ccff-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="1ccff-152">Mettre en forme le résultat XSLT</span><span class="sxs-lookup"><span data-stu-id="1ccff-152">Format the XSLT output</span></span>

<span data-ttu-id="1ccff-153">Lorsque la transformation est exécutée, elle crée un fichier de sortie visible dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ccff-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="1ccff-154">Faites Ctrl+A, Ctrl+K, et Ctrl+D pour mettre en forme rapidement le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="1ccff-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="1ccff-155">Ajuster la transformation</span><span class="sxs-lookup"><span data-stu-id="1ccff-155">Adjust the transformation</span></span>

<span data-ttu-id="1ccff-156">Ajustez la transformation pour obtenir le champ ou l’élément approprié dans le fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="1ccff-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="1ccff-157">Mappez ensuite ce champ ou cet élément à l’élément Finance approprié.</span><span class="sxs-lookup"><span data-stu-id="1ccff-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="1ccff-158">Indicateur de débit/crédit</span><span class="sxs-lookup"><span data-stu-id="1ccff-158">Debit/credit indicator</span></span>

<span data-ttu-id="1ccff-159">Parfois, les débits peuvent être importés en tant que crédits, et des crédits peuvent être importés en tant que débits.</span><span class="sxs-lookup"><span data-stu-id="1ccff-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="1ccff-160">Pour résoudre ce problème, vous devez modifier le XSLT approprié.</span><span class="sxs-lookup"><span data-stu-id="1ccff-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="1ccff-161">Si des relevés bancaires proviennent de plusieurs banques, assurez-vous qu’elles utilisent toutes la même méthode de débit/crédit, ou créez des transformations distinctes.</span><span class="sxs-lookup"><span data-stu-id="1ccff-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="1ccff-162">Modèle BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="1ccff-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="1ccff-163">Modèle ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="1ccff-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="1ccff-164">Modèle MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="1ccff-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="1ccff-165">Exemples de formats de relevé bancaire et de mises en page techniques</span><span class="sxs-lookup"><span data-stu-id="1ccff-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="1ccff-166">Le tableau suivant répertorie des exemples de définitions de mise en page techniques de fichier d’importation de rapprochement bancaire avancé et trois fichiers d’exemples de relevé bancaire associés :</span><span class="sxs-lookup"><span data-stu-id="1ccff-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="1ccff-167">Vous pouvez télécharger les fichiers d’exemple et les dispositions techniques ici : https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="1ccff-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="1ccff-168">Définition de mise en page technique</span><span class="sxs-lookup"><span data-stu-id="1ccff-168">Technical layout definition</span></span>                             | <span data-ttu-id="1ccff-169">Fichier d’exemple de relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="1ccff-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="1ccff-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="1ccff-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="1ccff-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="1ccff-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="1ccff-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="1ccff-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="1ccff-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="1ccff-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="1ccff-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="1ccff-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="1ccff-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="1ccff-175">BAI2StatementExample</span></span>                 |





