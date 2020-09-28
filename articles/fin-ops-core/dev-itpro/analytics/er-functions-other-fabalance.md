---
title: Fonction FA_BALANCE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FA_BALANCE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a969e3a484208388fd82d7a714bee27b7fe64a9
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744165"
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
