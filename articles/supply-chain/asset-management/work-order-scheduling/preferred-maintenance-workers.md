---
title: Définir les agents de maintenance préférés
description: Cette rubrique explique comment paramétrer des agents de maintenance préférés dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5b044e4616555559be51b0846327b1d55bfe47b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822537"
---
# <a name="set-up-preferred-maintenance-workers"></a>Définir les agents de maintenance préférés

[!include [banner](../../includes/banner.md)]

 

Lors de la planification des ordres de travail, vous pouvez définir une préférence concernant l’agent de maintenance ou le groupe de collaborateurs affecté pour effectuer l’ordre de travail. L’utilisation de cette fonctionnalité est facultative. Elle peut néanmoins vous aider à choisir l’agent de maintenance le plus qualifié pour effectuer une tâche, selon les compétences et les aptitudes des agents. Seuls les agents de maintenance qui sont disponibles pour le temps de planification sont planifiés. Si un paramétrage d’agent de maintenance préféré correspond à un ordre de travail durant la planification, mais si l’agent de maintenance est alloué à d’autres tâches, l’ordre de travail est alors planifié pour un autre agent de maintenance disponible.

Avant de paramétrer des agents de maintenance recommandés, vous devez d’abord paramétrer les agents de maintenance et les groupes de collaborateurs. Pour une description de la manière de configurer les agents et groupes d’agents de maintenance, consultez [Agents et groupes d’agents de maintenance](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Configurer les agents préférés

Un agent de maintenance ou un groupe d’agents de maintenance préféré peut être associé à l’un des éléments suivants :

- commerce  
- variante du type de tâche de maintenance  
- type de tâche de maintenance  
- catégorie de type tâche de maintenance  
- actif  
- type d’actif spécifique  

Plus vous faites de sélections pour le même enregistrement, plus votre paramétrage est spécifique.

1. Cliquez sur **Gestion des actifs** > **Paramétrage** > **Agents** > **Agents de maintenance préférés**.

2. Cliquez sur **Nouveau** pour créer un enregistrement.

3. Commencez par créer un agents et groupes d’agents de maintenance « par défaut ». Autrement dit, vous effectuez une seule sélection dans le champ **Groupe d’agents de maintenance préféré** ou le champ **Agent de maintenance préféré**. Dans la capture d’écran ci-dessous, vous voyez un exemple dans le premier enregistrement dans lequel « Demandes » est sélectionné comme le **groupe d’agents de maintenance préféré**.

    [!NOTE] Le paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l’ordre de travail.

4. Répétez l’étape 2 pour créer un enregistrement. Effectuez les sélections nécessaires, selon le niveau de détail pour l’agent ou le groupe d’agents de maintenance préféré. 

    *Exemple :* dans la capture d’écran ci-dessous, dans le sixième enregistrement, l’agent de maintenance Shawn Richardson est sélectionné comme agent préféré. Il est automatiquement sélectionné lors de la planification d’un ordre de travail contenant l’agent « CH-BP1-03-02 et la tâche de maintenance de type "Évaluation du site" », s’il est disponible au moment prévu.

    [!NOTE] En général, si un agent de maintenance préféré est sélectionné lors de la planification des ordres de travail, le module Gestion des actifs parcourt tous les enregistrements **Agents de maintenance préférés** pour vérifier une correspondance éventuelle, en vérifiant toujours la combinaison la plus spécifique en premier. Si aucune correspondance n’est trouvée, l’enregistrement « par défaut » avec une sélection dans le champ **Groupe d’agents de maintenance préféré** ou le champ **Agent de maintenance préféré** est utilisé.

![Figure 1](media/02-work-order-scheduling.png)

Vous pouvez également paramétrer les agents de maintenance *responsables* à sélectionner lorsqu’une demande de maintenance ou un ordre de travail est créé. Vous pouvez modifier la sélection dans **Tous les ordres de travail** et **Toutes les demandes de maintenance**, le cas échéant. Pour plus d’informations, consultez [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md).

Lors de la planification des ordres de travail, différents scores sont calculés pour déterminer quels agents doivent effectuer les tâches associées à un ordre de travail (ces scores sont paramétrés dans le lien **Paramètres de la gestion des actifs** **Planification des ordres de travail** > ). Si au moins deux agents de maintenance préférés ou responsables obtiennent le même score lors de la planification des ordres de travail, un agent est sélectionné de manière aléatoire. Sinon, il s’agit toujours de l’agent ayant le score le plus élevé qui est affecté pour exécuter un ordre de travail.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]