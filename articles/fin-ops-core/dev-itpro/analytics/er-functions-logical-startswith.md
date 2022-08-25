---
title: Fonction ER STARTSWITH
description: Cet article fournit des informations sur l’utilisation de la fonction STARTSWITH États électroniques (ER).
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
ms.openlocfilehash: 010646d2ab96d9a326ffb01c369726790b6377a6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287216"
---
# <a name="startswith-er-function"></a>Fonction ER STARTSWITH

[!include [banner](../includes/banner.md)]

La fonction `STARTSWITH` détermine si l’entrée spécifiée commence par le texte spécifié. Elle renvoie une valeur *Booléenne* **TRUE** si l’entrée spécifiée commence par le texte spécifié. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**.

## <a name="syntax"></a>Syntaxe

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Le chemin valide d’un élément d’une source de données du type *Chaîne* ou d’une constante de chaîne, dont la valeur peut commencer par le deuxième argument.

`start text` : *Chaîne*

Le chemin valide d’une source de données du type de données *Chaîne* ou d’une constante de chaîne, dont la valeur peut être au début du premier argument.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Cette fonction peut être utilisée pour spécifier une expression de condition de la fonction [FILTER](er-functions-list-filter.md) uniquement lorsque le mappage approprié est configuré dans [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) accéder [Microsoft Dataverse](/power-platform/admin/data-integrator). Sinon, une exception est levée au moment de la conception. Le message que vous recevez vous recommande d’utiliser la fonction [WHERE](er-functions-list-where.md) au lieu de la fonction `FILTER`.

## <a name="example-1"></a>Exemple 1

L’expression `STARTSWITH ("abc", "d")` renvoie **FALSE**, alors que l’expression `STARTSWITH ("abc", "A")` renvoie **TRUE**.

## <a name="example-2"></a>Exemple 2

L’expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` renvoie **TRUE** si la valeur du champ **Adresse** de la source de données **modèle** commence par la chaîne **123 Coffee Street**. Sinon, elle renvoie la valeur **FALSE**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)
