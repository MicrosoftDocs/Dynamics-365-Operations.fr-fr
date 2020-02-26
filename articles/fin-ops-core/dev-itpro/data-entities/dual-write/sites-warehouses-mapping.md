---
title: Sites et entrepôts intégrés
description: Cette rubrique décrit l'intégration des données de site et d'entrepôt entre les applications Finance and Operations et Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 0f5ed58ad50df49250aa4c001401ff52d460dfa6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019775"
---
# <a name="integrated-sites-and-warehouses"></a>Sites et entrepôts intégrés

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Cette rubrique décrit l'intégration des données de site et d'entrepôt entre les applications Finance and Operations et Common Data Service. Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management. Ils sont utilisés pour modéliser la chaîne d'approvisionnement de votre société.

## <a name="templates"></a>Modèles

Avec l'intégration avec Common Data Service, ces concepts et toutes les informations associées sont disponibles dans Common Data Service à l'aide des entités de données des sites et des entrepôts dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365 | Description
--------------------------|---------------------------|---
Sites | msdyn_operationalsites | 
Entrepôts | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

