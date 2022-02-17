---
title: Vue d’ensemble du système de workflow
description: Cette rubrique décrit le système de workflow.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "56381"
- intro-internal
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70776ba0a0461998d2c1f62ba05b55cd4307a0f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067931"
---
# <a name="workflow-system-overview"></a>Vue d’ensemble du système de workflow

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cette rubrique décrit le système de workflow.

## <a name="what-is-workflow"></a>Qu’est-ce qu’un workflow ?

Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.

### <a name="workflow-is-a-system"></a>Un workflow est un système

Un workflow est un système qui s’exécute sur le serveur d’objets d’application (AOS). Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.

### <a name="workflow-is-a-business-process"></a>Un workflow est un processus entreprise

Un workflow représente un processus entreprise. Il définit la circulation, la progression, d’un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document. Par exemple, l’illustration suivante représente un workflow d’état de dépenses.

![Workflow avec des éléments affectés à des utilisateurs.](./media/workflow_user.gif)

Pour mieux comprendre ce workflow, supposons que Sam soumette un état de dépenses de 7 000 EUR. Dans ce scénario, Ivan doit passer en revue les reçus envoyés par Sam. Frank et Sue doivent ensuite approuver l’état de dépenses. Supposons maintenant que Sam soumette un état de dépenses de 11 000 EUR. Dans ce scénario, Ivan doit passer en revue les reçus, et Frank, Sue et Ann doivent approuver l’état de dépenses.

## <a name="benefits-of-using-the-workflow-system"></a>Avantages de l’utilisation du système de workflow

L’utilisation du système de workflow dans votre organisation présente plusieurs avantages :

- **Processus cohérents** – Vous pouvez définir le traitement de documents spécifiques, tels que des demandes d’achat ou des états de dépenses. Lorsque vous utilisez le système de workflow, vous pouvez vérifier que les documents sont traités et approuvés de manière cohérente et efficace.
- **Visibilité du processus** – Vous pouvez suivre le statut, l’historique et les mesures de performance des instances de workflow. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d’en optimiser l’efficacité.
- **Liste de travail centralisée** – Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.


## <a name="workflow-content"></a>Contenu de workflow

+ [Architecture de système de workflow](workflow-system-architecture.md)
+ [Éléments du flux de travail](workflow-elements.md)
+ [Actions dans les processus d’approbation d’un workflow](workflow-actions.md)
+ [Vue d’ensemble de création des workflows](create-workflow.md)
+ [Configuration des propriétés de workflow](configure-workflow-properties.md)
+ [Configurer des tâches manuelles dans un workflow](configure-manual-task-workflow.md)
+ [Configurer des tâches automatiques dans un workflow](configure-automated-task-workflow.md)
+ [Configurer des processus d’approbation dans un workflow](configure-approval-process-workflow.md)
+ [Configurer des étapes d’approbation dans un workflow](configure-approval-step-workflow.md)
+ [Configurer des décisions manuelles dans un workflow](configure-manual-decision-workflow.md)
+ [Configurer des décisions conditionnelles dans un workflow](configure-conditional-decision-workflow.md)
+ [Configurer des activités parallèles dans un workflow](configure-parallel-activity-workflow.md)
+ [Configurer des branches parallèles dans un workflow](configure-parallel-branch-workflow.md)
+ [Configuration de workflows pour ligne](configure-line-item-workflow.md)
+ [FAQ sur les workflows](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]