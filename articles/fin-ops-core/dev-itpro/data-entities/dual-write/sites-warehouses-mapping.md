---
title: Sites et entrepôts intégrés
description: Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse.
author: t-benebo
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750664"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="9e6aa-103">Sites et entrepôts intégrés</span><span class="sxs-lookup"><span data-stu-id="9e6aa-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="9e6aa-104">Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e6aa-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="9e6aa-105">Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9e6aa-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="9e6aa-106">Ils sont utilisés pour modéliser la chaîne d’approvisionnement de votre société.</span><span class="sxs-lookup"><span data-stu-id="9e6aa-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="9e6aa-107">Modèles</span><span class="sxs-lookup"><span data-stu-id="9e6aa-107">Templates</span></span>

<span data-ttu-id="9e6aa-108">Avec l’intégration avec Dataverse, ces concepts et toutes les informations associées sont disponibles dans Dataverse à l’aide des tables de données des sites et des entrepôts dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9e6aa-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="9e6aa-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9e6aa-109">Finance and Operations apps</span></span> | <span data-ttu-id="9e6aa-110">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9e6aa-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="9e6aa-111">Description</span><span class="sxs-lookup"><span data-stu-id="9e6aa-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="9e6aa-112">Sites</span><span class="sxs-lookup"><span data-stu-id="9e6aa-112">Sites</span></span> | <span data-ttu-id="9e6aa-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="9e6aa-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="9e6aa-114">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="9e6aa-114">Warehouses</span></span> | <span data-ttu-id="9e6aa-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="9e6aa-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]