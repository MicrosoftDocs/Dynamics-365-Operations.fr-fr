---
title: Fonction NULLDATETIME ER
description: Cet article fournit des informations sur l’utilisation de la fonction NULLDATETIME États électroniques (ER).
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
ms.openlocfilehash: 49b75a6cc1e2c1eee926ed8a235ae886d781ad3c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287276"
---
# <a name="nulldatetime-er-function"></a>Fonction NULLDATETIME ER

[!include [banner](../includes/banner.md)]

La fonction `NULLDATETIME` renvoie une valeur de *DateTime* qui représente la valeur de date/heure **null** (1er janvier 1900) en temps universel coordonné (heure moyenne de Greenwich \[GMT\]).

## <a name="syntax"></a>Syntaxe

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Valeurs de retour

*Date et heure*

Valeur de date/heure résultante.

## <a name="example"></a>Exemple

`DATETIMEFORMAT( NULLDATETIME(), "O")` renvoie la valeur de chaîne **1900-01-01T00:00:00.0000000+00:00** lorsqu’il est appelé lors d’un processus qui a été lancé par un utilisateur d’application qui a la valeur de fuseau horaire **(GMT) Temps universel coordonné** dans la section **Préférences de langue et paramètres locaux**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de date et d’heure](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
