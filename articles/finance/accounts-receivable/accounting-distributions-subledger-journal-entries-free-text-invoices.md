---
title: Répartitions comptables et écritures de journal pour les factures financières
description: Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière. Chaque montant qui doit être pris en compte lorsque la facture financière est journalisée aura une ou plusieurs répartitions comptables.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5120c4e75e821776201d5add2d498feb94d0297
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778409"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>Répartitions comptables et écritures de journal pour les factures financières

[!include [banner](../includes/banner.md)]

Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont le produit, la taxe ou les frais seront reportés sur une facture financière. Chaque montant qui doit être pris en compte lorsque la facture financière est journalisée aura une ou plusieurs répartitions comptables.

## <a name="accounting-distributions"></a>Répartitions comptables

Vous pouvez utiliser les boutons suivants sur la page **Facture financière** pour afficher et éventuellement modifier les répartitions comptables pour chaque montant de la facture financière.

-   **Répartir les montants** : Permet d’afficher et de modifier les répartitions comptables pour une ligne individuelle et toutes les lignes enfants, telles que des taxes ou des frais. Vous pouvez également afficher et changer les répartitions comptables de la ligne enfant directement dans la page **Transactions de taxe** ou la page **Transactions de frais**.
    -   Modifiez les montants d’en-tête de facture financière, comme les frais ou les arrondis de devise.
    -   Modifiez les montants de la ligne de facture financière.
-   **Afficher les distributions** : Permet d’afficher les répartitions comptables pour toutes les lignes du document. Vous ne pouvez pas modifier les répartitions comptables de cette vue.
    -   Afficher les montants d’en-tête et de ligne.

## <a name="distributing-amounts"></a>Répartition des montants
Lorsque vous entrez une facture financière, chaque montant est réparti comme suit.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de montant en devises</th>
<th>Origine de l’affichage du compte principal</th>
<th>L’ordre de priorité qui détermine la dimension financière par défaut s’affiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ligne de facture financière</td>
<td>Compte général de la ligne de facture financière.</td>
<td><ol>
<li>Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</li>
<li>Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte général sur la page Plan de comptes.</li>
</ol></td>
</tr>
<tr class="even">
<td>Ligne de facture financière pour une combinaison numéro d’immobilisation et modèle de valeur
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Remarque </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Le compte principal sur la ligne de facture financière correspond au compte de la cession d’immobilisation.</td>
</tr>
</tbody>
</table>
</div></td>
<td>Compte général de la ligne de facture financière.</td>
<td><ol>
<li>Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte général sur la page Plan de comptes.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Montant de remise de facture financière</td>
<td>Champ Compte principal pour les remises client sur la page Escomptes de règlement.</td>
<td><ol>
<li>Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</li>
<li>Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte général sur la page Plan de comptes.</li>
</ol></td>
</tr>
<tr class="even">
<td>Montant de la taxe de la facture financière</td>
<td>Champ Taxe collectée sur la page Groupes de validations dans la comptabilité.</td>
<td><ol>
<li>Utilisez les dimensions financières définies sur le montant de la ligne de facture financière ou les répartitions pour le montant de la ligne de frais.</li>
<li>Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte général sur la page Plan de comptes.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Montant de la ligne de frais de la facture financière</td>
<td>Champ Compte à créditer sur la page Code frais.</td>
<td><ol>
<li>Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</li>
<li>Si le compte principal n’est pas un compte de répartition, utilisez le modèle par défaut de dimension financière sur la ligne de facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut sur la ligne de la facture financière.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte général sur la page Plan de comptes.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Répartition des taxes
Il est impossible de créer des répartitions comptables pour les taxes tant que ces dernières n’ont pas été calculées. Pour calculer les taxes, vous devez effectuer l’une des tâches suivantes sur la page **Facture financière** :
-   Afficher la taxe.
-   Afficher le total de la facture.
-   Afficher le flux de trésorerie.
-   Afficher les répartitions comptables pour la facture financière entière.
-   Afficher le journal de comptabilité auxiliaire.

## <a name="subledger-journals-for-free-text-invoices"></a>Journaux de comptabilité auxiliaires pour les factures financières
Avant de valider une facture financière, vous pouvez afficher l’écriture de compte complète de la facture, qui inclut des débits et des crédits, pour vérifier que la facture est imputée dans les comptes corrects. Cette vue de l’écriture de compte complète est appelée écriture de journal de comptabilité auxiliaire. Si l’écriture de journal de comptabilité auxiliaire est incorrecte lorsque vous en affichez un aperçu avant de journaliser la facture financière, vous ne pouvez pas la modifier. Vous devez plutôt modifier les répartitions comptables ou le profil de validation. Les répartitions comptables permettent de définir un côté de l’écriture de compte, de débit ou de crédit. L’écriture de compte de journal de comptabilité auxiliaire de contrepartie est créée à l’aide des profils de validation, par exemple le compte client ou la taxe.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
