---
title: Restrictions applicables aux version d’évaluation des coûts standard
description: Cet article décrit les restrictions qui s’appliquent à une version d’évaluation des coûts standard.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867983"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Restrictions applicables aux version d’évaluation des coûts standard

[!include [banner](../includes/banner.md)]

Cet article décrit les restrictions qui s’appliquent à une version d’évaluation des coûts standard. 

Les restrictions suivantes aident à garantir le respect des principes d’évaluation des coûts standard :

-  Les frais doivent être inclus dans le coût d’un article. Les frais d’un article fabriqué représentent les coûts constants amortis dans les informations de nomenclature et de gamme. Il faut donc les inclure dans le coût unitaire. Les frais d’un article acheté sont également inclus dans le coût unitaire de l’article.

-  Le calcul des coûts standard des articles fabriqués doit être basé sur les enregistrements des coûts dans une version d’évaluation des coûts standard. D’autres sources de données de coût peuvent être utilisées uniquement avec une version d’évaluation des coûts planifiés, comme les accords commerciaux de prix d’achat pour les articles achetés. D’autres sources de données de coût sont définies par le groupe de calcul de nomenclature.

-  Les calculs de nomenclature doivent être effectués en mode d’éclatement à un seul niveau.

Les données de coût de l’article pour les coûts standard peuvent être copiées dans une autre version d’évaluation des coûts qui contient des coûts standard ou des coûts planifiés. Toutefois, les données de coût d’article pour les coûts planifiés ne peuvent pas être copiées dans une version d’évaluation des coûts qui contient des coûts standard, car les restrictions répertoriées précédemment dans cet article ne s’appliquent pas aux coûts planifiés.

## <a name="related-articles"></a>Articles connexes

[Vue d’ensemble des versions d’évaluation des coûts](costing-versions.md)

[Mise à jour des coûts standard dans un environnement hors fabrication](update-standard-costs-non-manufacturing-environment.md)

[Préparation de la mise à jour des coûts standard pour les articles fabriqués](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]