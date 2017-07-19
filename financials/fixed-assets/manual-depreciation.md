---
title: Amortissement manuel
description: "Cet article donne une vue d'ensemble de la méthode d'amortissement manuelle."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 75d176623b4fdf2198440becd0345628f873f6da
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="manual-depreciation"></a>Amortissement manuel

[!include[banner](../includes/banner.md)]


Cet article donne une vue d'ensemble de la méthode d'amortissement manuelle.

Lorsque vous paramétrez un profil d'amortissement d'immobilisation et sélectionnez **Manuel** dans le champ **Méthode** de la page **Profils d'amortissement**, l'amortissement des immobilisations affectées au profil d'amortissement est déterminé par le pourcentage que vous spécifiez pour chaque intervalle dans l'année civile. Les intervalles pour lesquels vous paramétrez des pourcentages sont validés en fonction de la valeur sélectionnée dans le champ **Période fréquence** de l'organisateur **Général** de la page **Profils d'amortissement**. Les valeurs que vous pouvez sélectionner sont les suivants :

-   Tous les ans
-   Mensuel
-   Trimestriel
-   Semestriel
-   Opérations diverses

Après avoir sélectionné la fréquence de période, cliquez sur **Programmes manuels** et paramétrez les pourcentages pour chaque intervalle de validation. Ensemble, les programmes manuels et les intervalles de validation définissent le montant d'amortissement, comme l'illustrent les exemples de cet article. L'amortissement manuel est toujours calculé comme pourcentage du prix d'acquisition. Dans le cas de l'amortissement manuel, les pourcentages que vous spécifiez dans les intervalles de l'amortissement ne doivent pas nécessairement totaliser 100 pour cent. L'amortissement manuel est une méthode d'amortissement flexible qui est souvent utilisée pour définir un profil d'amortissement exceptionnel sur la page **Registres**, tel qu'un amortissement non périodique à des fins particulières (par exemple, de taxe).

## <a name="examples"></a>Exemples
Prix d'acquisition : 11 000,00 Valeur de mise au rebut prévue : 1 000,00 Le tableau suivant indique les intervalles et les pourcentages que vous paramétrez sur la page **Programmes de profil d'amortissement des immobilisations**.

| Nombre d'intervalles | Pourcentage |
|-----------------|------------|
| 1               | 10,00      |
| 2               | 50,00      |
| 3               | 8,00       |

Le tableau suivant illustre la façon dont l'amortissement de chaque intervalle est calculé.

|  Nombre d'intervalles | Calcul du montant d'amortissement annuel | Valeur nette à la fin de l'intervalle |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11 000 – 1 000) × 10 % = 1 000                | 10 000 (11 000 – 1 000)                   |
| 2                | (11 000 – 1 000) × 50 % = 5 000                | 5 000 (10 000 – 5 000)                    |
| 3                | (11 000 – 1 000) × 8 % = 800                   | 4 200 (5 000 – 800)                       |

Si vous sélectionnez **Mensuel** dans le champ**Période fréquence**, vous paramétrez 12 intervalles de planification manuels. Le tableau suivant illustre les montants d'amortissement pour les deux premiers intervalles.

| Intervalle | Montant d'amortissement            |
|----------|--------------------------------|
| Janvier  | (11 000 – 1 000) × 10 % = 1 000 |
| Février | (11 000 – 1 000) × 50 % = 5 000 |

Si vous sélectionnez **Semestriel** dans le champ **Période fréquence**, vous paramétrez deux intervalles de planification manuels. Le tableau suivant illustre les montants d'amortissement pour ces deux intervalles.

| Intervalle    | Montant d'amortissement            |
|-------------|--------------------------------|
| 30 juin     | (11 000 – 1 000) × 10 % = 1 000 |
| 31 décembre | (11 000 – 1 000) × 50 % = 5 000 |

Le total des pourcentages de tous les intervalles ne doit pas être 100. Toutefois, vous recevez un message si la valeur du champ **Pourcentage cumulé** de la page **Programmes de profil d'amortissement des immobilisations** n'est pas **100**.




