---
title: Exclure les produits avec des états du cycle de vie des produits spécifiques
description: Cette rubrique explique comment exclure des produits en fonction de leur état de cycle de vie lorsque la fonctionnalité d’optimisation de planification est utilisée.
author: t-benebo
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: cdc1d47a4d12515e82e5feb55c5d473476e36873
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469196"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Exclure les produits avec des états du cycle de vie des produits spécifiques

[!include [banner](../../includes/banner.md)]

Les produits lancés et les versions de produits lancés incluent un champ **État du cycle de vie du produit**. Ce champ vous permet de contrôler, entre autres, quels produits sont inclus lors de la planification. Vous pouvez ajouter, supprimer et modifier les états du cycle de vie selon vos besoins en accédant à **Gestion des informations produit \> Configurer \> État du cycle de vie du produit**. Pour chaque état du cycle de vie du produit, définissez l’option **Actif pour la planification** sur *Oui* si les produits qui ont cet état doivent être inclus lors de la planification. Lorsque l’option est définie sur *Non*, les produits et variantes associés seront exclus de toute planification et de tous les calculs au niveau de la nomenclature (BOM).

Produits lancés et variantes où le champ **État du cycle de vie du produit** est laissé vide sont traités comme s’ils avaient un état du cycle de vie du produit où l’option **Actif pour la planification** est définie sur *Oui*. En d’autres termes, ils seront inclus lors de la planification.

> [!NOTE]
> Pour éviter les suggestions d’approvisionnement inutiles, nous vous recommandons vivement d’associer tous les produits et variantes obsolètes à un état du cycle de vie du produit où l’option **Actif pour la planification** est définie sur *Non*. Cette approche est particulièrement importante lorsque vous travaillez avec des variantes de configuration de produit qui ne sont pas réutilisables, car elle permet d’éviter le gaspillage.

## <a name="related-resources"></a>Ressources associées

Pour plus d’informations sur les états du cycle de vie du produit, voir [Vue d’ensemble des états du cycle de vie du produit](../../pim/product-lifecycle.md).

Pour des informations détaillées avec étapes sur l’utilisation des états du cycle de vie des produits pour exclure des produits de la planification et des calculs au niveau de la nomenclature, voir [Créer un état du cycle du vie des produits pour exclure des produits de la planification](../../pim/tasks/exclude-products-master-planning.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]