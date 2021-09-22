---
title: Travail de prélèvement bloqué en raison de travaux de réapprovisionnement inachevés
description: Le travail de prélèvement peut être bloqué en raison du travail de réapprovisionnement dépendant. Terminez le travail de réapprovisionnement, puis traitez le travail de prélèvement.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476382"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>Le travail de prélèvement ne peut être débloqué en raison d'un travail de réapprovisionnement inachevé

## <a name="symptoms"></a>Symptômes

Lors de l'utilisation du réapprovisionnement à la demande par vagues, le travail de prélèvement peut être bloqué en raison d'un travail de réapprovisionnement dépendant. Si un site de prélèvement doit être réapprovisionné pour répondre à la demande de commande d’origine, le système crée à la fois le travail de réapprovisionnement et le travail de prélèvement. Cependant, il bloque le travail de prélèvement jusqu'à ce que le travail de réapprovisionnement soit terminé, et vous recevez le message d'erreur suivant :

> Impossible de débloquer le travail %1, car il est associé à un travail de réapprovisionnement inachevé.

## <a name="resolution"></a>Résolution

Ce comportement est intentionnel, car l’emplacement de prélèvement n’aura pas suffisamment de stock tant que le travail de réapprovisionnement ne sera pas terminé. Terminez le travail de réapprovisionnement, puis traitez le travail de prélèvement.
