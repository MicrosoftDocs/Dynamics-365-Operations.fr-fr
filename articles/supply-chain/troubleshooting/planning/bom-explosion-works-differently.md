---
title: La distribution de la nomenclature se comporte différemment pour les ordres de fabrication confirmés et estimés
description: La distribution de nomenclatures se comporte différemment pour les ordres de fabrication confirmés et pour les ordres de fabrication estimés pour le travail créé manuellement
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
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476333"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>La distribution de la nomenclature se comporte différemment pour les ordres de fabrication confirmés et estimés

## <a name="symptoms"></a>Symptômes

Lorsqu’un ordre de fabrication est confirmé, les articles ne sont pas distribués lorsque vous distribuez la nomenclature (BOM). Cependant, lorsque vous créez manuellement un ordre de travail et que vous estimez ensuite l’ordre de fabrication, les postes sont répartis.

### <a name="resolution"></a>Résolution

La distribution qui se produit lorsque l’ordre de fabrication est confirmé pointera vers l’ordre planifié, mais il ne semble pas que l’ordre planifié soit actuellement confirmé dans ce cas. Cependant, si l’ordre de fabrication a été estimé, l’explosion est déclenchée à partir de l’ordre de fabrication lancé lorsqu’il n’existe aucun ordre planifié.
