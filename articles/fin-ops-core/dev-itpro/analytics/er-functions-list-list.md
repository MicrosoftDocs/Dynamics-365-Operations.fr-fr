---
title: Fonction LIST ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LIST États électroniques (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f8e701ec2836206d2299abba5e5b8542b4cf92
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683085"
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