--- 
title: "Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022"
description: "Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022."
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Créer et exporter des paiements fournisseur à l'aide du format de paiement ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment créer des lignes de paiement dans le journal des paiements fournisseur et générer un fichier de paiement fournisseur à l'aide de l'exemple de virement ISO2022. 

La société fictive de démonstration utilisée pour créer cette procédure est DEMF.

Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-payment-lines"></a>Créer des lignes de paiement
1. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Saisissez ou sélectionnez une valeur dans le champ Nom.
5. Cliquez sur Lignes.
6. Cliquez sur Proposition de paiement.
7. Cliquez sur Créer une proposition de paiement.
8. Développez les enregistrements pour inclure la section.
9. Cliquez sur Filtre.
10. Dans la liste, sélectionnez la ligne de la table Fournisseurs et du champ Compte fournisseur.
11. Dans le champ Critères, saisissez ou sélectionnez une valeur.
    * Vous pouvez appliquer les critères de sélection des transactions fournisseur à payer. Pour cet exemple, utilisez DE-001 comme compte fournisseur.  
12. Cliquez sur OK.
13. Cliquez sur OK.
14. Cliquez sur Créer des paiements.

## <a name="generate-an-iso20022-payment-file"></a>Générer un fichier de paiement ISO20022


