---
title: Fonction WHERE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction WHERE États électroniques (ER).
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
ms.openlocfilehash: 392cf7acebd7ad95bcc0f5d4b7a67500a412a795
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041830"
---
# <a name="WHERE">Fonction WHERE ER</a>

[!include [banner](../includes/banner.md)]

La fonction `WHERE` renvoie la liste spécifiée sous la forme d'une *Liste des enregistrements* après avoir été filtrée selon la condition spécifiée.

## <a name="syntax"></a>Syntaxe

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d'enregistrements*

Chemin d'accès valide d'une source de données du type de données *Liste d'enregistrements*.

`condition` : *Booléen*

Expression conditionnelle valide utilisée pour filtrer les enregistrements de la liste spécifiée.

## <a name="return-values"></a>Valeurs de retour

*Liste d'enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d'utilisation

Cette fonction diffère de la fonction [FILTER](er-functions-list-filter.md), car la condition spécifiée est appliquée à toute source de données États électroniques (ER) du type *Liste des enregistrements* présent dans la mémoire.

Si les arguments configurés pour cette fonction (`list` et `condition`) ne permettent pas de traduire cette demande en appel SQL direct, un message d'avertissement est levé au moment de la conception. Ce message informe l'utilisateur que les performances peuvent être améliorées si la fonction [FILTER](er-functions-list-filter.md) est utilisée au lieu de `WHERE`.

## <a name="example-1"></a>Exemple 1

Si **Fournisseur** est configuré comme source de données ER qui fait référence à la table VendTable, l'expression `WHERE (Vendors, Vendors.VendGroup = "40")` renvoie la liste des fournisseurs faisant partie uniquement du groupe de fournisseurs 40.

## <a name="example-2"></a>Exemple 2

Si vous entrez la source de données **DS** de type *Champ calculé*, et qu'elle contient l'expression `SPLIT ("A|B|C", "|")`, l'expression `WHERE( DS, DS.Value = "B")` retourne une liste d'une seul enregistrement qui contient le texte **« B »** dans le champ **Valeur**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
