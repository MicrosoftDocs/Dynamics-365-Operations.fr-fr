---
title: Le cumul des remises client échoue lorsque des groupes de remises d'articles sont utilisés
description: Lorsque vous utilisez des accords de remise client en combinaison avec des groupes de remise d'article, les remises sont calculées, mais le cumul échoue.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026497"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Le cumul des remises client échoue lorsque des groupes de remises d'articles sont utilisés

Numéro de la base de connaissances : 4611372

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez des accords de remise client en combinaison (du type *montant*) avec des groupes de remise d'article, les remises sont calculées, mais le cumul échoue.

## <a name="resolution"></a>Résolution

Le système se comporte comme prévu. Les groupes d'articles regroupent uniquement les articles qui ont la même condition de seuil. La condition de remise (seuil) est définie par rapport au montant de chaque article, et non par rapport au montant cumulé pour tout article du groupe d'articles.
