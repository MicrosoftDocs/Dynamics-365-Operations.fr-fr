---
title: "Vue d&quot;ensemble du système de workflow"
description: "Cet article décrit le système de workflow dans Microsoft Dynamics 365 for Operations."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>Vue d'ensemble du système de workflow

[!include[banner](../includes/banner.md)]


Cet article décrit le système de workflow dans Microsoft Dynamics 365 for Operations.

<a name="what-is-workflow"></a>Qu'est-ce qu'un workflow ?
-----------------

Le terme *workflow* revêt deux concepts : workflow en tant que système et workflow en tant que processus entreprise.
### <a name="workflow-is-a-system"></a>Un workflow est un système

Un workflow est un système installé avec Dynamics 365 for Operations, qui s'exécute sur le Serveur d'objets d'application (AOS). Les fonctionnalités du système de workflow permettent de créer des workflows ou des processus entreprise.

### <a name="workflow-is-a-business-process"></a>Un workflow est un processus entreprise

Un workflow représente un processus entreprise. Il définit la circulation, la progression, d'un document dans le système en indiquant qui doit traiter une tâche, prendre une décision ou approuver un document. Par exemple, la figure suivante représente un workflow d'état de dépenses. ![Workflow avec des éléments affectés à des utilisateurs](./media/workflow_user.gif) Pour mieux comprendre ce workflow, supposons que Sam envoie un état des dépenses de 7 000 USD. Dans ce scénario, Ivan doit passer en revue les reçus envoyés par Sam. Frank et Sue doivent ensuite approuver l'état de dépenses. Supposons maintenant que Sam soumette un état de dépenses de USD 11 000. Dans ce scénario, Ivan doit passer en revue les reçus, et Frank, Sue et Ann doivent approuver l'état de dépenses.
Avantages de l'utilisation du système de workflow
-------------------------------------

L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :
-   **Processus cohérents** – Vous pouvez définir le traitement de documents spécifiques, tels que des demandes d'achat ou des états de dépenses. Lorsque vous utilisez le système de workflow, vous pouvez vérifier que les documents sont traités et approuvés de manière cohérente et efficace.
-   **Visibilité du processus** – Vous pouvez suivre le statut, l'historique et les mesures de performance des instances de workflow. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.
-   **Liste de travail centralisée** – Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées.





