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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2536e87953267eae13cf3b42c2bd5476fc647c22
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994713"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calculer et ajuster la taxe sur une facture fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment ajuster la taxe sur une facture fournisseur. Si le document source d’origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation. La société fictive DEMF est citée en exemple dans cette tâche.

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
11. Sous l’onglet **Ajustement**, les montants de taxe peuvent être ajustés par code taxe.
12. Sélectionnez **Réinitialiser les montants réels des montants calculés**.
13. Cliquez sur **OK**.
14. Sélectionnez **Enregistrer**.

