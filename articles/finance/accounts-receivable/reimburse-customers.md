---
title: Rembourser les clients
description: Cet article explique la création des transactions de remboursement pour un groupe de clients. Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bceeaf99437f6ef66bd3b4e1710b469c262e693e
ms.sourcegitcommit: 9e7ceb5604472f3088f611aa0360bd6a716db32b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022541"
---
# <a name="reimburse-customers"></a>Rembourser les clients

[!include [banner](../includes/banner.md)]

Cet article explique la création des transactions de remboursement pour un groupe de clients. Si un client a un solde créditeur, vous pouvez le rembourser pour le montant du solde. 

Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

| Logiciel requis                                                            | Description                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spécification du montant minimal de remboursement pour l'entité juridique.          | Dans la page **Paramètres de comptabilité client** , dans la zone **Général** , dans le champ **Remboursement minimal** , entrez le montant minimal qui peut être remboursé des trop-perçus client. |
| Facultatif : ajoutez un compte fournisseur à chaque client qui peut être remboursé. | Sur la page **Client** , dans l'organisateur **Détails divers** , dans le champ **Compte fournisseur** , sélectionnez le compte fournisseur pour le client.                                           |

Lorsque vous créez des transactions de remboursement, une facture fournisseur est créée pour le montant du solde créditeur. Le processus de remboursement permet de supprimer le solde créditeur du compte client et crée un solde dû pour le compte fournisseur correspondant au client.

1.  Dans Comptabilité client, exécutez le processus **Remboursement**.
2.  Utilisez l'une des procédures suivantes :
    -   Pour rembourser des comptes client spécifiques, cliquez sur **Sélectionner** et spécifiez les comptes client dans la requête.
    -   Pour rembourser tous les comptes client, cliquez sur **OK**.

    Les montants de crédit sont transférés vers les comptes fournisseur des clients et sont traités comme des paiements ordinaires. Si un client n'a pas de compte fournisseur, un compte fournisseur occasionnel est créé automatiquement pour le client.
3.  Pour afficher les transactions de remboursement créées, utilisez la page **Remboursement**.
4.  Dans Comptabilité fournisseur, créez un paiement pour les factures fournisseur créées par le processus de remboursement.




