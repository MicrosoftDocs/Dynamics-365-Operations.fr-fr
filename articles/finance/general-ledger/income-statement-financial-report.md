---
title: Rapport financier du relevé des revenus
description: Cet article décrit l’état par défaut des comptes de résultats. Il décrit également les blocs de construction associés à cet état.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a1f20ed5e2a84e0d18101ede46ffffef4230c7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868458"
---
# <a name="income-statement-financial-report"></a>Rapport financier du relevé des revenus

[!include [banner](../includes/banner.md)]

Cet article décrit l’état par défaut des comptes de résultats. Il décrit également les blocs de construction associés à cet état. 

## <a name="default-income-statement-report"></a>Rapport par défaut du relevé des revenus

| État par défaut             | Fonction                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Relevé des revenus – Par défaut. | Permet d’afficher la rentabilité de l’organisation pour la période en cours ainsi que pour l’année en cours. |

## <a name="building-blocks"></a>Blocs élémentaires
Le rapport financier du relevé des revenus utilise les blocs élémentaires suivants.

| Rapport par défaut             | Définition de ligne                     | Définition de colonne          |
|----------------------------|------------------------------------|----------------------------|
| Relevé des revenus – Par défaut | Récapitulatif du relevé des revenus – Par défaut | Périodique et Année en cours – Par défaut |

### <a name="row-definition"></a>Définition de ligne

La définition de ligne, Récapitulatif du relevé des revenus – Par défaut, contient une section pour chaque partie d’un relevé de revenus traditionnel. La dimension Catégorie de compte principal est utilisée afin d’établir cette définition de ligne. Par conséquent, n’importe qui peut générer le rapport sans avoir à apporter de modifications.

### <a name="column-definition"></a>Définition de colonne

Les définitions de colonne contiennent différents types de colonnes afin d’offrir différents niveaux de détails et de données financières.

-   **Périodique et Année en cours – Types de colonne par défaut :**
    -   **DESC** : Description de la définition de ligne.
    -   **DF** – Données financières pour la période en cours
    -   **DF** – Données financières pour l’année en cours



## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états financiers](financial-reporting-getting-started.md)

[Afficher les états financiers](view-financial-reports.md)

[États financiers Dynamics (blog)](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
