---
title: "Solde de règlement"
description: "Vous pouvez régler le montant restant de l'activité de règlement en appliquant ce montant à un compte général."
author: mikefalkner
manager: aolson
ms.date: 10/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: e67bd36adc92bffea48087d0322ab14e9c066a4e
ms.contentlocale: fr-fr
ms.lasthandoff: 12/06/2018

---

# <a name="settle-remainder"></a>Solde de règlement

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

Vous pouvez régler le montant restant de l'activité de règlement en appliquant ce montant à un compte général ou à un autre client. Vous pouvez régler le solde lorsque vous réglez des montants entrés dans un journal ou lorsque vous réglez uniquement les transactions en cours.

## <a name="setting-up-defaults"></a>Paramétrage des valeurs par défaut 
Vous devez activer la fonctionnalité Solde de règlement et définir les paramètres par défaut avant d'utiliser Solde de règlement

1)  Cliquez sur **Comptabilité client > Paramètres > Règlements** ou **Comptabilité fournisseur > Paramètres > Règlements**
2)  Sélectionnez l'onglet **Règlement** et cliquez sur **Activer le solde de règlement**
3)  Dans **Code motif par défaut**, sélectionnez un code motif par défaut. Les codes motif doivent avoir déjà été paramétrés dans **Comptabilité client > Paramétrage > Codes de motif d'annulation client** ou **Comptabilité fournisseur > Paramétrage > Codes de motif d'annulation client**. Le **Compte de solde de règlement par défaut** prendra comme valeur par défaut le compte affecté au code motif d'annulation.
3)  Mettez à jour le **Compte de solde de règlement par défaut** si nécessaire.
4)  Dans **Nom du journal par défaut**, sélectionnez un journal des paiements qui sera utilisé si vous souhaitez créer un journal des paiements lorsque vous réglez uniquement des transactions en cours. Si vous activez la fonctionnalité de solde de règlement, vous devez ajouter un nom de journal par défaut.

## <a name="settle-remainder-from-a-journal"></a>Solde de règlement d'un journal
Si vous n'activez pas la fonctionnalité **Solde de règlement**, vous pouvez toujours entrer une transaction dans un journal et ensuite régler des transactions à l'aide de celle-ci comme par le passé. Lorsque vous cliquez sur le bouton **OK**, le solde en cours sur la facture est réduit du montant de disponibilités. Si les disponibilités ne règlent pas complètement la facture, la facture reste en cours avec un montant restant à régler ultérieurement.

Lorsque la fonctionnalité **Solde de règlement** est activée, vous pouvez régler le montant restant sur un compte général. Vous pouvez également transférer le solde vers un autre compte client (pour les transactions client) ou un autre fournisseur (pour les transactions fournisseur) au lieu de laisser les factures en cours. 

Pour régler le solde de la page **Règlement**, procédez comme suit :

1)  Sur la page **Règlement**, sélectionnez les factures ou les transactions à régler.
2)  Cliquez sur le bouton **Solde de règlement**.
3)  Une boîte de dialogue s'affiche, affichant le montant qui sera réglé sur un compte général, la date qui sera utilisée pour régler le solde, le code motif par défaut des paramètres, et le compte par défaut des paramètres. 
4)  Sélectionnez un nouveau motif de règlement si vous souhaitez modifier le motif par défaut. Le compte de règlement sera modifié avec le compte associé au code motif.
5)  Modifiez le compte de règlement si vous le souhaitez.
6)  Si vous réglez des transactions client et que vous souhaitez déplacer le solde vers un autre client, sélectionnez un client dans **Solde de règlement du compte client**. Si vous réglez des transactions fournisseur et que vous souhaitez déplacer le solde vers un autre fournisseur, sélectionnez un fournisseur dans **Solde de règlement du compte fournisseur**.
6)  Cliquez sur **Solde de règlement**.
7)  La page **Journal** s'affiche. Une ligne de journal supplémentaire sera ajoutée au journal avec le montant du solde de règlement comme montant et le compte de montant de règlement comme compte de contrepartie. Si vous avez ajouté un client ou fournisseur afin de pouvoir déplacer le montant du règlement vers un autre client ou fournisseur, une ligne supplémentaire sera ajoutée au journal pour déplacer le montant du règlement vers ce client ou fournisseur.

Lorsque vous validez le journal, la transaction en cours est entièrement réglée. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Régler le solde lorsque vous réglez uniquement les transactions en cours
Vous pouvez également régler le solde lorsque vous réglez des transactions en cours sans journal.

Pour régler le solde, procédez comme suit :

1)  Sur la page **Règlement**, sélectionnez les factures ou les transactions à régler
2)  Cliquez sur **Solde de règlement**
3)  Une boîte de dialogue s'affiche, affichant le montant qui sera réglé sur un compte général, la date qui sera utilisée pour régler le solde, le code motif par défaut des paramètres, et le compte par défaut des paramètres. 
4)  Sélectionnez un nouveau motif de règlement si vous souhaitez modifier le motif par défaut. Le compte de règlement sera modifié avec le compte associé au code motif.
5)  Modifiez le **compte de règlement** si vous le souhaitez.
6)  Si vous réglez des transactions client et que vous souhaitez déplacer le solde vers un autre client, sélectionnez un client dans **Solde de règlement du compte client**. Si vous réglez des transactions fournisseur et que vous souhaitez déplacer le solde vers un autre fournisseur, sélectionnez un fournisseur dans **Solde de règlement du compte fournisseur**
7)  Vous pouvez également choisir de créer un journal des paiements avec le solde de règlement ou seulement le valider sans journal. Sélectionnez **Oui** pour **Modifier dans le journal** pour créer un journal des paiements. Vous pourrez modifier le journal des paiements que vous créez.
8)  Cliquez sur **Solde de règlement**. Si vous choisissez de créer un journal, le bouton devient **Créer un journal**. Cliquez sur **Créer un journal** à la place.
9)  Si vous avez créé un journal des paiements, la page du journal s'ouvre lorsque vous cliquez sur **Solde de règlement**. Une ligne de journal sera ajoutée au journal avec le montant du solde de règlement comme montant et le compte de montant de règlement comme compte de contrepartie. Si vous avez ajouté un client ou fournisseur afin de pouvoir déplacer le montant du règlement vers un autre client ou fournisseur, une ligne supplémentaire sera ajoutée au journal pour déplacer le montant du règlement vers ce client ou fournisseur.

