---
title: Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu'il est prévu de supprimer de Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 07f37488747766dcca96884e204339b425bbd201
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597114"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="8b4ff-103">Fonctions supprimées ou obsolètes dans Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8b4ff-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b4ff-104">Cette rubrique sera mise à jour à mesure que de nouvelles fonctionnalités supprimées ou obsolètes sont documentées pour Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="8b4ff-105">Une fonction *supprimée* n'est plus disponible dans le produit.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="8b4ff-106">Une fonction *déconseillée* n'est pas en développement actif et peut être supprimée dans une prochaine mise à jour.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="8b4ff-107">Cette liste est conçue pour vous aider à prendre en compte ces suppressions et abandons pour votre propre planification.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="8b4ff-108">Des informations détaillées sur les objets dans les applications Finance and Operations sont disponibles dans les [États de référence technique](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="8b4ff-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="8b4ff-109">Vous pouvez comparer les différentes versions de ces états pour en savoir plus sur les objets qui ont été modifiés ou supprimés dans chaque version des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="8b4ff-110">Fonctions supprimées ou obsolètes dans Supply Chain Management version 10.0.11</span><span class="sxs-lookup"><span data-stu-id="8b4ff-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="8b4ff-111">Utilisation du moteur de planification Supply Chain Management intégré à des fins de distribution</span><span class="sxs-lookup"><span data-stu-id="8b4ff-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="8b4ff-112">**Motif de l'abandon/de la suppression**</span><span class="sxs-lookup"><span data-stu-id="8b4ff-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="8b4ff-113">Pour améliorer les performances et minimiser la charge de la base de données SQL lors des exécutions de planification, le moteur de planification de Supply Chain Management intégré est remplacé par l'Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="8b4ff-114">Optimisation de la planification permet des cycles de planification rapides qui peuvent être effectués même pendant les heures de bureau.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="8b4ff-115">Cela permet aux planificateurs de réagir immédiatement aux changements de la demande ou des paramètres de planification.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="8b4ff-116">**Remplacé par une autre fonctionnalité ?**</span><span class="sxs-lookup"><span data-stu-id="8b4ff-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="8b4ff-117">Oui, Optimisation de la planification remplacera le moteur de planification de Supply Chain Management existant.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="8b4ff-118">**Zones de produit affectées**</span><span class="sxs-lookup"><span data-stu-id="8b4ff-118">**Product areas affected**</span></span>         | <span data-ttu-id="8b4ff-119">Supply Chain Management - Planification</span><span class="sxs-lookup"><span data-stu-id="8b4ff-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="8b4ff-120">**Option de déploiement**</span><span class="sxs-lookup"><span data-stu-id="8b4ff-120">**Deployment option**</span></span>              | <span data-ttu-id="8b4ff-121">Cloud uniquement.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-121">Cloud only.</span></span> <span data-ttu-id="8b4ff-122">Notez que Optimisation n'est pas pris en charge avec les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="8b4ff-123">**État**</span><span class="sxs-lookup"><span data-stu-id="8b4ff-123">**Status**</span></span>                         | <span data-ttu-id="8b4ff-124">Obsolète.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-124">Deprecated.</span></span> <span data-ttu-id="8b4ff-125">En avril 2021, les scénarios de distribution ne seront plus pris en charge avec le moteur de planification Dynamics 365 Supply Chain Management intégré.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="8b4ff-126">Pour les scénarios de distribution, les clients doivent utiliser Optimisation de la planification pour les calculs de planification.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="8b4ff-127">Pour plus d'informations, voir [Documentation relative à Optimisation de la planification](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="8b4ff-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="8b4ff-128">Les clients avec des déploiements locaux de Dynamics 365 Supply Chain Management peuvent continuer à utiliser le moteur de planification de Supply Chain Management pour les scénarios de distribution après avril 2021.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="8b4ff-129">Cependant, aucune amélioration supplémentaire des fonctionnalités ne sera fournie.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="8b4ff-130">Annonces précédentes sur les fonctions supprimées ou obsolètes</span><span class="sxs-lookup"><span data-stu-id="8b4ff-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="8b4ff-131">Pour en savoir plus sur les fonctionnalités supprimées ou obsolètes dans les versions précédentes, consultez [Fonctionnalités supprimées ou obsolètes dans les versions précédentes](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="8b4ff-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
