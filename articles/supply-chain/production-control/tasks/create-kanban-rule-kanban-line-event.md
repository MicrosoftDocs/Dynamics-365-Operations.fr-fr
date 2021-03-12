---
title: Créer une règle de kanban à l'aide d'un événement de ligne de kanban
description: Cette procédure crée une règle de kanban à l'aide du paramètre d'événement de ligne kanban pour déclencher l'extraction d'une activité de processus.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02511fea05cb1dfde17b1b8acaac97dcc136c062
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981251"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Créer une règle de kanban à l'aide d'un événement de ligne de kanban

[!include [banner](../../includes/banner.md)]

Cette procédure crée une règle de kanban à l'aide du paramètre d'événement de ligne kanban pour déclencher l'extraction d'une activité de processus. La règle de kanban est déclenchée par une activité de processus kanban, avec une quantité égale ou supérieure à 25 pour chaque. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié dans un environnement lean.


## <a name="create-a-kanban-rule"></a>Création d'une règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Cliquez sur Nouveau.
3. Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».
    * Des kanbans sont alors générés directement à partir de la demande. Cette option permet de paramétrer les règles qui définissent un scénario de fabrication à la commande.  
4. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Entrez ou sélectionnez SpeakerAssemblyAndPolish. La première activité d'une règle de kanban de fabrication est une activité de processus dans le flux de production. Lorsque vous sélectionnez l'activité, les dates de validité de l'activité sont copiées dans les dates de validité de la règle de kanban.  
5. Développez la section Détails.
6. Dans le champ Produit, tapez « L0001 ».
7. Développez la section Événements.
8. Dans le champ Événement de ligne de kanban, sélectionnez « Automatique ».
    * Ceci produit des kanbans d'événement à la demande.  Ce champ permet de configurer les règles de kanban qui réapprovisionnent les matières requises pour une activité de processus en aval. Quand vous choisissez Automatique, les kanbans d'événement sont créés avec la demande. Ce paramètre est recommandé si vous comptez exécuter la production le même jour.  
9. Définissez la quantité d'événement minimale sur « 25 ».
    * Des kanbans d'événement sont créés lorsque la quantité de la demande est égale ou supérieure à ce champ. C'est utile si vous voulez produire une quantité de commande inférieure au montant de ce champ sur une machine et supérieure au montant de ce champ sur une autre machine.  
10. Cliquez sur Enregistrer.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Créer une commande client et déclencher une chaîne kanban
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Entrez ou sélectionnez une valeur dans le champ Compte client.
    * Sélectionnez le compte client US-003, Forest Wholesales.  
4. Cliquez sur OK.
5. Entrez « L0001 » dans le champ Numéro d'article.
    * L0001 représente l'article pour lequel la règle de kanban est créée.  
6. Définir la Quantité sur « 27 ».
    * Puisque 27 est supérieur à la quantité minimum de 25 sur la règle de kanban, ceci déclenchera un kanban d'événement.  
7. Dans le champ Site, tapez « 1 ».
8. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
    * Sélectionner l'entrepôt 13.  
9. Cliquez sur Enregistrer.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Afficher le kanban produit par la règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Développer la section Kanbans.
    * Notez qu'un kanban pour 27 a été créé pour traiter l'activité basée sur la règle de kanban créée.  
    * Il s'agit de la dernière étape.  

