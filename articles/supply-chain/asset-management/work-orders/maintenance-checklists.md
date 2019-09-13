---
title: Listes de contrôle de maintenance
description: Cette rubrique décrit les listes de contrôle de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875657"
---
# <a name="maintenance-checklists"></a>Listes de contrôle de maintenance


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Les listes de contrôle de maintenance sont paramétrées sur les types de tâches de maintenance et utilisées lorsque vous travaillez sur un ordre de travail. Remplir les listes de contrôle de maintenance fait partie de l'exécution d'un ordre de travail. Consultez la section [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) pour en savoir plus sur la manière de configurer les listes de contrôle de maintenance sur les types de tâche de maintenance dans le formulaire **Type de tâche de maintenance par défaut**.

Lorsque vous travaillez avec des listes de contrôle de maintenance sur un ordre de travail, vous pouvez compléter les listes de contrôle de maintenance associées aux types de tâche de maintenance. Il est également possible d'ajouter des listes de contrôle de maintenance supplémentaires.

## <a name="fill-out-a-maintenance-checklist"></a>Exécuter une liste de contrôle de maintenance

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l'ordre de travail et cliquez sur **Liste de contrôle de maintenance**.

3. Dans la **Liste de contrôle de maintenance des ordres de travail**, vous voyez les listes de contrôle de maintenance pour toutes les tâches de l'ordre de travail. Si les tâches de l'ordre de travail ont différents types de tâche de maintenance, les listes de contrôle de maintenance peuvent être différentes sur chaque tâche de l'ordre de travail. Sélectionnez une tâche de l'ordre de travail pour utiliser la liste de contrôle de maintenance associée. Les détails d'une ligne de la liste de contrôle de maintenance sélectionnée sont affichés sur l'organisateur **Détails de la ligne**.

4. Exécutez toutes les lignes de la liste de contrôle de maintenance, une à la fois, dans l'ordre séquentiel dans lequel elles sont affichées. Une ligne de la liste de contrôle de maintenance de type « En-tête » est utilisée comme titre pour regrouper les lignes de liste de contrôle de maintenance ci-dessous. Vous n'êtes pas obligé de compléter un en-tête, mais concernant tous les types de ligne de la liste de contrôle de maintenance, il est possible d'ajouter une **Note** à l'en-tête.

5. Si les instructions sont associées à une ligne de liste de contrôle de maintenance, la case à cocher **Instructions** est sélectionnée. Lisez les instructions pour la ligne de la liste de contrôle de maintenance sélectionnée sur le raccourci **Détails de ligne** > section **Instructions**.

6. Les informations requises pour exécuter une ligne de liste de contrôle de maintenance peut varier, selon le type de liste de contrôle de maintenance associée. Vous exécutez une ligne de contrôle de maintenance en complétant les champs sur l'organisateur **Détails de ligne**. Par exemple, sur une ligne de type « Texte », vous ajoutez **Note** pour déterminer le résultat de cette ligne de la liste de contrôle. Sur une ligne de type « Mesure », vous ajoutez la **Contre-valeur** que vous lisez sur l'équipement, et vous pouvez également ajouter une **Note**, si nécessaire.

- Lorsque vous avez terminé une ligne de la liste de contrôle de maintenance, cochez la case **Vérifié** sur la ligne pour la marquer avec le statut Terminé. Si vous souhaitez ignorer une ligne de la liste de contrôle de maintenance, car cela n'est pas pertinent pour la tâche de l'ordre de travail, cochez la case **N/A** sur la ligne. Si une ligne de la liste du contrôle de maintenance est marquée comme **Obligatoire**, vous devez la marquer comme « Vérifié » ou « N/A ».  
- Vous pouvez uniquement mettre à jour les registres de la liste de contrôle de maintenance si l'ordre de travail est défini à l'état du cycle de vie [Actif](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Ajouter une ligne de la liste de contrôle de maintenance

Les listes de contrôle de maintenance sont créées depuis la définition sur le type de tâche de maintenance par défaut et transférées vers une tâche de l'ordre de travail. Le cas échéant, vous pouvez ajouter des lignes de la liste de contrôle de maintenance à une tâche de l'ordre de travail. Les lignes de la liste de contrôle de maintenance ajoutées manuellement obtiennent la référence « Manuelle ».

1. Dans la **Liste de contrôle de maintenance des ordres de travail**, sélectionnez la tâche de l'ordre de travail pour laquelle vous souhaitez ajouter une liste de contrôle de maintenance.

2. Dans l'organisateur **Lignes de liste de contrôle de maintenance**, sélectionnez une ligne de liste de contrôle de maintenance et appuyez sur le bouton de la flèche vers le bas sur votre clavier si vous souhaitez insérer une nouvelle ligne une fois la ligne de la liste de contrôle de maintenance sélectionnée. Le numéro suivant dans la séquence est inséré automatiquement dans le champ **Numéro de ligne**. Vous pouvez également sélectionner une ligne de la liste de contrôle de maintenance et cliquer sur le bouton **Ajouter une ligne** si vous souhaitez insérer une nouvelle ligne au-dessus de la ligne sélectionnée de la liste de contrôle de maintenance.

3. Insérez un nom de ligne de la liste de contrôle de maintenance dans le champ **Nom**.

4. Dans le champ **Type**, sélectionnez un type pour la ligne de la liste de contrôle de maintenance. Pour chaque type de liste de contrôle de maintenance, les champs associés sont affichés sous l'organisateur **Détails de ligne**.  
  a. Le « Texte » est utilisé pour ajouter une ligne de liste de contrôle de maintenance avec une description textuelle indiquant ce qu'il convient de faire. Ce type de liste de contrôle de maintenance peut être utilisé si vous souhaitez qu'un employé contrôle ou vérifie quelque chose, sans attendre un résultat spécifique (mesurable). Insérez une description de ce qu'il convient de faire dans la section **Instructions** sur l'organisateur **Détails de ligne**. b. L'« En-tête » est utilisé comme en-tête pour regrouper les lignes de liste de contrôle de maintenance affichées en-dessous de l'en-tête. Cela est utile si vous avez plusieurs lignes de liste de contrôle de maintenance qui peuvent être divisées en zones spécifiques. Dans le champ **Nom**, insérez un nom descriptif.  
  c. Le « Modèle » ne s'applique pas lorsque vous ajoutez manuellement une ligne de liste de contrôle de maintenance sur une tâche de l'ordre de travail.  
  d. La « Variable » est utilisée pour définir un résultat possible dans une plage sur une ligne de liste de contrôle de maintenance. La configuration des variables de la liste de contrôle de maintenance est décrite dans la rubrique [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Insérez un nom pour décrire la variable dans le champ **Nom**. Sélectionnez le type de variable dans le champ **Variable**. Insérez une description de ce qu'il convient de faire dans la section **Instructions** sur l'organisateur **Détails de ligne**.  
  e. La « Mesure » permet d'enregistrer une mesure spécifique. Insérez un nom pour la mesure dans le champ **Nom**. Dans l'organisateur **Détails de ligne**, sélectionnez **Compteur** et **Unité**. Insérez une description de ce qu'il convient de faire dans la section **Instructions**.  

5. Lorsque vous avez fini d'ajouter manuellement des lignes de liste de contrôle de maintenance, complétez les lignes comme décrit dans la section ci-dessus.

>[!NOTE]
>Dans la section **Liste de contrôle de maintenance des ordres de travail**, vous ne pouvez pas supprimer les lignes de la liste de contrôle de maintenance avec la référence « Type de tâche ». Vous pouvez supprimer uniquement les lignes de la liste de contrôle de maintenance ayant la référence « Manuelle », que vous ou d'autres agents de maintenance avez créé manuellement.


![Figure 1](media/14-work-orders.png)

