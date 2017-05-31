---
title: Dimensions de produit
description: "Il existe quatre dimensions de produit -  Couleur, Configuration, Taille et Style. Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques. Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7e6409db92b929eebca70d6d0176dd9b54a5f9b9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="product-dimensions"></a>Dimensions de produit

[!include[banner](../includes/banner.md)]


Il existe quatre dimensions de produit -  Couleur, Configuration, Taille et Style. Vous combinez des dimensions de produit dans les groupes de dimensions et vous affectez des groupes de dimensions aux produits génériques. Les combinaisons de dimensions de produit déterminent la manière dont les variantes de produit sont définies.

Les dimensions de produit sont des caractéristiques qui permettent d'identifier une variante de produit. Vous pouvez utiliser des combinaisons de dimensions de produit pour définir des variantes de produit. Vous devez définir au moins une dimension de produit pour un produit générique pour créer une variante de produit.
Variantes de produit
----------------

Les variantes de produit sont également appelées des articles. Un article est un produit corporel, ce qui n'est pas le même qu'un service. Il est également possible de définir un produit générique de type Service. En utilisant le type Service, vous pouvez spécifier des variantes de produit qui incluent les services. Par exemple, vous pouvez spécifier un produit générique pour le travail Conseil et des variantes de produit pour le travail qui est effectué par les consultants supérieurs et les consultants juniors.

## <a name="product-dimensions"></a>Dimensions de produit
Les dimensions de produit suivantes sont disponibles : Configuration, Couleur, Taille et Style. Une variante de produit peut être générée selon les valeurs de dimension de produit.

Les valeurs de dimensions de produit telles que la taille, la couleur et le style peuvent être créées dans les pages **Taille**, **Couleur** et **Style**, qui sont accessibles à partir des emplacements suivants : **Gestion des informations sur les produits** &gt; **Paramétrage** &gt; **Groupes de dimensions et de variantes** &gt; **Tailles/Couleurs/Styles**. Les valeurs de dimension de produit pour la dimension Configuration sont généralement créées à l'aide du configurateur de produits ou du configurateur basé sur les dimensions. Les dimensions de produit peuvent également être créées et tenues à jour dans la page **Dimensions de produit**, qui est accessible depuis les emplacements suivants :
-   Cliquez sur **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits génériques**. Dans le volet **Actions**, cliquez sur **Dimensions de produit**.
-   Cliquez sur **Gestion des informations sur les produits** &gt; **Produits** &gt; **Tous les produits et produits génériques**. Sélectionnez un produit générique. Dans le volet **Actions**, cliquez sur **Dimensions de produit**.
-   Cliquez sur **Gestion des informations sur les produits** &gt; **Produits lancés**. Sélectionnez un produit générique. Dans le volet **Actions**, cliquez sur **Produit**. Dans le groupe **Produit générique**, cliquez sur **Dimensions de produit**.

Le nombre de variantes que vous pouvez créer pour un article est limité par le nombre de combinaisons possibles de dimension de produit.
| **Conseil**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lorsque vous utilisez un produit sur, par exemple, une ligne de commande, vous sélectionnez les dimensions de produit pour identifier la variante de produit avec laquelle vous souhaitez travailler. |

## <a name="example"></a>Exemple
Une entreprise vend des jeans. Les articles, des jeans, utilisent les dimensions de produit Couleur et Taille. Ils sont vendus en trois couleurs et en six tailles différentes. Couleurs : bleu, noir, marron. Tailles : XS, S, M, L, XL, XXL. Toutes les tailles ne sont pas disponibles dans les trois couleurs. Si toutes les combinaisons étaient disponibles, il y aurait 18 types différents de jeans. Dans cet exemple, seules les neuf combinaisons de variantes de produit suivantes sont produites.

| Couleur | Taille |
|-------|------|
| Bleu  | XS   |
| Bleu  | Sa    |
| Bleu  | F    |
| Noir | F    |
| Noir | R    |
| Noir | XL   |
| Marron | R    |
| Marron | XL   |
| Marron | XXL  |






