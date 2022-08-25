---
title: Fonction TEXT ER
description: Cet article fournit des informations sur l’utilisation de la fonction TEXT États électroniques (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: a32da5588c5231b20bc8166d20888c1611ca273e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278854"
---
# <a name="text-er-function"></a>Fonction TEXT ER

[!include [banner](../includes/banner.md)]

La fonction `TEXT` renvoie le nombre spécifié comme valeur de *Chaîne* une fois qu’elle a été convertie en une chaîne de texte qui est mise en forme en fonction des paramètres régionaux du serveur de l’instance d’application actuelle.

## <a name="syntax"></a>Syntaxe

```vb
TEXT (number)
```

## <a name="arguments"></a>Arguments

`number` : *Entier* ou *Réel*

Nombre qui doit être converti en chaîne de texte.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Pour les valeurs de type *Réel*, la conversion de chaîne est limitée à deux décimales.

## <a name="example"></a>Exemple

Si les paramètres régionaux du serveur de l’instance Microsoft Dynamics 365 Finance sont définis comme **EN-US**, `TEXT (NOW ())` renvoie la date de la session de Finance actuelle, 17 décembre 2015, comme chaîne de texte **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` renvoie **« 0.33 »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
