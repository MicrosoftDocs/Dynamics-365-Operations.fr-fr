---
title: Taxe intégrée
description: Cet article décrit l’intégration des données de taxe entre les applications de finances et d’opérations et Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 29d8b2079b5d1cd70f14e096780f83a4a38d4b63
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111534"
---
# <a name="integrated-tax"></a>Taxe intégrée

[!include [banner](../../includes/banner.md)]



Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source. Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d’autres concepts.

## <a name="templates"></a>Modèles

Les données de taxe comprennent un ensemble de mappages de tables qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Applications de finances et d'opérations | Applications Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Groupe de taxe d’article](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Administrations fiscales](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entité Code d’exonération fiscale pour CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Groupes de taxe](mapping-reference.md#195) | msdyn_taxgroups | |
[Groupes de validation dans la comptabilité des taxes V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Codes de retenue à la source](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Groupes de retenue à la source](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

