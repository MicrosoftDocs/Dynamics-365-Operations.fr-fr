--- 
title: Enregistrer une facture fournisseur dans le journal des factures
description: "Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 42f93e6d8fcf62babc3e3244bc1fe76d1efd9d13
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Enregistrer une facture fournisseur dans le journal des factures

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur. Parmi les exemples de ce type de facture on trouve des dépenses pour les approvisionnements ou les services.  La société fictive USMF sert d'exemple dans cet enregistrement.

1. Accédez à Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur.
2. Cliquez sur Nouveau journal des factures.
3. Cliquez sur Nouveau.
4. Entrez le nom du journal dans le champ Nom ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Lignes.
    * Dans le champ Date, entrez la date de validation qui mettra la comptabilité à jour.  
7. Spécifiez le compte fournisseur dans le champ Compte.
8. Entrez le numéro de la facture dans le champ Facture.
9. Tapez une valeur dans le champ Description.
10. Entrez un numéro dans le champ Crédit.
11. Entrez le numéro de compte dans le champ Compte de contrepartie ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le groupe Taxe est par défaut celui du compte fournisseur.  
    * Le groupe Taxe d'article est par défaut celui du compte principal spécifié dans le champ Compte de contrepartie.  
    * La date d'échéance sera calculée sur la base des conditions de paiement.  
    * L'escompte de règlement est par défaut celui du compte fournisseur.  
12. Cliquez sur Valider.
13. Fermez la page.


