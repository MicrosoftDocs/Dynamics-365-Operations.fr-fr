---
title: Fonctions de plateforme supprimées ou obsolètes
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087881"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="b79d9-103">Fonctions de plateforme supprimées ou obsolètes</span><span class="sxs-lookup"><span data-stu-id="b79d9-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b79d9-104">Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer dans les mises à jour de plateforme des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b79d9-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="b79d9-105">Une fonction *supprimée* n'est plus disponible dans le produit.</span><span class="sxs-lookup"><span data-stu-id="b79d9-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="b79d9-106">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b79d9-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="b79d9-107">Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="b79d9-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="b79d9-108">Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="b79d9-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="b79d9-109">Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b79d9-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="b79d9-110">Platform update 32</span><span class="sxs-lookup"><span data-stu-id="b79d9-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="b79d9-111">La boîte de dialogue de demande de modification du workflow n'inclut plus de liste déroulante de sélection de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b79d9-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="b79d9-112">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="b79d9-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="b79d9-113">Il s'agissait d'un problème de sécurité, car la demande de modification pouvait être envoyée à un utilisateur indésirable.</span><span class="sxs-lookup"><span data-stu-id="b79d9-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="b79d9-114">Il s'agissait également d'un problème d'utilisation, car cela obligeait l'utilisateur à déterminer le créateur du workflow et à le sélectionner manuellement.</span><span class="sxs-lookup"><span data-stu-id="b79d9-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="b79d9-115">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="b79d9-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="b79d9-116">Non</span><span class="sxs-lookup"><span data-stu-id="b79d9-116">No</span></span> |
| <span data-ttu-id="b79d9-117">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="b79d9-117">**Product areas affected**</span></span>         | <span data-ttu-id="b79d9-118">Workflow</span><span class="sxs-lookup"><span data-stu-id="b79d9-118">Workflow</span></span> |
| <span data-ttu-id="b79d9-119">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="b79d9-119">**Deployment option**</span></span>              | <span data-ttu-id="b79d9-120">Tous</span><span class="sxs-lookup"><span data-stu-id="b79d9-120">All</span></span> |
| <span data-ttu-id="b79d9-121">**État **</span><span class="sxs-lookup"><span data-stu-id="b79d9-121">**Status**</span></span>                         | <span data-ttu-id="b79d9-122">La liste déroulante de sélection de l'utilisateur a été supprimée de la boîte de dialogue de demande de modification dans Platform update 32.</span><span class="sxs-lookup"><span data-stu-id="b79d9-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="b79d9-123">Les demandes de modification seront automatiquement envoyées à l'expéditeur comme prévu.</span><span class="sxs-lookup"><span data-stu-id="b79d9-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="b79d9-124">Pour plus d'informations sur cette fonctionnalité, consultez [Actions dans les processus d'approbation de workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="b79d9-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="b79d9-125">Annonces précédentes sur les fonctions supprimées ou obsolètes</span><span class="sxs-lookup"><span data-stu-id="b79d9-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="b79d9-126">Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="b79d9-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

