---
title: Fonction LISTJOIN ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction LISTJOIN États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249033"
---
# <a name=""></a><a name="LISTJOIN">Fonction LISTJOIN ER</a>

[!include [banner](../includes/banner.md)]

La fonction `LISTJOIN` renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste d'enregistrements créée à partir des arguments spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Arguments

`list 1` : *Liste d'enregistrements*

Référence à une source de données du type de données *Liste d'enregistrements*. Cet argument est obligatoire.

`list N` : *Liste d'enregistrements*

Référence à une source de données du type de données *Liste d'enregistrements*. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Liste d'enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d'utilisation

La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.

## <a name="example"></a>Exemple

Vous entrez une source de données **Enregistrement 1** du type `Container`. Cette source de données contient les champs imbriqués suivants du type `Calculated field` :

- **Code** : Ce champ contient une expression qui renvoie une valeur de type `String`.
- **Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.

Vous entrez ensuite une source de données **Enregistrement 2** du type `Container`. Cette source de données contient les champs imbriqués suivants du type `Calculated field` :

- **Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.
- **IsValid** : Ce champ contient une expression qui renvoie une valeur de type `Boolean`.

Dans ce cas, l'expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` renvoie une nouvelle liste qui contient deux enregistrements. La structure de cette liste se compose d'un seul champ **Montant** de type `Real`, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)
