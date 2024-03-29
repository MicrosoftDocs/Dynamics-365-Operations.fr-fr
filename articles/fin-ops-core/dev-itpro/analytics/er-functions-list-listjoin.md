---
title: Fonction LISTJOIN ER
description: Cet article fournit des informations sur l’utilisation de la fonction LISTJOIN États électroniques (ER).
author: kfend
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ec8a5985277de8036ec8ad51b947a8bab098a1c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291202"
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
