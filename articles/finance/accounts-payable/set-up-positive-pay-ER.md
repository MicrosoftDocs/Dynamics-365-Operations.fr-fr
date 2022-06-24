---
title: Configurer et générer des fichiers de paie positifs à l’aide d’états électroniques
description: Cet article décrit comment paramétrer le paiement positif à l’aide d’états électroniques.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878216"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurer des fichiers de paie positifs à l’aide d’états électroniques

Cet article décrit comment paramétrer le paiement positif et générer des fichiers à l’aide de la notification électronique.

> [!NOTE] 
> Avant d’utiliser la fonction **Générer un fichier de paiement positif bancaire**, vous devrez d’abord actualiser la liste des entités.
> Accédez au raccourci **Gestion des données > Importer / Exporter > Paramètres de l’environnement** 
> **Paramètres de l’entité**, sélectionnez **Actualiser la liste des entités**.


Paramétrez le paiement positif pour générer la liste électronique de chèques qui est fournie à la banque. Lorsque le chèque est présenté à la banque, la banque le compare avec la liste des chèques. Si le chèque correspond à un chèque de la liste, la banque le compense. Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.

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

## <a name="set-up-the-electronic-reporting-configuration"></a>Paramétrer la configurations de la gestion des états électroniques

1. Accédez à **Espaces de travail \> États électroniques**.
2. Sur la vignette du fournisseur de configuration **Microsoft**, sélectionnez **Référentiels**.
3. Sélectionnez **Global**, puis sélectionnez **Ouvrir**.
4. Si une connexion au référentiel doit être établie, sélectionnez le lien bleu dans la boîte de dialogue.
5. Dans la liste de configurations, recherchez et sélectionnez **Modèle de paiement positif \> Format de paiement positif**.
6. Dans l’organisateur **Versions**, sélectionnez la version la plus récente, puis sélectionnez **Importer**.

## <a name="set-up-a-positive-pay-format"></a>Paramétrer un format de paiement positif

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Formats de paiement positifs**.
2. Cliquez sur **Nouveau**.
3. Définissez les champs **Format du paiement** et **Description**.
4. Cochez la case **Format d’exportation électronique générique**.
5. Définissez le champ **Configuration du format d’exportation** sur **Format de paiement positif**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Affecter un format de paiement positif à un compte bancaire
Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif que vous avez spécifié dans la section précédente. Dans la page Comptes bancaires, sélectionnez le format de paiement positif correspondant au compte bancaire. Dans le champ **Date de début du paiement positif** , entrez la première date pour générer des fichiers de paiement positif. 

>[!Important]
> Entrez une date dans le champ **Date de début du paiement positif**. Si le champ est laissé vide, le premier fichier de paiement positif qui est généré inclura tous les chèques jamais créés pour ce compte bancaire.

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez le compte bancaire.
3. Dans l’organisateur **Général**, définissez le champ **Format de paiement positif** au format qui a été créé précédemment.
4. Définissez le champ **Date de début du paiement positif** à la date du jour.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Assigner une souche de Numéros pour les fichiers de paiement positif
Chaque fichier de paiement positif doit avoir un numéro unique. Sur la page **Paramètres de gestion de la trésorerie et de la banque**, créez une souche de numéros pour des fichiers de paiement positif dans l’onglet **Souches de numéros**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Générer un fichier de paiement positif pour un compte bancaire unique
Vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique. Pour en savoir plus sur la manière de générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps, référez-vous aux sections suivantes. Pour générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique, ouvrez la boîte de dialogue **Générer un fichier de paiement positif** depuis la page **Comptes bancaires**. Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif. Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez un compte bancaire pour lequel un paiement positif est mis en place.
3. Sélectionnez **Gérer les paiements \> Paiement positif \> Fichier de paiement positif**.
4. Définissez le champ **Date limite**. Les chèques émis avant cette date seront inclus.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Générer un fichier de paiement positif pour plusieurs comptes bancaires
Pour générer un fichier de paiement positif pour plusieurs comptes bancaires, utilisez la tâche périodique **Fichier de paiement positif**. Choisissez le format de paiement positif pour le fichier et spécifiez si le fichier doit être généré pour toutes les entités juridiques ou pour une entité juridique sélectionnée. Vous pouvez également générer le fichier de paiement positif pour tous les comptes bancaires qui utilisent le format de paiement positif spécifié ou pour un compte bancaire sélectionné. Dans le champ **Date limite**, entrez la dernière date de chèque à inclure dans le fichier de paiement positif. Tous les chèques qui n’ont pas été inclus dans un fichier de paiement positif avant la fin de cette date de chèque sont inclus dans le fichier.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Afficher les résultats de la génération du fichier de paiement positif
Une fois que le fichier de paiement positif est généré, vous pouvez afficher les résultats dans la page **Résumé du fichier de paiement positif**. Pour afficher les détails des chèques individuels, accédez à la page **Fichier de paiement positif**.

## <a name="confirm-a-positive-pay-file"></a>Confirmation d’un fichier de paiement positif
Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque. Vous pouvez ensuite confirmer le fichier de paiement positif. Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Entrer la confirmation**. Lorsque vous confirmez un fichier de paiement positif, le numéro de confirmation que vous recevez de la banque est enregistré.

## <a name="recall-a-positive-pay-file"></a>Rappeler un fichier de paiement positif
Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler. Dans la page **Résumé du fichier de paiement positif**, sélectionnez un fichier de paiement positif ayant le statut **Créé**, puis sélectionnez l’action **Rappeler**. Pour chaque chèque présent dans le fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé. Vous pouvez alors créer un nouveau fichier de paiement positif qui inclut le chèque rappelé.


Le fichier XML résultant sera téléchargé.
