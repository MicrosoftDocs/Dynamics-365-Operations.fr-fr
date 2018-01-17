---
title: "Définir les processus de comptage d'inventaire"
description: "Cette procédure vous guide dans la configuration des processus de comptage d'inventaire basiques en créant un groupe de comptage et un journal d'inventaire."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c14c846c55a3d821945160835817cd4f467deda9
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="define-inventory-counting-processes"></a>Définir les processus de comptage d'inventaire

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous guide dans la configuration des processus de comptage d'inventaire basiques en créant un groupe de comptage et un journal d'inventaire. Elle vous indique également comment activer les stratégies d'inventaire dans un entrepôt et au niveau d'un article. Ces tâches sont généralement effectuées par un superviseur de l'entrepôt. Il est impératif d'avoir déjà des produits lancés et des entrepôts. Si vous utilisez une société fictive, vous pouvez exécuter cette procédure à l'aide de la société USMF avec n'importe quel article en stock.


## <a name="create-a-counting-group"></a>Créer un groupe de comptage
1. Accédez à Gestion des stocks > Configuration > Stock > Groupes de comptage.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Groupe de comptage.
4. Tapez une valeur dans le champ Nom.
5. Sélectionnez une option dans le champ Code comptage.
    * Manuel : inclut des lignes chaque fois que vous exécutez la tâche. Autrement dit, vous décidez de l'intervalle d'inventaire pour le groupe de comptage.  Période : inclut des lignes pour la période dans le journal d'inventaire une fois que l'intervalle de périodes a expiré.   Stock épuisé : si le stock disponible atteint zéro (0), des lignes sont générées dans le journal d'inventaire lors de l'exécution de la tâche. Si le stock disponible atteint 0 après le comptage, des lignes sont générées la prochaine fois que vous lancez l'inventaire.   Minimum : insère des lignes dans le journal d'inventaire si le stock disponible est égal ou inférieur au minimum spécifié.  
    * Facultatif : Si vous avez spécifié Période dans le champ Code comptage, vous devez entrer l'intervalle de la période dans le champ Période de comptage. L'unité des intervalles est le jour.  
    * Lorsque vous exécutez la tâche pour créer des lignes dans le journal d'inventaire, de nouvelles lignes sont créées dans l'intervalle spécifié dans ce champ, indépendamment de la fréquence d'exécution de la tâche. Par exemple, si la période de comptage est définie sur 7, et que les lignes du journal ont été générées pour la dernière fois le 1er janvier, si une autre tâche a démarré le 5 janvier, sept jours ne se sont pas écoulés et donc aucune ligne n'est générée dans le journal pour cet intervalle. Si vous redémarrez la tâche le 8 janvier, des lignes sont générées pour la période dans le journal d'inventaire car 7 jours se sont écoulés.  
6. Cliquez sur Enregistrer.

## <a name="create-a-counting-journal-name"></a>Créer un nom de journal d'inventaire de stock
1. Accédez à Gestion des stocks > Configuration > Noms de journal > Stock.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Sélectionnez Comptage dans le champ Type de journal.
    * Facultatif : Vous pouvez sélectionner un ID de souche de N° de documents différent si vous souhaitez une souche de numéros spécifique pour des ID N° document générés lors de la création des journaux d'inventaire. La souche de numéros est créée dans la page Souches de numéros.  
6. Sélectionnez une option dans le champ Niveau de détail.
    * Il s'agit du niveau de détail appliqué lors de la validation du journal.  
    * Facultatif : Vous pouvez modifier la valeur du champ Réservation. Il s'agit de la méthode utilisée pour réserver des articles lors du comptage.   
    * Manuel : Les articles sont réservés manuellement dans l'écran Réservation.   Automatique : La quantité de commande est réservée dans le stock disponible de l'article.   Éclatement : La réservation fait partie de la planification de la transaction.  
7. Cliquez sur Enregistrer.

## <a name="set-standard-counting-journal-name"></a>Définir le nom du journal d'inventaire standard
1. Accédez à Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts.
2. Cliquez sur l'onglet Journaux.
3. Dans le champ Comptage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez le journal créé précédemment.
    * Ce journal sera ensuite le nom de journal par défaut pour les journaux de stock du type Comptage.  
5. Cliquez sur l'onglet Général.
    * Facultatif : Sélectionnez cette option pour verrouiller un article pendant le comptage pour éviter les mises à jour des bons de livraison, des prélèvements ou des enregistrements de prélèvement).  

## <a name="set-the-counting-policy-for-an-item"></a>Définir une stratégie de comptage pour un article
1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, cliquez sur le lien du numéro d'article du produit pour lequel vous souhaitez définir des stratégies d'inventaire.
    * Notez que vous devez sélectionner un article qui fait l'objet d'un suivi en stock. Un produit non stocké ne peut pas être compté. Si vous utilisez la société fictive USMF, vous pouvez sélectionner l'article A0001.  
3. Cliquez sur Modifier.
4. Activez ou désactivez l'extension de la section Gérer le stock.
5. Dans le champ Groupe de comptage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, dans le groupe de comptage que vous avez précédemment créé.
    * Ce produit est désormais inclus lorsque les lignes du journal d'inventaire sont créées à l'aide de ce groupe de comptage.  
7. Cliquez sur Enregistrer.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Définir la stratégie de comptage pour un article dans un entrepôt spécifique
1. Dans le volet Actions, cliquez sur Gérer le stock.
2. Cliquez sur Articles par entrepôt.
3. Cliquez sur Nouveau.
4. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, sélectionnez l'entrepôt pour lequel vous souhaitez définir des stratégies d'inventaire spécifiques.
6. Dans le champ Groupe de comptage, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Sélectionner un groupe de comptage dans la liste
    * Ici vous pouvez sélectionner un groupe de comptage spécifique devant être appliqué aux articles de l'entrepôt spécifique sélectionné. Lors du comptage dans cet entrepôt, cette stratégie de comptage remplace la stratégie de comptage générale pour l'article.  
8. Cliquez sur Enregistrer.

