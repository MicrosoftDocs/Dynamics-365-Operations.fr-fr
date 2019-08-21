---
title: Créer une règle de kanban d'événement de vente
description: Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e05ebbec1ffb3e3cdd683d847ffc1d2cf817357
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837780"
---
# <a name="create-a-sales-event-kanban-rule"></a>Créer une règle de kanban d'événement de vente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban qui est déclenchée pendant la création d'une commande client. La règle de kanban d'événement réalise le réapprovisionnement des besoins provenant des lignes de commande client. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Elle est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié.




## <a name="create-a-new-kanban-rule"></a>Créer une règle de kanban
1. Accédez aux règles de kanban.
2. Cliquez sur Nouveau.
3. Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».
    * Le fait de sélectionner Événement signifie que la règle de kanban est déclenchée par un événement, par exemple par la création d'une ligne de commande client.   Cela s'applique aux domaines où chaque kanban doit couvrir une demande spécifique.  
4. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Sélectionnez Assemblage final.  
5. Développez la section Détails.
6. Dans le champ Produit, saisissez ou sélectionnez une valeur.
    * Sélectionnez L0050.  

## <a name="define-an-event"></a>Définir un événement
1. Développez la section Événements.
2. Dans le champ Événement de vente, sélectionnez « Automatique ».
    * En sélectionnant l'événement de vente Automatique, cette règle de kanban sera déclenchée automatiquement lorsqu'une ligne de vente correspondra au produit et à l'emplacement de réception. Dans cette procédure, il s'agit du produit L0050 dans l'entrepôt 13.  
3. Définissez la quantité d'événement minimale sur « 50 ».
    * Avec une quantité minimale d'événement de 50, la règle de kanban ne sera déclenchée que par les événements d'une quantité de 50 ou davantage.  
4. Développez la section Flux de production.
    * Notez que l'emplacement de réception est l'entrepôt 13. Cela signifie que cette règle de kanban sera déclenchée pour cet emplacement.  
    * Dans cet exemple, une ligne de vente du produit L0050, avec une quantité de 50 ou plus, dans l'entrepôt 13, déclenchera cette règle de kanban.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Créer une ligne de vente pour déclencher une règle de kanban d'événement
1. Allez dans Toutes les commandes client.
    * Un avertissement s'affiche lorsque la règle de kanban est enregistrée, ce qui signifie que les kanbans sont créés en temps réel lors de la création de commande client.  
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Par exemple, sélectionnez US-003.  
4. Cliquez sur OK.
5. Entrez « L0050 » dans le champ Numéro d'article.
6. Dans le champ Site, tapez « 1 ».
    * Sélectionnez Site 1 car l'entrepôt 13 se trouve sur le site 1.  
7. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
    * Définissez Entrepôt sur 13.  
8. Définir la Quantité sur « 75 ».
    * Entrez une quantité de 50 ou supérieure, pour déclencher la règle de kanban créée.  

## <a name="verify-that-kanban-is-created"></a>Vérifier que le kanban est créé
1. Cliquez sur Produit et approvisionnement.
2. Cliquez sur Afficher l'arborescence d'origine des besoins.
    * Notez qu'un kanban est créé avec la même quantité que la ligne de vente. Vous pouvez également afficher les sorties de matériel nécessaires pour produire le L0050. Il s'agit de la dernière étape de cette procédure.  

