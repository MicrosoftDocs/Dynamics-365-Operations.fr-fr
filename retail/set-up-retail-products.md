---
title: "Paramétrer les produits vendus au détail"
description: "Cet article décrit la procédure de paramétrage des produits vendus au détail dans Microsoft Dynamics 365 pour les opérations - au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 116c49174989ff14982027cc235640c2ad7322f2
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-retail-products"></a>Paramétrer les produits vendus au détail

Cet article décrit la procédure de paramétrage des produits vendus au détail dans Microsoft Dynamics 365 pour les opérations - au détail.

Avant de proposer des produits pour la revente dans vos canaux de vente au détail, vous devez créer et de configurer des produits dans Dynamics 365 pour Microsoft Dynamics® AX d'opérations - au détail. La vente au détail utilise les fonctions de produit dans Dynamics 365 pour les opérations créent des produits à l'échelle de l'organisation dans le produit générique. Vous pouvez créer les produits, définir les propriétés de produit et les attributs, et affecter les produits aux hiérarchies des catégories de vente au détail. Pour rendre les produits disponibles sur vos canaux de vente au détail et les ajouter à un assortiment actif, vous devez lancer les produits dans les entités juridiques dans lesquelles ils sont disponibles. Pour paramétrer les produits que vous vendez à l'aide de canaux de vente au détail, réalisez les tâches suivantes.

1.  Définissez une hiérarchie de produits vendus au détail. Avec une hiérarchie de catégories fonctions dans Dynamics 365 pour les opérations, vous pouvez définir des hiérarchies des catégories de vente au détail pour regrouper et de commander des produits par catégorie que vous répartissez à vos canaux de vente au détail. Les attributs définis par l'utilisateur et les attributs système peuvent être définis au niveau de la catégorie. Ensuite, tous les produits affectés à cette catégorie héritent de ces attributs. Plusieurs hiérarchies de catégories peuvent être définies, et chaque produit peut être affecté à plusieurs hiérarchies. Toutefois, dans une hiérarchie unique, chaque produit ne peut être affecté qu'à une seule catégorie.
2.  Ajoutez des produits et des variantes de produit au produit générique. les produits ajoutés au produit générique représentent une liste globale des produits. Vous pouvez ajouter des produits manuellement et de manière individuelle ou vous pouvez importer les données de produit de vos fournisseurs.
3.  Lancez les produits dans l'entité juridique. Seuls les produits lancés dans des entités juridiques peuvent être rendus accessibles à vos canaux de vente au détail. Lorsque vous définissez un produit en premier lieu, vous le définissez au niveau de l'organisation. Vous pouvez sélectionner une ou plusieurs entités juridiques dans lesquelles lancer le produit. Le produit est alors disponible sur plusieurs canaux de vente au détail au sein de votre organisation. Vous pouvez utiliser cette fonctionnalité pour créer un produit à une seule reprise, pour ajouter et mettre à jour les attributs et les propriétés du produit dans un emplacement, puis distribuer le produit au sein de votre organisation, dans les canaux de vente au détail dans lesquels le produit est disponible.
4.  Ajout de produits aux assortiments. Un assortiment représente un ensemble de produits que vous proposez dans vos canaux de vente au détail. Vous pouvez définir un ou plusieurs assortiment(s), et chaque produit peut être affecté à un ou plusieurs assortiment(s). Pour affecter des produits à des canaux de vente au détail, vous affectez les assortiments à ces canaux de vente au détail. Lorsque vous créez un assortiment, vous pouvez ajouter des produits qui n'ont pas encore été lancés dans une entité juridique. Toutefois, vous devez lancer les produits dans une entité juridique avant que ceux-ci puissent être rendus accessibles sur les canaux de vente au détail.
5.  Ajout de produits aux hiérarchies de navigation. Avant que les produits puissent accessible en ligne ou dans le point de vente (POS), ils doivent être classés dans une hiérarchie des ventes au détail de navigation.
6.  Ajout de produits aux catalogues. Bien que cette étape est facultative du PDV, les magasins en ligne demandent que les produits sont inclus dans au moins un catalogue.



