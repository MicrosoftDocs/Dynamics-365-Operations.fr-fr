---
title: Fonction COUNT ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction COUNT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 72d2ea1b26c295c97575a3c7a479ee4e06762424
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042203"
---
# <a name="COUNT">Fonction COUNT ER</a>

[!include [banner](../includes/banner.md)]

La fonction `COUNT` renvoie une valeur *Entier* qui représente le nombre d'enregistrements dans la liste spécifiée, si la liste n'est pas vide. Si la liste est vide, cette fonction renvoie **0** (zéro).

## <a name="syntax"></a>Syntaxe

```vb
COUNT (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d'enregistrements*

Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Entier*

Valeur numérique résultante.

## <a name="example"></a>Exemple

`COUNT (SPLIT("abcd" , 3))` renvoie **2**, parce que la fonction `SPLIT` utilisée dans cet exemple crée une liste composée de deux enregistrements.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
