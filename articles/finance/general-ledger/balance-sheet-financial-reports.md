---
title: États financiers du bilan
description: Cet article décrit les états par défaut des bilans. Il décrit également les blocs de construction associés à ces états.
author: jinniew
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad297f401143388d682da175a6b14727a8f2f0
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643821"
---
# <a name="balance-sheet-financial-reports"></a>États financiers du bilan

[!include [banner](../includes/banner.md)]

Cet article décrit les états par défaut des bilans. Il décrit également les blocs de construction associés à ces états. 

## <a name="default-balance-sheet-reports"></a>États du bilan par défaut

Par défaut, le bilan se distingue par deux états. Dans un état, les sections sont empilées. Dans l’autre état, les sections sont côte à côte.

| État par défaut                       | Fonction                                                                                                                           |
|--------------------------------------|--------------------------------------------------------------------------------------|
| Bilan – Par défaut              | Permet d’afficher la position financière de l’organisation pour l’année.                    |
| Bilan et relevé des revenus côte à côte – Par défaut | Permet d’afficher la position financière de l’organisation pour l’année côte à côte. |

## <a name="building-blocks"></a>Blocs élémentaires
Les rapports financiers du relevé des revenus utilisent les blocs élémentaires suivants.

| État par défaut                       | Définition de ligne                       | Définition de colonne             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Bilan – Par défaut              | Bilan – Par défaut              | Année en cours et écart – Par défaut    |
| Bilan et relevé des revenus côte à côte – Par défaut | Bilan et relevé des revenus côte à côte – Par défaut | Colonne Année en cours – Par défaut |

### <a name="row-definition"></a>Définition de ligne

Les définitions de ligne pour les deux états du bilan contiennent les sections de chaque partie d’un bilan traditionnel. L’état côte à côte inclut un saut de colonne, de telle sorte que le passif et les capitaux propres du propriétaire s’affichent en regard de l’actif. La dimension Catégorie de compte principal est utilisée afin d’établir les deux définitions de ligne. Par conséquent, n’importe qui peut générer les rapports sans avoir à apporter de modifications.

### <a name="column-definition"></a>Définition de colonne

Les définitions de colonne contiennent différents types de colonnes afin d’offrir différents niveaux de détails et de données financières.

-   **Année en cours et écart – Types de colonne par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **DF** – Données financières pour l’année en cours
    -   **DF** – Données financières pour l’année passée
    -   **CALC** – Écart résultant de la soustraction entre l’année passée et l’année en cours

<!-- -->

-   **Colonne Année en cours – Par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **DF** – Données financières pour l’année en cours



## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états financiers](financial-reporting-getting-started.md)

[Afficher les états financiers](view-financial-reports.md)

[États financiers Dynamics (blog)](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
