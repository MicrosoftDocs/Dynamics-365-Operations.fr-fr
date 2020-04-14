---
title: Calculer et ajuster la taxe sur une facture fournisseur
description: Cette rubrique explique comment ajuster la taxe sur une facture fournisseur dans Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139965"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calculer et ajuster la taxe sur une facture fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment ajuster la taxe sur une facture fournisseur. Si le document source d'origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation. La société fictive DEMF est citée en exemple dans cette tâche.

1. Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Journal des factures**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom** de la nouvelle ligne, sélectionnez une option du menu déroulant.
4. Dans le volet Actions, sélectionnez **Lignes**.
5. Dans le champ **Compte**, spécifiez les valeurs souhaitées.
6. Dans le champ **Facture**, tapez une valeur.
7. Dans le champ **Crédit**, entrez un numéro.
8. Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.
9. Sélectionnez **Taxe**.
10. Dans le champ **Montant réel de taxe total**, entrez un nombre.
11. Sous l'onglet **Ajustement**, les montants de taxe peuvent être ajustés par code taxe.
12. Sélectionnez **Réinitialiser les montants réels des montants calculés**.
13. Cliquez sur **OK**.
14. Sélectionnez **Enregistrer**.

