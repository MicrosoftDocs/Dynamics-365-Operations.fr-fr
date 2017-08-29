---
title: "Nomenclature de numéros et de noms de variante de produit"
description: "Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe. La nouvelle nomenclature a un format ciblé qui inclut le numéro du produit générique, les dimensions du produit actif et les séparateurs de texte de votre choix. Vous pouvez également créer une nomenclature pour les noms de produit. Enfin, vous pouvez créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes. Ces nomenclatures peuvent contenir des attributs de votre choix."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 0c3c1a3e64b016aa72e933f4d6cba854549ff13a
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Nomenclature de numéros et de noms de variante de produit

Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéros de produit pour remplacer le format [Numéro du produit générique - Configuration - Taille - Couleur - Style] fixe. La nouvelle nomenclature a un format ciblé qui inclut le numéro du produit générique, les dimensions du produit actif et les séparateurs de texte de votre choix. Vous pouvez également créer une nomenclature pour les noms de produit. Enfin, vous pouvez créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes. Ces nomenclatures peuvent contenir des attributs de votre choix.

Les nouvelles nomenclatures des numéros et des noms de variante de produit vous permettent d'inclure des segments dans les identificateurs des variantes de produit. Ces segments peuvent inclure le numéro et le nom du produit générique, les ID et noms de dimension de produit, les souches de numéros, les constantes de texte et les attributs. Cette fonctionnalité vous permet de rechercher rapidement une variante de produit spécifique lorsque vous créez une commande client ou fournisseur. Vous créez des nomenclatures pour les numéros et les noms de variante de produit à l'aide de la page **Nomenclature de produit**. Pour ouvrir cette page, cliquez sur **Gestion des informations sur les produits** &gt; **Paramétrage**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclature de variantes de produit prédéfinies
Les variantes de produit sont générées pour les produits génériques selon l'une des trois technologies de configuration suivantes :

-   Variantes prédéfinies
-   Basé sur les contraintes
-   Basé sur les dimensions

Chaque variante de produit dispose d'un numéro et d'un nom, et les nomenclatures d'identification de la variante de produit vous permet de sélectionner les segments qui seront inclus dans chaque numéro ou nom de variante de produit. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :

-   Numéro du produit générique
-   Nom du produit générique
-   Valeur de souche de numéros
-   Texte constant
-   Dimensions de produit
    -   Nom ou ID configuration
    -   Nom ou ID couleur
    -   Nom ou ID taille
    -   Nom ou ID style

Une fois que vous définissez une nomenclature de numéros d'identification de variante de produit, vous pouvez l'associer à un groupe de dimensions de produit. Des numéros de variante de produit sont affectés à tous les produits génériques qui font référence à ce groupe de dimensions de produit en fonction de la nomenclature. Toutefois, les nomenclatures de noms de variante de produit ne peuvent pas être associées à des groupes de dimensions de produit. Vous pouvez également affecter une nomenclature d'identification de variante de produit directement à un produit générique. Dans ce cas, des numéros et des noms de variante de produit sont affectés aux variantes de produit qui appartiennent au produit générique en fonction des nomenclatures.

### <a name="example"></a>Exemple

Un T-shirt (TS1234) est produit dans trois tailles (S, M, L), quatre couleurs (rouge, vert, bleu, jaune) et deux styles (polo, col en V). Ainsi, 24 variantes de produit sont possibles (= 3 × 4 x 2). Vous créez une nomenclature de numéros de variante de produit qui comporte les segments suivants :

1.  Numéro du produit générique
2.  Constante de texte : "-"
3.  Couleur
4.  Constante de texte : "-"
5.  Taille
6.  Constante de texte : "-"
7.  Style

Dans ce cas, le numéro de variante de produit pour un T-shirt polo rouge de taille S sera TS1234-Red-Small-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenclature des configurations basées sur les dimensions
Pour les configurations basées sur les contraintes, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :

-   Valeur de souche de numéros
-   Texte constant
-   Valeur d'attribut

Chaque composant d'un modèle de configuration de produit peut avoir sa propre nomenclature de configuration. Seuls les attributs appartenant au composant peuvent être utilisés. Les attributs des sous-composants ou des exigences client ne peuvent pas être utilisés.

### <a name="example"></a>Exemple

Un modèle de configuration de produit dispose d'un composant racine avec deux attributs :

-   Matières (plastique, bois, acier)
-   Longueur (10... 100)

Vous créez une nomenclature de configuration qui comporte les segments suivants :

1.  Valeur d'attribut : Matières
2.  Constante de texte : "AAA"
3.  Valeur d'attribut : Longueur

Dans ce cas, l'ID de configuration des matières en bois avec une longueur de 78 est WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenclature des configurations basées sur les dimensions
Pour les configurations basées sur les dimensions, vous pouvez créer une nomenclature dédiée pour la dimension de produit de configuration. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit** :

-   Valeur de souche de numéros
-   Texte constant
-   Article de groupe de configuration

Vous pouvez définir une nomenclature de configuration pour une nomenclature.

### <a name="example"></a>Exemple

Une nomenclature comporte quatre lignes de nomenclature qui sont divisées en deux groupes de configuration :

-   Ligne de nomenclature : Meuble standard, M0007
    -   Groupe de configurations : Meuble
-   Ligne de nomenclature : M0008, Meuble haut de gamme
    -   Groupe de configurations : Meuble
-   Ligne de nomenclature : M0021, tissu de grille avant
    -   Groupe de configurations : Grille avant
-   Ligne de nomenclature : M0022, métal de grille avant
    -   Groupe de configurations : Grille avant

Vous créez une nomenclature de configuration qui comporte les segments suivants :

1.  Groupe de configurations : Meuble
2.  Constante de texte : "&"
3.  Groupe de configurations : Grille avant

Dans ce cas, l'ID de configuration d'un meuble standard avec grille avant en tissu est M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Nomenclature d'une combinaison de variantes de produit et de configurations
Lorsque vous utilisez la technologie de configuration basée sur les contraintes ou basée sur les dimensions pour configurer des variantes de produit pour un produit générique, les numéros des variantes de produit peuvent inclure la nomenclature de la dimension de configuration. Pour configurer les variantes, procédez comme suit :

1.  Sur la page **Nomenclature de produit**, définissez une nomenclature de numéros de variante de produit qui contient la dimension de configuration.
2.  Affectez la nomenclature à un groupe de dimensions de produit qui inclut la dimension de configuration.
3.  Définissez une nomenclature de configuration pour les composants ou les nomenclatures qui seront utilisées pour configurer les variantes de produit.

Vous pouvez également créer des nomenclatures pour les noms de variante de produit. Les noms de variante de produit peuvent être configurés pour inclure l'ID ou le nom de configuration.

### <a name="example-for-constraint-based-configurations"></a>Exemple de configurations basées sur des contraintes

Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :

1.  Numéro du produit générique
2.  Constante de texte : "\_"
3.  Configuration

La nomenclature de configuration comporte les segments suivants :

1.  Valeur d'attribut : Matières
2.  Constante de texte : "AAA"
3.  Valeur d'attribut : Longueur

Entrez les valeurs suivantes pour les segments :

-   Numéro du produit générique = **M0099**
-   Matières = **Plastique**
-   Longueur = **12**

Dans ce cas, le numéro de variante de produit est M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exemple de configurations basées sur des dimensions

Pour cet exemple, vous pouvez utiliser une nomenclature de numéros de variante de produit qui comporte les segments suivants :

1.  Numéro du produit générique
2.  Constante de texte : "//"
3.  Configuration

La nomenclature de configuration comporte les segments suivants :

1.  Groupe de configurations : Meuble
2.  Constante de texte : "&"
3.  Groupe de configurations : Grille avant

Entrez les valeurs suivantes pour les segments :

-   Numéro du produit générique = **D0123**
-   Meuble = **M0008**
-   Grille avant = **M0022**

Dans ce cas, le numéro de variante de produit est D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflits de numérotation
Dans certains cas, une nomenclature de numéros de variante de produit que vous paramétrez peut ne pas produire des numéros de variante de produit uniques. Par exemple, les numéros de variante de produit ne sont pas uniques si une dimension de produit active n'est pas incluse dans la nomenclature d'un produit générique qui utilise la technologie de configuration de variante prédéfinie. La façon dont vous gérez les conflits varie selon la technologie de configuration.

### <a name="predefined-variants"></a>Variantes prédéfinies

Une erreur se produit si vous essayez de créer manuellement ou de générer automatiquement des variantes de produit, et plusieurs variantes de produit se terminent avec le même numéro de variante de produit. Pour éviter ce scénario, vous devez utiliser toutes les dimensions de produit actives dans le groupe de dimensions de produit. Sinon, incluez une souche de numéros pour garantir que les numéros de variante de produit sont uniques.

### <a name="constraint-based-configurations"></a>Configurations basées sur les contraintes

Selon la nomenclature, le système peut tenter d'affecter un numéro de variante de produit non unique à une configuration. Dans ce cas, le système utilise la souche de numéros de la dimension de configuration comme numéro de variante de produit à la place. Vous recevrez alors un avertissement. Pour éviter ce scénario, vous devez inclure assez d'attributs dans la nomenclature pour garantir que les numéros de variable de produit sont uniques. Vous devez également vous assurer que l'option **Réutilisation** est activée pour le composant.

### <a name="dimension-based-configurations"></a>Configurations basées sur les dimensions

Au cours d'une étape du processus de configuration, le système suggère une valeur de configuration selon la nomenclature. À cette étape, vous pouvez modifier manuellement la valeur de la configuration. Lorsque vous enregistrez la configuration, le système vérifie que la valeur de configuration est unique. Si la valeur entrée n'est pas unique, vous recevez un message d'erreur. Pour enregistrer la configuration, vous devez entrer une valeur de configuration unique.

<a name="see-also"></a>Voir également :
--------

[Créer une nomenclature de numéros de produit pour des variantes de produit prédéfinies](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-predefined-variants-2016-11)

[Créer une nomenclature de numéros de produit pour des variantes de produit configurées](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-product-variants_2016_11)


