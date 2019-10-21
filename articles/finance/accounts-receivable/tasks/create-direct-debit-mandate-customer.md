---
title: Créer un mandat de débit direct pour un client
description: Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ca5ff2290df2179004ca1cebd11f67fbb7a724e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177767"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Créer un mandat de débit direct pour un client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture.


## <a name="create-a-bank-account"></a>Créer un compte bancaire
1. Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Clients > Tous les clients**.
2. Sélectionnez un enregistrement dans la liste. Par exemple, sélectionnez US-001.
3. Cliquez sur **Client** dans le volet Actions.
4. Cliquez sur **Comptes bancaires**.
5. Cliquez sur **Nouveau**.
6. Tapez une valeur dans le champ **Compte bancaire**.
7. Tapez une valeur dans le champ **Nom**.
8. Tapez une valeur dans le champ **IBAN**.
9. Tapez une valeur dans le champ **Devise**.
10. Cliquez sur **Enregistrer**.
11. Fermez la page.
12. Dans le **Volet de navigation**, allez dans **Modules > Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires**.
13. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Cliquez sur **Modifier**.
16. Développez le raccourci **Identification supplémentaire**.
17. Tapez une valeur dans le champ **ID débit direct**.
18. Tapez une valeur dans le champ **IBAN**.
19. Fermez la page.
20. Fermez la page.

## <a name="define-the-electronic-payment-method"></a>Définir le mode de paiement électronique
1. Dans le **Volet de navigation**, allez dans **Modules > Comptabilité client > Paramétrage des paiements > Modes de paiement**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Mode de paiement**.
4. Tapez une valeur dans le champ **Description**.
5. Entrez « Paiement électronique » dans le champ **Type de paiement**. Le type de paiement doit être électronique pour un mode de paiement pour les mandats de débit direct.
6. Sélectionnez Oui dans le champ **Demander un mandat**.
7. Fermez la page.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Ajoutez un mandat de débit direct à un client.
1. Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Clients > Tous les clients**.
2. Sélectionnez un enregistrement dans la liste. Par exemple, sélectionnez US-001.
3. Cliquez sur **Modifier**.
4. Développez le raccourci **Valeurs par défaut de paiement**.
5. Dans le champ **Mode de paiement**, saisissez ou sélectionnez une valeur.
6. Développez le raccourci **Valeurs par défaut de paiement**.
7. Développez le raccourci **Mandats de débit direct**.
8. Cliquez sur **Ajouter**.
9. Dans le champ **Compte en banque**, saisissez ou sélectionnez une valeur.
10. Entrez ou sélectionnez une valeur dans le champ **Compte bancaire du créditeur**.
11. Entrez le nombre de paiements que vous prévoyez de traiter pour ce mandat dans le champ **Fréquence de paiement**.
12. Cliquez sur **OK**.
13. Cliquez sur **Imprimer**.
14. Cliquez sur **État des mandats**.
15. Fermez la page.
16. Cliquez sur **Modifier**.
17. Entrez une date dans le champ **Date de signature**.
18. Cliquez sur **Oui**.
19. Entrez le lieu de signature du mandat.
20. Cliquez sur **OK**.
21. Fermez la page.

## <a name="create-a-free-text-invoice-with-mandate"></a>Créez une facture financière avec mandat.
1. Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Factures > Toutes factures financières**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez le client pour lequel vous avez ajouté le mandat.
4. Entrez ou sélectionnez une valeur dans le champ **ID mandat de débit direct**.

