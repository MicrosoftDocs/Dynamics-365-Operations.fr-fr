---
title: Éléments du flux de travail
description: Cet article décrit les divers éléments qui constituent un workflow.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e145a8ebb082aa2d59c9a05a0cbbf38e9936bae0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900098"
---
# <a name="workflow-elements"></a>Éléments du flux de travail

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cet article décrit les divers éléments qui constituent un workflow.

Un workflow est constitué d’éléments. Les sections suivantes décrivent chaque type d’élément.

## <a name="tasks"></a>Tâches

Une *tâche* est une unité de travail qui doit être réalisée. Deux types de tâche peuvent être ajoutés à un workflow : des tâches manuelles et des tâches automatiques.

### <a name="manual-task"></a>Tâche manuelle

Une *tâche manuelle* est une unité de travail qui doit être réalisée par un utilisateur. Par exemple, un workflow d’état de dépenses peut comporter des tâches manuelles qui nécessitent les actions suivantes des utilisateurs affectés :

- révision des reçus soumis avec un état de dépenses ;
- appel du responsable d’un employé.

### <a name="automated-task"></a>Tâche automatique

Une *tâche automatique* est une unité de travail qui doit être réalisée par le système. Aucune intervention n’est requise. Par exemple, un workflow de commande client peut comporter des tâches automatiques qui nécessitent les actions suivantes du système :

- vérification d’un crédit ;
- création d’un enregistrement client pour le client, s’il n’en existe pas déjà un.

## <a name="approval-processes"></a>Processus d’approbation

Un *processus d’approbation* est un processus qui consiste en différentes étapes. À chaque étape d’approbation, l’utilisateur peut effectuer les actions suivantes :

- approuver le document ;
- rejeter le document ;
- demander une modification du document ;
- affecter le document à un autre utilisateur pour approbation.

## <a name="line-item-workflow-elements"></a>Éléments de workflow pour ligne

Vous pouvez créer un workflow pour traiter des documents ou les lignes d’un document. Par exemple, vous avez créé un workflow d’approbation pour des feuilles de temps. (Nous appellerons ce workflow le *workflow de document*.) Il est possible d’y ajouter un élément de *workflow pour ligne*. Lorsque l’élément de ligne est exécuté, chaque ligne du document est soumise pour traitement. Vous pouvez décider de faire traiter toutes les lignes par le même workflow pour ligne ou chaque ligne par un workflow pour ligne différent. Imaginons qu’un employé ait soumis une feuille de temps semblable à celle de la figure suivante.

![Workflow avec lignes.](./media/workflow_lineitemworkflow.gif)

Dans ce cas, il pourrait s’avérer utile de créer les workflows pour ligne suivants :

- **Workflow pour ligne 1** – Ce workflow permet de traiter les lignes dont l’ID projet est 1111.
- **Workflow pour ligne 2** – Ce workflow permet de traiter les lignes dont l’ID projet est 2222.
- **Workflow pour ligne 3** – Ce workflow permet de traiter les lignes dont l’ID projet est 3333.

## <a name="flow-control-elements"></a>Éléments de contrôle des flux

Les éléments suivants permettent de concevoir des workflows avec des branches secondaires ou avec des branches qui s’exécutent simultanément.

### <a name="manual-decision"></a>Décision manuelle

Une *décision manuelle* est un point où un workflow se divise en deux branches. Un utilisateur doit prendre une décision qui détermine la branche utilisée pour traiter le document soumis.

### <a name="conditional-decision"></a>Décision conditionnelle

Une *décision conditionnelle* est également un point où un workflow se divise en deux branches. Toutefois, le système détermine la branche utilisée pour traiter le document soumis. Pour prendre cette décision, le système évalue le document pour déterminer s’il répond aux conditions spécifiées.

### <a name="parallel-activity"></a>Activité parallèle

Une *activité parallèle* est un élément de workflow qui inclut deux branches de workflow ou plus s’exécutant simultanément.

### <a name="subworkflow"></a>Sous-workflow

Un *sous-workflow* est un workflow qui s’exécute dans le contexte d’un autre workflow.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]