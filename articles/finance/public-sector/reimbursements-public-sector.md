---
title: Remboursements dans le secteur public
description: Cet article répond aux questions courantes associées aux remboursements dans le secteur public.
author: JodiChristiansen
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27311
ms.assetid: 9d61d1d8-1672-4bd0-ae0d-605b09240890
ms.search.industry: Public sector
ms.search.form: CustBillingClassification
ms.openlocfilehash: 4155d2a0ceb4e9b55bb1c9b2f04d15f43add8cc3
ms.sourcegitcommit: e25fe4228add88dd37f4f38ece86979e1c621f6a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9734311"
---
# <a name="reimbursements-in-the-public-sector"></a>Remboursements dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article répond aux questions courantes associées aux remboursements dans le secteur public. 

## <a name="how-do-billing-classifications-affect-reimbursements-for-overpayments"></a>Comment les classifications de facturation affectent-elles les remboursements des trop-perçus ?
Elle ne les affectent pas. Les classifications de facturation ne sont jamais appliquées aux paiements client, et elles ne sont donc pas utilisées lors du traitement des remboursements des trop-perçus.

## <a name="can-i-process-a-reimbursement-for-a-customer-who-has-outstanding-debit-transactions"></a>Puis-je traiter un remboursement pour un client ayant des transactions débitrices en attente ?
Oui. Si vous devez traiter un remboursement pour un client ayant des transactions débitrices en attente, utilisez les filtres sur la page de remboursement afin de sélectionner le client, puis sélectionnez l’option permettant d’inclure les clients avec des transactions débitrices en attente. Lorsque vous procédez ainsi, les transactions de remboursement sont créées pour le montant total de toutes les transactions créditrices du client. Les montants débiteurs impayés ne sont pas déduits des montants créditeurs.

## <a name="can-i-process-reimbursements-for-customers-who-have-pending-settlements"></a>Puis-je traiter les remboursements pour les clients ayant des règlements en attente ?
Non Les remboursements ne sont traités pour aucun client qui possède des règlements en attente non validés au journal.

## <a name="can-i-reverse-reimbursement-settlements"></a>Puis-je contrepasser des règlements de remboursement ?
Non, pas directement. Toutefois, vous pouvez utiliser les entrées du journal des opérations diverses pour créer les transactions qui auraient l’effet de contrepasser les écritures comptables.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
