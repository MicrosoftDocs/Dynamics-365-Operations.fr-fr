---
title: Paramétrer les produits vendus au détail
description: Cet article explique comment configurer les produits dans Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b2c5a8976973203a943a2cec7658a2998c54f279
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412345"
---
# <a name="set-up-retail-products"></a>Paramétrer les produits vendus au détail

[!include [banner](includes/banner.md)]

Cet article explique comment configurer les produits dans Dynamics 365 Commerce.

Avant de proposer des produits à la revente dans vos canaux de commerce, vous devez créer et configurer les produits. Commerce crée des produits à l'échelle de l'organisation dans le produit générique. Vous pouvez créer des produits, en définir les propriétés et les attributs, et les affecter aux hiérarchies de catégories de commerce. Pour afficher les produits sur vos canaux et les ajouter à un assortiment actif, vous devez les lancer dans les entités juridiques dans lesquelles ils sont disponibles. Pour configurer les produits que vous vendez sur les canaux, réalisez les tâches suivantes.

1. **Définissez une hiérarchie de produits.** À l'aide des fonctionnalités de hiérarchie de catégories disponibles dans Commerce, définissez des hiérarchies de catégories pour regrouper et hiérachiser les produits que vous distribuez sur vos canaux. Les attributs définis par l'utilisateur et les attributs système peuvent être définis au niveau de la catégorie. Ensuite, tous les produits affectés à cette catégorie héritent de ces attributs. Plusieurs hiérarchies de catégories peuvent être définies, et chaque produit peut être affecté à plusieurs hiérarchies. Toutefois, dans une hiérarchie unique, chaque produit ne peut être affecté qu'à une seule catégorie.
2. **Ajoutez des produits et des variantes de produit au produit générique.** les produits ajoutés au produit générique représentent une liste globale des produits. Vous pouvez ajouter des produits manuellement et de manière individuelle ou vous pouvez importer les données de produit de vos fournisseurs.
3. **Lancez les produits dans l'entité juridique.** Seuls les produits lancés dans les entités juridiques sont disponibles pour vos canaux. Lorsque vous définissez un produit en premier lieu, vous le définissez au niveau de l'organisation. Vous pouvez sélectionner une ou plusieurs entités juridiques dans lesquelles lancer le produit. Le produit est alors disponible sur plusieurs canaux au sein de votre organisation. Utilisez cette fonctionnalité pour créer un produit à une seule reprise, ajouter et mettre à jour les attributs et les propriétés du produit dans un emplacement, puis distribuer le produit dans toute l'organisation, vers les canaux dans lesquels le produit est disponible.
4. **Ajout de produits aux assortiments.** Un assortiment représente un ensemble de produits que vous proposez dans vos canaux. Vous pouvez définir un ou plusieurs assortiment(s), et chaque produit peut être affecté à un ou plusieurs assortiment(s). Pour affecter des produits à des canaux, affectez les assortiments à ces canaux. Lorsque vous créez un assortiment, vous pouvez ajouter des produits qui n'ont pas encore été lancés dans une entité juridique. Toutefois, vous devez lancer les produits dans une entité juridique pour que ceux-ci soient accessibles sur les canaux.
5. **Ajoutez des produits aux hiérarchies de navigation.** Pour pouvoir parcourir les produits en ligne ou dans un point de vente (PDV), ils doivent être classés par catégorie dans une hiérarchie de navigation Commerce.
6. **Ajoutez des produits aux catalogues.** Bien que cette étape soit facultative pour le point de vente, les magasins en ligne exigent que les produits sont inclus dans au moins un catalogue.


[!INCLUDE[footer-include](../includes/footer-banner.md)]