---
title: Résoudre les problèmes de réapprovisionnement de l’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réapprovisionnement en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e4d87e85520c2b6f2346fddf3b985d4e17fe35cb
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644871"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Résoudre les problèmes de réapprovisionnement de l’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réapprovisionnement en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Je reçois le message d’erreur suivant : « Le travail %1 ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »

### <a name="issue-description"></a>Description du problème

Le travail de prélèvement est bloqué en raison du travail de réapprovisionnement dépendant.

### <a name="issue-resolution"></a>Résolution du problème

Lorsque vous utilisez le réapprovisionnement de la demande de vague, si un site de prélèvement doit être réapprovisionné pour répondre à la demande de commande d'origine, le système crée à la fois le travail de réapprovisionnement et le travail de prélèvement. Cependant, il bloque le travail de prélèvement jusqu'à ce que le travail de réapprovisionnement soit terminé. Ce comportement est intentionnel, car l'emplacement de prélèvement n'aura pas suffisamment de stock tant que le travail de réapprovisionnement n'est pas terminé. Terminez le travail de réapprovisionnement, puis traitez le travail de prélèvement.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]