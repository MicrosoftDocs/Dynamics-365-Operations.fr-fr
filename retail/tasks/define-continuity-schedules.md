--- 
title: " Définir les programmes périodiques"
description: "Cette rubrique vous guide dans le paramétrage d'un programme périodique (également appelé commandes récurrentes)."
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
ms.openlocfilehash: f51cb4fc093db60f03bbe6d2133f61ef90046155
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="define-continuity-schedules"></a> Définir les programmes périodiques

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette rubrique vous guide dans le paramétrage d'un programme périodique (également appelé commandes récurrentes). Elle utilise la société USRT dans les données de démonstration.


## <a name="create-continuity-program"></a>Créer un programme périodique
1. Accédez à Commerce et vente au détail > Périodicité > Programmes périodiques.
2. Cliquez sur Nouveau.
3. Dans le champ ID programme, entrez l'ID du programme périodique.
4. Dans le champ Début de commande, sélectionnez « Premier événement ».
    * Si un client passe une nouvelle commande pour le programme périodique, il existe deux options pour lesquelles le produit est expédié : 1. Premier événement : le premier produit du programme périodique est expédié.  2. Événement actuel : le produit actuel est expédié. Par exemple, trois mois dans le programme, le client reçoit le troisième produit du programme.  
5. Sélectionnez » Oui » pour demander la date de début de la commande.
6. Cliquez sur Ajouter une ligne.
7. Dans le champ Numéro d'article, tapez le numéro d'article du premier produit (0013).
8. Tapez « CP ».
9. Entrez la date à laquelle le premier produit sera disponible à la commande.
10. Cliquez sur Ajouter une ligne.
11. Dans le champ Numéro d'article, tapez « 0014 ».
12. Dans le champ Code intervalle de dates, effacez la valeur pour que le champ soit vide.
    * Pour cette procédure, désactivez l'intervalle de dates. Vous définirez la date comme valeur incrémentielle à partir de la date de début du premier article.  
13. Vous entrerez ici l'intervalle d'expédition des produits. Tapez « 30 ».
    * Pour un programme mensuel, vous entrerez 30 jours pour l'intervalle.  
14. Cliquez sur Ajouter une ligne.
15. Dans le champ Numéro d'article, tapez « 0015 ».
16. Tapez « Terminer ».
17. Cliquez sur Enregistrer.

## <a name="assign-to-continuity-item"></a>Affecter à un article périodique
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Sélectionnez l'article « 0016 ».
    * Pour cette procédure, vous sélectionnerez le numéro d'article 0016. Normalement, vous créerez un produit lancé dont une logique métier périodique supplémentaire est appliquée lorsqu'il est placé sur une commande client dans le centre d'appels.  
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Développez ou réduisez la section Vendre.
6. Vous entrerez ici le programme périodique que cet article représente. Tapez l'ID programme que vous avez créé précédemment.
    * Lorsque cet article est vendu dans un centre d'appels, une logique métier supplémentaire est appliquée à partir du programme périodique sélectionné.  
7. Cliquez sur Enregistrer.


