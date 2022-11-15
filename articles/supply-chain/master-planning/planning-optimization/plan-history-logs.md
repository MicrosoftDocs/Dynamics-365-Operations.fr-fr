---
title: Afficher l’historique du plan et les journaux de planification
description: Cet article explique comment afficher l’historique des tâches de planification.
author: t-benebo
ms.date: 06/01/2020
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
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ab469686a009364bf53cb963506fd2107075a283
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740929"
---
# <a name="view-plan-history-and-planning-logs"></a>Afficher l’historique du plan et les journaux de planification

[!include [banner](../../includes/banner.md)]

Cet article explique comment afficher l’historique des tâches de planification dans Microsoft Dynamics 365 Supply Chain Management.

Pour afficher l’historique d’un plan, ouvrez le plan en accédant à **Planification** \> **Paramétrage** \> **Plans** \> **Plans généraux** et en sélectionnant **Historique**. L’historique répertorie toutes les tâches du plan sélectionné. La liste inclut les tâches terminées et actives.

Le système conserve un maximum de 60 enregistrements d'historique par plan directeur et supprime les enregistrements de plus de 30 jours. Chaque fois que vous exécutez un nouveau calcul de planification générale, le système ajoute un nouvel enregistrement d'historique, puis nettoie les enregistrements les plus anciens si nécessaire.

Outre le fait de voir l’heure de début et le statut des tâches, vous pouvez afficher le journal pour une tâche spécifique. Le journal inclut des informations supplémentaires et des avertissements. Toutes les tâches n’ont pas un journal. Pour afficher le journal pour une tâche, sélectionnez **Journal**. Les entrées de journal ne sont stockées que pendant 30 jours après la date de fin de la tâche, après quoi elles sont automatiquement supprimées.

Si l’option **Traitement par lots** du raccourci **Exécuter en arrière-plan** a été activée lors de la configuration du traitement de la planification générale, le journal des tâches de traitement par lots affiche plus d’informations sur les avertissements et les erreurs générés lors de l’exécution de la planification générale. Par exemple, les erreurs de confirmation automatique sont capturées uniquement dans le journal des tâches de traitement par lots. Elles ne sont pas affichées dans les journaux de la page **Historique**.

Pour afficher les erreurs de confirmation automatique et d’autres avertissements ou erreurs qui se sont produits lors d’une exécution de la planification générale, procédez comme suit.

1. Allez dans **Administration du système \> Recherches \> Traitements par lots**.
1. Recherchez et sélectionnez l’enregistrement qui représente l’exécution de la planification générale qui vous intéresse. (Par exemple, la valeur du champ **Description de la tâche** peut commencer par *Planification générale*.)
1. Suivez l’une de ces étapes, selon que vous utilisez ou non le *formulaire amélioré* ou le *formulaire hérité (non amélioré)* pour la page **Tâches de traitement par lots** :

    - Si vous utilisez le formulaire amélioré : dans le volet Actions, sélectionnez **Historique des tâches de traitement par lots**. Puis, sur la page **Historique des tâches de traitement par lots**, dans le volet Actions, sélectionnez **Journal**.
    - Si vous utilisez le formulaire hérité : dans le volet Actions, sur l’onglet **Tâche de traitement par lots**, sélectionnez **Journal**.

1. Sélectionnez **Détails du message** pour ouvrir le volet **Détails du message**, où vous pouvez afficher tous les avertissements et les erreurs qui ont été capturés pendant le traitement.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
