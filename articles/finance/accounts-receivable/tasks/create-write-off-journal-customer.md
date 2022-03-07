---
title: Créer un journal d’annulation pour un client
description: Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d’annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd97f91f1ba53b56150b556fffdfed10a0c8911a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443280"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Créer un journal d’annulation pour un client

[!include [banner](../../includes/banner.md)]

Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d’annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client. La société fictive USMF est citée en exemple dans cette tâche.


## <a name="set-up-the-write-off-parameters"></a>Définir les paramètres d’annulation
1. Allez dans **Volet de navigation > Modules > Crédit et recouvrements > Paramétrage > Paramètres de la comptabilité client**.
2. Cliquez sur l’onglet **Recouvrement**.
3. Développez ou réduisez la section **Annulation**.
    - Le **journal d’annulation** est le journal des opérations diverses qui va contenir les transactions d’annulation que vous créez.  
    - Vous pouvez associer un code motif à chaque annulation. Vous pouvez remplacer ce paramétrage par défaut au moment de l’annulation.  
    - Définissez **Taxe distincte** sur Oui si vous souhaitez fractionner la taxe de la transaction d’origine dans l’annulation.  
4. Fermez la page.
5. Accédez à **Crédit et relances > Paramétrage > Profils de validation client**. Le compte d’annulation est utilisé comme compte de dépenses ou ajustement de réserve dans le journal des opérations diverses.
6. Fermez la page.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Annuler le solde d’un client à partir de la page des balances âgées
1. Accédez à **Crédit et relances > Collections > Soldes chronologiques**.
2. Marquez la ligne pour le client à annuler. Par exemple, marquez la ligne contenant la société Birch.
3. Cliquez sur **Collecter** dans le volet **Actions**.
4. Cliquez sur **Annuler**.
5. Cliquez sur **OK**.
6. Fermez la page.
7. Allez dans le **Volet de navigation > Modules > Comptabilité > Entrées de journal > Journaux des opérations diverses**.
8. Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation. Une ligne est créée pour contrepasser le solde du client. Une ou plusieurs lignes sont créées pour valider l’annulation du compte d’annulation.  
9. Fermez la page.
10. Fermez la page.

## <a name="write-off-transactions-from-the-collections-form"></a>Annuler des transactions à partir de l’écran de recouvrement.
1. Accédez à **Crédit et relances > Collections > Soldes chronologiques**.
2. Sélectionnez le nom du client ayant les transactions que vous souhaitez annuler. Sélectionnez par exemple Cave Wholesales (US-004).
3. Marquez la ligne de la première transaction.
4. Marquez la ligne de la deuxième transaction.
5. Cliquez sur **Annuler**.
6. Dans le champ **Commentaire du motif**, entrez « Créances irrécouvrables ».
7. Cliquez sur **OK**.
8. Fermez la page.
9. Fermez la page.
10. Accédez à **Comptabilité > Entrées de journal > Journaux des opérations diverses.**.
11. Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation. Une ligne est créée pour contrepasser le solde du client. Une ou plusieurs lignes sont créées pour valider l’annulation du compte d’annulation.  
12. Fermez la page.
13. Fermez la page.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Annuler une facture à partir de la page Ouvrir les factures des clients
1. Accédez à **Volet de navigation > Modules > Comptabilité client > Factures > Factures client en cours**.
2. Marquez le ligne d’une facture. Par exemple, marquez la ligne pour CIV-000667.
3. Cliquez sur **Facture** dans le volet **Actions**.
4. Cliquez sur **Annuler**.
5. Cliquez sur **OK**.
6. Fermez la page.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Annuler le solde d’un client à partir de la page client
1. Allez dans **Comptabilité client > Clients > Tous les clients**.
2. Permet de sélectionner un compte client. Par exemple, sélectionnez US-001 (Contoso Retail San Diego).
3. Cliquez sur **Collecter** dans le volet **Actions**.
4. Cliquez sur **Annuler**.
5. Cliquez sur **OK**.
6. Fermez la page.

