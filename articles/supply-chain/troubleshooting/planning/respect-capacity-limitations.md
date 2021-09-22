---
title: La planification générale planifie plus que la capacité disponible
description: La planification générale ne semble pas respecter les limites de capacité et prévoit plus que la capacité disponible.
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
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476350"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>La planification générale planifie plus que la capacité disponible

## <a name="symptoms"></a>Symptômes

La planification générale ne semble pas respecter les limites de capacité et prévoit plus que la capacité disponible.

Lorsque vous utilisez la planification des opérations là où il y a une capacité limitée et où l’itinéraire spécifie un mélange d’exigences pour un groupe de ressources et des ressources individuelles, il existe un faible risque de surréservation en raison de la façon dont l’algorithme valide les conflits de capacité. Cette surréservation peut se produire lorsque vous utilisez des assistants pour exécuter la planification générale. Il est plus probable que cela se produise s’il existe de nombreux travaux dont la durée d’exécution est relativement courte.

## <a name="resolution"></a>Résolution

S’il est essentiel qu’aucune surréservation ne se produise pour la planification des opérations, vous pouvez faire de la planification une partie de la planification mono-thread en activant l’option **Capacité finie précise pour la planification des opérations** sur la page **Paramètres de planification**. Cette option n’est pas disponible par défaut. Vous devez l’ajouter manuellement à la page à l’aide des fonctionnalités de personnalisation. Lorsque vous utilisez cette option, la planification s’exécute plus lentement en raison du manque de traitement parallèle.
