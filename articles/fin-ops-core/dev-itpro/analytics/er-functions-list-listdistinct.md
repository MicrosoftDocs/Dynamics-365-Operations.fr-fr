---
title: Fonction LISTDISTINCT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction LISTDISTINCT États électroniques (ER).
author: NickSelin
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 9ab9354b0fdb1c08c192b90e6bab303cb85ea41a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743821"
---
# <a name="listdistinct-er-function"></a>Fonction LISTDISTINCT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La fonction `LISTDISTINCT` calcule l’expression spécifiée comme un sélecteur pour chaque enregistrement de la liste spécifiée. Elle renvoie une nouvelle valeur *Liste des enregistrements* qui contient un seul enregistrement pour chaque valeur de sélecteur unique.

## <a name="syntax"></a>Syntaxe

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Arguments

`list` : *Liste d’enregistrements*

Chemin d’accès valide d’une source de données du type de données *Liste d’enregistrements*.

`selector` : *Type de données primitif*

Expression valide utilisée pour calculer une valeur de sélecteur pour chaque enregistrement de la liste spécifiée.

Les types de données suivants sont pris en charge pour ce paramètre :

- Booléen
- Date
- Date et heure
- GUID
- Entier
- Int64
- Réel
- Chaîne

## <a name="return-values"></a>Valeurs de retour

*Liste d’enregistrements*

Liste des enregistrements résultante.

## <a name="usage-notes"></a>Notes d’utilisation

La structure de la liste créée correspond à la structure de la liste spécifiée.

La même valeur de sélecteur peut être calculée pour plusieurs enregistrements dans la liste spécifiée. Dans ce cas, les valeurs de champ de l’enregistrement correspondant dans la liste créée sont égales aux valeurs du premier enregistrement de la liste spécifiée pour laquelle la valeur du sélecteur est calculée.

L’exécution de cette fonction se fait sur toute source de données [Gestion des états électroniques (ER)](general-electronic-reporting.md) du type *Liste des enregistrements* présent en mémoire.

La source de données **GROUPBY** peut également être utilisée pour générer la liste des enregistrements pour lesquels le sélecteur qui a des valeurs distinctes est calculé. Cependant, du point de vue des performances et de la consommation de mémoire, il est préférable d’utiliser la fonction `LISTDISTINCT` que la source de données **GROUPBY**, car l’exécution de la fonction se fait en mémoire.

## <a name="example"></a>Exemple

L’exemple suivant montre comment vous pouvez obtenir la liste des numéros de compte client uniques auxquels au moins une facture vente ou une facture projet a été émise au cours d’une période spécifique.

1. Entrez la source de données **SalesInvoice** de type `Record list` qui fait référence à la table d’application **CustInvoiceJour** et filtre les factures vente pour des périodes spécifiques.

    Le champ `InvoiceAccount` de cette source de données renvoie le numéro de compte d’un client facturé.

2. Entrez la source de données **ProjectInvoice** de type `Record list` qui fait référence à la table d’application **ProjInvoiceJour** et filtre les factures projet pour des périodes spécifiques.

    Le champ `InvoiceAccount` de cette source de données renvoie le numéro de compte d’un client facturé.

3. Configurez la source de données **AllInvoices** du type `Calculated field` qui contient l’expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Cette source de données renvoie la liste jointe des factures vente et des factures projet.

4. Configurez la source de données **InvoicedCustomer** du type `Record list` qui contient l’expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Cette source de données renvoie une nouvelle liste qui contient un enregistrement unique pour chaque client unique qui a été facturé pendant la période définie. Le champ `InvoiceAccount` de cette liste contient un numéro de compte client.

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions de liste](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]