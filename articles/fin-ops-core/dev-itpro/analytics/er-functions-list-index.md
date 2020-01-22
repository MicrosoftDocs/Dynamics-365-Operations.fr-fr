---
title: Fonction INDEX ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction INDEX États électroniques (ER).
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
ms.openlocfilehash: a7fe2cbb5421da3c6dd1d044316b276836c5e5c1
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917302"
---
# <a name="INDEX">Fonction INDEX ER</a>

[!include [banner](../includes/banner.md)]

La fonction `INDEX` renvoie une valeur de *Conteneur (enregistrement)* sélectionnée à l'aide de l'index numérique spécifié dans la liste spécifiée. Si l'index est hors des limites pour les enregistrements dans la liste spécifiée, une exception est levée.

## <a name="syntax"></a>Syntaxe

```
INDEX (list, index)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d'enregistrements*

Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.

`index` : *Entier*

Index numérique qui indique la position de l'enregistrement souhaité dans la liste spécifiée.

## <a name="return-values"></a>Valeurs de retour

*Conteneur (enregistrement)*

Valeur de l'enregistrement résultante.

## <a name="example-1"></a>Exemple 1

Si vous entrez la source de données **DS** de type *Champ calculé*, et qu'elle contient l'expression `SPLIT ("A|B|C", "|")`, l'expression `DS.Value` retourne la valeur de texte **« B »** pour le second enregistrement de cette liste d'enregistrements. L'expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` renvoie aussi la valeur texte **« B »**.

## <a name="example-2"></a>Exemple 2

Si vous entrez une source de données **DS** de type *Champ calculé*, et qu'elle contient l'expression `SPLIT ("A|B|C", "|")`, l'expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lève une exception à l'exécution.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
