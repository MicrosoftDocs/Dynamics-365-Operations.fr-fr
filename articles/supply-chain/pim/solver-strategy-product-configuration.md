---
title: Stratégie du solveur pour la configuration du produit
description: Cette rubrique décrit comment utiliser la stratégie du solveur pour améliorer les performances de configuration du produit.
author: cvocph
manager: tfehr
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f79211f9a557813f0030a11002dc0ed2015ce258
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983246"
---
# <a name="solver-strategy-for-product-configuration"></a>Stratégie du solveur pour la configuration du produit

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser la stratégie du solveur pour améliorer les performances de configuration du produit.

Le concept de stratégies du solveur a été introduit pour la première fois dans la mise à jour cumulative 7 (CU7) de Microsoft Dynamics AX 2012 R2. Il a été étendu dans la mise à jour cumulative 8 (CU8) pour Microsoft Dynamics AX R3 2012 et Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3.

Le concept de stratégie du solveur comprend désormais les stratégies suivantes :

- Par défaut
- Nombre minimal de domaines en premier
- Haut-bas
- Z3

## <a name="solver-strategy"></a>Stratégie du solveur 

Un modèle de configuration de produit peut être formulé en tant que [problème de satisfaction de contraintes (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf) Microsoft Solver Foundation (MSF) propose deux types de stratégies du solveur pour résoudre les CSP qui peuvent être utilisés dans les modèles de configuration de produit. Ces stratégies du solveur se basent sur l'[heuristique](https://techterms.com/definition/heuristic), qui permet de déterminer l'ordre dans lequel les variables des CSP sont prises en compte lors de la résolution du problème. L'heuristique peut affecter considérablement les performances lors de la résolution d'un problème ou d'une classe de problème.

La stratégie du solveur pour les modèles de configuration de produit détermine le solveur utilisé avec l'heuristique. Les stratégies **Par défaut**, **Nombre minimal de domaines en premier** et **Haut-bas** utilisent les deux solveurs de MSF, alors que la stratégie **Z3** utilise le solveur Z3. 

Des études d'implémentation client réelles ont montré qu'une modification de la stratégie du solveur pour un modèle de configuration de produit peut réduire le temps de réponse de minutes en millisecondes. Par conséquent, il est utile d'essayer différentes stratégies du solveur pour trouver la plus efficace pour votre modèle de configuration de produit.

## <a name="change-the-settings-for-the-solver-strategy"></a>Modifier les paramètres de la stratégie du solveur

Pour modifier la stratégie du solveur, dans la page **Modèles de configuration de produit**, dans le volet Actions, sélectionnez **Propriétés du modèle**. Puis, dans la boîte de dialogue **Modifier les détails du modèle**, sélectionnez une stratégie du solveur.

[![Modification de la stratégie du solveur](./media/solver-strategy.png)](./media/solver-strategy.png)

Actuellement, il n'existe aucune logique qui détecte automatiquement la stratégie du solveur la plus efficace pour la configuration du produit basée sur les contraintes. Par conséquent, vous devez tester les stratégies du solveur une par une.

Le tableau suivant fournit des recommandations sur la stratégie du solveur à utiliser dans différents scénarios.

| Stratégie du solveur      | Utiliser la stratégie dans ce scénario |
|----------------------|-----------------------------------|
| Par défaut              | La stratégie **Par défaut** a été optimisée pour résoudre les modèles basés sur des contraintes de table. Des études d'implémentation client ont montré que cette stratégie est la plus efficace dans les scénarios où les contraintes de table sont utilisées de manière intensive. |
| Nombre minimal de domaines en premier | Les stratégies **Nombre minimal de domaines en premier** et **Haut-Bas** sont étroitement liées. Des études d'implémentation client ont montré que la stratégie **Haut-bas** est plus performante que la stratégie **Nombre minimal de domaines en premier**. Toutefois, la stratégie **Nombre minimal de domaines en premier** est conservée dans le produit pour la compatibilité ascendante. Ces deux stratégies du solveur se sont avérées plus efficaces pour résoudre les modèles contenant plusieurs expressions arithmétiques où aucune contrainte de table n'est utilisée. Toutefois, dans certains cas, la stratégie **Par défaut** est plus performante que ces deux stratégies. Il est donc recommandé d'essayer chaque stratégie. |
| Haut-bas             | Les stratégies **Nombre minimal de domaines en premier** et **Haut-Bas** sont étroitement liées. Des études d'implémentation client ont montré que la stratégie **Haut-bas** est plus performante que la stratégie **Nombre minimal de domaines en premier**. Toutefois, la stratégie **Nombre minimal de domaines en premier** est conservée dans le produit pour la compatibilité ascendante. Ces deux stratégies du solveur se sont avérées plus efficaces pour résoudre les modèles contenant plusieurs expressions arithmétiques où aucune contrainte de table n'est utilisée. Toutefois, dans certains cas, la stratégie **Par défaut** est plus performante que ces deux stratégies. Il est donc recommandé d'essayer chaque stratégie. |
| Z3                   | Nous vous recommandons d'utiliser la stratégie **Z3** comme stratégie du solveur par défaut. Si vous êtes préoccupé par les performances et l'évolutivité, vous pouvez évaluer les autres stratégies. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la configuration du produit](build-product-configuration-model.md)

[Heuristique](https://techterms.com/definition/heuristic)

[Problème de satisfaction de contraintes](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]