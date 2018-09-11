--- 
title: "Surveiller l'exécution d'une planification générale"
description: "Le responsable de production veut voir si une exécution de la planification est en cours."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="monitor-a-master-planning-run"></a>Surveiller l'exécution d'une planification générale

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


