---
title: Remboursements dans le secteur public
description: "Cette rubrique répond aux questions courantes associées aux remboursements dans le secteur public."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustBillingClassification
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27311
ms.assetid: 9d61d1d8-1672-4bd0-ae0d-605b09240890
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9ee5536d6e157ced0518e36fab0c92301a33a66d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="reimbursements-in-the-public-sector"></a>Remboursements dans le secteur public

[!include[banner](../includes/banner.md)]


Cette rubrique répond aux questions courantes associées aux remboursements dans le secteur public. 

<a name="what-happens-if-i-create-a-separate-reimbursement-transaction-for-each-billing-classification"></a>Que se passe-t-il si je crée une transaction de remboursement distincte pour chaque classification de facturation ?
----------------------------------------------------------------------------------------------

Lorsque vous créez une transaction de remboursement distincte pour chaque classification de facturation, les transactions d'avoir qui sont réparties vers le même compte général et dotées de la même classification de facturation sont combinées dans une transaction de remboursement unique. Les transactions d'avoir qui sont réparties vers le même compte général et qui sont dotées de classifications de facturation différentes génèrent des transactions de remboursement distinctes. Supposons, par exemple, que vous traitiez les remboursements pour trois avoirs. Les trois avoirs sont d'un montant de 1 000 €.

-   Le premier avoir, doté de la classification de facturation UTL, est distribué vers trois comptes, avec 15 % vers le compte 1110, 30 % vers le compte 2210 et 55 % vers le compte 3210.
-   Le deuxième avoir est également doté de la classification de facturation UTL. Il est distribué à 100 % vers le compte 3210.
-   Le troisième avoir, doté de la classification de facturation GEN, est distribué à 100 % vers le compte 1110.

Si vous créez une transaction de remboursement distincte pour chaque classification de facturation, quatre transactions de remboursement sont créées, de la façon suivante :

-   150 € vers le compte 1110
-   1 000 € vers le compte 1110
-   300 € vers le compte 2210
-   1 550 € vers le compte 3210

Les montants dirigés vers le compte 3210 sont combinés, car ils utilisent tous deux la même classification de facturation. Les montants dirigés vers le compte 1110 ne sont pas combinés, car ils n'utilisent pas la même classification de facturation. Si vous ne créez pas un remboursement distinct pour chaque classification de facturation, les transactions associées au compte 1110 seraient combinées, et seulement trois transactions de remboursement seraient créées.

## <a name="how-do-billing-classifications-affect-reimbursements-for-overpayments"></a>Comment les classifications de facturation affectent-elles les remboursements des trop-perçus ?
Elle ne les affectent pas. Les classifications de facturation ne sont jamais appliquées aux paiements client, et elles ne sont donc pas utilisées lors du traitement des remboursements des trop-perçus.

## <a name="can-i-process-a-reimbursement-for-a-customer-who-has-outstanding-debit-transactions"></a>Puis-je traiter un remboursement pour un client ayant des transactions débitrices en attente ?
Oui. Si vous devez traiter un remboursement pour un client ayant des transactions débitrices en attente, utilisez les filtres sur la page de remboursement afin de sélectionner le client, puis sélectionnez l'option permettant d'inclure les clients avec des transactions débitrices en attente. Lorsque vous procédez ainsi, les transactions de remboursement sont créées pour le montant total de toutes les transactions créditrices du client. Les montants débiteurs impayés ne sont pas déduits des montants créditeurs.

## <a name="can-i-process-reimbursements-for-customers-who-have-pending-settlements"></a>Puis-je traiter les remboursements pour les clients ayant des règlements en attente ?
N° Les remboursements ne sont traités pour aucun client qui possède des règlements en attente non validés au journal.

## <a name="can-i-reverse-reimbursement-settlements"></a>Puis-je contrepasser des règlements de remboursement ?
Non, pas directement. Toutefois, vous pouvez utiliser les entrées du journal des opérations diverses pour créer les transactions qui auraient l'effet de contrepasser les écritures comptables.






