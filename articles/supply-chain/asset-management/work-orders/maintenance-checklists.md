---
title: Listes de contrôle de maintenance
description: Cet article décrit les listes de contrôle de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 25e9139ce57283482d8da4b7f1e5d6275c74ad28
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854527"
---
# <a name="maintenance-checklists"></a>Listes de contrôle de maintenance

[!include [banner](../../includes/banner.md)]



Les listes de contrôle de maintenance sont paramétrées sur les types de tâches de maintenance. Vous remplissez les listes de contrôle de maintenance dans le cadre du processus d’exécution d’un ordre de travail. Pour en savoir plus sur la manière de configurer les listes de contrôle de maintenance sur les types de tâche de maintenance sur la page **Valeurs par défaut du type de tâche de maintenance**, voir [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

Lorsque vous travaillez avec des listes de contrôle de maintenance sur un ordre de travail, vous pouvez remplir les listes de contrôle de maintenance associées aux types de tâche de maintenance. Vous pouvez également ajouter des listes de contrôle de maintenance supplémentaires.


## <a name="fill-in-a-maintenance-checklist"></a>Remplir une liste de contrôle de maintenance

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l’ordre de travail puis, dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **Lignes**, sélectionnez **Liste de contrôle de maintenance**.

3. La **Liste de contrôle de maintenance des ordres de travail** affiche les listes de contrôle pour toutes les tâches de l’ordre de travail. Si les tâches de l’ordre de travail ont différents types de tâche de maintenance, les listes de contrôle de maintenance peuvent être différentes sur chaque tâche de l’ordre de travail. Sélectionnez une tâche de l’ordre de travail pour utiliser la liste de contrôle de maintenance associée. Les détails de la ligne de la liste de contrôle de maintenance sélectionnée sont affichés sur l’organisateur **Détails de la ligne**.

4. Exécutez toutes les lignes de la liste de contrôle de maintenance, une à la fois, dans l’ordre où elles sont affichées. Vous exécutez une ligne de contrôle de maintenance en remplissant les champs sur l’organisateur **Détails de ligne**. Les informations requises pour accomplir une ligne peuvent varier, selon le type de ligne. Par exemple, sur une ligne de type **Texte**, vous ajoutez une note expliquant le résultat de votre contrôle. Sur une ligne de type **Mesure**, vous entrez une contre-valeur que vous lisez sur l’équipement, et vous pouvez également ajouter une note, si nécessaire. Une ligne de la liste de contrôle de maintenance de type **En-tête** est utilisée comme titre pour regrouper les lignes de liste de contrôle de maintenance qui s’affichent dessous. Vous ne devez pas renseigner un en-tête. Pour tous les autres types de lignes de liste de contrôle de maintenance, vous pouvez ajouter une note à une ligne de type **En-tête**.

5. Si les instructions sont associées à une ligne de liste de contrôle de maintenance, la case à cocher **Instructions** est sélectionnée. Lisez les instructions pour la ligne de la liste de contrôle de maintenance sélectionnée dans le champ **Instructions** du raccourci **Détails de ligne**.

6. Lorsque vous avez terminé une ligne de la liste de contrôle de maintenance, cochez la case **Vérifié** sur cette ligne pour la marquer avec le statut Terminé. Pour ignorer une ligne de la liste de contrôle de maintenance, car elle n’est pas pertinente pour la tâche de l’ordre de travail, cochez la case **S. o.** sur la ligne. Si la case à cocher **Obligatoire** est activée sur une ligne de la liste de contrôle de maintenance, vous devez activer la case à cocher **Vérifié** ou la case à cocher **S. o.**.

>[!NOTE]
>Vous pouvez uniquement mettre à jour les registres de la liste de contrôle de maintenance si l’ordre de travail est défini à l’état du cycle de vie [Actif](../setup-for-work-orders/work-order-lifecycle-states.md).  


## <a name="add-a-maintenance-checklist-line"></a>Ajouter une ligne de la liste de contrôle de maintenance

Les listes de contrôle de maintenance sont créées depuis la définition sur le type de tâche de maintenance par défaut et sont transférées vers une tâche de l’ordre de travail. Au besoin, vous pouvez ajouter des lignes de la liste de contrôle de maintenance à une tâche de l’ordre de travail. Les lignes de la liste de contrôle de maintenance ajoutées manuellement obtiennent la référence **Manuelle**.

1. Sur la page **Liste de contrôle de maintenance des ordres de travail**, sélectionnez la tâche de l’ordre de travail pour laquelle ajouter une liste de contrôle de maintenance.

2. Dans le raccourci **Lignes de liste de contrôle de maintenance**, sélectionnez une ligne de la liste de contrôle de maintenance. Ensuite, pour insérer une nouvelle ligne après la ligne sélectionnée, appuyez sur la touche **Flèche vers le bas**. Le numéro suivant dans la séquence est entré automatiquement dans le champ **Numéro de ligne**. Pour insérer une nouvelle ligne avant la ligne sélectionnée, sélectionnez **Ajouter une ligne**. 

3. Sur le champ **Nom**, entrez un nom de ligne pour la ligne de la liste de contrôle de maintenance.

4. Dans le champ **Type**, sélectionnez un type pour la ligne de la liste de contrôle de maintenance. Le raccourci **Détails de ligne** contient des champs associés pour chaque type de liste de contrôle de maintenance.
    - **Texte** - Utilisez ce type pour ajouter une ligne de liste de contrôle de maintenance ayant du texte qui décrit ce qui doit être effectué. Par exemple, vous pouvez utiliser ce type de liste de contrôle de maintenance si vous souhaitez qu’un employé contrôle ou vérifie quelque chose, sans attendre un résultat spécifique (mesurable). Après avoir sélectionné ce type, sous l’organisateur **Détails des lignes**, dans le champ **Instructions**, entrez du texte qui décrit ce qui doit être effectué.
    - **En-tête** - Une ligne de la liste de contrôle de maintenance de ce type est utilisée comme titre pour regrouper les lignes de liste de contrôle de maintenance qui s’affichent dessous. Ce type est utile si vous avez plusieurs lignes de liste de contrôle de maintenance qui peuvent être divisées en zones spécifiques. Après avoir sélectionné ce type, dans le champ **Nom**, entrez un nom descriptif.
    - **Modèle** - Ce type ne s’applique pas lorsque vous ajoutez manuellement une ligne de liste de contrôle de maintenance sur une tâche de l’ordre de travail.  
    - **Variable** - Utilisez ce type pour définir un résultat possible dans une plage sur la ligne de liste de contrôle de maintenance. Pour plus d’informations sur la configuration des variables de la liste de contrôle de maintenance, voir [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Après avoir sélectionné ce type, dans le champ **Nom**, entrez un nom descriptif pour la variable. Dans l’organisateur **Détails de ligne**, dans le champ **Variable**, sélectionnez la variable. Dans le champ **Instructions**, entrez du texte décrivant ce qui doit être effectué.
    - **Mesure** - Utilisez ce type pour enregistrer une mesure spécifique sur la ligne de liste de contrôle de maintenance. Après avoir sélectionné ce type, dans le champ **Nom**, entrez un nom pour la mesure. Dans l’organisateur **Détails de ligne**, dans les champs **Compteur** et **Unité**, sélectionnez les valeurs appropriées. Dans le champ **Instructions**, entrez du texte décrivant ce qui doit être effectué.

5. Lorsque vous avez terminé d’ajouter manuellement des lignes de liste de contrôle de maintenance, complétez les lignes comme décrit dans la section **Remplir une liste de contrôle de maintenance** ci-dessus.

>[!NOTE]
>Sur la page **Liste de contrôle de maintenance des ordres de travail**, vous ne pouvez pas supprimer les lignes de la liste de contrôle de maintenance avec la référence **Type de tâche**. Vous pouvez supprimer uniquement les lignes de la liste de contrôle de maintenance que vous ou d’autres agents de maintenance avez créé manuellement ayant la référence **Manuelle**.

L’illustration ci-dessous présente un exemple de liste de contrôle de maintenance.

![Figure 1.](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]