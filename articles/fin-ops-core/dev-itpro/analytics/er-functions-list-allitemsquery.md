---
title: Fonction ALLITEMSQUERY ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction ALLITEMSQUERY États électroniques (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 7995b497a2bd95d4aec9ae6d5f1c3cb790823ea0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746697"
---
# <a name="allitemsquery-er-function"></a>Fonction ALLITEMSQUERY ER

[!include [banner](../includes/banner.md)]

La fonction `ALLITEMSQUERY` s’exécute en tant que requête SQL jointe. Elle renvoie une nouvelle valeur de *Liste des enregistrements* aplatie qui consiste en une liste d’enregistrements qui représente tous les éléments qui correspondent au chemin spécifié.

## <a name="syntax"></a>Syntaxe

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Arguments

`path` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*. Il doit contenir au moins une relation.

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Le chemin spécifié doit être défini comme le chemin d’accès valide de la source de données vers un élément de source de données d’un type de données de *Liste des enregistrements*. Il doit également contenir au moins une relation. Les éléments de données tels que la *Chaîne* de chemin d’accès et la *Date* doivent déclencher une erreur dans le générateur d’expression États électroniques ER au moment de la conception.

Lorsque cette fonction est appliquée aux sources de données du type de données *Liste des enregistrements* qui fait référence à un objet d’application qui peut être appelé directement à l’aide de SQL (par exemple, une table, une entité ou une requête), il s’exécute en tant que requête SQL jointe. Sinon, il s’exécute en mémoire en tant que fonction [ALLITEMS](er-functions-list-allitems.md).

## <a name="example"></a>Exemple

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- Source de données **CustInv** de type *Enregistrements de la table* qui fait référence à la table CustInvoiceTable
- Source de données **FilteredInv** du type *Champ calculé* qui contient l’expression `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- **JourLines** du type *Champ calculé* qui contient l’expression `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

Lorsque vous exécutez la mise en correspondance des modèles pour appeler la source de données **JourLines**, l’instruction SQL suivante est exécutée :

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]