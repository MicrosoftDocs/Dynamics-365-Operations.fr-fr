---
title: Fonction TABLENAME2ID ER
description: Cet article fournit des informations sur l’utilisation de la fonction TABLENAME2ID États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: b5deea69d5c43be599ccf02c0344ba8d662a6e0f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886847"
---
# <a name="tablename2id-er-function"></a>Fonction TABLENAME2ID ER

[!include [banner](../includes/banner.md)]

La fonction `TABLENAME2ID` renvoie une représentation numérique de l’ID de table pour le nom de table spécifié en tant que valeur *Entier*.

## <a name="syntax"></a>Syntaxe

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Valeur de texte qui représente un nom de table valide.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="usage-notes"></a>Notes d’utilisation

L’exécution de cette fonction peut avoir des résultats différents dans différentes instances de Microsoft Dynamics 365 Finance, même si le même nom de société est utilisé.

## <a name="example"></a>Exemple

`TABLENAME2ID ("Intrastat")` renvoie **1510**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]