---
title: La mise à jour des ordres prévisionnels prend du temps
description: Lors de la mise à jour de la quantité requise et/ou de la date de livraison d’un ordre prévisionnel, il faut généralement au moins 30 secondes par commande pour enregistrer la mise à jour
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476349"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>La mise à jour des ordres prévisionnels prend du temps

## <a name="symptoms"></a>Symptômes

Lors de la mise à jour de la quantité requise et/ou de la date de livraison d’un ordre planifié, il faut généralement au moins 30 secondes par commande pour enregistrer la mise à jour.

## <a name="resolution"></a>Résolution

Il s’agit d’un problème connu avec le moteur de planification intégré. Cela est dû à la distribution automatique sous-jacente à travers la structure de la nomenclature lors des modifications. Ce problème est résolu dans l’Optimisation de la planification, où un planificateur peut mettre à jour et approuver les commandes pertinentes et, s’il le souhaite, déclencher un cycle de planification pour mettre à jour les ordres planifiés pour la structure de nomenclature sous-jacente.

Une façon d’améliorer les performances avec le moteur de planification intégré consiste à effectuer les étapes suivantes :

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez un plan.
1. Développez le raccourci **Plage de gestion en jours**.
1. Définissez **Répartition** sur *Oui* et définissez le champ sous ce paramètre sur 0 (zéro).

> [!NOTE]
> Cela limitera la période des distributions effectuées pour ce plan à une seule journée.
