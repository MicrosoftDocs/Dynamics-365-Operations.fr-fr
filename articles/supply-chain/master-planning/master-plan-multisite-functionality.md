---
title: "Planification et fonctionnalité multisite"
description: "La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 04f61141497570577520fe9146fbd1464f31062e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="master-planning-and-multisite-functionality"></a>Planification et fonctionnalité multisite

[!include[banner](../includes/banner.md)]


La planification prend en compte les paramètres des dimensions de stock du site et de l'entrepôt. 

La dimension de site est obligatoire, et vous pouvez définir la dimension d'entrepôt comme étant obligatoire.

Lorsqu'une dimension est obligatoire, une valeur de dimension doit être entrée pour tous les mouvements de stock. Par conséquent, lors de la planification, le site et l'entrepôt pour la demande initiale sont connus. La dimension de site est également cohérente afin que, lors de l'éclatement de la demande de niveau inférieur, la valeur du site ne change pas.

Lorsque l'entrepôt n'est pas obligatoire, il se peut qu'il ne soit pas connu à partir de la demande initiale. Le moteur de planification doit déterminer l'entrepôt à utiliser en fonction des paramètres définis pour l'article, les entrepôts individuels et les détails de la ligne de commande.

Les rubriques suivantes décrivent le fonctionnement du moteur de planification, lorsque différents paramètres sont définis, pour déterminer l'entrepôt à utiliser.

[Planification - couverture du site et de l'entrepôt, entrepôt obligatoire](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planification - couverture du site, entrepôt obligatoire](master-plan-site-coverage-warehouse-mandatory.md)

[Planification - couverture du site et de l'entrepôt, entrepôt non obligatoire](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planification - couverture du site, entrepôt no obligatoire](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planification - Méthode de détermination de la version de nomenclature](master-plan-bom-version-determined.md)




