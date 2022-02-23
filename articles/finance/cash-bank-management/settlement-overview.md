---
title: Vue d’ensemble des règlements
description: Cette rubrique fournit des informations générales sur le processus de règlement. Elle décrit les types de transaction pouvant être réglés, ainsi que le calendrier et le processus de règlement. Elle décrit également les résultats du processus de règlement.
author: kweekley
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 650b0ef0123cf9acf42c2e7460693b555897744f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443159"
---
# <a name="settlement-overview"></a>Vue d’ensemble des règlements

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales sur le processus de règlement. Elle décrit les types de transaction pouvant être réglés, ainsi que le calendrier et le processus de règlement. Elle décrit également les résultats du processus de règlement.

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

## <a name="additional-resources"></a>Ressources supplémentaires

- [Solde de règlement](settle-remainder.md)
