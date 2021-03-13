---
title: Définir les règles d'admissibilité et les stratégies relatives aux avantages
description: Cet article montre comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: cc80549eaffa72a22dec51829c86d04a763de96a
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112489"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Définir les règles d’admissibilité et les stratégies relatives aux avantages

Cette rubrique montre comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.  

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
4. Activez ou désactivez l'extension des sections **Organisations de stratégie**. Vous pouvez ajouter ou supprimer toutes les organisations à inclure dans la stratégie.
5. Développez ou réduisez la section **Règles de stratégie**.
6. Dans la liste, recherchez la règle de stratégie créée précédemment.
7. Sélectionnez **Créer une règle de stratégie**.
8. Dans le champ **Date d'effet**, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.
    * La définition des dates d'effet et de fin vous permet d'apporter de futures modifications aux règles de stratégie, ainsi vous n'avez pas à rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.  
9. Si nécessaire, ajoutez une clause where au champ **Ajouter une condition**.
    * Par exemple si vous souhaitez que la règle s'applique uniquement aux directeurs des ventes, vous pouvez créer la clause where comme ceci : Où la description du poste est égale au responsable des ventes. Vous pouvez ajouter plusieurs instructions where dans la règle.  
10. Cliquez sur **OK**.
11. Fermez la page.

## <a name="assign-rule-to-benefit"></a>Affecter une règle à un avantage

1. Accédez à **Ressources humaines > Avantages > Avantages**.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
4. Développez ou réduisez la section **Règles d'admissibilité**.
5. Sélectionnez **Modifier**.
6. Sélectionnez la règle dans le champ **Admissibilité**.
7. Sélectionnez la règle créée précédemment dans le champ **Type de règle**.
9. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
10. Sélectionnez **Enregistrer**.
11. Permet de fermer l’écran.

