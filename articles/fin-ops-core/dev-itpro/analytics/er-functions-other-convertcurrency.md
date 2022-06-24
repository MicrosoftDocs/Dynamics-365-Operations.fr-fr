---
title: Fonction CONVERTCURRENCY ER
description: Cet article fournit des informations sur l’utilisation de la fonction CONVERTCURRENCY États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: e51086d977652e4be4c19390a824d4f4507b60d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898460"
---
# <a name="convertcurrency-er-function"></a>Fonction CONVERTCURRENCY ER

[!include [banner](../includes/banner.md)]

La fonction `CONVERTCURRENCY` renvoie une valeur de *Réel* qui représente le résultat de la conversion du montant en devises spécifié de la devise source spécifiée dans la devise cible spécifiée à l’aide des paramètres de la société spécifiée à la date spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Arguments

`amount` : *Entier* ou *Réel*

Valeur numérique qui représente le montant en devises qui doit être converti.

`source currency` : *Chaîne*

Code de la devise source.

`target currency` : *Chaîne*

Code de la devise cible.

`date` : *Date*

Valeur de *Date* qui représente la date utilisée pour déterminer le taux de change pour la conversion.

`company` : *Chaîne*

Valeur de *Chaîne* qui représente le code d’une entreprise qui fournit les paramètres utilisés pour la conversion.

## <a name="return-values"></a>Valeurs de retour

*Réel*

Valeur numérique résultante.

## <a name="example"></a>Exemple

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` renvoie l’équivalent d’un euro en dollars US à la date de session actuelle, basée sur les paramètre de la société **DEMF**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]