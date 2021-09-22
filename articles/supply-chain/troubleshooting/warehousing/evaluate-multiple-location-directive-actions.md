---
title: Évaluer toutes les actions pour les directives d’emplacement qui autorise plusieurs SKU
description: Une nouvelle fonctionnalité a été ajoutée pour évaluer toutes les actions pour les directives d’emplacement à plusieurs SKU. Cette page vous guide vers des informations sur la façon de l'activer.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476319"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>L'option de SKU multiple n'évalue pas les actions de directive d'emplacements multiples

## <a name="symptoms"></a>Symptômes

Les directives d’emplacement du type d’ordre de travail *Commandes client* et le type de travail *Ranger* n’évalue pas plusieurs actions de directive d’emplacement lorsque l’option **Plusieurs SKU** est sélectionnée. Seule la première action de directive d’emplacement est évaluée.

## <a name="resolution"></a>Résolution

Une nouvelle fonctionnalité, *Évaluer toutes les actions pour les directives d’emplacement à plusieurs SKU*, a été ajouté dans la version 10.0.15 (voir [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Cette fonctionnalité évalue toutes les actions pour les directives d’emplacement à plusieurs SKU. Si vous avez besoin de cette fonctionnalité, utilisez [Gestion des fonctionnalités](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) pour l’activer.
