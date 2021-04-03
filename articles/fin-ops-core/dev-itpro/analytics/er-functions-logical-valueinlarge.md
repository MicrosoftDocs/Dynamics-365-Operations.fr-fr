---
title: Fonctions VALUEINLARGE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction VALUEINLARGE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 1e35c695d697e0d0f42baeaf568548273f9d205b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565806"
---
# <a name="valueinlarge-er-function"></a>Fonctions VALUEINLARGE ER

[!include [banner](../includes/banner.md)]

La fonction `VALUEINLARGE` détermine si l’entrée spécifiée de type *Int64* ou *Entier* correspond à une valeur quelconque d’un article donné dans la liste spécifiée. La fonction renvoie une *Booléenne* de **TRUE** si l’entrée spécifiée correspond au résultat de l’exécution de l’expression spécifiée pour au moins un enregistrement de la liste spécifiée. Sinon, elle renvoie une valeur *Booléenne* de **FALSE**. Pour comprendre la différence avec la fonction `VALUEIN`, voir la section [Note d’utilisation](#usage_note) plus loin dans cette rubrique.

## <a name="syntax"></a>Syntaxe

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Arguments

`input` : *Champ*

Chemin d’accès valide d’un élément de la source de données du type *Liste d’enregistrements*. La valeur de cet article est mise en correspondance.

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`list item expression` : *Expression*

Expression conditionnelle valide qui indique ou contient un champ unique de la liste spécifiée à utiliser pour la mise en correspondance.

## <a name="return-values"></a>Valeurs de retour

*Booléen*

Valeur *Booléenne* résultante.

## <a name=""></a><a name="usage_note">Notes d’utilisation</a>

Lorsque l’entrée spécifiée représente un type d’un élément de la source de données *Int64* ou *Entier* dont l’appel est traduisible en instruction SQL directe, la liste spécifiée est convertie en table SQL temporaire et la mise en correspondance est effectuée dans la base de données en exécutant une seule requête `EXISTS JOIN`. Sinon, cette fonction fonctionne comme la fonction [`VALUEIN`](er-functions-logical-valuein.md).

Lorsque l’entrée spécifiée représente un élément de source de données conçu comme un élément autre que de type *Int64* et *Entier*, une erreur se produit au moment de la conception pour vous informer que la fonction `VALUEINLARGE` n’est pas applicable pour l’expression ER configurée.

Quand l’expression de la fonction `VALUEINLARGE` est exécutée et que plus d’une table temporaire est utilisée dans le cadre de cette exécution, une erreur d’exécution se produit.

## <a name="example"></a>Exemple

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **In** du type *Enregistrements de la table*.
    - Cette source de données fait référence à la table **Déclaration d’échanges de biens**.
    - L’option **Intersociétés** est définie sur **Non**.
- Source de données **InMemory** du type *Champ calculé*.
    - Cette source de données contient l’expression `WHERE (In, In.Port <> "")`.
- Source de données **InFiltered** du type *Champ calculé*.
    - Cette source de données contient l’expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.

Lorsque la source de données **InFiltered** est appelée dans le contexte de l’entreprise **DEMF**, une table temporaire est créée dans la base de données de l’application, la liste des codes d’identification d’enregistrement collectée en mémoire est insérée dans cette table et l’instruction SQL suivante est générée pour renvoyer les enregistrements filtrés de la table **Déclaration d’échanges de biens**.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions logiques](er-functions-category-logical.md)

[Fonction VALUEIN](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]