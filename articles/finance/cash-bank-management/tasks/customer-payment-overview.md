---
title: Vue d’ensemble des paiements client
description: Ce guide de tâche présente diverses méthodes utilisées pour entrer des paiements client.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71e1657d738f691644b6d9cc4d34f812b853934e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978861"
---
# <a name="customer-payment-overview"></a>Vue d’ensemble des paiements client

[!include [banner](../../includes/banner.md)]

Ce guide de tâche présente diverses méthodes utilisées pour entrer des paiements client. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à **Volet de navigation > Modules > Comptabilité client > Paiements > Journal des paiements**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez le journal des paiements dans lequel les paiements client seront enregistrés.
4. Sélectionnez le journal ou entrez-le manuellement.
5. Dans **volet Actions**, cliquez sur **Entrer les paiements client**. La page Entrer les paiements client est utilisée pour enregistrer un paiement client à la fois. Vous entrez les données de paiement en haut, puis vous pouvez marquer les factures qui ont été payées par le paiement, toutes depuis la même page.  
6. Entrez le client qui a envoyé le paiement. Si vous ne connaissez pas le client mais avez connaissance d’une transaction qui a été payée, vous pouvez utiliser le champ Transaction pour entrer le paiement. Entrez ou sélectionnez la facture dans le champ Transaction. Le client sera automatiquement transféré après que vous avez sélectionné la transaction.
7. Dans le champ **Référence de paiement**, entrez une référence de paiement. La référence de paiement peut être le numéro de chèque ou une référence du client issu du paiement électronique du client. La référence de paiement n’est requise que si vous choisissez d’inclure le paiement sur un bordereau de remise.  
8. Dans le champ **Bordereau de remise**, sélectionnez si le paiement est inclus dans un bordereau de remise. 
9. Dans le champ **Montant**, entrez le montant du paiement client. Le montant du paiement ne sera pas transféré. Il doit être entré manuellement. 
10. Marquez les factures qui ont été payées par le client. Si le paiement est un acompte, il n’est pas nécessaire de marquer d’autres factures pour le règlement. Il reste toujours possible d’enregistrer et de valider le paiement. Le règlement d’une facture peut se faire à une date ultérieure.
11. Entrez le montant du paiement qui doit être réglé sur les factures marquées. Ce champ peut être utilisé lorsque le paiement concerne un paiement partiel. Si vous n’entrez pas de montant, le montant à régler est automatiquement déterminé pour vous.
12. Cliquez sur **Enregistrer dans le journal**. Avant d’enregistrer le paiement dans le journal, assurez-vous que le compte de contrepartie est défini. Avec **Sauvegarde dans le journal**, vous sauvegarderez le paiement et le déplacerez dans le journal. Vous pouvez ensuite continuer et entrer le paiement suivant.
13. Fermez la page.
14. Dans le **volet Actions**, cliquez sur Lignes. Lors de l’ouverture de Lignes, vous verrez tous les paiements consignés sur la page **Entrer les paiements client** et enregistrés dans le journal. Cette page permet également d’entrer de nouveaux paiements client ou de modifier un paiement client existant avant sa validation.
15. Cliquez sur **Nouveau** pour créer un autre paiement. 
16. Sélectionnez le client qui a envoyé le paiement. Si vous ne connaissez pas le client, mais avez connaissance d’une facture payée par le paiement, utilisez le champ Facture pour entrer ou sélectionner manuellement la facture. Le client sera transféré une fois la facture sélectionnée.  
17. Cliquez sur **Régler les transactions** pour marquer les factures qui ont été payées. Vous n’avez besoin de régler le paiement d’aucune facture. S’il s’agit d’un acompte ou si vous ne savez pas quelle facture a été payée, vous pouvez entrer et valider le paiement. Le paiement peut être réglé ultérieurement sur une facture.  
18. Marquez les factures réglées à l’aide du paiement. 
19. Dans le champ **Montant**, entrez le montant du paiement qui sera réglé sur les factures marquées.
20. Cliquez sur **OK**.
21. Dans le champ **Référence de paiement**, entrez une référence de paiement. La référence de paiement n’est requise que si vous choisissez d’inclure le paiement sur un bordereau de remise.  
22. Sur le **volet Actions**, cliquez sur **Publier** pour publier les paiements client. 

