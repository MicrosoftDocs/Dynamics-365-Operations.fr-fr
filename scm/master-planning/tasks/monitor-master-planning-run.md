--- 
title: "Surveiller l'exécution d'une planification générale"
description: "Le responsable de production veut voir si une exécution de la planification est en cours."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8eb19ac9ded4dc2a091ff733f2f43cb6cafa1b43
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-a-master-planning-run"></a>Surveiller l'exécution d'une planification générale

[!include[task guide banner](../../includes/task-guide-banner.md)]

Le responsable de production veut voir si une exécution de la planification est en cours. Utilisez les données fictives de la société USMF pour réaliser cette procédure.


## <a name="run-master-planning"></a>Exécuter la planification générale
1. Cliquez sur Planification.
    * Vous trouverez cela dans le tableau de bord par défaut.  
2. Dans le champ Régime, saisissez ou sélectionnez une valeur.
    * Exemple : StaticPlan  
3. Cliquez sur Exécuter.
4. Dans le champ Suivre la durée du traitement, sélectionnez Oui.
    * Si le champ est déjà sélectionné, ignorez cette étape.  
5. Entrez un nombre dans le champ Nombre de threads.
6. Développez les enregistrements pour inclure la section.
7. Cliquez sur Filtre.
8. Dans la liste, marquez la ligne sélectionnée.
    * Marquez la ligne où Champ = Numéro d'article.  
9. Dans le champ Critères, saisissez ou sélectionnez une valeur.
    * Exemple : T0001  
10. Cliquez sur OK.
11. Cliquez sur OK.

## <a name="monitor-the-master-planning-run"></a>Surveiller l'exécution d'une planification générale
1. Cliquez sur Historique.
2. Cliquez sur Recherches.
3. Cliquez sur Durée de tâche du processus.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Pour chaque article vous pouvez obtenir une vue d'ensemble de la durée nécessaire pour réaliser chaque étape de planification.  


