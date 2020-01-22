---
title: Taxe intégrée
description: Cette rubrique décrit l'intégration des données de taxe entre Finance and Operations et Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853857"
---
# <a name="integrated-tax"></a>Taxe intégrée

[!include [banner](../includes/banner.md)]

Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source. Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d'autres concepts.

## <a name="templates"></a>Modèles

Les données de taxe comprennent un ensemble de mappages d'entités qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.

Finance and Operations   | Autres applications Dynamics 365
-------------------------|---------------------------------
Codes taxe                  | msdyn\_taxcodes.md
Groupes de taxe               | msdyn\_taxgroups.md
Groupes de taxe d'article          | msdyn\_taxitemgroups.md
Exemptions de taxe           | msdyn\_taxexemptcodes.md
Administrations fiscales          | msdyn\_taxauthorities.md
Codes de retenue à la source      | msdyn\_withholdingtaxcodes.md
Groupes de retenue à la source   | msdyn\_withholdingtaxgroups.md
Groupe de compte général de taxe | msdyn\_taxpostinggroups  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

