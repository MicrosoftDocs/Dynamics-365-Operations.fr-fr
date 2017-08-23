--- 
title: "Créer un journal d'annulation pour un client"
description: "Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d'annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1c7ecd07c294b7357e4bda9f4183deb346b3e6ee
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-write-off-journal-for-a-customer"></a>Créer un journal d'annulation pour un client

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche vous indique comment définir les paramètres pour les annulations, puis pour les transactions d'annulation à partir de la page Recouvrement, de la page Factures client en cours et de la page Client. La société fictive USMF est citée en exemple dans cette tâche.


## <a name="set-up-the-write-off-parameters"></a>Définir les paramètres d'annulation
1. Accédez à Crédit et relances > Paramétrage > Paramètres de la comptabilité client.
2. Cliquer sur l'onglet Recouvrement.
3. Développez ou réduisez la section Annulation.
    * Le journal d'annulation est le journal des opérations diverses qui va contenir les transactions d'annulation que vous créez.  
    * Vous pouvez associer un code motif à chaque annulation. Vous pouvez remplacer ce paramétrage par défaut au moment de l'annulation.  
    * Paramétrez cela sur Oui si vous souhaitez fractionner la taxe de la transaction d'origine dans l'annulation.  
4. Fermez la page.
5. Accédez à Crédit et relances > Paramétrage > Profils de validation client.
    * Le compte d'annulation est utilisé comme compte de dépenses ou ajustement de réserve dans le journal des opérations diverses   
6. Fermez la page.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Annuler le solde d'un client à partir de la page des balances âgées
1. Accédez à Crédit et relances > Collections > Soldes chronologiques.
2. Marquez la ligne pour le client à annuler. Par exemple, marquez la ligne contenant la société Birch.
3. Cliquez sur Collecter dans le volet Actions.
4. Cliquez sur Annuler.
5. Cliquez sur OK.
6. Fermez la page.
7. Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.
8. Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation.
    * Une ligne est créée pour contrepasser le solde du client. Une ou plusieurs lignes sont créées pour valider l'annulation du compte d'annulation.  
9. Fermez la page.
10. Fermez la page.

## <a name="write-off-transactions-from-the-collections-form"></a>Annuler des transactions à partir de l'écran de recouvrement.
1. Accédez à Crédit et relances > Collections > Soldes chronologiques.
2. Sélectionnez le nom du client ayant les transactions que vous souhaitez annuler. Sélectionnez par exemple Cave Wholesales (US-004).
3. Marquez la ligne de la première transaction.
4. Marquez la ligne de la deuxième transaction.
5. Cliquez sur Annuler.
6. Dans le champ Commentaire du motif, entrez « Créances irrécouvrables ».
7. Cliquez sur OK.
8. Fermez la page.
9. Fermez la page.
10. Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.
11. Sélectionnez le numéro de lot du journal pour le journal contenant votre annulation.
    * Une ligne est créée pour contrepasser le solde du client. Une ou plusieurs lignes sont créées pour valider l'annulation du compte d'annulation.  
12. Fermez la page.
13. Fermez la page.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Annuler une facture à partir de la page Ouvrir les factures des clients
1. Accédez à Comptabilité client > Factures > Factures client en cours.
2. Marquez le ligne d'une facture. Par exemple, marquez la ligne pour CIV-000667.
3. Dans le volet Actions, cliquez sur Facture.
4. Cliquez sur Annuler.
5. Cliquez sur OK.
6. Fermez la page.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Annuler le solde d'un client à partir de la page client
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Permet de sélectionner un compte client. Par exemple, sélectionnez US-001 (Contoso Retail San Diego).
3. Cliquez sur Collecter dans le volet Actions.
4. Cliquez sur Annuler.
5. Cliquez sur OK.
6. Fermez la page.


