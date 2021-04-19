---
title: Fonction NUMSEQVALUE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction NUMSEQVALUE États électroniques (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3351360d0c1afca9f828ba4fc935096ddfd67f2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744001"
---
# <a name="numseqvalue-er-function"></a>Fonction NUMSEQVALUE ER

[!include [banner](../includes/banner.md)]

La fonction `NUMSEQVALUE` renvoie une valeur de *Chaîne* qui représente la nouvelle valeur générée d’une souche de numéros, en fonction de la souche de numéros, de l’étendue et de l’ID d’étendue spécifiés. L’ID d’étendue est égal à la société fournie par le contexte sous lequel le format d’états électroniques (ER) est exécuté.

## <a name="syntax-1"></a>Syntaxe 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Syntaxe 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Syntaxe 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Arguments

`number sequence code` : *Chaîne*

Valeur de texte qui représente le code de la souche de numéros dans laquelle une nouvelle valeur est requise.

`number sequence record ID` : *Int64*

Valeur *Int64* qui représente l’ID d’enregistrement d’un enregistrement dans la table NumberSequenceTable qui contient la définition de la souche de numéros dans laquelle une nouvelle valeur est requise.

`scope type` : *Valeur de l’énumération*

Valeur d’énumération de l’énumération **ERExpressionNumberSequenceScopeType** qui définit l’étendue de la souche de numéros dans laquelle une nouvelle valeur est requise. Les types d’étendues disponibles sont **Partagé**, **Entité légale** et **Entreprise**.

`scope ID` : *Chaîne*

Valeur de *Chaîne* qui identifie l’étendue, en fonction du type d’étendue spécifié.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Pour le type d’étendue **Partagé**, spécifiez une chaîne vide comme ID d’étendue.

Pour les types d’étendues **Société** et **Entité juridique**, spécifiez le code société comme ID d’étendue. Si vous spécifiez une chaîne vide comme ID d’étendue pour ces types d’étendues, le code société actuel est utilisé.

Lorsque la syntaxe 1 est utilisée, la souche de numéros est demandée pour le type d’étendue **Entreprise** et le code société est fourni par le contexte dans lequel le format ER est exécuté.

## <a name="example-1"></a>Exemple 1

Dans votre format ER, vous définissez la source de données **AskNumSeq** du type *Paramètre d’entrée utilisateur*. Cette source de données fait référence au type de données étendu (EDT) **Description**. Ensuite, vous définissez la source de données **NumSeq** du type *Champ calculé*. Cette source de données contient l’expression `NUMSEQVALUE (AskNumSeq)`. Quand la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros spécifiée au moment de l’exécution en entrant son code dans la boîte de dialogue. La souche de numéros est demandée pour le type d’étendue **Société**. Le code société est égal à la société fournie par le contexte sous lequel le format ER est exécuté.

## <a name="example-2"></a>Exemple 2

Les sources de données suivantes sont définies dans la mise en correspondance des modèles :

- Source de données **LedgerParms** du type *Table*. Cette source de données fait référence à la table LedgerParameters.
- Source de données **NumSeq** du type *Champ calculé*. Cette source de données contient l’expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros qui a été configurée dans les paramètres de la comptabilité pour la société qui fournit le contexte sous lequel le format ER est exécuté. Cette souche de numéros identifie de manière unique les journaux et sert de numéro de lot qui relie les transactions.

## <a name="example-3"></a>Exemple 3

Les sources de données suivantes sont définies dans la mise en correspondance des modèles :

- Source de données **enumScope** de type *énumération* Microsoft Dynamics 365 Finance. Cette source de données fait référence au type d’énumération **ERExpressionNumberSequenceScopeType**.
- Source de données **NumSeq** du type *Champ calculé*. Cette source de données contient l’expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

Lorsque la source de données **NumSeq** est appelée, elle renvoie la nouvelle valeur générée de la souche de numéros **Gene\_1** qui a été configurée pour la société qui fournit le contexte sous lequel le format ER est exécuté.

## <a name="additional-resources"></a>Ressources supplémentaires

[Autre fonctions (spécifiques au domaine d’affaires)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]