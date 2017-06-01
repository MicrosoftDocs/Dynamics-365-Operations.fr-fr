---
title: "Paramétrer les produits vendus au détail"
description: "Cet article décrit paramétrer les produits de vente au détail dans Microsoft Dynamics 365 for Operations - Vente au détail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a0fdea7560c6a43f973cc79ebc117ce1e21d73fb
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-retail-products"></a>Paramétrer les produits vendus au détail

[!include[banner](includes/banner.md)]


Cet article décrit paramétrer les produits de vente au détail dans Microsoft Dynamics 365 for Operations - Vente au détail.

Avant de pouvoir proposer des produits pour la revente dans vos canaux de vente au détail, vous devez créer et configurer les produits dans Dynamics 365 for Operations - Vente au détail. La vente au détail utilise les fonctionnalités de produit de Microsoft Dynamics 365 for Operations pour créer des produits à l'échelle de l'organisation dans le produit générique. Vous pouvez créer les produits, définir les propriétés de produit et les attributs, et affecter les produits aux hiérarchies des catégories de vente au détail. Pour rendre les produits disponibles sur vos canaux de vente au détail et les ajouter à un assortiment actif, vous devez lancer les produits dans les entités juridiques dans lesquelles ils sont disponibles. Pour paramétrer les produits que vous vendez à l'aide de canaux de vente au détail, réalisez les tâches suivantes.

1.  Définissez une hiérarchie de produits vendus au détail. À l'aide des fonctions de hiérarchie de catégories disponibles dans Dynamics 365 for Operations, vous pouvez définir des hiérarchies de catégories de vente au détail pour grouper et classer par catégorie les produits que vous distribuez dans vos canaux de vente au détail. Les attributs définis par l'utilisateur et les attributs système peuvent être définis au niveau de la catégorie. Ensuite, tous les produits affectés à cette catégorie héritent de ces attributs. Plusieurs hiérarchies de catégories peuvent être définies, et chaque produit peut être affecté à plusieurs hiérarchies. Toutefois, dans une hiérarchie unique, chaque produit ne peut être affecté qu'à une seule catégorie.
2.  Ajoutez des produits et des variantes de produit au produit générique. les produits ajoutés au produit générique représentent une liste globale des produits. Vous pouvez ajouter des produits manuellement et de manière individuelle ou vous pouvez importer les données de produit de vos fournisseurs.
3.  Lancez les produits dans l'entité juridique. Seuls les produits lancés dans des entités juridiques peuvent être rendus accessibles à vos canaux de vente au détail. Lorsque vous définissez un produit en premier lieu, vous le définissez au niveau de l'organisation. Vous pouvez sélectionner une ou plusieurs entités juridiques dans lesquelles lancer le produit. Le produit est alors disponible sur plusieurs canaux de vente au détail au sein de votre organisation. Vous pouvez utiliser cette fonctionnalité pour créer un produit à une seule reprise, pour ajouter et mettre à jour les attributs et les propriétés du produit dans un emplacement, puis distribuer le produit au sein de votre organisation, dans les canaux de vente au détail dans lesquels le produit est disponible.
4.  Ajout de produits aux assortiments. Un assortiment représente un ensemble de produits que vous proposez dans vos canaux de vente au détail. Vous pouvez définir un ou plusieurs assortiment(s), et chaque produit peut être affecté à un ou plusieurs assortiment(s). Pour affecter des produits à des canaux de vente au détail, vous affectez les assortiments à ces canaux de vente au détail. Lorsque vous créez un assortiment, vous pouvez ajouter des produits qui n'ont pas encore été lancés dans une entité juridique. Toutefois, vous devez lancer les produits dans une entité juridique avant que ceux-ci puissent être rendus accessibles sur les canaux de vente au détail.
5.  Ajoutez des produits aux hiérarchies de navigation. Pour pouvoir parcourir les produits en ligne ou dans un point de vente, ils doivent être classés par catégorie dans une hiérarchie de navigation de vente au détail.
6.  Ajoutez des produits aux catalogues. Bien que cette étape soit facultative pour le point de vente, les magasins en ligne exigent que les produits sont inclus dans au moins un catalogue.





