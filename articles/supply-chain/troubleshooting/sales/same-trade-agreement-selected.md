---
title: Même accord commercial sélectionné lors de la création des lignes de commande client
description: S’il y a plus d’un accord commercial défini pour une date donnée, l’accord commercial qui a le prix le plus bas est toujours sélectionné lors de la création des lignes de commande client.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476341"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Si deux accords commerciaux existent pour des dates qui se chevauchent, le même est toujours sélectionné

## <a name="symptoms"></a>Symptômes

Si deux accords commerciaux sont définis pour la même période ou des périodes qui se chevauchent, le même accord commercial semble être sélectionné à chaque fois que vous créez des lignes de commande client contenant ces articles.

## <a name="resolution"></a>Résolution

S’il y a plus d’un accord commercial pour une date donnée, l’accord commercial qui a le prix le plus bas est toujours sélectionné. Pour plus d’informations, téléchargez le livre blanc suivant : [Accords commerciaux dans Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
