---
title: Paramétrer et générer des fichiers de paiement positif
description: Cet article décrit comment paramétrer le paiement positif et générer des fichiers de paiement positif.
author: panolte
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: kfend
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: d54e246b175c81b5d161ea35f141fc7dea9c6f1f
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070722"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Paramétrer et générer des fichiers de paiement positif

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Cette fonctionnalité sera obsolète en septembre 2022, les nouveaux utilisateurs doivent utiliser les rapports électroniques. Pour plus d’informations, voir [Paramétrer des fichiers de paiement positif avec la génération des états électroniques](set-up-positive-pay-er.md).

Cet article décrit comment paramétrer le paiement positif et générer des fichiers de paiement positif. 

Paramétrez le paiement positif pour générer la liste électronique de chèques qui est fournie à la banque. Puis, lorsque le chèque est présenté à la banque, la banque le compare avec la liste des chèques. Si le chèque correspond à un chèque de la liste, la banque le compense. Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.

## <a name="security-for-positive-pay-files"></a>Sécurité pour les fichiers de paiement positif
Les fichiers de paiement positif peuvent contenir des informations confidentielles sur les bénéficiaires et les montants des chèques. Veillez donc à utiliser les mesures de sécurité appropriées depuis la génération des fichiers jusqu’à leur réception par la banque. Les fichiers de paiement positif sont chargés à l’emplacement spécifié par votre navigateur Web. Comme les fichiers de paiement positif peuvent contenir des informations confidentielles, il est important que seuls les utilisateurs autorisés y aient accès pour générer et afficher ces informations dans Microsoft Dynamics 365 Finance. Utilisez le tableau suivant pour vous permettre de déterminer les privilèges requis.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tâche</th>
<th>Privilège</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Générer des fichiers de paiement positif à partir de la page de liste <strong>Comptes bancaires</strong> ou la page <strong>Comptes bancaires</strong>.</td>
<td><ul>
<li><strong>Mettre à jour les informations sur les paiements positifs bancaires</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires à partir de la page <strong>Générer un fichier de paiement positif</strong>.</td>
<td><ul>
<li><strong>Mettre à jour les informations sur les paiements positifs bancaires</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Afficher les fichiers de paiement positif dans la page <strong>Résumé du fichier de paiement positif</strong>.</td>
<td><strong>Afficher les informations sur les paiements positifs bancaires pour plusieurs entités juridiques</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confirmer un fichier de paiement positif bancaire dans la page <strong>Résumé du fichier de paiement positif</strong>.</td>
<td><strong>Confirmer le fichier de paiement positif</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Rappeler un fichier de paiement positif bancaire dans la page <strong>Résumé du fichier de paiement positif</strong>.</td>
<td><strong>Rappeler un fichier de paiement positif bancaire</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Paramétrer un format de paiement positif
Les fichiers de paiement positifs sont créés à l’aide d’entités de données. Avant de pouvoir générer un fichier de paiement positif, vous devez paramétrer un format d’entrée de transformation qui sera utilisé pour traduire les informations de chèque en un format pouvant communiquer avec la banque. Dans la page **Format du paiement positif**, vous pouvez créer un identificateur de format de fichier et une description. Le format d’entrée de la transformation doit être de type XML. Le format spécifique dépend du fichier de transformation que vous utilisez. Par exemple, le fichier exemple Extensible Stylesheet Language Transformation (XSLT) fourni utilise le format **Élément XML**. Utilisez l’action **Télécharger le fichier utilisé pour la transformation** pour spécifier l’emplacement du fichier de transformation pour le format que votre banque requiert.

## <a name="example-xslt-file-for-positive-pay-file"></a>Exemple : fichier XSLT pour un fichier de paiement positif

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
> Les noms XML dans le XSLT doivent correspondre à la casse des nœuds dans le XML. Les fichiers XSLT et XML sont sensibles à la casse. 

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Affecter le format de paiement positif à un compte bancaire
Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif que vous avez spécifié dans la section précédente. Dans la page **Comptes bancaires**, sélectionnez le format de paiement positif correspondant au compte bancaire. Dans le champ **Date de début du paiement positif** , entrez la première date pour générer des fichiers de paiement positif. Il est important que vous entriez une date dans ce champ. Sinon, le premier fichier de paiement positif que vous générerez inclura tous les chèques jamais créés pour ce compte bancaire.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Assigner une souche de Numéros pour les fichiers de paiement positif
Chaque fichier de paiement positif doit avoir un numéro unique. Utilisez l’onglet **Souches de numéros** dans la page **Paramètres de gestion de la trésorerie et de la banque** pour créer une souche de numéros pour des fichiers de paiement positif.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Générer un fichier de paiement positif pour un compte bancaire unique
Vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique. Pour en savoir plus sur la manière de générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps, référez-vous aux sections suivantes. Pour générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique, ouvrez la boîte de dialogue **Générer un fichier de paiement positif** depuis la page **Comptes bancaires**. Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif. Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Générer un fichier de paiement positif pour plusieurs comptes bancaires
Pour générer un fichier de paiement positif pour plusieurs comptes bancaires, utilisez la tâche périodique **Générer un fichier de paiement positif**. Choisissez le format de paiement positif pour le fichier et spécifiez si le fichier doit être généré pour toutes les entités juridiques ou pour une entité juridique sélectionnée. Vous pouvez également générer le fichier de paiement positif pour tous les comptes bancaires qui utilisent le format de paiement positif spécifié ou pour un compte bancaire sélectionné. Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif. Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Afficher les résultats de la génération du fichier de paiement positif
Une fois que le fichier de paiement positif est généré, vous pouvez afficher les résultats dans la page **Résumé du fichier de paiement positif**. Pour afficher les détails des chèques individuels, utilisez la page de détails **Fichier de paiement positif**.

## <a name="confirm-a-positive-pay-file"></a>Confirmation d’un fichier de paiement positif
Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque. Vous pouvez ensuite confirmer le fichier de paiement positif. Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Entrer la confirmation**. Lorsque vous confirmez un fichier de paiement positif, le numéro de confirmation que vous recevez de la banque est enregistré.

## <a name="recall-a-positive-pay-file"></a>Rappeler un fichier de paiement positif
Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler. Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Rappeler**. Pour chaque chèque présent dans le fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé. Vous pouvez alors créer un nouveau fichier de paiement positif qui inclut le chèque rappelé.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
