---
title: Impossible de lancer la commande client avec les opérations d’entrepôt sortantes
description: Il existe plusieurs raisons pour lesquelles vous pouvez recevoir un message d’erreur indiquant qu’une commande client n’a pas pu être validée. Cette page explique pourquoi et comment atténuer le problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476351"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>Impossible de lancer la commande client avec les opérations d’entrepôt sortantes

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez des opérations d’entrepôt sortantes, le message d’erreur suivant peut s’afficher :

> La commande client n’a pas pu être lancée.

## <a name="cause"></a>Cause

Ce problème peut se produire pour plusieurs raisons. Par exemple, la commande est en attente de gestion du crédit et aucune livraison ne peut être créée tant qu’une adresse postale valide n’est pas saisie pour toutes les lignes de vente associées à une commande. Il existe également un blocage de commande qui doit être traité avant que la commande puisse être validée vers l’entrepôt. Ce blocage peut être lié à la commande ou au compte client.

## <a name="resolution"></a>Résolution

Ajoutez ou mettez à jour l’adresse sur la commande client et les lignes de commande, puis validez la commande vers l’entrepôt. Les commandes ne peuvent être validées dans l’entrepôt que si elles ont une adresse de livraison valide (selon le format d’adresse configuré dans le module **Administration de l’organisation**).

Examinez le blocage de la commande et résolvez les problèmes. Supprimez ensuite le blocage de la commande ou du client et transférez la commande à l’entrepôt.
