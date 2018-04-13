---
title: Commandes fournisseur pour un projet
description: "Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: dae65394a2180ccbf3317a41b635ba97034e541b
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="purchase-orders-for-a-project"></a>Commandes fournisseur pour un projet

[!INCLUDE [banner](../includes/banner.md)]

Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet.

Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez utiliser plusieurs méthodes pour créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés, et celle à laquelle ils sont validés pour un projet.

### <a name="methods-for-creating-a-purchase-order"></a>Méthodes de création d'une commande fournisseur

Utilisez l'une des méthodes suivantes pour créer des commandes fournisseur dans Gestion et comptabilité des projets. L'objectif de la commande fournisseur détermine quand celle-ci est consommée et donc le moment où les articles sont validés pour un projet.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Méthode</th>
<th>Objectif</th>
<th>Consommation d'articles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Créer une commande fournisseur directement à partir d'un projet</td>
<td>Cette méthode permet d'acheter des articles à un fournisseur externe en vue d'une consommation sur un projet. Vous pouvez créer une commande fournisseur de deux manières :
<ul>
<li>À partir du projet lui-même. Dans ce cas, le projet est déjà défini pour la commande fournisseur.</li>
<li>En accédant à la commande fournisseur. Vous devez sélectionner le fournisseur et le projet pour lequel créer la commande fournisseur.</li>
</ul></td>
<td>Les articles sont consommés lorsque la facture fournisseur est mise à jour.</td>
</tr>
<tr class="even">
<td>Créez une commande fournisseur à partir d'une commande client.</td>
<td>Utilisez cette méthode pour des articles achetés lorsque vous créez une commande client à partir d'un projet.</td>
<td>Des articles sont consommés lorsque la commande client est facturée au client.</td>
</tr>
<tr class="odd">
<td>Créez une commande fournisseur à partir d'une demande d'articles.</td>
<td>Utilisez cette méthode pour des articles achetés lorsque vous créez une demande d'articles à partir d'un projet.</td>
<td>Des articles sont consommés lors de la mise à jour du bon de livraison de demande d'articles.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Lorsque vous mettez à jour la facture fournisseur ou le bon de livraison, vous êtes invité à mettre à jour le bon de livraison sur la demande d'articles.

Pour plus d'informations, voir [Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles](tasks/receive-items-purchase-order-item-requirement.md).


