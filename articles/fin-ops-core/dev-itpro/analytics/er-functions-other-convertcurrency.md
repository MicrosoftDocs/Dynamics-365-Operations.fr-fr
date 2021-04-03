---
title: Fonction CONVERTCURRENCY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CONVERTCURRENCY États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 0f0d5bace9b62cf6f0d7576744a6cc271666bf73
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567638"
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