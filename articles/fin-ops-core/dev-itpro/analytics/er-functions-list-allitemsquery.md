---
title: Fonction ALLITEMSQUERY ER
description: Cet article fournit des informations sur l’utilisation de la fonction ALLITEMSQUERY États électroniques (ER).
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
ms.openlocfilehash: e350dfbe800ddc3e7b1f388fb951d091a283f4e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285303"
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
