---
title: Fonction NEWGUID ER
description: Cet article fournit des informations sur l’utilisation de la fonction NEWGUID États électroniques (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 321e2eda4accf9c8fe33b5a4c092c7be55276f26
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861814"
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
