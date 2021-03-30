---
title: Mappage de membres de dimension d’élément de coût à un ensemble commun de membres de dimension
description: En mappant différents membres de la dimension d’élément de coût à un ensemble commun de membres de la dimension d’élément de coût, vous fusionnez les données en un format commun à des fins de analyse.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eb752ef853aedbe492dc2880b90d1683c5433a12
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217360"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Mappage de membres de dimension d’élément de coût à un ensemble commun de membres de dimension

[!include [banner](../includes/banner.md)]

En mappant différents membres de la dimension d’élément de coût à un ensemble commun de membres de la dimension d’élément de coût, vous fusionnez les données en un format commun à des fins de analyse.

Si vous êtes une société internationale et que vous vous conformez aux besoins statutaires de comptabilité, vous pouvez utiliser plusieurs plans de comptes. Lorsque vous importez des membres de la dimension d’article des coûts de différents plans de comptes, vous pouvez vous retrouver avec une combinaison de comptes. Toutefois, ces comptes peuvent en fait être de même nature, et vous pouvez analyser et répartir les coûts associés à l’aide d’un format courant.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mapper les membres de la dimension d’élément de coût à un format commun
L’exemple suivant illustre comment vous, contrôleur de coût, pouvez créer une nouvelle dimension d’élément de coût dans le contrôle de gestion qui mappe des membres de la dimension d’élément de coût dans la structure du plan de comptes américain et la structure de plan de comptes française à un ensemble commun de membres de la dimension d’élément de coût. Vous pouvez ensuite utiliser l’ensemble commun de membres de la dimension d’élément de coût pour analyser les données de coût des deux entités juridiques dans la comptabilité de contrôle de gestion.

| Source : Plan de comptes américain                                          | Source : Plan de comptes français                                          | Nouvel ensemble commun de membres de la dimension d’élément de coût                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Membres de dimension d’élément de coût importés du plan de comptes américain | Membres de dimension d’élément de coût importés du plan de comptes français | Mappage des membres de dimension d’élément de coût américains et français à un ensemble commun |
| 5001 : Ventes                                                           | 5001 : Ventes et publicité                                               | 5000 : Ventes et publicité                                             |
| 5030 : Publicité                                                     | 6390 : Achat d’actions\*                                                    | 7000 : Dépenses de nettoyage                                                 |
| 7001 : Dépenses de nettoyage                                               | 7001 : Dépenses de déplacements                                                      | 7001 : Dépenses de déplacements                                                   |

\*Le membre de dimension de l’élément du coût d’achat d’actions français n’est pas mappé.

## <a name="currency-conversion"></a>Conversion de devise
Les différents plans de comptes que vous utilisez peuvent être paramétrés pour utiliser plusieurs devises. Dans ce cas, assurez-vous de spécifier une conversion de devise, afin que les données de coût soient traitées à l’aide de la devise appropriée, comme défini dans la comptabilité de contrôle de gestion dans laquelle les membres de la dimension d’élément de coût sont utilisés. Dans l’exemple précédent, si les dollars américains (USD) sont utilisés dans la comptabilité de contrôle de gestion, vous devez créer une conversion de devise des USD en euro (EUR) pour traiter les transactions des membres de dimension d’élément de coût mappés.

## <a name="update-mappings-at-any-time"></a>Mettre à jour les mappages à tout moment
Vous pouvez mettre à jour les définitions de mappage pour une dimension d’article de coût à tout moment. Comme les mappages n’ont pas de dates d’effet, les modifications sont appliquées la prochaine fois que vous exécutez des transactions de coût ou des calculs de coûts.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]