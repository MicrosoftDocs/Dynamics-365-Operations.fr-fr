---
title: Fonction LISTJOIN ER
description: Cet article fournit des informations sur l’utilisation de la fonction LISTJOIN États électroniques (ER).
author: NickSelin
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba7b4b52f5403232d3a32a6b2907c20de29c80d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877123"
---
# <a name="listjoin-er-function"></a>Fonction LISTJOIN ER

[!include [banner](../includes/banner.md)]

La fonction `LISTJOIN` renvoie une valeur *Liste des enregistrements* qui représente une nouvelle liste d’enregistrements créée à partir des arguments spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Arguments

`list 1` : *Liste d’enregistrements*

Référence à une source de données du type de données *Liste d’enregistrements*. Cet argument est obligatoire.

`list N` : *Liste d’enregistrements*

Référence à une source de données du type de données *Liste d’enregistrements*. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.

## <a name="example"></a>Exemple

Vous entrez une source de données **Enregistrement 1** du type `Container`. Cette source de données contient les champs imbriqués suivants du type `Calculated field` :

- **Code** : Ce champ contient une expression qui renvoie une valeur de type `String`.
- **Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.

Vous entrez ensuite une source de données **Enregistrement 2** du type `Container`. Cette source de données contient les champs imbriqués suivants du type `Calculated field` :

- **Montant** : Ce champ contient une expression qui renvoie une valeur de type `Real`.
- **IsValid** : Ce champ contient une expression qui renvoie une valeur de type `Boolean`.

![Page du concepteur de mise en correspondance des modèles ER.](./media/er-functions-list-listjoin-image1.gif)

Dans ce cas, l’expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` renvoie une nouvelle liste qui contient deux enregistrements.

![Page de concepteur de mappage de modèle ER avec deux enregistrements.](./media/er-functions-list-listjoin-image2.gif)

La structure de cette liste se compose d’un seul champ **Montant** de type `Real`, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.

![Champ Montant de la page du concepteur de mise en correspondance des modèles ER.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)

[Déboguer les sources de données d’un format ER exécuté pour analyser le flux de données et la transformation](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
