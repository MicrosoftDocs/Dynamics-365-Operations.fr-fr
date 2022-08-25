---
title: Fonction LIST ER
description: Cet article fournit des informations sur l’utilisation de la fonction LIST États électroniques (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 7a5f27baa248ec84c75725cf32a1f482841424c2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277630"
---
# <a name="list-er-function"></a>Fonction LIST ER

[!include [banner](../includes/banner.md)]

La fonction `LIST` renvoie une valeur *Liste des enregistrements* constituée d’une nouvelle liste d’enregistrements créée à partir des arguments spécifiés.

## <a name="syntax"></a>Syntaxe

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Arguments

`record 1` : *Conteneur (enregistrement)*

Référence à une source de données du type de données *Enregistrement*. Cet argument est obligatoire.

`record N` : *Conteneur (enregistrement)*

Référence à une source de données du type de données *Enregistrement*. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La structure de la liste qui est créée contient uniquement les champs qui sont présentés dans la structure de chaque enregistrement mentionné dans les arguments.

## <a name="example"></a>Exemple

Vous entrez une source de données **Enregistrement 1** du type *Conteneur*. Cette source de données contient les champs imbriqués suivants du type *Champ calculé* :

- **Code :** Ce champ contient une expression qui renvoie une valeur de type *Chaîne*.
- **Montant :** Ce champ contient une expression qui renvoie une valeur de type *Réel*.

Vous entrez ensuite une source de données **Enregistrement 2** du type *Conteneur*. Cette source de données contient les champs imbriqués suivants du type *Champ calculé* :

- **Montant :** Ce champ contient une expression qui renvoie une valeur de type *Réel*.
- **IsValid :** Ce champ contient une expression qui renvoie une valeur de type *Booléen*.

Dans ce cas, l’expression `LIST('Record 1', 'Record 2')` renvoie une nouvelle liste qui contient deux enregistrements. La structure de cette liste se compose d’un seul champ **Montant** de type *Réel*, car ce champ est le seul champ présenté dans chaque argument de la fonction appelée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
