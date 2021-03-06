---
title: Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article
description: Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026522"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Il n'y a pas de valeur de date de début dans l'onglet Prix actifs de la page Prix de l'article

Numéro de la base de connaissances : 4613548

## <a name="symptoms"></a>Symptômes

Il n'y a pas de valeur **Date de début** dans l'onglet **Prix actifs** de la page **Prix de l'article**.

## <a name="resolution"></a>Résolution

La valeur **Date de début** (date d'effet) qui est définie sur le prix en attente n'est pas transférée au prix actif.

La première fois qu’un enregistrement de coûts d’articles est saisi, il est doté du statut *En attente* et une date d’effet choisie. Lorsque vous activez l’enregistrement des coûts d’articles, le statut est mis à jour sur *Actif*, et la date d’effet est mise à jour sur la date d’activation. Par conséquent, la date d'activation du prix actif est toujours la date réelle de l'activation.

Pour plus d’informations, voir [Vue d’ensemble des versions d’évaluation des coûts](../../cost-management/costing-versions.md).
