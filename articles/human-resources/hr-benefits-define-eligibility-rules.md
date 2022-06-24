---
title: Définir les règles d’admissibilité et les stratégies relatives aux avantages
description: Cette rubrique explique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 4781a00ae63bb2d27df0610a1886cc43e52798f9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861187"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Définir les règles d’admissibilité et les stratégies relatives aux avantages


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article explique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Créer un type de règles de stratégie de droit aux avantages

1. Allez dans **Ressources humaines > Avantages > Admissibilité > Types de règles de stratégie de droit aux avantages**.
2. Sélectionnez **Nouveau**.
3. Entrez une valeur dans le champ **Nom de la règle**.
4. Dans le champ **Description**, entrez une valeur.
5. Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ **Nom de la requête**.
6. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
7. Sélectionnez **Enregistrer**.
8. Fermez la page.

## <a name="benefit-eligibility-policy"></a>Stratégie de droit aux avantages

1. Allez dans **Ressources humaines > Avantages > Admissibilité > Stratégies de droit aux avantages**.
2. Sélectionnez une stratégie de droit existante.
3. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
4. Activez ou désactivez l’extension des sections **Organisations de stratégie**. Vous pouvez ajouter ou supprimer toutes les organisations à inclure dans la stratégie.
5. Développez ou réduisez la section **Règles de stratégie**.
6. Dans la liste, recherchez la règle de stratégie créée précédemment.
7. Sélectionnez **Créer une règle de stratégie**.
8. Dans le champ **Date d’effet**, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.
    * La définition des dates d’effet et de fin vous permet d’apporter de futures modifications aux règles de stratégie, ainsi vous n’avez pas à rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.  
9. Si nécessaire, ajoutez une clause where au champ **Ajouter une condition**.
    * Par exemple si vous souhaitez que la règle s’applique uniquement aux directeurs des ventes, vous pouvez créer la clause where comme ceci : Où la description du poste est égale au responsable des ventes. Vous pouvez ajouter plusieurs instructions where dans la règle.  
10. Cliquez sur **OK**.
11. Fermez la page.

## <a name="assign-rule-to-benefit"></a>Affecter une règle à un avantage

1. Accédez à **Ressources humaines > Avantages > Avantages**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
4. Développez ou réduisez la section **Règles d’admissibilité**.
5. Sélectionnez **Modifier**.
6. Sélectionnez la règle dans le champ **Admissibilité**.
7. Sélectionnez la règle créée précédemment dans le champ **Type de règle**.
9. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
10. Sélectionnez **Enregistrer**.
11. Permet de fermer l’écran.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
