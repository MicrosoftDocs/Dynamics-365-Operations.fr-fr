--- 
title: "Créer un mandat de débit direct pour un client"
description: "Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
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
ms.openlocfilehash: e1ac289c261922f013b679eecfb054390b8aef73
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Créer un mandat de débit direct pour un client

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche montre comment créer un mandat de débit direct et l'utiliser dans une facture.


## <a name="create-a-bank-account"></a>Créer un compte bancaire
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Par exemple, sélectionnez US-001.
3. Cliquez sur Client dans le volet Actions.
4. Cliquez sur Comptes bancaires.
5. Cliquez sur Nouveau.
6. Tapez une valeur dans le champ Compte en banque.
7. Tapez une valeur dans le champ Nom.
8. Tapez une valeur dans le champ IBAN.
9. Tapez une valeur dans le champ Devise.
10. Cliquez sur Enregistrer.
11. Fermez la page.
12. Accédez à Gestion de la trésorerie et de la banque > Comptes bancaires > Comptes bancaires.
13. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
14. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
15. Cliquez sur Modifier.
16. Développez la section Identification supplémentaire.
17. Dans le champ ID débit direct, tapez une valeur.
18. Tapez une valeur dans le champ IBAN.
19. Fermez la page.
20. Fermez la page.

## <a name="define-the-electronic-payment-method"></a>Définir le mode de paiement électronique
1. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Mode de paiement.
4. Dans le champ Description, entrez une valeur.
5. Le type de paiement doit être électronique pour un mode de paiement pour les mandats de débit direct.
6. Sélectionnez Oui dans le champ Demander un mandat.
7. Fermez la page.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Ajoutez un mandat de débit direct à un client.
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Par exemple, sélectionnez US-001.
3. Cliquez sur Modifier.
4. Développez la section Valeurs par défaut du paiement.
5. Entrez ou sélectionnez une valeur dans le champ Mode de paiement.
6. Développez la section Valeurs par défaut du paiement.
7. Développez la section Mandats de débit direct.
8. Cliquez sur Ajouter.
9. Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.
10. Dans le champ Compte bancaire du créditeur, entrez ou sélectionnez une valeur.
11. Entrez le nombre de paiements que vous prévoyez de traiter pour ce mandat.
12. Cliquez sur OK.
13. Cliquez sur Imprimer.
14. Cliquez sur État des mandats.
15. Fermez la page.
16. Cliquez sur Modifier.
17. Entrez une date dans le champ Date de signature.
18. Cliquez sur Oui.
19. Entrez le lieu de signature du mandat.
20. Cliquez sur OK.
21. Fermez la page.

## <a name="create-a-free-text-invoice-with-mandate"></a>Créez une facture financière avec mandat.
1. Accédez à Comptabilité client > Factures > Toutes factures financières.
2. Cliquez sur Nouveau.
3. Sélectionnez le client pour lequel vous avez ajouté le mandat.
4. Dans le champ ID mandat de débit direct, entrez ou sélectionnez une valeur.


