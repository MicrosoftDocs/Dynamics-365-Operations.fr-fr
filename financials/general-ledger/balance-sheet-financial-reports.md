---
title: "États financiers du bilan"
description: "Cet article décrit les états par défaut pour les bilans. Elle décrit également les blocs élémentaires associés à ces états."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 664d32c2bfecb50e24fd48a66ab5b34cef6c09a3
ms.lasthandoff: 03/31/2017


---

# <a name="balance-sheet-financial-reports"></a>États financiers du bilan

Cet article décrit les états par défaut pour les bilans. Elle décrit également les blocs élémentaires associés à ces états. 

<a name="default-balance-sheet-reports"></a>États du bilan par défaut
-----------------------------

Par défaut, le bilan se distingue par deux états. Dans un état, les sections sont empilées. Dans l'autre état, les sections sont côte à côte.

| État par défaut                       | Fonction                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Bilan – Par défaut              | Permet d'afficher la position financière de l'organisation pour l'année.                                                                 |
| Bilan côte à côte bilan – Par défaut | Permet d'afficher la position financière de l'organisation pour l'année. Les actifs et passifs et les capitaux propres des actionnaires sont affichés côte à côte. |

## <a name="building-blocks"></a>Blocs élémentaires
Les rapports financiers du relevé des revenus utilisent les blocs élémentaires suivants.

| État par défaut                       | Définition de ligne                       | Définition de colonne             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Bilan - Par défaut              | Bilan - Par défaut              | Année en cours et écart - Par défaut    |
| Bilan côte à côte bilan – Par défaut | Bilan côte à côte bilan – Par défaut | Colonne Année en cours - Par défaut |

### <a name="row-definition"></a>Définition de ligne

Les définitions de ligne pour les deux états du bilan contiennent les sections de chaque partie d'un bilan traditionnel. L'état côte à côte inclut un saut de colonne, de telle sorte que le passif et les capitaux propres du propriétaire s'affichent en regard de l'actif. La dimension Catégorie de compte principal est utilisée afin d'établir les deux définitions de ligne. Par conséquent, n'importe qui peut générer les rapports sans avoir à apporter de modifications.

### <a name="column-definition"></a>Définition de colonne

Les définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.

-   **Année en cours et écart – Types de colonne par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **DF** – Données financières pour l'année en cours
    -   **DF** – Données financières pour l'année passée
    -   **CALC** – Écart résultant de la soustraction entre l'année passée et l'année en cours

<!-- -->

-   **Colonne Année en cours – Par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **DF** – Données financières pour l'année en cours

 

<a name="see-also"></a>Voir également :
--------

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[Blog d'états financiers de Dynamics (http://blogs.msdn.com/b/dynamics_financial_reporting/)]


