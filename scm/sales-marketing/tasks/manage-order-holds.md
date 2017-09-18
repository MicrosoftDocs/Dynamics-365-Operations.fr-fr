--- 
title: "Gérer les commandes en attente"
description: "Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande."
author: omulvad
manager: AnnBe
ms.date: 01/09/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 6a9487567620b7b7d6d15015f7f0b7675e227c8a
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="manage-order-holds"></a>Gérer les commandes en attente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande. Une commande peut être mise en attente pour des raisons diverses. Par exemple, vous pouvez mettre une commande en attente jusqu'à ce qu'une adresse du client ou un mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client. Tant que la commande est en attente, elle ne peut pas être traitée par l'entrepôt pour l'expédition. 

Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-order-holds"></a>Paramétrer des blocages de commande
1. Accédez à Ventes et marketing > Paramétrage > Commandes client > Codes de blocage de commande.
2. Cliquez sur Nouveau.
3. Dans le champ Code de blocage, saisissez une valeur.
    * Par exemple, tapez Rappeler.  
4. Dans le champ Description, entrez une valeur.
    * Par exemple, Commande bloquée dans l'attente du rappel du client.  
    * Le cas échéant, activez la case à cocher Supprimer des réservations pour supprimer toute réservation physique de la commande lorsque ce code de blocage est ajouté.  
5. Cliquez sur Enregistrer.

## <a name="place-order-on-hold"></a>Mettre une commande en attente
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
4. Cliquez sur OK.
5. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
6. Dans le champ Quantité, entrer un numéro.
7. Cliquez sur Commandes client dans le volet Actions.
8. Cliquez sur Blocage de commandes.
9. Cliquez sur Nouveau.
10. Dans le champ Code de blocage, sélectionnez le code créé à la sous-tâche précédente.
11. Cliquez sur Enregistrer.
12. Fermez la page.
13. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
14. Dans la liste, marquez la ligne sélectionnée.
    * Les champs « Ne pas traiter » et « Bloquer » des commandes actuellement en attente sont activés.    
15. Cliquez sur Prélever et emballer dans le volet Actions.

## <a name="manage-order-holds"></a>Gérer les commandes en attente
1. Accédez à Ventes et marketing > Commandes client > Commandes en cours > Blocage de commandes.
    * La page de blocage des commandes se présente comme une console où vous pouvez obtenir une vue d'ensemble de tous les blocages actuels et traités, et les gèrer avec les commandes client associées.      
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le volet Action, cliquez sur Extraire le blocage.
4. Cliquez sur Extraction.
5. Dans la liste, désactiver la ligne sélectionnée.
    * Le champ Extrait par contient désormais votre ID utilisateur.   
6. Cliquez sur Supprimer l'extraction.
7. Dans le volet Action, cliquez sur Supprimer le blocage.
    * Lorsque vous êtes prêt à lever le blocage et à autoriser la commande à passer à l'étape de traitement suivante, vous devez supprimer le blocage. Si la commande n'a pas besoin d'être modifiée, vous pouvez exécuter l'action Supprimer les blocages. Toutefois, vous pouvez utiliser l'action Supprimer et modifier, si au moment de lever le blocage, la commande doit être mise à jour.      
    * L'action Supprimer et soumettre n'est applicable que si vous utilisez la fonctionnalité Centre d'appels.  
8. Cliquez sur Supprimer le blocage.
    * Le blocage a désormais été effacé de la commande et supprimé de la liste Blocages actifs. Pour afficher tous les blocages ou leur sous-ensemble défini selon un statut spécifique, modifiez la valeur du champ Afficher.     

