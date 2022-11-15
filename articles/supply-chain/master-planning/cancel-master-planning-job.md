---
title: Annuler une tâche créée à l’aide du moteur de planification générale déprécié
description: Cet article explique comment annuler une tâche de planification active qui utilise le moteur de planification générale déprécié.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7b71a43f407050dccb7550db7c4b6a98a596d589
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740875"
---
# <a name="cancel-a-job-that-was-created-using-the-deprecated-master-planning-engine"></a>Annuler une tâche créée à l’aide du moteur de planification générale déprécié

[!include [banner](../includes/banner.md)]

Il existe plusieurs options pour annuler une tâche créée avec le moteur de planification générale déprécié. Par exemple, vous souhaiterez peut-être annuler une tâche de planification si elle a été démarrée par erreur ou s’exécute plus longtemps que prévu et que vous souhaitez y mettre fin.

La meilleure façon d’annuler un travail de planification se trouve sur la page **Processus de planification inachevés**. Les options alternatives aux pages **Traitement par lots** et **Traitement par lots améliorés** ne doivent être utilisées que si l’annulation de la tâche de planification de la page **Processus de planification inachevés** ne s’est pas terminée en quelques minutes.

## <a name="preferred-cancel-option"></a>Option d’annulation préférée

### <a name="cancel-master-planning-job-from-the-unfinished-planning-processes-page"></a>Annuler une tâche de planification générale de la page Processus de planification inachevés

1. Allez dans **Planification > Recherches et états > Planification > Processus de planification non terminés**.
2. Sélectionnez la ligne du processus de planification à annuler.
3. Sélectionnez **Annuler**.

## <a name="additional-cancel-options"></a>Options d’annulation supplémentaires

Celles-ci ne doivent être utilisées que si l’annulation du travail de planification sur la page **Processus de planification non terminés** ne s’est pas terminée en quelques minutes.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Suppression du travail de planification de la page **Traitement par lots**

1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Sélectionnez la ligne de la tâche de planification à supprimer.
3. Sélectionnez **Supprimer**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Abandon de la tâche du travail de planification de la page **Traitement par lots améliorés**

1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Si l’ID de tâche n’apparaît pas dans la liste, cliquez sur **Basculer vers le formulaire amélioré**, sinon passez à l’étape suivante.
3. Ouvrez le traitement par lots. Sélectionnez l’**ID de tâche** du traitement par lots avec les tâches à terminer.
4. Dans **Tâches des traitements par lots**, sélectionnez les tâches à terminer.
5. Sélectionnez **Modifier le statut**, choisissez **Annulation** et cliquez sur **OK**.
6. Sur l’organisateur **Tâches des traitements par lots**, cliquez sur **Abandonner**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]