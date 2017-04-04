---
title: "Planification et fonctionnalité multisite"
description: "La planification prend en compte les paramètres des dimensions de stock du site et de l&quot;entrepôt."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 19eeee753c15cf2670948ce2c615a112813c16ad
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-and-multisite-functionality"></a>Planification et fonctionnalité multisite

La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt. 

La dimension de site est obligatoire, et vous pouvez définir la dimension d'entrepôt comme étant obligatoire.

Lorsqu'une dimension est obligatoire, une valeur de dimension doit être entrée pour tous les mouvements de stock. Par conséquent, lors de la planification, le site et l'entrepôt pour la demande initiale sont connus. La dimension de site est également cohérente afin que, lors de l'éclatement de la demande de niveau inférieur, la valeur du site ne change pas.

Lorsque l'entrepôt n'est pas obligatoire, il se peut qu'il ne soit pas connu à partir de la demande initiale. Le moteur de planification doit déterminer l'entrepôt à utiliser en fonction des paramètres définis pour l'article, les entrepôts individuels et les détails de la ligne de commande.

Les articles wiki suivants décrivent le fonctionnement du moteur de planification, lorsque différents paramètres sont définis, pour déterminer l'entrepôt à utiliser.

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification - couverture du site, entrepôt no obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)


