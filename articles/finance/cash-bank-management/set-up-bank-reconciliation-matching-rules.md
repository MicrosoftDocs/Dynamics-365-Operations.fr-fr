---
title: Configurer les règles de correspondance de rapprochement bancaire
description: Cet article explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement.
author: angelad116
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: kfend
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed8572eca14beb8a0e3c382f0f328cc6d118491c
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151309"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurer les règles de correspondance de rapprochement bancaire

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement.

Vous pouvez paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour aider le processus de rapprochement bancaire. Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire Dynamics 365 Finance lors du processus de rapprochement. La page **Règles de correspondance de rapprochement** permet de paramétrer les règles de correspondance de rapprochement. Vous pouvez paramétrer plusieurs règles de correspondance, puis créer un ensemble de règles de correspondance de rapprochement dans la page **Ensembles de règles de correspondance de rapprochement**. 

> [!NOTE] 
> Les règles de correspondance de rapprochement bancaire sont utilisées si vous rapprochez un relevé bancaire électronique en utilisant le rapprochement bancaire avancé. 

Sur la page **Règles de correspondance de rapprochement**, vous pouvez sélectionner les actions et critères de sélection qui sont utilisés lorsque la règle de rapprochement est exécutée. Dans le groupe de champs **Actions**, sélectionnez l’action qui est effectuée lorsque la règle de rapprochement est exécutée lors du processus de rapprochement.  

Par défaut, les règles de mise en correspondance correspondent au premier document bancaire qui répond aux critères de la règle de correspondance. Si plusieurs documents bancaires répondent aux critères de la règle, le paramètre exigeant une mise en correspondance manuelle peut être activé en accédant à **Gestion de la trésorerie et de la banque > Configuration > Paramètres de gestion de la trésorerie et des banques > Rapprochement bancaire > Exiger un rapprochement manuel lorsque les règles de rapprochement avancées du rapprochement bancaire trouvent plusieurs documents correspondant au montant**.

> [!NOTE] 
> L’option sélectionnée détermine les champs qui s’affichent.

| Action | Description   | Critères de sélection disponibles lorsque l’action est activée     |
|--------|---------------|----------------------------------------------------------|
| **Faire correspondre au document bancaire**       | Permet de créer des critères afin de spécifier comment les documents bancaires et les lignes de relevé bancaire sont mis en correspondance lorsque la règle de rapprochement est exécutée à partir de la page **Feuille de calcul de rapprochement bancaire**. Les lignes de transaction sont sélectionnées en fonction des critères supplémentaires paramétrés dans les organisateurs.                                | **Étape 1 : définir la règle de correspondance** : sélectionnez des critères pour spécifier les relevés bancaires qui doivent être mis en correspondance avec les transactions bancaires Finance. **Étape 2 (facultatif) : sélectionner les lignes de relevés pour exécuter les règles de correspondance sur cette base :** Appliquer un filtre sur les lignes de relevé pour exécuter les règles.                                                                                                                                                                                                                                                                                                               |
| **Effacer les lignes de relevés de contrepassation** | Permet de créer des critères pour spécifier comment les lignes de relevé de contrepassation doivent être supprimées de la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée. Cette option est utilisée lorsqu’une erreur bancaire survient et que deux lignes de relevé bancaire sont répertoriées dans le relevé bancaire importé et que ces lignes doivent être rapprochées. | **Étape 1** :**rechercher les lignes de relevés de contrepassation** Permet d’ajouter des critères de sélection pour sélectionner des lignes de relevé bancaire de contrepassation. Par exemple, pour sélectionner uniquement des chèques, sélectionnez **Code de transaction en banque** dans le champ Champ, sélectionnez le signe plus (+) dans le champ **Opérateur**, puis entrez **Chèques** dans le champ de valeur. **Étape 2 : rechercher les lignes de relevés d’origine** : Vous pouvez ajouter des critères de sélection pour faire correspondre les lignes de document bancaire aux lignes de relevé bancaire. **Étape 3 : rechercher les transactions bancaires Finance** : Vous pouvez ajouter des critères de sélection pour faire correspondre les transactions Finance aux lignes de relevé bancaire. |
| **Marquer les nouvelles transactions**          | Permet de créer des critères pour spécifier comment les nouvelles transactions doivent être marquées sur la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée.                                                                                                                                                                 | **Étape 1 : rechercher les lignes de relevé** : permet d’ajouter des champs de sélection pour spécifier les lignes de relevé bancaire qui doivent être sélectionnées dans la page **Feuille de calcul de rapprochement bancaire**. **Étape 2 : rechercher des applications de finances et d’opérations** : vous pouvez ajouter des critères de sélection pour rechercher des lignes de document bancaire. Si aucun document bancaire n’est trouvé, une ligne de relevé est marquée comme nouvelle transaction.                                                                                                                                                                                                                                             |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

