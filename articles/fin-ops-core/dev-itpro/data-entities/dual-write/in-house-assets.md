---
title: Actifs internes pour la maintenance
description: Cette rubrique décrit comment vous pouvez utiliser Microsoft Dtnamics 365 Field Service pour gérer à la fois les actifs client et les actifs internes.
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
ms.openlocfilehash: 040f9d26a137ebce1edc6adf28ff226b3a81e1ae
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748591"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="1ed96-103">Actifs internes pour la maintenance</span><span class="sxs-lookup"><span data-stu-id="1ed96-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="1ed96-104">Microsoft Dynamics 365 Field Service est conçu pour servir les actifs des clients.</span><span class="sxs-lookup"><span data-stu-id="1ed96-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="1ed96-105">La gestion d’actifs pour Dynamics 365 Supply Chain Management est conçu pour maintenir les actifs internes.</span><span class="sxs-lookup"><span data-stu-id="1ed96-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="1ed96-106">L’intégration de ces deux applications vous permet d’utiliser Field Service pour gérer à la fois les actifs des clients et les actifs internes.</span><span class="sxs-lookup"><span data-stu-id="1ed96-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="1ed96-107">Vous pouvez également classer les actifs, en fonction de l’emplacement fonctionnel ou de la hiérarchie, et suivre la maintenance à un niveau détaillé.</span><span class="sxs-lookup"><span data-stu-id="1ed96-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="1ed96-108">Pour plus d’informations, voir [Intégrer Dynamics 365 Field Service et Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="1ed96-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="1ed96-109">Modèles</span><span class="sxs-lookup"><span data-stu-id="1ed96-109">Templates</span></span>

<span data-ttu-id="1ed96-110">Les actifs internes incluent un ensemble de mappages de tables de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1ed96-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="1ed96-111">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1ed96-111">Finance and Operations apps</span></span> | <span data-ttu-id="1ed96-112">Applications pilotées par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1ed96-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="1ed96-113">Description</span><span class="sxs-lookup"><span data-stu-id="1ed96-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="1ed96-114">Gestion des actifs Actifs Modèles de cycle de vie</span><span class="sxs-lookup"><span data-stu-id="1ed96-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="1ed96-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="1ed96-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="1ed96-116">Gestion des actifs Actifs Statuts du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="1ed96-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="1ed96-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="1ed96-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="1ed96-118">Gestion des actifs Actifs</span><span class="sxs-lookup"><span data-stu-id="1ed96-118">Asset management assets</span></span> | <span data-ttu-id="1ed96-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="1ed96-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="1ed96-120">Gestion des actifs Types d’actifs</span><span class="sxs-lookup"><span data-stu-id="1ed96-120">Asset management asset types</span></span> | <span data-ttu-id="1ed96-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="1ed96-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="1ed96-122">Gestion des actifs Postes techniques Modèles de cycle de vie</span><span class="sxs-lookup"><span data-stu-id="1ed96-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="1ed96-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="1ed96-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="1ed96-124">Gestion des actifs Postes techniques Statuts du cycle de vie</span><span class="sxs-lookup"><span data-stu-id="1ed96-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="1ed96-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="1ed96-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="1ed96-126">Gestion des actifs Postes techniques</span><span class="sxs-lookup"><span data-stu-id="1ed96-126">Asset management functional locations</span></span> | <span data-ttu-id="1ed96-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="1ed96-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="1ed96-128">Gestion des actifs Types de postes techniques</span><span class="sxs-lookup"><span data-stu-id="1ed96-128">Asset management functional location types</span></span> | <span data-ttu-id="1ed96-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="1ed96-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="1ed96-130">Gestion des actifs Fabricants</span><span class="sxs-lookup"><span data-stu-id="1ed96-130">Asset management manufacturers</span></span> | <span data-ttu-id="1ed96-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="1ed96-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="1ed96-132">Modèles de gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="1ed96-132">Asset management models</span></span> | <span data-ttu-id="1ed96-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="1ed96-133">msdyn\_models</span></span> | |
| <span data-ttu-id="1ed96-134">Garantie de la gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="1ed96-134">Asset management warranty</span></span> | <span data-ttu-id="1ed96-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="1ed96-135">msdyn\_warranties</span></span> | |

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