---
title: Sites et entrepôts intégrés
description: Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse.
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
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679318"
---
# <a name="integrated-sites-and-warehouses"></a>Sites et entrepôts intégrés

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse. Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management. Ils sont utilisés pour modéliser la chaîne d’approvisionnement de votre société.

## <a name="templates"></a>Modèles

Avec l’intégration avec Dataverse, ces concepts et toutes les informations associées sont disponibles dans Dataverse à l’aide des tables de données des sites et des entrepôts dans le tableau suivant.

Applications Finance and Operations | Autres applications Dynamics 365 | Description
--------------------------|---------------------------|---
Sites | msdyn_operationalsites | 
Entrepôts | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]