---
title: La limite maximale d’un contrat d’achat n’est pas effective sur une demande d’achat
description: La limite maximale d’un contrat d’achat n’est pas effective sur une demande d’achat
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476314"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>La limite maximale d’un contrat d’achat n’est pas effective sur une demande d’achat

## <a name="symptoms"></a>Symptômes

Lorsqu’une demande d’achat est liée à un contrat d’achat, la limite maximale du contrat d’achat n’est pas effective sur la demande d’achat. Les informations de prix par défaut sont correctement saisies, mais la limite maximale du contrat d’achat peut être dépassée dans la demande d’achat.

## <a name="resolution"></a>Résolution

Ce comportement est attendu. Étant donné que les demandes d’approvisionnement ne sont pas toujours approuvées, une quantité ou un montant ne doit pas être réservé sur le contrat d’achat. Par conséquent, vous ne respecterez pas la limite maximale du contrat d’achat.
