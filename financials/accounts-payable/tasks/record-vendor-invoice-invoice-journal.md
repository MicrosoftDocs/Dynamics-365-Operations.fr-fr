--- 
title: Enregistrer une facture fournisseur dans le journal des factures
description: "Ce guide de tâche indique comment enregistrer des factures fournisseur qui ne sont pas associées à des commandes fournisseur."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 127875443da1d43783440083b11afd423f2a12fe
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Enregistrer une facture fournisseur dans le journal des factures

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


