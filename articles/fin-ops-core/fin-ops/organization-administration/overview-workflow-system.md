---
title: Vue d'ensemble du système de workflow
description: Cette rubrique décrit le système de workflow.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e5e795ca6f7831ecd3fa28be9782f0b287eea6e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190003"
---
# <a name="workflow-system-overview"></a>Vue d'ensemble du système de workflow

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le système de workflow.

## <a name="what-is-workflow"></a>Qu'est-ce qu'un workflow ?

Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.

### <a name="workflow-is-a-system"></a>Un workflow est un système

Un workflow est un système qui s'exécute sur le serveur d'objets d'application (AOS). Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.

### <a name="workflow-is-a-business-process"></a>Un workflow est un processus entreprise

Un workflow représente un processus entreprise. Il définit la circulation, la progression, d'un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document. Par exemple, l'illustration suivante représente un workflow d'état de dépenses.

![Workflow avec des éléments affectés à des utilisateurs](./media/workflow_user.gif)

Pour mieux comprendre ce workflow, supposons que Sam soumette un état de dépenses de USD 7 000. Dans ce scénario, Ivan doit passer en revue les reçus envoyés par Sam. Frank et Sue doivent ensuite approuver l'état de dépenses. Supposons maintenant que Sam soumette un état de dépenses de USD 11 000. Dans ce scénario, Ivan doit passer en revue les reçus, et Frank, Sue et Ann doivent approuver l'état de dépenses.

## <a name="benefits-of-using-the-workflow-system"></a>Avantages de l'utilisation du système de workflow

L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :

- **Processus cohérents** – Vous pouvez définir le traitement de documents spécifiques, tels que des demandes d'achat ou des états de dépenses. Lorsque vous utilisez le système de workflow, vous pouvez vérifier que les documents sont traités et approuvés de manière cohérente et efficace.
- **Visibilité du processus** – Vous pouvez suivre le statut, l'historique et les mesures de performance des instances de workflow. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.
- **Liste de travail centralisée** – Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.


## <a name="workflow-content"></a>Contenu de workflow

+ [Architecture de workflow](workflow-system-architecture.md)
+ [Éléments du workflow](workflow-elements.md)
+ [Actions de workflow](workflow-actions.md)
+ [Création d'un workflow](create-workflow.md)
+ [Configuration des propriétés de workflow](configure-workflow-properties.md)
+ [Configurer une tâche manuelle dans un workflow](configure-manual-task-workflow.md)
+ [Configurer une tâche automatique dans un workflow](configure-automated-task-workflow.md)
+ [Configurer un processus d'approbation dans un workflow](configure-approval-process-workflow.md)
+ [Configurer une étape d'approbation dans un workflow](configure-approval-step-workflow.md)
+ [Configurer une décision manuelle dans un workflow](configure-manual-decision-workflow.md)
+ [Configurer une décision conditionnelle dans un workflow](configure-conditional-decision-workflow.md)
+ [Configurer une activité parallèle dans un workflow](configure-parallel-activity-workflow.md)
+ [Configurer une branche parallèle dans un workflow](configure-parallel-branch-workflow.md)
+ [Configuration d'un workflow pour ligne](configure-line-item-workflow.md)
+ [FAQ Workflow](workflow-FAQ.md)