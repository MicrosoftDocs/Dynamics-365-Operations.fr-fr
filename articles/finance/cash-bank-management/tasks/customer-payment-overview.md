---
title: Vue d’ensemble des paiements client
description: Cette procédure présente diverses méthodes utilisées pour entrer des paiements client.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b90b7f200133cfb0d30b335aca20c328856fba5
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778120"
---
# <a name="customer-payment-overview"></a>Vue d’ensemble des paiements client

[!include [banner](../../includes/banner.md)]

Cette procédure présente diverses méthodes utilisées pour entrer des paiements client. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à **Volet de navigation > Modules > Comptabilité client > Paiements > Journal des paiements**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez le journal des paiements dans lequel les paiements client seront enregistrés.
4. Sélectionnez le journal ou entrez-le manuellement.
5. Dans **volet Actions**, cliquez sur **Entrer les paiements client**. La page Entrer les paiements client est utilisée pour enregistrer un paiement client à la fois. Vous entrez les données de paiement en haut, puis vous pouvez marquer les factures qui ont été payées par le paiement, toutes depuis la même page.  
6. Entrez le client qui a envoyé le paiement. Si vous ne connaissez pas le client mais avez connaissance d’une transaction qui a été payée, utilisez le champ **Transaction** pour entrer le paiement. Entrez ou sélectionnez la facture dans le champ **Transaction**. Le client sera automatiquement transféré après que vous avez sélectionné la transaction.
7. Dans le champ **Référence de paiement**, entrez une référence de paiement. La référence de paiement peut être le numéro de chèque ou une référence du client issu du paiement électronique du client. La référence de paiement n’est requise que si vous choisissez d’inclure le paiement sur un bordereau de remise.  
8. Dans le champ **Bordereau de remise**, sélectionnez si le paiement est inclus dans un bordereau de remise. 
9. Dans le champ **Montant**, entrez le montant du paiement client. Le montant du paiement ne sera pas transféré. Il doit être entré manuellement. 
10. Marquez les factures qui ont été payées par le client. Si le paiement est un acompte, il n’est pas nécessaire de marquer d’autres factures pour le règlement. Il reste toujours possible d’enregistrer et de valider le paiement. Le règlement d’une facture peut se faire à une date ultérieure.
11. Entrez le montant du paiement qui doit être réglé sur les factures marquées. Ce champ peut être utilisé lorsque le paiement concerne un paiement partiel. Si vous n’entrez pas de montant, le montant à régler est automatiquement déterminé pour vous.
12. Cliquez sur **Enregistrer dans le journal**. Avant d’enregistrer le paiement dans le journal, assurez-vous que le compte de contrepartie est défini. Avec **Sauvegarde dans le journal**, vous sauvegarderez le paiement et le déplacerez dans le journal. Vous pouvez ensuite continuer et entrer le paiement suivant.
13. Fermez la page.
14. Dans le volet **Action**, cliquez sur **Lignes**. Lors de l’ouverture de **Lignes**, vous affichez tous les paiements consignés sur la page **Entrer les paiements client** et enregistrés dans le journal. Cette page permet également d’entrer de nouveaux paiements client ou de modifier un paiement client existant avant sa validation.
15. Cliquez sur **Nouveau** pour créer un autre paiement. 
16. Sélectionnez le client qui a envoyé le paiement. Si vous ne connaissez pas le client, mais avez connaissance d’une facture payée par le paiement, utilisez le champ **Facture** pour entrer ou sélectionner manuellement la facture. Le client sera transféré une fois la facture sélectionnée.  
17. Cliquez sur **Régler les transactions** pour marquer les factures qui ont été payées. Vous n’avez besoin de régler le paiement d’aucune facture. S’il s’agit d’un acompte ou si vous ne savez pas quelle facture a été payée, vous pouvez entrer et valider le paiement. Le paiement peut être réglé ultérieurement sur une facture.  
18. Marquez les factures réglées à l’aide du paiement. 
19. Dans le champ **Montant**, entrez le montant du paiement qui sera réglé sur les factures marquées.
20. Cliquez sur **OK**.
21. Dans le champ **Référence de paiement**, entrez une référence de paiement. La référence de paiement n’est requise que si vous choisissez d’inclure le paiement sur un bordereau de remise.  
22. Sur le **volet Actions**, cliquez sur **Publier** pour publier les paiements client. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
