---
title: Fonction CH_BANK_MOD_10 ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction CH_BANK_MOD_10 États électroniques (ER).
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
ms.openlocfilehash: 21942fa47b968fa10bfc9b07f269d44e495139fe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564838"
---
# <a name="ch_bank_mod_10-er-function"></a>Fonction CH_BANK_MOD_10 ER

[!include [banner](../includes/banner.md)]

La fonction `CH_BANK_MOD_10` renvoie une valeur *Chaîne* qui représente une référence de créancier en tant qu’expression MOD10, sur la base des chiffres du numéro de facture spécifié.

## <a name="syntax"></a>Syntaxe

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a>Arguments

`invoice number digits` : *Chaîne*

Valeur de texte qui représente les chiffres d’un numéro de facture.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="example"></a>Exemple

`CH_BANK_MOD_10 ("VEND-200002")` renvoie **3**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]