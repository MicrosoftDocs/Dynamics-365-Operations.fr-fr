---
title: Traitement des documents électroniques entrants
description: Cette rubrique fournit une vue d’ensemble du traitement des documents électroniques entrants.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9701367e1ba1f9dbd1e53deb863c10af4213a359
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371608"
---
# <a name="processing-of-incoming-electronic-documents"></a>Traitement des documents électroniques entrants

[!include [banner](../includes/banner.md)]

Les documents électroniques entrants, tels que les factures électroniques des fournisseurs, peuvent être importés et traités de deux manières :

- Les fichiers sont récupérés à partir de canaux externes et transmis directement à votre application connectée. Là, ils subissent une transformation supplémentaire et sont ensuite importés dans la base de données.
- Les fichiers font l’objet d’un prétraitement dans le service Facturation électronique et sont ensuite transmis à votre application connectée.

La facturation électronique prend en charge deux canaux pour les documents entrants : e-mail et dossiers Microsoft SharePoint.

Il existe des types de configuration twp pour spécifier si les documents subissent un prétraitement ou sont transmis directement à votre application connectée :

- **Canal de données** –  Le système transmettra le document directement à l’application connectée.
- **Canal de données avec pipeline de traitement** –  Vous pouvez configurer des actions supplémentaires qui seront exécutées avant que le document ne soit transmis à l’application connectée.

Pour plus d’informations sur la mise en place des scénarios de traitement des documents électroniques entrants pour les différents canaux, voir [Configurer un canal de messagerie](e-invoicing-configure-email.md) et [Configurer un canal SharePoint](e-invoicing-configure-sharepoint-channel.md).
