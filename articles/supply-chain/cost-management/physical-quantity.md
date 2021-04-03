---
title: Valeurs d’un objet de stock
description: Cet article fournit des informations sur la manière dont les valeurs d’un objet de stock sont calculées.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f14248ffa8f9f5a460b090ca5754442cd50bf45a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263540"
---
# <a name="inventory-object-values"></a>Valeurs d’un objet de stock

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la manière dont les valeurs d’un objet de stock sont calculées. 

Une nouvelle fonctionnalité nommée **quantité physique** vous permet de consulter les valeurs d’un objet de stock spécifique. 

Un objet de coût représente le niveau d’entité où est effectué le comptage d’inventaire. Pour plus d’informations sur les objets de coût, consultez [Objets de coût](cost-object.md). 

Pour afficher les valeurs d’un objet de stock spécifique, cliquez sur **Quantité physique** dans la page **Objet de coût**. Spécifiez comment la valeur d’un objet de stock est calculée : 

Objet de stock. Valeur = Objet de coût.Coût unitaire moyen × Objet de stock.Quantité 

L’exemple suivant montre comment les valeurs d’un objet de stock et d’un objet de coût sont calculées. Deux événements d’accusé de réception de marchandises sont enregistrés pour l’article A :

-   Accusé de réception de marchandises 1 : Quantité = 100., pcs, Montant = 1 000.00 USD, Site = 1, Entrepôt =11, N° de lot. = B1
-   Accusé de réception de marchandises 2 : Quantité = 50., pcs, Montant = 800.00 USD, Site = 1, Entrepôt =11, N° de lot. = B2

Le tableau suivant donne le résultat du calcul pour un objet de coût. Vous pouvez afficher le résultat dans la page **Objet de coût**.

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’objet</th>
<th>Numéro d’article</th>
<th>site ;</th>
<th>Quantité</th>
<th>Unité de stock</th>
<th>Valeur</th>
<th>Coût unitaire moyen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objet de coût</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>Pcs.</td>
<td><p>1800,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
</tbody>
</table>

Le tableau suivant donne le résultat du calcul pour un objet de stock. Vous pouvez afficher le résultat en cliquant sur **Quantité physique** dans la page **Objet de coût**.

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’objet</th>
<th>Numéro d’article</th>
<th>site ;</th>
<th>Entrepôt</th>
<th>N° de lot</th>
<th>Quantité</th>
<th>Unité de stock</th>
<th>Valeur</th>
<th>Coût unitaire moyen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objet de stock</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Pcs.</td>
<td><p>1200,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
<tr class="even">
<td>Objet de stock</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Pcs.</td>
<td><p>600,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Objets de coût](cost-object.md)

[Écritures de coût](cost-entries.md)

[Nouveautés et changements](../../fin-and-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]