---
title: Résoudre les problèmes liés aux accusés de réception de marchandises et à la facturation
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des accusés de réception de marchandises et la facturation.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428313"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Résoudre les problèmes liés aux accusés de réception de marchandises et à la facturation

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lorsque vous utilisez des accusés de réception de marchandises et la facturation.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Je ne peux pas valider plus d'une facture pour une ligne de commande fournisseur contenant des articles basés sur la catégorie.

Une quantité est obligatoire si vous souhaitez valider des factures. Par conséquent, si la quantité totale d'une ligne n'a été facturée que pour un montant partiel, vous ne pourrez pas facturer le montant restant sur une autre facture.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Je reçois une erreur "Référence d'objet non définie" lors de la confirmation de la commande fournisseur, ou une exception "Une exception a été levée par la cible d'un appel" se produit lors de la validation de la facture fournisseur.

Ce problème peut se produire en raison d'une incohérence dans les répartitions des commandes fournisseur.

Pour débloquer ce problème et réinitialiser la commandes fournisseur sur l'état *Brouillon*, allez dans **Approvisionnements \> Tâches périodiques \> Nettoyer \> Réinitialisation de la répartition des commandes fournisseur**. Pour plus d'informations, consultez l'article de blog suivant : [Résoudre les erreurs de répartition des commandes fournisseur dans Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Je ne peux pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur.

Vous ne pouvez pas consolider plusieurs accusés de réception de marchandises en une seule commande fournisseur si les différentes lignes d'accusé de réception de marchandises ont des dates comptables différentes.

Dans les versions antérieures de Microsoft Dynamics 365 Supply Chain Management, la consolidation était autorisée dans cette situation. Cependant, la pratique pouvait causer des erreurs. La date comptable sur les lignes de commande fournisseur qui sont créées ne doit pas différer de la date comptable sur les lignes d'accusé de réception de marchandises à partir desquelles ces lignes de commande fournisseur ont été créées. (La date comptable sur les lignes de commande fournisseur correspond à la date comptable sur l'en-tête de commande fournisseur.) Par conséquent, la consolidation de plusieurs accusés de réception de marchandises en une seule commande fournisseur n'est plus autorisée.

La date comptable est utilisée, par exemple, pour les réservations budgétaires et les engagements. Par conséquent, elle doit être conservée pendant la transition de l'accusé de réception de marchandises à la commande fournisseur.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>Lorsque les accusés de réception de marchandises sont annulés, les transactions peuvent être imputées sur un compte général suspendu.

### <a name="issue-description"></a>Description du problème

Si un accusé de réception de marchandises est annulé, le système autorise la validation des transactions sur les comptes généraux suspendus, même si les comptes principaux sont suspendus.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Sur la page **Paramètres de la comptabilité fournisseur**, sur l'onglet **Général**, assurez-vous que l'option **Valider l'accusé de réception de marchandises dans la comptabilité** est définie sur *Oui*.
1. Créez une commande fournisseur et ajoutez une ligne de commande d'une quantité de *1 000* pour un produit.
1. Confirmez la commande fournisseur.
1. Validez l'accusé de réception de marchandises et vérifiez les bons.
1. Suspendez les comptes principaux concernés, *200140* et *140200*.
1. Annulez l'accusé de réception de marchandises validé.
1. Notez que les transactions peuvent être validées sur les comptes généraux suspendus.

### <a name="issue-resolution"></a>Résolution du problème

Les transactions peuvent être validées sur les comptes généraux suspendus lorsque les accusés de réception de marchandise sont annulés, car ce comportement permet des validations correctes.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Un numéro document d'accusé de réception de marchandises est consommé même si aucun document financier n'est généré lors de la réception de produit.

Si l'option **Provisionner le passif sur l'accusé de réception de marchandises** est définie sur *Non* pour le groupe de modèles d'article, aucune validation dans la comptabilité n'aura lieu. Cependant, un événement physique sera enregistré à des fins de comptabilisation dans une comptabilité auxiliaire, et cet événement nécessite un numéro de document. Ce numéro de document est le numéro de document qui est référencé dans les mouvements de stock.

Nous vous recommandons de définir l'option **Provisionner le passif sur l'accusé de réception de marchandises** sur *Oui*, comme décrit dans l'article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Le paramètre Valider sur le compte de frais dans la comptabilité n'est pas activé.

### <a name="issue-description"></a>Description du problème

Ce problème se produit lorsqu'une commande fournisseur est facturée, si l'option **Valider sur le compte de frais dans la comptabilité** est définie sur *Oui* sur l'onglet **Facture** de la page **Paramètres de la comptabilité fournisseur**.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
1. Sur l'onglet **Facture**, définissez l'option **Valider sur le compte de frais dans la comptabilité** sur *Oui*.
1. Accédez à **Gestion des stocks \> Paramétrage \> Validation \> Validation**.
1. Sur l'onglet **Commande fournisseur**, assurez-vous d'avoir supprimé toutes les lignes de dépenses d'achat pour le produit.
1. Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Création d'une commande fournisseur. Dans le champ **Compte fournisseur**, sélectionnez *1001 Fournitures de bureau Acme*.
1. Ajoutez une ligne de commande fournisseur avec les paramètres suivants :

    - **Numéro d'article :** *Projecteur laser D0011*
    - **Site :** *1*
    - **Entrepôt :** *11*
    - **Quantité :** *4*

1. Dans le volet Actions, sous l'onglet **Achats**, dans le groupe **Action**, cliquez sur **Confirmer**.
1. Dans le volet Actions, sous l'onglet **Recevoir**, dans le groupe **Générer**, sélectionnez **Accusé de réception de marchandises**.
1. Dans la boîte de dialogue **Validation de l’accusé de réception de produits**, dans le champ **Accusé de réception de produits**, entrez un nombre arbitraire, puis sélectionnez **OK**.
1. Dans le volet Actions, sous l'onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
1. Dans le champ **Numéro**, entrez un numéro arbitraire comme numéro de facture.
1. Mettez à jour le statut de rapprochement et validez.
1. Notez que vous recevez maintenant l'erreur suivante lorsque vous générez une facture à partir d'une commande fournisseur : "Le numéro de compte pour le type de transaction Dépenses d'achat pour le produit n'existe pas".

### <a name="issue-resolution"></a>Résolution du problème

Cela dépend des paramètres des factures et des groupes de factures. Pour plus d'informations, consultez l'article de blog suivant : [Comptabilité pour les frais d'achat et la variation des stocks](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]