---
title: Fonction ALLITEMS ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ALLITEMS États électroniques (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 5ddcf989bdfd1d1f5d0a412a2ffefe0e3037ca79
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746721"
---
# <a name="allitems-er-function"></a>Fonction ALLITEMS ER

[!include [banner](../includes/banner.md)]

La fonction `ALLITEMS` s’exécute comme une sélection en mémoire et retourne une nouvelle valeur *Liste des enregistrements* aplatie comme une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié.

## <a name="syntax"></a>Syntaxe

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Arguments

`path` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Le chemin doit être défini comme le chemin d’accès valide de la source de données vers un élément de source de données d’un type de données de *Liste des enregistrements*. Les éléments de données tels que la chaîne de chemin d’accès et la date doivent déclencher une erreur dans le générateur d’expression États électroniques ER au moment de la conception.

Nous vous déconseillons d’utiliser cette fonction pour les sources de données transactionnelles pouvant contenir un grand volume de données. Au lieu de cela, envisagez d’utiliser la fonction [ALLTEMSQUERY](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Exemple 1

Si vous entrez `SPLIT("abcdef" , 2)` comme source de données **DS**, l’expression `COUNT( ALLITEMS (DS))` renvoie **3**.

## <a name="example-2"></a>Exemple 2

Si vous entrez **Vend** comme source de données du type de données *Liste des enregistrements* qui fait référence à la table d’application VendTable, l’expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` renvoie une liste d’enregistrements aplatie qui a la structure de la table **ContactPerson** et contient toutes les personnes de contact qui sont accessibles en utilisant la relation **ContactPerson.ContactForParty == VendTable.Party** et qui est disponible pour tous les fournisseurs à partir de la table des fournisseurs référencés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]