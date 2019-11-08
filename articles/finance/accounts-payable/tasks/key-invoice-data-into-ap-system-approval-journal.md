---
title: Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un journal d'approbation
description: Cette rubrique explique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: fb690769a33f88e63ab8f54cec69a5e927fd324c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177786"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un journal d'approbation

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment utiliser le registre des factures pour créer des factures et utiliser le journal d'approbation pour mettre à jour les comptes de dépenses.

## <a name="create-and-post-and-invoice"></a>Créer et valider une facture
1. Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Registre des factures**.
2. Sélectionnez **Nouveau**.
3. Sélectionnez le nom du registre des factures à utiliser.
4. Sélectionnez **Lignes** pour ouvrir le registre, puis entrez des lignes de dépense.
5. Sélectionnez un fournisseur. Par exemple, entrez ou sélectionnez `US-104`.
6. Dans le champ **Facture**, tapez une valeur.
7. Tapez une valeur dans le champ **Description**.
8. Dans le champ **Crédit**, entrez un numéro.
9. Dans le champ **Approuvé par**, sélectionnez un approbateur dans le menu déroulant.
10. Sélectionnez **Valider**.

## <a name="approve-an-invoice"></a>Approuver une facture
1. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Factures > Approbation des factures**.
2. Sélectionnez **Nouveau**.
3. Sélectionnez le nom du journal d'approbation des factures à utiliser.
4. Sélectionnez **Lignes** pour afficher la page sur laquelle vous pourrez sélectionner les factures que vous souhaitez approuver.
5. Sélectionnez **Rechercher des N° documents** pour afficher toutes les factures prêtes pour approbation.
6. Marquez la facture que vous avez créée, puis cliquez sur **Sélectionner**. Les N° documents sélectionnés précédemment sont déplacés vers cette liste une fois que vous les avez sélectionnés.  
7. Cliquez sur **OK**.
8. Sélectionnez le champ **Numéro de compte** pour ajouter un compte de dépenses à la facture.
9. Entrez un numéro de compte et appuyez sur la touche de tabulation pour quitter le champ. Par exemple, entrez `600120`.
10. Sélectionnez **Valider**.
11. Sélectionnez **N° document** pour afficher les entrées qui ont été validées. Le compte Factures en attente d'approbation est contrepassé et remplacé par le compte de dépenses actif.  
