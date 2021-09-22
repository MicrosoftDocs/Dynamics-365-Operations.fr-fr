---
title: Une remise fournisseur n’est pas cumulée en fonction des factures
description: Une remise fournisseur n’est pas cumulée en fonction des factures
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476379"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Une remise fournisseur n’est pas cumulée en fonction des factures

## <a name="symptoms"></a>Symptômes

Si les factures validées ont des dates d’échéance différentes, ces factures ne sont pas reflétées dans les remises fournisseur générées à partir d’elles.

## <a name="resolution"></a>Résolution

La date d’échéance n’est pas prise en compte lors du calcul de la remise fournisseur. Envisagez de personnaliser le système afin que la date d’échéance et la relation avec la facture soient plus apparentes par rapport à la remise fournisseur réelle.
