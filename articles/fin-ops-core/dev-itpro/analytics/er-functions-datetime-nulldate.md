---
title: Fonction NULLDATE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction NULLDATE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 7761342c6759c11591e06fc7c32f0ddd8bef407a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916313"
---
# <a name="NULLDATE">Fonction NULLDATE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `NULLDATE` renvoie une valeur *Date* qui représente la date **null** (1er janvier 1900).

## <a name="syntax"></a>Syntaxe

```
NULLDATE () as 
```

## <a name="return-values"></a>Valeurs de retour

*date ;*

Valeur de date résultante.

## <a name="example-1"></a>Exemple 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` renvoie la date **null**, 1er janvier 1900, comme **« 1900-01-01 »**, basé sur le format personnalisé spécifié.

## <a name="example-2"></a>Exemple 2

L'expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` renvoie **True** lorsque la valeur du champ **Date du document** est égale à la date **null**. Dans cet exemple, **Facture** est une source de données d'états électroniques (ER) de type **Enregistrements Finance/Table** qui fait référence à la table CustInvoiceJour.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d'heure](er-functions-category-datetime.md)
