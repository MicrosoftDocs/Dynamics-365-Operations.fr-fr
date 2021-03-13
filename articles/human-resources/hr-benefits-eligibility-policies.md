---
title: Stratégies de droit aux avantages
description: Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cc5dfedc0022cbf9bdbc636bbe96971422c29838
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112487"
---
# <a name="benefit-eligibility-policies"></a>Stratégies de droit aux avantages

Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.

Lorsque vous créez des avantages, vous décidez quels avantages sont accessibles pour des employés donnés. Le tableau suivant indique les exemples des avantages que vous pouvez rendre disponibles à des employés spécifiques.

| Avantage          | Pour qui l'avantage est disponible |
|------------------|---------------------------------|
| Assurance médicale maladie | Tous les employés                   |
| Téléphone portable     | Vendeurs, cadres         |
| Cartes de parking   | Cadres                      |

Les composants suivants permettent de créer des stratégies d'éligibilité :

-   Types de règles de stratégie
-   Stratégies de droit aux avantages

Les types de règles de stratégie définissent les paramètres de requête utilisés lorsque vous développez des règles de stratégie spécifiques. Après avoir créé des types de règles de stratégie, vous pouvez créer des stratégies de droit aux avantages. Les stratégies permettent de créer une collection de règles qui s'appliquent à une ou plusieurs entités juridiques. Dans chaque stratégie, vous pouvez afficher les types de règles de stratégie de droit aux avantages que vous avez créés précédemment. 

Vous définissez la portée de la règle dans la stratégie. Par exemple, si vous créez un type de règle de stratégie de droit aux avantages nommé **Direction**, vous pouvez spécifier ce qu'est la règle de cette stratégie. Dans cet exemple, la règle peut stipuler que toute fonction qui contient le mot « directeur » doit être comprise dans la règle. Après avoir défini les paramètres des règles incluses dans la stratégie, vous pouvez affecter une règle spécifique à l'avantage.




