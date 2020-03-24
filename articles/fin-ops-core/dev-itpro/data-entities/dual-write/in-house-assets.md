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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: d931811e9fbea3c10f83b048a3c3fbeda5396d39
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112439"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="8017a-103">Actifs internes pour la maintenance</span><span class="sxs-lookup"><span data-stu-id="8017a-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="8017a-104">Microsoft Dynamics 365 Field Service est conçu pour servir les actifs des clients.</span><span class="sxs-lookup"><span data-stu-id="8017a-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="8017a-105">La gestion d'actifs pour Dynamics 365 Supply Chain Management est conçu pour maintenir les actifs internes.</span><span class="sxs-lookup"><span data-stu-id="8017a-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="8017a-106">L'intégration de ces deux applications vous permet d'utiliser Field Service pour gérer à la fois les actifs des clients et les actifs internes.</span><span class="sxs-lookup"><span data-stu-id="8017a-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="8017a-107">Vous pouvez également classer les actifs, en fonction de l'emplacement fonctionnel ou de la hiérarchie, et suivre la maintenance à un niveau détaillé.</span><span class="sxs-lookup"><span data-stu-id="8017a-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="8017a-108">Pour plus d'informations, voir [Intégrer Dynamics 365 Field Service et Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="8017a-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="8017a-109">Modèles</span><span class="sxs-lookup"><span data-stu-id="8017a-109">Templates</span></span>

<span data-ttu-id="8017a-110">Les actifs internes incluent un ensemble de mappages d'entités de base qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8017a-110">In-house-assets include a collection of core entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="8017a-111">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8017a-111">Finance and Operations apps</span></span> | <span data-ttu-id="8017a-112">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8017a-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="8017a-113">Description </span><span class="sxs-lookup"><span data-stu-id="8017a-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="8017a-114">Gestion des actifs  Actifs  Modèles de cycle de vie</span><span class="sxs-lookup"><span data-stu-id="8017a-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="8017a-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="8017a-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="8017a-116">Gestion des actifs  Actifs  Statuts du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="8017a-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="8017a-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="8017a-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="8017a-118">Gestion des actifs  Actifs</span><span class="sxs-lookup"><span data-stu-id="8017a-118">Asset management assets</span></span> | <span data-ttu-id="8017a-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="8017a-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="8017a-120">Gestion des actifs  Types d'actifs</span><span class="sxs-lookup"><span data-stu-id="8017a-120">Asset management asset types</span></span> | <span data-ttu-id="8017a-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="8017a-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="8017a-122">Gestion des actifs  Postes techniques  Modèles de cycle de vie</span><span class="sxs-lookup"><span data-stu-id="8017a-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="8017a-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="8017a-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="8017a-124">Gestion des actifs  Postes techniques  Statuts du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="8017a-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="8017a-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="8017a-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="8017a-126">Gestion des actifs  Postes techniques</span><span class="sxs-lookup"><span data-stu-id="8017a-126">Asset management functional locations</span></span> | <span data-ttu-id="8017a-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="8017a-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="8017a-128">Gestion des actifs  Types de postes techniques</span><span class="sxs-lookup"><span data-stu-id="8017a-128">Asset management functional location types</span></span> | <span data-ttu-id="8017a-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="8017a-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="8017a-130">Gestion des actifs  Fabricants</span><span class="sxs-lookup"><span data-stu-id="8017a-130">Asset management manufacturers</span></span> | <span data-ttu-id="8017a-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="8017a-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="8017a-132">Modèles de gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="8017a-132">Asset management models</span></span> | <span data-ttu-id="8017a-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="8017a-133">msdyn\_models</span></span> | |
| <span data-ttu-id="8017a-134">Garantie de la gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="8017a-134">Asset management warranty</span></span> | <span data-ttu-id="8017a-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="8017a-135">msdyn\_warranties</span></span> | |

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
