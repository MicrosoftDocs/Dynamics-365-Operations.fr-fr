---
title: Les ordres prévisionnels sont générés pour le stock avec les ordres de fabrication
description: Les ordres prévisionnels sont générés même si vous avez des articles en stock et que des ordres de fabrication existent déjà pour eux
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
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476385"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>Les ordres prévisionnels sont générés pour le stock avec les ordres de fabrication

## <a name="symptoms"></a>Symptômes

Les ordres prévisionnels sont générés même si vous avez des articles en stock et que des ordres de fabrication existent déjà pour eux.

## <a name="resolution"></a>Résolution

Vous pourrez peut-être résoudre ce problème en augmentant la valeur **Jours positifs** pour les groupes concernés sur la page **Groupe de couverture**. Ce changement amènera le système à déterminer si le stock disponible peut être utilisé pour la demande. Ensuite, un nouvel ordre planifié ne sera pas généré pour les articles en stock.
