---
title: Fonction TRIM ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction TRIM États électroniques (ER).
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 816f6d6623bb778c9186d294c9b67db7edddd671
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367790"
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
