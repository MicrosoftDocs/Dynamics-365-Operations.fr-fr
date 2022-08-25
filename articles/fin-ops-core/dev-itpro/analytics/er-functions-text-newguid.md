---
title: Fonction NEWGUID ER
description: Cet article fournit des informations sur l’utilisation de la fonction NEWGUID États électroniques (ER).
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274770"
---
# <a name="newguid-er-function"></a>Fonction NEWGUID ER

[!include [banner](../includes/banner.md)]

La fonction `NEWGUID` génère un nouvel identificateur global unique (GUID) et le renvoie sous la forme d’une valeur *[GUID](er-formula-supported-data-types-primitive.md#guid)*.

## <a name="syntax"></a>Syntaxe

```vb
NEWGUID ()
```

## <a name="return-values"></a>Valeurs de retour

*GUID*

Valeur GUID résultante.

## <a name="example"></a>Exemple

`NEWGUID()` renvoie toujours une nouvelle valeur *GUID*, comme **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
