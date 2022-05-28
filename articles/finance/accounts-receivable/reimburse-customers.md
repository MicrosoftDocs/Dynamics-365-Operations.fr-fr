---
title: Rembourser les clients
description: Cette rubrique illustre la création des transactions de remboursement pour un groupe de clients.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d464dd23d70e1a340211eb83828550d807a543
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735637"
---
# <a name="reimburse-customers"></a>Rembourser les clients

[!include [banner](../includes/banner.md)]

Cette rubrique illustre la création des transactions de remboursement pour un groupe de clients. Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde. 

Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

| Logiciel requis                                                            | Description |
|-------------------------------------------------------------------------|-------------|
| Spécification du montant minimal de remboursement pour l’entité juridique.          | Dans la page **Paramètres de comptabilité client**, dans la zone **Général**, dans le champ **Remboursement minimal**, entrez le montant minimal qui peut être remboursé des trop-perçus client. |
| Facultatif : ajoutez un compte fournisseur à chaque client qui peut être remboursé. | Sur la page **Client**, dans l’organisateur **Détails divers**, dans le champ **Compte fournisseur**, sélectionnez le compte fournisseur pour le client. |

Lorsque vous créez des transactions de remboursement, une facture fournisseur est créée pour le montant du solde créditeur. Le processus de remboursement permet de supprimer le solde créditeur du compte client et crée un solde dû pour le compte fournisseur correspondant au client.

1. Dans Comptabilité client, exécutez le processus **Remboursement** (**Comptabilité client \> Tâches périodiques \> Remboursement**).
2. Pour regrouper toutes les transactions, quelles que soient les dimensions comptables, définissez l’option **Résumer le client** sur **Oui**. Pour regrouper uniquement les transactions qui ont des dimensions comptables similaires, définissez l’option sur **Non**.
3. Sélectionnez **Inclure les clients avec des transactions de débit en cours** pour sélectionner les clients qui ont des montants débiteurs non réglés.
4. Pour rembourser des comptes clients spécifiques, sur l’organisateur **Enregistrements à inclure**, sélectionnez **Filtrer**, puis spécifiez les comptes clients dans la requête.

    Les montants de crédit sont transférés vers les comptes fournisseur des clients et sont traités comme des paiements ordinaires. Si un client n’a pas de compte fournisseur, un compte fournisseur occasionnel est créé automatiquement pour le client.

5. Pour afficher les opérations de remboursement qui ont été créées, utilisez l’état **Remboursement** (**Comptabilité client \> Demandes de renseignements et rapports \> Rapport de remboursement**).
6. Dans Comptabilité fournisseur, créez un paiement pour les factures fournisseur créées par le processus de remboursement. Pour plus d’informations sur la façon de payer les fournisseurs, voir [Aperçu du paiement du fournisseur](../accounts-payable/Vendor-payments-workspace.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
