--- 
title: "Créer des paiements pour les clients qui ont des mandats de débit direct"
description: "Cette procédure indique comment générer un fichier de paiement à débit direct ISO20022 pour un client dont le débit direct est configuré et qui a une facture à payer."
author: mrolecki
manager: AnnBe
ms.date: 10/14/2016
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
ms.openlocfilehash: 8a0e48d4681014899a4cc1a31ba902f244c6644b
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Créer des paiements pour les clients qui ont des mandats de débit direct

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment générer un fichier de paiement à débit direct ISO20022 pour un client dont le débit direct est configuré et qui a une facture à payer. La création et la validation d'une facture sont facultatives. Au lieu d'avoir une facture à payer, vous pouvez sélectionner un mandat dans un journal avant de générer un fichier de paiement, pour prendre en charge un scénario d'acompte client.



La société fictive de démonstration utilisée pour créer cette procédure est DEMF.



Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques. Avant de pouvoir effectuer cette tâche, vous devez effectuer les tâches précédentes. Vous devez d'abord importer les configurations de génération d'états électroniques de paiement client, configurer les modes de paiement et paramétrer les informations de votre société et du client. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Valider une facture financière avec les informations de débit direct
1. Accédez à Comptabilité client > Factures > Toutes factures financières.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Par exemple, sélectionnez DE-010.  
4. Entrez ou sélectionnez une valeur dans le champ Mode de paiement.
    * Par exemple, sélectionnez Électronique.  
5. Dans le champ ID mandat de débit direct, entrez ou sélectionnez une valeur.
6. Cliquez sur Ajouter une ligne.
7. Tapez une valeur dans le champ Description.
8. Dans le champ Compte principal, spécifiez les valeurs souhaitées.
9. Entrez un nombre dans le champ Prix unitaire.
10. Cliquez sur Valider.
11. Cliquez sur OK.

## <a name="create-a-payment"></a>Créer un paiement
1. Accédez à Comptabilité client > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Cliquez sur Lignes.
5. Cliquez sur Proposition de paiement.
6. Cliquez sur Créer une proposition de paiement.
7. Développez les enregistrements pour inclure la section.
8. Cliquez sur Filtre.
9. Dans la liste, sélectionnez la ligne de la table Transactions client et du champ Mode de paiement.
    * Vous pouvez appliquer les critères de sélection des transactions client à payer. Pour cet exemple, utilisez Électronique comme mode de paiement pour filtrer les transactions.  
10. Dans le champ Critères, saisissez ou sélectionnez une valeur.
11. Cliquez sur OK.
12. Cliquez sur OK.
13. Cliquez sur Créer des paiements.

## <a name="generate-a-payment-file"></a>Générer un fichier de paiement

