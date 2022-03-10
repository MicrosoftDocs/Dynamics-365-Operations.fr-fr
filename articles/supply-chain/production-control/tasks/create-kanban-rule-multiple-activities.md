---
title: Créer une règle de kanban pour des activités multiples
description: Cette procédure montre comment créer une règle de kanban qui inclut des activités multiples à partir d’un flux de production.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f55034f4f0557023ce0c659c1e8258214cf8bfa3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569237"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Créer une règle de kanban pour des activités multiples

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment créer une règle de kanban qui inclut des activités multiples à partir d’un flux de production. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d’un produit nouveau ou modifié dans un environnement lean.


## <a name="create-a-new-kanban-rule"></a>Créer une règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Cliquez sur Nouveau.
3. Dans le champ Stratégie de réapprovisionnement, sélectionnez « Planifié ».
4. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Sélectionnez SpeakerAssemblyAndPolish.  
5. Choisissez la case à cocher Plusieurs activités.
    * Le but est d’inclure plus d’une activité dans la règle de kanban. Vous devez choisir un chemin dans le flux de production quand vous choisissez la dernière activité du plan.  
6. Entrez ou sélectionnez une valeur dans le champ Dernière activité de plan.
    * Sélectionnez « SpeakerTestAndPackaging ». Une page s’ouvre automatiquement quand vous avez sélectionné la valeur. Sélectionnez le flux kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging. Cliquez sur OK.  
7. Développez la section Détails.
8. Dans le champ Produit, saisissez ou sélectionnez une valeur.
    * Sélectionner l’article L0006.  

## <a name="create-kanban-and-view-jobs"></a>Créer un kanban et afficher les tâches
1. Développer la section Kanbans.
2. Cliquez sur Ajouter.
3. Entrez 1 dans le champ Nombre de nouveaux kanbans.
    * Cette opération crée un kanban.  
4. Définissez la quantité de produit sur 3.
    * Kanban traitera 3 produits.  
5. Entrez une date et une heure dans le champ Date/heure d’échéance.
    * Vous pouvez entrer Aujourd’hui.  
6. Cliquez sur Créer.
7. Cliquez sur Détails.
    * Notez que le kanban a deux opérations de traitement à partir d’un flux de production. La première est SpeakerAssemblyAndPolish, et la deuxième est SpeakerTestAndPackaging.  
    * Il s’agit de la dernière étape.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]