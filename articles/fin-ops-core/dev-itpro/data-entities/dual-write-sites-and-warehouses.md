---
title: Sites et entrepôts intégrés
description: Cette rubrique décrit l'intégration des données de sites et d'entrepôts entre Finance and Operations et Common Data Service.
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
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770984"
---
# <a name="integrated-sites-and-warehouses"></a>Sites et entrepôts intégrés

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l'intégration des données de sites et d'entrepôts entre Finance and Operations et Common Data Service. Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management. Ils sont utilisés pour modéliser la chaîne d'approvisionnement de votre société.

## <a name="templates"></a>Modèles

Avec l'intégration avec Common Data Service, ces concepts et toutes les informations associées sont disponibles dans Common Data Service à l'aide des entités de données des sites et des entrepôts dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365 | Description
--------------------------|---------------------------|---
Sites | msdyn_operationalsites | 
Entrepôts | msdyn_warehouses | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

