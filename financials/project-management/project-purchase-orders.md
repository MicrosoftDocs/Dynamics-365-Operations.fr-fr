---
title: Commandes fournisseur pour un projet
description: "Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l&quot;objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 82305cfe38e7193cece3b9e7784fb81fd40f9c70
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-orders-for-a-project"></a>Commandes fournisseur pour un projet

[!include[banner](../includes/banner.md)]


Cet article décrit les différentes méthodes qui vous permettent de créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés et validés pour un projet.

Dans Microsoft Dynamics 365 for Operations, vous pouvez utiliser plusieurs méthodes pour créer des commandes fournisseur pour un projet. La méthode que vous utilisez dépend de l'objectif de la commande fournisseur, la date à laquelle les articles achetés sont consommés, et celle à laquelle ils sont validés pour un projet.

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




