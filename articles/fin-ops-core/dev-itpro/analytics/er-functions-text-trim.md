---
title: Fonction TRIM ER
description: Cet article fournit des informations sur l’utilisation de la fonction TRIM États électroniques (ER).
author: kfend
ms.date: 02/28/2022
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
ms.openlocfilehash: 95b8d2989d705c4998da0af8e683adf567edfe92
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273096"
---
# <a name="trim-er-function"></a>Fonction TRIM ER

[!include [banner](../includes/banner.md)]

La fonction `TRIM` renvoie la chaîne de texte spécifiée sous forme de *Chaîne* après la tabulation, le retour chariot, le saut de ligne et le saut de page ont été remplacés par un seul caractère d’espacement, après que les espaces de début et de fin ont été tronqués et après que plusieurs espaces entre les mots ont été supprimés.

## <a name="syntax"></a>Syntaxe

```vb
TRIM (text)
```

## <a name="arguments"></a>Arguments

`text` : *Chaîne*

Chemin d’accès valide d’une source de données du type *Chaîne*.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Dans certains cas, vous souhaiterez peut-être tronquer les espaces de début et de fin, mais préférez conserver la mise en forme du texte spécifié. Par exemple, lorsque ce texte représente une adresse qui peut être saisie dans la zone de texte multiligne et peut contenir une mise en forme de saut de ligne et de retour chariot. Dans ce cas, utilisez l’expression suivante : `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` où `text` est l’argument qui fait référence à la chaîne de texte spécifiée.

## <a name="example-1"></a>Exemple 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` renvoie **« Exemple de texte »**.

## <a name="example-2"></a>Exemple 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` renvoie **« Exemple de texte »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de texte](er-functions-category-text.md)

[Fonction REPLACE ER](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
