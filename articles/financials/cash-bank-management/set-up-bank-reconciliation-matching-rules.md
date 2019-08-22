---
title: Configurer les règles de correspondance de rapprochement bancaire
description: Cette rubrique explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement.
author: ShylaThompson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ced5d7b00fd512d0af0fb88f9d30042213b6908
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842231"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurer les règles de correspondance de rapprochement bancaire

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour faciliter le processus de rapprochement bancaire. Les règles de correspondance de rapprochement sont un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire lors du processus de rapprochement.

Vous pouvez paramétrer des règles de correspondance de rapprochement et des ensembles de règles de correspondance de rapprochement pour aider le processus de rapprochement bancaire. Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire Microsoft Dynamics 365 for Finance and Operations lors du processus de rapprochement. La page **Règles de correspondance de rapprochement** permet de paramétrer les règles de correspondance de rapprochement. Vous pouvez paramétrer plusieurs règles de correspondance, puis créer un ensemble de règles de correspondance de rapprochement dans la page **Ensembles de règles de correspondance de rapprochement**. 

> [!NOTE] 
> Les règles de correspondance de rapprochement bancaire sont utilisées si vous rapprochez un relevé bancaire électronique en utilisant le rapprochement bancaire avancé. 

Sur la page **Règles de correspondance de rapprochement**, vous pouvez sélectionner les actions et critères de sélection qui sont utilisés lorsque la règle de rapprochement est exécutée. Dans le groupe de champs **Actions**, sélectionnez l'action qui est effectuée lorsque la règle de rapprochement est exécutée lors du processus de rapprochement.  

> [!NOTE] 
> L'option sélectionnée détermine les champs qui s'affichent.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action**                         |                                                                                                                                                                                                                                                                                                               | **Critères de sélection disponibles lorsque l'action est activée**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Faire correspondre au document bancaire**       | Permet de créer des critères afin de spécifier comment les documents bancaires et les lignes de relevé bancaire sont mis en correspondance lorsque la règle de rapprochement est exécutée à partir de la page **Feuille de calcul de rapprochement bancaire**. Les lignes de transaction sont sélectionnées en fonction des critères supplémentaires paramétrés dans les organisateurs.                                | **Étape 1 : définir la règle de correspondance** : sélectionnez des critères pour spécifier les relevés bancaires qui doivent être mis en correspondance avec les transactions bancaires Finance and Operations. **Étape 2 (facultatif) : sélectionner les lignes de relevés pour exécuter les règles de correspondance sur cette base :** Appliquer un filtre sur les lignes de relevé pour exécuter les règles.                                                                                                                                                                                                                                                                                                               |
| **Effacer les lignes de relevés de contrepassation** | Permet de créer des critères pour spécifier comment les lignes de relevé de contrepassation doivent être supprimées de la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée. Cette option est utilisée lorsqu'une erreur bancaire survient et que deux lignes de relevé bancaire sont répertoriées dans le relevé bancaire importé et que ces lignes doivent être rapprochées. | **Étape 1** :**rechercher les lignes de relevés de contrepassation** Permet d'ajouter des critères de sélection pour sélectionner des lignes de relevé bancaire de contrepassation. Par exemple, pour sélectionner uniquement des chèques, sélectionnez **Code de transaction en banque** dans le champ Champ, sélectionnez le signe plus (+) dans le champ **Opérateur**, puis entrez **Chèques** dans le champ de valeur. **Étape 2 : rechercher les lignes de relevés d'origine** : Vous pouvez ajouter des critères de sélection pour faire correspondre les lignes de document bancaire aux lignes de relevé bancaire. **Étape 3 : rechercher les transactions bancaires Finance and Operations** : vous pouvez ajouter des critères de sélection pour faire correspondre les transactions Finance and Operations aux lignes de relevé bancaire. |
| **Marquer les nouvelles transactions**          | Permet de créer des critères pour spécifier comment les nouvelles transactions doivent être marquées sur la page **Feuille de calcul de rapprochement bancaire** lorsque la règle de rapprochement est exécutée.                                                                                                                                                                 | **Étape 1 : rechercher les lignes de relevé** : permet d'ajouter des champs de sélection pour spécifier les lignes de relevé bancaire qui doivent être sélectionnées dans la page **Feuille de calcul de rapprochement bancaire**. **Étape 2 : rechercher Finance and Operations** : vous pouvez ajouter des critères de sélection pour rechercher des lignes de document bancaire. Si aucun document bancaire n'est trouvé, une ligne de relevé est marquée comme nouvelle transaction.                                                                                                                                                                                                                                             |








