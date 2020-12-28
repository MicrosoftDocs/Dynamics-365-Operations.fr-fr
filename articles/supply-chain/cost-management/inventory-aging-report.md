---
title: Exemples et logique du rapport de vieillissement des stocks
description: Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d’un rapport de vieillissement des stocks.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427869"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Exemples et logique du rapport de vieillissement des stocks

[!include [banner](../includes/banner.md)]

Cette rubrique présente quelques exemples qui montrent comment interpréter les résultats d’un rapport sur le **vieillissement des stocks**. Ce rapport classe les quantités en stock et les valeurs de stock pour un article ou un groupe d’articles sélectionné dans plusieurs plages de périodes. Cette rubrique montre également la logique interne du rapport.

Les exemples de cette rubrique montrent les résultats présentés dans un rapport **Vieillissement des stocks** standard. Cependant, en général, nous vous recommandons d’utiliser la version de ce rapport [Stockage des rapports de vieillissement des stocks](inventory-aging-report-storage.md), en particulier lorsque de nombreux articles et entrepôts doivent être traités. Le stockage des rapports de vieillissement des stocks enregistre chaque rapport que vous générez, affiche les résultats sous forme de page interactive et de graphique et vous permet d’exporter n’importe quel rapport enregistré.

## <a name="sample-data-that-is-used-in-these-examples"></a>Exemples de données utilisées

Les exemples de cette rubrique sont basés sur les exemples de données de transaction de stock décrits dans cette section.

### <a name="storage-dimension-setup"></a>Configuration de la dimension de stockage

L’exemple de système contient la configuration suivante des dimensions de stockage.

| Nom      | Actifs | Stock physique | Stock financier |
|-----------|--------|--------------------|---------------------|
| Site      | Oui    | Oui                | Oui                 |
| Entrepôt | Oui    | Oui                | N°                  |

### <a name="inventory-model"></a>Modèle de stock

Pour l’exemple de système, le modèle de stock pour les produits lancés est *FIFO*, et le paramètre **Prix de revient** du modèle de stock est *Inclure une valeur physique*.

### <a name="inventory-transactions"></a>Mouvements de stock

L’exemple de système contient les transactions de stock suivantes pour un produit lancé portant le numéro d’article *1000*.

| Référence      | Site | Entrepôt | Reçu   | Sortie | Date physique | Date financière | Quantité | Coût | Montant du coût physique |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Commande fournisseur | 1    | 11        | Acheté |       | 15 mars      | 15 mars       | 10       | 1 000       | 1 000                |
| Commande fournisseur | 2    | 21        | Acheté |       | 15 mars      | 15 mars       | 10       | 2,000       | 2,000                |
| Commande fournisseur | 1    | 11        | Reçu(e)  |       | 15 avril      |                | 5        |             | 375                  |
| Ordre de transfert | 1    | 11        |           | Vendu  | mai 2         | mai 2          | -5       | -458,33     | -458,33              |
| Ordre de transfert | 1    | 12        | Acheté |       | mai 2         | mai 2          | 5        | 458.33      | 458.33               |
| Commandes client    | 1    | 12        |           | Vendu  | mai 3         | mai 3          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Comment les quantités et les montants de chaque période sont calculés

En utilisant les exemples de données décrits dans les sections précédentes, vous pouvez exécuter un rapport **Vieillissement des stocks** contenant les paramètres suivants :

- **À ce jour :** *9 mai 2020*
- **Site :** *Vue*
- **Entrepôt :** *Non*
- **Numéro d’article :** *Total*
- **Période de vieillissement :** Définissez ce champ pour générer des compartiments mensuels.

Dans ce cas, le contenu du rapport généré ressemblera à l’exemple suivant.

<table>
<thead>
<tr>
    <th rowspan="2">numéro d’article</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Quantité disponible</th>
    <th rowspan="2">Valeur disponible</th>
    <th rowspan="2">Quantité de valeur en stock</th>
    <th rowspan="2">Valeur en stock</th>
    <th rowspan="2">Coût unitaire moyen</th>
    <th colspan="2">08/05/2020 - 01/05/2020</th>
    <th colspan="2">30/04/2020 - 01/04/2020</th>
    <th colspan="2">31/03/2020 - 01/03/2020</th>
</tr>
<tr>
    <th>P1:Quantité</th>
    <th>P1:Montant</th>
    <th>P2:Quantité</th>
    <th>P2:Montant</th>
    <th>P3:Quantité</th>
    <th>P3:Montant</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Nombre total : 1000</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Notez les détails suivants dans cet exemple de rapport :

- Les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** indiquées dans le rapport sont des valeurs pour la dimension de stock financier (**Site**, dans ce cas).

    Par exemple, pour le site 1, le rapport affiche les informations suivantes :

    - La valeur **Quantité de valeur du stock** est *14* (= 10 + 5 – 5 + 5 – 1).
    - La valeur **Quantité du stock** est *1 283,33* (= 1 000 + 375 – 458,33 + 458,33 – 91,67).
    - La valeur du **Coût unitaire moyen** est *91,67*.
    - Les valeurs **Valeur disponible** et **Montant** de chaque période sont calculées à l’aide de la valeur **Coût unitaire moyen**.

- Le rapport détermine la quantité en stock pour chaque groupe de périodes en résumant la quantité totale des stocks reçus pour chaque groupe de période. Il applique ensuite le principe du premier entré, premier sorti (FIFO) pour déduire la quantité totale délivrée, quel que soit le modèle de stock utilisé par les articles.

Si vous exécutez à nouveau le même rapport, mais cette fois, vous définissez à la fois les champs **Site** et **Entrepôt** sur *Afficher*, le nouveau rapport ressemblera à l’exemple suivant.

<table>
<thead>
<tr>
    <th rowspan="2">numéro d’article</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Entrepôt</th>
    <th rowspan="2">Quantité disponible</th>
    <th rowspan="2">Valeur disponible</th>
    <th rowspan="2">Quantité de valeur en stock</th>
    <th rowspan="2">Valeur en stock</th>
    <th rowspan="2">Coût unitaire moyen</th>
    <th colspan="2">08/05/2020 - 01/05/2020</th>
    <th colspan="2">30/04/2020 - 01/04/2020</th>
    <th colspan="2">31/03/2020 - 01/03/2020</th>
</tr>
<tr>
    <th>P1:Quantité</th>
    <th>P1:Montant</th>
    <th>P2:Quantité</th>
    <th>P2:Montant</th>
    <th>P3:Quantité</th>
    <th>P3:Montant</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Nombre total : 1000</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Cette fois, le site 1 est divisé en deux lignes, une pour l’entrepôt 11 et une pour l’entrepôt 12. Cependant, les valeurs **Quantité de valeur du stock**, **Valeur du stock** et **Coût unitaire moyen** sont identiques, car **Entrepôt** n’est pas une dimension de stock financier.

En outre, notez que la distribution des quantités du site 1 est différente. Dans le premier rapport que vous avez exécuté, le système a ignoré l’ordre de transfert qui s’est produit sur le même site et a déduit la quantité de la facture de vente de la plage de périodes **31/03/2020 - 01/03/2020** dans le site 1. Cependant, dans le nouveau rapport, le système déduit la quantité de la facture de vente de la plage de périodes **08/05/2020 - 01/05/2020** dans l’entrepôt 12.

## <a name="effects-of-inventory-closing"></a>Effets de la clôture des stocks

Si vous exécutez la clôture des stocks pour mai, puis réexécutez le rapport précédent, mais que vous définissez le champ **À partir du** sur le *31 mai 2020*, vous remarquerez les résultats suivants :

- Les valeurs **Valeur de stock** et **Coût unitaire moyen** sont mises à jour.
- La valeur **Valeur disponible** et toutes les valeurs **Montant** de chaque période sont mises à jour en conséquence.

Le nouveau rapport ressemblera à l’exemple ci-dessous.

<table>
<thead>
<tr>
    <th rowspan="2">numéro d’article</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Entrepôt</th>
    <th rowspan="2">Quantité disponible</th>
    <th rowspan="2">Valeur disponible</th>
    <th rowspan="2">Quantité de valeur en stock</th>
    <th rowspan="2">Valeur en stock</th>
    <th rowspan="2">Coût unitaire moyen</th>
    <th colspan="2">31/05/2020 - 01/05/2020</th>
    <th colspan="2">30/04/2020 - 01/04/2020</th>
    <th colspan="2">31/03/2020 - 01/03/2020</th>
</tr>
<tr>
    <th>P1:Quantité</th>
    <th>P1:Montant</th>
    <th>P2:Quantité</th>
    <th>P2:Montant</th>
    <th>P3:Quantité</th>
    <th>P3:Montant</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Nombre total : 1000</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
