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
ms.openlocfilehash: df11b1c1e7de36fa0458cd931d4be7f84a15d143
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476365"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Le volet de filtre de la page Liste disponible ne fonctionne pas comme prévu

## <a name="symptoms"></a>Symptômes

Les filtres du volet de filtre de la page **Liste disponible**  ne filtrent pas les résultats comme prévu.

## <a name="resolution"></a>Résolution

La page  **Liste disponible**  est assemblée à partir d’une table de stock disponible détaillée qui comprend toutes les dimensions disponibles. Cependant, la liste sur cette page est un résumé. Par conséquent, elle peut combiner des lignes de la table source en regroupant les valeurs en fonction des dimensions affichées.

Les filtres configurés dans le volet de filtre s’appliquent à la table source, et non à la liste regroupée. Ce comportement peut parfois produire des résultats inattendus, comme indiqué dans [ces exemples](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Cependant, les [filtres disponibles dans la grille](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *s’appliquent* à la liste regroupée. Ces filtres comprennent à la fois le filtre rapide en haut de la grille et le filtre pour chaque en-tête de colonne.
