---
title: Actifs internes pour la maintenance
description: Cette rubrique décrit comment vous pouvez utiliser Microsoft Dynamics 365 Field Service pour gérer à la fois les actifs des clients et les actifs internes.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941412"
---
# <a name="in-house-assets-for-servicing"></a>Actifs internes pour la maintenance

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service est conçu pour servir les actifs des clients. La gestion d’actifs pour Dynamics 365 Supply Chain Management est conçu pour maintenir les actifs internes. L’intégration de ces deux applications vous permet d’utiliser Field Service pour gérer à la fois les actifs des clients et les actifs internes. Vous pouvez également classer les actifs, en fonction de l’emplacement fonctionnel ou de la hiérarchie, et suivre la maintenance à un niveau détaillé.

Pour plus d’informations, voir [Intégrer Dynamics 365 Field Service et Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modèles

Les actifs internes incluent un ensemble de mappages de tables de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Applications Finance and Operations | Applications pilotées par modèle dans Dynamics 365 | Description |
|-----------------------------|-----------------------------------|-------------|
| Gestion des actifs Actifs Modèles de cycle de vie | msdyn\_assetlifecyclemodels | |
| Gestion des actifs Actifs Statuts du cycle de vie | msdyn\_assetlifecyclestates | |
| Gestion des actifs Actifs | msdyn\_customerassets | |
| Gestion des actifs Types d’actifs | msdyn\_customerassetcategories | |
| Gestion des actifs Postes techniques Modèles de cycle de vie | msdyn\_functionallocationlifecyclemodels | |
| Gestion des actifs Postes techniques Statuts du cycle de vie | msdyn\_functionallocationlifecyclestates | |
| Gestion des actifs Postes techniques | msdyn\_functionallocations | |
| Gestion des actifs Types de postes techniques | msdyn\_functionallocationtypes | |
| Gestion des actifs Fabricants | msdyn\_manufacturers | |
| Modèles de gestion des actifs | msdyn\_models | |
| Garantie de la gestion des actifs | msdyn\_warranties | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]