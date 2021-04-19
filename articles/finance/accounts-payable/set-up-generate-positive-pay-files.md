---
title: Paramétrer et générer des fichiers de paiement positif
description: Cette rubrique décrit comment paramétrer le paiement positif et générer des fichiers de paiement positif.
author: panolte
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9f96e34b8d94f9e83afb39d6ad97aca85386b458
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830710"
---
# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="cca56-103">Paramétrer et générer des fichiers de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-103">Set up and generate positive pay files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cca56-104">Cette rubrique décrit comment paramétrer le paiement positif et générer des fichiers de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-104">This topic explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="cca56-105">Paramétrez le paiement positif pour générer la liste électronique de chèques qui est fournie à la banque.</span><span class="sxs-lookup"><span data-stu-id="cca56-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="cca56-106">Puis, lorsque le chèque est présenté à la banque, la banque le compare avec la liste des chèques.</span><span class="sxs-lookup"><span data-stu-id="cca56-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="cca56-107">Si le chèque correspond à un chèque de la liste, la banque le compense.</span><span class="sxs-lookup"><span data-stu-id="cca56-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="cca56-108">Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.</span><span class="sxs-lookup"><span data-stu-id="cca56-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="cca56-109">Sécurité pour les fichiers de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-109">Security for positive pay files</span></span>
<span data-ttu-id="cca56-110">Les fichiers de paiement positif peuvent contenir des informations confidentielles sur les bénéficiaires et les montants des chèques.</span><span class="sxs-lookup"><span data-stu-id="cca56-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="cca56-111">Veillez donc à utiliser les mesures de sécurité appropriées depuis la génération des fichiers jusqu’à leur réception par la banque.</span><span class="sxs-lookup"><span data-stu-id="cca56-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="cca56-112">Les fichiers de paiement positif sont chargés à l’emplacement spécifié par votre navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="cca56-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="cca56-113">Comme les fichiers de paiement positif peuvent contenir des informations confidentielles, il est important que seuls les utilisateurs autorisés y aient accès pour générer et afficher ces informations dans Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="cca56-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="cca56-114">Utilisez le tableau suivant pour vous permettre de déterminer les privilèges requis.</span><span class="sxs-lookup"><span data-stu-id="cca56-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cca56-115">Tâche</span><span class="sxs-lookup"><span data-stu-id="cca56-115">Task</span></span></th>
<th><span data-ttu-id="cca56-116">Privilège</span><span class="sxs-lookup"><span data-stu-id="cca56-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cca56-117">Générer des fichiers de paiement positif à partir de la page de liste <strong>Comptes bancaires</strong> ou la page <strong>Comptes bancaires</strong>.</span><span class="sxs-lookup"><span data-stu-id="cca56-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="cca56-118"><strong>Mettre à jour les informations sur les paiements positifs bancaires</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="cca56-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="cca56-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="cca56-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cca56-120">Générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires à partir de la page <strong>Générer un fichier de paiement positif</strong>.</span><span class="sxs-lookup"><span data-stu-id="cca56-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="cca56-121"><strong>Mettre à jour les informations sur les paiements positifs bancaires</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="cca56-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="cca56-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="cca56-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cca56-123">Afficher les fichiers de paiement positif dans la page <strong>Résumé du fichier de paiement positif</strong>.</span><span class="sxs-lookup"><span data-stu-id="cca56-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="cca56-124"><strong>Afficher les informations sur les paiements positifs bancaires pour plusieurs entités juridiques</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="cca56-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cca56-125">Confirmer un fichier de paiement positif bancaire dans la page <strong>Résumé du fichier de paiement positif</strong>.</span><span class="sxs-lookup"><span data-stu-id="cca56-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="cca56-126"><strong>Confirmer le fichier de paiement positif</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="cca56-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cca56-127">Rappeler un fichier de paiement positif bancaire dans la page <strong>Résumé du fichier de paiement positif</strong>.</span><span class="sxs-lookup"><span data-stu-id="cca56-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="cca56-128"><strong>Rappeler un fichier de paiement positif bancaire</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="cca56-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="cca56-129">Paramétrer un format de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-129">Set up a positive pay format</span></span>
<span data-ttu-id="cca56-130">Les fichiers de paiement positifs sont créés à l’aide d’entités de données.</span><span class="sxs-lookup"><span data-stu-id="cca56-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="cca56-131">Avant de pouvoir générer un fichier de paiement positif, vous devez paramétrer un format d’entrée de transformation qui sera utilisé pour traduire les informations de chèque en un format pouvant communiquer avec la banque.</span><span class="sxs-lookup"><span data-stu-id="cca56-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="cca56-132">Dans la page **Format du paiement positif**, vous pouvez créer un identificateur de format de fichier et une description.</span><span class="sxs-lookup"><span data-stu-id="cca56-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="cca56-133">Le format d’entrée de la transformation doit être de type XML.</span><span class="sxs-lookup"><span data-stu-id="cca56-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="cca56-134">Le format spécifique dépend du fichier de transformation que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="cca56-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="cca56-135">Par exemple, le fichier exemple Extensible Stylesheet Language Transformation (XSLT) fourni utilise le format **Élément XML**.</span><span class="sxs-lookup"><span data-stu-id="cca56-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="cca56-136">Utilisez l’action **Télécharger le fichier utilisé pour la transformation** pour spécifier l’emplacement du fichier de transformation pour le format que votre banque requiert.</span><span class="sxs-lookup"><span data-stu-id="cca56-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="cca56-137">Exemple : fichier XSLT pour un fichier de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-137">Example: XSLT file for positive pay file</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
  <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:value-of select="'
'" />
    <Document>
      <xsl:value-of select="'
'" />
      <!--Header Begin-->
      <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
      <xsl:value-of select="'
'" />
      <!--Header End-->
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
        <!--Cheque Detail begin-->
        <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
            <xsl:value-of select='string("Yes")'/>
          </xsl:when>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
            <xsl:value-of select='string("No")'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='string(" ")'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("Payment")'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='CHEQUENUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='AMOUNTCUR/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("BOA-#1812")'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
            <xsl:value-of select='VENDGROUP/text()'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='CUSTGROUP/text()'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="'
'" />
      </xsl:for-each>
    </Document>
  </xsl:template>
</xsl:stylesheet>
```

> [!NOTE]
> <span data-ttu-id="cca56-138">Les noms XML dans le XSLT doivent correspondre à la casse des nœuds dans le XML.</span><span class="sxs-lookup"><span data-stu-id="cca56-138">XML names in the XSLT must match the casing of the nodes in the XML.</span></span> <span data-ttu-id="cca56-139">Les fichiers XSLT et XML sont sensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="cca56-139">Both the XSLT and XML files are case sensitive.</span></span> 

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="cca56-140">Affecter le format de paiement positif à un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="cca56-140">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="cca56-141">Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif que vous avez spécifié dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="cca56-141">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="cca56-142">Dans la page **Comptes bancaires**, sélectionnez le format de paiement positif correspondant au compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="cca56-142">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="cca56-143">Dans le champ **Date de début du paiement positif** , entrez la première date pour générer des fichiers de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-143">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="cca56-144">Il est important que vous entriez une date dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="cca56-144">It's important that you enter a date in this field.</span></span> <span data-ttu-id="cca56-145">Sinon, le premier fichier de paiement positif que vous générerez inclura tous les chèques jamais créés pour ce compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="cca56-145">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="cca56-146">Assigner une souche de Numéros pour les fichiers de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-146">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="cca56-147">Chaque fichier de paiement positif doit avoir un numéro unique.</span><span class="sxs-lookup"><span data-stu-id="cca56-147">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="cca56-148">Utilisez l’onglet **Souches de numéros** dans la page **Paramètres de gestion de la trésorerie et de la banque** pour créer une souche de numéros pour des fichiers de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-148">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="cca56-149">Générer un fichier de paiement positif pour un compte bancaire unique</span><span class="sxs-lookup"><span data-stu-id="cca56-149">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="cca56-150">Vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique.</span><span class="sxs-lookup"><span data-stu-id="cca56-150">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="cca56-151">Pour en savoir plus sur la manière de générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps, référez-vous aux sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="cca56-151">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="cca56-152">Pour générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique, ouvrez la boîte de dialogue **Générer un fichier de paiement positif** depuis la page **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="cca56-152">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="cca56-153">Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-153">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="cca56-154">Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="cca56-154">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="cca56-155">Générer un fichier de paiement positif pour plusieurs comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="cca56-155">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="cca56-156">Pour générer un fichier de paiement positif pour plusieurs comptes bancaires, utilisez la tâche périodique **Générer un fichier de paiement positif**.</span><span class="sxs-lookup"><span data-stu-id="cca56-156">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="cca56-157">Choisissez le format de paiement positif pour le fichier et spécifiez si le fichier doit être généré pour toutes les entités juridiques ou pour une entité juridique sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cca56-157">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="cca56-158">Vous pouvez également générer le fichier de paiement positif pour tous les comptes bancaires qui utilisent le format de paiement positif spécifié ou pour un compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cca56-158">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="cca56-159">Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-159">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="cca56-160">Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="cca56-160">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="cca56-161">Afficher les résultats de la génération du fichier de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-161">View the results of positive pay file generation</span></span>
<span data-ttu-id="cca56-162">Une fois que le fichier de paiement positif est généré, vous pouvez afficher les résultats dans la page **Résumé du fichier de paiement positif**.</span><span class="sxs-lookup"><span data-stu-id="cca56-162">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="cca56-163">Pour afficher les détails des chèques individuels, utilisez la page de détails **Fichier de paiement positif**.</span><span class="sxs-lookup"><span data-stu-id="cca56-163">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="cca56-164">Confirmation d’un fichier de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-164">Confirm a positive pay file</span></span>
<span data-ttu-id="cca56-165">Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque.</span><span class="sxs-lookup"><span data-stu-id="cca56-165">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="cca56-166">Vous pouvez ensuite confirmer le fichier de paiement positif.</span><span class="sxs-lookup"><span data-stu-id="cca56-166">You can then confirm the positive pay file.</span></span> <span data-ttu-id="cca56-167">Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Entrer la confirmation**.</span><span class="sxs-lookup"><span data-stu-id="cca56-167">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="cca56-168">Lorsque vous confirmez un fichier de paiement positif, le numéro de confirmation que vous recevez de la banque est enregistré.</span><span class="sxs-lookup"><span data-stu-id="cca56-168">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="cca56-169">Rappeler un fichier de paiement positif</span><span class="sxs-lookup"><span data-stu-id="cca56-169">Recall a positive pay file</span></span>
<span data-ttu-id="cca56-170">Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler.</span><span class="sxs-lookup"><span data-stu-id="cca56-170">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="cca56-171">Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Rappeler**.</span><span class="sxs-lookup"><span data-stu-id="cca56-171">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="cca56-172">Pour chaque chèque présent dans le fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="cca56-172">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="cca56-173">Vous pouvez alors créer un nouveau fichier de paiement positif qui inclut le chèque rappelé.</span><span class="sxs-lookup"><span data-stu-id="cca56-173">You can then create a new positive pay file that includes the check that was recalled.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
