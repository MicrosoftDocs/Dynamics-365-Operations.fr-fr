--- 
title: " Créer des commandes de centre d'appels"
description: "Cette procédure décrit la recherche d'un client, la création d'une commande, la recherche d'un produit et la collecte du paiement auprès du client."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 62f88cc2e28405a9d2eb43819fb09d83a64658b6
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="create-call-center-orders"></a> Créer des commandes de centre d'appels

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la recherche d'un client, la création d'une commande, la recherche d'un produit et la collecte du paiement auprès du client. Cette procédure utilise la société fictive USRT et est destinée au commis aux commandes client. Conditions préalables : l'utilisateur exécutant la procédure est configuré en tant qu'utilisateur du centre d'appels et le catalogue semi-annuel de Fabrikam est publié avec au moins un code source.

1. Accédez à Commerce et vente au détail > Clients > Service client.
2. Dans le champ Texte recherché, saisissez les critères de recherche du client.
    * Pour cet exemple de procédure, saisissez « Karen », puis appuyez sur l'onglet.  
3. Cliquez sur Rechercher.
    * Comme il n'existe qu'un seul client nommé Karen dans les données de démonstration, il est automatiquement sélectionné.  
4. Cliquez sur Nouvelle commande client.
5. Développez ou réduisez la section En-tête de commande client.
6. Sélectionnez le code source du catalogue.
    * Si aucun code source n'est actif, vous pouvez fermer le champ Source et ignorer cette étape.  
7. Cliquez sur Ajouter une ligne.
8. Dans le champ Numéro d'article, saisissez le terme de recherche de l'article.
    * Pour cet exemple de procédure, saisissez le numéro d'article partiel « 8111 », puis appuyez sur l'onglet. La fenêtre de recherche d'article s'affiche alors.  
9. Sélectionner le produit à ajouter à la commande client
10. Saisissez la quantité vendue.
11. Cliquez sur Créer.
12. Cliquez sur Terminer pour capturer le paiement du client.
13. Cliquez sur Ajouter.
    * Le lien Ajouter se trouve sous l'onglet Paiements. Développez l'onglet Paiements s'il est réduit.  
14. Sélectionnez le mode de paiement.
    * Pour cette procédure, sélectionnez le mode de paiement au comptant.  
15. Fermez la page.
16. Entrez le montant.
    * Pour cette procédure, saisissez un montant égal au solde de la commande qui s'affiche dans la page Résumé de la commande client à gauche du champ de montant. Vous pourrez ainsi terminer la commande comme étant intégralement payée.  
17. Cliquez sur OK.
18. Cliquez sur Soumettre.


