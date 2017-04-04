---
title: "Paramétrage des règles de correspondance du rapprochement bancaire"
description: "Cet article explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: e4c07a6afb90535c57f372d5b850919b5b34aaa4
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Paramétrage des règles de correspondance du rapprochement bancaire

Cet article explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement.

Vous pouvez paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour aider le processus de rapprochement bancaire. Un rapprochement Règle correspondante est un ensemble de critères utilisés pour filtrer les lignes du relevé bancaire et Microsoft Dynamics 365 pour les lignes de transaction bancaire d'opérations durant le processus de rapprochement. La page **Règles de correspondance de rapprochement** permet de paramétrer les règles de correspondance de rapprochement. Vous pouvez paramétrer plusieurs règles de correspondance, puis créer un ensemble de règles de correspondance de rapprochement dans la page **Ensembles de règles de correspondance de rapprochement**. 

> [!NOTE] 
> Le rapprochement bancaire correspondant des règles sont utilisés si vous rapprochez un relevé bancaire électronique à l'aide de le rapprochement bancaire acompte. 

Sur la page **Règles de correspondance de rapprochement**, vous pouvez sélectionner les actions et critères de sélection qui sont utilisés lorsque la règle de rapprochement est exécutée. ** Les actions ** du groupe de champs, sélectionnez l'action qui sera exécutée que lorsque la règle correspondante est exécutée lors de le processus de rapprochement.  

> [!NOTE] 
> L'option sélectionnée détermine les champs affichés.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                         |                                                                                                                                                                                                                                                                                                               | **Critères de sélection disponibles lorsque l'action est activée**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Faire correspondre au document bancaire **       | Permet de créer des critères afin de spécifier comment les documents bancaires et les lignes de relevé bancaire sont mis en correspondance lorsque la règle de rapprochement est exécutée à partir de la page **Feuille de calcul de rapprochement bancaire**. Les lignes de transaction sont sélectionnées en fonction des critères supplémentaires paramétrés dans les organisateurs.                                | ** Étape 1 : Définissez la règle correspondante ** – Sélectionner des criterias pour spécifier les relevés bancaires doivent être mis en correspondance avec Dynamics 365 pour les transactions bancaires d'opérations. **Étape 2 (facultatif) : sélectionner les lignes de relevés pour exécuter les règles de correspondance sur cette base : **Appliquer un filtre sur les lignes de relevé pour exécuter les règles.                                                                                                                                                                                                                                                                                                               |
| **Effacer les lignes de relevés de contrepassation ** | Permet de créer des critères pour spécifier comment les lignes de relevé de contrepassation doivent être supprimées de la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée. Cette option est utilisée lorsqu'une erreur bancaire survient et que deux lignes de relevé bancaire sont répertoriées dans le relevé bancaire importé et que ces lignes doivent être rapprochées. | **Étape 1** :** rechercher les lignes de relevés de contrepassation **Permet d'ajouter des critères de sélection pour sélectionner des lignes de relevé bancaire de contrepassation. Par exemple, pour sélectionner uniquement des chèques, sélectionnez **Code de transaction en banque** dans le champ Champ, sélectionnez le signe plus (+) dans le champ **Opérateur**, puis entrez **Chèques** dans le champ de valeur. **Étape 2 : rechercher les lignes de relevés d'origine** : Vous pouvez ajouter des critères de sélection pour faire correspondre les lignes de document bancaire aux lignes de relevé bancaire. ** Étape 3 : La Rechercher Dynamics 365 pour les transactions bancaires d'opérations ** – Vous pouvez ajouter des critères de sélection pour correspondre Dynamics 365 pour les transactions bancaires d'opérations aux lignes de relevé bancaire. |
| **Mark new transactions**          | Permet de créer des critères pour spécifier comment les nouvelles transactions doivent être marquées sur la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée.                                                                                                                                                                 | **Étape 1 : rechercher les lignes de relevé** : permet d'ajouter des champs de sélection pour spécifier les lignes de relevé bancaire qui doivent être sélectionnées dans la page **Feuille de calcul de rapprochement bancaire**. ** Étape 2 : La Rechercher Dynamics 365 pour les transactions bancaires d'opérations ** – Vous pouvez ajouter des critères de sélection des lignes de document bancaire de recherche. Si aucun document bancaire n'est trouvé, une ligne de relevé est marquée comme nouvelle transaction.                                                                                                                                                                                                                                             |

 





