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
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="1ce71-103">Sites et entrepôts intégrés</span><span class="sxs-lookup"><span data-stu-id="1ce71-103">Integrated sites and warehouses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ce71-104">Cette rubrique décrit l'intégration des données de sites et d'entrepôts entre Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1ce71-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="1ce71-105">Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ce71-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="1ce71-106">Ils sont utilisés pour modéliser la chaîne d'approvisionnement de votre société.</span><span class="sxs-lookup"><span data-stu-id="1ce71-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="1ce71-107">Modèles</span><span class="sxs-lookup"><span data-stu-id="1ce71-107">Templates</span></span>

<span data-ttu-id="1ce71-108">Avec l'intégration avec Common Data Service, ces concepts et toutes les informations associées sont disponibles dans Common Data Service à l'aide des entités de données des sites et des entrepôts dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1ce71-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="1ce71-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1ce71-109">Finance and Operations apps</span></span> | <span data-ttu-id="1ce71-110">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1ce71-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="1ce71-111">Description</span><span class="sxs-lookup"><span data-stu-id="1ce71-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="1ce71-112">Sites</span><span class="sxs-lookup"><span data-stu-id="1ce71-112">Sites</span></span> | <span data-ttu-id="1ce71-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="1ce71-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="1ce71-114">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="1ce71-114">Warehouses</span></span> | <span data-ttu-id="1ce71-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="1ce71-115">msdyn_warehouses</span></span> | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

