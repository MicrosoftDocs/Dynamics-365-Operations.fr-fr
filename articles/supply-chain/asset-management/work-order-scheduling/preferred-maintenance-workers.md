---
title: Définir les agents de maintenance préférés
description: Cette rubrique explique comment paramétrer des agents de maintenance préférés dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887409"
---
# <a name="preferred-maintenance-workers"></a>Agents de maintenance préférés

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Vous pouvez définir une préférence concernant les agents de maintenance affectés pour effectuer des ordres de travail lors de la planification des ordres de travail. L'utilisation de cette fonctionnalité est facultative. Elle peut néanmoins vous aider à choisir l'agent de maintenance le plus qualifié pour effectuer une tâche, selon les compétences et les aptitudes des agents. Par conséquent, lors de la planification des ordres de travail, le paramétrage dans **Agents de maintenance préférés** permet de déterminer si un agent de maintenance ou un groupe d'agents spécifique doit être prévu pour un ordre de travail. Seuls les agents de maintenance qui sont disponibles pour le temps de planification sont planifiés. Si un paramétrage d'agent de maintenance préféré correspond à un ordre de travail durant la planification, mais si l'agent de maintenance est alloué à d'autres tâches, l'ordre de travail est alors planifié pour un autre agent de maintenance disponible.

Avant de paramétrer des agents de maintenance préférés, vous devez paramétrer tout d'abord les agents et groupes d'agents de maintenance qui doivent être disponibles pour sélection. Consultez la section [Agents et groupes d'agents de maintenance](../setup-for-objects/workers-and-worker-groups.md) pour obtenir une description sur la manière de configurer les agents et groupes d'agents de maintenance.

## <a name="set-up-preferred-workers"></a>Configurer les agents préférés

Un agent de maintenance ou un groupe d'agents de maintenance préféré peut être associé à un(e)

- commerce  
- variante du type de tâche de maintenance  
- type de tâche de maintenance  
- catégorie de type tâche de maintenance  
- actif  
- type d'actif spécifique  

ou à une combinaison de ces sélections. Plus vous faites de sélections pour le même enregistrement, plus votre paramétrage est spécifique.

1. Cliquez sur **Gestion des actifs** > **Paramétrage** > **Agents** > **Agents de maintenance préférés**.

2. Cliquez sur **Nouveau** pour créer un enregistrement.

3. Commencez en créant un paramétrage de groupe d'agents ou d'agent de maintenance « par défaut » sans sélection dans les champs indiqués dans la liste à puce ci-dessus. Autrement dit, vous effectuez une seule sélection dans le champ **Groupe d'agents de maintenance préféré** ou le champ **Agent de maintenance préféré**. Dans la figure ci-dessous, vous voyez un exemple dans le premier enregistrement dans lequel « Demandes » est sélectionné comme le groupe d'agents de maintenance préféré.

>[!NOTE]
>Ce paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l'ordre de travail dans le cadre de la planification des ordres de travail.

4. Répétez l'étape 2 pour créer un enregistrement. Effectuez les sélections nécessaires, selon le niveau de détail pour l'agent ou le groupe d'agents de maintenance préféré. *Exemple :* dans la figure ci-dessous, dans le sixième enregistrement, l'agent de maintenance Shawn Richardson est sélectionné comme agent préféré. Il est automatiquement sélectionné lors de la planification d'un ordre de travail contenant l'agent « CH-BP1-03-02 et la tâche de maintenance de type "Évaluation du site" », s'il est disponible au moment prévu.

>[!NOTE]
>En général, si un agent de maintenance préféré est sélectionné lors de la planification des ordres de travail, le module Gestion des actifs parcourt tous les enregistrements **Agents de maintenance préférés** pour vérifier une correspondance éventuelle, en vérifiant toujours la combinaison la plus spécifique en premier. Si aucune correspondance n'est trouvée, l'enregistrement « par défaut » avec une sélection dans le champ **Groupe d'agents de maintenance préféré** ou le champ **Agent de maintenance préféré** est utilisé.


![Figure 1](media/02-work-order-scheduling.png)

Vous pouvez également paramétrer les agents de maintenance responsables à sélectionner lorsqu'une demande de maintenance ou un ordre de travail est créé. Dans **Tous les ordres de travail** et **Toutes les demandes de maintenance**, vous pouvez modifier la sélection, le cas échéant. Consultez [Agents de maintenance responsables](../setup-for-maintenance-requests/responsible-workers.md) pour en savoir plus.

Lors de la planification des ordres de travail, différents scores sont calculés pour déterminer quels agents doivent effectuer les tâches associées à un ordre de travail (ces scores sont paramétrés dans le lien**Paramètres de la gestion des actifs** **Planification des ordres de travail** > ). Si au moins deux agents de maintenance préférés ou responsables obtiennent le même score lors de la planification des ordres de travail, un agent est sélectionné de manière aléatoire. Sinon, il s'agit toujours de l'agent ayant le score le plus élevé qui est affecté pour exécuter un ordre de travail.

