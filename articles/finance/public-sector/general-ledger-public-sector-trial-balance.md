---
title: État Balance comptable avec le détail des transactions
description: Cette rubrique décrit l’état par défaut des balances comptables. Elle décrit également les blocs élémentaires associés à cet état et comment il est possible de modifier l’état pour l’adapter à vos exigences métier.
author: v-kiarnd
manager: AnnBe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-kiarnd
ms.search.validFrom: 2019-10-24
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 76b0560499532eb3e97b03a9e797a9168ebcbcdc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407934"
---
# <a name="trial-balance-with-transactional-detail-report"></a>État Balance comptable avec le détail des transactions

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l’état par défaut des balances comptables. Elle décrit également les blocs élémentaires associés à cet état et comment il est possible de modifier l’état pour l’adapter à vos exigences métier.

Vous pouvez utiliser l’état **Balance comptable avec le détail des transactions** pour afficher les détails de chaque transaction pour les comptes généraux. L’état couvre les informations suivantes : 

- Soldes d’ouverture
- Débits et crédits 
- Soldes qui en résultent pour une plage de dates de 31 jours ou moins

Pour les transactions, l’état comprend les informations suivantes : 

- Date de transaction
- N° document
- Numéro de compte
- Numéro de référence
- Dimension comptable
- Nom de dimension comptable
- Description de la transaction
- Débits ou crédits
- Solde courant pour l’année en cours, basé sur l’exercice fiscal en cours

Vous pouvez utiliser la balance comptable pour identifier les erreurs des soldes de compte. Tous les comptes avec des soldes débiteurs doivent être égaux à tous les comptes avec des soldes créditeurs. L’état comprend les informations des écritures comptables du journal des opérations diverses.

Vous pouvez filtrer les données selon l’un des éléments suivants :

- Transactions validées
- Transactions en attente (Ces transactions comprennent toutes les transactions qui ne sont pas validées.) 
- Toutes les transactions 

Si les transactions comprennent des dimensions financières, l’état affiche ces informations dans un compte général. Sinon, les informations des dimensions financières sont regroupées en haut de la page. 

Actuellement, l’état est exporté directement vers Microsoft Excel. 

## <a name="transaction-information-on-the-report"></a>Informations de transaction de l’état

Selon le type de transaction, comme une écriture comptable avancée (ALE) ou une commande fournisseur, les informations supplémentaires suivantes s’affichent sur l’état.

<table> 
<thead>
<tr>
<th>Type de transaction</th>
<th>Informations supplémentaires sur le document</th>
<th>Informations supplémentaires sur la description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<ul>
<li>N° document ALE</li>
<li>Règle de répartition</li>
<li>Transfert d’un journal des opérations diverses</li>
<li>Journal</li>
</ul>
</td>
<td>Numéro ALE ou numéro du journal des opérations diverses</td>
<td>Description de la ligne</td>
</tr>
<tr>
<td></td>
<td>Pas de données</td>
<td>Description de l’en-tête du journal ALE ou des opérations diverses</td>
</tr>
<tr>
<td>
<ul>
<li>N° document de facture</li>
<li>N° document d’avoir</li>
</ul>
</td>
<td>Numéro de facture</td>
<td>Numéro de fournisseur et nom du fournisseur</td>
</tr>
<tr>
<td></td>
<td>Date de la facture</td>
<td>Description de la ligne</td>
</tr>
<tr>
<td></td>
<td>Pas de données</td>
<td>Numéro de commande fournisseur et/ou numéro PA</td>
</tr>
<tr>
<td>N° document de paiement de la comptabilité fournisseur</td>
<td>Numéro de chèque ou numéro de transfert électronique de fonds (TEF)</td>
<td>Numéro de fournisseur – Nom du fournisseur pour le compte de paiement ou de facturation</td>
</tr>
<tr>
<td></td>
<td>Date du chèque, date du TEF ou date du règlement</td>
<td>Numéro de fournisseur et nom du fournisseur pour le compte commande d’origine</td>
</tr>
<tr>
<td>
<ul>
<li>Avoir financier</li>
<li>N° document de facture financière</li>
</ul>
</td>
<td>Numéro de facture financière</td>
<td>Numéro de client et nom du client</td>
</tr>
<tr>
<td></td>
<td>Code facturation</td>
<td>Description de la ligne de facture financière<br>
(Champ <strong>Description</strong> de l’organisateur <strong>Lignes de facture</strong> de la page <strong>Factures financières</strong>)</td>
</tr>
<tr>
<td>N° document de paiement de la comptabilité client</td>
<td>Numéro de lot du journal<br>
(Champ <strong>Numéro de lot du journal</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>Journal des paiements</strong>)</td>
<td>Numéro de client – Nom du client<br>
(Champs <strong>Compte</strong> et <strong>Nom du compte</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>N° document de journal</strong>)</td>
</tr>
<tr>
<td></td>
<td>Référence de paiement</td>
<td>Description de la ligne<br>
(Champ <strong>Description</strong> de l’onglet <strong>Vue d’ensemble</strong> de la page <strong>N° document de journal</strong>)</td>
</tr>
<tr>
<td>Écritures de registre budgétaires</td>
<td>Numéro d’écriture de registre budgétaire</td>
<td>Description de l’écriture de registre budgétaire</td>
</tr>
<tr>
<td></td>
<td>Code budgétaire</td>
<td>Code motif – Description de l’en-tête de l’écriture de registre budgétaire<br>
(Champ <strong>Commentaire</strong> de l’organisateur <strong>Détails sur l’écriture de compte budgétaire</strong> de la page <strong>Écriture budgétaire</strong> ou de la page <strong>Écriture de registre budgétaire</strong>)</td>
</tr>
<tr>
<td>
<ul>
<li>Confirmation de la commande fournisseur</li>
<li>N° document de la confirmation de commande fournisseur</li>
</ul>
</td>
<td>Numéro de commande fournisseur</td>
<td>Description de la ligne<br>
(Champ <strong>Texte</strong> de l’organisateur <strong>Détails de la ligne</strong> de la page <strong>Commande fournisseur</strong>).</td>
</tr>
<tr>
<td></td>
<td>Numéro de ligne de commande fournisseur</td>
<td>Catégorie d’approvisionnement</td>
</tr>
<tr>
<td>N° document de la demande d’achat</td>
<td>Numéro de demande d’achat</td>
<td>Nom de demande d’achat</td>
</tr>
<tr>
<td></td>
<td>Numéro de ligne de la demande d’achat</td>
<td>Description de la ligne de demande d’achat<br>
(Champ <strong>Nom du produit</strong> de l’organisateur <strong>Lignes de demande d’achat</strong> de la page <strong>Demande d’achat</strong>).</td>
</tr>
<tr>
<td>
<ul>
<li>N° document de facture de projet</li>
<li>Facture de projet</li>
</ul>
</td>
<td>Numéro de facture du projet</td>
<td>Compte de facturation et nom du compte</td>
</tr>
<tr>
<td></td>
<td>Source de financement</td>
<td>ID projet et nom du projet</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]