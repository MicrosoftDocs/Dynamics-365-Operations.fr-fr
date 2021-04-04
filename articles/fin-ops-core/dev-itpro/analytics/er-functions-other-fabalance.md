---
title: Fonction FA_BALANCE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FA_BALANCE États électroniques (ER).
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
ms.openlocfilehash: 37c440a5c626016ebdb75703a2be63c9a1a2b560
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567590"
---
# <a name="fa_balance-er-function"></a>Fonction FA_BALANCE ER

[!include [banner](../includes/banner.md)]

La fonction `FA_BALANCE` renvoie une valeur de *Conteneur (enregistrement)* constituée des données relatives au solde des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur, l’année de déclaration et la date de déclaration.

## <a name="syntax"></a>Syntaxe

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Arguments

`fixed asset code` : *Chaîne*

Valeur de *Chaîne* qui représente le code d’un élément d’immobilisation pour lequel le solde est calculé.

`value model code` : *Chaîne*

Valeur de *Chaîne* qui représente le code d’un modèle de valeur pour lequel le solde est calculé.

`reporting year` : *Valeur d’énumération*

Valeur d’énumération de l’énumération d’application **AssetYear** qui définit une période pour le calcul du solde.

`reporting date` : *Date*

Valeur de *Date* qui définit une date pour le calcul du solde.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="example"></a>Exemple

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` renvoie le conteneur de données des soldes de l’immobilisation **COMP-000001** préparé pour le modèle de valeur **Current** à la date de la session de l’application actuelle.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]