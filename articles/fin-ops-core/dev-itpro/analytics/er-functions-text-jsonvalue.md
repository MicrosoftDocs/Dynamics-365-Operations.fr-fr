---
title: Fonction JSONVALUE ER
description: Cet article fournit des informations sur l’utilisation de la fonction JSONVALUE États électroniques (ER).
author: kfend
ms.date: 10/25/2021
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
ms.openlocfilehash: fba1141bce91fd7c9da3cd21aef13ce99329f379
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267961"
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
