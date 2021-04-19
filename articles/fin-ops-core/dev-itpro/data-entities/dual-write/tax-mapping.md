---
title: Taxe intégrée
description: Cette rubrique décrit l’intégration des données de taxe entre les applications Finance and Operations et Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a7992520b57b4c19b6dc8e13bd8e9ffc87b40f5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750640"
---
# <a name="integrated-tax"></a>Taxe intégrée

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Les données de paramétrage de la taxe définissent le paramétrage pour les taxes indirectes (TVA, GST, taxe) et la retenue à la source. Elles décrivent la règle de calcul de taxe, le taux de taxe, la comptabilité des taxes, le règlement et d’autres concepts.

## <a name="templates"></a>Modèles

Les données de taxe comprennent un ensemble de mappages de tables qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

Applications Finance and Operations | Applications pilotées par modèle dans Dynamics 365 | Description |
-------------------------|---------------------------------|----|
Groupe de taxe d’article | msdyn_taxitemgroups |
Administrations fiscales | msdyn_taxauthorities |
Entité Code d’exonération fiscale pour CDS | msdyn_taxexemptcodes |
Groupes de taxe | msdyn_taxgroups |
Groupes de validation dans la comptabilité des taxes V2 | msdyn_taxpostinggroups |
Codes de retenue à la source | msdyn_withholdingtaxcodes |
Groupes de retenue à la source | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]