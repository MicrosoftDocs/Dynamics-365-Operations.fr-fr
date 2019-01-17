---
title: "Système de workflow"
description: "Cette rubrique décrit le système de workflow dans Microsoft Dynamics 365 for Finance and Operations."
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 770796b42e79ad616b469e1dbf5149789bff0788
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="workflow-system"></a>Système de workflow

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.

## <a name="what-is-workflow"></a>Qu'est-ce qu'un workflow ?

Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.

### <a name="workflow-is-a-system"></a>Un workflow est un système

Un workflow est un système installé avec Finance and Operations, qui s'exécute sur le Serveur d'objets d'application (AOS). Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.

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

