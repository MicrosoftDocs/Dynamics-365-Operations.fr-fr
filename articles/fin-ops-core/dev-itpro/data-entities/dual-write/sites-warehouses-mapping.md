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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997622"
---
# <a name="integrated-sites-and-warehouses"></a>Sites et entrepôts intégrés

[!include [banner](../../includes/banner.md)]



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

