---
title: Actifs internes pour la maintenance
description: Cette rubrique décrit comment vous pouvez utiliser Microsoft Dtnamics 365 Field Service pour gérer à la fois les actifs client et les actifs internes.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 0e87a3d645c19fab3bb0560ba5114d193e2d0be7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997168"
---
# <a name="in-house-assets-for-servicing"></a>Actifs internes pour la maintenance

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service est conçu pour servir les actifs des clients. La gestion d'actifs pour Dynamics 365 Supply Chain Management est conçu pour maintenir les actifs internes. L'intégration de ces deux applications vous permet d'utiliser Field Service pour gérer à la fois les actifs des clients et les actifs internes. Vous pouvez également classer les actifs, en fonction de l'emplacement fonctionnel ou de la hiérarchie, et suivre la maintenance à un niveau détaillé.

Pour plus d'informations, voir [Intégrer Dynamics 365 Field Service et Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modèles

Les actifs internes incluent un ensemble de mappages d'entités de base qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.

| Applications Finance and Operations | Applications pilotées par modèle dans Dynamics 365 | Description  |
|-----------------------------|-----------------------------------|-------------|
| Gestion des actifs  Actifs  Modèles de cycle de vie | msdyn\_assetlifecyclemodels | |
| Gestion des actifs  Actifs  Statuts du cycle de vie | msdyn\_assetlifecyclestates | |
| Gestion des actifs  Actifs | msdyn\_customerassets | |
| Gestion des actifs  Types d'actifs | msdyn\_customerassetcategories | |
| Gestion des actifs  Postes techniques  Modèles de cycle de vie | msdyn\_functionallocationlifecyclemodels | |
| Gestion des actifs  Postes techniques  Statuts du cycle de vie | msdyn\_functionallocationlifecyclestates | |
| Gestion des actifs  Postes techniques | msdyn\_functionallocations | |
| Gestion des actifs  Types de postes techniques | msdyn\_functionallocationtypes | |
| Gestion des actifs  Fabricants | msdyn\_manufacturers | |
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
