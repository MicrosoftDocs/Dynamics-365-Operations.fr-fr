---
title: Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement
description: Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: da5905fb7ed1e890c85e891843379aa07de3279bd8972d6fc57136aa703c9ea4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762792"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Une erreur se produit lorsque l'emplacement est sélectionné lors de l'enregistrement de la liste de prélèvement

Numéro de la base de connaissances : 4613106

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsque votre système est configuré pour réserver automatiquement les commandes client. Si vous essayez de sélectionner l'emplacement d'une ligne d'enregistrement de liste de prélèvement, vous recevez le message d'erreur suivant lorsque vous utilisez les processus de réservation de gestion d'entrepôt (WMS) :

> Impossible de mettre à jour la quantité avec de nouvelles dimensions

Ce problème peut se produire car vous ne disposez pas de suffisamment de stock disponible à un emplacement spécifié.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu.

Dans les scénarios où vous utilisez le processus de réservation au niveau de l'entrepôt, si le stock disponible ne sera pas réservé à tous les niveaux de dimension de stock et que vous ne disposez pas d'un stock disponible suffisant à un emplacement spécifié, nous vous recommandons d'utiliser le processus de réservation manuelle à partir de la ligne de prélèvement. Vous pouvez ensuite utiliser la fonction *Lot de réserve* pour distribuer les réservations inférieures, telles que l'emplacement, pour toutes les quantités disponibles en stock.
