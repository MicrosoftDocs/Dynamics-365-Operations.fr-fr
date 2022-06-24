---
title: Fonction EMPTYRECORD ER
description: Cet article fournit des informations sur l’utilisation de la fonction EMPTYRECORD États électroniques (ER).
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
ms.openlocfilehash: 6f339347187f145b90f14d56017097ff3d7712e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886818"
---
# <a name="emptyrecord-er-function"></a>Fonction EMPTYRECORD ER

[!include [banner](../includes/banner.md)]

La fonction `EMPTYRECORD` renvoie une valeur de *Conteneur (enregistrement)* nulle avec la même structure que la liste d’enregistrements ou de l’enregistrement spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste des enregistrements* ou *Conteneur (enregistrement)*

Chemin d’accès valide d’une source de données de type *Liste des enregistrements* ou *Conteneur (enregistrement)*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="usage-notes"></a>Notes d’utilisation

> [!NOTE] 
> Un enregistrement null est un enregistrement où tous les champs ont une valeur vide. Une valeur vide correspond à **0** (zéro) pour les nombres, à une chaîne vide pour les chaînes, etc.

## <a name="example"></a>Exemple

`EMPTYRECORD (SPLIT ("abc", 1))` renvoie un nouvel enregistrement vide ayant la même structure que la liste qui est renvoyée par la fonction `SPLIT`. Pour plus d’informations, voir [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions d’enregistrement](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]