---
title: Fonction JSONVALUE ER
description: Cet article fournit des informations sur l’utilisation de la fonction JSONVALUE États électroniques (ER).
author: NickSelin
ms.date: 10/25/2021
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
ms.openlocfilehash: 7deaed83959f033d11333efb5a2b398cbe57076d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909498"
---
# <a name="jsonvalue-er-function"></a>Fonction JSONVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `JSONVALUE` analyse les données au format JavaScript Object Notation (JSON) qui sont accessibles au chemin d’accès spécifié et extrait une valeur scalaire avec l’ID spécifié. Elle renvoie ensuite la valeur scalaire extraite sous forme de valeur de *Chaîne*.

## <a name="syntax"></a>Syntaxe

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Chemin d’accès valide d’une source de données du type *Chaîne* contenant des données JSON.

`path` : *Chaîne*

Identificateur d’une valeur scalaire de données JSON. Utilisez une barre oblique inverse (/) pour séparer les noms des nœuds JSON associés. Utilisez des crochets (\[\]) pour spécifier l’index d’une valeur particulière dans un tableau JSON. Notez que la numérotation de base zéro est utilisée pour cet index.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example-1"></a>Exemple 1

La source de données **$JsonField** contient les données suivantes au format JSON : **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. Dans ce cas, l’expression `JSONVALUE (JsonField, "BuildNumber")` renvoie la valeur suivante de type de données *Chaîne* : **"7.3.1234.1"**.

## <a name="example-2"></a>Exemple 2

La source de données **JsonField** du type *Champ calculé* contient l’expression suivante : `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`.

Cette expression est configurée pour retourner une valeur [*Chaîne*](er-formula-supported-data-types-primitive.md#string) qui représente les données suivantes au format JSON.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

Dans ce cas, l’expression `JSONVALUE(json, "workers/[1]/emails/[0]")` renvoie la valeur suivante de type de données *Chaîne* : `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
