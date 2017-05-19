---
title: "Nomenclature de numéros de produit"
description: "Cette rubrique décrit la procédure de paramétrage d&quot;une nomenclature de numéro de produit pour remplacer le format fixe, [Numéro de produit générique:Configuration - Taille - Couleur - Style], par un format ciblé qui inclut le numéro de produit générique, les dimensions du produit actif, et des séparateurs de texte de votre choix. Vous pouvez également créer une nomenclature afin d&quot;identifier les configurations créées par le configurateur de produit basé sur les contraintes. Ces nomenclatures peuvent contenir des attributs de votre choix."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: deda2b7986333e0d865aa87e6b34b6acdc8f6a6d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="product-number-nomenclature"></a>Nomenclature de numéros de produit

[!include[banner](../includes/banner.md)]


Cette rubrique décrit la procédure de paramétrage d'une nomenclature de numéro de produit pour remplacer le format fixe, [Numéro de produit générique:Configuration - Taille - Couleur - Style], par un format ciblé qui inclut le numéro de produit générique, les dimensions du produit actif, et des séparateurs de texte de votre choix. Vous pouvez également créer une nomenclature afin d'identifier les configurations créées par le configurateur de produit basé sur les contraintes. Ces nomenclatures peuvent contenir des attributs de votre choix.

La nouvelle nomenclature de numéro de variante de produit permet d'inclure des segments dans les identificateurs de variantes de produit. Ces segments peuvent inclure le numéro de produit générique, les dimensions de produit, les souches de numéros, les constantes de texte, et les attributs. Cette fonctionnalité vous permet de rechercher rapidement une variante de produit spécifique lorsque vous créez une commande client ou fournisseur.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclature de variantes de produit prédéfinies
Les variantes de produit sont générées pour les produits génériques selon l'une des trois technologies de configuration suivantes :

-   Variantes prédéfinies
-   Basé sur les contraintes
-   Basé sur les dimensions

Chaque variante de produit dispose d'un numéro, et la nomenclature d'identification de la variante de produit vous permet de sélectionner les segments qui seront inclus dans chaque numéro de variante de produit. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit**.

-   Numéro du produit générique
-   Valeur de souche de numéros
-   Texte constant
-   Dimensions de produit
    -   Configuration
    -   Couleur
    -   Taille
    -   Style

Une fois qu'une nomenclature d'identification de variante de produit est définie, elle peut être associée à un groupe de dimensions de produit. Par conséquent, des numéros de variante de produit sont affectés à tous les produits génériques faisant référence à ce groupe de dimensions de produit en fonction de la nomenclature. Il est également possible d'affecter une nomenclature d'identification de variante de produits directement à un produit générique, auquel cas les variantes de produit appartenant à ce produit générique reçoivent des numéros de variantes de produit en fonction de la nomenclature.

### <a name="example"></a>Exemple

Un T-shirt (TS1234) est produit dans 3 tailles différentes (S, M, L), 4 couleurs différentes (rouge, vert, bleu, jaune), et 2 styles (polo, col en V), soit un total de 24 variantes de produit possibles. Une nomenclature d'identification de variantes de produit est créée avec les segments suivants :

1.  Numéro du produit générique
2.  Constante de texte : '-'
3.  Couleur
4.  Constante de texte : '-'
5.  Taille
6.  Constante de texte : '-'
7.  Style

Le numéro de variante de produit pour le polo rouge de taille S sera : TS1234-Red-Small-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenclature des configurations basées sur les dimensions
Pour les configurations basées sur une contrainte, une nomenclature dédiée peut être paramétrée pour la dimension de produit de configuration. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit**.

-   Valeur de souche de numéros
-   Texte constant
-   Valeur d'attribut 

Chaque composant d'un modèle de configuration de produit peut avoir sa propre nomenclature de configuration. Seuls les attributs appartenant au composant peuvent être utilisés. Les attributs des sous-composants ou des exigences client ne sont pas disponibles.

### <a name="example"></a>Exemple

Un modèle de configuration de produit dispose d'un composant racine avec deux attributs.

-   Matières (plastique, bois, acier)
-   Longueur (10... 100)

Une nomenclature de configuration est définie à l'aide des segments suivants :

1.  Valeur d'attribut : Matières
2.  Constante de texte : 'AAA'
3.  Valeur d'attribut : Longueur

L'ID de configuration des matières en bois avec une longueur de 78 obtient l'ID de configuration suivant : WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenclature des configurations basées sur les dimensions
Pour les configurations basées sur les dimensions, une nomenclature dédiée peut être paramétrée pour la dimension de produit de configuration. Vous pouvez sélectionner les segments suivants sur la page **Nomenclature de produit**.

-   Valeur de souche de numéros
-   Texte constant
-   Article de groupe de configuration

Une nomenclature de configuration peut être définie pour une nomenclature.

### <a name="example"></a>Exemple

Une nomenclature a 4 lignes de nomenclature divisées en 2 groupes de configurations.

-   Ligne de nomenclature : Meuble standard, M0007
    -   Groupe de configurations : Meuble
-   Ligne de nomenclature : M0008, Meuble haut de gamme
    -   Groupe de configurations : Meuble
-   Ligne de nomenclature : M0021, tissu de grille avant
    -   Groupe de configurations : Grille avant
-   Ligne de nomenclature : M0022, métal de grille avant
    -   Groupe de configurations : Grille avant

Une nomenclature de configuration est définie à l'aide des segments suivants :

1.  Groupe de configurations : Meuble
2.  Constante de texte : '&'
3.  Groupe de configurations : Grille avant

L'ID de configuration d'un meuble standard avec grille avant en tissu est le suivant : M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nomenclature d'une combinaison de variantes de produit et de configurations
Lorsque vous utilisez une technologie de configuration basée sur une contrainte ou basée sur les dimensions pour configurer des variantes de produit pour un produit générique, les variantes de produit peuvent obtenir des numéros de variantes de produit qui incluent la nomenclature de la dimension de configuration. Pour configurer les variantes, procédez comme suit :

1.  Définissez une nomenclature de numéro de variante de produit qui contient la dimension de configuration sur la page **Nomenclature de produit**.
2.  Affectez cette nomenclature à un groupe de dimensions de produit avec la dimension de configuration.
3.  Définissez une nomenclature de configuration pour les composants ou les nomenclatures qui seront utilisées pour configurer les variantes de produit.

### <a name="example-for-constraint-based-configurations"></a>Exemple de configurations basées sur des contraintes

Dans cet exemple, vous pouvez utiliser une nomenclature de numéro de variante de produit qui inclut les segments suivants :

1.  Numéro du produit générique
2.  Texte constant '\_'
3.  Configuration

La nomenclature de configuration peut se composer des segments suivants :

1.  Valeur d'attribut : Matières
2.  Constante de texte : 'AAA'
3.  Valeur d'attribut : Longueur

Vous pouvez entrer les valeurs suivantes pour les segments :

-   Numéro du produit générique = M0099
-   Matières = plastique
-   Longueur = 12

Le numéro de variante de produit devient : M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exemple de configurations basées sur des dimensions

Dans cet exemple, vous pouvez utiliser une nomenclature de numéro de variante de produit qui inclut les segments suivants :

1.  Numéro du produit générique
2.  Constante de texte : '//'
3.  Configuration

La nomenclature de configuration peut se composer des segments suivants :

1.  Groupe de configurations : Meuble
2.  Constante de texte : '&'
3.  Groupe de configurations : Grille avant

Vous pouvez entrer les valeurs suivantes pour les segments :

-   Numéro du produit générique = D0123
-   Meuble = M0008
-   Grille avant = M0022

Le numéro de variante de produit devient : D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflits de numérotation
Il est possible de paramétrer une nomenclature de numéro de variante de produit qui n'entraîne pas des numéros de variables de produit uniques. Par exemple, cela peut se produire si une dimension de produit active n'est pas incluse dans la nomenclature d'un produit générique qui utilise la technologie de configuration de variante prédéfinie. Les conflits sont gérés différemment pour les différentes technologies de configuration.

### <a name="predefined-variants"></a>Variantes prédéfinies

Une erreur se produit si vous essayez de générer manuellement ou automatiquement des variantes de produit dans lesquelles une ou plusieurs terminent avec le même numéro de variante de produit. Afin d'éviter cela, vous devez utiliser toutes les dimensions de produit actives du groupe de dimensions de produit, ou inclure une souche de numéros pour garantir que les numéros de variantes de produit soient uniques.

### <a name="constraint-based-configurations"></a>Configurations basées sur les contraintes

Selon la nomenclature, le système peut tenter d'affecter un numéro de variante de produit non unique à une configuration. Dans ce cas, le système utilise la souche de numéros de la dimension de configuration comme nombre de variante de produit à la place. Dans ce cas, vous recevez un avertissement. Afin d'éviter cela, vous devez inclure assez d'attributs dans la nomenclature pour garantir l'unicité, et vous assurez que l'option **Réutiliser** est activée pour ce composant.

### <a name="dimension-based-configurations"></a>Configurations basées sur les dimensions

Le processus de configuration inclut une étape dans laquelle le système suggère une valeur de configuration selon la nomenclature. À cette étape, vous pouvez modifier manuellement la valeur de la configuration. Lorsque vous enregistrez la configuration, le système vérifie si la valeur de configuration est unique. Si ce n'est pas le cas, une erreur s'affiche. Vous devez entrer une valeur de configuration unique afin d'enregistrer la configuration.



<a name="see-also"></a>Voir également :
--------

[Créer une nomenclature de numéros de produit pour des variantes de produit prédéfinies (Guide de tâche)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Créer une nomenclature de numéros de produit pour des variantes de produit prédéfinies (Guide de tâche)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)




