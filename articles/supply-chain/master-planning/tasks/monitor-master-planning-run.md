---
title: Surveiller l’exécution d’une planification générale
description: Cette rubrique explique comment le responsable de production peut vérifier si une exécution de la planification est en cours.
author: josaw1
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1733562768b3fe869f326bbfb47b6135a91b5cb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829640"
---
# <a name="monitor-a-master-planning-run"></a>Surveiller l’exécution d’une planification générale

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Utiliser un diagramme de Gantt pour visualiser la progression de la planification

Depuis la page **Afficher la progression de la planification**, vous pouvez afficher les détails des exécutions de planification historiques en tant que diagramme de Gantt. Cette fonctionnalité peut vous aider à comprendre le temps passé aux différentes phases de la planification. Pour une tâche de planification active actuelle, la page **Afficher la progression de la planification** peut être utilisée pour suivre la progression et afficher le temps restant estimé.

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a>Activer et utiliser la fonction de visualisation de la progression du plan

Pour utiliser cette fonctionnalité, procédez comme suit :

1. Dans l’espace de travail **Gestion des fonctionnalités**, sous l’onglet **Nouveau**, sélectionnez **Visualisation de la progression de la planification** dans la liste. Si la fonctionnalité ne s’affiche pas sur l’onglet **Nouveau**, examinez les onglets **Non activé** et **Tous**.
1. Sélectionnez **Activer maintenant**. Sinon, sélectionnez **Programme**, puis sélectionnez l’heure à laquelle vous souhaitez activer la fonctionnalité.

La page **Afficher la progression de la planification** peut afficher les tâches historiques de planification et les tâches actives de planification. 

Pour afficher les tâches historiques de planification, il existe deux options. 

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**, puis, dans le volet Actions, sélectionnez **Historique**. Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**
1. Accédez à **Planification \> Espaces de travail \> Planification**, sur la vignette de planification cliquez sur **Historique**. Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**

Pour afficher les tâches actives de planification, il existe deux options. 
1. Accédez à **Planification \> Espaces de travail \> Planification**, dans le volet Actions, sélectionnez **Processus de planification non terminés**. Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**.
1. Accédez à **Planification \> Espaces de travail \> Planification**, sur la vignette de planification cliquez sur **Afficher la progression**. Avec la tâche souhaitée est activée, sélectionnez **Recherches**, puis sélectionnez **Afficher la progression**

Remarque : vous pouvez afficher les tâches actives uniquement lorsqu’une tâche de planification est en cours.

### <a name="analyze-a-master-planning-job"></a>Analyser une tâche de planification

Dans le diagramme de Gantt, vous pouvez développer chacun des processus de planification suivants pour afficher des informations supplémentaires sur le temps passé :

- Initialisation
- Suppression et insertion de données
- Planification de la couverture
- Retards
- Messages d’action
- Finalisation
- Confirmation automatique

Le diagramme de Gantt est un outil utile si vous souhaitez afficher l’impact de l’utilisation des messages d’action.

#### <a name="navigation-in-the-gantt-chart"></a>Navigation dans le diagramme de Gantt

- Pour développer le groupe sélectionné et afficher les détails, sélectionnez le signe (**+**) dans l’arborescence.
- Pour réduire le groupe sélectionné, sélectionnez le signe (**-**) dans l’arborescence.
- Vous pouvez utiliser le clavier pour la navigation. Utilisez les touches **Flèche vers le haut** et **Flèche vers le bas** pour passer d’une ligne à l’autre. Utilisez les touches **Flèche droite** et **Flèche gauche** pour développer et réduire les groupes.
- Pour ouvrir ou fermer tous les niveaux dans le diagramme de Gantt, sélectionnez **Développer tout** ou **Réduire tout**.
- Pour afficher le temps de traitement associé, survolez une tâche avec la souris. (Les tâches sont le niveau le plus bas dans le diagramme de Gantt.)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Afficher une exécution supplémentaire de planification pour comparer des tâches

En sélectionnant une tâche de planification dans le champ **Afficher une exécution de planification supplémentaire**, vous pouvez afficher une exécution supplémentaire de planification dans le diagramme de Gantt et comparer les deux tâches.

#### <a name="bom-level-display"></a>Affichage au niveau de la nomenclature

Les niveaux de nomenclature sont affichés différemment pour la planification de couverture, les retards, les actions et la confirmation.

- **Planification de la couverture** : les niveaux de nomenclature sont affichés comme prévu. Ils sont calculés de haut en bas.

    **Exemple :** niveau de nomenclature 0, 1, 2

- **Retards** : les niveaux de nomenclature sont affichés comme niveaux de nomenclature de planification de la couverture multipliés par – 1. (Autrement dit, ils ont un signe négatif.)

    **Exemple :** niveau de nomenclature –2, –1, 0

- **Message d’action** : les niveaux de nomenclature sont affichés comme prévu. Ils sont calculés de haut en bas.

    **Exemple :** niveau de nomenclature 0, 1, 2

- **Confirmation automatique** : les niveaux de nomenclature sont affichés comme 999 moins le niveau de nomenclature de la planification de couverture.

    **Exemple :** niveau de nomenclature 999, 998, 997

Le tableau suivant résume le comportement.

| Niveau de nomenclature qui s’affiche | Article final | Sous-composant | Matière première |
|---|---|---|---|
| Planification de la couverture | 0 | 1 | 2 |
| Retards | 0 | –1 | –2 |
| Message d’action | 0 | 1 | 2 |
| Confirmation automatique | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Visualiser la progression

Si vous affichez une tâche de planification en cours d’exécution, la progression est affichée en couleurs dans le diagramme de Gantt. Les couleurs suivantes s’appliquent au thème bleu. Pour d’autres thèmes de couleur, les couleurs différeront.

- **Bleu foncé** : Tâches de planification terminées.
- **Orange** : la tâche qui est actuellement ouverte.
- **Bleu clair** : l’estimation pour les tâches restantes.

La couleur est affichée uniquement sur le niveau le plus bas dans le diagramme de Gantt. Sélectionnez **Développer tout** pour afficher toutes les tâches dans la tâche de planification. L’estimation des tâches restantes est basée sur des tâches historiques de planification.

## <a name="run-master-planning-and-track-processing-time"></a>Exécuter la planification et suivre le temps de traitement

1. Dans le tableau de bord par défaut, sélectionnez **Planification**.
1. Dans le champ **Plan**, saisissez ou sélectionnez une valeur.
1. Sélectionnez **Exécuter**.
1. Définissez l’option **Suivre le temps de traitement** sur **Oui**.
1. Entrez un nombre dans le champ **Nombre de threads**.
1. Dans l’organisateur **Enregistrements à inclure**, sélectionnez **Filtre**.
1. Dans la grille, sélectionnez la ligne où le champ **Champ** est défini sur **Numéro d’article**.
1. Dans le champ **Critère**, entrez une valeur.
1. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]