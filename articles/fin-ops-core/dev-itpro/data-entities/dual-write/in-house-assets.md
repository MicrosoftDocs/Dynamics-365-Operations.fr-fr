---
title: Actifs internes pour la maintenance
description: Cet article décrit comment vous pouvez utiliser Microsoft Dynamics 365 Field Service pour gérer à la fois les actifs des clients et les actifs internes.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: b3e741c85fcad2abc18879280ef7332ae091c984
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289248"
---
# <a name="in-house-assets-for-servicing"></a>Actifs internes pour la maintenance

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service est conçu pour servir les actifs des clients. La gestion d’actifs pour Dynamics 365 Supply Chain Management est conçu pour maintenir les actifs internes. L’intégration de ces deux applications vous permet d’utiliser Field Service pour gérer à la fois les actifs des clients et les actifs internes. Vous pouvez également classer les actifs, en fonction de l’emplacement fonctionnel ou de la hiérarchie, et suivre la maintenance à un niveau détaillé.

Pour plus d’informations, voir [Intégrer Dynamics 365 Field Service et Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modèles

Les actifs internes incluent un ensemble de mappages de tables de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Applications de finances et d'opérations | Applications Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Gestion des actifs Actifs Modèles de cycle de vie](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Gestion des actifs Actifs Statuts du cycle de vie](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Gestion des actifs Types d’actifs](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Gestion des actifs Actifs](mapping-reference.md#125) | msdyn_customerassets | |
[Gestion des actifs Postes techniques Modèles de cycle de vie](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Gestion des actifs Postes techniques Statuts du cycle de vie](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Gestion des actifs Types de postes techniques](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Gestion des actifs Postes techniques](mapping-reference.md#136) | msdyn_functionallocations | |
[Gestion des actifs Fabricants](mapping-reference.md#153) | msdyn_manufacturers | |
[Modèles de gestion des actifs](mapping-reference.md#154) | msdyn_models | |
[Garantie de la gestion des actifs](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
