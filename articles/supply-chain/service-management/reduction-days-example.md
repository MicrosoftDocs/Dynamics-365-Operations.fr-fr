---
title: "Exemple de jours de réduction"
description: "Exemple de jours de réduction."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a>Exemple de jours de réduction 

[!include [banner](../includes/banner.md)]


Vous avez créé une transaction d'abonnement pour un abonnement de maintenance d'un client, comme décrit dans le tableau suivant.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Du</p></th>
<th><p>Au</p></th>
<th><p>Abonnement</p></th>
<th><p>Type d'abonnement</p></th>
<th><p>Projet</p></th>
<th><p>Catégorie</p></th>
<th><p>Devise de vente</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>01 mars 2011</p></td>
<td><p>31 mars 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Normal</strong></p></td>
<td><p>9013</p></td>
<td><p>SousCat2</p></td>
<td><p>EUR</p></td>
<td><p>200,00</p></td>
</tr>
</tbody>
</table>


Le client signale qu'il n'a pas besoin d'une couverture de service pendant deux jours (10 et 11 mars). Vous acceptez de réduire l'abonnement pour ces deux jours.

Vous créez une nouvelle transaction de type **Jours de réduction**, telle que décrite dans le tableau suivant.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Date de début</p></th>
<th><p>Au</p></th>
<th><p>Abonnement</p></th>
<th><p>Type d'abonnement</p></th>
<th><p>Projet</p></th>
<th><p>Catégorie</p></th>
<th><p>Devise de vente</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>10 mars 2011</p></td>
<td><p>11 mars 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Jours de réduction</strong></p></td>
<td><p>9013</p></td>
<td><p>SousCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12,90</p></td>
</tr>
</tbody>
</table>


Lorsque les transactions pour mars 2011 sont facturées, le prix de vente de 200 EUR est réduit de 12,90 EUR. Le montant facturable pour la transaction d'abonnement est donc de 187,10 EUR et deux transactions sont facturées pour un total de 187,10 EUR.

## <a name="see-also"></a>Voir également :

[Réduction des jours sur les frais d'abonnement](reduce-the-days-on-subscription-fees.md)

  



