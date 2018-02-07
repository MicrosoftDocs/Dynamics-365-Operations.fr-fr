--- 
title: " Utiliser un programme de continuité"
description: "Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: e94d9ded5cefc731e28af6898004419a00e0c189
ms.contentlocale: fr-fr
ms.lasthandoff: 11/14/2017

---
# <a name="use-a-continuity-program"></a> Utiliser un programme de continuité

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure vous guide dans la vente d'un programme périodique et le traitement des commandes client associées. Pour exécuter cette procédure, l'utilisateur doit être configuré comme utilisateur du centre d'appels. La société fictive USRT sert d'exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Clients > Service client.
2. Dans le champ SearchText, tapez « Karen », puis appuyez sur la touche Tab.
    * La boîte de dialogue de recherche avancée doit s'afficher. Si elle ne s'affiche pas, cliquez sur Rechercher à droite de ce champ.  
3. Dans la liste, marquez la ligne sélectionnée.
    * Il ne doit y avoir qu'une ligne portant la mention Karen Berg. Sélectionnez la ligne en cliquant sur la colonne à l'extrême gauche de la grille.  
4. Cliquez sur Sélectionner.
5. Cliquez sur Nouvelle commande client.
    * Il est conseillé de noter le numéro de la commande client. Vous en aurez besoin ultérieurement dans cette procédure.  
6. Dans le champ Numéro d'article, tapez « 88000 », puis appuyez sur la touche Tab.
    * Il s'agit d'un article périodique dans les données de démonstration USRT.  
7. Cliquez sur Terminé.
8. Dans le champ Mode de paiement, entrez « Visa ».
9. Cliquez sur Ajouter une carte de crédit.
    * Entrez les informations de carte de crédit requises dans cette page.  
10. Cliquez sur OK.
11. Développez la section Paiement.
    * Pour envoyer une commande du centre d'appels, les paiements doivent être entrés pour la commande.  
12. Cliquez sur OK.
13. Cliquez sur Soumettre.
    * Vous avez terminé de créer une commande périodique. Vous exécuterez ensuite deux processus de traitement par lots qui sont utilisés pour traiter les commandes périodiques.  
14. Fermez la page.
15. Accédez à Commerce et vente au détail > Périodicité > Traiter les paiements périodiques.
16. Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.
17. Cliquez sur OK.
18. Accédez à Commerce et vente au détail > Périodicité > Créer des commandes enfant périodiques.
    * Ce processus créera des commandes client en fonction des paramètres de vos programmes périodiques.  
19. Dans le champ Article périodique, tapez « 88000 », puis appuyez sur la touche Tab.
    * L'article « 88000 »est un article périodique dans les données de démonstration USRT.  
20. Dans le champ Commande client, entrez ou sélectionnez une valeur.
    * Entrez le numéro de la commande client que vous avez noté précédemment dans la procédure. La durée de traitement sera maintenue à une valeur minimale pour cette procédure. Le champ Commande client est facultatif ; vous pouvez traiter toutes les commandes pour n'importe quel programme.  
21. Cliquez sur OK.


