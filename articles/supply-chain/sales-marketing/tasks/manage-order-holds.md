---
title: Gérer les commandes en attente
description: Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caf6651813f0111b873db1769140d973f1a2e3b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427982"
---
# <a name="manage-order-holds"></a>Gérer les commandes en attente

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment placer des commandes client en attente, comment utiliser les extractions de blocage de commande, et comment supprimer les blocages de commande. Une commande peut être mise en attente pour des raisons diverses. Par exemple, vous pouvez mettre une commande en attente jusqu'à ce qu'une adresse du client ou un mode de paiement soit vérifié, ou jusqu'à ce qu'un responsable puisse revoir la limite de crédit du client. Tant que la commande est en attente, elle ne peut pas être traitée par l'entrepôt pour l'expédition. 

Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-order-holds"></a>Paramétrer des blocages de commande
1. Accédez à **volet Navigation > Modules > Ventes et marketing > Configuration > Commandes client > Codes de blocage de commande**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Code de blocage**, saisissez une valeur. Par exemple, tapez Rappeler.  
4. Tapez une valeur dans le champ **Description**.
    - Par exemple, Commande bloquée dans l'attente du rappel du client.  
    - Le cas échéant, activez la case à cocher **Supprimer des réservations** pour supprimer toute réservation physique de la commande lorsque ce code de blocage est ajouté.  
5. Cliquez sur **Enregistrer**.

## <a name="place-order-on-hold"></a>Mettre une commande en attente
1. Accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Cliquez sur **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Compte client**.
4. Cliquez sur **OK**.
5. Entrez ou sélectionnez une valeur dans le champ **Numéro d'article**.
6. Entrez un nombre dans le champ **Quantité**.
7. Cliquez sur **Commande client** dans le **volet Actions**.
8. Cliquez sur **Blocage de commandes**.
9. Cliquez sur **Nouveau**.
10. Dans le champ **Code de blocage**, sélectionnez le code créé à la sous-tâche précédente.
11. Cliquez sur **Enregistrer**.
12. Fermez la page.
13. Accédez à **Ventes et marketing > Commandes client > Toutes les commandes client**.
14. Dans la liste, marquez la ligne sélectionnée. Les champs « Ne pas traiter » et « Bloquer » des commandes actuellement en attente sont activés.
15. Dans le volet Actions, cliquez sur **Prélever et emballer**.

## <a name="manage-order-holds"></a>Gérer les commandes en attente
1. Accédez à **Ventes et marketing > Commandes client > Commandes en cours > Blocage de commandes**. La page **Blocage de commandes** se présente comme une console où vous pouvez obtenir une vue d'ensemble de tous les blocages actuels et traités, et les gérer avec les commandes client associées.     
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le **volet Actions**, cliquez sur **Extraire le blocage**.
4. Cliquez sur **Extraction**.
5. Dans la liste, désactiver la ligne sélectionnée. Le champ **Extrait par** contient désormais votre ID utilisateur.   
6. Cliquez sur **Supprimer l'extraction**.
7. Dans le **volet Actions**, cliquez sur **Supprimer le blocage**.
    - Lorsque vous êtes prêt à lever le blocage et à autoriser la commande à passer à l'étape de traitement suivante, vous devez supprimer le blocage. Si la commande n'a pas besoin d'être modifiée, vous pouvez exécuter l'action Supprimer les blocages. Toutefois, vous pouvez utiliser l'action Supprimer et modifier, si au moment de lever le blocage, la commande doit être mise à jour.      
    - L'action **Supprimer et soumettre** n'est applicable que si vous utilisez la fonctionnalité Centre d'appels.  
8. Cliquez sur **Supprimer le blocage**. Le blocage a désormais été effacé de la commande et supprimé de la liste Blocages actifs. Pour afficher tous les blocages ou leur sous-ensemble défini selon un statut spécifique, modifiez la valeur du champ Afficher.     

