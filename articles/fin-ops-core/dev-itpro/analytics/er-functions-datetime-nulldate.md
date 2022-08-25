---
title: Fonction NULLDATE ER
description: Cet article fournit des informations sur l’utilisation de la fonction NULLDATE États électroniques (ER).
author: kfend
ms.date: 12/04/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 276ad99303a4e88ecb1c83e9518e06bfd7afaa45
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272650"
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
