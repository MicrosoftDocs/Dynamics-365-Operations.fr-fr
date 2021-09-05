---
title: Stratégies de droit aux avantages
description: Cette rubrique fournit des informations sur les stratégies de droit aux avantages, qui définissent qui peut prétendre à des avantages spécifiques.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 88b801be5be4f9abcec4632fe1d96dbd83aaec96
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416927"
---
# <a name="benefit-eligibility-policies"></a>Stratégies de droit aux avantages

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit des informations sur les stratégies de droit aux avantages, qui définissent qui peut prétendre à des avantages spécifiques.

Lorsque vous créez des avantages, vous décidez quels avantages sont accessibles pour des employés donnés. Le tableau suivant indique les exemples des avantages que vous pouvez rendre disponibles à des employés spécifiques.

| Avantage          | Pour qui l’avantage est disponible |
|------------------|---------------------------------|
| Assurance médicale maladie | Tous les employés                   |
| Téléphone portable     | Vendeurs, cadres         |
| Cartes de parking   | Cadres                      |

Les composants suivants permettent de créer des stratégies d’éligibilité :

-   Types de règles de stratégie
-   Stratégies de droit aux avantages

Les types de règles de stratégie définissent les paramètres de requête utilisés lorsque vous développez des règles de stratégie spécifiques. Après avoir créé des types de règles de stratégie, vous pouvez créer des stratégies de droit aux avantages. Les stratégies permettent de créer une collection de règles qui s’appliquent à une ou plusieurs entités juridiques. Dans chaque stratégie, vous pouvez afficher les types de règles de stratégie de droit aux avantages que vous avez créés précédemment. 

Vous définissez la portée de la règle dans la stratégie. Par exemple, si vous créez un type de règle de stratégie de droit aux avantages nommé **Direction**, vous pouvez spécifier ce qu’est la règle de cette stratégie. Dans cet exemple, la règle peut stipuler que toute fonction qui contient le mot « directeur » doit être comprise dans la règle. Après avoir défini les paramètres des règles incluses dans la stratégie, vous pouvez affecter une règle spécifique à l’avantage.






[!INCLUDE[footer-include](../includes/footer-banner.md)]
