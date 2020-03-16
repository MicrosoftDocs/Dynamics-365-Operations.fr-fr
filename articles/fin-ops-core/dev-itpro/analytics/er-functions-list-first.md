---
title: Fonction FIRST ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction FIRST États électroniques (ER).
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042088"
---
# <a name="FIRST">Fonction FIRST ER</a>

[!include [banner](../includes/banner.md)]

La fonction `FIRST` renvoie le premier enregistrement de la liste spécifiée sous la forme d'une valeur de *Conteneur (enregistrement)*, si cette liste n'est pas vide. Si la liste est vide, cette fonction lève une exception.

## <a name="syntax"></a>Syntaxe

```vb
FIRST (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d'enregistrements*

Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l'enregistrement résultante.

## <a name="example-1"></a>Exemple 1

L'expression `FIRST(SPLIT("ABC",1)).Value` renvoie la valeur texte **« A »**.

## <a name="example-2"></a>Exemple 2

L'expression `FIRST(SPLIT("",1)).Value` lève une exception lors de l'exécution.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
