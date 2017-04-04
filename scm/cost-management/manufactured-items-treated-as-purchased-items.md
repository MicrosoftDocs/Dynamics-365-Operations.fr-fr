---
title: "Paramétrez les produits pouvant être produits ou obtenus"
description: "Les produits peuvent être originaires de différentes manières - ils peuvent être produits (fabriqué) ou être obtenus (acheté). Cet article décrit certains points habituels dont vous devez tenir compte lors de la configuration des produits pour prendre en charge le multi- approvisionnement."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5360c7b1475763b8e33205bff560393e9ee51882
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-products-that-can-be-produced-or-procured"></a>Paramétrez les produits pouvant être produits ou obtenus

Les produits peuvent être originaires de différentes manières - ils peuvent être produits (fabriqué) ou être obtenus (acheté). Cet article décrit certains points habituels dont vous devez tenir compte lors de la configuration des produits pour prendre en charge le multi- approvisionnement. 

Les sources d'approvisionnement multiples sont généralement utilisées pour un article acheté qui est occasionnellement fabriqué, ou lorsqu'un article qui est principalement un article fabriqué est modifié pour devenir principalement un article acheté. L'article est d'abord désigné comme un article fabriqué afin de définir les informations de nomenclature et de gamme et de prendre en charge les ordres de fabrication pour l'article. Le type de production doit être défini sur **Nomenclature** (ou, pour le traitement de la production, **Formule** ou **Coproduit**).

Lorsque vous utilisez le coût standard, l'enregistrement des coûts de l'article peut être calculé pour l'article fabriqué. Toutefois, il se peut que l'enregistrement des coûts de l'article ne corresponde pas au coût standard que vous souhaitez pour l'achat. Dans ce cas, le coût standard doit être entré et activé manuellement pour l'enregistrement des coûts de l'article. Pour le calcul des coûts, envisagez d'utiliser une nomenclature et une gamme spéciales qui représentent la combinaison d'approvisionnement du produit au cours d'une période fiscale, pour réduire les écarts dans le temps. En outre, un article fabriqué sur un seul site peut être transféré vers un autre site. Aussi, le coût de l'article doit être entré et activé manuellement pour le site vers lequel l'article est transféré. Lorsque vous utilisez l'article fabriqué comme composant de produits de niveau supérieur, les coûts du composant doivent être considérés comme un article acheté, Ces instructions s'appliquent, que les coûts du composant soient calculés ou entrés manuellement. En d'autres termes, le calcul de la nomenclature doit considérer les coûts de l'article comme un composant acheté au lieu d'utiliser les informations de nomenclature et de gamme de l'article pour calculer les coûts. Pour éviter le calcul, sélectionnez l'indicateur **Arrêter l'éclatement** qui est intégré au groupe de calcul de la nomenclature attribué à l'article. Pour empêcher les calculs PDP/MRP de faire éclater les demandes d'article, définissez la plage d'éclatement sur 0 (zéro) jours dans la couverture d'article ou dans le groupe de couverture. Le calcul PDP/MRP considère l'article comme un article acheté et n'effectue plus de calculs pour les informations de nomenclature et de gamme de l'article.




