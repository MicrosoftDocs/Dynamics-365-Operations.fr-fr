---
title: Fonction NUMERALSTOTEXT ER
description: Cet article fournit des informations sur l’utilisation de la fonction NUMERALSTOTEXT États électroniques (ER).
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
ms.openlocfilehash: 172693583699edfad7deeb16f8fc081abb6119d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287986"
---
# <a name="numeralstotext-er-function"></a>Fonction NUMERALSTOTEXT ER

[!include [banner](../includes/banner.md)]

La fonction `NUMERALSTOTEXT` renvoie le nombre spécifié sous la forme *Chaîne* après avoir été épelée (c’est-à-dire convertie en chaînes de texte) dans la langue spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Arguments

`number` : *Entier* ou *Réel*

Valeur numérique qui spécifie le numéro qui doit être épelé.

`language` : *Chaîne*

Valeur *Chaîne* qui représente le code langue.

`currency` : *Chaîne*

Valeur *Chaîne* qui représente le code devise.

`print currency name flag` : *Booléen*

Valeur *Booléenne* qui indique si un nom de devise doit être ajouté au texte épelé.

`decimal points` : *Entier*

Valeur *Entier* qui indique le nombre de décimales que doit contenir le texte épelé.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Le code langue est facultatif. S’il est défini comme une chaîne vide, le code langue du contexte d’exécution est utilisé. Le code langue par défaut est **EN-US**. Le code langue pour le contexte en cours d’exécution est défini dans un élément **Dossier** ou **Fichier** du format d’états électroniques (ER) en cours d’exécution.

Le code devise est facultatif. S’il est défini comme une chaîne vide, la devis d’entreprise du contexte d’exécution est utilisé.

> [!NOTE] 
> Les arguments `print currency name flag` et `decimal points` sont analysés pour les codes de langue suivants uniquement : **CS**, **ET**, **HU**, **LT**, **LV**, **PL** et **RU**. En outre, l’arguments `print currency name flag` est analysé uniquement pour les sociétés où le contexte du pays ou de la région prend en charge la déclinaison des noms de devise.

## <a name="example-1"></a>Exemple 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` renvoie **"Mille deux cent trente-quatre et 56"**.

## <a name="example-2"></a>Exemple 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` renvoie **"Sto dwadzieścia"**. 

## <a name="example-3"></a>Exemple 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` renvoie **"Сто двадцать евро 21 евроцент"**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
