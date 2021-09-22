---
title: La planification de la production ne tient pas compte des marges de sécurité
description: La planification de la production ne prend pas en compte les marges de sécurité définies sur la couverture des articles pour l’approvisionnement indexé
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
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476315"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>La planification de la production ne tient pas compte des marges de sécurité

## <a name="symptoms"></a>Symptômes

La planification tient compte des marges de sécurité. Cependant, les marges de sécurité sont ignorées lors de la planification des ordres de fabrication planifiés.

## <a name="resolution"></a>Résolution

Les marges ne sont prises en compte que lors de la planification, pas lors de la planification manuelle. Les marges sont conçues pour agir comme un tampon pendant la phase de planification, pour donner une certaine "marge" pour le processus réel.

Pour obtenir le résultat souhaité, vous pouvez supprimer la marge. L’itinéraire doit ensuite être mis à jour pour inclure l’heure souhaitée (par exemple, en tant que durée de la file d’attente). La planification et la planification manuelle devraient alors produire le même résultat.
