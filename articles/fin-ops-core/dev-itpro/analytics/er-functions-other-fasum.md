---
title: Fonction FA_SUM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FA_SUM États électroniques (ER).
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744293"
---
# <a name="fa_sum-er-function"></a>Fonction FA_SUM ER

[!include [banner](../includes/banner.md)]

La fonction `FA_SUM` renvoie une valeur de *Conteneur (enregistrement)* constituée des données des montants des immobilisations pour l’élément d’immobilisation spécifié, le code du modèle de valeur et la période des dates.

## <a name="syntax"></a>Syntaxe

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Arguments

`fixed asset code` : *Chaîne*

Valeur de *Chaîne* qui représente le code d’un élément d’immobilisation pour lequel le solde est calculé.

`value model code` : *Chaîne*

Valeur de *Chaîne* qui représente le code d’un modèle de valeur pour lequel le solde est calculé.

`start date` : *Date*

Valeur de *Date* qui représente la date de début d’une période pour laquelle les montants des immobilisations sont calculés.

`end date` : *Date*

Valeur de *Date* qui représente la date de fin d’une période pour laquelle les montants des immobilisations sont calculés.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l’enregistrement résultante.

## <a name="example"></a>Exemple

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` renvoie le conteneur de données pour l’immobilisation **COMP-000001** qui a été préparée pour le modèle de valeur **Current** et pour une période de **Date1** à **Date2**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]