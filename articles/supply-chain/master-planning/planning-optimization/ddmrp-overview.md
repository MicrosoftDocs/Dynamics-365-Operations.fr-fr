---
title: Vue d’ensemble de la planification des besoins en matériaux basée sur la demande (DDMRP)
description: Cet article fournit des informations sur la planification des besoins en matériaux pilotée par la demande (DDMRP), une méthodologie de planification basée sur le découplage de l’offre et de la demande.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689486"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Vue d’ensemble de la planification des besoins en matériaux basée sur la demande (DDMRP)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Pendant des années, les entreprises ont utilisé la planification des besoins en matériaux (MRP) comme système de calcul des matériaux et des composants nécessaires à la fabrication d’un produit. Cependant, les chaînes d’approvisionnement ont maintenant changé. Les pièces ont des délais de livraison plus longs, car elles proviennent de plus en plus de l’étranger. Par conséquent, de nombreuses entreprises ont signalé des ruptures de stock ou des surstocks, car elles ne savent pas sur quantité de stock se baser. Il y a aussi plus de fluctuations du marché (parfois des prévisions inexactes) et les clients exigent des produits dans des délais courts. Par conséquent, il y a des pénuries dans la chaîne d’approvisionnement partout dans le monde. De plus, les outils MRP donnent souvent aux planificateurs des milliers d’actions à faire. Par conséquent, il est difficile de savoir sur quoi se concentrer. Souvent, la solution à bon nombre de ces problèmes consiste à passer à la planification des besoins en matériaux basée sur la demande (DDMRP).

Le DDMRP est une méthodologie de planification basée sur le découplage de l’offre et de la demande. Ce découplage est réalisé par la mise en place d’éléments ponctuels de découplage. Pour ces articles, des marges sont maintenues pour s’assurer que la quantité correcte de stock est conservée. Le découplage de l’offre et de la demande permet d’éviter « l’effet coup de fouet », car la variabilité n’est pas répercutée dans la chaîne. (L’*effet coup de fouet* fait référence à la façon dont de petites fluctuations de la demande au niveau de la vente au détail peuvent entraîner des fluctuations progressivement plus importantes de la demande au niveau du grossiste, du distributeur, du fabricant et du fournisseur de matières premières.) Chaque marge est destinée à couvrir l’utilisation moyenne d’une pièce et peut également être ajustée pour couvrir les pics de demande.

La DDMRP s’avère une méthodologie de planification précieuse pour les environnements variables où les délais de tolérance des clients sont plus courts que les délais cumulés.

## <a name="the-five-components-of-ddmrp"></a>Les cinq composants de la DDMRP

La DDMRP comporte cinq composants séquentiels (étapes). Les trois premiers composants définissent essentiellement la configuration initiale et évolutive d’un modèle de planification des besoins en matériaux axée sur la demande. Les deux derniers éléments définissent le fonctionnement quotidien de la méthodologie.

1. **[Positionnement stratégique du stock](ddmrp-inventory-positioning.md)**  : identifier les points de découplage dans le réseau de la chaîne d’approvisionnement. Les points de découplage sont des points spécifiques de votre chaîne d’approvisionnement où vous placez une marge de stock que vous surveillerez et réapprovisionnerez.
2. **[Profils et niveaux de tampon](ddmrp-buffer-profile-and-levels.md)**  : pour chaque point de découplage, identifier les tailles de tampon (quantité minimale, quantité maximale et point de réapprovisionnement) et la quantité de réapprovisionnement.
3. **[Ajustements de tampon dynamiques](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)**  : ajuster les niveaux de tampon, en fonction des paramètres de fonctionnement variables ou des événements futurs prévus.
4. **[Planification axée sur la demande](ddmrp-planning.md)**  : générer des commandes d’approvisionnement au fur et à mesure des besoins. Parmi ces commandes d’approvisionnement figurent les commandes de fabrication, les commandes d’achat et les commandes de transfert de stock
5. **[Exécution hautement collaborative et visible](ddmrp-visual-and-collaborative-execution.md)**  : exécutez les commandes d’approvisionnement à l’aide de la visualisation.

Le DDMRP est généralement utilisé par les fabricants qui ont une nomenclature à plusieurs niveaux. Cependant, il peut également être appliqué aux réseaux de distribution et de vente au détail.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP dans Dynamics 365 Supply Chain Management

DDMRP est inclus avec Microsoft Dynamics 365 Supply Chain Management et ne nécessite pas de frais de licence supplémentaire. Dans Supply Chain Management, la fonctionnalité DDMRP a été ajoutée au modèle **Planification générale**. Cependant, cela nécessite que vous utilisiez le complément Optimisation de la planification. 

DDMRP est intégré aux configurations de planification existantes dans Supply Chain Management et est utilisé avec ces configurations pour arriver à la configuration de planification appropriée pour votre entreprise. Il est contrôlé par un nouveau code de couverture qui est complètement différent de la période, du min/max, de l’exigence, etc. Ce n’est pas un nouveau module et il ne remplace pas la fonctionnalité de planification existante. Cependant, cela vous donne plus de fonctionnalités à utiliser.
