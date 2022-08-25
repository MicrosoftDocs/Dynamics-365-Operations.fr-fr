---
title: Test des données agnostiques à l’aide de Regression Suite Automation Tool
description: Cet article présente les recommandations pour le test agnostique en matière de données avec Regression Suite Automation Tool.
author: FrankDahl
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.custom: 21761
ms.openlocfilehash: f4322cb76d1d83c02ec9d4dcb997a1cd4730d090
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269589"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Test agnostique en matière de données à l’aide de Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Même si la validation technique d’une application d’ERP ne peut pas être totalement agnostique en matière de données, il existe plusieurs phases et approches de test. Ces phases de test incluent :  

- La structure SysTest
- La structure ATL
- Regression Suite Automation Tool (RSAT)

[![Pyramide de classification de test.](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Vue d’ensemble
-   **Structure SysTest** : la structure SysTest est fiable pour écrire les tests unitaires. Parce que les tests unitaires sont généralement l’occasion de tester une méthode ou une fonction, ils doivent toujours être agnostique en matière de données et dépendre uniquement des données de saisie fournies dans le cadre du test.
-   **Structure ATL** : Microsoft a une structure ATL qui correspond à une abstraction sur la structure SysTest et qui se charge du test technique en écrivant beaucoup plus simplement et de manière fiable. Cette structure doit être utilisée pour écrire des tests de composant ou des tests d’intégration simples.
-   **RSAT** : utilisé pour les tests d’intégration et les tests du cycle métier. Les tests du cycle métier, également appelés tests de validation de la régression, dépendent des données existantes. Cependant, ces tests peuvent devenir agnostiques en matière de données si vous tenez compte de facteurs supplémentaires. 

    - o Lorsque les tests unitaires et les tests de composant sont de bas niveau, et peuvent être entièrement agnostiques en matière de données (ne dépendent pas de l’ensemble de données existant), les tests de validation de la régression ou du cycle métier dépendent de certaines données existantes. Parmi ces données figurent le paramétrage, les paramètres de configuration et les données principales (client, fournisseurs, articles, etc.), mais jamais les données de transaction. Veillez à ce que pendant le test, si l’une d’entre elles est modifiée, elle est rétablie dans le cadre du test final.
    - Sélectionnez les données principales selon certains critères plutôt qu’en sélectionnant un enregistrement en particulier. Par exemple, si vous souhaitez sélectionner un élément selon ses valeurs dimensionnelles, et la disponibilité en stock, filtrez la liste de produits avec ces valeurs, sélectionnez le premier article et copiez le numéro à utiliser pour les tests à venir. S’il s’agit d’une ligne de données principales simple comme client, fournisseur ou article, elle peut être créée dans le cadre de l’automatisation et utilisée lors de tests à venir via l’enchaînement. 
    - o Saisissez les identifiants uniques, comme les numéros de facture, via la série de numéro ou à l’aide des fonctions Microsoft Excel comme =TEXT(NOW(),"yyyymmddhhmm"). Cette fonctionnalité fournira un numéro unique chaque minute, ce qui vous permet de suivre lorsque l’action s’est produite. Elle peut être utilisée pour les variables telles que les numéros de reçu de produit et les numéros de facture fournisseur. Ces tests continuent de fonctionner sur la même base de données, encore et encore, sans exiger de restauration.
    - Définissez toujours le **mode Modifier** de l’environnement sur **Lire** ou **Modifier** comme le premier cas de test, car l’option par défaut est **Auto**. Les options **Auto** utilisent toujours le paramètre précédent et peut générer des tests non fiables. 
 
    [![Page Options, onglet Performance.](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Validez uniquement après avoir filtré sur une transaction spécifique plutôt qu’une validation générique. Par exemple, pour le nombre d’enregistrements, filtrez le nombre de transactions ou la date de transaction de telle sorte que la validation exclut toutes les autres transactions. 
    - Si vous vérifiez un solde client ou un contrôle budgétaire, enregistrez la valeur tout d’abord, puis ajoutez la valeur de votre transaction pour valider le résultat attendu au lieu de valider une valeur attendue fixe. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
