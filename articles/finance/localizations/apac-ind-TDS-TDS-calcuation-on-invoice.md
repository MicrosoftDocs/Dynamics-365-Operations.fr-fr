---
title: Calcul TDS sur les factures
description: Cette rubrique fournit une référence pour les transactions où la taxe déduite à la source (TDS) est calculée au niveau de la facture.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023242"
---
# <a name="tds-calculation-on-invoices"></a>Calcul TDS sur les factures

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une référence pour les transactions où la taxe déduite à la source (TDS) est calculée au niveau de la facture.

| Numéro de série | Type de transaction                                 | Montant de la transaction | Nom et chemin d'accès de la sélection                                 | Type de compte et type de compte de contrepartie                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Achat effectué auprès du fournisseur/enregistrement des dépenses   | Débit ou crédit  | Page Journaux des opérations diverses (Comptabilité > Entrées de journal > Journaux des opérations diverses), page Journal des approbations de facture (Comptes fournisseurs> Factures> Approbation des factures), page Journal des factures (Comptes fournisseurs > Factures> Journal des factures) | Comptabilité (Dr)  Fournisseur (Cr.)  La retenue à la source est calculée pour la combinaison fournisseur-compte général uniquement lorsque le compte général a le type de validation **Acheter** **en espèces**. |
| 2.            | Achat effectué auprès du client/enregistrement des dépenses | Débit ou crédit  | Page Journaux généraux (Comptabilité > Entrées de journal> Journaux des opérations diverses), page Journal des factures (Comptes fournisseurs > Factures> Journal des factures) | Comptabilité (Dr)  Client (Cr.)                                 |
| 3.            | Achat d'immobilisation au fournisseur              | Débit ou crédit  | Page Journaux des opérations diverses (Comptabilité > Entrées de journal > Journal du registre des factures), page Journal des approbations de facture (Comptes fournisseurs> Factures> Approbation des factures), page Journal des factures (Comptes fournisseurs > Factures> Registre des factures) | Fournisseur d'immobilisations (Dr.) (Cr.)                             |
| 4.            | Achat d'immobilisation au client            | Débit ou crédit  | Page Journaux généraux (Comptabilité > Entrées de journal> Journaux des opérations diverses), page Journal des factures (Comptes fournisseurs > Factures> Journal des factures) | Fournisseur d'immobilisations (Dr.)  Client (Cr.)                           |
| 5.            | Facture d'achat (TDS payable)                  |                    | Page Commande fournisseur (Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur) |                                                              |
| 6.            | Facture de vente (créances TDS)                  |                    | Page Commande client (Comptes clients > Commandes> Toutes les commandes client), Page Facture financière (Comptes clients > Factures> Toutes les factures financières) |                                                              |
