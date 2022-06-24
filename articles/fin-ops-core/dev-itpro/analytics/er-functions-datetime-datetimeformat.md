---
title: Fonction DATETIMEFORMAT ER
description: Cet article fournit des informations sur l’utilisation de la fonction DATETIMEFORMAT États électroniques (ER).
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 693ec465b56a1c7fbd9828c9e972da8a3e3fc6d4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896790"
---
# <a name="datetimeformat-er-function"></a>Fonction DATETIMEFORMAT ER

[!include [banner](../includes/banner.md)]

La fonction `DATETIMEFORMAT` renvoie une valeur de *[Chaîne](er-formula-supported-data-types-primitive.md#string)* qui présente une valeur de date/heure donnée dans le format spécifié et dans une [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) éventuellement spécifiée. Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Syntaxe 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Arguments

`datetime`: *[DateHeure](er-formula-supported-data-types-primitive.md#datetime)*

Valeur de date/heure qui représente la date et l’heure à mettre en forme.

`format` : *Chaîne*

Format de la chaîne de sortie. Pour plus d’informations sur les formats pris en charge, consultez [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) et [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> La chaîne de format est sensible à la casse lorsque vous utilisez un format standard ou un format personnalisé. Par exemple, le spécificateur de format [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) « d »renvoie la date à l’aide du schéma de date courte, tandis que le spécificateur de format standard « D » renvoie la date à l’aide du schéma de date longue. De plus, le spécificateur de format [personnalisé](/dotnet/standard/base-types/custom-date-and-time-format-strings) « M » renvoie le mois de 1 à 12, tandis que le spécificateur de format personnalisé « m » renvoie les minutes de 0 à 59.

`culture` : *Chaîne*

Culture à utiliser pour la mise en forme. Pour plus d’informations sur les cultures prises en charge, voir [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de la chaîne résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si la culture n’est pas définie comme un argument de la fonction appelée, la valeur de `culture` est définie par le contexte d’appel. Par exemple, si la fonction `DATETIMEFORMAT` est appelée en utilisant la syntaxe 1 dans un format d’états électroniques (ER) pour un élément **FILE** configuré pour utiliser la culture allemande, la conversion se fera en utilisant la culture allemande. La valeur `culture` par défaut est **EN-US**.

Quand la fonction `DATETIMEFORMAT` convertit une valeur de date/heure donnée, elle considère le paramètre de fuseau horaire de l’utilisateur de l’application qui exécute le format ER que la fonction est appelée dans le contexte.

## <a name="example-1"></a>Exemple 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` renvoie la valeur de date/heure du serveur d’applications actuelle, 24 décembre 2015, sous la forme **« 24-12-2015 »**, en fonction du format personnalisé spécifié.

## <a name="example-2"></a>Exemple 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` renvoie la valeur de date/heure de la session de l’application actuelle, 24 décembre 2015, sous la forme de **« 24.12.2015 »**, en fonction de la culture allemande et du format sélectionnés spécifiés.

## <a name="example-3"></a>Exemple 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` renvoie la valeur de chaîne **2019-11-12T08:00:00.0000000-08:00** lorsqu’il est appelé lors d’un processus qui a été lancé par un utilisateur d’application qui a la valeur de fuseau horaire **(GMT-08:00) Heure du Pacifique (États-Unis et Canada)** dans la section **Préférences de langue et paramètres locaux**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
