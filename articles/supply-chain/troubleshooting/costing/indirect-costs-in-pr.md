---
title: Le rapport Coûts indirects en cours comprend les ordres de fabrication supprimés
description: Le rapport Coûts indirects en cours présente des informations sur les ordres de fabrication qui ont été partiellement traités puis supprimés.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 817802f1f2ad3ab07f35c28d3e833a14cd02cf8b9705c576325dc83933a0c6de
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751767"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Le rapport Coûts indirects en cours comprend les ordres de fabrication supprimés

Numéro de la base de connaissances : 4612748

## <a name="symptoms"></a>Symptômes

Le rapport **Coûts indirects en cours** présente des informations sur les ordres de fabrication qui ont été partiellement traités puis supprimés.

## <a name="resolution"></a>Résolution

Lorsque vous annulez un ordre de fabrication, vous annulez également toutes les transactions de cet ordre de fabrication. Lorsque vous supprimez l'ordre de fabrication, les tables de livres auxiliaires et le compte général conservent toutes les transactions qui y sont liées. Les rapports afficheront les transactions dans les tables de livres auxiliaires. Pour l'ordre de fabrication spécifique, la valeur nette doit être de 0,00.
