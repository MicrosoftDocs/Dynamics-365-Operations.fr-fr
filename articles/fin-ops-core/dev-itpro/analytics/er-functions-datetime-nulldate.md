---
title: Fonction NULLDATE ER
description: Cet article fournit des informations sur l’utilisation de la fonction NULLDATE États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 7d1f0535796da096253dbd3ed55e9407cc9150f4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870404"
---
# <a name="nulldate-er-function"></a>Fonction NULLDATE ER

[!include [banner](../includes/banner.md)]

La fonction `NULLDATE` renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900).

## <a name="syntax"></a>Syntaxe

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Valeurs de retour

*date ;*

Valeur de date résultante.

## <a name="example-1"></a>Exemple 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` renvoie la date **null**, 1er janvier 1900, comme **« 1900-01-01 »**, basé sur le format personnalisé spécifié.

## <a name="example-2"></a>Exemple 2

L’expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` renvoie **True** lorsque la valeur du champ **Date du document** est égale à la date **null**. Dans cet exemple, **Facture** est une source de données d’états électroniques (ER) de type **Enregistrements Finance/Table** qui fait référence à la table CustInvoiceJour.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]