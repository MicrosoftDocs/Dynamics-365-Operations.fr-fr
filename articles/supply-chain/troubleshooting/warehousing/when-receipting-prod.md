---
title: Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu
description: Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026506"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Une seule étiquette est imprimée pour plusieurs en-têtes de travail sur un seul reçu

Numéro de la base de connaissances : 4614667

## <a name="symptoms"></a>Symptômes

Plusieurs en-têtes de travail sont créés pour le même contenant cible dans le cadre d'un seul événement de réception d'application d'entrepôt. Cependant, une seule étiquette de contenant est imprimée lors de la réception du produit.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu.

Dans la conception actuelle, une seule étiquette de contenant est toujours générée, quel que soit le nombre de combinaisons d'en-tête de travail et de ligne de travail qui existent. L'étiquette générée comprend les informations pour une seule combinaison.

Pour contourner ce problème, assurez-vous que la création d'en-tête de travail est toujours mappée à un seul contenant cible.
