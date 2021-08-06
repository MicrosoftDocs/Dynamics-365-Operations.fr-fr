---
title: Taxe intégrée
description: Cette rubrique décrit l’intégration des données de taxe entre les applications Finance and Operations et Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: e1b5d62e56dd1f87dbfedc6a8ca7379587481ff4
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542317"
---
# <a name="integrated-tax"></a>Taxe intégrée

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source. Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d’autres concepts.

## <a name="templates"></a>Modèles

Les données de taxe comprennent un ensemble de mappages de tables qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Applications Finance and Operations | Applications Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Groupe de taxe d’article](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Administrations fiscales](mapping-reference.md#193) | msdyn_taxauthorities | |
[Entité Code d’exonération fiscale pour CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Groupes de taxe](mapping-reference.md#195) | msdyn_taxgroups | |
[Groupes de validation dans la comptabilité des taxes V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Codes de retenue à la source](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Groupes de retenue à la source](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
