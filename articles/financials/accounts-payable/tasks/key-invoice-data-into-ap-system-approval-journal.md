---
title: Données de facture clés dans le système de comptabilité fournisseur à l'aide du journal d'approbation
description: Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0faece510cc85fd86113d8b62d54b71f3014b1db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837035"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a>Données de facture clés dans le système de comptabilité fournisseur à l'aide du journal d'approbation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche vous indique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.


## <a name="create-and-post-and-invoice"></a>Créer et valider une facture
1. Accédez à Comptabilité fournisseur > Factures > Registre des factures.
2. Cliquez sur Nouveau.
3. Sélectionnez le nom du registre des factures à utiliser.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur Lignes pour ouvrir le registre, puis entrez des lignes de dépense.
6. Sélectionnez un fournisseur. Par exemple, entrez ou sélectionnez US-104
7. Tapez une valeur dans le champ Facture.
8. Tapez une valeur dans le champ Description.
9. Entrez un numéro dans le champ Crédit.
10. Dans le champ Approbateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Mettez un approbateur en surbrillance et cliquez sur Sélectionner pour le sélectionner.
12. Cliquez sur Valider.
13. Fermez la page.
14. Fermez la page.

## <a name="approve-an-invoice"></a>Approuver une facture
1. Accédez à Comptabilité fournisseur > Factures > Approbation de facture.
2. Cliquez sur Nouveau.
3. Sélectionnez le nom du journal d'approbation des factures à utiliser.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur les lignes pour afficher la page dans laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.
6. Sélectionnez Rechercher des N° documents pour afficher toutes les factures prêtes pour approbation.
7. Marquez la facture que vous avez créée.
8. Cliquez sur Sélectionner.
    * Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.  
9. Cliquez sur OK.
10. Cliquez sur le champ Numéro de compte pour ajouter un compte de dépenses à la facture.
11. Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ. Par exemple, entrez 600120.
12. Cliquez sur Valider.
13. Cliquez sur N° document pour afficher les entrées qui ont été validées.
    * Le compte Factures en attente d'approbation est contrepassé et remplacé par le compte de dépenses actif.  

