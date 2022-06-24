---
title: Vue d’ensemble des règlements
description: Cet article fournit des informations générales sur le processus de règlement. Elle décrit les types de transaction pouvant être réglés, ainsi que le calendrier et le processus de règlement. Elle décrit également les résultats du processus de règlement.
author: panolte
ms.date: 07/30/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: a495a71a95032a0022cbab2783f356db48ee349d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887946"
---
# <a name="settlement-overview"></a>Vue d’ensemble des règlements

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Cet article fournit des informations générales sur le processus de règlement. Elle décrit les types de transaction pouvant être réglés, ainsi que le calendrier et le processus de règlement. Elle décrit également les résultats du processus de règlement.

Lors d’un règlement, les transactions dans un document sont appliquées aux transactions dans un autre document pour augmenter ou diminuer le solde de chaque document. Par exemple, un paiement peut être appliqué à une facture. Différents types de transaction peuvent être réglés, à différents moments et par différentes méthodes. Le processus de règlement peut également générer de nouvelles transactions.

## <a name="what-transactions-can-be-settled"></a>Quelles transactions peuvent être réglées

Dans Comptabilité fournisseur et Comptabilité client, le règlement peut être effectué entre les types de transaction qui affectent le solde fournisseur ou le solde client. Ces types de transactions peuvent inclure des factures, des paiements, des notes de crédit et des frais. Tout type de transaction peut être réglé pour un autre type de transaction. Par exemple, vous pouvez régler un paiement pour une facture, un avoir pour une facture, une facture pour une autre facture et un paiement pour un autre paiement.

Vous pouvez régler des paiements pour une transaction dans la même entité juridique ou dans une autre entité juridique. Dans les organisations qui utilisent un modèle de paiement centralisé, les [paiements centralisés](set-up-centralized-payments.md) permettent de simplifier le processus de paiement.

## <a name="when-to-settle-transactions"></a>Quand régler des transactions

Les transactions peuvent être réglées lors de la saisie des paiements. Par exemple, lorsque vous effectuez un paiement à un fournisseur, vous sélectionnez généralement les factures à payer. En sélectionnant les factures, vous les marquez pour règlement par rapport au paiement. Lorsque les commis aux paiements de la comptabilité client enregistrent un paiement client, ils peuvent marquer les factures appropriées pour règlement, selon les informations fournies avec le paiement de chaque client. Utilisez la page **Régler les transactions** pour marquer les transactions pour règlement. Vous pouvez ouvrir cette page à partir d’une facture ou d’un paiement non validé. Lorsque la transaction est validée, le règlement l’est également. 

Les transactions peuvent également être réglées après leur validation. Vous pouvez entrer et valider un paiement client sans le régler pour des factures. Toutefois, vous devez d’abord effectuer des recherches pour vérifier que le paiement est réglé pour la facture appropriée. La page **Régler les transactions** peut être ouverte à partir de la page **Tous les clients** ou **Tous les fournisseurs**, ou de la page **Transactions** pour un client ou fournisseur.

Vous pouvez également réserver des acomptes validés pour une facture en marquant le paiement pour règlement par rapport à une commande fournisseur ou une commande client. Dans ce cas, le paiement a toujours un solde en cours, mais il ne peut pas être réglé par rapport à une autre facture. Le paiement sera réglé automatiquement par rapport à la facture qui a été créée à partir de la commande fournisseur ou de la commande client.

## <a name="how-to-settle-transactions"></a>Comment régler des transactions

Les transactions peuvent être réglées manuellement, automatiquement ou en utilisant une combinaison des deux méthodes. Le choix d’un mode de règlement dépend de vos processus d’affaires. Sur les pages **Paramètres des comptes fournisseurs** et **Paramètres des comptes clients**, vous pouvez configurer le processus de règlement afin qu’il soit aligné sur ces processus métier.

Vous pouvez créer des paiements fournisseur et des paiements par prélèvement automatique en utilisant une proposition de paiement. Une proposition de paiement est utilisée pour sélectionner les factures à payer. La proposition de paiement est activée manuellement, puis le système marque automatiquement les factures sélectionnées pour règlement lorsque les paiements sont créés.

Si les paiements sont créés manuellement, vous pouvez utiliser la page **Régler les transactions** pour sélectionner les factures pour règlement. Vous pouvez sélectionner manuellement les factures, ou vous pouvez utiliser l’option **Marquer par priorité** pour marquer automatiquement les factures pour règlement. L’option **Marquer par priorité** n’est disponible que pour la comptabilité client. Vous pouvez activer cette option sur l’onglet **Priorité de règlement** de la page **Paramètres des comptes clients**.

Si un commis aux paiement entre un paiement mais ne règle pas ce paiement avant de le valider, le paiement peut être réglé automatiquement. Vous pouvez activer le règlement automatique dans les pages **Paramètres de la comptabilité client** et **Comptabilité fournisseur**. Le règlement automatique règle les transactions uniquement dans la même entité juridique. Il ne règle pas les transactions entre plusieurs entités juridiques.

Lorsque vous utilisez le règlement automatique, vous pouvez utiliser la priorité de règlement prédéfini, ou vous pouvez définir votre propre ordre de priorité de règlement dans la page **Paramètres de la comptabilité client**. Cette fonctionnalité n’est disponible que pour la comptabilité client.

## <a name="results-of-settlement"></a>Résultats du règlement

Lorsque les transactions sont réglées, le solde impayé de chaque transaction est augmenté ou diminué selon le cas. Habituellement, dans un scénario classique, lorsqu’une facture et un paiement sont réglés, le statut et le solde de chaque transaction sont mis à jour selon les règles suivantes :

- Si le montant du paiement est supérieur au montant de la facture, le solde de la facture est réduit à 0,00 et la facture est clôturée. Le paiement reste en cours et le solde est égal à la différence entre le montant du paiement et le montant de la facture.
- Si le montant du paiement est inférieur au montant de la facture, le solde est réduit à 0,00 et le paiement est clôturé. La facture reste en cours et le solde est égal à la différence entre le montant de la facture et le montant du paiement.
- Si le montant du paiement est égal au montant de la facture, le paiement et la facture sont clôturés et leur solde est réduit à 0,00.

Si le [paiement est inférieur au montant de la facture](../accounts-payable/vendor-payments-partial-amount.md) en raison d’un escompte de règlement, d’une annulation ou d’un moins-perçu, la facture et le paiement peuvent toujours être clôturés, selon le mode de configuration des règlements dans les pages **Paramètres de la comptabilité fournisseur** et **Paramètres de la comptabilité client**.

Les règlements peuvent également générer des transactions. Par exemple, le règlement d’une facture et d’un paiement peut produire un escompte de règlement, un profit ou une perte réalisé, des ajustements de taxe, des annulations ou des différences minimes.

## <a name="identifying-marked-transactions-during-settlement"></a>Identification des transactions marquées lors du règlement

Lorsque vous essayez de régler une transaction, vous remarquerez peut-être un symbole qui indique que la transaction est marquée dans un autre emplacement. Dans ce cas, vous pouvez sélectionner la transaction sur la page **Règlement des transactions**, puis sélectionnez **Enquête \> Règlement depuis la fenêtre de règlement**. La vue de cette demande affiche les journaux, les commandes client, les factures, les propositions de paiement et les emplacements des clients qui pourraient bloquer la transaction du règlement. Pour résoudre le problème, vous pouvez sélectionner le lien pour passer directement de l’enquête à l’emplacement bloqué. Vous pouvez ensuite mettre à jour le document avec les ajustements nécessaires pour le régler. Vous pouvez également utiliser l’indicateur **Marqué** permettant d’identifier d’autres documents inclus dans le même emplacement de blocage.

## <a name="resolve-issues-with-transactions-that-cant-be-settled"></a>Résoudre les problèmes liés aux transactions qui ne peuvent pas être réglées

Parfois, vous ne pouvez pas régler les transactions car une autre activité traite actuellement le document. Si vous essayez de régler les transactions, une erreur se produit, car ces transactions sont utilisées. Pour résoudre ce problème, vous pouvez utiliser la page **Détails de la transaction marquée** pour rechercher les transactions marquées pour le règlement et identifier tout autre processus qui y accède.

Les transactions sont marquées pour le règlement lorsque des factures fournisseur sont payées ou lorsque des clients paient leurs factures en cours. Parfois, ces factures peuvent déjà être marquées pour le règlement. Par conséquent, les utilisateurs ne peuvent pas les sélectionner pour le paiement. Les factures peuvent être marquées par un autre journal des paiements client, commande client, journal des paiements fournisseur ou commande fournisseur dans l’entité juridique actuelle ou une autre entité juridique.

Si une transaction est bloquée pour le règlement lorsque vous saisissez un paiement client, ouvrez la page **Détails de la transaction marquée par le client** (**Comptabilité client \> Tâches périodiques \> Détails de la transaction marquée par le client**). Pour identifier rapidement l’endroit où une transaction est bloquée, vous pouvez définir n’importe lequel des paramètres de sélection suivants : **Compte client**, **Justificatif**, **Date** ou **Facture**. Si vous ne définissez aucun paramètre de sélection, le système affiche tous les documents bloqués de la société actuelle ou d’une autre société que vous sélectionnez. Une fois que la transaction qui a été bloquée pour le règlement est identifiée, vous pouvez la sélectionner, puis sélectionner **Supprimer le marquage des transactions sélectionnées**. La transaction sélectionnée est ensuite supprimée de tous les journaux l’incluant. Cependant, le document n’est pas supprimé de l’autre emplacement. Seules les informations de marquage sont supprimées de ce journal.

Si une transaction est bloquée pour le règlement lorsque vous saisissez un paiement fournisseur, ouvrez la page **Détails de la transaction marquée par le fournisseur** (**Comptabilité fournisseur \> Tâches périodiques \> Détails de la transaction marquée par le fournisseur**). Pour identifier rapidement l’endroit où une transaction est bloquée, vous pouvez définir n’importe lequel des paramètres de sélection suivants : **Compte fournisseur**, **Justificatif**, **Date** ou **Facture**. Si vous ne définissez aucun paramètre de sélection, le système affiche tous les documents bloqués de la société actuelle ou d’une autre société que vous sélectionnez. Une fois que la transaction est identifiée, vous pouvez la sélectionner, puis sélectionner **Supprimer le marquage des transactions sélectionnées** pour réparer le problème bloquant. La transaction sélectionnée est ensuite supprimée de tous les journaux l’incluant. Cependant, le document n’est pas supprimé de l’autre emplacement. Seules les informations de marquage sont supprimées de ce journal.

Pour identifier tous les documents bloqués, ouvrez la page **Tous les détails de la transaction marquée** (**Comptabilité client \> Tâches périodiques \> Tous les détails de la transaction marquée** ou **Comptabilité fournisseur \> Tâches périodiques \> Tous les détails de la transaction marquée**). Pour identifier rapidement l’endroit où une transaction est bloquée, vous pouvez définir n’importe lequel des paramètres de sélection suivants : **Compte client**, **Compte fournisseur**, **Justificatif**, **Date** ou **Facture**. Si vous ne définissez aucun paramètre de sélection, le système affiche tous les documents bloqués de la société actuelle ou d’une autre société que vous sélectionnez. Une fois que la transaction est identifiée, vous pouvez la sélectionner, puis sélectionner **Supprimer le marquage des transactions sélectionnées** pour réparer le problème bloquant. La transaction sélectionnée est ensuite supprimée de tous les journaux l’incluant. Cependant, le document n’est pas supprimé de l’autre emplacement. Seules les informations de marquage sont supprimées de ce journal.

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail **gestion des fonctionnalités** pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** gestion de la trésorerie et de la banque
- **Nom de la fonctionnalité :** Formulaire de détail de la transaction marquée

## <a name="additional-resources"></a>Ressources supplémentaires

- [Solde de règlement](settle-remainder.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
