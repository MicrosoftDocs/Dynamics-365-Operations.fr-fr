--- 
title: "Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022"
description: "Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f01947840553a65af4aba1309d89f9b3e9ced872
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Paramétrer les fournisseurs et les comptes bancaires fournisseur pour les virements ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment paramétrer le fournisseur et les informations de compte bancaire spécifiques au fournisseur qui sont requises pour le virement ISO20022 ou toute autre génération du fichier de paiement fournisseur. 

La société fictive de démonstration utilisée pour créer cette procédure est DEMF.
Il s'agit de la quatrième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="set-up-bank-details"></a>Paramétrer les détails bancaires
1. Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, appliquez un filtre au champ Compte fournisseur avec une valeur de « DE-001 ».
3. Cliquez sur DE-001 pour ouvrir les détails sur le fournisseur.
4. Cliquez sur Fournisseur dans le volet Actions.
5. Cliquez sur Comptes bancaires.
6. Cliquez sur Modifier.
    * Si aucun compte bancaire disponible, vous devez en créer un.  
7. Tapez le code « COBADEFFXXX » dans le champ Code SWIFT.
8. Tapez DE36200400000628808808 dans le champ IBAN.
9. Fermez la page.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Paramétrer un mode de paiement pour le fournisseur
1. Cliquez sur Modifier.
2. Développez ou réduisez la section Paiement.
3. Dans le champ Mode de paiement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquez sur le lien dans la ligne SEPA CT.
5. Cliquez sur Enregistrer.


