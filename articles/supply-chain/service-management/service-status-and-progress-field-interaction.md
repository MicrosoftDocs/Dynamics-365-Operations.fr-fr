---
title: Interaction entre le statut de service et le champ Progression
description: Dans l'écran Commandes de service, le champ Progression de l'en-tête reflète le statut de la totalité de la commande de service, et le champ Statut indique le statut des lignes de commande de service individuelles.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd70d00f7ce531b225362065dfd9f1f5c1adc754
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207322"
---
# <a name="service-status-and-progress-field-interaction"></a>Interaction entre le statut de service et le champ Progression 

[!include [banner](../includes/banner.md)]


Dans l'écran **Commandes de service**, le champ **Progression** de l'en-tête de la commande de service reflète le statut de la totalité de la commande service, et le champ **Statut** indique le statut des lignes de commande de service individuelles.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Progression</p></th>
<th><p>Statut de la ligne 1</p></th>
<th><p>Statut de la ligne 2</p></th>
<th><p>Statut de la ligne 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>En cours de traitement</strong></p></td>
<td><p><strong>Créé</strong></p></td>
<td><p><strong>Créé</strong></p></td>
<td><p><strong>Créé</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>En cours de traitement</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Créé</strong></p></td>
<td><p><strong>Créé</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>En cours de traitement</strong></p></td>
<td><p><strong>Créé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Validé</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Validé</strong></p></td>
<td><p><strong>Validé</strong></p></td>
<td><p><strong>Validé</strong></p></td>
<td><p><strong>Validé</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Validé</strong></p></td>
<td><p><strong>Validé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
<td><p><strong>Annulé</strong></p></td>
</tr>
</tbody>
</table>


La progression d'une commande de service est en cours si toutes les lignes affichent le statut **Créé**. Elle est toujours en cours si certaines lignes affichent le statut **Annulé** ou **Validé**.

Si toutes les lignes d'une commande de service affichent le statut **Validé**, la progression de la commande de service est **Validé**. Si certaines lignes ont le statut **Validé** et d'autres lignes ont le statut **Annulé**, la progression est toujours **Validé**.

  


