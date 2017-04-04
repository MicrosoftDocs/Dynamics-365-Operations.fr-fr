---
title: "Définissez et gérez un programme social"
description: "Les ressources humaines proposent un ensemble d&quot;outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu&quot;une organisation offre ou gère pour ses collaborateurs. Cet article fournit des informations sur la manière de paramétrer et de gérer les avantages."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Définissez et gérez un programme social

Les ressources humaines proposent un ensemble d'outils pouvant servir à paramétrer et à mettre à jour les avantages, les déductions et les plans de compensation des collaborateurs qu'une organisation offre ou gère pour ses collaborateurs. Cette rubrique fournit des informations sur le paramétrage des avantages d'un traitement.

<a name="benefit-setup"></a>Paramétrage d'avantage
-------------

Avant que les collaborateurs puissent être inscrits à des avantages, vous devez créer les éléments de chaque avantage. Ces éléments combinent des plans d'avantages similaires et définissent les paramètres par défaut, tels que les taux de déduction et les détails comptables. Plusieurs de ces paramètres peuvent être ajustés lors de l'inscription ultérieure des collaborateurs à l'avantage. Pour chaque plan d'avantages, une organisation peut proposer plusieurs options d'inscription. Un collaborateur peut également renoncer à son inscription au plan. 

[processus d'avantage d'![] (. /media/benefit-process-flow1.png)](. /media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Détails des avantages
Avant de commencer à créer des avantages et à y inscrire des collaborateurs, vous devez définir les éléments qui constituent un avantage : le type, le régime et les options.

-   **Type** – Ensemble de régimes pour un avantage spécifique, par exemple une prise en charge médicale ou une place de stationnement.
-   **Régime** – Un avantage spécifique contracté auprès d'un fournisseur.
-   **Option** – Le niveau de couverture, comme par exemple « l'employé uniquement » ou « l'employé et le (la) conjoint(e)/partenaire ».

Pour chaque type d'avantage, tel que les soins ophtalmologiques ou dentaires, une organisation peut offrir un ou plusieurs régimes à ses collaborateurs. Pour chaque régime, l'organisation peut proposer différentes options. Par exemple, les collaborateurs peuvent acheter une couverture d'assurance vie supplémentaire équivalent à une, deux ou trois fois leur salaire annuel. Chaque combinaison d'un régime et d'options forme un avantage auquel les collaborateurs peuvent s'inscrire. 

[PIC d'avantage d'![] (. /media/benefit-pic.png)](. /media/benefit-pic.png)

## <a name="eligibility"></a>Admissibilité
Plusieurs facteurs déterminent le droit des collaborateurs aux différents types d'avantages qu'un employeur offre. Lorsque vous créez un avantage dans Microsoft Dynamics 365 pour les opérations, vous pouvez définir le type d'admissibilité s'appliquant à cet avantage. 

Vous pouvez rendre un avantage disponible pour tous les travailleurs. Par exemple, stationnement de devis de certaines sociétés passe à tous les employés comme avantages en nature. Lorsque vous créez cet avantage, vous définissez le droit sur **Tous les collaborateurs sont éligibles**. 

Pour d'autres avantages, tels que des saisies-arrêt et des ensembles de taxe, l'octroi d'un emploi ne s'applique pas. Petit lait vous créez ces types d'avantages, vous définissez l'admissibilité ** sautez le processus d'admissibilité **. 

Enfin, le droit aux avantages peut être basé sur les règles. Par exemple, une société offre deux types d'avantage d'assurance-vie aux employés. Les employés exécutifs sont habilités à un plan d'assurance-vie temporaire, alors que tous les autres employés à temps plein sont habilités à l'autre plan d'assurance-vie temporaire. Dans Dynamics 365 pour les opérations, vous pouvez créer une règle de droit aux avantages de rechercher tous les employés exécutifs et une règle différente de rechercher tous autres employés à temps plein, puis vous appliquez les règles à l'avantage approprié.

## <a name="enrollment"></a>Inscription
Après avoir créé les avantages que votre organisation propose et déterminé l'éligibilité, vous pouvez inscrire vos collaborateurs aux avantages. Vous pouvez inscrire un seul collaborateur à des avantages. Vous pouvez également inscrire plusieurs collaborateurs à un ou plusieurs avantages dans le cadre d'un seul et même processus. 

Parfois, une organisation cesse d'offrir certains avantages. Dans ce cas, vous devez mettre l'avantage et les travailleurs à jour inscrits dans. L'expiration en masse d'avantage permet de modifier la date d'expiration d'un avantage et des inscriptions de travailleur pour cet avantage simultanément. Vous pouvez également sélectionner plusieurs collaborateurs inscrits à un avantage et modifier la date de fin de leur couverture. 

De même, l'extension de l'avantage collectif vous permet de prolonger la date d'expiration d'un avantage ainsi que l'inscription des collaborateurs à cet avantage si vous décidez d'offrir un avantage plus longtemps que prévu.

<a name="see-also"></a>Voir également :
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


