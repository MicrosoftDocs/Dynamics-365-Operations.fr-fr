---
title: Répartitions comptables et écritures de journal pour les factures fournisseur
description: Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont la dépense, l’immobilisation, la taxe ou les frais seront reportés sur la facture fournisseur. Chaque montant qui doit être pris en compte lorsque la facture fournisseur est journalisée aura une ou plusieurs répartitions comptables.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358179"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Répartitions comptables et écritures de journal pour les factures fournisseur

[!include [banner](../includes/banner.md)]

Les répartitions comptables permettent de définir la façon dont un montant sera pris en compte, par exemple, la manière dont la dépense, l’immobilisation, la taxe ou les frais seront reportés sur la facture fournisseur. Chaque montant qui doit être pris en compte lorsque la facture fournisseur est journalisée aura une ou plusieurs répartitions comptables. 

## <a name="accounting-distributions"></a>Répartitions comptables 

Vous pouvez utiliser les boutons suivants de la page Facture fournisseur pour afficher et éventuellement modifier les répartitions comptables pour chaque montant de la facture fournisseur.
-   **Répartir des montants** – permet d’afficher et de modifier les répartitions comptables pour une ligne individuelle et toutes les lignes enfants, telles que les taxes ou des frais. Vous pouvez également afficher et modifier les répartitions comptables de la ligne enfant directement dans la page **Transactions de taxe** ou la page **Transactions de frais**.
    -   Modifiez les montants d’en-tête de facture fournisseur, comme les frais ou les arrondis de devise.
    -   Modifiez les montants de ligne de facture fournisseur.
-   **Afficher les distributions** – Permet d’afficher les répartitions comptables pour toutes les lignes du document. Vous ne pouvez pas modifier les répartitions comptables de cette vue.
    -   Afficher les montants d’en-tête et de ligne.

Si la facture fournisseur fait référence à une commande fournisseur, vous pouvez fractionner et modifier les répartitions comptables pour les lignes contenant un article qui n’est pas stocké. Si la ligne de facture fournisseur ne fait pas référence à une ligne de commande fournisseur, vous pouvez également supprimer une répartition comptable. Vous ne pouvez pas fractionner ou supprimer des lignes pour les frais, les taxes et les remises ligne. Vous pouvez modifier le compte général, mais vous ne pouvez pas modifier les montants ou les pourcentages.
> [!NOTE]                                                                                                                                 
> Si la ligne parente contient un article qui n’est pas stocké et les répartitions comptables sont fractionnées, la ligne enfant fractionne automatiquement pour faire correspondre les dimensions financières de la ligne parente. Les répartitions comptables de la ligne enfant ne peuvent pas être fractionnées ni supprimées, mais selon le paramétrage de la ligne enfant, vous pouvez modifier le compte général pour les répartitions comptables de la ligne enfant.

## <a name="distributing-amounts"></a>Répartition des montants
Lorsque vous entrez une facture fournisseur, chaque montant est réparti comme suit.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de ligne de facture fournisseur</th>
<th>Ordre de priorité qui détermine à partir de quel emplacement le compte principal par défaut s’affiche</th>
<th>L’ordre de priorité qui détermine la dimension financière par défaut s’affiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produit stocké</td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur</li>
<li>Le champ <strong>Compte principal</strong> lorsque Dépenses d’achat pour le produit est sélectionné dans la page <strong>Validation</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut de la facture fournisseur.</li>
</ol></td>
</tr>
<tr class="even">
<td>Catégorie d’approvisionnement, ou produit non stocké.</td>
<td><ol>
<li>La répartition comptable pour a ligne de commande fournisseur, si la ligne de facture fournisseur fait référence à une ligne de commande fournisseur.</li>
<li>Le champ <strong>Compte principal</strong> lorsque Dépenses d’achat pour dépense est sélectionné dans la page <strong>Validation</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</li>
<li>Utilisez les valeurs de dimension financière par défaut de la facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Immobilisation</td>
<td><ol>
<li>La répartition comptable pour a ligne de commande fournisseur, si la ligne de facture fournisseur fait référence à une ligne de commande fournisseur.</li>
<li>Si <strong>Acquisition</strong> est sélectionné dans le champ <strong>Type de transaction</strong> de l’écran <strong>Facture fournisseur</strong>, le champ <strong>Compte principal</strong> lorsque <strong>Acquisition</strong> est sélectionné sur la page <strong>Profils de validation d’immobilisation</strong>.</li>
<li>Si <strong>Ajustement d’acquisition</strong> est sélectionné sur le champ <strong>Type de transaction</strong>, le champ <strong>Compte principal</strong> lorsque <strong>Ajustement d’acquisition</strong> est sélectionné dans la page <strong>Profils de validation d’immobilisation</strong>.</li>
</ol></td>
<td><ol>
<li>Utilisez la répartition comptable pour la ligne de commande fournisseur si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Projet défini sur la ligne de facture fournisseur.</td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Si <strong>Solde</strong> est sélectionné dans le champ <strong>Valider les coûts – Article</strong> de la page <strong>Groupes de projets</strong>, le champ <strong>Compte principal</strong> lorsque <strong>Coût</strong> est sélectionné dans la page <strong>Paramétrage de la validation dans la comptabilité</strong>.</li>
<li>Si <strong>Résultats</strong> est sélectionné dans le champ <strong>Valider les coûts – Article</strong> de la page <strong>Groupes de projets</strong>, le champ <strong>Compte principal</strong> lorsque <strong>Coût – Article</strong> est sélectionné dans la page <strong>Paramétrage de la validation dans la comptabilité</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Remise ligne</td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Le champ <strong>Compte principal</strong> lorsque <strong>Remise</strong> est sélectionné dans la page <strong>Validation</strong>.</li>
<li>Si aucun compte principal de remise n’est défini dans le profil de validation, la répartition comptable du prix global de la ligne de commande fournisseur.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières pour la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Frais en relation avec les achats, entrés sous l’onglet <strong>Prix et remise</strong> de la ligne de commande fournisseur</td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Répartition comptable du prix global sur la ligne de commande fournisseur.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Frais de ligne</td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Si <strong>Compte général</strong> est sélectionné dans le champ <strong>Type de débit</strong> de la page <strong>Code frais</strong>, le champ <strong>Compte à débiter</strong> de la page <strong>Code frais</strong>.</li>
<li>Si <strong>Article</strong> est sélectionné dans le champ <strong>Type de débit</strong> de l’écran <strong>Code frais</strong>, la répartition comptable pour le prix global sur la ligne de commande fournisseur.</li>
<li>Si <strong>Client/Fournisseur</strong> est sélectionné dans le champ <strong>Type de débit</strong> de l’écran <strong>Code frais</strong>, le champ <strong>Compte à créditer</strong> de la page <strong>Code frais</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Taxe, qui remplit la condition suivante :
<ul>
<li>L’option <strong>Appliquer les règles de la taxe américaine</strong> est sélectionnée dans la page <strong>Paramètres de comptabilité</strong>.</li>
</ul></td>
<td><ol>
<li>La répartition comptable pour la ligne de commande fournisseur, si la ligne de facture fait référence à une ligne de commande fournisseur.</li>
<li>Répartition comptable du prix global ou des frais.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Taxe, qui remplit les conditions suivantes :
<ul>
<li>L’option <strong>Appliquer les règles de la taxe américaine</strong> est désactivée dans la page <strong>Paramètres de comptabilité</strong>.</li>
<li>Le champ <strong>Taxe d’utilisation</strong> pour le groupe de taxe est désactivé dans la page <strong>Groupes de taxe</strong>.</li>
</ul></td>
<td><ol>
<li>Si le montant de la taxe est récupérable, le champ <strong>Taxe déductible</strong> de la page <strong>Groupes de validation dans la comptabilité</strong>.</li>
<li>Si le montant de la taxe n’est pas récupérable, le prix global ou la répartition comptable pour les frais.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières du prix global ou des répartitions comptables pour les frais de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Taxe, qui remplit les conditions suivantes :
<ul>
<li>L’option Appliquer les règles de la taxe américaine est désactivée dans la page <strong>Paramètres de comptabilité</strong>.</li>
<li>Le champ <strong>Taxe d’utilisation</strong> pour le groupe de taxe est sélectionné dans la page <strong>Groupes de taxe</strong>.</li>
</ul></td>
<td><ol>
<li>Si le montant de la taxe est récupérable, le champ <strong>Taxe déductible</strong> de la page <strong>Groupes de validation dans la comptabilité</strong>.</li>
<li>Si le montant de la taxe n’est pas récupérable, le champ <strong>Dépenses de taxe d’utilisation</strong> de la page <strong>Groupes de validation dans la comptabilité</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières du prix global ou des répartitions comptables pour les frais de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Frais d’en-tête</td>
<td><ol>
<li>Si <strong>Compte général</strong> est sélectionné dans le champ <strong>Type de débit</strong> de la page <strong>Code frais</strong>, le champ <strong>Compte à débiter</strong> de la page <strong>Code frais</strong>.</li>
<li>Si <strong>Client/Fournisseur</strong> est sélectionné dans le champ <strong>Type de débit</strong> de l’écran <strong>Code frais</strong>, le champ <strong>Compte à créditer</strong> de la page <strong>Code frais</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Si le compte principal est un compte de répartition, utilisez la valeur par défaut de la définition du compte de répartition.</li>
<li>Utilisez les valeurs du modèle par défaut de dimension financière de l’en-tête de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Remise d’en-tête</td>
<td><ol>
<li>Le champ <strong>Compte principal</strong> pour le <strong>type de validation de remise sur la facture fournisseur</strong> dans la page <strong>Comptes pour transactions automatiques</strong>.</li>
</ol></td>
<td><ol>
<li>Si la ligne de facture fait référence à une ligne de commande fournisseur, utilisez la répartition comptable pour la ligne de commande fournisseur.</li>
<li>Utilisez les dimensions financières des répartitions comptables pour le prix global de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimensions financières de la ligne de facture fournisseur.</li>
<li>Utilisez les valeurs de dimension financière par défaut du compte principal dans la page <strong>Plan comptable</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Répartition des taxes

Il est impossible de créer des répartitions comptables pour les taxes tant que ces dernières n’ont pas été calculées. Pour calculer les taxes, vous devez effectuer l’une des tâches suivantes dans la page **Facture fournisseur** :
-   Afficher le total de la facture.
-   Afficher la taxe.
-   Afficher le journal de comptabilité auxiliaire.
-   Afficher les répartitions comptables pour toute la facture fournisseur.
-   Placer une facture fournisseur en attente.
-   Valider la facture fournisseur.

## <a name="subledger-journals-for-vendor-invoices"></a>Journaux de comptabilité auxiliaire pour les factures fournisseur
Avant de valider une facture fournisseur, vous pouvez afficher l’écriture comptable complète de la facture, qui inclut des débits et des crédits, pour vérifier que la facture est validée dans les comptes corrects. Cette vue de l’écriture de compte complète est appelée écriture de journal de comptabilité auxiliaire. 

Si l’écriture de journal de comptabilité auxiliaire est incorrecte lorsque vous en affichez un aperçu avant de journaliser la facture fournisseur, vous ne pouvez pas la modifier. Vous devez plutôt modifier les répartitions comptables ou le profil de validation. Les répartitions comptables permettent de définir un côté de l’écriture de compte, de débit ou de crédit. L’écriture de compte de journal de comptabilité auxiliaire de contrepartie est créée à l’aide des profils de validation, par exemple le compte fournisseur ou la taxe.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
