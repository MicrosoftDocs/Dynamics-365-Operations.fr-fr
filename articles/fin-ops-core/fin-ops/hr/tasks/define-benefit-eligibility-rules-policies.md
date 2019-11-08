---
title: Définir les règles d'admissibilité et les stratégies relatives aux avantages
description: Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d35266c95cfbf3473a14fec47a1c748229dd25
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190555"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Définir les règles d'admissibilité et les stratégies relatives aux avantages

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cet enregistrement vous indique comment créer des règles et des stratégies de droit aux avantages, puis comment affecter les règles aux avantages.  

Les données fictives utilisées pour créer cet enregistrement correspondent à la société USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Créer un type de règles de stratégie de droit aux avantages
1. Allez dans Ressources humaines > Avantages > Admissibilité > Types de règles de stratégie de droit aux avantages.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom de la règle.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Nom de la requête, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur Enregistrer.
8. Fermez la page.

## <a name="benefit-eligibility-policy"></a>Stratégie de droit aux avantages
1. Allez dans Ressources humaines > Avantages > Admissibilité > Stratégies de droit aux avantages.
2. Sélectionnez une stratégie de droit existante.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Activez ou désactivez l'extension des sections Organisations de stratégie.  Vous pouvez alors ajouter ou supprimer toutes les organisations à inclure dans la stratégie.
5. Développez ou réduisez la section Règles de stratégie.
6. Dans la liste, recherchez la règle de stratégie créée précédemment.
7. Cliquez sur Créer une règle de stratégie.
8. Dans le champ Date d'effet, entrez la date à laquelle vous souhaitez que la stratégie prenne effet.
    * La définition des dates d'effet et de fin vous permet d'apporter de futures modifications aux règles de stratégie et de supprimer la nécessité de rétablir la stratégie lorsque vous souhaitez que ces modifications prennent effet.  
9. 
    * Par exemple si vous souhaitez que la règle s'applique uniquement aux directeurs des ventes, vous pouvez créer la clause Where comme ceci : Où la description du poste est égale au responsable des ventes.  Vous pouvez avoir des instructions Where multiples dans la règle.  
10. Cliquez sur OK.
11. Fermez la page.
12. Fermez la page.

## <a name="assign-rule-to-benefit"></a>Affecter une règle à un avantage
1. Accédez à Ressources humaines > Avantages > Avantages.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Développez ou réduisez la section Règles d'admissibilité.
5. Cliquez sur Modifier.
6. Dans le champ Admissibilité, sélectionnez Selon les règles dans la liste.
7. Dans le champ Type de règle, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez la règle créée précédemment.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Cliquez sur Enregistrer.
11. Permet de fermer l'écran.
