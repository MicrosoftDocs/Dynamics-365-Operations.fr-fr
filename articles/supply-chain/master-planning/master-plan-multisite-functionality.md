---
title: Vue d'ensemble de planification générale et fonctionnalité multisite
description: La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b26ff5c2f580c30113b82302bbad744bbf285ff
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213720"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Vue d'ensemble de planification générale et fonctionnalité multisite

[!include [banner](../includes/banner.md)]

La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt. 

La dimension de site est obligatoire, et vous pouvez définir la dimension d'entrepôt comme étant obligatoire.

Lorsqu'une dimension est obligatoire, une valeur de dimension doit être entrée pour tous les mouvements de stock. Par conséquent, lors de la planification, le site et l'entrepôt pour la demande initiale sont connus. La dimension de site est également cohérente afin que, lors de l'éclatement de la demande de niveau inférieur, la valeur du site ne change pas.

Lorsque l'entrepôt n'est pas obligatoire, il se peut qu'il ne soit pas connu à partir de la demande initiale. Le moteur de planification doit déterminer l'entrepôt à utiliser en fonction des paramètres définis pour l'article, les entrepôts individuels et les détails de la ligne de commande.

Les rubriques suivantes décrivent le fonctionnement du moteur de planification, lorsque différents paramètres sont définis, pour déterminer l'entrepôt à utiliser.

[Planification de couverture de site et d'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification pour couverture de site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification de couverture de site et d'entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification pour couverture de site, entrepôt non obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)

[Déterminer la version de nomenclature](master-plan-bom-version-determined.md)



