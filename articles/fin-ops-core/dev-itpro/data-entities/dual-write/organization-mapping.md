---
title: Hiérarchie d'organisation dans Common Data Service
description: Cette rubrique décrit l'intégration des données organisationnelles entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000732"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="fc982-103">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fc982-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc982-104">Comme Dynamics 365 Finance est un système financier, l' *organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="fc982-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="fc982-105">Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="fc982-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="fc982-106">Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes.</span><span class="sxs-lookup"><span data-stu-id="fc982-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="fc982-107">Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fc982-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="fc982-108">Flux de données</span><span class="sxs-lookup"><span data-stu-id="fc982-108">Data flow</span></span>

<span data-ttu-id="fc982-109">Un écosystème commercial composé des applications Finance and Operations et de Common Data Service continue d'avoir une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="fc982-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="fc982-110">Cette hiérarchie d'organisation repose sur les applications Finance and Operations, mais elle est exposée dans Common Data Service à des fins d'informations et d'extensibilité.</span><span class="sxs-lookup"><span data-stu-id="fc982-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="fc982-111">L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fc982-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Image de l'architecture](media/dual-write-data-flow.png)

<span data-ttu-id="fc982-113">Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fc982-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="fc982-114">Modèles</span><span class="sxs-lookup"><span data-stu-id="fc982-114">Templates</span></span>

<span data-ttu-id="fc982-115">Les informations de produit contiennent toutes les informations associées au produit et à sa définition, comme les dimensions du produit ou les dimensions de suivi et de stockage.</span><span class="sxs-lookup"><span data-stu-id="fc982-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="fc982-116">Lorsque le tableau suivant s'affiche, un ensemble de cartes d'entité est créé pour synchroniser les produits et les informations associées.</span><span class="sxs-lookup"><span data-stu-id="fc982-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="fc982-117">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fc982-117">Finance and Operations apps</span></span> | <span data-ttu-id="fc982-118">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fc982-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="fc982-119">Description</span><span class="sxs-lookup"><span data-stu-id="fc982-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="fc982-120">Objectifs de la hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="fc982-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="fc982-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="fc982-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="fc982-122">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objectif de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="fc982-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="fc982-123">Type de la hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="fc982-123">Organization hierarchy type</span></span> | <span data-ttu-id="fc982-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="fc982-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="fc982-125">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="fc982-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="fc982-126">Hiérarchie d'organisation - publiée</span><span class="sxs-lookup"><span data-stu-id="fc982-126">Organization hierarchy - published</span></span> | <span data-ttu-id="fc982-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="fc982-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="fc982-128">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Hiérarchie d'organisation publiée.</span><span class="sxs-lookup"><span data-stu-id="fc982-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="fc982-129">Unité opérationnelle</span><span class="sxs-lookup"><span data-stu-id="fc982-129">Operating unit</span></span> | <span data-ttu-id="fc982-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="fc982-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="fc982-131">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="fc982-131">Legal entities</span></span> | <span data-ttu-id="fc982-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="fc982-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="fc982-133">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="fc982-133">Legal entities</span></span> | <span data-ttu-id="fc982-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="fc982-134">cdm_companies</span></span> | <span data-ttu-id="fc982-135">Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société).</span><span class="sxs-lookup"><span data-stu-id="fc982-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="fc982-136">Organisation interne</span><span class="sxs-lookup"><span data-stu-id="fc982-136">Internal Organization</span></span>

<span data-ttu-id="fc982-137">Les informations d'organisation internes dans Common Data Service proviennent de deux entités, **unité opérationnelle** et **entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="fc982-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
