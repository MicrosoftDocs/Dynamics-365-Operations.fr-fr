---
title: Règlement d’un chèque postdaté provenant d’un client
description: Vous pouvez régler un chèque postdaté après que celui-ci ait été compensé par la banque.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bc6f90e7adb3facdfa1facb50fecb0de4ccb04d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443236"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Règlement d’un chèque postdaté provenant d’un client

[!include [banner](../../includes/banner.md)]

Vous pouvez régler un chèque postdaté après que celui-ci ait été compensé par la banque. Cette transaction financière permet également d’effacer la transaction de compte d’attente pour le chèque postdaté. 

Les tâches suivantes doivent être terminées avant de commencer celui-ci.

1) Paramétrage de chèques postdatés

2) Enregistrer et valider un chèque postdaté pour un client 



Le rôle de ces guides de tâches est Trésorier.



La société fictive USMF sert d’exemple dans cette procédure.

1. Accédez à Crédit et relances > Recherches et états > Paiements > Chèques client postdatés.
2. Cliquez sur Régler.
3. Cliquez sur Régler les lignes de compensation.
    * Réglez le compte client pour la transaction par chèque.  
4. Fermez la page.
5. Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.
6. Dans le champ Afficher, sélectionnez une option.
7. Activez ou désactivez la case à cocher Afficher uniquement les journaux créés par l’utilisateur.
8. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
9. Cliquez sur Lignes.
10. Cliquez Document.
11. Fermez la page.

