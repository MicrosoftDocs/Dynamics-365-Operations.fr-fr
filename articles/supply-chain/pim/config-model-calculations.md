---
title: Calculs du modèle de configuration de produit
description: Cette rubrique décrit comment créer des calculs pour les attributs dans un modèle de configuration de produit
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f0806a5b36b04e77a5a6d10f3c2eb3d7ba680e75
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356414"
---
# <a name="product-configuration-model-calculations"></a>Calculs du modèle de configuration de produit

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer des calculs pour les attributs dans un modèle de configuration de produit.

## <a name="prerequisites"></a>Conditions préalables

Les calculs sont utilisés dans un modèle de configuration de produit pour calculer les valeurs de configuration pour un produit. Avant de pouvoir commencer à configurer des calculs, le modèle de configuration de produit associé doit exister. Pour une présentation du processus de paramétrage des modèles de configuration et des tâches associées, voir [Paramétrer un modèle de configuration de produit](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>Création d’un calcul

Un calcul se compose d’une expression et d’un attribut cible. Pour plus d’informations, voir [FAQ sur les calculs pour les modèles de configuration de produit](calculate-product-configuration-models.md).

Pour créer un calcul pour un modèle de produit existant, procédez comme suit.

1. Accédez à **Gestion des informations sur les produits \> Commun \> Modèles de configuration de produit**.
1. Ouvrez un modèle de configuration de produit, puis sélectionnez **Modifier**.
1. Sur le raccourci **Calculs**, sélectionnez **Ajouter** pour ajouter un calcul, puis définissez les champs suivants :

    - **Nom** : Entrez un nom pour le calcul.
    - **Description** : entrez une description du calcul.
    - **Attribut cible** : sélectionnez l’attribut pour lequel vous effectuez le calcul.

1. Sélectionnez **Modifier l’expression**.
1. Dans la boîte de dialogue **Entrer un calcul**, ajoutez les attributs, opérateurs et valeurs requis à l’expression. Pour plus d’informations sur l’utilisation de ces éléments, voir la rubrique [Contraintes d’expression et contraintes de table dans les modèles de configuration du produit](expression-constraints-table-constraints-product-configuration-models.md).
1. Lorsque votre expression est prête, sélectionnez **OK**.

## <a name="calculation-examples"></a>Exemples de calcul

Cette section fournit quelques exemples illustrant le fonctionnement des calculs.

### <a name="example-1"></a>Exemple 1

L’attribut cible est de type booléen, et le calcul utilise l’expression conditionnelle suivante :

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

Cette expression renvoie la valeur *True* à l’attribut cible si `decimalAttribute2` est supérieur ou égal à `decimalAttribute1`. Sinon, elle renvoie une valeur *False*.

### <a name="example-2"></a>Exemple 2

Cet exemple utilise l’attribut texte `textFixedList` comme attribut cible. Cet attribut contient la liste fixe suivante.

| Valeur | Valeur de solveur |
|---|---|
| A | 1a |
| o | 2b |
| C | 2c |

La capture d’écran suivante montre à quoi peuvent ressembler les paramètres de cet attribut dans votre système.

![Paramètres de type d’attribut pour l’exemple 2.](media/model-calculations-example2.png "Paramètres de type d’attribut pour l’exemple 2")

L’attribut est utilisé dans l’instruction conditionnelle suivante :

`If[integerAttribute < 150, 0, 2]`

Si `integerAttribute` est inférieur à 150, cette instruction renvoie la valeur textuelle du premier enregistrement de la liste fixe, *A*. Sinon, elle renvoie la valeur textuelle du troisième enregistrement de la liste fixe, *C*.

> [!NOTE]
> La liste fixe équivaut à une énumération de base zéro (enum) et ses valeurs sont accessibles par la valeur entière appropriée. Par conséquent, la première valeur de liste fixe (*A*) correspond à *0*, la deuxième valeur (*B*) correspond à *1* et la troisième valeur (*C*) correspond à *2*.

### <a name="example-3"></a>Exemple 3

Cet exemple utilise l’attribut cible `textFixedList` de l’exemple précédent. Il utilise également un autre attribut texte, `textAttribute`, qui contient la liste fixe suivante.

| Valeur | Valeur de solveur |
|---|---|
| AA | 1aa |
| BB | 2bb |

La capture d’écran suivante montre à quoi peuvent ressembler les paramètres de cet attribut dans votre système.

![Paramètres de type d’attribut pour l’exemple 3.](media/model-calculations-example3.png "Paramètres de type d’attribut pour l’exemple 3")

La valeur de l’attribut `textFixedList` est calculée à l’aide de l’instruction conditionnelle suivante :

`If[textAttribute == "1aa", 0, 2]`

Si la valeur de `textAttribute` a une valeur de solveur égale à *1aa*, cette expression renvoie la valeur textuelle du premier enregistrement de la liste fixe `textFixedList`, *A*. Sinon, elle renvoie la valeur textuelle du troisième enregistrement de la liste fixe `textFixedList`, *C*.

> [!NOTE]
> - L’instruction conditionnelle doit utiliser la valeur de solveur de l’attribut.
> - Seuls les attributs texte de liste fixe peuvent être utilisés dans les calculs.

## <a name="see-also"></a>Voir également :

- [Forums aux questions sur les calculs pour les modèles de configuration de produit](calculate-product-configuration-models.md)
- [Ajouter une contrainte d’expression à un modèle de configuration de produit](tasks/add-expression-constraint-product-configuration-model.md)
- [Vue d’ensemble des modèles de configuration de produit](product-configuration-models.md)
