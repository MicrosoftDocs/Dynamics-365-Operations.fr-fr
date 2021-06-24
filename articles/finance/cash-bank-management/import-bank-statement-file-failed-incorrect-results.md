---
title: Dépannage d’importation de fichier de relevé bancaire
description: Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 Finance. En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement. Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects. Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire. Cet article décrit comment résoudre ces différences ainsi que les problèmes.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f0e480b93e663f81db5a1edb2ae71b559bb05e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188557"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="b4127-107">Dépannage d’importation de fichier de relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="b4127-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4127-108">Il est important que le fichier de relevé bancaire de la banque corresponde à la mise en page prise en charge par Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b4127-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="b4127-109">En raison de normes strictes pour les relevés bancaires, la plupart des intégrations fonctionneront correctement.</span><span class="sxs-lookup"><span data-stu-id="b4127-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="b4127-110">Toutefois, il arrive que le fichier de relevé ne puisse pas être importé ou contienne des résultats incorrects.</span><span class="sxs-lookup"><span data-stu-id="b4127-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="b4127-111">Généralement, ces problèmes sont engendrés par de petites différences dans le fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="b4127-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="b4127-112">Cet article décrit comment résoudre ces différences ainsi que les problèmes.</span><span class="sxs-lookup"><span data-stu-id="b4127-112">This article explains how to fix these differences and resolve the issues.</span></span>

## <a name="what-is-the-error"></a><span data-ttu-id="b4127-113">Quelle est l’erreur ?</span><span class="sxs-lookup"><span data-stu-id="b4127-113">What is the error?</span></span>

<span data-ttu-id="b4127-114">Une fois que vous avez essayé d’importer un fichier de relevé bancaire, allez dans l’historique des tâches de gestion des données et ses détails d’exécution pour trouver l’erreur.</span><span class="sxs-lookup"><span data-stu-id="b4127-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="b4127-115">L’erreur peut aider en pointant vers le relevé, le solde ou la ligne de relevé.</span><span class="sxs-lookup"><span data-stu-id="b4127-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="b4127-116">Toutefois, il est peu probable qu’elle fournisse assez d’informations pour vous aider à identifier le champ ou l’élément qui provoque le problème.</span><span class="sxs-lookup"><span data-stu-id="b4127-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="b4127-117">Les relevés bancaires importés ne peuvent se chevaucher que pour un seul instant.</span><span class="sxs-lookup"><span data-stu-id="b4127-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="b4127-118">Par exemple, si un relevé se termine à minuit le 1er janvier 2021, la date de début du relevé suivant peut être minuit le 1er janvier, 2021.</span><span class="sxs-lookup"><span data-stu-id="b4127-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="b4127-119">Quelles sont les différences ?</span><span class="sxs-lookup"><span data-stu-id="b4127-119">What are the differences?</span></span>
<span data-ttu-id="b4127-120">Comparez la définition bancaire de la mise en page de fichier à la définition d’importation de Finance, et notez les différences dans les champs et les éléments.</span><span class="sxs-lookup"><span data-stu-id="b4127-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="b4127-121">Comparez le fichier de relevé bancaire à l’exemple de fichier Finance associé.</span><span class="sxs-lookup"><span data-stu-id="b4127-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="b4127-122">Dans les fichiers ISO20022, il est facile d’afficher toutes les différences.</span><span class="sxs-lookup"><span data-stu-id="b4127-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="b4127-123">Différences de fuseau horaire dans les relevés bancaires importés</span><span class="sxs-lookup"><span data-stu-id="b4127-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="b4127-124">Les valeurs d’heure et de date dans le fichier d’importation peuvent différer des valeurs d’heure et de date affichées dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b4127-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="b4127-125">Pour éviter cet écart, saisissez la préférence de fuseau horaire sur la page **Configurer les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="b4127-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="b4127-126">Pour plus d’informations sur la saisie d’une préférence de fuseau horaire, voir [Paramétrage du processus d’importation du rapprochement bancaire](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="b4127-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="b4127-127">Transformations</span><span class="sxs-lookup"><span data-stu-id="b4127-127">Transformations</span></span>
<span data-ttu-id="b4127-128">Généralement, la modification doit être effectuée dans l’une des trois transformations.</span><span class="sxs-lookup"><span data-stu-id="b4127-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="b4127-129">Chaque transformation concerne une norme spécifique.</span><span class="sxs-lookup"><span data-stu-id="b4127-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="b4127-130">Nom de la ressource</span><span class="sxs-lookup"><span data-stu-id="b4127-130">Resource name</span></span>                                         | <span data-ttu-id="b4127-131">Nom de fichier</span><span class="sxs-lookup"><span data-stu-id="b4127-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="b4127-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="b4127-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="b4127-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="b4127-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="b4127-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="b4127-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="b4127-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="b4127-138">Transformations de débogage</span><span class="sxs-lookup"><span data-stu-id="b4127-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="b4127-139">Modifiez les fichiers BAI2 et MT940</span><span class="sxs-lookup"><span data-stu-id="b4127-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="b4127-140">Les fichiers BAI2 et MT940 sont basés sur des fichiers texte et exigent un ajustement pour activer le débogage Extensible Stylesheet Language Transformations (XSLT).</span><span class="sxs-lookup"><span data-stu-id="b4127-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="b4127-141">Le programme effectue cet ajustement lors de l’importation d’un fichier.</span><span class="sxs-lookup"><span data-stu-id="b4127-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="b4127-142">Créez un fichier XML, puis copiez le texte suivant dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="b4127-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="b4127-143">Copiez le contenu du fichier de relevé bancaire, et collez-le dans le fichier XML afin qu’il remplace **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="b4127-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="b4127-144">Déboguer un XSLT</span><span class="sxs-lookup"><span data-stu-id="b4127-144">Debug the XSLT</span></span>

<span data-ttu-id="b4127-145">Pour plus d’informations, voir <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="b4127-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="b4127-146">Démarrez Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4127-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="b4127-147">Créez une application de console.</span><span class="sxs-lookup"><span data-stu-id="b4127-147">Create a console application.</span></span>
3.  <span data-ttu-id="b4127-148">Ouvrez le XSLT approprié.</span><span class="sxs-lookup"><span data-stu-id="b4127-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="b4127-149">Cliquez sur le XLST et sa page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="b4127-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="b4127-150">Définissez l’entrée de l’emplacement du fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="b4127-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="b4127-151">Définissez un emplacement et un nom de fichier pour le résultat.</span><span class="sxs-lookup"><span data-stu-id="b4127-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="b4127-152">Définissez les points d’arrêt requis.</span><span class="sxs-lookup"><span data-stu-id="b4127-152">Set the required break points.</span></span>
8.  <span data-ttu-id="b4127-153">Dans le menu, cliquez sur **XML** &gt; **Démarrer le débogage XSLT**.</span><span class="sxs-lookup"><span data-stu-id="b4127-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="b4127-154">Mettre en forme le résultat XSLT</span><span class="sxs-lookup"><span data-stu-id="b4127-154">Format the XSLT output</span></span>

<span data-ttu-id="b4127-155">Lorsque la transformation est exécutée, elle crée un fichier de sortie visible dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4127-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="b4127-156">Faites Ctrl+A, Ctrl+K, et Ctrl+D pour mettre en forme rapidement le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="b4127-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="b4127-157">Ajuster la transformation</span><span class="sxs-lookup"><span data-stu-id="b4127-157">Adjust the transformation</span></span>

<span data-ttu-id="b4127-158">Ajustez la transformation pour obtenir le champ ou l’élément approprié dans le fichier de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="b4127-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="b4127-159">Mappez ensuite ce champ ou cet élément à l’élément Finance approprié.</span><span class="sxs-lookup"><span data-stu-id="b4127-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="b4127-160">Indicateur de débit/crédit</span><span class="sxs-lookup"><span data-stu-id="b4127-160">Debit/credit indicator</span></span>

<span data-ttu-id="b4127-161">Parfois, les débits peuvent être importés en tant que crédits, et des crédits peuvent être importés en tant que débits.</span><span class="sxs-lookup"><span data-stu-id="b4127-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="b4127-162">Pour résoudre ce problème, vous devez modifier le XSLT approprié.</span><span class="sxs-lookup"><span data-stu-id="b4127-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="b4127-163">Si des relevés bancaires proviennent de plusieurs banques, assurez-vous qu’elles utilisent toutes la même méthode de débit/crédit, ou créez des transformations distinctes.</span><span class="sxs-lookup"><span data-stu-id="b4127-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="b4127-164">Modèle BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="b4127-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="b4127-165">Modèle ISO20022XML-to-Reconcilation.xslt GetCreditDebit</span><span class="sxs-lookup"><span data-stu-id="b4127-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="b4127-166">Modèle MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator</span><span class="sxs-lookup"><span data-stu-id="b4127-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="b4127-167">Exemples de formats de relevé bancaire et de mises en page techniques</span><span class="sxs-lookup"><span data-stu-id="b4127-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="b4127-168">Le tableau suivant répertorie des exemples de définitions de mise en page techniques de fichier d’importation de rapprochement bancaire avancé et trois fichiers d’exemples de relevé bancaire associés :</span><span class="sxs-lookup"><span data-stu-id="b4127-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="b4127-169">Vous pouvez télécharger les fichiers d’exemple et les dispositions techniques ici : [Importer des fichiers d’exemple](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="b4127-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="b4127-170">Définition de mise en page technique</span><span class="sxs-lookup"><span data-stu-id="b4127-170">Technical layout definition</span></span>                             | <span data-ttu-id="b4127-171">Fichier d’exemple de relevé bancaire</span><span class="sxs-lookup"><span data-stu-id="b4127-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="b4127-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="b4127-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="b4127-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="b4127-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="b4127-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="b4127-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="b4127-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="b4127-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="b4127-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="b4127-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="b4127-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="b4127-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
