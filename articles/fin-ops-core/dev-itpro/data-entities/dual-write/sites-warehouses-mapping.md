---
title: Sites et entrepôts intégrés
description: Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse.
author: t-benebo
manager: AnnBe
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
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560359"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="e1a1a-103">Sites et entrepôts intégrés</span><span class="sxs-lookup"><span data-stu-id="e1a1a-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="e1a1a-104">Cette rubrique décrit l’intégration des données de site et d’entrepôt entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e1a1a-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="e1a1a-105">Les sites et les entrepôts opérationnels sont des concepts courants dans une application de type Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e1a1a-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="e1a1a-106">Ils sont utilisés pour modéliser la chaîne d’approvisionnement de votre société.</span><span class="sxs-lookup"><span data-stu-id="e1a1a-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="e1a1a-107">Modèles</span><span class="sxs-lookup"><span data-stu-id="e1a1a-107">Templates</span></span>

<span data-ttu-id="e1a1a-108">Avec l’intégration avec Dataverse, ces concepts et toutes les informations associées sont disponibles dans Dataverse à l’aide des tables de données des sites et des entrepôts dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="e1a1a-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="e1a1a-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e1a1a-109">Finance and Operations apps</span></span> | <span data-ttu-id="e1a1a-110">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e1a1a-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="e1a1a-111">Description</span><span class="sxs-lookup"><span data-stu-id="e1a1a-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="e1a1a-112">Sites</span><span class="sxs-lookup"><span data-stu-id="e1a1a-112">Sites</span></span> | <span data-ttu-id="e1a1a-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="e1a1a-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="e1a1a-114">Entrepôts</span><span class="sxs-lookup"><span data-stu-id="e1a1a-114">Warehouses</span></span> | <span data-ttu-id="e1a1a-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="e1a1a-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]