---
title: "Définir et gérer un programme social"
description: "Les ressources humaines proposent un ensemble d'outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs. Cet article fournit des informations sur la manière de paramétrer et de gérer les avantages."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7344fad7c4dffabd99993924604e2e497bebc5ef
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="define-and-manage-a-benefits-program"></a>Définir et gérer un programme social

[!INCLUDE [banner](includes/banner.md)]

Les ressources humaines proposent un ensemble d'outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs. Cette rubrique fournit des informations sur la manière de paramétrer et de gérer les avantages.

<a name="benefit-setup"></a>Paramétrer les avantages
-------------

Avant que les collaborateurs puissent être inscrits à des avantages, vous devez créer les éléments de chaque avantage. Ces éléments combinent des plans d'avantages similaires et définissent les paramètres par défaut, tels que les taux de déduction et les détails comptables. Plusieurs de ces paramètres peuvent être ajustés lors de l'inscription ultérieure des collaborateurs à l'avantage. Pour chaque plan d'avantages, une organisation peut proposer plusieurs options d'inscription. Un collaborateur peut également renoncer à son inscription au plan. 

[![Avantage du flux de processus](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Détails des avantages
Avant de commencer à créer des avantages et à y inscrire des collaborateurs, vous devez définir les éléments qui constituent un avantage : le type, le régime et les options.

-   **Type** – Ensemble de régimes pour un avantage spécifique, par exemple une prise en charge médicale ou une place de stationnement.
-   **Régime** – Un avantage spécifique contracté auprès d'un fournisseur.
-   **Option** – Le niveau de couverture, comme par exemple « l'employé uniquement » ou « l'employé et le (la) conjoint(e)/partenaire ».

Pour chaque type d'avantage, tel que les soins ophtalmologiques ou dentaires, une organisation peut offrir un ou plusieurs régimes à ses collaborateurs. Pour chaque régime, l'organisation peut proposer différentes options. Par exemple, les collaborateurs peuvent acheter une couverture d'assurance vie supplémentaire équivalent à une, deux ou trois fois leur salaire annuel. Chaque combinaison d'un régime et d'options forme un avantage auquel les collaborateurs peuvent s'inscrire. 

[![illustration d'avantage](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Admissibilité
Plusieurs facteurs déterminent le droit des collaborateurs aux différents types d'avantages qu'un employeur offre. Lorsque vous créez un avantage dans Microsoft Talent, vous pouvez définir le type de droit qui s'applique à cet avantage. 

Vous pouvez rendre un avantage accessible à tous les collaborateurs. Par exemple, certaines entreprises offrent des cartes de parking à tous les employés comme avantage en nature. Lorsque vous créez cet avantage, vous définissez le droit sur **Tous les collaborateurs sont éligibles**. 

Pour d'autres avantages, tels que les saisies-arrêts et les prélèvements de taxe, l'éligibilité ne s'applique pas. Lorsque vous créez ces types d'avantages, vous définissez le droit sur **Ignorer le processus d'éligibilité**. 

Enfin, le droit à l'avantage peut être basé sur une règle. Par exemple, une entreprise offre deux types d'avantage Assurance-vie à ses employés. Les cadres ont droit à un régime d'assurance-vie tandis que les autres employés à temps plein ont droit à un autre régime d'assurance-vie. Dans Talent, vous pouvez créer une règle de droit à un avantage pour trouver tous les cadres et une autre règle pour trouver tous les autres employés à temps plein, puis appliquer ces règles à l'avantage concerné

## <a name="enrollment"></a>Inscription
Après avoir créé les avantages que votre organisation propose et déterminé l'éligibilité, vous pouvez inscrire vos collaborateurs aux avantages. Vous pouvez inscrire un seul collaborateur à des avantages. Vous pouvez également inscrire plusieurs collaborateurs à un ou plusieurs avantages dans le cadre d'un seul et même processus. 

Parfois, une organisation cesse d'offrir certains avantages. Dans ce cas, vous devez mettre à jour l'avantage et les collaborateurs qui y sont inscrits. L'expiration de l'avantage collectif vous permet de modifier la date d'échéance d'un avantage et l'inscription des collaborateurs à cet avantage. Vous pouvez également sélectionner plusieurs collaborateurs inscrits à un avantage et modifier la date de fin de leur couverture. 

De même, l'extension de l'avantage collectif vous permet de prolonger la date d'expiration d'un avantage ainsi que l'inscription des collaborateurs à cet avantage si vous décidez d'offrir un avantage plus longtemps que prévu.

<a name="see-also"></a>Voir également :
--------

[Stratégies de droit aux avantages](benefit-eligibility-policies.md)




