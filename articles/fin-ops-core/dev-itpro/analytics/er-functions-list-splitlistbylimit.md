---
title: Fonction SPLITLISTBYLIMIT ER
description: Cet article fournit des informations sur l’utilisation de la fonction SPLITLISTBYLIMIT États électroniques (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: d43ca9bd33cf21a0d72e407317088c9703bbf303
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271671"
---
# <a name="splitlistbylimit-er-function"></a>Fonction SPLITLISTBYLIMIT ER

[!include [banner](../includes/banner.md)]

La fonction `SPLITLISTBYLIMIT` fractionne la liste spécifiée en une nouvelle liste de sous-listes (lots). Le nombre d’enregistrements dans chaque lot est calculé dynamiquement. La fonction renvoie ensuite le résultat en tant que nouvelle valeur de *Liste des enregistrements* constituée des lots.

## <a name="syntax"></a>Syntaxe

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`limit value` : *Entier* ou *Réel*

Valeur maximale de la limite utilisée pour fractionner la liste d’origine en lots.

`limit source` : *Champ*

Chemin d’accès valide d’un champ de type *Entier* ou *Réel* dans la liste spécifiée. La valeur de ce champ définit l’étape à laquelle la somme totale est augmentée.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La liste des traitements par lots renvoyée contient les éléments suivants :

- **Valeur** : *liste*

    Liste des enregistrements qui appartiennent au lot en cours.

- **Numéro de lot** : *Entier*

    Numéro du lot actuel dans la liste renvoyée.

La limite n’est pas appliquée à un article unique de la liste d’origine si la source de limite dépasse la limite définie.

## <a name="example"></a>Exemple

L’illustration suivante présente un format d’états électroniques (ER).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

L’illustration suivante présente les sources de données utilisées pour le format.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

L’illustration suivante présente le résultat de l’exécution du format. Dans ce cas, la sortie est une liste plate des articles de marchandise.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

Dans les illustrations suivantes, le même format a été ajusté de manière à présenter la liste des articles de marchandise par lots lorsqu’un seul lot doit inclure des marchandises et le poids total ne doit pas dépasser une limite de 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

L’illustration suivante présente le résultat de l’exécution du format ajusté.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> La limite n’est pas appliquée au dernier article de la liste d’origine, car la valeur (**11**) de la source de sa limite (**poids**) dépasse la limite définie (**9**). Pour ignorer les sous-listes lors de la génération d’états, utilisez la fonction `WHERE` ou l’expression **Activé** de l’élément de format correspondant, si nécessaire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
