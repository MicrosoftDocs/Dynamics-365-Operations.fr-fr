---
title: Fonction ER ENDSWITH
description: Cet article fournit des informations sur l’utilisation de la fonction ENDSWITH États électroniques (ER).
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 2608593238e5b2f738b452fb042837238f17e44e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271611"
---
# <a name="endswith-er-function"></a>Fonction ER ENDSWITH

[!include [banner](../includes/banner.md)]

La fonction `ENDSWITH` détermine si l’entrée spécifiée se termine par le texte spécifié. Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée se termine par le texte spécifié. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Le chemin valide d’un élément d’une source de données du type *Chaîne* ou d’une constante de chaîne, dont la valeur peut se terminer par le deuxième argument.

`start text` : *Chaîne*

Le chemin valide d’une source de données du type de données *Chaîne* ou d’une constante de chaîne, dont la valeur peut être à la fin du premier argument.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction peut être utilisée pour spécifier une expression de condition de la fonction [FILTER](er-functions-list-filter.md) uniquement lorsque le mappage approprié est configuré dans [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) accéder [Microsoft Dataverse](/power-platform/admin/data-integrator). Sinon, une exception est levée au moment de la conception. Le message que vous recevez vous recommande d’utiliser la fonction [WHERE](er-functions-list-where.md) au lieu de la fonction `FILTER`.

## <a name="example-1"></a>Exemple 1

L’expression `ENDSWITH ("abc", "d")` renvoie **FALSE**, alors que l’expression `ENDSWITH ("abc", "C")` renvoie **TRUE**.

## <a name="example-2"></a>Exemple 2

L’expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` renvoie **TRUE** si la valeur du champ **Adresse** de la source de données **modèle** se termine par la chaîne **USA**. Sinon, elle renvoie la valeur **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)
