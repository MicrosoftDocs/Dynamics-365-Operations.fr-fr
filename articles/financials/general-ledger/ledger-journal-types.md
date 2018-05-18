---
title: Types de journaux comptables
description: "Cet article décrit les types de journaux que vous pouvez paramétrer pour les journaux financiers. Utilisez la page **Noms de journal** pour paramétrer les journaux que vous pouvez utiliser dans Microsoft Dynamics 365 for Finance and Operations."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9f8fc40f199b83a9e0cb36ce905163c3ed547057
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="ledger-journal-types"></a>Types de journaux comptables

[!include [banner](../includes/banner.md)]

Cet article décrit les types de journaux que vous pouvez paramétrer pour les journaux financiers. Utilisez la page **Noms de journal** pour paramétrer les journaux que vous pouvez utiliser dans Microsoft Dynamics 365 for Finance and Operations.

| Type de journal                      | Objectif                       | Entrer les transactions sur cette page                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Affectation                        | Créer des transactions de répartition dans un journal des répartitions. Avant de pouvoir créer un journal de répartition, vous devez créer une règle de répartition sur la page **Règle de répartition comptable**.      | Traiter la demande de répartition             |
| Approbation                          | Permet de valider les factures fournisseur approuvées dans les comptes généraux appropriés.  | Journal des approbations de facture                                       |
| Contrepassation de chèque bancaire               | Contrepasser un chèque validé. Pour utiliser ce type de journal, sélectionnez l'option **Utiliser le processus de révision pour les contrepassations de paiement** sur la page **Paramètres de gestion des disponibilités et des banques**.   | Contrepassations de chèques, contrepassation de paiement                   |
| Annulation du bordereau de remise en banque    | Annuler un paiement de bordereau de remise. Pour utiliser ce type de journal, sélectionnez l'option **Utiliser le processus de révision pour les annulations de paiement par bordereau de remise** sur la page **Paramètres de gestion des disponibilités et des banques**.   | Annulations de paiement de bordereau de remise            |
| Budget                            | Traiter les affectations du budget. Pour utiliser ce type de journal, sélectionnez l'option **Activer l'affectation budgétaire** sur la page **Paramètres de comptabilité**. Les entrées du journal des budgets comprennent des informations basées sur les comptes généraux définis sur la page **Définitions de validation**.                                                        |                                                                |
| Acceptation de la lettre de change  | Créer des transactions d'acceptation client pour les lettres de change.             | Journal de création des lettres de change, Journal de renouvellement des lettres de change |
| Remise en banque de lettres de change          | Créer un fichier de remise de lettre de change qui peut être envoyé à la banque de votre organisation. Pour utiliser ce type de journal, désactivez l'option **Règlement automatique** sur la page **Paramètres** **de la comptabilité client**.            | Remise                                                     |
| Création des lettres de change    | Créer des transactions de création de lettres de change client. Pour utiliser ce type de journal, désactivez l'option **Créer et valider automatiquement le journal de création lors de la validation des factures** sur la page **Modes de paiement - clients**.   | Journal de création des lettres de change                                  |
| Client - Paiements                  | Créer des transactions de paiement client.                             | Journal des paiements             |
| Lettres de change client impayées | Créer des transactions de lettres de change client impayées.                    | Journal des lettres de change impayées                               |
| Renouvellement de lettres de change  | Créer des transactions de renouvellement de lettres de change client.                     | Journal de renouvellement des lettres de change                                |
| Règlement des lettres de change client  | Créer des transactions de règlement de lettres de change client.                       | Journal de règlement des lettres de change                                |
| Opérations diverses                             | Créer des transactions quotidiennes dans le journal des opérations diverses.                          | Journal des opérations diverses                                                |
| Élimination                       | Créer des transactions d'élimination dans un journal des éliminations. Pour utiliser ce type de journal, sélectionnez le processus **Utiliser pour le processus d'élimination financière** et les options **Utiliser pour le processus de consolidation financière** sur la page **Entités juridiques**. Avant d'être en mesure d'utiliser ce type de journal, vous devez créer une règle d'élimination comptable sur la page **Règle d'élimination comptable**. | Élimination                                                    |
| Budget d'immobilisations                | Créer les entrées du registre des budgets d'immobilisations.                                                                                                                                                                                                                                                                                                                 | Budget d'immobilisations                                             |
| Registre des factures                  | Enregistrer les informations de base sur les factures fournisseur.                                                                                                                                                                                                                                                                                                           | Registre des factures                                               |
| Décaissement de la paie              | Émettre des paiements basés sur les bordereaux de salaire. Vous ne pouvez pas entrer manuellement des transactions dans ce journal. Vous devez générer les bordereaux de salaire puis envoyer ces instructions pour le paiement.                                                                                                                                                              |                                                                |
| Périodique                          | Créer des transactions périodiques pour le journal périodique.                                                                                                                                                                                                                                                                                                      | Journaux périodiques                                              |
| Valider les immobilisations                 | Valider des transactions d'immobilisation.                                                                                                                                                                                                                                                                                                                              | Immobilisations                                                   |
| Projet - dépenses                | Créer des transactions de dépense du projet.                                                                                                                                                                                                                                                                                                                        | Dépenses                                                        |
| Transactions statistiques            | Créer des transactions de statistiques.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Remises de billets à ordre            | Créer une remise de billet à ordre qui peut être envoyée à la banque de votre organisation.                                                                                                                                                                                                                                                                      | Journal des remises                                             |
| Fournisseur - Paiements               | Créer des transactions de déboursement fournisseur.                                                                                                                                                                                                                                                                                                                    | Journal des paiements                                                |
| Création des billets à ordre       | Créer des billets à ordre fournisseur comme mode de paiement. Pour utiliser ce type de journal, désactivez l'option **Créer et valider automatiquement le journal de création lors de la validation des factures** sur la page **Modes de paiement - fournisseurs**.                                                                                                                                          | Journal de création des billets à ordre                                   |
| Registre de factures fournisseur hors comptabilité | Créer des transactions de facture fournisseur qui n'ont pas encore été validées dans un compte d'arrivée temporaire.                                                                                                                                                                                                                                                             | Registre de factures fournisseur excluant les détails de validation                  |
| Registre de factures fournisseur               | Créer des transactions de registre de factures fournisseur.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Enregistrement de facture fournisseur          | Permet de valider les factures fournisseur qui figurent dans un journal.                                                                                                                                                                                                                                                                                                                 | Journal des factures                                                |
| Renouvellement de billets à ordre     | Renouveler un billet à ordre préalablement réglé par la banque de votre organisation.                                                                                                                                                                                                                                                                      | Journal de renouvellement des billets à ordre                                 |
| Règlement des billets à ordre des fournisseurs     | Créer des transactions de règlement de billets à ordre des fournisseurs.                                                                                                                                                                                                                                                                                                          | Journal des règlements des billets à ordre                                 |






