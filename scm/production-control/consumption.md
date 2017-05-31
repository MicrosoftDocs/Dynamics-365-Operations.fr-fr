---
title: "Calculer la consommation de matières"
description: "Cet article fournit des informations sur les différentes options relatives au calcul de la consommation de matières."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1bd3168e80719c86e9a0541200fdb1608410c8f5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="calculate-material-consumption"></a>Calculer la consommation de matières

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les différentes options relatives au calcul de la consommation de matières. 

Les options suivantes relatives au calcul de la consommation de matières sont disponibles sous les onglets **Paramétrage** et **Consommation de l'étape** sur l'organisateur **Détails de ligne** de la page **Nomenclatures**.

## <a name="variable-and-constant-consumption"></a>Consommation variable et constante
Dans le champ **Type de consommation**, vous pouvez sélectionner si la consommation doit être calculée comme quantité constante ou comme quantité variable. Sélectionnez **Constante** si une quantité ou un volume fixe est requis pour la production, peu importe la quantité produite. Sélectionnez **Variable**, qui est le paramètre par défaut, si la quantité de matières requises dans des produits finis est proportionnelle au nombre de produits finis fabriqués.

## <a name="calculating-consumption-from-a-formula"></a>Calcul de la consommation à partir d'une formule
Dans le champ **Formule**, vous pouvez paramétrer diverses formules pour calculer la consommation de matières. Si vous utilisez la valeur par défaut, **Standard**, la consommation n'est pas calculée à partir d'une formule. Les formules suivantes s'associent aux champs **Hauteur**, **Largeur**, **Profondeur**, **Densité** et  **Constante** :

-   Hauteur \* Constante
-   Hauteur \* Largeur \* Constante
-   Hauteur \* Largeur \* Profondeur \* Constante
-   (Hauteur \* Largeur \* Profondeur / Densité) \* Constante

## <a name="rounding-up-and-multiples"></a>Arrondi et multiples
Associés, les champs **Arrondi** et **Multiples** permettent d'arrondir la valeur de consommation des matières. Par exemple, vous pouvez arrondir la valeur en fonction de l'unité de manutention dans laquelle la matière première est prélevée pour la production. Les options suivantes sont disponibles dans le champ **Arrondi** : **Quantité****Mesure** et **Consommation**.

### <a name="quantity"></a>Quantité

Si vous sélectionnez **Quantité** comme mécanisme d'arrondi, la quantité doit être un multiple de la quantité spécifiée. Par exemple, si des nombres entiers sont requis, sélectionnez **1** dans le champ **Multiples**. Les numéros sont ensuite arrondis jusqu'à une quantité divisible par 1.

### <a name="measurement"></a>Mesure

En général, vous sélectionnez **Mesure** comme mécanisme d'arrondi lorsque la matière première a des dimensions spécifiques. Par exemple, un tube métallique de 2 mètres est requis pour fabriquer un produit fini, et le tube en métal est disponible en longueur de 4,5 mètres. Dans ce cas, le mécanisme d'arrondi **Mesure** peut être utilisé pour calculer le nombre de tubes métalliques nécessaires pour fabriquer une quantité spécifique de produits finis. Pour cet exemple, le champ **Formule** est défini sur **Hauteur \* Constante**. Le champ **Hauteur** est défini sur **2** pour indiquer la longueur du tube requise pour obtenir le produit fini. Le champ **Multiple** est défini sur **4,5** pour indiquer que le tube est disponible dans une longueur de 4,5 mètres. Voici le calcul :

1.  Nombre de multiples nécessaires pour 10 pièces de produits finis : 10 ÷ 2 = 5 pièces
2.  Consommation totale : 4,5 × 5 = 22,5 mètres de tube métallique

On suppose que 0,5 mètre de tube est mis au rebut pour chaque lot de 5 pièces de tube consommées.

### <a name="consumption"></a>Consommation

En général, vous sélectionnez**Consommation** comme mécanisme d'arrondi lorsque la matière première doit être prélevée selon des quantités d'une unité de manutention spécifique du produit. Par exemple, 2 litres de peinture sont utilisés pour produire une pièce de produit fini, et la peinture est prélevée par boîtes de 25 l. Dans ce cas, le mécanisme d'arrondi **Consommation** peut être utilisé pour arrondir la consommation de la totalité des boîtes de 25 l. Voici le calcul de la quantité de peinture requise si 180 pièces de produits finis doivent être fabriquées :

1.  Peinture requise, hormis mise au rebut : 180 × 2 = 360 litres
2.  Nombre de boîtes : 360 ÷ 25 = 14,4, qui est arrondi à 15
3.  Peinture requise, mise au rebut incluse : 15 × 25 = 375 litres

## <a name="step-consumption"></a>Consommation de l'étape
L'option Consommation de l'étape est utilisée pour calculer la consommation constante selon des intervalles de quantité. Si vous sélectionnez **Consommation de l'étape** dans le champ **Formule** sous l'onglet **Paramétrage**, vous pouvez ajouter des informations sur les étapes sous l'onglet **Consommation de l'étape**. La quantité consommée fixe peut être paramétrée selon des intervalles de quantité produite. Par exemple, la consommation de l'étape est paramétrée comme indiqué dans le tableau suivant.

| Série de départ | Quantité |
|-------------|----------|
| 0,00        | 10,0000  |
| 100,00      | 20,0000  |
| 200,00      | 40,0000  |

La quantité de la nomenclature est de 1, et la quantité de la production est de 110. La formule de la consommation est Série de départ (Quantité) = Consommation. Étant donné que la quantité de production est de 110, elle passe dans la « Série de départ 100 ». Par conséquent, la quantité est 20.




