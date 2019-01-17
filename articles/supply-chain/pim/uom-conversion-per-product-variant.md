---
title: "Conversion d'unité de mesure selon la variante de produit"
description: "Cette rubrique explique comment les conversions d'unités de mesure peuvent être paramétrées selon les variantes de produit."
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 9d5d6fd65717cd886f1c6576aabf2bc59ca4fcaf
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2018

---

# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversion d'unité de mesure selon la variante de produit

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

Cette rubrique explique comment les conversions d'unités de mesure peuvent être paramétrées selon les variantes de produit. Elle inclut un exemple de paramétrage.

Cette fonctionnalité permet aux sociétés de définir différentes conversions d'unités entre les variantes du même produit. L'exemple ci-dessous est utilisé dans cette rubrique. Une société vend des t-shirts dans les tailles S, M, L et XL. Le T-shirt est défini comme produit, et les différentes tailles sont définies en tant que variantes de produit. Les t-shirts sont emballés dans des boîtes et il peut y avoir cinq t-shirts dans une boîte, à l'exception de la taille XL où il n'y a d'espace pour quatre t-shirts. La société souhaite suivre les différentes variantes de t-shirts dans l'unité **Pièces** mais vend les t-shirts dans l'unité **Boîtes**. La conversion entre l'unité de stock et l'unité de vente est de 1 boîte = 5 pièces, sauf la variante XL, où la conversion est 1 boîte = 4 pièces.

## <a name="setup"></a>Paramétrage

Vous pouvez configurer les paramètres pour utiliser la fonctionnalité pour les articles activés pour **Tous les processus** ou uniquement pour le produit activé pour les **Processus d'entrepôt** à l'aide de l'option **Activer les conversations d'unités de mesure** sur la page **Paramètres des informations produit**.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Paramétrage d'un produit pour la conversion d'unités par variante

Les variantes de produit peuvent être créées uniquement pour les produits du **sous-type Produit** : **Produit générique**. Pour plus d'informations, voir [Création d'un produit générique](tasks/create-product-master.md).

La fonctionnalité n'est pas activée pour les produits paramétrés pour les processus en poids variable. 

Lors de la création d'un produit générique activez la conversion des unités de mesure à l'aide de l'option **Activer les conversions d'unités de mesure** sur la page **Détails de produit**.

Lorsque le produit générique avec des variantes de produits lancés est créé, des conversions d'unités par variantes peuvent être paramétrées. Vous pouvez trouver l'option de menu pour ouvrir la page de conversion d'unités dans le contexte d'un produit ou d'une variante de produit dans les pages suivantes.

-   Page **Détails de produit**
-   Page **Détails des produits lancés**
-   Page **Variantes de produits lancés**

Lorsque vous ouvrez la page **Conversion d'unités** dans le contexte d'une variante de produit générique ou de produit lancé, vous pouvez choisir si vous voulez paramétrer la conversion d'unités pour le produit ou pour une variante de produit. Pour cela, sélectionnez **Variante de produit** ou **Produit** dans le champ **Créer la conversion pour**.

### <a name="product-variant"></a>Variante de produit

Si vous sélectionnez **Variante de produit**, vous pouvez sélectionner pour quelle variante vous souhaitez paramétrer la conversion d'unités dans le champ **Variante de produit**.

### <a name="product"></a>Produit

Si vous sélectionnez **Produit**, vous pouvez paramétrer une conversion d'unités pour le produit générique. Cette conversion d'unité s'appliquera pour toutes les variantes de produit sans conversion d'unité définie.

### <a name="example"></a>Exemple

Un produit générique, **T-shirt**, a quatre variantes de produits lancés : S, M, L et XL. Les t-shirts sont emballés dans des boîtes et il peut y avoir cinq t-shirts dans une boîte, à l'exception de la taille XL où il n'y a d'espace pour quatre t-shirts.

Premièrement, ouvrez la page **Conversion d'unité** de la page de détails de produit lancé pour **T-shirt.**

Dans la page **Conversion d'unité**, paramétrez la conversion d'unité pour la variante de produit lancé XL.

| **Champ**             | **Paramètre**             |
|-----------------------|-------------------------|
| Créer une conversion pour | Variante de produit         |
| Variante de produit       | T-shirt : : XL : : |
| Unité - De             | Boîtes                   |
| Facteur                | 4                       |
| À l'unité               | Pièces                  |

Les variantes de produit lancé S, M et L ont la même conversion d'unité entre l'unité Boîte et Pièces, ce qui signifie que vous pouvez définir une conversion d'unité pour ces variantes de produit dans le produit générique.

| **Champ**             | **Paramètre** |
|-----------------------|-------------|
| Créer une conversion pour | Produit     |
| Produit               | T-shirt     |
| Unité - De             | Boîtes       |
| Facteur                | 5           |
| À l'unité               | Pièces      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Utilisation d'Excel pour mettre à jour les conversions d'unité

Si un produit a plusieurs variantes de produit différentes avec des conversions d'unités distinctes, il est conseillé d'exporter les conversions d'unités de la page **Conversion d'unité** dans une feuille de calcul Excel, de mettre à jour les conversions, puis de les publier dans Finance and Operations.

L'option permettant d'exporter vers Excel et de republier les modifications dans Finance and Operations est activée dans l'option de menu **Ouvrir dans Microsoft Office** sur le volet Actions de la page **Conversion d'unité**.

