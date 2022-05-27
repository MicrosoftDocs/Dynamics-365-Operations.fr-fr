---
title: Le volet de filtre de la page Liste disponible ne fonctionne pas comme prévu
description: Les filtres du volet de filtre de la page « Liste disponible » ne filtrent pas les résultats comme prévu.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 3857ce3720430c6f512d5abc4c9c4d390a0c3377
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686681"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Le volet de filtre de la page Liste disponible ne fonctionne pas comme prévu

## <a name="symptoms"></a>Symptômes

Les filtres du volet de filtre de la page **Liste disponible** ne filtrent pas les résultats comme prévu.

## <a name="resolution"></a>Résolution

La page **Liste disponible** est assemblée à partir d’une table du stock disponible détaillée qui comprend toutes les dimensions disponibles. Cependant, la liste sur cette page est un résumé. Par conséquent, elle peut combiner des lignes de la table source en regroupant les valeurs en fonction des dimensions affichées.

Les filtres configurés dans le volet de filtre s’appliquent à la table source, et non à la liste regroupée. Ce comportement peut parfois produire des résultats inattendus, comme indiqué dans [ces exemples](/dynamics365/supply-chain/inventory/inventory-on-hand-list#examples).

Cependant, les [filtres disponibles dans la grille](/dynamics365/supply-chain/inventory/inventory-on-hand-list#grid-filters) *s’appliquent* à la liste regroupée. Ces filtres comprennent à la fois le filtre rapide en haut de la grille et le filtre pour chaque en-tête de colonne.
