---
title: Afficher l’historique du plan et les journaux de planification
description: Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 93e8f933524b34116987c9e0d91d226e21d98f4d
ms.sourcegitcommit: 5c9a5bfef507ed36f0f849ab56fa0aa8abb78d54
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2021
ms.locfileid: "6646485"
---
# <a name="view-plan-history-and-planning-logs"></a>Afficher l’historique du plan et les journaux de planification

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment afficher l’historique des tâches de planification déclenchées par la fonctionnalité d’Optimisation de la planification dans Microsoft Dynamics 365 Supply Chain Management.

Pour afficher l’historique d’un plan, ouvrez le plan en accédant à **Planification** \> **Paramétrage** \> **Plans** \> **Plans généraux** et en sélectionnant **Historique**. L’historique répertorie toutes les tâches du plan sélectionné. La liste inclut les tâches terminées et actives.

L’historique des exécutions de la planification générale de l’optimisation de la planification ne conserve que 60 enregistrements maximum par plan général. Chaque fois que vous exécutez un nouveau calcul de planification générale, le premier enregistrement de l’historique de ce plan est supprimé.

Outre le fait de voir l’heure de début et le statut des tâches, vous pouvez afficher le journal pour une tâche spécifique. Le journal inclut des informations supplémentaires et des avertissements. Toutes les tâches n’ont pas un journal. Pour afficher le journal pour une tâche, sélectionnez **Journal**. Les entrées de journal ne sont stockées que pendant 30 jours après la date de fin de la tâche, après quoi elles sont automatiquement supprimées.

Si l'option **Traitement par lots** du raccourci **Exécuter en arrière-plan** a été activée lors de la configuration du traitement de la planification générale, le journal des tâches de traitement par lots affiche plus d'informations sur les avertissements et les erreurs générés lors de l'exécution de la planification générale. Par exemple, les erreurs de confirmation automatique sont capturées uniquement dans le journal des tâches de traitement par lots. Elles ne sont pas affichées dans les journaux de la page **Historique**.

Pour afficher les erreurs de confirmation automatique et d'autres avertissements ou erreurs qui se sont produits lors d'une exécution de la planification générale, procédez comme suit.

1. Allez dans **Administration du système \> Recherches \> Traitements par lots**.
1. Recherchez et sélectionnez l'enregistrement qui représente l'exécution de la planification générale qui vous intéresse. (Par exemple, la valeur du champ **Description de la tâche** peut commencer par *Planification générale*.)
1. Suivez l'une de ces étapes, selon que vous utilisez ou non le *formulaire amélioré* ou le *formulaire hérité (non amélioré)* pour la page **Tâches de traitement par lots** :

    - Si vous utilisez le formulaire amélioré : dans le volet Actions, sélectionnez **Historique des tâches de traitement par lots**. Puis, sur la page **Historique des tâches de traitement par lots**, dans le volet Actions, sélectionnez **Journal**.
    - Si vous utilisez le formulaire hérité : dans le volet Actions, sur l'onglet **Tâche de traitement par lots**, sélectionnez **Journal**.

1. Sélectionnez **Détails du message** pour ouvrir le volet **Détails du message**, où vous pouvez afficher tous les avertissements et les erreurs qui ont été capturés pendant le traitement.

## <a name="related-resources"></a>Ressources associées

- [Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)
- [Mise en route de l’optimisation de la planification](get-started.md)
- [Analyse de concordance d’optimisation de la planification](planning-optimization-fit-analysis.md)
- [Appliquer les filtres à un plan](plan-filters.md)
- [Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
