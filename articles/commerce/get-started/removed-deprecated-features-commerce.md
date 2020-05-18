---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Commerce
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335274"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="1d9e4-103">Fonctions supprimées ou obsolètes dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1d9e4-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d9e4-104">Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="1d9e4-105">Une fonction *supprimée* n'est plus disponible dans le produit.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="1d9e4-106">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="1d9e4-107">Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="1d9e4-108">Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="1d9e4-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="1d9e4-109">Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="1d9e4-110">Fonctions supprimées ou obsolètes dans Commerce version 10.0.10</span><span class="sxs-lookup"><span data-stu-id="1d9e4-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="1d9e4-111">Fonctionnement PDV 803 - Prélèvement et réception</span><span class="sxs-lookup"><span data-stu-id="1d9e4-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="1d9e4-112">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="1d9e4-113">Les opérations de prélèvement et de réception sont obsolètes en raison de la nouvelle conception de l'opération.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="1d9e4-114">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="1d9e4-115">Oui.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-115">Yes.</span></span> <span data-ttu-id="1d9e4-116">Il est remplacé par deux nouvelles opérations PDV : l'opération entrante (804) et l'opération sortante (805).</span><span class="sxs-lookup"><span data-stu-id="1d9e4-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="1d9e4-117">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-117">**Product areas affected**</span></span>         | <span data-ttu-id="1d9e4-118">Application Point De Vente (PDV)</span><span class="sxs-lookup"><span data-stu-id="1d9e4-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="1d9e4-119">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-119">**Deployment option**</span></span>              | <span data-ttu-id="1d9e4-120">Tout</span><span class="sxs-lookup"><span data-stu-id="1d9e4-120">All</span></span> |
| <span data-ttu-id="1d9e4-121">**État**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-121">**Status**</span></span>                         | <span data-ttu-id="1d9e4-122">Obsolète : à partir de la version 10.0.10, l'opération de prélèvement et de réception ne recevra plus de nouvelles mises à jour de fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="1d9e4-123">Seules les corrections de bogues critiques seront effectuées pour cette opération dans les versions futures.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="1d9e4-124">Tous les clients sont encouragés à passer aux nouvelles [Opérations entrantes](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) et [Opérations sortantes](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), qui continueront à faire partie de notre feuille de route des produits à long terme.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="1d9e4-125">Fonctions supprimées ou obsolètes dans Commerce version 10.0.7</span><span class="sxs-lookup"><span data-stu-id="1d9e4-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="1d9e4-126">API Commerce GetProductAvailabilities et GetAvailableInventoryNearby</span><span class="sxs-lookup"><span data-stu-id="1d9e4-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="1d9e4-127">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="1d9e4-128">Ces nouvelles API optimisées ont été créées pour remplacer les API GetProductAvailabilities et GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="1d9e4-129">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="1d9e4-130">Oui : remplacement par les API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="1d9e4-131">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-131">**Product areas affected**</span></span>         | <span data-ttu-id="1d9e4-132">SDK d'application e-Commerce</span><span class="sxs-lookup"><span data-stu-id="1d9e4-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="1d9e4-133">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-133">**Deployment option**</span></span>              | <span data-ttu-id="1d9e4-134">Tout</span><span class="sxs-lookup"><span data-stu-id="1d9e4-134">All</span></span> |
| <span data-ttu-id="1d9e4-135">**État**</span><span class="sxs-lookup"><span data-stu-id="1d9e4-135">**Status**</span></span>                         | <span data-ttu-id="1d9e4-136">Obsolète : à compter de la version 10.0.7, il n'y aura plus d'investissement d'ingénierie pour GetProductAvailabilities et GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="1d9e4-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="1d9e4-137">Les organisations qui utilisent ces API dans leurs déploiements de commerce électronique doivent passer aux nouvelles API GetEstimatedAvailabilty et GetEstimatedProductWarehouseAvailability et activer la [fonction de calcul de la disponibilité des produits optimisée](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="1d9e4-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="1d9e4-138">Annonces précédentes sur les fonctions supprimées ou obsolètes</span><span class="sxs-lookup"><span data-stu-id="1d9e4-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="1d9e4-139">Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="1d9e4-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
