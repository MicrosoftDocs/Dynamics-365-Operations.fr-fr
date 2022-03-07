---
title: Interaction entre le statut de service et le champ Progression
description: Dans l’écran Commandes de service, le champ Progression de l’en-tête reflète le statut de la totalité de la commande de service, et le champ Statut indique le statut des lignes de commande de service individuelles.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0758c370fd1548770d596115b18f133071f3bbc0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566093"
---
# <a name="service-status-and-progress-field-interaction"></a>Interaction entre le statut de service et le champ Progression

[!include [banner](../includes/banner.md)]

Dans l’écran **Commandes de service**, le champ **Progression** de l’en-tête de la commande de service reflète le statut de la totalité de la commande service, et le champ **Statut** indique le statut des lignes de commande de service individuelles.

<table>
<colgroup>
<col />
<col />
<col />
<col />
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

La progression d’une commande de service est en cours si toutes les lignes affichent le statut **Créé**. Elle est toujours en cours si certaines lignes affichent le statut **Annulé** ou **Validé**.

Si toutes les lignes d’une commande de service affichent le statut **Validé**, la progression de la commande de service est **Validé**. Si certaines lignes ont le statut **Validé** et d’autres lignes ont le statut **Annulé**, la progression est toujours **Validé**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
