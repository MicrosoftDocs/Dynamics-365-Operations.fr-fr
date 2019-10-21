---
title: Enregistrer une facture fournisseur dans le journal des factures
description: Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97dd03a96389ab22e441acd0af1ad35852570be4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177783"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Enregistrer une facture fournisseur dans le journal des factures

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur. Parmi les exemples de ce type de facture on trouve des dépenses pour les approvisionnements ou les services.  La société fictive USMF sert d'exemple dans cet enregistrement.

1. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Espaces de travail > Saisie de facture fournisseur**.
2. Dans le **Volet Actions**, cliquez sur **Nouveau journal des factures**.
3. Cliquez sur **Nouveau**.
4. Entrez le nom du journal dans le champ **Nom** ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Tapez une valeur dans le champ **Description**.
6. Dans le **Volet Actions**, cliquez sur **Lignes**. Dans le champ **Date**, entrez la date de validation qui mettra la comptabilité à jour.  
7. Spécifiez le **Compte fournisseur** dans le champ **Compte**.
8. Entrez le numéro de la facture dans le champ **Facture**.
9. Tapez une valeur dans le champ **Description**.
10. Dans le champ **Crédit**, entrez un numéro.
11. Entrez le numéro de compte dans le champ **Compte de contrepartie** ou cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le **Groupe de taxe** est par défaut celui du compte fournisseur.  
    * Le **Groupe de taxe d'article** est par défaut celui du compte principal spécifié dans le champ **Compte de contrepartie**.  
    * La **Date d'échéance** sera calculée sur la base des conditions de paiement.  
    * L'**Escompte de règlement** est par défaut celui du compte fournisseur.  
12. Cliquez sur **Valider**.
13. Fermez la page.

