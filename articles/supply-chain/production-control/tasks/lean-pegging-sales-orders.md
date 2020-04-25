---
title: Origine des besoins au plus juste pour les commandes client
description: Cette procédure traite de la validation de l'arborescence d'origine des besoins d'une ligne de vente où l'article est produit avec des kanbans.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e429fef6101f611d7a2c1b5323d6fe1e39d1cdd3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207000"
---
# <a name="lean-pegging-from-sales-orders"></a>Origine des besoins au plus juste pour les commandes client

[!include [banner](../../includes/banner.md)]

Cette procédure traite de la validation de l'arborescence d'origine des besoins d'une ligne de vente où l'article est produit avec des kanbans. Après la validation de l'arborescence d'origine des besoins, toutes les tâches de kanban sont planifiées. Cela est utile pour les scénarios de commande dans lesquels le responsable de la commande doit vérifier que la production peut démarrer immédiatement. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au responsable avancé des commandes travaillant pour une société fonctionnant selon le concept « au plus juste ».


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Créer une commande client pour un article contrôlé par kanban
1. Allez dans Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Utilisez US-001.  
4. Cliquez sur OK.
5. Entrez « L0001 » dans le champ Numéro d'article.
6. Définir la Quantité sur « 30 ».
    * Il est important que la quantité soit supérieure à 24 afin de déclencher la règle de kanban d'événement.  

## <a name="open-a-pegging-tree"></a>Ouvrir une arborescence d'origine des besoins 
1. Cliquez sur Produit et approvisionnement.
2. Cliquez sur Afficher l'arborescence d'origine des besoins.
    * Notez que l'arborescence d'origine des besoins affiche tous les niveaux de l'origine des besoins nécessaire pour la ligne de commande client. Dans ce cas, il existe deux niveaux de kanbans et de tous les composants nécessaires.  

## <a name="plan-the-pegging-tree"></a>Planifier l'arborescence de l'origine des besoins
1. Dans l'arborescence, sélectionnez « Ligne de vente 000832\Kanban 000558 ».
2. Développez la section Tâches de kanban.
    * Notez que le statut de la tâche de kanban est Non planifiée.  
3. Cliquez sur Planifier l'ensemble de l'arborescence des événements de l'origine des besoins.
    * Cela planifiera toutes les tâches de kanban dans l'arborescence d'origine des besoins, modifiant le statut de la tâche de Non planifiée à Planifiée.  
4. Actualisez la page.
    * Notez que le statut de la tâche de kanban est passé de Non planifiée à Planifiée.  
5. Dans l'arborescence, sélectionnez « Ligne de vente 000832\Kanban 000558\Stock en sortie pour L0001\Kanban 000559 ».
    * La tâche pour le deuxième kanban est également planifiée, car l'intégralité de l'arborescence d'origine des besoins est planifiée. Notez que le statut de la tâche de kanban est passé de Non planifiée à Planifiée.  

