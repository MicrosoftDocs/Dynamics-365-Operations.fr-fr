---
title: Fonction CASE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CASE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69b76a06bcd3ba002d9543447e60afa14d5a6ce6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687024"
---
# <a name="case-er-function"></a>Fonction CASE ER

[!include [banner](../includes/banner.md)]

La fonction `CASE` évalue la valeur de l’expression spécifiée par rapport aux options alternatives spécifiées et renvoie le résultat de la première option qui est égale à la valeur de l’expression spécifiée. Sinon, elle renvoie le résultat par défaut facultatif, si un résultat par défaut est spécifié comme dernier argument de la fonction appelée qui n’est pas précédé d’une option. La valeur renvoyée peut être une valeur de n’importe quel type de données pris en charge.

## <a name="syntax"></a>Syntaxe

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Arguments

`expression` : *Type de données primitif* (Booléen, numérique ou texte)

Expression valide qui renvoie une valeur du type de données primitif.

`option 1` : *Type de données primitif* (Booléen, numérique ou texte)

Expression valide qui renvoie une valeur du même type de données primitif que l’argument `expression` de la fonction appelée. Cet argument est obligatoire.

`result 1` : *N’importe lequel des types de données pris en charge*

Résultat renvoyé qui correspond à l’option précédente. Cet argument est obligatoire.

`option N` : *Type de données primitif* (Booléen, numérique ou texte)

Expression valide qui renvoie une valeur du même type de données primitif que l’argument `expression` de la fonction appelée. Cet argument est facultatif.

`result N` : *N’importe lequel des types de données pris en charge*

Résultat renvoyé qui correspond à l’option précédente. Cet argument est facultatif.

`default result` : *N’importe lequel des types de données pris en charge*

Résultat qui doit être renvoyé s’il n’y a pas de correspondance. Cet argument est facultatif.

## <a name="return-values"></a>Valeurs de retour

*N’importe lequel des types de données pris en charge*

Valeur résultante de l’un des types de données pris en charge.

## <a name="usage-notes"></a>Notes d’utilisation

Une exception est levée au moment de l’exécution s’il n’y a pas de correspondance et qu’un résultat par défaut facultatif n’est pas défini.

Tous les résultats doivent être spécifiés en utilisant le même type de données. Une exception est levée au moment de la conception si les types de données des résultats configurés ne correspondent pas.

Si la première valeur de résultat et la *N* ième valeur de résultat sont des valeurs de type de données *Conteneur (enregistrement)* ou *Liste des enregistrements*, le résultat n’a que les champs qui existent dans les deux valeurs.

## <a name="example"></a>Exemple

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` renvoie la chaîne **"HIVER"** si la date de la session de l’application actuelle se situe entre octobre et décembre. Sinon, elle renvoie une chaîne vide.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]