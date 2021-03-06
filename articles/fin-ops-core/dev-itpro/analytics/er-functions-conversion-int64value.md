---
title: Fonction INT64VALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction INT64VALUE États électroniques (ER).
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 89a26e867579bcb34a9bae33fa0b98e1ecfe9995
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755394"
---
# <a name="int64value-er-function"></a>Fonction INT64VALUE ER

[!include [banner](../includes/banner.md)]

La fonction `INT64VALUE` renvoie une valeur *Int64* qui représente la chaîne spécifiée.

## <a name="syntax-1"></a>Syntaxe 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui doit être convertie en nombre *Int64*.

`number` : *Réel* ou *Entier*

Valeur *Réel* ou *Entier* numérique qui doit être convertie en nombre *Int64*.

## <a name="return-values"></a>Valeurs de retour

*Int64*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Les décimales sont tronquées.

## <a name="example-1"></a>Exemple 1

`INT64VALUE ("22565422744")` renvoie la valeur *Int64* **22565422744**.

## <a name="example-2"></a>Exemple 2

`INT64VALUE ( VALUE("22565422744.77"))` renvoie la valeur *Int64* **22565422744**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de conversion des types](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]