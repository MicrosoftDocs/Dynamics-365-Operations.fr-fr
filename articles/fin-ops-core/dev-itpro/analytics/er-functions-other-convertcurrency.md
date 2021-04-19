---
title: Fonction CONVERTCURRENCY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CONVERTCURRENCY États électroniques (ER).
author: NickSelin
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
ms.openlocfilehash: fb8f7f28f5a9bb27402544efcffa6393238e38d8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744365"
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