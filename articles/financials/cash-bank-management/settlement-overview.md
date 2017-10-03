---
title: "Vue d'ensemble des règlements"
description: "Cet article fournit des informations générales sur le processus de règlement. Il décrit les types de transactions pouvant être réglées, quand et comment les transactions peuvent être réglées ainsi que les résultats du processus de règlement."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: ab12ef4127daf57fb0816ae1585876b50d1e81ed
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="settlement-overview"></a>Vue d'ensemble des règlements

[!include[banner](../includes/banner.md)]


Cet article fournit des informations générales sur le processus de règlement. Il décrit les types de transactions pouvant être réglées, quand et comment les transactions peuvent être réglées ainsi que les résultats du processus de règlement.

Lors d'un règlement, les transactions dans un document sont appliquées aux transactions dans un autre document pour augmenter ou diminuer le solde de chaque document. Par exemple, un paiement peut être appliqué à une facture. Différents types de transaction peuvent être réglés, à différents moments et par différentes méthodes. Un règlement peut également entraîner la génération de nouvelles transactions.

## <a name="what-transactions-can-be-settled"></a>Quelles transactions peuvent être réglées
Un règlement dans la comptabilité fournisseur et la comptabilité client peut être effectué entre les types de transaction qui affectent le solde fournisseur ou le solde client, tels que des factures, paiements, avoirs et frais. Tout type de transaction peut être réglé pour un autre type de transaction. Par exemple, vous pouvez régler un paiement pour une facture, un avoir pour une facture, une facture pour une facture et un paiement pour un paiement. Vous pouvez régler des paiements pour une transaction dans la même entité juridique ou dans une autre entité juridique. Dans les organisations qui utilisent un modèle de paiement centralisé, les [paiements centralisés](set-up-centralized-payments.md) permettent de simplifier le processus de paiement.

## <a name="when-to-settle-transactions"></a>Quand régler des transactions
Les transactions peuvent être réglées au moment de la saisie du paiement. Par exemple, lorsque vous effectuez un paiement à un fournisseur, vous sélectionnez généralement les factures à payer. En sélectionnant les factures, vous les marquez pour règlement par rapport au paiement. Lorsque les commis aux paiements de la comptabilité client enregistrent un paiement client, ils peuvent marquer les factures appropriées pour règlement, selon les informations fournies avec le paiement du client. La page **Régler les transactions** permet de marquer les transactions pour règlement. Cette page peut être ouverte à partir d'une facture ou d'un paiement non validé. Lorsque la transaction est validée, le règlement l'est également. Les transactions peuvent également être réglées après leur validation. Vous pouvez entrer et valider un paiement client sans le régler pour des factures. Toutefois, vous devez d'abord effectuer des recherches pour vérifier que le paiement est réglé pour la facture appropriée. La page **Régler les transactions** peut être ouverte à partir de la page **Tous les clients** ou **Tous les fournisseurs**, ou de la page **Transactions** pour un client ou fournisseur. Vous pouvez également réserver des acomptes validés pour une facture en marquant le paiement pour règlement par rapport à une commande fournisseur ou une commande client. Dans ce cas, le paiement a toujours un solde en cours, mais il ne peut pas être réglé par rapport à une autre facture. Le paiement sera réglé automatiquement par rapport à la facture qui a été créée à partir de la commande fournisseur ou de la commande client.

## <a name="how-to-settle-transactions"></a>Comment régler des transactions
Les transactions peuvent être réglées manuellement, automatiquement ou en utilisant une combinaison des deux méthodes. Le choix d'un mode de règlement dépend des processus d'entreprise, qui peuvent ensuite être implémentés via le paramétrage du règlement dans les paramètres de la comptabilité fournisseur et les paramètres de la comptabilité client. Vous pouvez créer des paiements fournisseur et des paiements client de débit direct à l'aide d'une proposition de paiement, utilisée pour sélectionner les factures à payer. La proposition de paiement est activée manuellement, mais Microsoft Dynamics 365 for Finance and Operations marque automatiquement les factures sélectionnées pour règlement lorsque les paiements sont créés. Si les paiements sont créés manuellement, vous pouvez utiliser la page **Régler les transactions** pour sélectionner les factures pour règlement. Vous pouvez sélectionner manuellement les factures, ou vous pouvez utiliser l'option **Marquer par priorité** pour marquer automatiquement les factures pour règlement. L'option **Marquer par priorité** n'est disponible que pour la comptabilité client. Pour activer cette option, utilisez la page **Priorité de règlement** dans les paramètres de la comptabilité client. Si un commis aux paiement entre un paiement, mais ne règle pas ce paiement avant de le valider, le paiement peut être réglé automatiquement. Vous pouvez activer le règlement automatique dans les paramètres de la comptabilité client et de la comptabilité fournisseur. Lorsque vous utilisez le règlement automatique, vous pouvez utiliser l'ordre de règlement prédéfini, ou vous pouvez définir votre propre ordre de priorité de règlement dans les paramètres de la comptabilité client. Cette fonctionnalité n'est disponible que pour la comptabilité client.

## <a name="results-of-settlement"></a>Résultats du règlement
Lorsque les transactions sont réglées, le solde impayé de chaque transaction est augmenté ou diminué selon le cas. Dans un scénario classique, lorsqu'une facture et un paiement sont réglés, le statut et le solde de chaque transaction sont mis à jour selon les règles suivantes :

-   Si le montant du paiement est supérieur au montant de la facture, le solde de la facture est réduit à 0,00 et la facture est clôturée. Le paiement reste en cours et le solde est égal au montant du trop-perçu.
-   Si le montant du paiement est inférieur au montant de la facture, le solde est réduit à 0,00 et le paiement est clôturé. La facture reste en cours et le solde est égal au montant du moins-perçu.
-   Si le montant du paiement est égal au montant de la facture, le paiement et la facture sont clôturés et leur solde est de 0,00.

Si un [paiement est inférieur au montant de la facture](../accounts-payable/vendor-payments-partial-amount.md) en raison d'un escompte de règlement, d'une annulation ou d'un moins-perçu, la facture et le paiement peuvent toujours être clôturés, selon le paramétrage du règlement dans les paramètres de la comptabilité fournisseur et les paramètres de la comptabilité client. Le règlement peut également générer des transactions. Par exemple, le règlement d'une facture et d'un paiement peut produire un escompte de règlement, un profit ou une perte réalisé, des ajustements de taxe, des annulations ou des différences minimes.



