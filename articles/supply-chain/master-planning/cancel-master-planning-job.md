---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité de planification intégrée.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 513aee3b9475506e28db4bffe90df58567b6b281
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816602"
---
# <a name="cancel-a-master-planning-job"></a>Annuler une tâche de planification

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics 365 Supply Chain Management, il existe plusieurs options pour annuler un travail de planification. Par exemple, vous souhaiterez peut-être annuler une tâche de planification si elle a été démarrée par erreur ou s’exécute plus longtemps que prévu et que vous souhaitez y mettre fin. La meilleure façon d’annuler un travail de planification se trouve sur la page **Processus de planification inachevés**. Les options alternatives aux pages **Traitement par lots** et **Traitement par lots améliorés** ne doivent être utilisées que si l’annulation de la tâche de planification de la page **Processus de planification inachevés** ne s’est pas terminée en quelques minutes.

## <a name="preferred-cancel-option"></a>Option d’annulation préférée
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Annuler le travail de planification de la page **Processus de planification inachevés**
1. Allez dans **Planification > Recherches et états > Planification > Processus de planification non terminés**.
2. Sélectionnez la ligne du processus de planification à annuler.
3. Cliquez sur **Annuler**.

## <a name="additional-cancel-options"></a>Options d’annulation supplémentaires
Celles-ci ne doivent être utilisées que si l’annulation du travail de planification sur la page **Processus de planification non terminés** ne s’est pas terminée en quelques minutes.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Suppression du travail de planification de la page **Traitement par lots**
1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Sélectionnez la ligne de la tâche de planification à supprimer.
3. Cliquez sur **Supprimer**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Abandon de la tâche du travail de planification de la page **Traitement par lots améliorés**
1. Accédez à **Administration du système > Recherches > Traitements par lots**.
2. Si l’ID de tâche n’apparaît pas dans la liste, cliquez sur **Basculer vers le formulaire amélioré**, sinon passez à l’étape suivante.
3. Ouvrez le traitement par lots. Cliquez sur l’**ID de tâche** du traitement par lots avec les tâches à terminer.
4. Dans **Tâches des traitements par lots**, sélectionnez les tâches à terminer.
5. Cliquez sur **Modifier le statut**, choisissez **Annulation** et cliquez sur **OK**.
6. Sur l’organisateur **Tâches des traitements par lots**, cliquez sur **Abandonner**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]