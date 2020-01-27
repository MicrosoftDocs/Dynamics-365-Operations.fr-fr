---
title: Fonction LISTOFFIRSTITEM ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LISTOFFIRSTITEM États électroniques (ER).
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
ms.openlocfilehash: 4d985ef5015bc104a83260b64418821cc715e8cb
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917256"
---
# <a name="LISTOFFIRSTITEM">Fonction LISTOFFIRSTITEM ER</a>

[!include [banner](../includes/banner.md)]

La fonction `LISTOFFIRSTITEM` renvoie une valeur *Liste des enregistrements* constituée uniquement du premier enregistrement de la liste spécifiée.

## <a name="syntax"></a>Syntaxe

```
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d'enregistrements*

Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Liste d'enregistrements*

Liste des enregistrements résultante.

## <a name="example"></a>Exemple

L'expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` renvoie la valeur texte **« A »**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
