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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182023"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="0dbab-103">Hiérarchie d'organisation dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="0dbab-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="0dbab-104">Comme Dynamics 365 Finance est un système financier, l'*organisation* est un concept de base, et le système commence par la configuration d'une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="0dbab-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="0dbab-105">Les opérations financières et commerciales peuvent ensuite être suivies au niveau de l'organisation et également à tous les niveaux de la hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="0dbab-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="0dbab-106">Bien que Common Data Service ne dispose pas du concept de hiérarchie d'organisation, il dispose de certains concepts flous, tels que le total du produit des ventes.</span><span class="sxs-lookup"><span data-stu-id="0dbab-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="0dbab-107">Dans le cadre de l'intégration de Common Data Service, la structure de données de la hiérarchie d'organisation est ajoutée à Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0dbab-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="0dbab-108">Flux de données</span><span class="sxs-lookup"><span data-stu-id="0dbab-108">Data flow</span></span>

<span data-ttu-id="0dbab-109">Écosystème commercial composé des applications Finance and Operations et Common Data Service continue d'avoir une hiérarchie d'organisation.</span><span class="sxs-lookup"><span data-stu-id="0dbab-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="0dbab-110">Cette hiérarchie d'organisation repose sur les applications Finance and Operations, mais elle est exposée dans Common Data Service à des fins d'informations et d'extensibilité.</span><span class="sxs-lookup"><span data-stu-id="0dbab-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="0dbab-111">L'illustration suivante présente les informations de la hiérarchie d'organisation exposées dans Common Data Service comme un flux unidirectionnel entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0dbab-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Image de l'architecture](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="0dbab-113">Modèles</span><span class="sxs-lookup"><span data-stu-id="0dbab-113">Templates</span></span>

<span data-ttu-id="0dbab-114">Des mises en correspondance de l'entité Hiérarchie d'organisation sont disponibles pour la synchronisation unidirectionnelle des données entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0dbab-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="0dbab-115">Objectif de la hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="0dbab-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="0dbab-116">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Objet de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0dbab-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="0dbab-117">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-117">Source field</span></span> | <span data-ttu-id="0dbab-118">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-118">Map type</span></span> | <span data-ttu-id="0dbab-119">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-119">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="0dbab-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="0dbab-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="0dbab-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="0dbab-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="0dbab-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="0dbab-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="0dbab-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="0dbab-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="0dbab-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="0dbab-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="0dbab-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="0dbab-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="0dbab-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="0dbab-127">msdyn\_immutable</span></span>
<span data-ttu-id="0dbab-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0dbab-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="0dbab-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="0dbab-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="0dbab-130">Type de hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="0dbab-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="0dbab-131">Ce modèle fournit une synchronisation unidirectionnelle de l'entité Type de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0dbab-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="0dbab-132">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-132">Source field</span></span> | <span data-ttu-id="0dbab-133">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-133">Map type</span></span> | <span data-ttu-id="0dbab-134">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-134">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-135">NOM</span><span class="sxs-lookup"><span data-stu-id="0dbab-135">NAME</span></span> | \> | <span data-ttu-id="0dbab-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="0dbab-137">Hiérarchie d'organisation interne</span><span class="sxs-lookup"><span data-stu-id="0dbab-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="0dbab-138">Ce modèle fournit une synchronisation unidirectionnelle de l'entité publiée de la hiérarchie d'organisation entre Finance and Operations et d'autres applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0dbab-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="0dbab-139">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-139">Source field</span></span> | <span data-ttu-id="0dbab-140">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-140">Map type</span></span> | <span data-ttu-id="0dbab-141">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-141">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="0dbab-142">VALIDTO</span></span> | \> | <span data-ttu-id="0dbab-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="0dbab-143">msdyn\_validto</span></span>
<span data-ttu-id="0dbab-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="0dbab-144">VALIDFROM</span></span> | \> | <span data-ttu-id="0dbab-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="0dbab-145">msdyn\_validfrom</span></span>
<span data-ttu-id="0dbab-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="0dbab-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="0dbab-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="0dbab-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="0dbab-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="0dbab-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="0dbab-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="0dbab-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="0dbab-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="0dbab-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="0dbab-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="0dbab-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="0dbab-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="0dbab-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="0dbab-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="0dbab-158">Organisation interne</span><span class="sxs-lookup"><span data-stu-id="0dbab-158">Internal Organization</span></span>

<span data-ttu-id="0dbab-159">Les informations d'organisation internes dans Common Data Service proviennent de deux entités, **unité opérationnelle** et **entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="0dbab-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="0dbab-160">Unité opérationnelle</span><span class="sxs-lookup"><span data-stu-id="0dbab-160">Operating unit</span></span>

<span data-ttu-id="0dbab-161">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-161">Source field</span></span> | <span data-ttu-id="0dbab-162">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-162">Map type</span></span> | <span data-ttu-id="0dbab-163">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-163">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="0dbab-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="0dbab-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="0dbab-165">msdyn\_languageid</span></span>
<span data-ttu-id="0dbab-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="0dbab-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="0dbab-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="0dbab-167">msdyn\_namealias</span></span>
<span data-ttu-id="0dbab-168">NOM</span><span class="sxs-lookup"><span data-stu-id="0dbab-168">NAME</span></span> | \> | <span data-ttu-id="0dbab-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-169">msdyn\_name</span></span>
<span data-ttu-id="0dbab-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="0dbab-171">msdyn\_partynumber</span></span>
<span data-ttu-id="0dbab-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="0dbab-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="0dbab-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="0dbab-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="0dbab-174">Entité juridique</span><span class="sxs-lookup"><span data-stu-id="0dbab-174">Legal entity</span></span>

<span data-ttu-id="0dbab-175">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-175">Source field</span></span> | <span data-ttu-id="0dbab-176">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-176">Map type</span></span> | <span data-ttu-id="0dbab-177">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-177">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="0dbab-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="0dbab-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="0dbab-179">msdyn\_namealias</span></span>
<span data-ttu-id="0dbab-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="0dbab-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="0dbab-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="0dbab-181">msdyn\_languageid</span></span>
<span data-ttu-id="0dbab-182">NOM</span><span class="sxs-lookup"><span data-stu-id="0dbab-182">NAME</span></span> | \> | <span data-ttu-id="0dbab-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-183">msdyn\_name</span></span>
<span data-ttu-id="0dbab-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="0dbab-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="0dbab-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="0dbab-185">msdyn\_partynumber</span></span>
<span data-ttu-id="0dbab-186">aucun</span><span class="sxs-lookup"><span data-stu-id="0dbab-186">none</span></span> | \>\> | <span data-ttu-id="0dbab-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="0dbab-187">msdyn\_type</span></span>
<span data-ttu-id="0dbab-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="0dbab-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="0dbab-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="0dbab-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="0dbab-190">Société</span><span class="sxs-lookup"><span data-stu-id="0dbab-190">Company</span></span>

<span data-ttu-id="0dbab-191">Fournit la synchronisation bidirectionnelle d'informations sur l'entité juridique (société) entre Finance and Operations et d'autres applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0dbab-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="0dbab-192">Champ source</span><span class="sxs-lookup"><span data-stu-id="0dbab-192">Source field</span></span> | <span data-ttu-id="0dbab-193">Type de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="0dbab-193">Map type</span></span> | <span data-ttu-id="0dbab-194">Champ de destination</span><span class="sxs-lookup"><span data-stu-id="0dbab-194">Destination field</span></span>
---|---|---
<span data-ttu-id="0dbab-195">NOM</span><span class="sxs-lookup"><span data-stu-id="0dbab-195">NAME</span></span> | = | <span data-ttu-id="0dbab-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="0dbab-196">cdm\_name</span></span>
<span data-ttu-id="0dbab-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="0dbab-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="0dbab-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="0dbab-198">cdm\_companycode</span></span>
