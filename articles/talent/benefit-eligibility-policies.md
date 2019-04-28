---
title: Stratégies de droit aux avantages
description: Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ad179e505d045dc40898105e1cfd090daafa09a8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "855960"
---
# <a name="benefit-eligibility-policies"></a>Stratégies de droit aux avantages

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.

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

Vous définissez la portée de la règle dans la stratégie. Par exemple, si vous créez un type de règle de stratégie de droit aux avantages nommé **Direction**, vous pouvez spécifier ce qu'est la règle de cette stratégie. Dans cet exemple, la règle peut stipuler que toute fonction qui contient le mot « directeur » doit être comprise dans la règle. Après avoir défini les paramètres des règles incluses dans la stratégie, vous pouvez affecter une règle spécifique à l'avantage.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Définition et gestion d'un programme social](manage-benefit-program.md)



